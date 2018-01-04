---
title: "ICorDebugType::GetStaticFieldValue 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugType.GetStaticFieldValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugType::GetStaticFieldValue
helpviewer_keywords:
- GetStaticFieldValue method, ICorDebugType interface [.NET Framework debugging]
- ICorDebugType::GetStaticFieldValue method [.NET Framework debugging]
ms.assetid: 62eb5d55-53ee-4fb3-8d47-7b6c96808f9e
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2a6a7305017c83b539a3d5ec11fa61ccd2af90a8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugtypegetstaticfieldvalue-method"></a>ICorDebugType::GetStaticFieldValue 메서드
토큰을 지정 된 스택 프레임에 지정 된 필드에서 참조 하는 정적 필드의 값을 포함 하는 ICorDebugValue 개체에 인터페이스 포인터를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetStaticFieldValue (  
    [in]  mdFieldDef        fieldDef,  
    [in]  ICorDebugFrame    *pFrame,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `fieldDef`  
 [in] `mdFieldDef` 정적 필드를 지정 하는 토큰입니다.  
  
 `pFrame`  
 [in] 스택 프레임을 나타내는 ICorDebugFrame에 대 한 포인터입니다.  
  
 `ppValue`  
 [out] 주소에 대 한 포인터는 `ICorDebugValue` 정적 필드의 값이 들어 있는입니다.  
  
## <a name="remarks"></a>설명  
 `GetStaticFieldValue` 메서드 있습니다 사용할 형식이 ELEMENT_TYPE_CLASS 또는 ELEMENT_TYPE_VALUETYPE, 경우에에 표시 된 대로 [icordebugtype:: Gettype](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) 메서드.  
  
 제네릭이 아닌 형식에 대 한 작업을 수행 하 여 `GetStaticFieldValue` 호출 동일 [icordebugclass:: Getstaticfieldvalue](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getstaticfieldvalue-method.md) ICorDebugClass 개체에서 반환 되는에 [icordebugtype:: Getclass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md).  
  
 제네릭 형식의 정적 필드 값을 특정 인스턴스화와 관련 됩니다. 또한 정적 필드 스레드, 컨텍스트, 또는 응용 프로그램 도메인을 기준으로 될 수, 다음 스택 프레임 할 경우 디버거에서 적절 한 값을 결정 합니다.  
  
## <a name="remarks"></a>설명  
 `GetStaticFieldValue`호출할 때에 사용할 수 `ICorDebugType::GetType` ELEMENT_TYPE_CLASS 또는 ELEMENT_TYPE_VALUETYPE 값을 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
