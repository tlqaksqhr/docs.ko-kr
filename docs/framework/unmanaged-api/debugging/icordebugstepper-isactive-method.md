---
title: "ICorDebugStepper::IsActive 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStepper.IsActive
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStepper::IsActive
helpviewer_keywords:
- IsActive method, ICorDebugStepper interface [.NET Framework debugging]
- ICorDebugStepper::IsActive method [.NET Framework debugging]
ms.assetid: 8b35e7a9-b40e-40a9-8d8e-b82e823fc575
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dd919852d3e7c187dff7fc4304d0a1b42f5294e0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugstepperisactive-method"></a><span data-ttu-id="70718-102">ICorDebugStepper::IsActive 메서드</span><span class="sxs-lookup"><span data-stu-id="70718-102">ICorDebugStepper::IsActive Method</span></span>
<span data-ttu-id="70718-103">이 ICorDebugStepper이 현재 단계를 실행 하는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="70718-103">Gets a value that indicates whether this ICorDebugStepper is currently executing a step.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70718-104">구문</span><span class="sxs-lookup"><span data-stu-id="70718-104">Syntax</span></span>  
  
```  
HRESULT IsActive (  
    [out] BOOL   *pbActive  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="70718-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="70718-105">Parameters</span></span>  
 `pbActive`  
 <span data-ttu-id="70718-106">[out] 반환 `true` 스텝 퍼 단계; 현재 실행 중인 경우는 그렇지 않으면 반환 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="70718-106">[out] Returns `true` if the stepper is currently executing a step; otherwise, returns `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="70718-107">설명</span><span class="sxs-lookup"><span data-stu-id="70718-107">Remarks</span></span>  
 <span data-ttu-id="70718-108">모든 단계 작업 활성 상태로 유지 되는 디버거를 받을 때까지 한 [icordebugmanagedcallback:: Stepcomplete](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md) 스텝 퍼는 자동으로 비활성화를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="70718-108">Any step action remains active until the debugger receives a [ICorDebugManagedCallback::StepComplete](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md) call, which automatically deactivates the stepper.</span></span> <span data-ttu-id="70718-109">스텝 호출 하 여 중간 비활성화할 수도 있습니다 [icordebugstepper:: Deactivate](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-deactivate-method.md) 콜백 전에 조건에 도달 했습니다.</span><span class="sxs-lookup"><span data-stu-id="70718-109">A stepper may also be deactivated prematurely by calling [ICorDebugStepper::Deactivate](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-deactivate-method.md) before the callback condition is reached.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70718-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="70718-110">Requirements</span></span>  
 <span data-ttu-id="70718-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="70718-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70718-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="70718-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="70718-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="70718-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="70718-114">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70718-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
