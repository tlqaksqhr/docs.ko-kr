---
title: "대리자를 사용한 비동기 프로그래밍"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BeginInvoke method
- asynchronous programming, delegates
- asynchronous delegates
- calling synchronous methods in asynchronous manner
- EndInvoke method
- calling asynchronous methods
- delegates [.NET Framework], asynchronous
- synchronous calling in asynchronous manner
ms.assetid: 38a345ca-6963-4436-9608-5c9defef9c64
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 596d2be26318b782423653b4eb3f43c1f9fc4b92
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="asynchronous-programming-using-delegates"></a><span data-ttu-id="b38cd-102">대리자를 사용한 비동기 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="b38cd-102">Asynchronous Programming Using Delegates</span></span>
<span data-ttu-id="b38cd-103">대리자를 사용하면 비동기 방식으로 동기 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b38cd-103">Delegates enable you to call a synchronous method in an asynchronous manner.</span></span> <span data-ttu-id="b38cd-104">대리자를 동기적으로 호출하면 `Invoke` 메서드는 현재 스레드에서 직접 대상 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="b38cd-104">When you call a delegate synchronously, the `Invoke` method calls the target method directly on the current thread.</span></span> <span data-ttu-id="b38cd-105">`BeginInvoke` 메서드가 호출되면 CLR(공용 언어 런타임)에서 요청을 대기하고 호출자에게 즉시 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b38cd-105">If the `BeginInvoke` method is called, the common language runtime (CLR) queues the request and returns immediately to the caller.</span></span> <span data-ttu-id="b38cd-106">대상 메서드는 스레드 풀의 스레드에서 비동기적으로 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="b38cd-106">The target method is called asynchronously on a thread from the thread pool.</span></span> <span data-ttu-id="b38cd-107">요청을 제출하는 원래 스레드는 계속해서 대상 메서드와 함께 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="b38cd-107">The original thread, which submitted the request, is free to continue executing in parallel with the target method.</span></span> <span data-ttu-id="b38cd-108">`BeginInvoke` 메서드 호출에서 콜백 메서드가 지정된 경우 대상 메서드가 종료될 때 콜백 메서드가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="b38cd-108">If a callback method has been specified in the call to the `BeginInvoke` method, the callback method is called when the target method ends.</span></span> <span data-ttu-id="b38cd-109">콜백 메서드에서 `EndInvoke` 메서드는 반환 값 및 입/출력 또는 출력 전용 매개 변수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b38cd-109">In the callback method, the `EndInvoke` method obtains the return value and any input/output or output-only parameters.</span></span> <span data-ttu-id="b38cd-110">`BeginInvoke`를 호출할 때 콜백 메서드를 지정하지 않으면 `BeginInvoke`를 호출한 스레드에서 `EndInvoke`가 호출될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b38cd-110">If no callback method is specified when calling `BeginInvoke`, `EndInvoke` can be called from the thread that called `BeginInvoke`.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b38cd-111">컴파일러는 사용자가 지정한 대리자 시그니처를 사용하여 `Invoke`, `BeginInvoke` 및 `EndInvoke` 메서드를 통해 대리자 클래스를 내보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b38cd-111">Compilers should emit delegate classes with `Invoke`, `BeginInvoke`, and `EndInvoke` methods using the delegate signature specified by the user.</span></span> <span data-ttu-id="b38cd-112">`BeginInvoke` 및 `EndInvoke` 메서드는 네이티브로 데코레이팅해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b38cd-112">The `BeginInvoke` and `EndInvoke` methods should be decorated as native.</span></span> <span data-ttu-id="b38cd-113">이러한 메서드는 네이티브로 표시되므로 CLR은 클래스 로드 타임에 구현을 자동으로 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b38cd-113">Because these methods are marked as native, the CLR automatically provides the implementation at class load time.</span></span> <span data-ttu-id="b38cd-114">로더는 이러한 메서드가 재정의되지 않도록 보장합니다.</span><span class="sxs-lookup"><span data-stu-id="b38cd-114">The loader ensures that they are not overridden.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b38cd-115">단원 내용</span><span class="sxs-lookup"><span data-stu-id="b38cd-115">In This Section</span></span>  
 [<span data-ttu-id="b38cd-116">동기 메서드를 비동기 방식으로 호출</span><span class="sxs-lookup"><span data-stu-id="b38cd-116">Calling Synchronous Methods Asynchronously</span></span>](../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md)  
 <span data-ttu-id="b38cd-117">대리자를 사용하여 일반적인 메서드에 대해 비동기 호출을 수행하는 방법을 살펴보고 비동기 호출이 반환될 때까지 기다리는 4가지 방법을 보여 주는 간단한 코드 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b38cd-117">Discusses the use of delegates to make asynchronous calls to ordinary methods, and provides simple code examples that show the four ways to wait for an asynchronous call to return.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="b38cd-118">관련 단원</span><span class="sxs-lookup"><span data-stu-id="b38cd-118">Related Sections</span></span>  
 [<span data-ttu-id="b38cd-119">EAP(이벤트 기반 비동기 패턴)</span><span class="sxs-lookup"><span data-stu-id="b38cd-119">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 <span data-ttu-id="b38cd-120">.NET Framework를 사용한 비동기 프로그래밍에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b38cd-120">Describes asynchronous programming with the .NET Framework.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b38cd-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b38cd-121">See Also</span></span>  
 <xref:System.Delegate>
