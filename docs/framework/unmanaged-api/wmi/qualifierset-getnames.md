---
title: "QualifierSet_GetNames 함수 (관리 되지 않는 API 참조)"
description: "QualifierSet_GetNames 함수 개체 또는 속성에서 한정자의 이름을 검색합니다."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- QualifierSet_GetNames
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_GetNames
helpviewer_keywords:
- QualifierSet_GetNames function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6077b448c2644f68d12679cf208ee921c2af119a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="qualifiersetgetnames-function"></a>QualifierSet_GetNames 함수
현재 개체 또는 속성에서 사용할 수 있는 특정 한정자 또는 모든 한정자의 이름을 검색 합니다. 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>구문  
  
```  
HRESULT QualifierSet_GetNames (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LONG                 lFlags,
   [out] SAFEARRAY (BSTR)**  pstrNames
); 
```  

## <a name="parameters"></a>매개 변수

`vFunc`   
[in] 이 매개 변수를 사용 하지 않습니다.

`ptr`   
[in] 에 대 한 포인터는 [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) 인스턴스.

`lFlags`   
[in] 다음 플래그 또는 열거형에 포함 하는 이름을 지정 하는 값 중 하나입니다.

|상수  |값  |설명  |
|---------|---------|---------|
|  | 0 | 모든 한정자의 이름을 반환 합니다. |
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | 현재 속성 또는 개체에 특정 한정자의 이름만 반환 합니다. <br/> 속성에 대 한: (재정의 포함), 속성에 특정 한정자만 반환 하 고 클래스 정의에서 이러한 한정자 하지 전파 합니다. <br/> 인스턴스에 대 한: 인스턴스별 한정자 이름만 반환 합니다. <br/> 클래스에 대 한: 파생 클래스 beiong 특정 한정자만 반환 합니다.
|`WBEM_FLAG_PROPAGATED_ONLY` | 0x20 | 반환이 한정자의 이름만 전파 다른 개체에서입니다. <br/> 속성에 대 한:에서 반환 한정자만 전파이 속성에는 클래스 정의 및 속성 자체에서 해당 하지 않습니다. <br/> 인스턴스에 대 한: 클래스 정의에서 이러한 한정자만 전파를 반환 합니다. <br/> 클래스에 대 한: 부모 클래스에서 상속 된 한정자 이름만 반환 합니다. |

`pstrNames`[out] 새 `SAFEARRAY` 요청한 이름이 들어 있는입니다. 배열의 요소를 가질 수 있습니다. 오류가 발생할 때, 새 `SAFEARRAY` 반환 되지 않습니다.

## <a name="return-value"></a>반환 값

이 함수에서 반환 되는 다음 값에 정의 된는 *WbemCli.h* 헤더 파일 또는 있습니다를 정의할 수 상수로 코드:

|상수  |값  |설명  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | 매개 변수가 올바르지 않습니다. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 새 열거형을 시작 하려면 사용할 수 있는 메모리가 충분 하지 않습니다. |
|`WBEM_S_NO_ERROR` | 0 | 함수 호출이 성공 했습니다.  |
  
## <a name="remarks"></a>설명

이 함수에 대 한 호출을 래핑하는 [IWbemQualifierSet::GetNames](https://msdn.microsoft.com/library/aa391868(v=vs.85).aspx) 메서드.

검색 한 후 한정자 이름, 액세스할 수 있습니다 각 한정자 이름으로 호출 하 여는 [QualifierSet_Get](qualifierset-get.md) 함수입니다. 

따라서 0 한정자가 지정된 된 개체에 대 한 오류가 아닙니다의 문자열 수 `pstrNames` 반환 두 일 수 있습니다, 함수 반환 하는 경우에 `WBEM_S_NO_ERROR`합니다.

## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** WMINet_Utils.idl  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고 항목  
[WMI 및 성능 카운터 (관리 되지 않는 API 참조)](index.md)
