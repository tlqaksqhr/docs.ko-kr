---
title: "방법: ConcurrentBag을 사용하여 개체 풀 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- object pool, in .NET Framework
ms.assetid: 0480e7ff-b6f9-480e-a889-2ed4264d8372
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 66cde52d7453e149510d0c2e1d63f9e9182e3e99
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-create-an-object-pool-by-using-a-concurrentbag"></a><span data-ttu-id="85d24-102">방법: ConcurrentBag을 사용하여 개체 풀 만들기</span><span class="sxs-lookup"><span data-stu-id="85d24-102">How to: Create an Object Pool by Using a ConcurrentBag</span></span>
<span data-ttu-id="85d24-103">이 예제에서는 CurrentBag을 사용하여 개체 풀을 구현하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="85d24-103">This example shows how to use a concurrent bag to implement an object pool.</span></span> <span data-ttu-id="85d24-104">클래스에 여러 인스턴스가 필요하고 클래스를 만들거나 삭제하는 데 비용이 많이 드는 경우 개체 풀을 사용하면 응용 프로그램 성능을 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85d24-104">Object pools can improve application performance in situations where you require multiple instances of a class and the class is expensive to create or destroy.</span></span> <span data-ttu-id="85d24-105">클라이언트 프로그램에서 새 개체를 요청하면 먼저 개체 풀이 이미 풀에 만들어져 반환된 개체를 제공하려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="85d24-105">When a client program requests a new object, the object pool first attempts to provide one that has already been created and returned to the pool.</span></span> <span data-ttu-id="85d24-106">제공될 개체가 없는 경우에만 새 개체가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="85d24-106">If none is available, only then is a new object created.</span></span>  
  
 <span data-ttu-id="85d24-107"><xref:System.Collections.Concurrent.ConcurrentBag%601>는 특히 한 스레드에서 항목의 추가와 제거를 모두 수행할 때 추가하고 제거하는 속도가 빠르기 때문에 개체를 저장하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="85d24-107"><xref:System.Collections.Concurrent.ConcurrentBag%601> is used to store the objects because it supports fast insertion and removal, especially when the same thread is both adding and removing items.</span></span> <span data-ttu-id="85d24-108"><xref:System.Collections.Concurrent.ConcurrentQueue%601> 및 <xref:System.Collections.Concurrent.ConcurrentStack%601>와 같이 모음 데이터 구조가 구현하는 <xref:System.Collections.Concurrent.IProducerConsumerCollection%601>를 중심으로 구축되도록 이 예제를 강화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85d24-108">This example could be further augmented to be built around a <xref:System.Collections.Concurrent.IProducerConsumerCollection%601>, which the bag data structure implements, as do <xref:System.Collections.Concurrent.ConcurrentQueue%601> and <xref:System.Collections.Concurrent.ConcurrentStack%601>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="85d24-109">예</span><span class="sxs-lookup"><span data-stu-id="85d24-109">Example</span></span>  
 [!code-csharp[CDS#04](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds/cs/objectpool.cs#04)]
 [!code-vb[CDS#04](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds/vb/objectpool04.vb#04)]  
  
## <a name="see-also"></a><span data-ttu-id="85d24-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="85d24-110">See Also</span></span>  
 [<span data-ttu-id="85d24-111">스레드로부터 안전한 컬렉션</span><span class="sxs-lookup"><span data-stu-id="85d24-111">Thread-Safe Collections</span></span>](../../../../docs/standard/collections/thread-safe/index.md)
