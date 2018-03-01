---
title: "관리 디버깅 도우미를 사용하여 오류 진단"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- EHMDA
helpviewer_keywords:
- run-time error debugging
- managed code, run-time debugging
- resource debugging
- registry, MDAs
- common language runtime, debugging
- MDAs (managed debugging assistants)
- configuration files [.NET Framework], debugging runtime events
- messages, managed debugging assistants
- application configuration files, managed debugging assistants
- debugging [.NET Framework], managed debugging assistants
- environment variables, MDAs
- access violation debugging [.NET Framework]
- diagnostics, managed debugging assistants
- unmanaged code, run-time debugging
- default debug output stream
- memory, debugging
- app.config files, managed debugging assistants
- managed debugging assistants (MDAs)
- debugging [.NET Framework], run-time errors
- trapping events
- runtime, error debugging
- disabling MDAs
- output, managed debugging assistants
- errors [.NET Framework], managed debugging assistants
ms.assetid: 76994ee6-9fa9-4059-b813-26578d24427c
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 12a96068412f05d48b8b006385c66f3efbbf9870
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="diagnosing-errors-with-managed-debugging-assistants"></a><span data-ttu-id="74ad0-102">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="74ad0-102">Diagnosing Errors with Managed Debugging Assistants</span></span>
<span data-ttu-id="74ad0-103">MDA(관리 디버깅 도우미)는 런타임 상태에 대한 정보를 제공하기 위해 CLR(공용 언어 런타임)과 함께 작동하는 디버깅 도우미입니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-103">Managed debugging assistants (MDAs) are debugging aids that work in conjunction with the common language runtime (CLR) to provide information on runtime state.</span></span> <span data-ttu-id="74ad0-104">이 도우미는 다른 방법으로는 트래핑할 수 없는 런타임 이벤트에 대한 정보 메시지를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-104">The assistants generate informational messages about runtime events that you cannot otherwise trap.</span></span> <span data-ttu-id="74ad0-105">MDA를 사용하면 관리 코드와 비관리 코드 간에 변환할 때 발생하는 찾기 어려운 응용 프로그램 버그를 구분할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-105">You can use MDAs to isolate hard-to-find application bugs that occur when transitioning between managed and unmanaged code.</span></span> <span data-ttu-id="74ad0-106">Windows 레지스트리에 키를 추가하거나 환경 변수를 설정하여 모든 MDA를 사용하거나 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-106">You can enable or disable all MDAs by adding a key to the Windows registry or by setting an environment variable.</span></span> <span data-ttu-id="74ad0-107">응용 프로그램 구성 설정을 사용하여 특정 MDA를 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-107">You can enable specific MDAs by using application configuration settings.</span></span> <span data-ttu-id="74ad0-108">응용 프로그램의 구성 파일에서 일부 개별 MDA에 대한 추가 구성 설정을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-108">You can set additional configuration settings for some individual MDAs in the application's configuration file.</span></span> <span data-ttu-id="74ad0-109">이러한 구성 파일은 런타임이 로드될 때 구문 분석되므로 관리되는 응용 프로그램이 시작되기 전에 MDA를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-109">Because these configuration files are parsed when the runtime is loaded, you must enable the MDA before the managed application starts.</span></span> <span data-ttu-id="74ad0-110">이미 시작된 응용 프로그램에 대해서는 MDA를 사용하도록 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-110">You cannot enable it for applications that have already started.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="74ad0-111">MDA가 사용하도록 설정되면 코드가 디버거에서 실행되지 않을 때도 MDA가 활성 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-111">When an MDA is enabled, it is active even when your code is not executing under a debugger.</span></span> <span data-ttu-id="74ad0-112">디버거가 없을 때 MDA 이벤트가 발생하면 이벤트 메시지가 처리되지 않은 예외가 아니더라도 처리되지 않은 예외 대화 상자에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-112">If an MDA event is raised when a debugger is not present, the event message is presented in an unhandled exception dialog box, although it is not an unhandled exception.</span></span> <span data-ttu-id="74ad0-113">이 대화 상자가 표시되지 않도록 하려면 코드가 디버깅 환경에서 실행되지 않는 경우 MDA 사용 설정을 제거하세요.</span><span class="sxs-lookup"><span data-stu-id="74ad0-113">To avoid the dialog box, remove the MDA-enabling settings when your code is not executing in a debugging environment.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="74ad0-114">코드가 Visual Studio IDE(통합 개발 환경)에서 실행되는 경우 특정 MDA 이벤트에 대해 나타나는 예외 대화 상자가 표시되지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-114">When your code is executing in the Visual Studio integrated development environment (IDE), you can avoid the exception dialog box that appears for specific MDA events.</span></span> <span data-ttu-id="74ad0-115">이렇게 하려면 **디버그** 메뉴에서 **예외**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-115">To do that, on the **Debug** menu, click **Exceptions**.</span></span> <span data-ttu-id="74ad0-116">(**디버그** 메뉴에 **예외** 명령이 없는 경우 **도구** 메뉴에서 **사용자 지정**을 클릭하여 추가합니다.) **예외** 대화 상자에서 **관리 디버깅 도우미** 목록을 확장한 다음 개별 MDA의 **Throw됨** 확인란을 선택 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-116">(If the **Debug** menu does not contain an **Exceptions** command, click **Customize** on the **Tools** menu to add it.) In the **Exceptions** dialog box, expand the **Managed Debugging Assistants** list, and then clear the **Thrown** check box for the individual MDA.</span></span> <span data-ttu-id="74ad0-117">예를 들어, [contextSwitchDeadlock](../../../docs/framework/debug-trace-profile/contextswitchdeadlock-mda.md)에 대한 예외 대화 상자가 표시되지 않도록 하려면 **관리 디버깅 도우미** 목록에서 해당 이름 옆에 있는 **Throw됨** 확인란을 선택 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-117">For example, to avoid the exception dialog box for a [contextSwitchDeadlock](../../../docs/framework/debug-trace-profile/contextswitchdeadlock-mda.md) clear the **Thrown** check box next to its name in the **Managed Debugging Assistants** list.</span></span> <span data-ttu-id="74ad0-118">또한 이 대화 상자를 사용하여 MDA 예외 대화 상자가 표시되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-118">You can also use this dialog box to enable the display of MDA exception dialog boxes.</span></span>  
  
 <span data-ttu-id="74ad0-119">다음 테이블에서는 .NET Framework와 함께 제공되는 MDA를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-119">The following table lists the MDAs that ship with the .NET Framework.</span></span>  
  
