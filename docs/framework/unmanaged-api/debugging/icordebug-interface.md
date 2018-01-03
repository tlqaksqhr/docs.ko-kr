---
title: "ICorDebug 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebug
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebug
helpviewer_keywords: ICorDebug interface [.NET Framework debugging]
ms.assetid: 33f431d7-ab1a-494d-8af2-20ab15aba194
topic_type: apiref
caps.latest.revision: "20"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0ed0b3a8b42157f6a4fcbc6b4a05a416da736147
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebug-interface"></a><span data-ttu-id="41438-102">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="41438-102">ICorDebug Interface</span></span>
<span data-ttu-id="41438-103">공용 언어 런타임 (CLR) 환경에서 응용 프로그램을 디버깅 하는 데 사용할 수 있는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="41438-103">Provides methods that allow developers to debug applications in the common language runtime (CLR) environment.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="41438-104">비 x86 플랫폼 (예: IA64, AMD64) 또는 Windows 95, Windows 98 또는 Windows ME에서 (관리 / 네이티브 코드) 혼합 모드 디버깅이 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="41438-104">Mixed-mode (managed and native code) debugging is not supported on Windows 95, Windows 98, or Windows ME, or on non-x86 platforms (such as IA64 and AMD64).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="41438-105">메서드</span><span class="sxs-lookup"><span data-stu-id="41438-105">Methods</span></span>  
  
|<span data-ttu-id="41438-106">메서드</span><span class="sxs-lookup"><span data-stu-id="41438-106">Method</span></span>|<span data-ttu-id="41438-107">설명</span><span class="sxs-lookup"><span data-stu-id="41438-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="41438-108">CanLaunchOrAttach 메서드</span><span class="sxs-lookup"><span data-stu-id="41438-108">CanLaunchOrAttach Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-canlaunchorattach-method.md)|<span data-ttu-id="41438-109">새 프로세스를 시작 하거나 지정된 된 프로세스에 연결 하 여 현재 컴퓨터 및 런타임 구성의 컨텍스트 내에서 가능한 지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="41438-109">Determines whether launching a new process or attaching to the given process is possible within the context of the current machine and runtime configuration.</span></span>|  
|[<span data-ttu-id="41438-110">CreateProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="41438-110">CreateProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md)|<span data-ttu-id="41438-111">프로세스와 디버거 제어 기본 스레드를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="41438-111">Launches a process and its primary thread under the control of the debugger.</span></span>|  
|[<span data-ttu-id="41438-112">DebugActiveProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="41438-112">DebugActiveProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-debugactiveprocess-method.md)|<span data-ttu-id="41438-113">기존 프로세스에 디버거를 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="41438-113">Attaches the debugger to an existing process.</span></span>|  
|[<span data-ttu-id="41438-114">EnumerateProcesses 메서드</span><span class="sxs-lookup"><span data-stu-id="41438-114">EnumerateProcesses Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-enumerateprocesses-method.md)|<span data-ttu-id="41438-115">디버깅 중인 프로세스에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="41438-115">Gets an enumerator for the processes that are being debugged.</span></span>|  
|[<span data-ttu-id="41438-116">GetProcess 메서드</span><span class="sxs-lookup"><span data-stu-id="41438-116">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-getprocess-method.md)|<span data-ttu-id="41438-117">"ICorDebugProcess" 개체에 지정 된 프로세스 id를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="41438-117">Returns the "ICorDebugProcess" object with the given process ID.</span></span>|  
|[<span data-ttu-id="41438-118">Initialize 메서드</span><span class="sxs-lookup"><span data-stu-id="41438-118">Initialize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-initialize-method.md)|<span data-ttu-id="41438-119">초기화는 `ICorDebug` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="41438-119">Initializes the `ICorDebug` object.</span></span>|  
|[<span data-ttu-id="41438-120">SetManagedHandler 메서드</span><span class="sxs-lookup"><span data-stu-id="41438-120">SetManagedHandler Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-setmanagedhandler-method.md)|<span data-ttu-id="41438-121">관리 되는 이벤트에 대 한 이벤트 처리기 개체를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="41438-121">Specifies the event handler object for managed events.</span></span>|  
|[<span data-ttu-id="41438-122">SetUnmanagedHandler 메서드</span><span class="sxs-lookup"><span data-stu-id="41438-122">SetUnmanagedHandler Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-setunmanagedhandler-method.md)|<span data-ttu-id="41438-123">관리 되지 않는 이벤트에 대 한 이벤트 처리기 개체를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="41438-123">Specifies the event handler object for unmanaged events.</span></span>|  
|[<span data-ttu-id="41438-124">Terminate 메서드</span><span class="sxs-lookup"><span data-stu-id="41438-124">Terminate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-terminate-method.md)|<span data-ttu-id="41438-125">종료는 `ICorDebug` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="41438-125">Terminates the `ICorDebug` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="41438-126">설명</span><span class="sxs-lookup"><span data-stu-id="41438-126">Remarks</span></span>  
 <span data-ttu-id="41438-127">`ICorDebug`디버거 프로세스에 대 한 이벤트 처리 루프를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="41438-127">`ICorDebug` represents an event processing loop for a debugger process.</span></span> <span data-ttu-id="41438-128">에 대 한 디버거 기다려야는 [icordebugmanagedcallback:: Exitprocess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) 이 인터페이스를 릴리스하기 전에 디버깅 중인 모든 프로세스에서 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="41438-128">The debugger must wait for the [ICorDebugManagedCallback::ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) callback from all processes being debugged before releasing this interface.</span></span>  
  
 <span data-ttu-id="41438-129">`ICorDebug` 개체는 추가 관리 되는 디버깅을 제어 하는 초기 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="41438-129">The `ICorDebug` object is the initial object to control all further managed debugging.</span></span> <span data-ttu-id="41438-130">이 개체를.NET Framework 버전 1.0 및 1.1에서는 `CoClass` COM에서 만든 개체</span><span class="sxs-lookup"><span data-stu-id="41438-130">In the .NET Framework versions 1.0 and 1.1, this object was a `CoClass` object created from COM.</span></span> <span data-ttu-id="41438-131">.NET Framework 버전 2.0에서에서이 개체는 더 이상는 `CoClass` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="41438-131">In the .NET Framework version 2.0, this object is no longer a `CoClass` object.</span></span> <span data-ttu-id="41438-132">여 생성 되어야 합니다는 [CreateDebuggingInterfaceFromVersion](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md) 버전 인식 하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="41438-132">It must be created by the [CreateDebuggingInterfaceFromVersion](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md) function, which is more version-aware.</span></span> <span data-ttu-id="41438-133">특정 구현을 가져올 클라이언트를 사용 하는이 새로운 만들기 함수 `ICorDebug`도 디버깅 API의 특정 버전을 에뮬레이트하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="41438-133">This new creation function enables clients to get a specific implementation of `ICorDebug`, which also emulates a specific version of the debugging API.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="41438-134">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="41438-134">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41438-135">요구 사항</span><span class="sxs-lookup"><span data-stu-id="41438-135">Requirements</span></span>  
 <span data-ttu-id="41438-136">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="41438-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41438-137">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="41438-137">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="41438-138">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="41438-138">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="41438-139">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41438-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41438-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="41438-140">See Also</span></span>  
 [<span data-ttu-id="41438-141">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="41438-141">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
