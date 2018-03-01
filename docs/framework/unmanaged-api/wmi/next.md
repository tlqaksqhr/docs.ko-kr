---
title: "Next 함수 (관리 되지 않는 API 참조)"
description: "다음 함수 retireves 열거형에서 다음 속성입니다."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
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
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e59ef3f65b75a91708dc65f7d4e3d811dc2d3f9d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="next-function"></a>Next 함수
에 대 한 호출으로 시작 하는 열거형에서 다음 속성을 검색 [BeginEnumeration](beginenumeration.md)합니다.  

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
[in] 이 매개 변수를 사용 하지 않습니다.

`ptr`  
[in] 에 대 한 포인터는 [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) 인스턴스.

`lFlags`  
[in] 예약 되어 있습니다. 이 매개 변수는 0 이어야 합니다.

`pstrName`  
[out] 새 `BSTR` 속성 이름이 들어 있는입니다. 이 매개 변수를 설정할 수 있습니다 `null` 이름이 필요 하지 않은 경우.

`pVal`  
[out] A `VARIANT` 속성의 값으로 채워집니다. 이 매개 변수를 설정할 수 있습니다 `null` 값이 필요 하지 않습니다. 함수는 오류 코드를 반환 하는 경우는 `VARIANT` 에 전달 된 `pVal` 왼쪽 수정 합니다. 

`pvtType`  
[out] 에 대 한 포인터는 `CIMTYPE` 변수 (한 `LONG` 속성의 형식을 추가 하는에). 이 속성의 값 수는 `VT_NULL_VARIANT`, 실제 형식의 속성을 확인 해야 하는 경우. 또한이 매개 변수 수 `null`합니다. 

`plFlavor`  
[out] `null`, 또는 속성의 출처 정보를 수신 하는 값입니다. 가능한 값은 [설명] 섹션을 참조 합니다. 

## <a name="return-value"></a>반환 값

이 함수에서 반환 되는 다음 값에 정의 된는 *WbemCli.h* 헤더 파일 또는 있습니다를 정의할 수 상수로 코드:

|상수  |값  |설명  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0 x 80041001 | 일반 오류가 발생이 했습니다. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | 매개 변수가 올바르지 않습니다. |
| `WBEM_E_UNEXPECTED` | 0x8004101d | 에 대 한 호출이 했습니다는 [ `BeginEnumeration` ](beginenumeration.md) 함수입니다. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 새 열거형을 시작 하려면 사용할 수 있는 메모리가 충분 하지 않습니다. |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | 현재 프로세스와 Windows 관리 하지 못했습니다 원격 프로시저 간에 호출 합니다. |
| `WBEM_S_NO_ERROR` | 0 | 함수 호출이 성공 했습니다.  |
| `WBEM_S_NO_MORE_DATA` | 0x40005 | 열거형에 더 많은 속성이 있습니다. |
  
## <a name="remarks"></a>설명

이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::Next](https://msdn.microsoft.com/library/aa391453(v=vs.85).aspx) 메서드.

또한이 메서드는 시스템 속성을 반환 합니다.

속성의 내부 형식이 개체 경로, 날짜 또는 시간 또는 다른 특수 형식 인 경우 다음 반환 된 형식에 충분 한 정보 호출자에 게 검사 해야 하는 `CIMTYPE` 속성이 개체 참조, 날짜 또는 시간 또는 다른 특별 한 형식 인지 확인 하려면 지정 된 속성입니다.

경우 `plFlavor` 않습니다 `null`, `LONG` 값 속성의 원점에 대 한 정보를 다음과 같이 수신:

|상수  |값  |설명  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | 0x40 | 속성에는 표준 시스템 속성이입니다. |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | 0x20 | 클래스에 대 한:의 속성이 부모 클래스 로부터 상속 됩니다. </br> 인스턴스에 대 한: 속성을 부모 클래스에서 상속 하는 동안 수정 되지 않은 인스턴스가 있습니다.  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | 0 | 클래스에 대 한: 속성이 파생된 클래스에 속해 있습니다. </br> 인스턴스에 대 한: 인스턴스에서; 속성이 수정 되 즉, 값이 제공 된 또는 한정자가 추가 되거나 수정 되었습니다. |

## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** WMINet_Utils.idl  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고 항목  
[WMI 및 성능 카운터 (관리 되지 않는 API 참조)](index.md)
