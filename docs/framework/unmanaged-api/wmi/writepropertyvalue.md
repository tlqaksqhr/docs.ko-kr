---
title: "WritePropertyValue 함수 (관리 되지 않는 API 참조)"
description: "WritePropertyValue 함수 속성에 바이트를 씁니다."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: WritePropertyValue
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: WritePropertyValue
helpviewer_keywords: WritePropertyValue function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 26337a13ab9840b79c253d4af2d84a10e70877c5
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2017
---
# <a name="writepropertyvalue-function"></a>WritePropertyValue 함수
속성 핸들에 의해 식별 된 속성에 지정된 된 수의 바이트를 씁니다.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>구문  
  
```  
HRESULT WritePropertyValue (
   [in] int                  vFunc, 
   [in] IWbemObjectAccess*   ptr, 
   [in] long                 lHandle,
   [in] long                 lNumBytes,
   [in] byte*                aData
); 
```  

## <a name="parameters"></a>매개 변수

`vFunc`  
[in] 이 매개 변수를 사용 하지 않습니다.

`ptr`  
[in] 에 대 한 포인터는 [IWbemObjectAccess](https://msdn.microsoft.com/library/aa391770(v=vs.85).aspx) 인스턴스.

`lHandle`  
[in] 이 속성을 식별 하는 핸들을 포함 하는 정수입니다. 호출 하 여 핸들을 검색할 수 있습니다는 [GetPropertyHandle](getpropertyhandle.md) 함수입니다.   

`lNumBytes`  
[in] 속성에 기록 되는 바이트 수입니다. 참조는 [주의](#remarks) 한 자세 합니다.

`pHandle`   
[out] 데이터를 포함 하는 바이트 배열에 대 한 포인터입니다.

## <a name="return-value"></a>반환 값

이 함수에서 반환 되는 다음 값에 정의 된는 *WbemCli.h* 헤더 파일 또는 있습니다를 정의할 수 상수로 코드:

|상수  |값  |설명  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | 매개 변수가 올바르지 않습니다. |
|`WBEM_E_TYPE_MISMATCH` | 0x80041005가 | 형식 불일치가 발생 했습니다. |
|`WBEM_S_NO_ERROR` | 0 | 함수 호출이 성공 했습니다.  |
  
## <a name="remarks"></a>설명

이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::WritePropertyValue](https://msdn.microsoft.com/library/aa391783(v=vs.85).aspx) 메서드.

이 함수를 사용 하 여 문자열 및 모든 다른 비를 설정 하려면`DWORD` 또는 비-`QWORD` 데이터입니다.

문자열이 아닌 속성 값에 대 한 `lNumBytes` 올바른 데이터 크기의 지정 된 속성 형식 이어야 합니다. 문자열 속성 값에 대 한 `lNumBytes` 길이 여야 합니다 (바이트)를 지정된 된 문자열 및 문자열도 길이 (바이트) 이어야 합니다 자체 및이 null 종결 문자와 함께 표시 되어야 합니다.

## <a name="requirements"></a>요구 사항  
**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** WMINet_Utils.idl  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고 항목  
[WMI 및 성능 카운터 (관리 되지 않는 API 참조)](index.md)
