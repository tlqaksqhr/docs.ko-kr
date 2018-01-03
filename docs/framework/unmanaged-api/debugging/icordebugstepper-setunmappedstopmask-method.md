---
title: "ICorDebugStepper::SetUnmappedStopMask 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStepper.SetUnmappedStopMask
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStepper::SetUnmappedStopMask
helpviewer_keywords:
- ICorDebugStepper::SetUnmappedStopMask method [.NET Framework debugging]
- SetUnmappedStopMask method [.NET Framework debugging]
ms.assetid: b1211981-e90c-4e05-8def-fa18d85ad9ab
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2fffd523caef6bba1b495f9b8a257f57bd8955af
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugsteppersetunmappedstopmask-method"></a>ICorDebugStepper::SetUnmappedStopMask 메서드
매핑되지 않은 코드 실행을 중지할의 유형을 지정 하는 값을 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT SetUnmappedStopMask (  
    [in] CorDebugUnmappedStop   mask  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `mask`  
 [in] 디버거는 실행을 중단 하는 데는 비관리 코드의 형식을 지정 하는 CorDebugUnmappedStop 열거형의 값입니다.  
  
 기본값은 STOP_OTHER_UNMAPPED 합니다. 값 STOP_UNMANAGED interop 디버깅에 유효합니다.  
  
## <a name="remarks"></a>설명  
 디버거는 적시에 (JIT) 컴파일에 Microsoft MSIL (intermediate language)로 해당 매핑되지는를 찾으면; 비관리 코드의 해당 형식을 지정 하는 플래그 설정 된 경우 실행 중단 그렇지 않은 경우 단계별 실행 투명 하 게 계속 합니다.  
  
 디버거를 사용 하지 않는 스텝 메서드를 입력 하는 경우 다음 않습니다 반드시 실행 되지 매핑되지 않은 코드.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
