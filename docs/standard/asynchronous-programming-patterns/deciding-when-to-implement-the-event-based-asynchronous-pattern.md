---
title: "이벤트 기반 비동기 패턴 구현 시기 결정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET Framework], asynchronous
- AsyncOperationManager class
- threading [.NET Framework], asynchronous features
- AsyncOperation class
- AsyncCompletedEventArgs class
ms.assetid: a00046aa-785d-4f7f-a8e5-d06475ea50da
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 48de1b736c251a61a2ad34975c77bc2bca139626
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="deciding-when-to-implement-the-event-based-asynchronous-pattern"></a><span data-ttu-id="a7beb-102">이벤트 기반 비동기 패턴 구현 시기 결정</span><span class="sxs-lookup"><span data-stu-id="a7beb-102">Deciding When to Implement the Event-based Asynchronous Pattern</span></span>
<span data-ttu-id="a7beb-103">이벤트 기반 비동기 패턴 클래스의 비동기 동작을 노출 하기 위한 패턴을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7beb-103">The Event-based Asynchronous Pattern provides a pattern for exposing the asynchronous behavior of a class.</span></span> <span data-ttu-id="a7beb-104">이 패턴의 도입으로는 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 비동기 동작을 노출 하기 위한 두 개의 패턴 정의: 비동기 패턴에 따라는 <xref:System.IAsyncResult?displayProperty=nameWithType> 인터페이스 및 이벤트 기반 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="a7beb-104">With the introduction of this pattern, the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] defines two patterns for exposing asynchronous behavior: the Asynchronous Pattern based on the <xref:System.IAsyncResult?displayProperty=nameWithType> interface, and the event-based pattern.</span></span> <span data-ttu-id="a7beb-105">이 항목에서는 두 패턴을 구현 하기 위한 적절 한 경우를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7beb-105">This topic describes when it is appropriate for you to implement both patterns.</span></span>  
  
 <span data-ttu-id="a7beb-106">비동기 프로그래밍에 대 한 자세한 내용은 <xref:System.IAsyncResult> 인터페이스를 참조 [이벤트 기반 비동기 패턴 (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a7beb-106">For more information about asynchronous programming with the <xref:System.IAsyncResult> interface, see [Event-based Asynchronous Pattern (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md).</span></span>  
  
## <a name="general-principles"></a><span data-ttu-id="a7beb-107">일반 원칙</span><span class="sxs-lookup"><span data-stu-id="a7beb-107">General Principles</span></span>  
 <span data-ttu-id="a7beb-108">일반적으로 가능 하면 이벤트 기반 비동기 패턴을 사용 하 여 비동기 기능을 노출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7beb-108">In general, you should expose asynchronous features using the Event-based Asynchronous Pattern whenever possible.</span></span> <span data-ttu-id="a7beb-109">그러나 이벤트 기반 패턴 충족할 수 없는 몇 가지 요구 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7beb-109">However, there are some requirements that the event-based pattern cannot meet.</span></span> <span data-ttu-id="a7beb-110">구현 해야 이러한 경우에는 <xref:System.IAsyncResult> 이벤트 기반 패턴 외에도 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="a7beb-110">In those cases, you may need to implement the <xref:System.IAsyncResult> pattern in addition to the event-based pattern.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a7beb-111">경우는 거의 <xref:System.IAsyncResult> 패턴 구현 되 고 이벤트 기반 패턴 없이 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7beb-111">It is rare for the <xref:System.IAsyncResult> pattern to be implemented without the event-based pattern also being implemented.</span></span>  
  
## <a name="guidelines"></a><span data-ttu-id="a7beb-112">지침</span><span class="sxs-lookup"><span data-stu-id="a7beb-112">Guidelines</span></span>  
 <span data-ttu-id="a7beb-113">다음 목록에서는 이벤트 기반 비동기 패턴을 구현 해야 하는 경우에 대 한 지침을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7beb-113">The following list describes the guidelines for when you should implement Event-based Asynchronous Pattern:</span></span>  
  
-   <span data-ttu-id="a7beb-114">기본 API로 이벤트 기반 패턴을 사용 하 여 클래스에 대 한 비동기 동작을 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7beb-114">Use the event-based pattern as the default API to expose asynchronous behavior for your class.</span></span>  
  
-   <span data-ttu-id="a7beb-115">노출 하지 마십시오.는 <xref:System.IAsyncResult> 클래스는 주로 Windows Forms 클라이언트 응용 프로그램에서 사용 하는 경우 패턴을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7beb-115">Do not expose the <xref:System.IAsyncResult> pattern when your class is primarily used in a client application, for example Windows Forms.</span></span>  
  
-   <span data-ttu-id="a7beb-116">노출 된 <xref:System.IAsyncResult> 요구 사항을 충족 해야 하는 경우 패턴을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7beb-116">Only expose the <xref:System.IAsyncResult> pattern when it is necessary for meeting your requirements.</span></span> <span data-ttu-id="a7beb-117">예를 들어 기존 API와의 호환성을 노출 해야 할 수도 있습니다는 <xref:System.IAsyncResult> 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="a7beb-117">For example, compatibility with an existing API may require you to expose the <xref:System.IAsyncResult> pattern.</span></span>  
  
-   <span data-ttu-id="a7beb-118">노출 하지 마십시오.는 <xref:System.IAsyncResult> 도 이벤트 기반 패턴을 노출 하지 않고 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="a7beb-118">Do not expose the <xref:System.IAsyncResult> pattern without also exposing the event-based pattern.</span></span>  
  
-   <span data-ttu-id="a7beb-119">노출 해야 하는 경우는 <xref:System.IAsyncResult> 고급 옵션으로, 패턴을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7beb-119">If you must expose the <xref:System.IAsyncResult> pattern, do so as an advanced option.</span></span> <span data-ttu-id="a7beb-120">예를 들어 프록시 개체를 생성 하는 경우 생성 이벤트 기반 패턴 기본적으로 생성 하는 옵션으로는 <xref:System.IAsyncResult> 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="a7beb-120">For example, if you generate a proxy object, generate the event-based pattern by default, with an option to generate the <xref:System.IAsyncResult> pattern.</span></span>  
  
-   <span data-ttu-id="a7beb-121">이벤트 기반 패턴 구현을 토대로 사용자 <xref:System.IAsyncResult> 패턴 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7beb-121">Build your event-based pattern implementation on your <xref:System.IAsyncResult> pattern implementation.</span></span>  
  
-   <span data-ttu-id="a7beb-122">두 이벤트 기반 패턴을 노출 하지 마십시오. 및 <xref:System.IAsyncResult> 동일한 클래스에는 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="a7beb-122">Avoid exposing both the event-based pattern and the <xref:System.IAsyncResult> pattern on the same class.</span></span> <span data-ttu-id="a7beb-123">"상위" 클래스에 따라 이벤트 패턴을 노출 및 <xref:System.IAsyncResult> 패턴을 "더 낮은 수준" 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="a7beb-123">Expose the event-based pattern on "higher level" classes and the <xref:System.IAsyncResult> pattern on "lower level" classes.</span></span> <span data-ttu-id="a7beb-124">예를 들어, 이벤트 기반 패턴의 비교는 <xref:System.Net.WebClient> 구성 요소는 <xref:System.IAsyncResult> 패턴에 <xref:System.Web.HttpRequest> 클래스.</span><span class="sxs-lookup"><span data-stu-id="a7beb-124">For example, compare the event-based pattern on the <xref:System.Net.WebClient> component with the <xref:System.IAsyncResult> pattern on the <xref:System.Web.HttpRequest> class.</span></span>  
  
    -   <span data-ttu-id="a7beb-125">이벤트 기반 패턴을 노출 및 <xref:System.IAsyncResult> 패턴 호환성 필요로 하는 경우 동일한 클래스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7beb-125">Expose the event-based pattern and the <xref:System.IAsyncResult> pattern on the same class when compatibility requires it.</span></span> <span data-ttu-id="a7beb-126">예를 들어, 이미 사용 하는 API를 해제 하는 경우는 <xref:System.IAsyncResult> 패턴을 유지 해야 할 것은 <xref:System.IAsyncResult> 이전 버전과 호환성에 대 한 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="a7beb-126">For example, if you have already released an API that uses the <xref:System.IAsyncResult> pattern, you would need to retain the <xref:System.IAsyncResult> pattern for backward compatibility.</span></span>  
  
    -   <span data-ttu-id="a7beb-127">이벤트 기반 패턴을 노출 및 <xref:System.IAsyncResult> 결과 개체 모델의 복잡성 구현을 구분 하 여 얻은 이점 보다 하는 경우 동일한 클래스에 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="a7beb-127">Expose the event-based pattern and the <xref:System.IAsyncResult> pattern on the same class if the resulting object model complexity outweighs the benefit of separating the implementations.</span></span> <span data-ttu-id="a7beb-128">이벤트 기반 패턴을 노출 하지 않는 것 보다는 단일 클래스에 두 패턴을 노출 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a7beb-128">It is better to expose both patterns on a single class than to avoid exposing the event-based pattern.</span></span>  
  
    -   <span data-ttu-id="a7beb-129">두 이벤트 기반 패턴을 노출 해야 하는 경우 및 <xref:System.IAsyncResult> 패턴에서 단일 클래스를 사용 하 여 <xref:System.ComponentModel.EditorBrowsableAttribute> 로 설정 <xref:System.ComponentModel.EditorBrowsableState.Advanced> 표시 하는 <xref:System.IAsyncResult> 는 고급 기능으로 패턴 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7beb-129">If you must expose both the event-based pattern and <xref:System.IAsyncResult> pattern on a single class, use <xref:System.ComponentModel.EditorBrowsableAttribute> set to <xref:System.ComponentModel.EditorBrowsableState.Advanced> to mark the <xref:System.IAsyncResult> pattern implementation as an advanced feature.</span></span> <span data-ttu-id="a7beb-130">디자인 환경에 같은 나타냅니다 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 를 나타내지 IntelliSense는 <xref:System.IAsyncResult> 속성 및 메서드.</span><span class="sxs-lookup"><span data-stu-id="a7beb-130">This indicates to design environments, such as [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] IntelliSense, not to display the <xref:System.IAsyncResult> properties and methods.</span></span> <span data-ttu-id="a7beb-131">이러한 속성 및 메서드는 계속 완벽 하 게 사용할 수 있지만 IntelliSense를 통해 작업 하는 개발자가 API 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7beb-131">These properties and methods are still fully usable, but the developer working through IntelliSense has a clearer view of the API.</span></span>  
  
## <a name="criteria-for-exposing-the-iasyncresult-pattern-in-addition-to-the-event-based-pattern"></a><span data-ttu-id="a7beb-132">이벤트 기반 패턴 외에도 IAsyncResult 패턴을 노출 하는 것에 대 한 기준</span><span class="sxs-lookup"><span data-stu-id="a7beb-132">Criteria for Exposing the IAsyncResult Pattern in Addition to the Event-based Pattern</span></span>  
 <span data-ttu-id="a7beb-133">이벤트 기반 비동기 패턴에는 앞에서 언급 한 시나리오에서 많은 장점이, 성능이 가장 중요 한 요구 사항 경우 알고 있어야 하는 몇 가지 장애가 들어지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a7beb-133">While the Event-based Asynchronous Pattern has many benefits under the previously mentioned scenarios, it does have some drawbacks, which you should be aware of if performance is your most important requirement.</span></span>  
  
 <span data-ttu-id="a7beb-134">이벤트 기반 패턴 해결 되지 않는 세 가지 시나리오가 있습니다으로 <xref:System.IAsyncResult> 패턴:</span><span class="sxs-lookup"><span data-stu-id="a7beb-134">There are three scenarios that the event-based pattern does not address as well as the <xref:System.IAsyncResult> pattern:</span></span>  
  
-   <span data-ttu-id="a7beb-135">대기 하나에 차단<xref:System.IAsyncResult></span><span class="sxs-lookup"><span data-stu-id="a7beb-135">Blocking wait on one <xref:System.IAsyncResult></span></span>  
  
-   <span data-ttu-id="a7beb-136">많은 대기 차단 <xref:System.IAsyncResult> 개체</span><span class="sxs-lookup"><span data-stu-id="a7beb-136">Blocking wait on many <xref:System.IAsyncResult> objects</span></span>  
  
-   <span data-ttu-id="a7beb-137">완료에 대 한 폴링는<xref:System.IAsyncResult></span><span class="sxs-lookup"><span data-stu-id="a7beb-137">Polling for completion on the <xref:System.IAsyncResult></span></span>  
  
 <span data-ttu-id="a7beb-138">이벤트 기반 패턴을 사용 하 여 이러한 시나리오를 처리할 수 있지만 방법은 사용 하 여 보다 성가 십니다는 <xref:System.IAsyncResult> 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="a7beb-138">You can address these scenarios by using the event-based pattern, but doing so is more cumbersome than using the <xref:System.IAsyncResult> pattern.</span></span>  
  
 <span data-ttu-id="a7beb-139">개발자는 종종 사용 된 <xref:System.IAsyncResult> 일반적으로 매우 높은 성능 요구 사항이 서비스에 대 한 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="a7beb-139">Developers often use the <xref:System.IAsyncResult> pattern for services that typically have very high performance requirements.</span></span> <span data-ttu-id="a7beb-140">예를 들어 완료 시나리오에 대 한 폴링은 고성능 서버 기술 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7beb-140">For example, the polling for completion scenario is a high-performance server technique.</span></span>  
  
 <span data-ttu-id="a7beb-141">또한, 이벤트 기반 패턴은 것 보다는 <xref:System.IAsyncResult> 특히 더 많은 개체를 만들기 때문에 패턴 <xref:System.EventArgs>, 때문이 스레드를 동기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7beb-141">Additionally, the event-based pattern is less efficient than the <xref:System.IAsyncResult> pattern because it creates more objects, especially <xref:System.EventArgs>, and because it synchronizes across threads.</span></span>  
  
 <span data-ttu-id="a7beb-142">다음 목록은 몇 가지 권장 사항 사용 하려는 경우 수행 하는 <xref:System.IAsyncResult> 패턴:</span><span class="sxs-lookup"><span data-stu-id="a7beb-142">The following list shows some recommendations to follow if you decide to use the <xref:System.IAsyncResult> pattern:</span></span>  
  
-   <span data-ttu-id="a7beb-143">표시는 <xref:System.IAsyncResult> 패턴에 대 한 지원 특별히 필요한 경우 <xref:System.Threading.WaitHandle> 또는 <xref:System.IAsyncResult> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="a7beb-143">Only expose the <xref:System.IAsyncResult> pattern when you specifically require support for <xref:System.Threading.WaitHandle> or <xref:System.IAsyncResult> objects.</span></span>  
  
-   <span data-ttu-id="a7beb-144">노출 된 <xref:System.IAsyncResult> 사용 하는 기존 API가 있는 경우는 <xref:System.IAsyncResult> 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="a7beb-144">Only expose the <xref:System.IAsyncResult> pattern when you have an existing API that uses the <xref:System.IAsyncResult> pattern.</span></span>  
  
-   <span data-ttu-id="a7beb-145">기반으로 하는 기존 API가 있는 경우는 <xref:System.IAsyncResult> 도 다음 릴리스에 따라 이벤트 패턴을 노출 하는 것이 좋습니다., 패턴을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7beb-145">If you have an existing API based on the <xref:System.IAsyncResult> pattern, consider also exposing the event-based pattern in your next release.</span></span>  
  
-   <span data-ttu-id="a7beb-146">주요 <xref:System.IAsyncResult> 패턴 있는 고성능 요구 사항이 있는 경우 이벤트 기반 패턴에 맞지 않습니다 하지만 하 여 충족할 수는 <xref:System.IAsyncResult> 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="a7beb-146">Only expose <xref:System.IAsyncResult> pattern if you have high performance requirements which you have verified cannot be met by the event-based pattern but can be met by the <xref:System.IAsyncResult> pattern.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7beb-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a7beb-147">See Also</span></span>  
 [<span data-ttu-id="a7beb-148">연습: 이벤트 기반 비동기 패턴을 지원하는 구성 요소 구현</span><span class="sxs-lookup"><span data-stu-id="a7beb-148">Walkthrough: Implementing a Component That Supports the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)  
 [<span data-ttu-id="a7beb-149">EAP(이벤트 기반 비동기 패턴)</span><span class="sxs-lookup"><span data-stu-id="a7beb-149">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 [<span data-ttu-id="a7beb-150">이벤트 기반 비동기 패턴을 사용한 다중 스레드 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="a7beb-150">Multithreaded Programming with the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/multithreaded-programming-with-the-event-based-asynchronous-pattern.md)  
 [<span data-ttu-id="a7beb-151">이벤트 기반 비동기 패턴 구현</span><span class="sxs-lookup"><span data-stu-id="a7beb-151">Implementing the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md)  
 [<span data-ttu-id="a7beb-152">최선의 이벤트 기반 비동기 패턴 구현 방법</span><span class="sxs-lookup"><span data-stu-id="a7beb-152">Best Practices for Implementing the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md)  
 [<span data-ttu-id="a7beb-153">이벤트 기반 비동기 패턴 개요</span><span class="sxs-lookup"><span data-stu-id="a7beb-153">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
