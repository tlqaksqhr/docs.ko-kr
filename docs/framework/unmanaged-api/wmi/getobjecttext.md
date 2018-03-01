---
title: "GetObjectText 함수 (관리 되지 않는 API 참조)"
description: "GetObjectText 함수 MOF 구문으로 개체의 텍스트 렌더링을 반환합니다."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- GetObjectText
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetObjectText
helpviewer_keywords:
- GetObjectText function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0b47dc73bb9da71b0c8593aa5758179327d7572d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="getobjecttext-function"></a>GetObjectText 함수
관리 되는 MOF (Object Format) 구문에서 개체의 텍스트 렌더링을 반환합니다.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>구문  
  
```  
HRESULT GetObjectText (
   [in] int                vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LONG                lFlags,
   [out] BSTR*              pstrObjectText
); 
```  

## <a name="parameters"></a>매개 변수

`vFunc`  
[in] 이 매개 변수를 사용 하지 않습니다.

`ptr`  
[in] 에 대 한 포인터는 [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) 인스턴스.

`lFlags`  
[in] 일반적으로 0입니다. 경우 `WBEM_FLAG_NO_FLAVORS` (또는 0x1)을 지정 한정자는 전파 또는 버전 정보 없이 포함 합니다.

`pstrObjectText`   
[out] 에 대 한 포인터는 `null` 항목입니다. 반환 시 새로 할당 된 `BSTR` 개체의 MOF 구문 렌더링을 포함 하 합니다.  

## <a name="return-value"></a>반환 값

이 함수에서 반환 되는 다음 값에 정의 된는 *WbemCli.h* 헤더 파일 또는 있습니다를 정의할 수 상수로 코드:

|상수  |값  |설명  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0 x 80041001 | 일반 오류가 발생이 했습니다. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | 매개 변수가 올바르지 않습니다. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 작업을 완료 하려면 사용할 수 있는 메모리가 충분 하지 않습니다. |
|`WBEM_S_NO_ERROR` | 0 | 함수 호출이 성공 했습니다.  |
  
## <a name="remarks"></a>설명

이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::GetObjectText](https://msdn.microsoft.com/library/aa391448(v=vs.85).aspx) 메서드.

개체에 대 한 모든 정보는 있지만 원본 개체를 다시 만들 수 있게 되기를 MOF 컴파일러에 대 한 충분 한 정보만 반환 하는 MOF 텍스트가 없습니다. 예를 들어, 없습니다 전파 한정자 또는 부모 클래스 속성이 포함 되어 있습니다.

다음 알고리즘은 메서드의 매개 변수 텍스트를 다시 만드는 데 사용 됩니다.

1. 매개 변수는 해당 식별자 값 순서 대로 resequenced 됩니다.
1. 으로 지정 된 매개 변수 `[in]` 및 `[out]` 단일 매개 변수를 결합 됩니다.
 
`pstrObjectText`에 대 한 포인터 여야 합니다는 `null` 함수를 호출할 때는 하지를 가리켜야 포인터가 할당을 취소할 수는 때문에 메서드 호출 전에 올바르지 않은 하는 문자열입니다.

## <a name="requirements"></a>요구 사항  
**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** WMINet_Utils.idl  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고 항목  
[WMI 및 성능 카운터 (관리 되지 않는 API 참조)](index.md)