|||  
|-|-|  
|[<span data-ttu-id="74ad0-120">asynchronousThreadAbort</span><span class="sxs-lookup"><span data-stu-id="74ad0-120">asynchronousThreadAbort</span></span>](../../../docs/framework/debug-trace-profile/asynchronousthreadabort-mda.md)|[<span data-ttu-id="74ad0-121">bindingFailure</span><span class="sxs-lookup"><span data-stu-id="74ad0-121">bindingFailure</span></span>](../../../docs/framework/debug-trace-profile/bindingfailure-mda.md)|  
|[<span data-ttu-id="74ad0-122">callbackOnCollectedDelegate</span><span class="sxs-lookup"><span data-stu-id="74ad0-122">callbackOnCollectedDelegate</span></span>](../../../docs/framework/debug-trace-profile/callbackoncollecteddelegate-mda.md)|[<span data-ttu-id="74ad0-123">contextSwitchDeadlock</span><span class="sxs-lookup"><span data-stu-id="74ad0-123">contextSwitchDeadlock</span></span>](../../../docs/framework/debug-trace-profile/contextswitchdeadlock-mda.md)|  
|[<span data-ttu-id="74ad0-124">dangerousThreadingAPI</span><span class="sxs-lookup"><span data-stu-id="74ad0-124">dangerousThreadingAPI</span></span>](../../../docs/framework/debug-trace-profile/dangerousthreadingapi-mda.md)|[<span data-ttu-id="74ad0-125">dateTimeInvalidLocalFormat</span><span class="sxs-lookup"><span data-stu-id="74ad0-125">dateTimeInvalidLocalFormat</span></span>](../../../docs/framework/debug-trace-profile/datetimeinvalidlocalformat-mda.md)|  
|[<span data-ttu-id="74ad0-126">dirtyCastAndCallOnInterface</span><span class="sxs-lookup"><span data-stu-id="74ad0-126">dirtyCastAndCallOnInterface</span></span>](../../../docs/framework/debug-trace-profile/dirtycastandcalloninterface-mda.md)|[<span data-ttu-id="74ad0-127">disconnectedContext</span><span class="sxs-lookup"><span data-stu-id="74ad0-127">disconnectedContext</span></span>](../../../docs/framework/debug-trace-profile/disconnectedcontext-mda.md)|  
|[<span data-ttu-id="74ad0-128">dllMainReturnsFalse</span><span class="sxs-lookup"><span data-stu-id="74ad0-128">dllMainReturnsFalse</span></span>](../../../docs/framework/debug-trace-profile/dllmainreturnsfalse-mda.md)|[<span data-ttu-id="74ad0-129">exceptionSwallowedOnCallFromCom</span><span class="sxs-lookup"><span data-stu-id="74ad0-129">exceptionSwallowedOnCallFromCom</span></span>](../../../docs/framework/debug-trace-profile/exceptionswallowedoncallfromcom-mda.md)|  
|[<span data-ttu-id="74ad0-130">failedQI</span><span class="sxs-lookup"><span data-stu-id="74ad0-130">failedQI</span></span>](../../../docs/framework/debug-trace-profile/failedqi-mda.md)|[<span data-ttu-id="74ad0-131">fatalExecutionEngineError</span><span class="sxs-lookup"><span data-stu-id="74ad0-131">fatalExecutionEngineError</span></span>](../../../docs/framework/debug-trace-profile/fatalexecutionengineerror-mda.md)|  
|[<span data-ttu-id="74ad0-132">gcManagedToUnmanaged</span><span class="sxs-lookup"><span data-stu-id="74ad0-132">gcManagedToUnmanaged</span></span>](../../../docs/framework/debug-trace-profile/gcmanagedtounmanaged-mda.md)|[<span data-ttu-id="74ad0-133">gcUnmanagedToManaged</span><span class="sxs-lookup"><span data-stu-id="74ad0-133">gcUnmanagedToManaged</span></span>](../../../docs/framework/debug-trace-profile/gcunmanagedtomanaged-mda.md)|  
|[<span data-ttu-id="74ad0-134">illegalPrepareConstrainedRegion</span><span class="sxs-lookup"><span data-stu-id="74ad0-134">illegalPrepareConstrainedRegion</span></span>](../../../docs/framework/debug-trace-profile/illegalprepareconstrainedregion-mda.md)|[<span data-ttu-id="74ad0-135">invalidApartmentStateChange</span><span class="sxs-lookup"><span data-stu-id="74ad0-135">invalidApartmentStateChange</span></span>](../../../docs/framework/debug-trace-profile/invalidapartmentstatechange-mda.md)|  
|[<span data-ttu-id="74ad0-136">invalidCERCall</span><span class="sxs-lookup"><span data-stu-id="74ad0-136">invalidCERCall</span></span>](../../../docs/framework/debug-trace-profile/invalidcercall-mda.md)|[<span data-ttu-id="74ad0-137">invalidFunctionPointerInDelegate</span><span class="sxs-lookup"><span data-stu-id="74ad0-137">invalidFunctionPointerInDelegate</span></span>](../../../docs/framework/debug-trace-profile/invalidfunctionpointerindelegate-mda.md)|  
|[<span data-ttu-id="74ad0-138">invalidGCHandleCookie</span><span class="sxs-lookup"><span data-stu-id="74ad0-138">invalidGCHandleCookie</span></span>](../../../docs/framework/debug-trace-profile/invalidgchandlecookie-mda.md)|[<span data-ttu-id="74ad0-139">invalidIUnknown</span><span class="sxs-lookup"><span data-stu-id="74ad0-139">invalidIUnknown</span></span>](../../../docs/framework/debug-trace-profile/invalidiunknown-mda.md)|  
|[<span data-ttu-id="74ad0-140">invalidMemberDeclaration</span><span class="sxs-lookup"><span data-stu-id="74ad0-140">invalidMemberDeclaration</span></span>](../../../docs/framework/debug-trace-profile/invalidmemberdeclaration-mda.md)|[<span data-ttu-id="74ad0-141">invalidOverlappedToPinvoke</span><span class="sxs-lookup"><span data-stu-id="74ad0-141">invalidOverlappedToPinvoke</span></span>](../../../docs/framework/debug-trace-profile/invalidoverlappedtopinvoke-mda.md)|  
|[<span data-ttu-id="74ad0-142">invalidVariant</span><span class="sxs-lookup"><span data-stu-id="74ad0-142">invalidVariant</span></span>](../../../docs/framework/debug-trace-profile/invalidvariant-mda.md)|[<span data-ttu-id="74ad0-143">jitCompilationStart</span><span class="sxs-lookup"><span data-stu-id="74ad0-143">jitCompilationStart</span></span>](../../../docs/framework/debug-trace-profile/jitcompilationstart-mda.md)|  
|[<span data-ttu-id="74ad0-144">loaderLock</span><span class="sxs-lookup"><span data-stu-id="74ad0-144">loaderLock</span></span>](../../../docs/framework/debug-trace-profile/loaderlock-mda.md)|[<span data-ttu-id="74ad0-145">loadFromContext</span><span class="sxs-lookup"><span data-stu-id="74ad0-145">loadFromContext</span></span>](../../../docs/framework/debug-trace-profile/loadfromcontext-mda.md)|  
|[<span data-ttu-id="74ad0-146">marshalCleanupError</span><span class="sxs-lookup"><span data-stu-id="74ad0-146">marshalCleanupError</span></span>](../../../docs/framework/debug-trace-profile/marshalcleanuperror-mda.md)|[<span data-ttu-id="74ad0-147">marshaling</span><span class="sxs-lookup"><span data-stu-id="74ad0-147">marshaling</span></span>](../../../docs/framework/debug-trace-profile/marshaling-mda.md)|  
|[<span data-ttu-id="74ad0-148">memberInfoCacheCreation</span><span class="sxs-lookup"><span data-stu-id="74ad0-148">memberInfoCacheCreation</span></span>](../../../docs/framework/debug-trace-profile/memberinfocachecreation-mda.md)|[<span data-ttu-id="74ad0-149">moduloObjectHashcode</span><span class="sxs-lookup"><span data-stu-id="74ad0-149">moduloObjectHashcode</span></span>](../../../docs/framework/debug-trace-profile/moduloobjecthashcode-mda.md)|  
|[<span data-ttu-id="74ad0-150">nonComVisibleBaseClass</span><span class="sxs-lookup"><span data-stu-id="74ad0-150">nonComVisibleBaseClass</span></span>](../../../docs/framework/debug-trace-profile/noncomvisiblebaseclass-mda.md)|[<span data-ttu-id="74ad0-151">notMarshalable</span><span class="sxs-lookup"><span data-stu-id="74ad0-151">notMarshalable</span></span>](../../../docs/framework/debug-trace-profile/notmarshalable-mda.md)|  
|[<span data-ttu-id="74ad0-152">openGenericCERCall</span><span class="sxs-lookup"><span data-stu-id="74ad0-152">openGenericCERCall</span></span>](../../../docs/framework/debug-trace-profile/opengenericcercall-mda.md)|[<span data-ttu-id="74ad0-153">overlappedFreeError</span><span class="sxs-lookup"><span data-stu-id="74ad0-153">overlappedFreeError</span></span>](../../../docs/framework/debug-trace-profile/overlappedfreeerror-mda.md)|  
|[<span data-ttu-id="74ad0-154">pInvokeLog</span><span class="sxs-lookup"><span data-stu-id="74ad0-154">pInvokeLog</span></span>](../../../docs/framework/debug-trace-profile/pinvokelog-mda.md)|[<span data-ttu-id="74ad0-155">pInvokeStackImbalance</span><span class="sxs-lookup"><span data-stu-id="74ad0-155">pInvokeStackImbalance</span></span>](../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md)|  
|[<span data-ttu-id="74ad0-156">raceOnRCWCleanup</span><span class="sxs-lookup"><span data-stu-id="74ad0-156">raceOnRCWCleanup</span></span>](../../../docs/framework/debug-trace-profile/raceonrcwcleanup-mda.md)|[<span data-ttu-id="74ad0-157">reentrancy</span><span class="sxs-lookup"><span data-stu-id="74ad0-157">reentrancy</span></span>](../../../docs/framework/debug-trace-profile/reentrancy-mda.md)|  
|[<span data-ttu-id="74ad0-158">releaseHandleFailed</span><span class="sxs-lookup"><span data-stu-id="74ad0-158">releaseHandleFailed</span></span>](../../../docs/framework/debug-trace-profile/releasehandlefailed-mda.md)|[<span data-ttu-id="74ad0-159">reportAvOnComRelease</span><span class="sxs-lookup"><span data-stu-id="74ad0-159">reportAvOnComRelease</span></span>](../../../docs/framework/debug-trace-profile/reportavoncomrelease-mda.md)|  
|[<span data-ttu-id="74ad0-160">streamWriterBufferedDataLost</span><span class="sxs-lookup"><span data-stu-id="74ad0-160">streamWriterBufferedDataLost</span></span>](../../../docs/framework/debug-trace-profile/streamwriterbuffereddatalost-mda.md)|[<span data-ttu-id="74ad0-161">virtualCERCall</span><span class="sxs-lookup"><span data-stu-id="74ad0-161">virtualCERCall</span></span>](../../../docs/framework/debug-trace-profile/virtualcercall-mda.md)|  
  
 <span data-ttu-id="74ad0-162">기본적으로 .NET Framework는 모든 관리되는 디버거에 대한 MDA의 하위 집합을 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-162">By default, the .NET Framework activates a subset of MDAs for all managed debuggers.</span></span> <span data-ttu-id="74ad0-163">**디버그** 메뉴에서 **예외**를 클릭하고 **관리 디버깅 도우미** 목록을 확장하여 Visual Studio의 기본 집합을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-163">You can view the default set in Visual Studio by clicking **Exceptions** on the **Debug** menu and expanding the **Managed Debugging Assistants** list.</span></span>  
  
