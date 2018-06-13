---
title: NextMethod 함수 (관리 되지 않는 API 참조)
description: NextMethod 함수 열거형의 다음 메서드를 검색합니다.
ms.date: 11/06/2017
api_name:
- NextMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- NextMethod
helpviewer_keywords:
- NextMethod function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cd4559663194cb845fb0cc040e1f6739e38caa0e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33461145"
---
# <a name="nextmethod-function"></a>NextMethod 함수
에 대 한 호출으로 시작 하는 열거형의 다음 메서드를 검색 [BeginMethodEnumeration](beginmethodenumeration.md)합니다.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>구문  
  
```  
HRESULT NextMethod (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LONG                lFlags,
   [out] BSTR*              pName,
   [out] IWbemClassObject** ppInSignature,
   [out] IWbemClassObject** ppOutSignature   
); 
```  

## <a name="parameters"></a>매개 변수

`vFunc`  
[in] 이 매개 변수를 사용 하지 않습니다.

`ptr`  
[in] 에 대 한 포인터는 [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) 인스턴스.

`lFlags`  
[in] 예약 되어 있습니다. 이 매개 변수는 0 이어야 합니다.

`pName`  
[out] 가리키는 포인터가 `null` 호출 하기 전에. 함수가 반환 하는 경우, 새 주소 `BSTR` 메서드 이름이 들어 있는입니다. 

`ppSignatureIn`  
[out] 에 대 한 포인터를 받는 포인터는 [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) 를 포함 하는 `in` 메서드의 매개 변수입니다. 

`ppSignatureOut`  
[out] 에 대 한 포인터를 받는 포인터는 [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) 를 포함 하는 `out` 메서드의 매개 변수입니다. 

## <a name="return-value"></a>반환 값

이 함수에서 반환 되는 다음 값에 정의 된는 *WbemCli.h* 헤더 파일 또는 있습니다를 정의할 수 상수로 코드:

|상수  |값  |설명  |
|---------|---------|---------|
| `WBEM_E_UNEXPECTED` | 0x8004101d | 에 대 한 호출이 했습니다는 [ `BeginEnumeration` ](beginenumeration.md) 함수입니다. |
| `WBEM_S_NO_ERROR` | 0 | 함수 호출이 성공 했습니다.  |
| `WBEM_S_NO_MORE_DATA` | 0x40005 | 열거형에 더 많은 속성이 있습니다. |
  
## <a name="remarks"></a>설명

이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::NextMethod](https://msdn.microsoft.com/library/aa391454(v=vs.85).aspx) 메서드.

호출 하 여 열거형 시퀀스를 시작 하는 호출자에 게는 [BeginMethodEnumeration](beginmethodenumeration.md) 함수 및 함수 반환 될 때까지 다음 [NextMethod] 함수를 호출 `WBEM_S_NO_MORE_DATA`합니다. 호출자가 호출 하 여 시퀀스를 완료 하는 필요에 따라 [EndMethodEnumeration](endmethodenumeration.md)합니다. 호출자에 게 해지할 수 있습니다 열거형 초기 호출 하 여 [EndMethodEnumeration](endmethodenumeration.md) 언제 든 지 합니다.

## <a name="example"></a>예제

C + + 예제에 대 한 참조는 [IWbemClassObject::NextMethod](https://msdn.microsoft.com/library/aa391454(v=vs.85).aspx) 메서드.

## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** WMINet_Utils.idl  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고자료  
[WMI 및 성능 카운터 (관리 되지 않는 API 참조)](index.md)
