---
title: "스레드 및 스레딩 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], about threading
- managed threading
ms.assetid: 9b5ec2cd-121b-4d49-b075-222cf26f2344
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 80eb4c3bb98acdd1f83dbf5bcf57b2f7b295742b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="using-threads-and-threading"></a><span data-ttu-id="540bd-102">스레드 및 스레딩 사용</span><span class="sxs-lookup"><span data-stu-id="540bd-102">Using Threads and Threading</span></span>
<span data-ttu-id="540bd-103">이 섹션의 항목 생성 및 관리의 관리 되는 스레드, 관리 되는 스레드 데이터를 전달 하 고 결과 다시 가져오는 방법 및 스레드를 삭제 하 고 처리 하는 방법에 설명 된 <xref:System.Threading.ThreadAbortException>합니다.</span><span class="sxs-lookup"><span data-stu-id="540bd-103">The topics in this section discuss the creation and management of managed threads, how to pass data to managed threads and get results back, and how to destroy threads and handle a <xref:System.Threading.ThreadAbortException>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="540bd-104">단원 내용</span><span class="sxs-lookup"><span data-stu-id="540bd-104">In This Section</span></span>  
 [<span data-ttu-id="540bd-105">스레드 만들기 및 시작할 때 데이터 전달</span><span class="sxs-lookup"><span data-stu-id="540bd-105">Creating Threads and Passing Data at Start Time</span></span>](../../../docs/standard/threading/creating-threads-and-passing-data-at-start-time.md)  
 <span data-ttu-id="540bd-106">에 대해 설명 하 고 데이터를 가져오는 방법을 다시 데이터 새 스레드를 전달 하는 방법을 비롯 하 여 관리 되는 스레드를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="540bd-106">Discusses and demonstrates the creation of managed threads, including how to pass data to new threads and how to get data back.</span></span>  
  
 [<span data-ttu-id="540bd-107">스레드 일시 중지 및 다시 시작</span><span class="sxs-lookup"><span data-stu-id="540bd-107">Pausing and Resuming Threads</span></span>](../../../docs/standard/threading/pausing-and-resuming-threads.md)  
 <span data-ttu-id="540bd-108">일시 중지 하 고 관리 되는 스레드를 다시 시작이 발생 하는 결과 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="540bd-108">Discusses the ramifications of pausing and resuming managed threads.</span></span>  
  
 [<span data-ttu-id="540bd-109">스레드 제거</span><span class="sxs-lookup"><span data-stu-id="540bd-109">Destroying Threads</span></span>](../../../docs/standard/threading/destroying-threads.md)  
 <span data-ttu-id="540bd-110">없애는 관리 되는 스레드 및 처리 하는 방법에 설명 된 <xref:System.Threading.ThreadAbortException>합니다.</span><span class="sxs-lookup"><span data-stu-id="540bd-110">Discusses the ramifications of destroying managed threads, and how to handle a <xref:System.Threading.ThreadAbortException>.</span></span>  
  
 [<span data-ttu-id="540bd-111">스레드 스케줄링</span><span class="sxs-lookup"><span data-stu-id="540bd-111">Scheduling Threads</span></span>](../../../docs/standard/threading/scheduling-threads.md)  
 <span data-ttu-id="540bd-112">스레드 우선 순위 및 스레드 일정에 어떻게 영향을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="540bd-112">Discusses thread priorities and how they affect thread scheduling.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="540bd-113">참조</span><span class="sxs-lookup"><span data-stu-id="540bd-113">Reference</span></span>  
 <xref:System.Threading.Thread>  
 <span data-ttu-id="540bd-114">에 대 한 참조 설명서를 제공는 <xref:System.Threading.Thread> 비관리 코드에서 가져왔는지 또는 관리 되는 응용 프로그램에서 만들어진 관리 되는 스레드를 나타내는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="540bd-114">Provides reference documentation for the <xref:System.Threading.Thread> class, which represents a managed thread, whether it came from unmanaged code or was created in a managed application.</span></span>  
  
 <xref:System.Threading.ThreadStart>  
 <span data-ttu-id="540bd-115">에 대 한 참조 설명서를 제공는 <xref:System.Threading.ThreadStart> 매개 변수가 없는 스레드 프로시저를 나타내는 대리자입니다.</span><span class="sxs-lookup"><span data-stu-id="540bd-115">Provides reference documentation for the <xref:System.Threading.ThreadStart> delegate that represents parameterless thread procedures.</span></span>  
  
 <xref:System.Threading.ParameterizedThreadStart>  
 <span data-ttu-id="540bd-116">수행 하지 않고도 강력한 형식 지정 스레드 프로시저에 데이터를 전달 하는 쉬운 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="540bd-116">Provides an easy way to pass data to a thread procedure, although without strong typing.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="540bd-117">관련 단원</span><span class="sxs-lookup"><span data-stu-id="540bd-117">Related Sections</span></span>  
 [<span data-ttu-id="540bd-118">스레드 및 스레딩</span><span class="sxs-lookup"><span data-stu-id="540bd-118">Threads and Threading</span></span>](../../../docs/standard/threading/threads-and-threading.md)  
 <span data-ttu-id="540bd-119">관리 되는 스레딩에 대 한 소개를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="540bd-119">Provides an introduction to managed threading.</span></span>
