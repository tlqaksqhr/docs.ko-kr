---
title: 이벤트 기반 비동기 패턴을 사용한 다중 스레드 프로그래밍
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET Framework], asynchronous
- AsyncOperationManager class
- threading [.NET Framework], asynchronous features
- components [.NET Framework], asynchronous
- AsyncOperation class
- AsyncCompletedEventArgs class
ms.assetid: 958d6617-5e70-4b36-b5db-63c16dc35e43
ms.openlocfilehash: 26e555a158ced352c297952b56f7557cbd825cd7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33567304"
---
# <a name="multithreaded-programming-with-the-event-based-asynchronous-pattern"></a><span data-ttu-id="a5e3b-102">이벤트 기반 비동기 패턴을 사용한 다중 스레드 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="a5e3b-102">Multithreaded Programming with the Event-based Asynchronous Pattern</span></span>
<span data-ttu-id="a5e3b-103">비동기 기능을 클라이언트 코드에 노출하는 방법은 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5e3b-103">There are a number of ways to expose asynchronous features to client code.</span></span> <span data-ttu-id="a5e3b-104">이벤트 기반 비동기 패턴은 클래스에 비동기 동작을 표시하는 권장 방법을 규정합니다.</span><span class="sxs-lookup"><span data-stu-id="a5e3b-104">The Event-based Asynchronous Pattern prescribes the recommended way for classes to present asynchronous behavior.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a5e3b-105">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="a5e3b-105">In This Section</span></span>  
 [<span data-ttu-id="a5e3b-106">이벤트 기반 비동기 패턴 개요</span><span class="sxs-lookup"><span data-stu-id="a5e3b-106">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 <span data-ttu-id="a5e3b-107">이벤트 기반 비동기 패턴이 다중 스레드 디자인에 본질적으로 존재하는 복잡한 여러 가지 문제를 숨기면서 다중 스레드 응용 프로그램의 장점을 이용할 수 있게 해주는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a5e3b-107">Describes how the Event-based Asynchronous Pattern makes available the advantages of multithreaded applications while hiding many of the complex issues inherent in multithreaded design.</span></span>  
  
 [<span data-ttu-id="a5e3b-108">이벤트 기반 비동기 패턴 구현</span><span class="sxs-lookup"><span data-stu-id="a5e3b-108">Implementing the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="a5e3b-109">비동기 기능을 포함하는 클래스를 패키징하는 표준화된 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a5e3b-109">Describes the standardized way to package a class that has asynchronous features.</span></span>  
  
 [<span data-ttu-id="a5e3b-110">최선의 이벤트 기반 비동기 패턴 구현 방법</span><span class="sxs-lookup"><span data-stu-id="a5e3b-110">Best Practices for Implementing the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="a5e3b-111">이벤트 기반 비동기 패턴에 따라 비동기 기능을 노출하기 위한 요구 사항을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a5e3b-111">Describes the requirements for exposing asynchronous features according to the Event-based Asynchronous Pattern.</span></span>  
  
 [<span data-ttu-id="a5e3b-112">이벤트 기반 비동기 패턴 구현 시기 결정</span><span class="sxs-lookup"><span data-stu-id="a5e3b-112">Deciding When to Implement the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/deciding-when-to-implement-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="a5e3b-113"><xref:System.IAsyncResult> 패턴 대신 이벤트 기반 비동기 패턴을 구현하도록 선택해야 하는 경우를 확인하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a5e3b-113">Describes how to determine when you should choose to implement the Event-based Asynchronous Pattern instead of the <xref:System.IAsyncResult> pattern.</span></span>  
  
 [<span data-ttu-id="a5e3b-114">연습: 이벤트 기반 비동기 패턴을 지원하는 구성 요소 구현</span><span class="sxs-lookup"><span data-stu-id="a5e3b-114">Walkthrough: Implementing a Component That Supports the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="a5e3b-115">이벤트 기반 비동기 패턴을 구현하는 구성 요소를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a5e3b-115">Illustrates how to create a component that implements the Event-based Asynchronous Pattern.</span></span> <span data-ttu-id="a5e3b-116">구성 요소가 모든 응용 프로그램 모델에서 올바르게 작동하도록 하는 <xref:System.ComponentModel?displayProperty=nameWithType> 네임스페이스의 도우미 클래스를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a5e3b-116">It is implemented using helper classes from the <xref:System.ComponentModel?displayProperty=nameWithType> namespace, which ensures that the component works correctly under any application model.</span></span>  
  
 [<span data-ttu-id="a5e3b-117">방법: 이벤트 기반 비동기 패턴을 지원하는 구성 요소 사용</span><span class="sxs-lookup"><span data-stu-id="a5e3b-117">How to: Use Components That Support the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/how-to-use-components-that-support-the-event-based-asynchronous-pattern.md)  
 <span data-ttu-id="a5e3b-118">이벤트 기반 비동기 패턴을 지원하는 구성 요소를 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a5e3b-118">Describes how to use a component that supports the Event-based Asynchronous Pattern.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="a5e3b-119">참조</span><span class="sxs-lookup"><span data-stu-id="a5e3b-119">Reference</span></span>  
 <xref:System.ComponentModel.AsyncOperation>  
 <span data-ttu-id="a5e3b-120"><xref:System.ComponentModel.AsyncOperation> 클래스를 설명하고 모든 해당 멤버의 링크를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="a5e3b-120">Describes the <xref:System.ComponentModel.AsyncOperation> class and has links to all its members.</span></span>  
  
 <xref:System.ComponentModel.AsyncOperationManager>  
 <span data-ttu-id="a5e3b-121"><xref:System.ComponentModel.AsyncOperationManager> 클래스를 설명하고 모든 해당 멤버의 링크를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="a5e3b-121">Describes the <xref:System.ComponentModel.AsyncOperationManager> class and has links to all its members.</span></span>  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="a5e3b-122"><xref:System.ComponentModel.BackgroundWorker> 구성 요소를 설명하고 모든 해당 멤버의 링크를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="a5e3b-122">Describes the <xref:System.ComponentModel.BackgroundWorker> component and has links to all its members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5e3b-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a5e3b-123">See Also</span></span>  
 [<span data-ttu-id="a5e3b-124">관리되는 스레딩을 구현하는 최선의 방법</span><span class="sxs-lookup"><span data-stu-id="a5e3b-124">Managed Threading Best Practices</span></span>](../../../docs/standard/threading/managed-threading-best-practices.md)  
 [<span data-ttu-id="a5e3b-125">이벤트</span><span class="sxs-lookup"><span data-stu-id="a5e3b-125">Events</span></span>](../../../docs/standard/events/index.md)  
 [<span data-ttu-id="a5e3b-126">구성 요소에서 다중 스레딩</span><span class="sxs-lookup"><span data-stu-id="a5e3b-126">Multithreading in Components</span></span>](https://msdn.microsoft.com/library/2fc31e68-fb71-4544-b654-0ce720478779)  
 [<span data-ttu-id="a5e3b-127">EAP(이벤트 기반 비동기 패턴)</span><span class="sxs-lookup"><span data-stu-id="a5e3b-127">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)
