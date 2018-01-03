---
title: "CLR ETW 공급자"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ETW, CLR providers
- CLR ETW providers
ms.assetid: 0beafad4-b2c8-47f4-b342-83411d57a51f
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0b76b3a1d4969a5ed81e5fa90afb06050b780804
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="clr-etw-providers"></a><span data-ttu-id="ede95-102">CLR ETW 공급자</span><span class="sxs-lookup"><span data-stu-id="ede95-102">CLR ETW Providers</span></span>
<span data-ttu-id="ede95-103">CLR(공용 언어 런타임)에는 런타임 공급자 및 런다운 공급자라는 두 개의 공급자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ede95-103">The common language runtime (CLR) has two providers: the runtime provider and the rundown provider.</span></span>  
  
 <span data-ttu-id="ede95-104">런타임 공급자는 사용하도록 설정된 키워드(이벤트 범주)에 따라 이벤트를 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="ede95-104">The runtime provider raises events, depending on which keywords (categories of events) are enabled.</span></span> <span data-ttu-id="ede95-105">예를 들어 `LoaderKeyword` 키워드를 사용하도록 설정하면 로더 이벤트를 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ede95-105">For example, you can collect loader events by enabling the `LoaderKeyword` keyword.</span></span>  
  
 <span data-ttu-id="ede95-106">ETW(Windows용 이벤트 추적) 이벤트는 .etl 확장명을 가진 파일에 기록되며, 필요에 따라 나중에 쉼표로 구분된 값(.csv) 파일로 사후 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ede95-106">Event tracking for Windows (ETW) events are logged into a file that has an .etl extension, which can later be post-processed in comma-separated value (.csv) files as needed.</span></span> <span data-ttu-id="ede95-107">.etl 파일을 .csv 파일로 변환하는 방법에 대한 자세한 내용은 [.NET Framework 로깅 제어](../../../docs/framework/performance/controlling-logging.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ede95-107">For information about how to convert the .etl file to a .csv file, see [Controlling .NET Framework Logging](../../../docs/framework/performance/controlling-logging.md).</span></span>  
  
