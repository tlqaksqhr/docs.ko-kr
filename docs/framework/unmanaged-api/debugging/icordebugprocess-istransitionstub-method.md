---
title: "ICorDebugProcess::IsTransitionStub 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess.IsTransitionStub
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess::IsTransitionStub
helpviewer_keywords:
- ICorDebugProcess::IsTransitionStub method [.NET Framework debugging]
- IsTransitionStub method [.NET Framework debugging]
ms.assetid: f7653317-7e48-4163-be03-f50f1a4b0f70
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 60f6e4116768d2d855edd941df796167754b3ab4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugprocessistransitionstub-method"></a>ICorDebugProcess::IsTransitionStub 메서드
관리 코드에 전환 하는 스텁 내부 주소 인지 여부를 나타내는 값을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT IsTransitionStub(  
    [in]  CORDB_ADDRESS address,  
    [out] BOOL *pbTransitionStub);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `address`  
 [in] A `CORDB_ADDRESS` 에 주소를 지정 하는 값입니다.  
  
 `pbTransitionStub`  
 [out] 부울 값이에 대 한 포인터 `true` 지정된 된 주소를 관리 코드로; 전환 하는 스텁 안에 있으면 그렇지 않은 경우 *`pbTransitionStub` 은 `false`합니다.  
  
## <a name="remarks"></a>설명  
 `IsTransitionStub` 메서드를 사용 하 단계별 실행의 비관리 코드 관리 스텝 퍼에 단계별 실행 제어를 반환할 때 결정할 수 있습니다.  
  
 이식 가능한 실행 (PE) 파일에 대 한 정보를 보고 하 여 전환 스텁을 식별할 수도 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
