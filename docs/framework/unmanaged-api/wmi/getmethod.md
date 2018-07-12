---
title: GetMethod 함수 (관리 되지 않는 API 참조)
description: GetMethod 함수는 메서드에 대 한 정보를 검색합니다.
ms.date: 11/06/2017
api_name:
- GetMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetMethod
helpviewer_keywords:
- GetMethod function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 65b8cb74a028892a3494e818f2b523f75e8766a1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33460449"
---
# <a name="getmethod-function"></a>GetMethod 함수
지정 된 메서드에 대 한 정보를 검색합니다.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>구문  
  
```  
HRESULT GetMethod (
   [in] int                vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszName,
   [in] LONG                lFlags,
   [out] IWbemClassObject** ppInSignature,
   [out] IWbemClassObject** ppOutSignature
); 
```  

## <a name="parameters"></a>매개 변수

`vFunc`  
[in] 이 매개 변수를 사용 하지 않습니다.

`ptr`  
[in] 에 대 한 포인터는 [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) 인스턴스.

`wszName`  
[in] 메서드 이름입니다. 이 매개 변수 여야 `null` 유효한를 가리켜야 `LPCWSTR`합니다.

`lFlags`  
[in] 예약 되어 있습니다. 이 매개 변수는 0 이어야 합니다.

`ppInSignature`   
[out] 주소에 대 한 포인터는 [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) 메서드에 paramteers 나타내는 인스턴스. 이 매개 변수는로 설정 되어 있으면 `null`합니다. 

`ppOutSignature`  
[out] 주소에 대 한 포인터는 [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) 메서드에 out 매개 변수를 나타내는 인스턴스. 이 매개 변수는로 설정 되어 있으면 `null`합니다. 

## <a name="return-value"></a>반환 값

이 함수에서 반환 되는 다음 값에 정의 된는 *WbemCli.h* 헤더 파일 또는 있습니다를 정의할 수 상수로 코드:

|상수  |값  |설명  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | 0x80041002 | 지정된 된 속성을 찾을 수 없습니다. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 작업을 완료 하려면 사용할 수 있는 메모리가 충분 하지 않습니다. |
|`WBEM_S_NO_ERROR` | 0 | 함수 호출이 성공 했습니다.  |
  
## <a name="remarks"></a>설명

이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::GetMethod](https://msdn.microsoft.com/library/aa391443(v=vs.85).aspx) 메서드.

Windows 관리에서 설정할 수는 [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) 에 대 한 포인터 `null` 메서드 매개 변수가 없는 경우에 합니다.

`ppInSignature` 및 `ppOutSignature` in 및 out 매개 변수를 각각 속성에 설명 된 `IWbemClassObject` 시스템 클래스의 인스턴스 [_Parameters](https://msdn.microsoft.com/library/aa394667(v=vs.85).aspx)합니다. 속성에 `ppInsignature` 이름이 지정 된 **Param * * * n*여기서 *n* 메서드 시그니처의 매개 변수의 위치입니다 (같은 `Param1`, `Param2`등.). 속성에 `ppOutSignature` 라고도 **Param * * * n*, 반환 값은 이름이 고 **ReturnValue**합니다. 자세한 내용 및 예제에 대 한 참조 [IWbemClassObject::GetMethod 메서드](https://msdn.microsoft.com/library/aa391443(v=vs.85).aspx)합니다.

## <a name="requirements"></a>요구 사항  
**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** WMINet_Utils.idl  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고자료  
[WMI 및 성능 카운터 (관리 되지 않는 API 참조)](index.md)
