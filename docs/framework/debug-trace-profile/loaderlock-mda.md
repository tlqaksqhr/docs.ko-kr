---
title: loaderLock MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deadlocks [.NET Framework]
- LoaderLock MDA
- MDAs (managed debugging assistants), loader locks
- managed debugging assistants (MDAs), loader locks
- operating system loader locks
- loader locks
- locks, threads
ms.assetid: 8c10fa02-1b9c-4be5-ab03-451d943ac1ee
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 90fa57bae7bec1fb7f29ad566e92ae9143a39539
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="loaderlock-mda"></a><span data-ttu-id="d0067-102">loaderLock MDA</span><span class="sxs-lookup"><span data-stu-id="d0067-102">loaderLock MDA</span></span>
<span data-ttu-id="d0067-103">`loaderLock` MDA(관리 디버깅 도우미)는 Microsoft Windows 운영 체제 로더 잠금을 보유하는 스레드에서 관리 코드를 실행하려는 시도를 감지합니다.</span><span class="sxs-lookup"><span data-stu-id="d0067-103">The `loaderLock` managed debugging assistant (MDA) detects attempts to execute managed code on a thread that holds the Microsoft Windows operating system loader lock.</span></span>  <span data-ttu-id="d0067-104">이와 같은 실행은 운영 체제의 로더에서 초기화하기 전에 DLL을 사용하고 교착 상태를 일으킬 수 있으므로 유효하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d0067-104">Any such execution is illegal because it can lead to deadlocks and to use of DLLs before they have been initialized by the operating system's loader.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="d0067-105">증상</span><span class="sxs-lookup"><span data-stu-id="d0067-105">Symptoms</span></span>  
 <span data-ttu-id="d0067-106">운영 체제의 로더 잠금에서 코드를 실행할 때 가장 많이 발생하는 오류는 마찬가지로 로더 잠금이 필요한 다른 Win32 함수를 호출하려고 할 때 스레드가 교착 상태가 된다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d0067-106">The most common failure when executing code inside the operating system's loader lock is that threads will deadlock when attempting to call other Win32 functions that also require the loader lock.</span></span>  <span data-ttu-id="d0067-107">이러한 함수의 예는 `LoadLibrary`, `GetProcAddress`, `FreeLibrary` 및 `GetModuleHandle`입니다.</span><span class="sxs-lookup"><span data-stu-id="d0067-107">Examples of such functions are `LoadLibrary`, `GetProcAddress`, `FreeLibrary`, and `GetModuleHandle`.</span></span>  <span data-ttu-id="d0067-108">응용 프로그램에서 이러한 함수를 직접 호출하지 않을 수 있습니다. CLR(공용 언어 런타임)에서는 <xref:System.Reflection.Assembly.Load%2A>와 같은 상위 레벨 호출 또는 플랫폼 호출 메서드를 처음 호출한 결과로 이러한 함수를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0067-108">The application might not directly call these functions; the common language runtime (CLR) might call these functions as the result of a higher level call like <xref:System.Reflection.Assembly.Load%2A> or the first call to a platform invoke method.</span></span>  
  
 <span data-ttu-id="d0067-109">교착 상태는 한 스레드에서 다른 스레드가 시작하거나 완료되기를 기다리는 경우에도 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0067-109">Deadlocks can also occur if a thread is waiting for another thread to start or finish.</span></span>  <span data-ttu-id="d0067-110">스레드가 실행을 시작하거나 완료하면 영향받은 DLL에 이벤트를 제공하도록 운영 체제의 로더 잠금을 획득해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0067-110">When a thread starts or finishes executing, it must acquire the operating system's loader lock to deliver events to affected DLLs.</span></span>  
  
 <span data-ttu-id="d0067-111">마지막으로 운영 체제의 로더에서 DLL을 제대로 초기화하기 전에 DLL을 호출할 수 있는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0067-111">Finally, there are cases where calls into DLLs can occur before those DLLs have been properly initialized by the operating system's loader.</span></span>  <span data-ttu-id="d0067-112">교착 상태와 관련된 모든 스레드의 스택을 검사하여 진단할 수 있는 교착 상태 오류와 달리 초기화되지 않은 DLL 사용은 이 MDA를 사용하지 않으면 진단하기가 매우 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="d0067-112">Unlike the deadlock failures, which can be diagnosed by examining the stacks of all the threads involved in the deadlock, it is very difficult to diagnose the use of uninitialized DLLs without using this MDA.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="d0067-113">원인</span><span class="sxs-lookup"><span data-stu-id="d0067-113">Cause</span></span>  
 <span data-ttu-id="d0067-114">.NET Framework 버전 1.0 또는 1.1용으로 빌드된 혼합 관리/관리되지 않는 C++ 어셈블리에서는 특별하게 주의를 기울이는 경우가 아니면(예: **/NOENTRY**와 링크) 일반적으로 로더 잠금 내의 관리 코드를 실행하려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="d0067-114">Mixed managed/unmanaged C++ assemblies built for .NET Framework versions 1.0 or 1.1 generally attempt to execute managed code inside the loader lock unless special care has been taken, for example, linking with **/NOENTRY**.</span></span>
  
 <span data-ttu-id="d0067-115">.NET Framework 버전 2.0용으로 빌드된 혼합된 관리/관리되지 않는 C++ 어셈블리에서는 이러한 문제점이 발생할 가능성이 적으며, 운영 체제의 규칙을 위반하는 관리되지 않는 DLL을 사용하는 응용 프로그램과 마찬가지로 위험이 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="d0067-115">Mixed managed/unmanaged C++ assemblies built for .NET Framework version 2.0 are less susceptible to these problems, having the same reduced risk as applications using unmanaged DLLs that violate the operating system's rules.</span></span>  <span data-ttu-id="d0067-116">예를 들어, 관리되지 않는 DLL의 `DllMain` 진입점에서 `CoCreateInstance`를 호출하여 COM에 노출된 관리되는 오브젝트를 확보하는 경우 결과적으로 로더 잠금 내에서 관리 코드를 실행하려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="d0067-116">For example, if an unmanaged DLL's `DllMain` entry point calls `CoCreateInstance` to obtain a managed object that has been exposed to COM, the result is an attempt to execute managed code inside the loader lock.</span></span> <span data-ttu-id="d0067-117">.NET Framework 버전 2.0 이상의 로더 잠금 문제점에 대한 자세한 내용은 [혼합 어셈블리 초기화](/cpp/dotnet/initialization-of-mixed-assemblies)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d0067-117">For more information about loader lock issues in the .NET Framework version 2.0 and later, see [Initialization of Mixed Assemblies](/cpp/dotnet/initialization-of-mixed-assemblies).</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="d0067-118">해결</span><span class="sxs-lookup"><span data-stu-id="d0067-118">Resolution</span></span>  
 <span data-ttu-id="d0067-119">Visual C++ .NET 2002 및 Visual C++ NET 2003에서 `/clr` 컴파일러 옵션을 사용하여 컴파일한 DLL을 로드할 때 명확하지 않은 교착 상태에 빠질 수 있습니다. 이 문제를 혼합 DLL 로드 또는 로더 잠금 문제라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0067-119">In Visual C++ .NET 2002 and Visual C++ .NET 2003, DLLs compiled with the `/clr` compiler option could non-deterministically deadlock when loaded; this issue was called the mixed DLL loading or loader lock issue.</span></span> <span data-ttu-id="d0067-120">Visual C++ 2005 이상에서 혼합 DLL 로드 프로세스의 불명확한 요소가 대부분 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d0067-120">In Visual C++ 2005 and later, almost all non-determinism has been removed from the mixed DLL loading process.</span></span> <span data-ttu-id="d0067-121">그러나 일부 시나리오에서는 명확한 로더 잠금 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0067-121">However, there are a few remaining scenarios for which loader lock can (deterministically) occur.</span></span> <span data-ttu-id="d0067-122">나머지 로더 잠금 문제의 원인과 해결 방법에 대한 자세한 내용은 [혼합 어셈블리 초기화](/cpp/dotnet/initialization-of-mixed-assemblies)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d0067-122">For a detailed account of the causes and resolutions for the remaining loader lock issues, see [Initialization of Mixed Assemblies](/cpp/dotnet/initialization-of-mixed-assemblies).</span></span> <span data-ttu-id="d0067-123">해당 항목에서 로더 잠금 문제를 식별하지 못하는 경우 스레드 스택을 검사하여 로더 잠금이 발생하는 이유와 문제를 정정하는 방법을 판별해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0067-123">If that topic does not identify your loader lock problem, you have to examine the thread's stack to determine why the loader lock is occurring and how to correct the problem.</span></span> <span data-ttu-id="d0067-124">이 MDA가 활성화된 스레드의 스택 추적을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d0067-124">Look at the stack trace for the thread that has activated this MDA.</span></span>  <span data-ttu-id="d0067-125">스레드에서 운영 체제의 로더 잠금을 보유하는 동안 관리 코드를 잘못 호출하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0067-125">The thread is attempting to illegally call into managed code while holding the operating system's loader lock.</span></span>  <span data-ttu-id="d0067-126">DLL의 `DllMain` 또는 스택의 해당 진입점이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0067-126">You will probably see a DLL's `DllMain` or equivalent entry point on the stack.</span></span>  <span data-ttu-id="d0067-127">이러한 진입점에서 올바르게 수행할 수 있는 사항에 대한 운영 체제 규칙은 상당히 제한되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0067-127">The operating system's rules for what you can legally do from inside such an entry point are quite limited.</span></span>  <span data-ttu-id="d0067-128">이러한 규칙은 관리되는 모든 실행을 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="d0067-128">These rules preclude any managed execution.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="d0067-129">런타임에 대한 영향</span><span class="sxs-lookup"><span data-stu-id="d0067-129">Effect on the Runtime</span></span>  
 <span data-ttu-id="d0067-130">일반적으로 프로세스 내의 여러 스레드가 교착 상태가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0067-130">Typically, several threads inside the process will deadlock.</span></span>  <span data-ttu-id="d0067-131">이러한 스레드 중 하나는 가비지 수집을 수행하는 스레드이므로 이 교착 상태가 전체 프로세스에 주된 영향을 미칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0067-131">One of those threads is likely to be a thread responsible for performing a garbage collection, so this deadlock can have a major impact on the entire process.</span></span>  <span data-ttu-id="d0067-132">또한 운영 체제의 로더 잠금이 필요한 추가 작업(예: 어셈블리 또는 DLL 로드 및 로드 해제, 스레드 시작 또는 중지)도 수행하지 못하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0067-132">Furthermore, it will prevent any additional operations that require the operating system's loader lock, like loading and unloading assemblies or DLLs and starting or stopping threads.</span></span>  
  
 <span data-ttu-id="d0067-133">드문 경우지만 액세스 위반이나 이와 비슷한 문제점이 DLL에서 트리거되어 초기화되기 전에 호출되는 문제도 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0067-133">In some unusual cases, it is also possible for access violations or similar problems to be triggered in DLLs which are called before they have been initialized.</span></span>  
  
## <a name="output"></a><span data-ttu-id="d0067-134">출력</span><span class="sxs-lookup"><span data-stu-id="d0067-134">Output</span></span>  
 <span data-ttu-id="d0067-135">이 MDA는 잘못된 관리 실행이 시도되고 있음을 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="d0067-135">This MDA reports that an illegal managed execution is being attempted.</span></span>  <span data-ttu-id="d0067-136">스레드 스택을 검사하여 로더 잠금이 발생하는 이유와 문제를 정정하는 방법을 판별해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0067-136">You need to examine the thread's stack to determine why the loader lock is occurring and how to correct the problem.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="d0067-137">구성</span><span class="sxs-lookup"><span data-stu-id="d0067-137">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <loaderLock/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d0067-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d0067-138">See Also</span></span>  
 [<span data-ttu-id="d0067-139">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="d0067-139">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
