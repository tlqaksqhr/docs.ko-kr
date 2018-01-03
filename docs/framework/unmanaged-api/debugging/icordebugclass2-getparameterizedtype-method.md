---
title: "ICorDebugClass2::GetParameterizedType 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugClass2.GetParameterizedType
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugClass2::GetParameterizedType
helpviewer_keywords:
- GetParameterizedType method [.NET Framework debugging]
- ICorDebugClass2::GetParameterizedType method [.NET Framework debugging]
ms.assetid: 94b591c4-9302-4af2-a510-089496afb036
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a9cbb755bd8f52482f7eece6e9d236f29cadc419
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugclass2getparameterizedtype-method"></a>ICorDebugClass2::GetParameterizedType 메서드
이 클래스에 대 한 형식 선언을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetParameterizedType (  
    [in] CorElementType                      elementType,  
    [in] ULONG32                             nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType  *ppTypeArgs[],  
    [out] ICorDebugType                    **ppType  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `elementType`  
 [in] 이 클래스에 대 한 요소 유형을 지정 하는 CorElementType 열거형의 값:이 ICorDebugClass2 값 형식을 나타내는 경우 ELEMENT_TYPE_VALUETYPE로이 값을 설정 합니다. 이 값을 설정 ELEMENT_TYPE_CLASS이 `ICorDebugClass2` 복합 유형을 나타냅니다.  
  
 `nTypeArgs`  
 [in] 형식이 제네릭 형식 매개 변수의 수입니다. 형식 매개 변수 (있는 경우)의 수는 클래스에 필요한 개수를 일치 해야 합니다.  
  
 `ppTypeArgs`  
 [in] 형식 매개 변수를 나타내는 ICorDebugType 개체를 가리키는 각각, 포인터의 배열입니다. 제네릭이 아닌 클래스가 사용 하는 경우이 값은 null입니다.  
  
 `ppType`  
 [out] 주소에 대 한 포인터는 `ICorDebugType` 형식 선언을 나타내는 개체입니다. 이 개체는 해당 하는 <xref:System.Type> 관리 코드에서 개체입니다.  
  
## <a name="remarks"></a>설명  
 클래스가 있는 경우 제네릭이 아닌 즉, 형식 매개 변수가 없는 경우 `GetParameterizedType` 단순히 클래스에 해당 하는 런타임 형식 개체를 가져옵니다. `elementType` 클래스에 대 한 올바른 요소 형식에 매개 변수를 설정 해야: ELEMENT_TYPE_VALUETYPE 클래스가 값 형식이 경우 이렇게 하지 않으면 ELEMENT_TYPE_CLASS 합니다.  
  
 클래스 형식 매개 변수를 허용 하는 경우 (예를 들어 `ArrayList<T>`)를 사용할 수 있습니다 `GetParameterizedType` 같은 인스턴스화된 형식에 대 한 형식 개체를 생성 하 `ArrayList<int>`합니다.  
  
## <a name="background-information"></a>배경 정보  
 .NET Framework 버전 1.0 및 1.1에서는 메타 데이터의 모든 형식은 실행 중인 프로세스의 형식에 직접 매핑할 수 없습니다. 따라서 런타임 형식과 메타 데이터 형식이 실행 중인 프로세스에 단일 표현 발생 했습니다. 그러나 메타 데이터에 제네릭 형식 하나 실행 중인 프로세스에서 형식의 다른 인스턴스화 많은에 매핑될 수 있습니다. 예를 들어 메타 데이터 형식 `SortedList<K,V>` 를 매핑할 수 `SortedList<String, EmployeeRecord>`, `SortedList<Int32, String>`, `SortedList<String,Array<Int32>>`등입니다. 따라서 형식 인스턴스를 처리 하는 방법이 필요 합니다.  
  
 .NET Framework 버전 2.0에 도입 된 `ICorDebugType` 인터페이스입니다. 제네릭 형식에 대 한는 `ICorDebugClass` 또는 `ICorDebugClass2` 인스턴스화되지 않은 형식 개체를 나타냅니다 (`SortedList<K,V>`), 및 `ICorDebugType` 개체는 인스턴스화된 여러 형식을 나타냅니다. 제공 된 `ICorDebugClass` 또는 `ICorDebugClass2` 개체를 만들 수 있습니다는 `ICorDebugType` 호출 하 여 인스턴스화에 대 한 개체는 `ICorDebugClass2::GetParameterizedType` 메서드. 만들 수도 있습니다는 `ICorDebugType` Int32 등의 단순 형식 또는 제네릭이 아닌 형식에 대 한 개체입니다.  
  
 도입 된 `ICorDebugType` 형식의 런타임 개념을 나타내는 개체를 API 전반에 걸쳐 ripple 효과 냅니다. 이전에 가져온 함수는 `ICorDebugClass` 또는 `ICorDebugClass2` 개체나는 `CorElementType` 값이 사용 하도록 일반화 되었습니다는 `ICorDebugType` 개체입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
