---
title: "ICorDebugController::Continue 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugController.Continue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugController::Continue
helpviewer_keywords:
- Continue method [.NET Framework debugging]
- ICorDebugController::Continue method [.NET Framework debugging]
ms.assetid: 8684cd06-ad3e-48ef-832e-15320e1f43a2
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 93fc138b8610d252be5c3ca3821bb1d41c5ac6ca
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugcontrollercontinue-method"></a><span data-ttu-id="3c427-102">ICorDebugController::Continue 메서드</span><span class="sxs-lookup"><span data-stu-id="3c427-102">ICorDebugController::Continue Method</span></span>
<span data-ttu-id="3c427-103">관리 되는 스레드를 호출한 후 실행을 계속 [Stop 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3c427-103">Resumes execution of managed threads after a call to [Stop Method](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c427-104">구문</span><span class="sxs-lookup"><span data-stu-id="3c427-104">Syntax</span></span>  
  
```  
HRESULT Continue (  
    [in] BOOL fIsOutOfBand  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3c427-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3c427-105">Parameters</span></span>  
 `fIsOutOfBand`  
 <span data-ttu-id="3c427-106">[in] 로 설정 `true` 밴드의 범위를 벗어난 이벤트;에서 계속 실행 하는 경우 이렇게 하지 않으면으로 설정 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="3c427-106">[in] Set to `true` if continuing from an out-of-band event; otherwise, set to `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3c427-107">설명</span><span class="sxs-lookup"><span data-stu-id="3c427-107">Remarks</span></span>  
 <span data-ttu-id="3c427-108">`Continue`호출한 후 프로세스를 계속는 `ICorDebugController::Stop` 메서드.</span><span class="sxs-lookup"><span data-stu-id="3c427-108">`Continue` continues the process after a call to the `ICorDebugController::Stop` method.</span></span>  
  
 <span data-ttu-id="3c427-109">혼합 모드 디버깅을 수행할 때 호출 하지 않으면 `Continue` Win32에 이벤트 스레드 대역의 이벤트에서 계속 실행 하는 경우가 아니면 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c427-109">When doing mixed-mode debugging, do not call `Continue` on the Win32 event thread unless you are continuing from an out-of-band event.</span></span>  
  
 <span data-ttu-id="3c427-110">*대역 이벤트* 는 관리 되는 이벤트 또는 일반 관리 되지 않는 이벤트는 디버거 프로세스의 관리 되는 상태와의 상호 작용을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c427-110">An *in-band event* is either a managed event or a normal unmanaged event during which the debugger supports interaction with the managed state of the process.</span></span> <span data-ttu-id="3c427-111">디버거 수신 하는 경우에 [icordebugunmanagedcallback:: Debugevent](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-debugevent-method.md) 사용 콜백을 해당 `fOutOfBand` 매개 변수 설정 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="3c427-111">In this case, the debugger receives the [ICorDebugUnmanagedCallback::DebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-debugevent-method.md) callback with its `fOutOfBand` parameter set to `false`.</span></span>  
  
 <span data-ttu-id="3c427-112">*밴드의 범위를 벗어난 이벤트* 는 프로세스의 관리 되는 상태와의 상호 작용 수 없는 이벤트로 인해 프로세스를 중지 하는 동안 관리 되지 않는 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="3c427-112">An *out-of-band event* is an unmanaged event during which interaction with the managed state of the process is impossible while the process is stopped due to the event.</span></span> <span data-ttu-id="3c427-113">디버거 수신 하는 경우에 `ICorDebugUnmanagedCallback::DebugEvent` 사용 콜백을 해당 `fOutOfBand` 매개 변수 설정 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="3c427-113">In this case, the debugger receives the `ICorDebugUnmanagedCallback::DebugEvent` callback with its `fOutOfBand` parameter set to `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c427-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3c427-114">Requirements</span></span>  
 <span data-ttu-id="3c427-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3c427-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c427-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3c427-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3c427-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3c427-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3c427-118">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c427-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c427-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3c427-119">See Also</span></span>  
 
