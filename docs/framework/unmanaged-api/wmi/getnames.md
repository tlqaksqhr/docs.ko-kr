---
title: "GetNames 함수 (관리 되지 않는 API 참조)"
description: "GetNames 함수 개체의 속성의 이름을 검색합니다."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- GetNames
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetNames
helpviewer_keywords:
- GetNames function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 80284900c318a3776168b781ce2e0e5e4a68f96d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="getnames-function"></a>GetNames 함수
하위 집합 또는 모든 개체의 속성 이름을 검색합니다. 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>구문  
  
```  
HRESULT GetNames (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszQualifierName,
   [in] LONG                lFlags,
   [in] VARIANT*            pQualifierValue,
   [out] SAFEARRAY (BSTR)** pstrNames
); 
```  

## <a name="parameters"></a>매개 변수

`vFunc`  
[in] 이 매개 변수를 사용 하지 않습니다.

`ptr`  
[in] 에 대 한 포인터는 [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) 인스턴스.

`wszQualifierName`  
[in] 에 대 한 포인터를 올바른 `LPCWSTR` 작동 하는 한정자 이름 필터의 일부분으로 지정 하는 합니다. 자세한 내용은 참조는 [주의](#remarks) 섹션. 이 매개 변수는 `null`일 수 있습니다. 

`lFlags`  
[in] 비트 필드의 조합입니다. 자세한 내용은 참조는 [주의](#remarks) 섹션.

`pQualifierValue`   
[in] 에 대 한 포인터를 올바른 `VARIANT` 구조 필터 값으로 초기화 합니다. 이 매개 변수는 `null`일 수 있습니다. 

`pstrNames`  
[out] A `SAFEARRAY` 속성 이름이 포함 된 구조입니다. 이 매개 변수 입력 시에 대 한 포인터를 일 항상 해야 `null`합니다. 참조는 [주의](#remarks) 한 자세 합니다. 

## <a name="return-value"></a>반환 값

이 함수에서 반환 되는 다음 값에 정의 된는 *WbemCli.h* 헤더 파일 또는 있습니다를 정의할 수 상수로 코드:

|상수  |값  |설명  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0 x 80041001 | 일반 오류가 발생이 했습니다. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | 하나 이상의 매개 변수가 유효 하지 않음 또는 플래그 및 매개 변수는 잘못 된 조합이 지정 되었습니다. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 작업을 완료 하려면 사용할 수 있는 메모리가 충분 하지 않습니다. |
|`WBEM_S_NO_ERROR` | 0 | 함수 호출이 성공 했습니다.  |
  
## <a name="remarks"></a>설명

이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::GetNames](https://msdn.microsoft.com/library/aa391447(v=vs.85).aspx) 메서드.

반환 된 명명 된 매개 변수 및 플래그의 조합에 의해 제어 됩니다. 예를 들어 함수에는 모든 속성 이름이 나 키 속성의 이름에만 반환할 수 있습니다.  기본 필터에 지정 된는 `lFlags` 매개 변수 및 다른 매개 변수와 그에 따라 달라 집니다.

플래그 값에 `lFlags` 는 비트 필드


로 전달 될 수 있는 플래그는 `lEnumFlags` 인수는에 정의 되어 있는 비트 필드는 *WbemCli.h* 헤더 파일 또는 있습니다를 정의할 수 상수로 코드입니다.  다른 그룹의 모든 플래그와 각 그룹에서 하나 이상의 플래그를 결합할 수 있습니다. 그러나 동일한 그룹의 플래그는 함께 사용할 수 없습니다. 

| 그룹 1 플래그 |값  |설명  |
|---------|---------|---------|
| `WBEM_FLAG_ALWAYS` | 0 | 모든 속성 이름이 반환 됩니다. `strQualifierName`및 `pQualifierVal` 이 사용 되지 않습니다. |
| `WBEM_FLAG_ONLY_IF_TRUE` | 1 | 지정 된 이름의 한정자가 있는 속성에만 반환는 `strQualifierName` 매개 변수입니다. 지정 해야이 플래그를 사용할 경우 `strQualifierName`합니다. |
|`WBEM_FLAG_ONLY_IF_FALSE` | 2 |  지정 된 이름의 한정자가 없는 속성에만 반환는 `strQualifierName` 매개 변수입니다. 지정 해야이 플래그를 사용할 경우 `strQualifierName`합니다. |
|`WBEM_FLAG_ONLY_IF_IDENTICAL` | 3 | 속성에서 지정 된 이름의 한정자가을 반환는 `wszQualifierName` 매개 변수 및 값에 지정 된 동일한도 `pQualifierVal` 구조입니다. 둘 다 지정 해야이 플래그를 사용 하는 경우는 `wszQualifierName` 및 `pQualifierValue`합니다. |

| 그룹 2 플래그 |값  |설명  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | 0x4 | 키를 정의 하는 속성의 이름만 반환 합니다. |
|`WBEM_FLAG_REFS_ONLY` | 0x8 | 반환 속성 이름만 개체 참조입니다. |

| 그룹 3 플래그 |값  |설명  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | 가장 많이 파생 된 클래스에 속하는 속성 이름이 반환 됩니다. 부모 클래스에서 속성을 제외 합니다. |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0x20 | 부모 클래스에 속하는 속성 이름이 반환 됩니다. |
|`WBEM_FLAG_SYSTEM_ONLY` | 0 x 30 | 시스템 속성의 이름만 반환 합니다. |
|`WBEM_FLAG_NONSYSTEM_ONLY` | 0x40 | 비 시스템 속성의 이름만 반환 합니다. |

함수는 항상 새 할당 `SAFEARRAY` 반환 하는 경우 `WBEM_S_NO_ERROR`, 및 `pstrNames` 항상 가리키면로 설정 됩니다. 속성이 지정된 된 필터와 일치 하는 경우 반환 되는 배열에서 0 요소를 포함할 수 있습니다. 함수가 아닌 다른 값을 반환 하는 경우 `WBM_S_NO_ERROR`, 새 `SAFEARRAY` 구조 반환 되지 않습니다.
 
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** WMINet_Utils.idl  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고 항목  
[WMI 및 성능 카운터 (관리 되지 않는 API 참조)](index.md)
