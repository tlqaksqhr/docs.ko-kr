---
title: ICorDebugController::HasQueuedCallbacks 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugController.HasQueuedCallbacks
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::HasQueuedCallbacks
helpviewer_keywords:
- HasQueuedCallbacks method [.NET Framework debugging]
- ICorDebugController::HasQueuedCallbacks method [.NET Framework debugging]
ms.assetid: 0d6a1cd9-370b-4462-adbf-e3980e897ea7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eba265b727d00690ab77c6ae831e954d59df7c50
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33411612"
---
# <a name="icordebugcontrollerhasqueuedcallbacks-method"></a><span data-ttu-id="a9d35-102">ICorDebugController::HasQueuedCallbacks 메서드</span><span class="sxs-lookup"><span data-stu-id="a9d35-102">ICorDebugController::HasQueuedCallbacks Method</span></span>
<span data-ttu-id="a9d35-103">지정 된 스레드에 대 한 모든 관리 되는 콜백이 현재 대기 중인 있는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a9d35-103">Gets a value that indicates whether any managed callbacks are currently queued for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9d35-104">구문</span><span class="sxs-lookup"><span data-stu-id="a9d35-104">Syntax</span></span>  
  
```  
HRESULT HasQueuedCallbacks (  
    [in] ICorDebugThread *pThread,  
    [out] BOOL           *pbQueued  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a9d35-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a9d35-105">Parameters</span></span>  
 `pThread`  
 <span data-ttu-id="a9d35-106">[in] 스레드를 나타내는 "ICorDebugThread" 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a9d35-106">[in] A pointer to an "ICorDebugThread" object that represents the thread.</span></span>  
  
 `pbQueued`  
 <span data-ttu-id="a9d35-107">[out] 값에 대 한 포인터 `true` 관리 되는 모든 콜백이 고, 그렇지 않으면 지정 된 스레드에 대 한 큐에 대기 중인 현재 경우 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="a9d35-107">[out] A pointer to a value that is `true` if any managed callbacks are currently queued for the specified thread; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="a9d35-108">에 대 한 null을 지정 하는 경우는 `pThread` 매개 변수를 `HasQueuedCallbacks` 돌아갑니다 `true` 현재 스레드에 대 한 관리 되는 콜백이 대기 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9d35-108">If null is specified for the `pThread` parameter, `HasQueuedCallbacks` will return `true` if there are currently managed callbacks queued for any thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a9d35-109">설명</span><span class="sxs-lookup"><span data-stu-id="a9d35-109">Remarks</span></span>  
 <span data-ttu-id="a9d35-110">콜백이 됩니다 발송 될 때마다 한 번에 [icordebugcontroller:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9d35-110">Callbacks will be dispatched one at a time, each time [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) is called.</span></span> <span data-ttu-id="a9d35-111">디버거는 동시에 발생 하는 여러 디버깅 이벤트를 보고 하려는 경우이 플래그를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9d35-111">The debugger can check this flag if it wants to report multiple debugging events that occur simultaneously.</span></span>  
  
 <span data-ttu-id="a9d35-112">디버깅 이벤트 큐에 대기 하는 경우 이러한 이미 발생 한, 디버거는 디버기에 상태의 내기 위해서는 전체 큐를 제거 해야 하므로 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9d35-112">When debugging events are queued, they have already occurred, so the debugger must drain the entire queue to be sure of the state of the debuggee.</span></span> <span data-ttu-id="a9d35-113">(호출 `ICorDebugController::Continue` 큐를 드레이닝 하도록 합니다.) 예를 들어, 큐 스레드에서 두 디버깅 이벤트를 포함 하는 경우 *X*, 디버거 스레드를 일시 중단 및 *X* 첫 번째 디버깅 이벤트 및 다음 호출 후 `ICorDebugController::Continue`에 대 한 두 번째 디버깅 이벤트 스레드 *X* 는 스레드가 일시 중단 된 더라도 디스패치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9d35-113">(Call `ICorDebugController::Continue` to drain the queue.) For example, if the queue contains two debugging events on thread *X*, and the debugger suspends thread *X* after the first debugging event and then calls `ICorDebugController::Continue`, the second debugging event for thread *X* will be dispatched although the thread has been suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9d35-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a9d35-114">Requirements</span></span>  
 <span data-ttu-id="a9d35-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a9d35-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9d35-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a9d35-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a9d35-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a9d35-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a9d35-118">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9d35-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9d35-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a9d35-119">See Also</span></span>  
 
