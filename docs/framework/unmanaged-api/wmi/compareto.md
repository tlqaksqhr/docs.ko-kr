---
title: CompareTo 함수 (관리 되지 않는 API 참조)
description: CompareTo 함수는 개체를 다른 WMI 개체를 비교합니다.
ms.date: 11/06/2017
api_name:
- CompareTo
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- CompareTo
helpviewer_keywords:
- CompareTo function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: db4431da90842f4f96a0f09a2f28dc473d956ee3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33460410"
---
# <a name="compareto-function"></a>CompareTo 함수
다른 Windows 관리 개체에 개체를 비교합니다.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>구문  
  
```
HRESULT CompareTo (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              flags,
   [in] IWbemClassObject* pCompareTo 
); 
```  

## <a name="parameters"></a>매개 변수

`vFunc`  
[in] 이 매개 변수를 사용 하지 않습니다.

`ptr`  
[in] 에 대 한 포인터는 [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) 인스턴스.

`flags`  
[in] 비교에 고려해 야 할 개체 특성을 지정 하는 플래그의 비트 조합입니다. 참조는 [주의](#remarks) 한 자세 합니다.

`pCompareTo`  

[in] 비교할 개체입니다. `pcompareTo` 유효한 [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) 인스턴스이거나 않아야 `null`합니다.

## <a name="return-value"></a>반환 값

이 함수에서 반환 되는 다음 값에 정의 된는 *WbemCli.h* 헤더 파일 또는 있습니다를 정의할 수 상수로 코드:

|상수  |값  |설명  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0 x 80041001 | 지정 되지 않은 오류가 발생 했습니다. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | 매개 변수가 올바르지 않습니다. |
| `WBEM_E_UNEXPECTED` | 0x8004101d | 두 번째 호출으로 `BeginEnumeration` 에 대 한 중간 호출 없이 만들어진 [ `EndEnumeration` ](endenumeration.md)합니다. |
| `WBEM_S_NO_ERROR` | 0 | 함수 호출이 성공 했습니다.  |
| `WBEM_S_DIFFERENT` | 0x40003 | 개체는 다릅니다. |
| `WBEM_S_SAME` | 0 | 개체는 비교 플래그에 따라 동일 합니다. |
  
## <a name="remarks"></a>설명

이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::CompareTo](https://msdn.microsoft.com/library/aa391437(v=vs.85).aspx) 메서드.

로 전달 될 수 있는 플래그는 `lEnumFlags` 에 정의 된 인수는 *WbemCli.h* 헤더 파일 또는 있습니다를 정의할 수 상수로 코드입니다. 다음 플래그의 비트 조합을 지정 하 여 비교에 사용 되는 개별 특성을 지정할 수 있습니다.

|상수  |값  |설명  |
|---------|---------|---------|
| `WBEM_FLAG_IGNORE_OBJECT_SOURCE` | 2 | 원본 (서버 및에서 가져온 네임 스페이스)를 무시 합니다. |
| `WBEM_FLAG_IGNORE_QUALIFIERS` | 1 | 모든 한정자를 무시 (포함 하 여 **키** 및 **동적**) |
| `WBEM_FLAG_IGNORE_DEFAULT_VALUES` | 4 | 속성의 기본값을 무시 합니다. 이 플래그는 클래스의 비교에만 적용 됩니다. |
| `WBEM_FLAG_IGNORE_FLAVOR` | 0x20 | 한정자 특성을 무시 합니다. 이 플래그 여전히 고려 한정자 하지만 특색 전파 규칙 등의 차이 무시 하 고 제한을 무시 합니다. |
| `WBEM_FLAG_IGNORE_CASE` | 0x10 | 문자열 값을 비교할 때 대/소문자를 무시 합니다. 문자열 및 값 한정자에 모두 적용 됩니다. 속성 이름과 한정자의 비교는 항상이 플래그가 설정 되어 있는지 여부에 관계 없이 대/소문자 구분 됩니다. |
| `WBEM_FLAG_IGNORE_CLASS` | 0x8 | 비교 되는 개체는 동일한 클래스의 인스턴스를 가정 합니다. 따라서이 플래그는 인스턴스와 관련 된 정보만 비교합니다. 이 플래그를 사용 하 여 성능을 최적화 합니다. 동일한 클래스의 개체가 없는 경우 결과가 정의 되지 않습니다. |

또는 다음과 같이 단일 복합 플래그를 지정할 수 있습니다.

|상수  |값  |설명  |
|---------|---------|---------|
|`WBEM_COMPARISON_INCLUDE_ALL` | 0 | 비교에 사용 된 모든 기능을 고려 합니다. |

## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** WMINet_Utils.idl  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고자료  
[WMI 및 성능 카운터 (관리 되지 않는 API 참조)](index.md)
