---
title: "ICorDebugType::EnumerateTypeParameters 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugType.EnumerateTypeParameters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::EnumerateTypeParameters
helpviewer_keywords:
- EnumerateTypeParameters method, ICorDebugType interface [.NET Framework debugging]
- ICorDebugType::EnumerateTypeParameters method [.NET Framework debugging]
ms.assetid: 1ee1f6e6-1bd7-4ebb-83b8-ff9a08ca03de
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d4b864b2b5fd4f2a6ed03218ce6e7b6f3bf62202
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugtypeenumeratetypeparameters-method"></a>ICorDebugType::EnumerateTypeParameters 메서드
포함 된 ICorDebugTypeEnum에 대 한 인터페이스 포인터를 가져옵니다는 <xref:System.Type> 이 ICorDebugType에서 참조 하는 클래스의 매개 변수입니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum   **ppTyParEnum  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppTyParEnum`  
 [out] 주소에 대 한 포인터는 `ICorDebugTypeEnum` 형식의 매개 변수가 포함 된 합니다.  
  
## <a name="remarks"></a>설명  
 사용할 수 있습니다 `EnumerateTypeParameters` CorElementType 값으로 반환 되 면 [icordebugtype:: Gettype](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) ELEMENT_TYPE_CLASS ELEMENT_TYPE_VALUETYPE, ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, ELEMENT_TYPE_ PTR, 또는 ELEMENT_TYPE_FNPTR 합니다. 매개 변수 목록 및 해당 순서 번호 형식에 따라 달라 집니다.  
  
-   ELEMENT_TYPE_CLASS 또는 ELEMENT_TYPE_VALUETYPE:에 포함 된 형식 매개 변수 개수는 `ICorDebugTypeEnum` 해당 클래스에 대 한 공식적인 형식 매개 변수 수에 따라 달라 집니다이 메서드가 반환 합니다. 예를 들어, 형식이 `class Dict<String,int32>`, 다음 `EnumerateTypeParameters` 돌아갑니다는 `ICorDebugTypeEnum` 나타내는 개체가 포함 된 `String` 및 `int32` 순서로 합니다.  
  
-   ELEMENT_TYPE_FNPTR:에 포함 된 형식 매개 변수 수는 `ICorDebugTypeEnum` 하나가 됩니다 함수에서 허용 하는 인수 개수 보다 큽니다. 에 포함 된 첫 번째 형식 매개 변수는 `ICorDebugTypeEnum` 함수에 대 한 반환 형식 및 후속 형식 매개 변수는 함수의 매개 변수입니다.  
  
-   ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, 또는 ELEMENT_TYPE_PTR: 하나의 형식 매개 변수 반환 됩니다. 예를 들어, 형식이 배열 형식 같은 `int32[]`,`EnumerateTypeParameters` 반환 됩니다는 `ICorDebugTypeEnum` 나타내는 개체를 포함 하는 `int32`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
