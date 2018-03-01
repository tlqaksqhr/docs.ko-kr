---
title: "ICorDebugController::SetAllThreadsDebugState 메서드"
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
- ICorDebugController.SetAllThreadsDebugState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::SetAllThreadsDebugState
helpviewer_keywords:
- SetAllThreadsDebugState method [.NET Framework debugging]
- ICorDebugController::SetAllThreadsDebugState method [.NET Framework debugging]
ms.assetid: bdda4bd7-4743-4d58-a22b-8067e967db95
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b8c9904c3c86e405660dcafe9963fe05049524b4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcontrollersetallthreadsdebugstate-method"></a><span data-ttu-id="04b02-102">ICorDebugController::SetAllThreadsDebugState 메서드</span><span class="sxs-lookup"><span data-stu-id="04b02-102">ICorDebugController::SetAllThreadsDebugState Method</span></span>
<span data-ttu-id="04b02-103">프로세스에서 모든 관리 되는 스레드의 디버그 상태를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="04b02-103">Sets the debug state of all managed threads in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04b02-104">구문</span><span class="sxs-lookup"><span data-stu-id="04b02-104">Syntax</span></span>  
  
```  
HRESULT SetAllThreadsDebugState (  
    [in] CorDebugThreadState  state,  
    [in] ICorDebugThread      *pExceptThisThread  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="04b02-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="04b02-105">Parameters</span></span>  
 `state`  
 <span data-ttu-id="04b02-106">[in] 디버깅을 위한 스레드 상태를 지정 하는 "CorDebugThreadState" 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="04b02-106">[in] A value of the "CorDebugThreadState" enumeration that specifies the state of the thread for debugging.</span></span>  
  
 `pExceptThisThread`  
 <span data-ttu-id="04b02-107">[in] 디버그 상태 설정에서 제외 해야 하는 스레드를 나타내는 "ICorDebugThread" 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="04b02-107">[in] A pointer to an "ICorDebugThread" object that represents a thread to be exempted from the debug state setting.</span></span> <span data-ttu-id="04b02-108">이 값이 null 이면 없는 스레드는 제외 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04b02-108">If this value is null, no thread is exempted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="04b02-109">설명</span><span class="sxs-lookup"><span data-stu-id="04b02-109">Remarks</span></span>  
 <span data-ttu-id="04b02-110">`SetAllThreadsDebugState` 메서드를 통해 표시 되지 않는 스레드 영향을 줄 수 [EnumerateThreads 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-enumeratethreads-method.md),으로 일시 중단 된 스레드 등의 `SetAllThreadsDebugState` 메서드도 다시 시작 해야 합니다는 `SetAllThreadsDebugState` 메서드.</span><span class="sxs-lookup"><span data-stu-id="04b02-110">The `SetAllThreadsDebugState` method may affect threads that are not visible via [EnumerateThreads Method](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-enumeratethreads-method.md), so threads that were suspended with the `SetAllThreadsDebugState` method will need to be resumed with the `SetAllThreadsDebugState` method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04b02-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="04b02-111">Requirements</span></span>  
 <span data-ttu-id="04b02-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="04b02-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04b02-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="04b02-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="04b02-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="04b02-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="04b02-115">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04b02-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04b02-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="04b02-116">See Also</span></span>  
 
