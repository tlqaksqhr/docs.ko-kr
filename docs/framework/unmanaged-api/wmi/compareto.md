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
ms.openlocfilehash: bde25ae7455dd7fe35fe1a0a43bb2a6b560c0e3e
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2018
ms.locfileid: "42935010"
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
[in] 이 매개 변수 사용 되지 않습니다.

`ptr`  
[in] 에 대 한 포인터를 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스.

`flags`  
[in] 비교에 대해 고려할 개체 특징을 지정 하는 플래그의 비트 조합입니다. 참조 된 [주의](#remarks) 자세한 내용은 섹션입니다.

`pCompareTo`  

[in] 비교할 개체입니다. `pcompareTo` 올바른 이어야 합니다 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스; 일 수 없습니다 `null`합니다.

## <a name="return-value"></a>반환 값

이 함수에 의해 반환 되는 다음 값에 정의 된 합니다 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드:

|상수  |값  |설명  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | 지정 되지 않은 오류가 발생 했습니다. |
| `WBEM_E_INVALID_PARAMETER` | '(0x80041008 | 매개 변수가 잘못 되었습니다. |
| `WBEM_E_UNEXPECTED` | 0x8004101d | 두 번째 호출 `BeginEnumeration` 에 대 한 중간 호출 없이 만들어진 [ `EndEnumeration` ](endenumeration.md)합니다. |
| `WBEM_S_NO_ERROR` | 0 | 함수 호출이 성공 했습니다.  |
| `WBEM_S_DIFFERENT` | 0x40003 | 개체가 서로 다릅니다. |
| `WBEM_S_SAME` | 0 | 개체는 비교 플래그에 따라 동일 합니다. |
  
## <a name="remarks"></a>설명

이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::CompareTo](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-compareto) 메서드.

로 전달 될 수 있는 플래그는 `lEnumFlags` 인수에 정의 된 합니다 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드. 다음 플래그의 비트 조합 지정 하 여 비교에 사용 되는 개별 특성을 지정할 수 있습니다.

|상수  |값  |설명  |
|---------|---------|---------|
| `WBEM_FLAG_IGNORE_OBJECT_SOURCE` | 2 | (서버 및 네임 스페이스에서 미끄러져) 소스를 무시 합니다. |
| `WBEM_FLAG_IGNORE_QUALIFIERS` | 1 | 모든 한정자를 무시 (포함 **키** 하 고 **동적**) |
| `WBEM_FLAG_IGNORE_DEFAULT_VALUES` | 4 | 속성의 기본값을 무시 합니다. 이 플래그는 클래스의 비교에만 적용 됩니다. |
| `WBEM_FLAG_IGNORE_FLAVOR` | 0x20 | 한정자 특성을 무시 합니다. 이 플래그 여전히 한정자 고려 하지만 전파 규칙과 같은 특색의 차이 무시 및 제한 사항을 무시 합니다. |
| `WBEM_FLAG_IGNORE_CASE` | 0x10 | 문자열 값 비교에서 대/소문자를 무시 합니다. 문자열과 한정자 값에 모두 적용 됩니다. 속성과 한정자 이름은의 비교는 항상이 플래그가 설정 되어 있는지 여부에 관계 없이 대/소문자 구분. |
| `WBEM_FLAG_IGNORE_CLASS` | 0x8 | 비교 되는 개체는 동일한 클래스의 인스턴스를 가정 합니다. 따라서이 플래그는 인스턴스와 관련 된 정보만을 비교합니다. 성능을 최적화 하려면이 플래그를 사용 합니다. 동일한 클래스의 개체가 없으면 결과가 정의 되지 않습니다. |

또는 다음과 같이 단일 복합 플래그를 지정할 수 있습니다.

|상수  |값  |설명  |
|---------|---------|---------|
|`WBEM_COMPARISON_INCLUDE_ALL` | 0 | 비교의 모든 기능을 고려 합니다. |

## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** WMINet_Utils.idl  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고자료  
[WMI 및 성능 카운터 (관리 되지 않는 API 참조)](index.md)
