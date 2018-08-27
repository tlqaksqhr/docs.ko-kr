---
title: 다음 함수 (관리 되지 않는 API 참조)
description: 다음 함수 retireves 열거형에서 다음 속성입니다.
ms.date: 11/06/2017
api_name:
- Next
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Next
helpviewer_keywords:
- Next function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 15d470ccf9384695aa38a50c2c062c1b660fea96
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2018
ms.locfileid: "42934975"
---
# <a name="next-function"></a>Next 함수
에 대 한 호출을 시작 하는 열거형의 다음 속성을 검색 [BeginEnumeration](beginenumeration.md)합니다.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>구문  
  
```  
HRESULT Next (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              lFlags,
   [out] BSTR*            pstrName,
   [out] VARIANT*         pVal,
   [out] CIMTYPE*         pvtType,
   [out] LONG*            plFlavor     
); 
```  

## <a name="parameters"></a>매개 변수

`vFunc`  
[in] 이 매개 변수 사용 되지 않습니다.

`ptr`  
[in] 에 대 한 포인터를 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스.

`lFlags`  
[in] 예약 되어 있습니다. 이 매개 변수는 0 이어야 합니다.

`pstrName`  
[out] 새 `BSTR` 속성 이름을 포함 하는 합니다. 이 매개 변수를 설정할 수 있습니다 `null` 이름이 필요 하지 않은 경우.

`pVal`  
[out] `VARIANT` 속성의 값으로 채워집니다. 이 매개 변수를 설정할 수 있습니다 `null` 값 필요 하지 않은 경우. 함수는 오류 코드를 반환 하는 경우는 `VARIANT` 전달할 `pVal` 는 왼쪽 수정 되지 않은 합니다. 

`pvtType`  
[out] 에 대 한 포인터를 `CIMTYPE` 변수 (한 `LONG` 배치 되는 속성의 형식으로). 이 속성의 값 수를 `VT_NULL_VARIANT`, 실제 형식의 속성을 확인 해야 하는 경우. 이 매개 변수 수도 있습니다 `null`합니다. 

`plFlavor`  
[out] `null`, 또는 속성의 원본에서 정보를 수신 하는 값입니다. 가능한 값에 대 한 [설명] 섹션을 참조 하세요. 

## <a name="return-value"></a>반환 값

이 함수에 의해 반환 되는 다음 값에 정의 된 합니다 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드:

|상수  |값  |설명  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | 일반 오류가 발생이 했습니다. |
| `WBEM_E_INVALID_PARAMETER` | '(0x80041008 | 매개 변수가 잘못 되었습니다. |
| `WBEM_E_UNEXPECTED` | 0x8004101d | 에 대 한 호출이 없습니다 합니다 [ `BeginEnumeration` ](beginenumeration.md) 함수입니다. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006(" | 새 열거형 시작에 사용할 있는 메모리가 충분 하지 않습니다. |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | 원격 프로시저는 현재 프로세스와 실패 한 Windows 관리 간에 호출 합니다. |
| `WBEM_S_NO_ERROR` | 0 | 함수 호출이 성공 했습니다.  |
| `WBEM_S_NO_MORE_DATA` | 0x40005 | 열거형에 더 많은 속성이 있습니다. |
  
## <a name="remarks"></a>설명

이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-next) 메서드.

이 메서드는 또한 시스템 속성을 반환합니다.

속성의 내부 형식이 개체 경로, 날짜 또는 시간 또는 다른 특별 한 형식, 그런 다음 반환 된 형식에 없는 경우 충분 한 정보입니다. 호출자를 검사 해야 합니다는 `CIMTYPE` 속성이 개체 참조, 날짜 또는 시간 또는 다른 특별 한 형식 인지 확인 하려면 지정된 된 속성에 대 한 합니다.

하는 경우 `plFlavor` 아닙니다 `null`, `LONG` 값이 다음과 같이 속성의 원본에 대 한 정보를 수신 합니다.

|상수  |값  |설명  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | 0x40 | 속성에는 표준 시스템 속성이입니다. |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | 0x20 | 클래스: 속성은 부모 클래스에서 상속 됩니다. </br> 인스턴스에 대 한: 속성을 부모 클래스에서 상속 하는 동안 수정 되지 않은 인스턴스가 있습니다.  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | 0 | 클래스: 속성이 파생된 클래스에 속합니다. </br> 인스턴스에 대 한: 인스턴스에서; 속성이 수정 됩니다 즉, 값이 제공 된 또는 한정자를 추가 또는 수정 합니다. |

## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** WMINet_Utils.idl  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고자료  
[WMI 및 성능 카운터 (관리 되지 않는 API 참조)](index.md)
