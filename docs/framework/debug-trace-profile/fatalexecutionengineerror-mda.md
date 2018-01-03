---
title: fatalExecutionEngineError MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- corrupted CLR
- fatal execution error
- terminated processes
- unexpected terminations
- fatal errors
- MDAs (managed debugging assistants), fatal errors
- process termination
- FatalExecutionEngineError MDA
- managed debugging assistants (MDAs), fatal errors
ms.assetid: 8b559e44-2393-4e4e-8160-7558d37a4a89
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6eb091883f59302e195d1b49b84693815196a4b5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="fatalexecutionengineerror-mda"></a><span data-ttu-id="fdf8e-102">fatalExecutionEngineError MDA</span><span class="sxs-lookup"><span data-stu-id="fdf8e-102">fatalExecutionEngineError MDA</span></span>
<span data-ttu-id="fdf8e-103">`fatalExecutionEngine``Error` MDA(관리 디버깅 도우미)는 CLR(공용 언어 런타임)에서 오류가 발견될 경우 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdf8e-103">The `fatalExecutionEngine``Error` managed debugging assistant (MDA) is activated when a fatal error in the common language runtime (CLR) has been detected.</span></span> <span data-ttu-id="fdf8e-104">프로세스가 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="fdf8e-104">The process will be terminated.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="fdf8e-105">증상</span><span class="sxs-lookup"><span data-stu-id="fdf8e-105">Symptoms</span></span>  
 <span data-ttu-id="fdf8e-106">예기치 않은 프로세스 종료.</span><span class="sxs-lookup"><span data-stu-id="fdf8e-106">Unexpected process termination.</span></span> <span data-ttu-id="fdf8e-107">다양한 이유로 CLR 오류가 발생할 수 있으므로 다른 증상을 결정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fdf8e-107">Other symptoms cannot be determined because a CLR failure can occur for a variety of reasons.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="fdf8e-108">원인</span><span class="sxs-lookup"><span data-stu-id="fdf8e-108">Cause</span></span>  
 <span data-ttu-id="fdf8e-109">CLR이 심각하게 손상되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fdf8e-109">The CLR has been fatally corrupted.</span></span> <span data-ttu-id="fdf8e-110">이 오류의 가장 많은 원인은 잘못된 형식의 플랫폼 호출 함수를 호출하거나 잘못된 데이터를 CLR에 전달하는 것과 같은 다양한 문제로 인해 발생할 수 있는 데이터 손상입니다.</span><span class="sxs-lookup"><span data-stu-id="fdf8e-110">This is most often caused by data corruption, which can be caused by a number of problems, such as calls to malformed platform invoke functions and passing invalid data to the CLR.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="fdf8e-111">해결</span><span class="sxs-lookup"><span data-stu-id="fdf8e-111">Resolution</span></span>  
 <span data-ttu-id="fdf8e-112">추가적인 MDA를 사용하면 문제를 식별하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdf8e-112">Enabling additional MDAs might help identify the problem.</span></span> <span data-ttu-id="fdf8e-113">다음 MDA는 문제를 진단하는 데 특히 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdf8e-113">The following MDAs can be particularly helpful in diagnosing the issue:</span></span>  
  
-   [<span data-ttu-id="fdf8e-114">invalidOverlappedToPinvoke</span><span class="sxs-lookup"><span data-stu-id="fdf8e-114">invalidOverlappedToPinvoke</span></span>](../../../docs/framework/debug-trace-profile/invalidoverlappedtopinvoke-mda.md)  
  
-   [<span data-ttu-id="fdf8e-115">overlappedFreeError</span><span class="sxs-lookup"><span data-stu-id="fdf8e-115">overlappedFreeError</span></span>](../../../docs/framework/debug-trace-profile/overlappedfreeerror-mda.md)  
  
-   [<span data-ttu-id="fdf8e-116">pInvokeStackImbalance</span><span class="sxs-lookup"><span data-stu-id="fdf8e-116">pInvokeStackImbalance</span></span>](../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md)  
  
