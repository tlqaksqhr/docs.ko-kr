---
title: "ICorDebugStepper::StepRange 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStepper.StepRange
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStepper::StepRange
helpviewer_keywords:
- StepRange method [.NET Framework debugging]
- ICorDebugStepper::StepRange method [.NET Framework debugging]
ms.assetid: b9776112-6e6d-4708-892a-8873db02e16f
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a02efe1b701506cc3de695c5b79d5e9c84b25b8f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugsteppersteprange-method"></a>ICorDebugStepper::StepRange 메서드
한 단계씩 실행 하 고 이후의 지정된 된 범위의 코드에 도달할 때 반환할 포함 스레드를 통해이 ICorDebugStepper 하면 됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT StepRange (  
    [in] BOOL     bStepIn,  
    [in, size_is(cRangeCount)] COR_DEBUG_STEP_RANGE ranges[],  
    [in] ULONG32  cRangeCount  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `bStepIn`  
 [in] 로 설정 `true` 스레드 내에서 호출 되는 함수를 한 단계씩에 있습니다. 로 설정 `false` 함수를 통해 단계로 합니다.  
  
 `ranges`  
 [in] 범위를 지정 하며 각 COR_DEBUG_STEP_RANGE 구조체의 배열입니다.  
  
 `cRangeCount`  
 [in] `ranges` 배열의 크기입니다.  
  
## <a name="remarks"></a>설명  
 `StepRange` 처럼 사용할 수 있는 방법의 [icordebugstepper:: Step](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-step-method.md) 메서드를 제외 하 고 지정된 된 범위 외부의 코드까지 완료 되지 않으면에 도달 합니다.  
  
 이 한 번에 하나의 명령을 단계별로 실행 하는 보다 더 효율적일 수 있습니다. 스텝 퍼의 프레임의 시작 부분부터 오프셋된 쌍의 목록으로 범위가 지정 됩니다.  
  
 범위는 메서드의 Microsoft MSIL (intermediate language) 코드를 기준으로 합니다. 호출 [icordebugstepper:: Setrangeil](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setrangeil-method.md) 와 `false` 메서드의 네이티브 코드에 상대적인 범위 수 있도록 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