## <a name="enabling-and-disabling-mdas"></a><span data-ttu-id="74ad0-164">MDA 사용 및 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="74ad0-164">Enabling and Disabling MDAs</span></span>  
 <span data-ttu-id="74ad0-165">레지스트리 키, 환경 변수 및 응용 프로그램 구성 설정을 사용하여 MDA를 사용하거나 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-165">You can enable and disable MDAs by using a registry key, an environment variable, and application configuration settings.</span></span> <span data-ttu-id="74ad0-166">응용 프로그램 구성 설정을 사용하려면 레지스트리 키 또는 환경 변수를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-166">You must enable either the registry key or the environment variable to use the application configuration settings.</span></span>  
  
 <span data-ttu-id="74ad0-167">Visual Studio 2005 이상 버전에서는 호스팅 프로세스가 사용하도록 설정된 경우 기본 집합에 있는 MDA를 사용하지 않도록 설정하거나 기본 집합에 없는 MDA를 사용하도록 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-167">In Visual Studio 2005 and later versions, when the hosting process is enabled, you cannot disable MDAs that are in the default set or enable MDAs that are not in the default set.</span></span> <span data-ttu-id="74ad0-168">호스팅 프로세스는 기본적으로 사용하도록 설정되므로 명시적으로 사용하지 않도록 설정되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-168">The hosting process is enabled by default, so it must be explicitly disabled.</span></span>  
  
 <span data-ttu-id="74ad0-169">Visual Studio에서 호스팅 프로세스를 사용하지 않도록 설정하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-169">To disable the hosting process in Visual Studio, do the following:</span></span>  
  
