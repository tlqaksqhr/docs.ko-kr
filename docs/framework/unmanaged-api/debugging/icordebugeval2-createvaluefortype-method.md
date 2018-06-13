---
title: ICorDebugEval2::CreateValueForType 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.CreateValueForType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::CreateValueForType
helpviewer_keywords:
- CreateValueForType method [.NET Framework debugging]
- ICorDebugEval2::CreateValueForType method [.NET Framework debugging]
ms.assetid: ea38ae20-7e0a-427a-be77-d78fae719d82
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 683457c249915708becadaeda9dec265666e2023
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412109"
---
# <a name="icordebugeval2createvaluefortype-method"></a>ICorDebugEval2::CreateValueForType 메서드
초기 값이 0 또는 null 인 지정 된 형식의 새 ICorDebugValue에 대 한 포인터를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT CreateValueForType (  
    [in] ICorDebugType         *pType,  
    [out] ICorDebugValue       **ppValue  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pType`  
 [in] 형식을 나타내는 ICorDebugType 개체에 대 한 포인터입니다.  
  
 `ppValue`  
 [out] 주소에 대 한 포인터는 `ICorDebugValue` 값을 나타내는 개체입니다.  
  
## <a name="remarks"></a>설명  
 `CreateValueForType` 일반화 [icordebugeval:: Createvalue](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-createvalue-method.md) 임의의 개체 종류를 지정할 수 있도록 하 여 포함 하 여 생성 된 형식을 같은 `List<int>`합니다. 이 메서드의 유일한 목적은 함수 실행에 전달 될 수 있는 값을 생성 하는 것입니다.  
  
 클래스 또는 값 형식이 형식 이어야 합니다. 배열 값 또는 문자열 값을 만드는이 메서드를 사용할 수 없습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
