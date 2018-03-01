---
title: "ICorDebugFrame::CreateStepper 메서드"
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
- ICorDebugFrame.CreateStepper
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::CreateStepper
helpviewer_keywords:
- ICorDebugFrame::CreateStepper method [.NET Framework debugging]
- CreateStepper method, ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 689e7f28-20c1-4d5c-9baa-17441cd63a88
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 93f6741a030e72406fb8099c6373896d14cb9332
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugframecreatestepper-method"></a><span data-ttu-id="e415e-102">ICorDebugFrame::CreateStepper 메서드</span><span class="sxs-lookup"><span data-stu-id="e415e-102">ICorDebugFrame::CreateStepper Method</span></span>
<span data-ttu-id="e415e-103">디버거에서이 ICorDebugFrame 기준으로 단계별 실행 작업을 수행할 수 있도록 스텝을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e415e-103">Gets a stepper that allows the debugger to perform stepping operations relative to this ICorDebugFrame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e415e-104">구문</span><span class="sxs-lookup"><span data-stu-id="e415e-104">Syntax</span></span>  
  
```  
HRESULT CreateStepper (  
    [out] ICorDebugStepper   **ppStepper  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e415e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e415e-105">Parameters</span></span>  
 `ppStepper`  
 <span data-ttu-id="e415e-106">[out] 디버거는 현재 프레임을 기준으로 단계별 실행 작업을 수행할 수 있도록 ICorDebugStepper 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e415e-106">[out] A pointer to the address of an ICorDebugStepper object that allows the debugger to perform stepping operations relative to the current frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e415e-107">설명</span><span class="sxs-lookup"><span data-stu-id="e415e-107">Remarks</span></span>  
 <span data-ttu-id="e415e-108">프레임 활성 상태 이면 해당 단계가 완료 되기 전에 프레임으로 돌아가려면 스텝 퍼 개체 일반적으로 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="e415e-108">If the frame is not active, the stepper object will typically have to return to the frame before the step is completed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e415e-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e415e-109">Requirements</span></span>  
 <span data-ttu-id="e415e-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e415e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e415e-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e415e-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e415e-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e415e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e415e-113">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e415e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