1.  <span data-ttu-id="74ad0-170">**솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-170">In **Solution Explorer**, select a project.</span></span>  
  
2.  <span data-ttu-id="74ad0-171">**프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-171">On the **Project** menu, click **Properties**.</span></span>  
  
     <span data-ttu-id="74ad0-172">**프로젝트 디자이너** 창이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-172">The **Project Designer** window appears.</span></span>  
  
3.  <span data-ttu-id="74ad0-173">**디버그** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-173">Click the **Debug** tab.</span></span>  
  
4.  <span data-ttu-id="74ad0-174">**디버거 사용** 섹션에서 **Visual Studio 호스팅 프로세스 사용** 확인란을 선택 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-174">In the **Enable Debuggers** section, clear the **Enable the Visual Studio hosting process** check box.</span></span>  
  
 <span data-ttu-id="74ad0-175">그러나 호스팅 프로세스를 사용하지 않도록 설정하면 성능에 영향을 미칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-175">However, disabling the hosting process can affect performance.</span></span> <span data-ttu-id="74ad0-176">MDA 알림을 받을 때마다 Visual Studio에 MDA 대화 상자가 표시되지 않도록 하여 MDA를 사용하지 않도록 설정해야 하는 필요성을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-176">You can avoid the need to disable MDAs by preventing Visual Studio from displaying the MDA dialog box whenever an MDA notification is received.</span></span> <span data-ttu-id="74ad0-177">이렇게 하려면 **디버그** 메뉴에서 **예외**를 클릭하고 **관리 디버깅 도우미** 목록을 확장한 다음 개별 MDA의 **Throw됨** 확인란을 선택하거나 선택 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-177">To do that, click **Exceptions** on the **Debug** menu, expand the **Managed Debugging Assistants** list, and then select or clear the **Thrown** check box for the individual MDA.</span></span>  
  
