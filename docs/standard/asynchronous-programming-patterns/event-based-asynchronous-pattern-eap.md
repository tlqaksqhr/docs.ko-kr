---
title: "이벤트 기반 비동기 패턴(EAP)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- asynchronous calls
- asynchronous programming, design patterns
- asynchronous programming
ms.assetid: c6baed9f-2a25-4728-9a9a-53b7b14840cf
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 2a83d638255d27317ba5d566ab46b83526659365
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="event-based-asynchronous-pattern-eap"></a><span data-ttu-id="fa37a-102">이벤트 기반 비동기 패턴(EAP)</span><span class="sxs-lookup"><span data-stu-id="fa37a-102">Event-based Asynchronous Pattern (EAP)</span></span>
<span data-ttu-id="fa37a-103">비동기 기능을 클라이언트 코드에 노출하는 방법은 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa37a-103">There are a number of ways to expose asynchronous features to client code.</span></span> <span data-ttu-id="fa37a-104">이벤트 기반 비동기 패턴은 클래스에 비동기 동작을 표시하는 한 가지 방법을 규정합니다.</span><span class="sxs-lookup"><span data-stu-id="fa37a-104">The Event-based Asynchronous Pattern prescribes one way for classes to present asynchronous behavior.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fa37a-105">[!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]부터는 작업 병렬 라이브러리에서 비동기 및 병렬 프로그래밍을 위한 새로운 모델을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fa37a-105">Starting with the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], the Task Parallel Library provides a new model for asynchronous and parallel programming.</span></span> <span data-ttu-id="fa37a-106">자세한 내용은 [병렬 프로그래밍](../../../docs/standard/parallel-programming/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fa37a-106">For more information, see [Parallel Programming](../../../docs/standard/parallel-programming/index.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fa37a-107">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="fa37a-107">In This Section</span></span>  
 [<span data-ttu-id="fa37a-108">이벤트 기반 비동기 패턴 개요</span><span class="sxs-lookup"><span data-stu-id="fa37a-108">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 <span data-ttu-id="fa37a-109">이벤트 기반 비동기 패턴이 다중 스레드 디자인에 본질적으로 존재하는 복잡한 여러 가지 문제를 숨기면서 다중 스레드 응용 프로그램의 장점을 이용할 수 있게 해주는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fa37a-109">Describes how the Event-based Asynchronous Pattern makes available the advantages of multithreaded applications while hiding many of the complex issues inherent in multithreaded design.</span></span>  
  
 [<span data-ttu-id="fa37a-110">이벤트 기반 비동기 패턴 구현</span><span class="sxs-lookup"><span data-stu-id="fa37a-110">Implementing the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="fa37a-111">비동기 기능을 포함하는 클래스를 패키징하는 표준화된 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fa37a-111">Describes the standardized way to package a class that has asynchronous features.</span></span>  
  
 [<span data-ttu-id="fa37a-112">최선의 이벤트 기반 비동기 패턴 구현 방법</span><span class="sxs-lookup"><span data-stu-id="fa37a-112">Best Practices for Implementing the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="fa37a-113">이벤트 기반 비동기 패턴에 따라 비동기 기능을 노출하기 위한 요구 사항을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fa37a-113">Describes the requirements for exposing asynchronous features according to the Event-based Asynchronous Pattern.</span></span>  
  
 [<span data-ttu-id="fa37a-114">이벤트 기반 비동기 패턴 구현 시기 결정</span><span class="sxs-lookup"><span data-stu-id="fa37a-114">Deciding When to Implement the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/deciding-when-to-implement-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="fa37a-115"><xref:System.IAsyncResult> 패턴 대신 이벤트 기반 비동기 패턴을 구현하도록 선택해야 하는 경우를 확인하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fa37a-115">Describes how to determine when you should choose to implement the Event-based Asynchronous Pattern instead of the <xref:System.IAsyncResult> pattern.</span></span>  
  
 [<span data-ttu-id="fa37a-116">연습: 이벤트 기반 비동기 패턴을 지원하는 구성 요소 구현</span><span class="sxs-lookup"><span data-stu-id="fa37a-116">Walkthrough: Implementing a Component That Supports the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="fa37a-117">이벤트 기반 비동기 패턴을 구현하는 구성 요소를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fa37a-117">Illustrates how to create a component that implements the Event-based Asynchronous Pattern.</span></span> <span data-ttu-id="fa37a-118">구성 요소가 모든 응용 프로그램 모델에서 올바르게 작동하도록 하는 <xref:System.ComponentModel?displayProperty=nameWithType> 네임스페이스의 도우미 클래스를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fa37a-118">It is implemented using helper classes from the <xref:System.ComponentModel?displayProperty=nameWithType> namespace, which ensures that the component works correctly under any application model.</span></span>  
  
 [<span data-ttu-id="fa37a-119">방법: 이벤트 기반 비동기 패턴을 지원하는 구성 요소 사용</span><span class="sxs-lookup"><span data-stu-id="fa37a-119">How to: Use Components That Support the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/how-to-use-components-that-support-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="fa37a-120">이벤트 기반 비동기 패턴을 지원하는 구성 요소를 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fa37a-120">Describes how to use a component that supports the Event-based Asynchronous Pattern.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="fa37a-121">참조</span><span class="sxs-lookup"><span data-stu-id="fa37a-121">Reference</span></span>  
 <xref:System.ComponentModel.AsyncOperation>  
 <span data-ttu-id="fa37a-122"><xref:System.ComponentModel.AsyncOperation> 클래스를 설명하고 모든 해당 멤버의 링크를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="fa37a-122">Describes the <xref:System.ComponentModel.AsyncOperation> class and has links to all its members.</span></span>  
  
 <xref:System.ComponentModel.AsyncOperationManager>  
 <span data-ttu-id="fa37a-123"><xref:System.ComponentModel.AsyncOperationManager> 클래스를 설명하고 모든 해당 멤버의 링크를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="fa37a-123">Describes the <xref:System.ComponentModel.AsyncOperationManager> class and has links to all its members.</span></span>  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="fa37a-124"><xref:System.ComponentModel.BackgroundWorker> 구성 요소를 설명하고 모든 해당 멤버의 링크를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="fa37a-124">Describes the <xref:System.ComponentModel.BackgroundWorker> component and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="fa37a-125">관련 단원</span><span class="sxs-lookup"><span data-stu-id="fa37a-125">Related Sections</span></span>  
 [<span data-ttu-id="fa37a-126">TPL(작업 병렬 라이브러리)</span><span class="sxs-lookup"><span data-stu-id="fa37a-126">Task Parallel Library (TPL)</span></span>](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)  
 <span data-ttu-id="fa37a-127">비동기 및 병렬 작업용 프로그래밍 모델에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fa37a-127">Describes a programming model for asynchronous and parallel operations.</span></span>  
  
 [<span data-ttu-id="fa37a-128">스레딩</span><span class="sxs-lookup"><span data-stu-id="fa37a-128">Threading</span></span>](../../../docs/standard/threading/index.md)  
 <span data-ttu-id="fa37a-129">.NET Framework 다중 스레딩 기능에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fa37a-129">Describes multithreading features in the .NET Framework.</span></span>  
  
 [<span data-ttu-id="fa37a-130">스레딩</span><span class="sxs-lookup"><span data-stu-id="fa37a-130">Threading</span></span>](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c)  
 <span data-ttu-id="fa37a-131">C# 및 Visual Basic 언어의 다중 스레딩 기능에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fa37a-131">Describes multithreading features in the C# and Visual Basic languages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa37a-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fa37a-132">See Also</span></span>  
 [<span data-ttu-id="fa37a-133">관리되는 스레딩을 구현하는 최선의 방법</span><span class="sxs-lookup"><span data-stu-id="fa37a-133">Managed Threading Best Practices</span></span>](../../../docs/standard/threading/managed-threading-best-practices.md)  
 [<span data-ttu-id="fa37a-134">이벤트</span><span class="sxs-lookup"><span data-stu-id="fa37a-134">Events</span></span>](../../../docs/standard/events/index.md)  
 [<span data-ttu-id="fa37a-135">구성 요소에서 다중 스레딩</span><span class="sxs-lookup"><span data-stu-id="fa37a-135">Multithreading in Components</span></span>](http://msdn.microsoft.com/library/2fc31e68-fb71-4544-b654-0ce720478779)  
 [<span data-ttu-id="fa37a-136">비동기 프로그래밍 패턴</span><span class="sxs-lookup"><span data-stu-id="fa37a-136">Asynchronous Programming Design Patterns</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)
