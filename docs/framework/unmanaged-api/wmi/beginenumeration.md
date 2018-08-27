---
title: BeginEnumeration 함수 (관리 되지 않는 API 참조)
description: BeginEnumeration 함수 열거형의 시작 부분에는 열거자를 다시 설정
ms.date: 11/06/2017
api_name:
- BeginEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- BeginEnumeration
helpviewer_keywords:
- BeginEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 08406f7d93671b406b3c7cd8719a7a0e5e423184
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2018
ms.locfileid: "42930632"
---
# <a name="beginenumeration-function"></a>BeginEnumeration 함수
열거형의 시작 부분에 다시 열거자를 다시 설정합니다.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>구문  
  
```  
HRESULT BeginEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              lEnumFlags
); 
```  

## <a name="parameters"></a>매개 변수

`vFunc`  
[in] 이 매개 변수 사용 되지 않습니다.

`ptr` [in] 에 대 한 포인터를 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스.

`lEnumFlags`  
[in] 플래그를 설명 하는 값의 비트 조합 합니다 [주의](#remarks) 열거형에 포함 된 속성을 제어 하는 섹션입니다.

## <a name="return-value"></a>반환 값

이 함수에 의해 반환 되는 다음 값에 정의 된 합니다 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드:

|상수  |값  |설명  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | '(0x80041008 | 플래그의 조합을 `lEnumFlags` 이 잘못 되었거나 잘못 된 인수가 지정 되었습니다. |
|`WBEM_E_UNEXPECTED` | 0x8004101d | 두 번째 호출 `BeginEnumeration` 에 대 한 중간 호출 없이 만들어진 [ `EndEnumeration` ](endenumeration.md)합니다. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006(" | 새 열거형 시작에 사용할 있는 메모리가 충분 하지 않습니다. |
|`WBEM_S_NO_ERROR` | 0 | 함수 호출이 성공 했습니다.  |
  
## <a name="remarks"></a>설명

이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::BeginEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 메서드.

로 전달 될 수 있는 플래그는 `lEnumFlags` 인수에 정의 된 합니다 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드.  다른 그룹의 모든 플래그를 사용 하 여 각 그룹에서 하나 이상의 플래그를 결합할 수 있습니다. 그러나 동일한 그룹의 플래그는 함께 사용할 수 없습니다. 

**그룹 1**

|상수  |값  |설명  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | 0x4 | 키에만 구성 하는 속성이 포함 됩니다. |
|`WBEM_FLAG_REFS_ONLY` | 0x8 | 개체 참조에만 해당 되는 속성이 포함 됩니다. |

**그룹 2**

상수  |값  |설명  |
|---------|---------|---------|
|`WBEM_FLAG_SYSTEM_ONLY` | 0x30 | 시스템 속성에 열거를 제한 합니다. |
|`WBEM_FLAG_NONSYSTEM_ONLY` | 0x40 | 로컬 및 전파 속성을 포함 하지만 열거의 시스템 속성을 제외 합니다. |

클래스:

상수  |값  |설명  |
|---------|---------|---------|
|`WBEM_FLAG_CLASS_OVERRIDES_ONLY` | 0x100 | 열거형 클래스 정의에서 재정의 된 속성을 제한 합니다. |
|`WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` | 0x100 | 현재 클래스 정의에서 재정의 된 속성을 클래스에 정의 된 새 속성을 열거를 제한 합니다. |
| `WBEM_MASK_CLASS_CONDITION` | 0x300 | A에 대해 적용할 (플래그) 대신 마스크를 `lEnumFlags` 경우 확인할 값 `WBEM_FLAG_CLASS_OVERRIDES_ONLY` 또는 `WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` 설정 됩니다. |
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | 열거형 클래스 자체에서 수정 되거나 정의 되는 속성을 제한 합니다. |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0x20 | 열거형 기본 클래스에서 상속 된 속성을 제한 합니다. |

에 대 한 인스턴스:

상수  |값  |설명  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | 열거형 클래스 자체에서 수정 되거나 정의 되는 속성을 제한 합니다. |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0x20 | 열거형 기본 클래스에서 상속 된 속성을 제한 합니다. |


## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** WMINet_Utils.idl  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고자료  
[WMI 및 성능 카운터 (관리 되지 않는 API 참조)](index.md)