### <a name="enabling-and-disabling-mdas-by-using-a-registry-key"></a><span data-ttu-id="74ad0-178">레지스트리 키를 사용하여 MDA 사용 및 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="74ad0-178">Enabling and Disabling MDAs by Using a Registry Key</span></span>  
 <span data-ttu-id="74ad0-179">Windows 레지스트리에서 HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework\MDA 하위 키(종류 REG_SZ, 값 1)를 추가하여 MDA를 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-179">You can enable MDAs by adding the HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework\MDA subkey (type REG_SZ, value 1) in the Windows registry.</span></span> <span data-ttu-id="74ad0-180">다음 예제를 MDAEnable.reg라는 텍스트 파일에 복사합니다. Windows 레지스트리 편집기(RegEdit.exe)를 열고 **파일** 메뉴에서 **가져오기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-180">Copy the following example into a text file named MDAEnable.reg. Open the Windows Registry Editor (RegEdit.exe) and from the **File** menu choose **Import**.</span></span> <span data-ttu-id="74ad0-181">MDAEnable.reg 파일을 선택하여 해당 컴퓨터에서 MDA를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-181">Select the MDAEnable.reg  file to enable MDAs on that computer.</span></span> <span data-ttu-id="74ad0-182">하위 키를 문자열 값 1(DWORD 값 1 아님)로 설정하면 *ApplicationName.suffix*.mda.config 파일에서 MDA 설정 읽기가 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-182">Setting the subkey to string value of 1 (not DWORD value of 1) enables the reading of MDA settings from the *ApplicationName.suffix*.mda.config file.</span></span> <span data-ttu-id="74ad0-183">(예를 들어, 메모장의 MDA 구성 파일은 이름이 notepad.exe.mda.config로 지정됩니다.)</span><span class="sxs-lookup"><span data-stu-id="74ad0-183">(For example the MDA configuration file for Notepad would be named notepad.exe.mda.config)</span></span>  
  
