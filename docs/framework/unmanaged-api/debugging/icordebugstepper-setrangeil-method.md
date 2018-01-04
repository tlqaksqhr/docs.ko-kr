---
title: "ICorDebugStepper::SetRangeIL 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStepper.SetRangeIL
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStepper::SetRangeIL
helpviewer_keywords:
- SetRangeIL method [.NET Framework debugging]
- ICorDebugStepper::SetRangeIL method [.NET Framework debugging]
ms.assetid: a20c95f0-6da7-4b41-b27f-584211cebb92
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 658f0164a73cfb5dbab0379eda2f61505865d2c4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugsteppersetrangeil-method"></a><span data-ttu-id="3412d-102">ICorDebugStepper::SetRangeIL 메서드</span><span class="sxs-lookup"><span data-stu-id="3412d-102">ICorDebugStepper::SetRangeIL Method</span></span>
<span data-ttu-id="3412d-103">지정 하는 값을 설정 여부에 대 한 호출이 [icordebugstepper:: Steprange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) 네이티브 코드에 상대적인 않거나 Microsoft를 기준으로 값을 중간는 실행 중인 메서드의 MSIL (language) 코드는 인수 전달 통해</span><span class="sxs-lookup"><span data-stu-id="3412d-103">Sets a value that specifies whether calls to [ICorDebugStepper::StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) pass argument values that are relative to the native code or relative to Microsoft intermediate language (MSIL) code of the method that is being stepped through.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3412d-104">구문</span><span class="sxs-lookup"><span data-stu-id="3412d-104">Syntax</span></span>  
  
```  
HRESULT SetRangeIL (  
    [in] BOOL    bIL  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3412d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3412d-105">Parameters</span></span>  
 `bIL`  
 <span data-ttu-id="3412d-106">[in] 로 설정 `true` 에 MSIL 코드 상대적인 범위를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3412d-106">[in] Set to `true` to specify that the ranges are relative to the MSIL code.</span></span> <span data-ttu-id="3412d-107">로 설정 `false` 를 네이티브 코드로 상대적인 범위를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3412d-107">Set to `false` to specify that the ranges are relative to the native code.</span></span> <span data-ttu-id="3412d-108">기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="3412d-108">The default value is `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3412d-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3412d-109">Requirements</span></span>  
 <span data-ttu-id="3412d-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3412d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3412d-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3412d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3412d-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3412d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3412d-113">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3412d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
