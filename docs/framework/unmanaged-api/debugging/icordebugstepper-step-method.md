---
title: "ICorDebugStepper::Step 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStepper.Step
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStepper::Step
helpviewer_keywords:
- Step method, ICorDebugStepper interface [.NET Framework debugging]
- ICorDebugStepper::Step method [.NET Framework debugging]
ms.assetid: 38c1940b-ada1-40ba-8295-4c0833744e1e
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f921725d6794f08530a537462208264ced1dc089
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugstepperstep-method"></a><span data-ttu-id="8528f-102">ICorDebugStepper::Step 메서드</span><span class="sxs-lookup"><span data-stu-id="8528f-102">ICorDebugStepper::Step Method</span></span>
<span data-ttu-id="8528f-103">한 단계씩 실행 하려면 필요에 따라 하 고 포함 스레드를 통해이 ICorDebugStepper로 인해 스레드 내에서 호출 된 함수를 통해 단일 단계를 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="8528f-103">Causes this ICorDebugStepper to single-step through its containing thread, and optionally, to continue single-stepping through functions that are called within the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8528f-104">구문</span><span class="sxs-lookup"><span data-stu-id="8528f-104">Syntax</span></span>  
  
```  
HRESULT Step (  
    [in] BOOL   bStepIn  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8528f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8528f-105">Parameters</span></span>  
 `bStepIn`  
 <span data-ttu-id="8528f-106">[in] 로 설정 `true` 스레드 내에서 호출 되는 함수를 한 단계씩에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8528f-106">[in] Set to `true` to step into a function that is called within the thread.</span></span> <span data-ttu-id="8528f-107">로 설정 `false` 함수를 통해 단계로 합니다.</span><span class="sxs-lookup"><span data-stu-id="8528f-107">Set to `false` to step over the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8528f-108">설명</span><span class="sxs-lookup"><span data-stu-id="8528f-108">Remarks</span></span>  
 <span data-ttu-id="8528f-109">공용 언어 런타임에서이 스텝 퍼이 프레임에서 다음 관리 되는 명령을 수행 하는 단계 완료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8528f-109">The step completes when the common language runtime performs the next managed instruction in this stepper's frame.</span></span> <span data-ttu-id="8528f-110">경우 `Step` 은 관리 코드에 속하지 않는 스텝에서 호출, 단계는 다음 관리 되는 코드 명령이 스레드에 의해 실행 될 때 완료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8528f-110">If `Step` is called on a stepper, which is not in managed code, the step will complete when the next managed code instruction is executed by the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8528f-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8528f-111">Requirements</span></span>  
 <span data-ttu-id="8528f-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8528f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8528f-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8528f-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8528f-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8528f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8528f-115">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8528f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
