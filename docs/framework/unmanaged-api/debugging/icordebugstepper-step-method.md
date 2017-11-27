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
ms.openlocfilehash: 914773adefd2ed4c1aa98310fd27a0cbc829bf49
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugstepperstep-method"></a>ICorDebugStepper::Step 메서드
한 단계씩 실행 하려면 필요에 따라 하 고 포함 스레드를 통해이 ICorDebugStepper로 인해 스레드 내에서 호출 된 함수를 통해 단일 단계를 계속 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT Step (  
    [in] BOOL   bStepIn  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `bStepIn`  
 [in] 로 설정 `true` 스레드 내에서 호출 되는 함수를 한 단계씩에 있습니다. 로 설정 `false` 함수를 통해 단계로 합니다.  
  
## <a name="remarks"></a>설명  
 공용 언어 런타임에서이 스텝 퍼이 프레임에서 다음 관리 되는 명령을 수행 하는 단계 완료 됩니다. 경우 `Step` 은 관리 코드에 속하지 않는 스텝에서 호출, 단계는 다음 관리 되는 코드 명령이 스레드에 의해 실행 될 때 완료 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
