---
title: "Get 함수 (관리 되지 않는 API 참조)"
description: "Get 함수는 지정된 된 속성 값을 검색합니다."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- Get
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Get
helpviewer_keywords:
- Get function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 69312030689ab1b87e3aadd040395f06e1c94ac8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="get-function"></a>Get 함수
있는 경우 지정된 된 속성 값을 검색 합니다.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>구문  
  
```  
HRESULT Get (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszName,
   [in] LONG              lFlags,
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

`wszName`  
[in] 속성의 이름입니다.

`lFlags`[in] 예약 되어 있습니다. 이 매개 변수는 0 이어야 합니다.

`pVal`[out] 값을 포함 하는 함수가 성공적으로 반환 하는 경우는 `wszName` 속성입니다. `pval` 인수는 올바른 형식 및 한정자의 값을 할당 됩니다.

`pvtType`[out] 함수가 성공적으로 반환 하는 경우를 포함 한 [CIM 형식 상수](https://msdn.microsoft.com/library/aa386309(v=vs.85).aspx) 속성 형식을 나타내는입니다. 해당 값 또한 수 `null`합니다. 

`plFlavor`[out] 함수가 성공적으로 반환 하는 경우에 속성의 원점에 대 한 정보를 받습니다. 해당 값으로 가능 `null`, 또는에 정의 된 다음 WBEM_FLAVOR_TYPE 상수 중 하나는 *WbemCli.h* 헤더 파일: 

|상수  |값  |설명  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | 0x40 | 속성에는 표준 시스템 속성이입니다. |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | 0x20 | 클래스에 대 한:의 속성이 부모 클래스 로부터 상속 됩니다. </br> 인스턴스에 대 한: 속성을 부모 클래스에서 상속 하는 동안 수정 되지 않은 인스턴스가 있습니다.  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | 0 | 클래스에 대 한: 속성이 파생된 클래스에 속해 있습니다. </br> 인스턴스에 대 한: 인스턴스에서; 속성이 수정 되 즉, 값이 제공 된 또는 한정자가 추가 되거나 수정 되었습니다. |

## <a name="return-value"></a>반환 값

이 함수에서 반환 되는 다음 값에 정의 된는 *WbemCli.h* 헤더 파일 또는 있습니다를 정의할 수 상수로 코드:

|상수  |값  |설명  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0 x 80041001 | 일반 오류가 발생이 했습니다. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | 하나 이상의 매개 변수가 올바르지 않습니다. |
|`WBEM_E_NOT_FOUND` | 0x80041002 | 지정된 된 속성을 찾을 수 없습니다. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 작업을 완료 하려면 사용할 수 있는 메모리가 충분 하지 않습니다. |
|`WBEM_S_NO_ERROR` | 0 | 함수 호출이 성공 했습니다.  |
  
## <a name="remarks"></a>설명

이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::Get](https://msdn.microsoft.com/library/aa391442(v=vs.85).aspx) 메서드.

`Get` 함수 시스템 속성을 반환할 수도 있습니다.

`pVal` 올바른 형식 및 값 한정자 및 COM에 대 한 인수는 할당 [VariantInit](https://msdn.microsoft.com/library/ms221402(v=vs.85).aspx) 함수

## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** WMINet_Utils.idl  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고 항목  
[WMI 및 성능 카운터 (관리 되지 않는 API 참조)](index.md)
