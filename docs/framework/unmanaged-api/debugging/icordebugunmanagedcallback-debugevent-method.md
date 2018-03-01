---
title: "ICorDebugUnmanagedCallback::DebugEvent 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugUnmanagedCallback.DebugEvent
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugUnmanagedCallback::DebugEvent
helpviewer_keywords:
- DebugEvent method [.NET Framework debugging]
- ICorDebugUnmanagedCallback::DebugEvent method [.NET Framework debugging]
ms.assetid: be9cab04-65ec-44d5-a39a-f90709fdd043
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 49c3386fcda0bc731935ec9db7d029d0e619ef14
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugunmanagedcallbackdebugevent-method"></a><span data-ttu-id="69029-102">ICorDebugUnmanagedCallback::DebugEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="69029-102">ICorDebugUnmanagedCallback::DebugEvent Method</span></span>
<span data-ttu-id="69029-103">네이티브 이벤트가 발생 했음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="69029-103">Notifies the debugger that a native event has been fired.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69029-104">구문</span><span class="sxs-lookup"><span data-stu-id="69029-104">Syntax</span></span>  
  
```  
HRESULT DebugEvent (  
    [in] LPDEBUG_EVENT  pDebugEvent,  
    [in] BOOL           fOutOfBand  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="69029-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="69029-105">Parameters</span></span>  
 `pDebugEvent`  
 <span data-ttu-id="69029-106">[in] 네이티브 이벤트에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="69029-106">[in] A pointer to the native event.</span></span>  
  
 `fOutOfBand`  
 <span data-ttu-id="69029-107">[in] `true`불가능 한 경우 관리 되는 프로세스 상태와 상호 작용 디버거 호출할 때까지 관리 되지 않는 이벤트가 발생 한 후, [icordebugcontroller:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md), 그렇지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="69029-107">[in] `true`, if interaction with the managed process state is impossible after an unmanaged event occurs, until the debugger calls [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md); otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="69029-108">설명</span><span class="sxs-lookup"><span data-stu-id="69029-108">Remarks</span></span>  
 <span data-ttu-id="69029-109">디버깅 중인 스레드의 Win32 스레드 이면 디버깅 인터페이스는 Win32의 모든 멤버를 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="69029-109">If the thread being debugged is a Win32 thread, do not use any members of the Win32 debugging interface.</span></span> <span data-ttu-id="69029-110">호출할 수 있습니다 `ICorDebugController::Continue` 밴드의 범위를 벗어난 이벤트 지 나 계속 하는 경우에 한 Win32 스레드에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="69029-110">You can call `ICorDebugController::Continue` only on a Win32 thread and only when continuing past an out-of-band event.</span></span>  
  
 <span data-ttu-id="69029-111">`DebugEvent` 콜백 콜백에 대 한 표준 규칙을 따르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="69029-111">The `DebugEvent` callback does not follow the standard rules for callbacks.</span></span> <span data-ttu-id="69029-112">호출 하는 경우 `DebugEvent`, 해당 프로세스에 원시 수, OS 디버그 상태를 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="69029-112">When you call `DebugEvent`, the process will be in the raw, OS-debug stopped state.</span></span> <span data-ttu-id="69029-113">프로세스 동기화 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="69029-113">The process will not be synchronized.</span></span> <span data-ttu-id="69029-114">중첩 된 다른 발생할 수 있습니다. 관리 코드에 대 한 정보에 대 한 요청을 충족 하기 위해 필요할 경우 동기화 된 상태로 자동 전환 됩니다 `DebugEvent` 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="69029-114">It will automatically enter the synchronized state when necessary to satisfy requests for information about managed code, which may result in other nested `DebugEvent` callbacks.</span></span>  
  
 <span data-ttu-id="69029-115">호출 [icordebugprocess:: Clearcurrentexception](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-clearcurrentexception-method.md) 과정을 계속 하기 전에 예외 이벤트를 무시 하는 프로세스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69029-115">Call [ICorDebugProcess::ClearCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-clearcurrentexception-method.md) on the process to ignore an exception event before continuing the process.</span></span> <span data-ttu-id="69029-116">이 메서드를 호출 계속 요청에서 DBG_EXCEPTION_NOT_HANDLED 대신 DBG_CONTINUE 보내고 대역의 중단점 및 단일 단계 예외를 자동으로 지워집니다.</span><span class="sxs-lookup"><span data-stu-id="69029-116">Calling this method sends DBG_CONTINUE instead of DBG_EXCEPTION_NOT_HANDLED on the continue request, and automatically clears out-of-band breakpoints and single-step exceptions.</span></span> <span data-ttu-id="69029-117">밴드의 범위를 벗어난 이벤트 및 디버깅 중인 응용 프로그램이 표시 중지 된 경우에 뛰어난 대역 이벤트 이미 있는 경우 언제 든 지 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69029-117">Out-of-band events can come at any time, even when the application being debugged appears stopped and when an outstanding in-band event already exists.</span></span>  
  
 <span data-ttu-id="69029-118">.NET Framework 버전 2.0에서에서 디버거 즉시 대역의 중단점 이벤트 지 나 계속 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="69029-118">In the .NET Framework version 2.0, the debugger should immediately continue past an out-of-band breakpoint event.</span></span> <span data-ttu-id="69029-119">디버거를 사용 해야 합니다는 [icordebugprocess2:: Setunmanagedbreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md) 및 [icordebugprocess2:: Clearunmanagedbreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-clearunmanagedbreakpoint-method.md) 메서드를 추가 하 고 중단점을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="69029-119">The debugger should be using the [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md) and [ICorDebugProcess2::ClearUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-clearunmanagedbreakpoint-method.md) methods to add and remove breakpoints.</span></span> <span data-ttu-id="69029-120">이러한 메서드는 자동으로 대역의 중단점을 통해 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="69029-120">These methods will skip over any out-of-band breakpoints automatically.</span></span> <span data-ttu-id="69029-121">따라서 밴드를만 중단점 디스패치되을 원시 중단점 이미 Win32 호출과 같은 명령 스트림의 해야 `DebugBreak` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="69029-121">Thus, the only out-of-band breakpoints that get dispatched should be raw breakpoints that are already in the instruction stream, such as a call to the Win32 `DebugBreak` function.</span></span> <span data-ttu-id="69029-122">사용 하지 마십시오 `ICorDebugProcess::ClearCurrentException`, [icordebugprocess:: Getthreadcontext](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthreadcontext-method.md), [icordebugprocess:: Setthreadcontext](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-setthreadcontext-method.md), 또는 다른 어떤 멤버도 [디버깅 API](../../../../docs/framework/unmanaged-api/debugging/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="69029-122">Do not try to use `ICorDebugProcess::ClearCurrentException`, [ICorDebugProcess::GetThreadContext](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthreadcontext-method.md), [ICorDebugProcess::SetThreadContext](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-setthreadcontext-method.md), or any other member of the [debugging API](../../../../docs/framework/unmanaged-api/debugging/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69029-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="69029-123">Requirements</span></span>  
 <span data-ttu-id="69029-124">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="69029-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69029-125">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="69029-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="69029-126">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="69029-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="69029-127">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69029-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69029-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="69029-128">See Also</span></span>  
 [<span data-ttu-id="69029-129">ICorDebugUnmanagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="69029-129">ICorDebugUnmanagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md)