```  
Windows Registry Editor Version 5.00  
  
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework]  
"MDA"="1"  
```  
  
 <span data-ttu-id="74ad0-184">컴퓨터가 64비트 운영 체제에서 32비트 응용 프로그램을 실행 중인 경우 MDA 키는 다음과 같이 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-184">If the computer is running a 32-bit application on a 64-bit operating system, then the MDA key should be set like the following:</span></span>  
  
```  
      Windows Registry Editor Version 5.00   
  
[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework]  
"MDA"="1"  
```  
  
 <span data-ttu-id="74ad0-185">자세한 내용은 [응용 프로그램별 구성 설정을 사용하여 MDA 사용 및 사용 안 함](#appConfig)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="74ad0-185">See [Enabling and Disabling MDAs by Using Application-Specific Configuration Settings](#appConfig) for more information.</span></span> <span data-ttu-id="74ad0-186">레지스트리 설정은 COMPLUS_MDA 환경 변수로 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-186">The registry setting can be overridden by the COMPLUS_MDA environment variable.</span></span> <span data-ttu-id="74ad0-187">자세한 내용은 [환경 변수를 사용하여 MDA 사용 및 사용 안 함](#envVariable)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="74ad0-187">See [Enabling and Disabling MDAs by Using an Environment Variable](#envVariable) for more information.</span></span>  
  
 <span data-ttu-id="74ad0-188">MDA를 사용하지 않도록 설정하려면 Windows 레지스트리 편집기를 사용하여 MDA 하위 키를 0(영)으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-188">To disable MDAs, set the MDA subkey to 0 (zero) using the Windows Registry Editor.</span></span>  
  
 <span data-ttu-id="74ad0-189">기본적으로 일부 MDA는 디버거에 연결된 응용 프로그램을 실행하면 레지스트리 키를 추가하지 않더라도 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-189">By default, some MDAs are enabled when you run an application that is attached to a debugger, even without adding the registry key.</span></span> <span data-ttu-id="74ad0-190">이러한 도우미의 예는 [pInvokeStackImbalance](../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md) 및 [invalidApartmentStateChange](../../../docs/framework/debug-trace-profile/invalidapartmentstatechange-mda.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-190">Examples of such assistants are [pInvokeStackImbalance](../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md) and [invalidApartmentStateChange](../../../docs/framework/debug-trace-profile/invalidapartmentstatechange-mda.md).</span></span> <span data-ttu-id="74ad0-191">이 섹션의 앞부분에 설명되어 있는 것처럼 MDADisable.reg 파일을 실행하여 이러한 도우미를 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-191">You can disable these assistants by running the MDADisable.reg file as described earlier in this section.</span></span>  
  
<a name="envVariable"></a>   
### <a name="enabling-and-disabling-mdas-by-using-an-environment-variable"></a><span data-ttu-id="74ad0-192">환경 변수를 사용하여 MDA 사용 및 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="74ad0-192">Enabling and Disabling MDAs by Using an Environment Variable</span></span>  
 <span data-ttu-id="74ad0-193">MDA 활성화는 레지스트리 키를 재정의하는 환경 변수 COMPLUS_MDA에 의해서도 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-193">MDA activation can also controlled by the environment variable COMPLUS_MDA, which overrides the registry key.</span></span> <span data-ttu-id="74ad0-194">COMPLUS_MDA 문자열은 대/소문자를 구분하지 않으며, 세미콜론으로 구분된 MDA 이름 또는 기타 특수 제어 문자열의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-194">The COMPLUS_MDA string is a case-insensitive, semicolon-delimited list of MDA names or other special control strings.</span></span> <span data-ttu-id="74ad0-195">관리되는 디버거 또는 관리되지 않는 디버거에서 시작하면 기본적으로 MDA 집합이 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-195">Starting under a managed or unmanaged debugger enables a set of MDAs by default.</span></span> <span data-ttu-id="74ad0-196">이러한 설정은 디버거에서 기본적으로 사용하도록 설정된, 세미콜론으로 구분된 MDA 목록을 환경 변수 또는 레지스트리 키 값에 추가하여 암시적으로 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-196">This is done by implicitly prepending the semicolon-delimited list of MDAs enabled by default under debuggers to the value of the environment variable or registry key.</span></span> <span data-ttu-id="74ad0-197">특수 제어 문자열은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-197">The special control strings are the following:</span></span>  
  
-   <span data-ttu-id="74ad0-198">`0` - 모든 MDA를 비활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-198">`0` - Deactivates all MDAs.</span></span>  
  
-   <span data-ttu-id="74ad0-199">`1` - *ApplicationName*.mda.config에서 MDA 설정을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-199">`1` - Reads MDA settings from *ApplicationName*.mda.config.</span></span>  
  
-   <span data-ttu-id="74ad0-200">`managedDebugger` - 관리되는 실행 파일이 디버거에서 시작되면 암시적으로 활성화되는 모든 MDA를 명시적으로 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-200">`managedDebugger` - Explicitly activates all MDAs that are implicitly activated when a managed executable is started under a debugger.</span></span>  
  
-   <span data-ttu-id="74ad0-201">`unmanagedDebugger` - 관리되지 않는 실행 파일이 디버거에서 시작되면 암시적으로 활성화되는 모든 MDA를 명시적으로 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-201">`unmanagedDebugger` - Explicitly activates all MDAs that are implicitly activated when an unmanaged executable is started under a debugger.</span></span>  
  
 <span data-ttu-id="74ad0-202">충돌하는 설정이 있는 경우 최신 설정이 이전 설정을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-202">If there are conflicting settings, the most recent settings override previous settings:</span></span>  
  
-   <span data-ttu-id="74ad0-203">`COMPLUS_MDA=0`은 디버거에서 암시적으로 사용하도록 설정된 MDA를 포함하여 모든 MDA를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-203">`COMPLUS_MDA=0` disables all MDAs, including those implicitly enabled under a debugger.</span></span>  
  
-   <span data-ttu-id="74ad0-204">`COMPLUS_MDA=gcUnmanagedToManaged`는 디버거에서 암시적으로 사용하도록 설정된 모든 MDA 외에 `gcUnmanagedToManaged`를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-204">`COMPLUS_MDA=gcUnmanagedToManaged` enables `gcUnmanagedToManaged` in addition to any MDAs that are implicitly enabled under a debugger.</span></span>  
  
-   <span data-ttu-id="74ad0-205">`COMPLUS_MDA=0;gcUnmanagedToManaged`는 `gcUnmanagedToManaged`를 사용하도록 설정하지만 디버거에서 달리 암시적으로 사용하도록 설정되지 않는 MDA를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-205">`COMPLUS_MDA=0;gcUnmanagedToManaged` enables `gcUnmanagedToManaged` but disables MDAs that would otherwise be implicitly enabled under a debugger.</span></span>  
  
<a name="appConfig"></a>   
### <a name="enabling-and-disabling-mdas-by-using-application-specific-configuration-settings"></a><span data-ttu-id="74ad0-206">응용 프로그램별 구성 설정을 사용하여 MDA 사용 및 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="74ad0-206">Enabling and Disabling MDAs by Using Application-Specific Configuration Settings</span></span>  
 <span data-ttu-id="74ad0-207">응용 프로그램의 MDA 구성 파일에서 일부 도우미를 개별적으로 사용하도록 설정, 사용하지 않도록 설정 및 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-207">You can enable, disable, and configure some assistants individually in the MDA configuration file for the application.</span></span> <span data-ttu-id="74ad0-208">MDA를 구성하는 데 응용 프로그램 구성 파일을 사용할 수 있으려면 MDA 레지스트리 키 또는 COMPLUS_MDA 환경 변수를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-208">To enable the use of an application configuration file for configuring MDAs, either the MDA registry key or the COMPLUS_MDA environment variable must be set.</span></span> <span data-ttu-id="74ad0-209">응용 프로그램 구성 파일은 일반적으로 응용 프로그램 실행 파일(.exe)과 동일한 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-209">The application configuration file is typically located in the same directory as the application's executable (.exe) file.</span></span> <span data-ttu-id="74ad0-210">파일 이름은 *ApplicationName*.mda.config 형식을 사용합니다(예: notepad.exe.mda.config). 응용 프로그램 구성 파일에서 사용하도록 설정된 도우미는 특별히 해당 도우미의 동작을 제어하도록 디자인된 특성 또는 요소를 포함할 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-210">The file name takes the form *ApplicationName*.mda.config; for example, notepad.exe.mda.config. Assistants that are enabled in the application configuration file may have attributes or elements specifically designed to control that assistant's behavior.</span></span> <span data-ttu-id="74ad0-211">다음 예제에서는 [마샬링](../../../docs/framework/debug-trace-profile/marshaling-mda.md)을 사용하도록 설정하고 구성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-211">The following example shows how to enable and configure the [marshaling](../../../docs/framework/debug-trace-profile/marshaling-mda.md).</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <marshaling>  
      <methodFilter>  
        <match name="*"/>  
      </methodFilter>  
      <fieldFilter>  
        <match name="*"/>  
      </fieldFilter>  
    </marshaling>  
  </assistants>  
</mdaConfig>  
```  
  
 <span data-ttu-id="74ad0-212">`Marshaling` MDA는 응용 프로그램에서 각 관리되는-관리되지 않는 변환의 관리되지 않는 형식으로 마샬링되는 관리되는 형식에 대한 정보를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-212">The `Marshaling` MDA emits information about the managed type that is being marshaled to an unmanaged type for each managed-to-unmanaged transition in the application.</span></span> <span data-ttu-id="74ad0-213">또한 `Marshaling` MDA는 각각 `<methodFilter>` 및 `<fieldFilter>` 자식 요소에 제공된 메서드 및 구조 필드의 이름을 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-213">The `Marshaling` MDA can also filter the names of the method and structure fields supplied in the `<methodFilter>` and `<fieldFilter>` child elements, respectively.</span></span>  
  
 <span data-ttu-id="74ad0-214">다음 예제에서는 해당 기본 설정을 사용하여 여러 MDA를 사용하도록 설정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-214">The following example shows how to enable multiple MDAs by using their default settings.</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <illegalPrepareConstrainedRegion />  
    <invalidCERCall />  
    <openGenericCERCall />  
    <virtualCERCall />  
  </assistants>  
</mdaConfig>  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="74ad0-215">구성 파일에 둘 이상의 도우미를 지정할 때는 사전순으로 나열해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-215">When you specify more than one assistant in a configuration file, you must list them in alphabetical order.</span></span> <span data-ttu-id="74ad0-216">예를 들어, `virtualCERCall` MDA와 `invalidCERCall` MDA를 둘 다 사용하도록 설정하려면 `<invalidCERCall />` 항목 앞에 `<virtualCERCall />` 항목을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-216">For example, if you want to enable both the `virtualCERCall` and the `invalidCERCall` MDAs, you must add the `<invalidCERCall />` entry before the `<virtualCERCall />` entry.</span></span> <span data-ttu-id="74ad0-217">항목이 사전순이 아니면 처리되지 않은 잘못된 구성 파일 예외 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-217">If the entries are not in alphabetical order, an unhandled invalid configuration file exception message is displayed.</span></span>  
  
### <a name="mda-output"></a><span data-ttu-id="74ad0-218">MDA 출력</span><span class="sxs-lookup"><span data-stu-id="74ad0-218">MDA Output</span></span>  
 <span data-ttu-id="74ad0-219">MDA 출력은 `pInvokeStackImbalance` MDA의 출력을 보여 주는 다음 예제와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="74ad0-219">MDA output is similar to the following example, which shows the output from the `pInvokeStackImbalance` MDA.</span></span>  
  
 `A call to PInvoke function 'MDATest!MDATest.Program::StdCall' has unbalanced the stack. This is likely because the managed PInvoke signature does not match the unmanaged target signature. Check that the calling convention and parameters of the PInvoke signature match the target unmanaged signature.`  
  
## <a name="see-also"></a><span data-ttu-id="74ad0-220">참고 항목</span><span class="sxs-lookup"><span data-stu-id="74ad0-220">See Also</span></span>  
 [<span data-ttu-id="74ad0-221">디버깅, 추적 및 프로파일링</span><span class="sxs-lookup"><span data-stu-id="74ad0-221">Debugging, Tracing, and Profiling</span></span>](../../../docs/framework/debug-trace-profile/index.md)