## <a name="the-runtime-provider"></a><span data-ttu-id="ede95-108">런타임 공급자</span><span class="sxs-lookup"><span data-stu-id="ede95-108">The Runtime Provider</span></span>  
 <span data-ttu-id="ede95-109">런타임 공급자는 기본 CLR ETW 공급자입니다.</span><span class="sxs-lookup"><span data-stu-id="ede95-109">The runtime provider is the main CLR ETW provider.</span></span>  
  
 <span data-ttu-id="ede95-110">CLR 런타임 공급자 GUID는 e13c0d23-ccbc-4e12-931b-d9cc2eee27e4입니다.</span><span class="sxs-lookup"><span data-stu-id="ede95-110">The CLR runtime provider GUID is e13c0d23-ccbc-4e12-931b-d9cc2eee27e4.</span></span>  
  
 <span data-ttu-id="ede95-111">일반적으로 사용 가능한 도구를 사용하여 CLR ETW 이벤트를 기록하고 보는 방법의 예제는 [.NET Framework 로깅 제어](../../../docs/framework/performance/controlling-logging.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ede95-111">For examples of how to log and view CLR ETW events by using commonly available tools, see [Controlling .NET Framework Logging](../../../docs/framework/performance/controlling-logging.md).</span></span>  
  
 <span data-ttu-id="ede95-112">`LoaderKeyword` 등의 키워드 사용 외에도 너무 자주 발생할 수 있는 이벤트를 기록하기 위해 키워드를 사용하도록 설정해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ede95-112">In addition to using keywords such as `LoaderKeyword`, you may have to enable keywords for logging events that may be raised too frequently.</span></span> <span data-ttu-id="ede95-113">이러한 이벤트는 `StartEnumerationKeyword` 및 `EndEnumerationKeyword` 키워드에 의해 활성화되며 두 키워드는 [CLR ETW 키워드 및 수준](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)에 요약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ede95-113">The `StartEnumerationKeyword` and the `EndEnumerationKeyword` keywords enable these events and are summarized in [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).</span></span>  
  
## <a name="the-rundown-provider"></a><span data-ttu-id="ede95-114">런다운 공급자</span><span class="sxs-lookup"><span data-stu-id="ede95-114">The Rundown Provider</span></span>  
 <span data-ttu-id="ede95-115">특별한 용도에 사용하려면 런다운 공급자를 켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ede95-115">The rundown provider must be turned on for certain special-purpose uses.</span></span> <span data-ttu-id="ede95-116">그러나 대부분의 사용자는 런타임 공급자로 충분합니다.</span><span class="sxs-lookup"><span data-stu-id="ede95-116">However, for a majority of users, the runtime provider should suffice.</span></span>  
  
 <span data-ttu-id="ede95-117">CLR 런다운 공급자 GUID는 A669021C-C450-4609-A035-5AF59AF4DF18입니다.</span><span class="sxs-lookup"><span data-stu-id="ede95-117">The CLR rundown provider GUID is A669021C-C450-4609-A035-5AF59AF4DF18.</span></span>  
  
 <span data-ttu-id="ede95-118">일반적으로 ETW 로깅은 프로세스가 시작되기 전에 사용되고, 프로세스가 종료된 후 로깅이 꺼집니다.</span><span class="sxs-lookup"><span data-stu-id="ede95-118">Normally, ETW logging is enabled before a process launches, and the logging is turned off after the process exits.</span></span> <span data-ttu-id="ede95-119">그러나 프로세스를 실행하는 동안 ETW 로깅이 켜져 있는 경우 프로세스에 대한 추가 정보가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ede95-119">However, if ETW logging is turned on while the process is executing, additional information is needed about the process.</span></span> <span data-ttu-id="ede95-120">예를 들어 기호를 확인하려면 로깅을 켜기 전에 이미 로드된 메서드에 대한 메서드 이벤트를 기록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ede95-120">For example, for symbol resolution you have to log method events for methods that were already loaded before logging was turned on.</span></span>  
  
 <span data-ttu-id="ede95-121">`DCStart` 및 `DCEnd` 이벤트는 데이터 수집이 시작 및 중지될 때 프로세스의 상태를 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="ede95-121">The `DCStart` and `DCEnd` events capture the state of the process when data collection was started and stopped.</span></span> <span data-ttu-id="ede95-122">상태는 JIT(Just-In-Time) 컴파일된 메서드 및 로드된 어셈블리를 포함하여 개괄적인 정보를 참조합니다. 이러한 두 이벤트는 프로세스에서 이미 발생한 사항(예: JIT 컴파일된 메서드 등)에 대한 정보를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ede95-122">(State refers to information at a high level, including the methods that were already just-in-time (JIT) compiled and assemblies that were loaded.) These two events can provide information about what has already happened in the process; for example, which methods were JIT- compiled, and so on.</span></span>  
  
 <span data-ttu-id="ede95-123">`DC`, `DCStart`, `DCEnd` 또는 `DCInit`가 이름에 포함된 이벤트만 런다운 공급자 아래에서 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="ede95-123">Only the events with `DC`, `DCStart`, `DCEnd`, or `DCInit` in their names are raised under the rundown provider.</span></span> <span data-ttu-id="ede95-124">또한 이들 이벤트는 런다운 공급자에서만 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="ede95-124">Additionally, these events are raised only under the rundown provider.</span></span>  
  
 <span data-ttu-id="ede95-125">이벤트 키워드 필터 외에도 런다운 공급자는 대상 필터링을 제공하는 `StartRundownKeyword` 및 `EndRundownKeyword` 키워드도 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ede95-125">In addition to the event keyword filters, the rundown provider also supports the `StartRundownKeyword` and `EndRundownKeyword` keywords to provide targeted filtering.</span></span>  
  
### <a name="start-rundown"></a><span data-ttu-id="ede95-126">시작 런다운</span><span class="sxs-lookup"><span data-stu-id="ede95-126">Start Rundown</span></span>  
 <span data-ttu-id="ede95-127">시작 런다운은 런다운 공급자 아래의 로깅이 `StartRundownKeyword` 키워드로 활성화된 경우에 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="ede95-127">A start rundown is triggered when logging under the rundown provider is enabled with the `StartRundownKeyword` keyword.</span></span> <span data-ttu-id="ede95-128">이 경우 `DCStart`가 발생하고 시스템 상태가 캡처됩니다.</span><span class="sxs-lookup"><span data-stu-id="ede95-128">This causes the `DCStart` event to be raised, and captures the state of the system.</span></span> <span data-ttu-id="ede95-129">열거를 시작하기 전에 `DCStartInit` 이벤트가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="ede95-129">Before the start of the enumeration, the `DCStartInit` event is raised.</span></span> <span data-ttu-id="ede95-130">열거형의 끝에는 `DCStartComplete` 이벤트가 발생하여 데이터 수집이 정상적으로 종료되었음을 컨트롤러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="ede95-130">At the end of the enumeration, the `DCStartComplete` event is raised to notify the controller that data collection terminated normally.</span></span>  
  
### <a name="end-rundown"></a><span data-ttu-id="ede95-131">끝 런다운</span><span class="sxs-lookup"><span data-stu-id="ede95-131">End Rundown</span></span>  
 <span data-ttu-id="ede95-132">끝 런다운은 런다운 공급자 아래의 로깅이 `EndRundownKeyword` 키워드로 활성화된 경우에 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="ede95-132">An end rundown is triggered when logging under the rundown provider is enabled with the `EndRundownKeyword` keyword.</span></span> <span data-ttu-id="ede95-133">끝 런다운은 계속 실행되는 프로세스에 대한 프로파일링을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="ede95-133">End rundown stops profiling on a process that continues to execute.</span></span> <span data-ttu-id="ede95-134">`DCEnd` 이벤트는 프로파일링이 중지될 때의 시스템 상태를 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="ede95-134">The `DCEnd` events capture the state of the system when profiling is stopped.</span></span>  
  
 <span data-ttu-id="ede95-135">열거를 시작하기 전에 `DCEndInit` 이벤트가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="ede95-135">Before the start of the enumeration, the `DCEndInit` event is raised.</span></span> <span data-ttu-id="ede95-136">열거형의 끝에는 `DCEndComplete` 이벤트가 발생하여 데이터 수집이 정상적으로 종료되었음을 소비자에게 알립니다.</span><span class="sxs-lookup"><span data-stu-id="ede95-136">At the end of the enumeration, the `DCEndComplete` event is raised to notify the consumer that data collection terminated normally.</span></span> <span data-ttu-id="ede95-137">시작 런다운 및 끝 런다운은 주로 관리되는 기호 확인에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ede95-137">Start rundown and end rundown are primarily used for managed symbol resolution.</span></span> <span data-ttu-id="ede95-138">시작 런다운은 프로파일링 세션이 시작되기 전에 이미 JIT 컴파일된 메서드에 대한 주소 범위 정보를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ede95-138">Start rundown can provide address range information for methods that were already JIT-compiled before the profiling session was started.</span></span> <span data-ttu-id="ede95-139">끝 런다운은 프로파일링을 끌 때 JIT 컴파일된 모든 메서드에 대한 주소 범위 정보를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ede95-139">End rundown can provide address range information for all methods that have been JIT-compiled when profiling is about to be turned off.</span></span>  
  
 <span data-ttu-id="ede95-140">끝 런다운은 프로파일링 세션을 중지할 때 자동으로 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ede95-140">End rundown does not happen automatically when a profiling session is stopped.</span></span> <span data-ttu-id="ede95-141">대신, 프로파일링이 중지되기 직전에 관리되는 기호 확인을 수행하려는 도구가 `EndRundownKeyword` 키워드를 사용하여 CLR 런다운 공급자 세션을 명시적으로 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ede95-141">Instead, a tool that is seeking to perform managed symbol resolution has to explicitly invoke a CLR rundown provider session with the `EndRundownKeyword` keyword enabled, just before profiling is stopped.</span></span>  
  
 <span data-ttu-id="ede95-142">시작 런다운 또는 끝 런다운은 관리되는 기호 확인을 위해 메서드 주소 범위 정보를 제공할 수 있지만 `StartRundownKeyword` 키워드(`DCStart` 이벤트 제공) 대신 `EndRundownKeyword` 키워드(`DCEnd` 이벤트 제공)를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ede95-142">Although either start rundown or end rundown can provide method address range information for managed symbol resolution, we recommend that you use the `EndRundownKeyword` keyword (which supplies `DCEnd` events) instead of the `StartRundownKeyword` keyword (which supplies `DCStart` events).</span></span> <span data-ttu-id="ede95-143">`StartRundownKeyword`를 사용하면 프로파일링 세션 중에 런다운이 발생하며 프로파일링된 시나리오를 방해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ede95-143">Using `StartRundownKeyword` causes the rundown to happen during the profiling session, which may disturb the profiled scenario.</span></span>  
  
## <a name="etw-data-collection-using-runtime-and-rundown-providers"></a><span data-ttu-id="ede95-144">런타임 및 런다운 공급자를 사용한 ETW 데이터 수집</span><span class="sxs-lookup"><span data-stu-id="ede95-144">ETW Data Collection Using Runtime and Rundown Providers</span></span>  
 <span data-ttu-id="ede95-145">다음 예제에서는 프로세스가 프로파일링된 창 내부 또는 외부에서 시작 또는 종료되는지에 관계없이 최소한의 영향으로 관리되는 프로세스의 기호 확인을 허용하는 방식으로 CLR 런다운 공급자를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ede95-145">The following example demonstrates how to use the CLR rundown provider in a way that allows symbol resolution of managed processes with minimal impact, regardless of whether the processes start or end inside or outside the profiled window.</span></span>  
  
1.  <span data-ttu-id="ede95-146">CLR 런타임 공급자를 사용하여 ETW 로깅 켜기:</span><span class="sxs-lookup"><span data-stu-id="ede95-146">Turn on ETW logging by using the CLR runtime provider:</span></span>  
  
    ```  
    xperf -start clr -on e13c0d23-ccbc-4e12-931b-d9cc2eee27e4:0x1CCBD:0x5 -f clr1.etl      
    ```  
  
     <span data-ttu-id="ede95-147">로그는 clr1.etl 파일에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="ede95-147">The log will be saved to the clr1.etl file.</span></span>  
  
2.  <span data-ttu-id="ede95-148">프로세스를 계속 실행하는 동안 프로파일링을 중지하려면 런다운 공급자를 시작하여 `DCEnd` 이벤트를 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="ede95-148">To stop profiling while the process continues to execute, start the rundown provider to capture the `DCEnd` events:</span></span>  
  
    ```  
    xperf -start clrRundown -on A669021C-C450-4609-A035-5AF59AF4DF18:0xB8:0x5 -f clr2.etl      
    ```  
  
     <span data-ttu-id="ede95-149">이렇게 하면 `DCEnd` 이벤트 컬렉션이 런다운 세션을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ede95-149">This enables the collection of `DCEnd` events to start a rundown session.</span></span> <span data-ttu-id="ede95-150">모든 이벤트가 수집되도록 30-60초 기다려야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ede95-150">You may need to wait 30 to 60 seconds for all events to be collected.</span></span> <span data-ttu-id="ede95-151">로그는 clr1.et2 파일에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="ede95-151">The log will be saved to the clr1.et2 file.</span></span>  
  
3.  <span data-ttu-id="ede95-152">모든 ETW 프로파일링 끄기:</span><span class="sxs-lookup"><span data-stu-id="ede95-152">Turn off all ETW profiling:</span></span>  
  
    ```  
    xperf -stop clrRundown   
    xperf -stop clr  
    ```  
  
4.  <span data-ttu-id="ede95-153">프로필을 병합하여 하나의 로그 파일 만들기:</span><span class="sxs-lookup"><span data-stu-id="ede95-153">Merge the profiles to create one log file:</span></span>  
  
    ```  
    xperf -merge -d clr1.etl clr2.etl merged.etl  
    ```  
  
     <span data-ttu-id="ede95-154">merged.etl 파일에는 런타임 및 런다운 공급자 세션의 이벤트가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ede95-154">The merged.etl file will contain the events from the runtime and the rundown provider sessions.</span></span>  
  
 <span data-ttu-id="ede95-155">도구는 사용자가 프로파일링 중지를 요청할 때 프로파일링을 즉시 끄지 않고 2단계와 3단계(런다운 세션을 시작한 다음 프로파일링 종료)를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ede95-155">A tool can execute steps 2 and 3 (starting a rundown session and then terminating profiling) instead of immediately turning off profiling when a user requests profiling to be stopped.</span></span> <span data-ttu-id="ede95-156">도구에서 4단계를 실행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ede95-156">A tool can also execute step 4.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ede95-157">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ede95-157">See Also</span></span>  
 [<span data-ttu-id="ede95-158">공용 언어 런타임의 ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="ede95-158">ETW Events in the Common Language Runtime</span></span>](../../../docs/framework/performance/etw-events-in-the-common-language-runtime.md)
