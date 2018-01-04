---
title: "Put 함수 (관리 되지 않는 API 참조)"
description: "Put 함수는 명명된 된 속성에 새 값을 할당합니다."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: Put
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: Put
helpviewer_keywords: Put function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 09d3edc74b34688d5cc36e688f634850cfb60910
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="put-function"></a>Put 함수
명명된 된 속성을 새 값으로 설정합니다.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>구문  
  
```  
HRESULT Put (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszName,
   [in] LONG              lFlags,
   [in] VARIANT*          pVal,
   [in] CIMTYPE           vtType
); 
```  

## <a name="parameters"></a>매개 변수

`vFunc`  
[in] 이 매개 변수를 사용 하지 않습니다.

`ptr`  
[in] 에 대 한 포인터는 [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) 인스턴스.

`wszName`  
[in] 속성의 이름입니다. 이 매개 변수 여야 `null`합니다.

`lFlags`  
[in] 예약 되어 있습니다. 이 매개 변수는 0 이어야 합니다.

`pVal`   
[in] 에 대 한 포인터를 올바른 `VARIANT` 하는 새 속성 값이 됩니다. 경우 `pVal` 은 `null` 가리키는 또는 `VARIANT` 형식의 `VT_NULL`는 속성이로 설정 된 `null`합니다. 

`vtType`  
[in] 유형의 `VARIANT` 가리키는 `pVal`합니다. 참조는 [주의](#remarks) 한 자세 합니다.
 

## <a name="return-value"></a>반환 값

이 함수에서 반환 되는 다음 값에 정의 된는 *WbemCli.h* 헤더 파일 또는 있습니다를 정의할 수 상수로 코드:

|상수  |값  |설명  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0 x 80041001 | 일반 오류가 발생이 했습니다. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | 하나 이상의 매개 변수가 올바르지 않습니다. |
|`WBEM_E_INVALID_PROPERTY_TYPE` | 0x8004102a | 속성 유형이 인식 되지 않습니다. 클래스가 이미 존재 하는 경우 클래스 인스턴스를 만들 때이 값이 반환 됩니다. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 작업을 완료 하려면 사용할 수 있는 메모리가 충분 하지 않습니다. |
| `WBEM_E_TYPE_MISMATCH` | 0x80041005가 | 에 대 한 인스턴스: 나타냅니다 `pVal` 가리키는 `VARIANT` 속성에 대 한 잘못 된 유형의 합니다. <br/> 클래스 정의 대 한: 속성이 부모 클래스에 이미 및 새 COM 형식을 이전 COM 종류와에서 다릅니다. |
|`WBEM_S_NO_ERROR` | 0 | 함수 호출이 성공 했습니다. |
  
## <a name="remarks"></a>설명

이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::Put](https://msdn.microsoft.com/library/aa391455(v=vs.85).aspx) 메서드.

이 함수는 새 항목으로는 현재 속성 값을 항상 덮어씁니다. 경우는 [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) 클래스 정의 가리키는 `Put` 만들거나 속성 값을 업데이트 합니다. 때 [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) CIM 인스턴스를 가리키는 `Put` 속성 값만 사용 합니다;이 업데이트 `Put` 속성 값을 만들 수 없습니다.

`__CLASS` 시스템 속성은 쓰기 가능한 클래스를 만드는 동안 때만 것 하지 비어 있을 수 있습니다. 다른 모든 시스템 속성은 읽기 전용입니다.

사용자는 밑줄 ("_")으로 시작 하거나 끝나서는 이름으로 속성을 만들 수 없습니다. 이 시스템 클래스 및 속성에 대해 예약 됩니다.

속성으로 설정 하는 경우는 `Put` 속성 형식은 부모 클래스 형식과 일치 하지 않는 하지 않는 한 속성의 기본값은 변경, 부모 클래스에 존재 합니다. 속성이 존재 하지 않는 경우 형식이 일치 하지 않습니다 속성이 ceated입니다.

사용 하 여는 `vtType` CIM 클래스 정의에서 새 속성을 만들 때에 매개 변수 및 `pVal` 은 `null` 가리키는 또는 `VARIANT` 형식의 `VT_NULL`합니다. 이 경우에 `vType` 매개 변수 속성의 CIM 형식을 지정 합니다. 다른 모든 경우에 `vtType` 0 이어야 합니다. `vtType`0 이어야 기본 개체 인스턴스 라면 (경우에 `Val` 은 `null`) 속성의 형식이 고정 되어 있고 변경할 수 없습니다.   

## <a name="example"></a>예

예를 들어 참조는 [IWbemClassObject::Put](https://msdn.microsoft.com/library/aa391455(v=vs.85).aspx) 메서드.

## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** WMINet_Utils.idl  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고 항목  
[WMI 및 성능 카운터 (관리 되지 않는 API 참조)](index.md)