-   [<span data-ttu-id="fdf8e-117">gcUnmanagedToManaged</span><span class="sxs-lookup"><span data-stu-id="fdf8e-117">gcUnmanagedToManaged</span></span>](../../../docs/framework/debug-trace-profile/gcunmanagedtomanaged-mda.md)  
  
-   [<span data-ttu-id="fdf8e-118">gcManagedToUnmanaged</span><span class="sxs-lookup"><span data-stu-id="fdf8e-118">gcManagedToUnmanaged</span></span>](../../../docs/framework/debug-trace-profile/gcmanagedtounmanaged-mda.md)  
  
-   [<span data-ttu-id="fdf8e-119">callbackOnCollectedDelegate</span><span class="sxs-lookup"><span data-stu-id="fdf8e-119">callbackOnCollectedDelegate</span></span>](../../../docs/framework/debug-trace-profile/callbackoncollecteddelegate-mda.md)  
  
-   [<span data-ttu-id="fdf8e-120">reportAvOnComRelease</span><span class="sxs-lookup"><span data-stu-id="fdf8e-120">reportAvOnComRelease</span></span>](../../../docs/framework/debug-trace-profile/reportavoncomrelease-mda.md)  
  
-   [<span data-ttu-id="fdf8e-121">invalidVariant</span><span class="sxs-lookup"><span data-stu-id="fdf8e-121">invalidVariant</span></span>](../../../docs/framework/debug-trace-profile/invalidvariant-mda.md)  
  
-   [<span data-ttu-id="fdf8e-122">invalidIUnknown</span><span class="sxs-lookup"><span data-stu-id="fdf8e-122">invalidIUnknown</span></span>](../../../docs/framework/debug-trace-profile/invalidiunknown-mda.md)  
  
-   [<span data-ttu-id="fdf8e-123">raceOnRCWCleanup</span><span class="sxs-lookup"><span data-stu-id="fdf8e-123">raceOnRCWCleanup</span></span>](../../../docs/framework/debug-trace-profile/raceonrcwcleanup-mda.md)  
  
-   [<span data-ttu-id="fdf8e-124">invalidFunctionPointerInDelegate</span><span class="sxs-lookup"><span data-stu-id="fdf8e-124">invalidFunctionPointerInDelegate</span></span>](../../../docs/framework/debug-trace-profile/invalidfunctionpointerindelegate-mda.md)  
  
-   [<span data-ttu-id="fdf8e-125">invalidGCHandleCookie</span><span class="sxs-lookup"><span data-stu-id="fdf8e-125">invalidGCHandleCookie</span></span>](../../../docs/framework/debug-trace-profile/invalidgchandlecookie-mda.md)  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="fdf8e-126">런타임에 대한 영향</span><span class="sxs-lookup"><span data-stu-id="fdf8e-126">Effect on the Runtime</span></span>  
 <span data-ttu-id="fdf8e-127">이 MDA는 런타임 동작에 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fdf8e-127">This MDA has no effect on the runtime's behavior.</span></span>  
  
## <a name="output"></a><span data-ttu-id="fdf8e-128">출력</span><span class="sxs-lookup"><span data-stu-id="fdf8e-128">Output</span></span>  
 <span data-ttu-id="fdf8e-129">오류를 초래한 CLR 함수의 주소, 오류가 발생한 스레드의 ID 및 오류 코드.</span><span class="sxs-lookup"><span data-stu-id="fdf8e-129">The address of the CLR function that caused the fatal error, the ID of the thread where the error occurred, and the error code.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="fdf8e-130">구성</span><span class="sxs-lookup"><span data-stu-id="fdf8e-130">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <fatalExecutionEngineError />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="fdf8e-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fdf8e-131">See Also</span></span>  
 <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A>  
 <xref:System.Runtime.ConstrainedExecution.Cer>  
 [<span data-ttu-id="fdf8e-132">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="fdf8e-132">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
