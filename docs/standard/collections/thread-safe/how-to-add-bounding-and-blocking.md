---
title: "방법: 컬렉션에 한계 지정 및 차단 기능 추가"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- thread-safe collections, custom blocking collections
ms.assetid: 4c2492de-3876-4873-b5a1-000bb404d770
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 7fe57d99382c3472d0af5e5f64f7b237692b921b
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-add-bounding-and-blocking-functionality-to-a-collection"></a><span data-ttu-id="28531-102">방법: 컬렉션에 한계 지정 및 차단 기능 추가</span><span class="sxs-lookup"><span data-stu-id="28531-102">How to: Add Bounding and Blocking Functionality to a Collection</span></span>
<span data-ttu-id="28531-103">이 예제에서는 클래스에서 <xref:System.Collections.Concurrent.IProducerConsumerCollection%601?displayProperty=nameWithType> 인터페이스를 구현한 다음 클래스 인스턴스를 <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType>의 내부 저장소 메커니즘으로 사용하여 사용자 지정 컬렉션 클래스에 한계 지정 및 차단 기능을 추가하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="28531-103">This example shows how to add bounding and blocking functionality to a custom collection class by implementing the <xref:System.Collections.Concurrent.IProducerConsumerCollection%601?displayProperty=nameWithType> interface in the class, and then using a class instance as the internal storage mechanism for a <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType>.</span></span> <span data-ttu-id="28531-104">한계 지정 및 차단에 대한 자세한 내용은 [BlockingCollection 개요](../../../../docs/standard/collections/thread-safe/blockingcollection-overview.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="28531-104">For more information about bounding and blocking, see [BlockingCollection Overview](../../../../docs/standard/collections/thread-safe/blockingcollection-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="28531-105">예</span><span class="sxs-lookup"><span data-stu-id="28531-105">Example</span></span>  
 <span data-ttu-id="28531-106">사용자 지정 컬렉션 클래스는 우선 순위 수준이 <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType>개 개체의 배열로 표시되는 기본 우선 순위 큐입니다.</span><span class="sxs-lookup"><span data-stu-id="28531-106">The custom collection class is a basic priority queue in which the priority levels are represented as an array of <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType> objects.</span></span> <span data-ttu-id="28531-107">각 큐 내에서 추가로 정렬이 수행되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="28531-107">No additional ordering is performed within each queue.</span></span>  
  
 <span data-ttu-id="28531-108">클라이언트 코드에서 다음 세 가지 작업이 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="28531-108">In the client code, three tasks are started.</span></span> <span data-ttu-id="28531-109">첫 번째 작업은 실행 중 언제든지 취소할 수 있도록 키보드 스트로크를 폴링합니다.</span><span class="sxs-lookup"><span data-stu-id="28531-109">The first task just polls for keyboard strokes to enable cancellation at any point during execution.</span></span> <span data-ttu-id="28531-110">두 번째 작업은 공급자 스레드입니다. 이 작업에서는 새 항목을 차단 컬렉션에 추가하고 임의 값에 기반하여 각 항목에 우선 순위를 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="28531-110">The second task is the producer thread; it adds new items to the blocking collection and gives each item a priority based on a random value.</span></span> <span data-ttu-id="28531-111">세 번째 작업은 컬렉션에서 제공되는 대로 항목을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="28531-111">The third task removes items from the collection as they become available.</span></span>  
  
 <span data-ttu-id="28531-112">이러한 스레드 중 하나가 다른 스레드보다 빠르게 실행되도록 함으로써 응용 프로그램의 동작을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="28531-112">You can adjust the behavior of the application by making one of the threads run faster than the other.</span></span> <span data-ttu-id="28531-113">공급자가 더 빠르게 실행되는 경우 차단 컬렉션에 포함된 항목이 생성자에 지정한 항목 개수에 이미 도달되었으면 한계 지정 기능으로 인해 항목이 차단 컬렉션에 추가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="28531-113">If the producer runs faster, you will notice the bounding functionality as the blocking collection prevents items from being added if it already contains the number of items that is specified in the constructor.</span></span> <span data-ttu-id="28531-114">소비자가 더 빠르게 실행되는 경우 차단 기능으로 인해 새 항목이 추가될 때까지 소비자가 기다리게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="28531-114">If the consumer runs faster, you will notice the blocking functionality as the consumer waits for a new item to be added.</span></span>  
  
 [!code-csharp[CDS_BlockingCollection#06](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/prodcon.cs#06)]  
  
 <span data-ttu-id="28531-115">기본적으로 <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType>의 저장소는 <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType>입니다.</span><span class="sxs-lookup"><span data-stu-id="28531-115">By default, the storage for a <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType> is <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28531-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="28531-116">See Also</span></span>  
 [<span data-ttu-id="28531-117">스레드로부터 안전한 컬렉션</span><span class="sxs-lookup"><span data-stu-id="28531-117">Thread-Safe Collections</span></span>](../../../../docs/standard/collections/thread-safe/index.md)
