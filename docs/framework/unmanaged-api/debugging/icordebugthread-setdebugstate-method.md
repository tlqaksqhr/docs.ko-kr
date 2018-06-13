---
title: ICorDebugThread::SetDebugState 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugThread.SetDebugState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::SetDebugState
helpviewer_keywords:
- ICorDebugThread::SetDebugState method [.NET Framework debugging]
- SetDebugState method [.NET Framework debugging]
ms.assetid: 6382bdf6-d488-4952-b653-cb09b6e1c6c2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ada120b9cb4100bfadff83d96e0226f911958bf7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420767"
---
# <a name="icordebugthreadsetdebugstate-method"></a><span data-ttu-id="a0058-102">ICorDebugThread::SetDebugState 메서드</span><span class="sxs-lookup"><span data-stu-id="a0058-102">ICorDebugThread::SetDebugState Method</span></span>
<span data-ttu-id="a0058-103">이 ICorDebugThread의 디버깅 상태를 설명 하는 플래그를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0058-103">Sets flags that describe the debugging state of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0058-104">구문</span><span class="sxs-lookup"><span data-stu-id="a0058-104">Syntax</span></span>  
  
```  
HRESULT SetDebugState (  
    [in] CorDebugThreadState state  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a0058-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a0058-105">Parameters</span></span>  
 `state`  
 <span data-ttu-id="a0058-106">[in] 이 스레드의 디버깅 상태를 지정 하는 CorDebugThreadState 열거형 값의 비트 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="a0058-106">[in] A bitwise combination of CorDebugThreadState enumeration values that specify the debugging state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a0058-107">설명</span><span class="sxs-lookup"><span data-stu-id="a0058-107">Remarks</span></span>  
 <span data-ttu-id="a0058-108">`SetDebugState` 스레드의 현재 디버그 상태를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a0058-108">`SetDebugState` sets the current debug state of the thread.</span></span> <span data-ttu-id="a0058-109">("현재 디버그 상태" 상태를 나타내는 디버그 프로세스가 계속 될 실제 현재 상태가 아니라 경우.) 이 일반적인 값은 THREAD_RUNNING입니다.</span><span class="sxs-lookup"><span data-stu-id="a0058-109">(The "current debug state" represents the debug state if the process were to be continued, not the actual current state.) The normal value for this is THREAD_RUNNING.</span></span> <span data-ttu-id="a0058-110">디버거에서 스레드 디버그 상태에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0058-110">Only the debugger can affect the debug state of a thread.</span></span> <span data-ttu-id="a0058-111">상태 디버깅 않는 마지막 across 계속 되 면 여러 통해 THREAD_SUSPENDed 계속 스레드를 유지 하려는 경우 한 번 설정 하 고 그 후 걱정 하지 않아도 항목에 대 한 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0058-111">Debug states do last across continues, so if you want to keep a thread THREAD_SUSPENDed over multiple continues, you can set it once and thereafter not have to worry about it.</span></span> <span data-ttu-id="a0058-112">스레드 일시 중단 하 고 프로세스를 다시 시작는 일반적으로 그럴 가능성은 있지만 교착 상태에 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0058-112">Suspending threads and resuming the process can cause deadlocks, though it's usually unlikely.</span></span> <span data-ttu-id="a0058-113">이 스레드 및 프로세스의 본래 특성 이며 디자인에 따라 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0058-113">This is an intrinsic quality of threads and processes and is by-design.</span></span> <span data-ttu-id="a0058-114">디버거 수 비동기적으로 해제 하 고 스레드는 교착 상태를 다시 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0058-114">A debugger can asynchronously break and resume the threads to break the deadlock.</span></span> <span data-ttu-id="a0058-115">스레드의 사용자 상태 USER_UNSAFE_POINT가 포함 된 경우 스레드는 GC (가비지 수집)를 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0058-115">If the thread's user state includes USER_UNSAFE_POINT, then the thread may block a garbage collection (GC).</span></span> <span data-ttu-id="a0058-116">즉, 일시 중지 된 스레드 확률이 훨씬 더 높은 교착 상태를 일으킵니다.</span><span class="sxs-lookup"><span data-stu-id="a0058-116">This means the suspended thread has a much higher chance of causing a deadlock.</span></span> <span data-ttu-id="a0058-117">디버그 이벤트 앱이 이미 큐에 영향을 주지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0058-117">This may not affect debug events already queued.</span></span> <span data-ttu-id="a0058-118">따라서 디버거 전체 이벤트 큐를 드레이닝 해야 (호출 하 여 [icordebugcontroller:: Hasqueuedcallbacks](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)) 중단 또는 스레드를 다시 시작 하기 전에.</span><span class="sxs-lookup"><span data-stu-id="a0058-118">Thus a debugger should drain the entire event queue (by calling [ICorDebugController::HasQueuedCallbacks](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)) before suspending or resuming threads.</span></span> <span data-ttu-id="a0058-119">다른 이벤트를 발생 것 이미 일시 중단 된 것으로 간주 된 스레드에서 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a0058-119">Else it may get events on a thread that it believes it has already suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0058-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a0058-120">Requirements</span></span>  
 <span data-ttu-id="a0058-121">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a0058-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0058-122">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a0058-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a0058-123">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a0058-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a0058-124">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0058-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
