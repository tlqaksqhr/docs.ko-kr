---
title: "ICorDebugManagedCallback::StepComplete 메서드"
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
- ICorDebugManagedCallback.StepComplete
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::StepComplete
helpviewer_keywords:
- StepComplete method [.NET Framework debugging]
- ICorDebugManagedCallback::StepComplete method [.NET Framework debugging]
ms.assetid: 5e1f2c47-81df-4530-826d-96489cd68719
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8e7a09216284593c79c0cda6f5283ea8250678af
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallbackstepcomplete-method"></a><span data-ttu-id="e2100-102">ICorDebugManagedCallback::StepComplete 메서드</span><span class="sxs-lookup"><span data-stu-id="e2100-102">ICorDebugManagedCallback::StepComplete Method</span></span>
<span data-ttu-id="e2100-103">단계가 완료 되었음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="e2100-103">Notifies the debugger that a step has completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2100-104">구문</span><span class="sxs-lookup"><span data-stu-id="e2100-104">Syntax</span></span>  
  
```  
HRESULT StepComplete (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugStepper    *pStepper,  
    [in] CorDebugStepReason   reason  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e2100-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e2100-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="e2100-106">[in] 단계가 완료 중인 스레드를 포함 하는 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e2100-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the thread in which the step has completed.</span></span>  
  
 `pThread`  
 <span data-ttu-id="e2100-107">[in] 스레드는 단계가 완료 되었음을 나타내는 ICorDebugThread 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e2100-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the step has completed.</span></span>  
  
 `pStepper`  
 <span data-ttu-id="e2100-108">[in] 코드 실행 하는 단계를 나타내는 ICorDebugStepper 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e2100-108">[in] A pointer to an ICorDebugStepper object that represents the step in code execution.</span></span>  
  
 `reason`  
 <span data-ttu-id="e2100-109">[in] 개별 단계의 결과 나타내는 CorDebugStepReason 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="e2100-109">[in] A value of the CorDebugStepReason enumeration that indicates the outcome of an individual step.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e2100-110">설명</span><span class="sxs-lookup"><span data-stu-id="e2100-110">Remarks</span></span>  
 <span data-ttu-id="e2100-111">스텝 퍼 단계별로 계속 필요한 경우 종료 된 디버깅 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2100-111">The stepper may be used to continue stepping if desired, unless the debugging is terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2100-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e2100-112">Requirements</span></span>  
 <span data-ttu-id="e2100-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e2100-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2100-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e2100-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e2100-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e2100-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e2100-116">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2100-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2100-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e2100-117">See Also</span></span>  
 [<span data-ttu-id="e2100-118">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e2100-118">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
