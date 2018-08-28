---
title: BeginMethodEnumeration 함수 (관리 되지 않는 API 참조)
description: BeginMethodEnumeration 함수 개체의 메서드는 열거를 시작합니다.
ms.date: 11/06/2017
api_name:
- BeginMethodEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- BeginMethodEnumeration
helpviewer_keywords:
- BeginMethodEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e69625184aca7d1ebd4bb0b7dc7c4958596b906a
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/27/2018
ms.locfileid: "43000345"
---
# <a name="beginenumeration-function"></a>BeginEnumeration 함수
개체에 대해 사용할 수 있는 방법의 열거형을 시작합니다.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>구문  
  
``` 
HRESULT BeginMethodEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              lEnumFlags
); 
```  

## <a name="parameters"></a>매개 변수

`vFunc`  
[in] 이 매개 변수 사용 되지 않습니다.

`ptr`  
[in] 에 대 한 포인터를 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스.

`lEnumFlags`  
[in] 영 (0) 모든 메서드 또는 열거형의 범위를 지정 하는 플래그에 대 한 합니다. 에 정의 된 다음 플래그를 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드:

상수  |값  |설명  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | 열거형 클래스 자체에 정의 된 메서드를 제한 합니다. |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0x20 | 열거형 기본 클래스에서 상속 된 속성을 제한 합니다. |

## <a name="return-value"></a>반환 값

이 함수에 의해 반환 되는 다음 값에 정의 된 합니다 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드:

|상수  |값  |설명  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | '(0x80041008 | `lEnnumFlags` 0이 아닌 값 이며 지정된 된 플래그 중 하나가 아닙니다. |
|`WBEM_S_NO_ERROR` | 0 | 함수 호출이 성공 했습니다.  |
  
## <a name="remarks"></a>설명

이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::BeginMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-beginmethodenumeration) 메서드.

이 메서드 호출은 현재 개체가 클래스 정의 하는 경우에 지원 됩니다. 조작 메서드를 사용할 수 없기 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스를 가리키는 포인터입니다. 지정된 된 인스턴스에 대 한 변형 되지 메서드를 열거 순서는 보장 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)합니다.

## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** WMINet_Utils.idl  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고자료  
[WMI 및 성능 카운터 (관리 되지 않는 API 참조)](index.md)
