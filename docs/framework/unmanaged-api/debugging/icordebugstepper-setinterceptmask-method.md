---
title: "ICorDebugStepper::SetInterceptMask 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStepper.SetInterceptMask
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStepper::SetInterceptMask
helpviewer_keywords:
- SetInterceptMask method [.NET Framework debugging]
- ICorDebugStepper::SetInterceptMask method [.NET Framework debugging]
ms.assetid: 6245e2ae-5cc2-43ff-8cc1-71953d12113a
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2a99b504c0ce58ca6b89153667598cd4c2c682d9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugsteppersetinterceptmask-method"></a>ICorDebugStepper::SetInterceptMask 메서드
한 단계씩 코드의 형식을 지정 하는 값을 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT SetInterceptMask (  
    [in] CorDebugIntercept    mask  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `mask`  
 [in] 코드의 형식을 지정 하는 CorDebugIntercept 열거형의 값의 조합입니다.  
  
## <a name="remarks"></a>설명  
 인터셉터에 대 한 비트가 설정 된 경우 스텝 퍼 가로채기 코드가의 지정된 된 형식 발생 될 때 완료 됩니다. 비트가 가로채기 코드가 건너뜁니다.  
  
 `SetInterceptMask` 메서드에 있을 수 있습니다와 상호 작용 예기치 못한 [icordebugstepper:: Setunmappedstopmask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) (사용자의 관점에서 볼). 예를 들어 경우만 표시 됨 (즉,-내부) 클래스 초기화 코드의 부분에 매핑 정보가 및 STOP_NO_MAPPING_INFO 설정 되어 있지 않습니다 (참조는 [icordebugstepper:: Setunmappedstopmask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) 메서드 및 CorDebugUnmappedStop 열거형) 스텝 퍼 클래스 초기화 건너뛸 됩니다. 기본적으로의 INTERCEPT_NONE 값만는 `CorDebugIntercept` 열거형이 사용 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
