---
title: "CLR ETW 이벤트"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- CLR ETW events
- ETW, common language runtime
- ETW, CLR events
ms.assetid: ef2b31c3-7426-43e7-9924-92339b96556d
caps.latest.revision: "45"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1d0619388b429bd1824a62bc29ccb222eea1ffde
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="clr-etw-events"></a><span data-ttu-id="0a13d-102">CLR ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="0a13d-102">CLR ETW Events</span></span>
<span data-ttu-id="0a13d-103">이 섹션의 항목은 ETW(Windows용 이벤트 추적) 이벤트를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0a13d-103">The topics in this section describe event tracing for Windows (ETW) events.</span></span> <span data-ttu-id="0a13d-104">각 이벤트에는 연결된 키워드 및 수준이 있으며, [CLR ETW 키워드 및 수준](../../../docs/framework/performance/clr-etw-keywords-and-levels.md) 항목에서 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0a13d-104">Each event has an associated keyword and level, which are described in the [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md) topic.</span></span> <span data-ttu-id="0a13d-105">CLR에는 이벤트에 대한 두 개의 공급자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a13d-105">The CLR has two providers for the events:</span></span>  
  
-   <span data-ttu-id="0a13d-106">런타임 공급자 - 사용하도록 설정된 키워드(이벤트 범주)에 따라 이벤트를 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="0a13d-106">The runtime provider, which raises events depending on which keywords (categories of events) are enabled.</span></span> <span data-ttu-id="0a13d-107">CLR 런타임 공급자 GUID는 e13c0d23-ccbc-4e12-931b-d9cc2eee27e4입니다.</span><span class="sxs-lookup"><span data-stu-id="0a13d-107">The CLR runtime provider GUID is e13c0d23-ccbc-4e12-931b-d9cc2eee27e4.</span></span>  
  
