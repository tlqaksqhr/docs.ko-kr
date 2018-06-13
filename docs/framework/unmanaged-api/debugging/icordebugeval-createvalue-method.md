---
title: ICorDebugEval::CreateValue 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugEval.CreateValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::CreateValue
helpviewer_keywords:
- ICorDebugEval::CreateValue method [.NET Framework debugging]
- CreateValue method [.NET Framework debugging]
ms.assetid: 9a1c0b47-6f10-4fcb-844a-4ab2d7990140
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6d67784daee055106f104d74d098b9926c6de2ec
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33417114"
---
# <a name="icordebugevalcreatevalue-method"></a>ICorDebugEval::CreateValue 메서드
초기 값이 0 또는 null 인 지정 된 형식의 값을 만듭니다.  
  
 이 메서드는.NET Framework 버전 2.0에서에서 사용 되지 않습니다. 사용 하 여 [icordebugeval2:: Createvaluefortype](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md) 대신 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT CreateValue (  
    [in] CorElementType     elementType,  
    [in] ICorDebugClass     *pElementClass,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `elementType`  
 [in] 값은 [CorElementType](../../../../docs/framework/unmanaged-api/metadata/corelementtype-enumeration.md) 값의 형식을 지정 하는 열거형입니다.  
  
 `pElementClass`  
 [in] 에 대 한 포인터는 [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md) 는 형식이 기본 형식이 아닌 경우 값의 클래스를 지정 하는 개체입니다.  
  
 `ppValue`  
 [out] 값을 나타내는 "ICorDebugValue" 개체의 주소에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 `CreateValue` 만듭니다는 `ICorDebugValue` 함수 실행에 사용 하 여의 목적 으로만 지정 된 형식의 개체입니다. 이 값 개체 사용자 상수를 매개 변수로 전달 데 사용할 수 있습니다.  
  
 값 형식의 기본 형식인 경우 해당 초기 값은 0 또는 null입니다. 사용 하 여 [icordebuggenericvalue:: Setvalue](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-setvalue-method.md) 기본 형식의 값을 설정 합니다.  
  
 하는 경우의 값 `elementType` ELEMENT_TYPE_CLASS은 "ICorDebugReferenceValue" 얻게 (에 반환 된 `ppValue`) null 개체 참조를 나타내는입니다. Null 개체 참조 매개 변수가 있는 함수 실행을 전달 하려면이 개체를 사용할 수 있습니다. 설정할 수 없습니다.는 `ICorDebugValue` ; 어디에이 항상 null로 유지 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** 1.0, 1.1  
  
## <a name="see-also"></a>참고 항목  
    
 [CreateValueForType 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md)  
 ICorDebugValue