-   <span data-ttu-id="0a13d-108">런다운 공급자 - 특별한 용도로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a13d-108">The rundown provider, which has special-purpose uses.</span></span> <span data-ttu-id="0a13d-109">CLR 런다운 공급자 GUID는 a669021c-c450-4609-a035-5af59af4df18입니다.</span><span class="sxs-lookup"><span data-stu-id="0a13d-109">The CLR rundown provider GUID is a669021c-c450-4609-a035-5af59af4df18.</span></span>  
  
 <span data-ttu-id="0a13d-110">공급자에 대한 자세한 내용은 [CLR ETW 공급자](../../../docs/framework/performance/clr-etw-providers.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0a13d-110">For more information about the providers, see [CLR ETW Providers](../../../docs/framework/performance/clr-etw-providers.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0a13d-111">단원 내용</span><span class="sxs-lookup"><span data-stu-id="0a13d-111">In This Section</span></span>  
 [<span data-ttu-id="0a13d-112">런타임 정보 이벤트</span><span class="sxs-lookup"><span data-stu-id="0a13d-112">Runtime Information Events</span></span>](../../../docs/framework/performance/runtime-information-etw-events.md)  
 <span data-ttu-id="0a13d-113">SKU, 버전 번호, 런타임이 활성화된 방법, 시작하는 데 사용된 명령줄 매개 변수, GUID(해당되는 경우) 및 다른 관련 정보를 비롯한 런타임 관련 정보를 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="0a13d-113">Captures information about the runtime, including the SKU, version number, the manner in which the runtime was activated, the command-line parameters it was started with, the GUID (if applicable), and other relevant information.</span></span>  
  
 [<span data-ttu-id="0a13d-114">예외가 throw된 V1 이벤트</span><span class="sxs-lookup"><span data-stu-id="0a13d-114">Exception Thrown_V1 Event</span></span>](../../../docs/framework/performance/exception-thrown-v1-etw-event.md)  
 <span data-ttu-id="0a13d-115">throw된 예외에 대한 정보를 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="0a13d-115">Captures information about exceptions that are thrown.</span></span>  
  
 [<span data-ttu-id="0a13d-116">경합 이벤트</span><span class="sxs-lookup"><span data-stu-id="0a13d-116">Contention Events</span></span>](../../../docs/framework/performance/contention-etw-events.md)  
 <span data-ttu-id="0a13d-117">런타임이 사용하는 모니터 잠금이나 네이티브 잠금의 경합에 대한 정보를 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="0a13d-117">Captures information about contention for monitor locks or native locks that the runtime uses.</span></span>  
  
 [<span data-ttu-id="0a13d-118">스레드 풀 이벤트</span><span class="sxs-lookup"><span data-stu-id="0a13d-118">Thread Pool Events</span></span>](../../../docs/framework/performance/thread-pool-etw-events.md)  
 <span data-ttu-id="0a13d-119">작업자 스레드 풀 및 I/O 스레드 풀에 대한 정보를 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="0a13d-119">Captures information about worker thread pools and I/O thread pools.</span></span>  
  
 [<span data-ttu-id="0a13d-120">로더 이벤트</span><span class="sxs-lookup"><span data-stu-id="0a13d-120">Loader Events</span></span>](../../../docs/framework/performance/loader-etw-events.md)  
 <span data-ttu-id="0a13d-121">응용 프로그램 도메인, 어셈블리 및 모듈 로딩 및 언로딩에 대한 정보를 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="0a13d-121">Captures information about loading and unloading application domains, assemblies, and modules.</span></span>  
  
 [<span data-ttu-id="0a13d-122">메서드 이벤트</span><span class="sxs-lookup"><span data-stu-id="0a13d-122">Method Events</span></span>](../../../docs/framework/performance/method-etw-events.md)  
 <span data-ttu-id="0a13d-123">기호 확인을 위한 CLR 메서드에 대한 정보를 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="0a13d-123">Captures information about CLR methods for symbol resolution.</span></span>  
  
 [<span data-ttu-id="0a13d-124">가비지 수집 이벤트</span><span class="sxs-lookup"><span data-stu-id="0a13d-124">Garbage Collection Events</span></span>](../../../docs/framework/performance/garbage-collection-etw-events.md)  
 <span data-ttu-id="0a13d-125">진단 및 디버깅에 도움이 되는 가비지 수집 관련 정보를 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="0a13d-125">Captures information pertaining to garbage collection, to help in diagnostics and debugging.</span></span>  
  
 [<span data-ttu-id="0a13d-126">JIT 추적 이벤트</span><span class="sxs-lookup"><span data-stu-id="0a13d-126">JIT Tracing Events</span></span>](../../../docs/framework/performance/jit-tracing-etw-events.md)  
 <span data-ttu-id="0a13d-127">JIT(Just-In-Time) 인라인 및 후속 호출에 대한 정보를 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="0a13d-127">Captures information about just-in-time (JIT) inlining and tail calls.</span></span>  
  
 [<span data-ttu-id="0a13d-128">Interop 이벤트</span><span class="sxs-lookup"><span data-stu-id="0a13d-128">Interop Events</span></span>](../../../docs/framework/performance/interop-etw-events.md)  
 <span data-ttu-id="0a13d-129">MSIL(Microsoft intermediate language) 스텁 생성 및 캐싱에 대한 정보를 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="0a13d-129">Captures information about Microsoft intermediate language (MSIL) stub generation and caching.</span></span>  
  
 [<span data-ttu-id="0a13d-130">ARM 이벤트</span><span class="sxs-lookup"><span data-stu-id="0a13d-130">ARM Events</span></span>](../../../docs/framework/performance/application-domain-resource-monitoring-arm-etw-events.md)  
 <span data-ttu-id="0a13d-131">응용 프로그램 도메인의 상태에 대한 세부적인 진단 정보를 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="0a13d-131">Captures detailed diagnostic information about the state of an application domain.</span></span>  
  
 [<span data-ttu-id="0a13d-132">보안 이벤트</span><span class="sxs-lookup"><span data-stu-id="0a13d-132">Security Events</span></span>](../../../docs/framework/performance/security-etw-events.md)  
 <span data-ttu-id="0a13d-133">강력한 이름 및 Authenticode 확인에 대한 정보를 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="0a13d-133">Captures information about strong name and Authenticode verification.</span></span>  
  
 [<span data-ttu-id="0a13d-134">스택 이벤트</span><span class="sxs-lookup"><span data-stu-id="0a13d-134">Stack Event</span></span>](../../../docs/framework/performance/stack-etw-event.md)  
 <span data-ttu-id="0a13d-135">이벤트가 발생한 이후 스택 추적을 생성하기 위해 다른 이벤트와 함께 사용되는 정보를 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="0a13d-135">Captures information that is used with other events to generate stack traces after an event is raised.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a13d-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0a13d-136">See Also</span></span>  
 [<span data-ttu-id="0a13d-137">디버깅 향상 및 ETW를 사용한 성능 조정</span><span class="sxs-lookup"><span data-stu-id="0a13d-137">Improve Debugging And Performance Tuning With ETW</span></span>](http://go.microsoft.com/fwlink/?LinkId=179696)  
 [<span data-ttu-id="0a13d-138">Windows 성능 블로그</span><span class="sxs-lookup"><span data-stu-id="0a13d-138">Windows Performance Blog</span></span>](http://go.microsoft.com/fwlink/?LinkId=179509)  
 [<span data-ttu-id="0a13d-139">.NET Framework 로깅 제어</span><span class="sxs-lookup"><span data-stu-id="0a13d-139">Controlling .NET Framework Logging</span></span>](../../../docs/framework/performance/controlling-logging.md)  
 [<span data-ttu-id="0a13d-140">CLR ETW 공급자</span><span class="sxs-lookup"><span data-stu-id="0a13d-140">CLR ETW Providers</span></span>](../../../docs/framework/performance/clr-etw-providers.md)  
 [<span data-ttu-id="0a13d-141">CLR ETW 키워드 및 수준</span><span class="sxs-lookup"><span data-stu-id="0a13d-141">CLR ETW Keywords and Levels</span></span>](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)  
 [<span data-ttu-id="0a13d-142">공용 언어 런타임의 ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="0a13d-142">ETW Events in the Common Language Runtime</span></span>](../../../docs/framework/performance/etw-events-in-the-common-language-runtime.md)
