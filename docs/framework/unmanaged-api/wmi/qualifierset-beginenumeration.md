---
title: QualifierSet_BeginEnumeration 함수 (관리 되지 않는 API 참조)
description: QualifierSet_BeginEnumeration 함수 개체의 한정자의 열거자를 다시 설정합니다.
ms.date: 11/06/2017
api_name:
- QualifierSet_BeginEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_BeginEnumeration
helpviewer_keywords:
- QualifierSet_BeginEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1fac897f743ca452c38282143cdf822b682df1df
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="qualifiersetbeginenumeration-function"></a>QualifierSet_BeginEnumeration 함수
열거형의 시작 부분에 있는 개체의 한정자의 열거자를 다시 설정합니다.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>구문  
  
```  
HRESULT QualifierSet_BeginEnumeration (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LONG                 lFlags
); 
```  

## <a name="parameters"></a>매개 변수

`vFunc`   
[in] 이 매개 변수를 사용 하지 않습니다.

`ptr`   
[in] 에 대 한 포인터는 [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) 인스턴스.

`lFlags`   
[in] 플래그 또는에 설명 된 값의 비트 조합은 [주의](#remarks) 열거형에 포함 하려면 한정자를 지정 하는 섹션이 있습니다.

## <a name="return-value"></a>반환 값

이 함수에서 반환 되는 다음 값에 정의 된는 *WbemCli.h* 헤더 파일 또는 있습니다를 정의할 수 상수로 코드:

|상수  |값  |설명  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | `lFlags` 매개 변수가 올바르지 않습니다. |
|`WBEM_E_UNEXPECTED` | 0x8004101d | 두 번째 호출으로 `QualifierSet_BeginEnumeration` 에 대 한 중간 호출 없이 만들어진 [ `QualifierSet_EndEnumeration` ](qualifierset-endenumeration.md)합니다. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 새 열거형을 시작 하려면 사용할 수 있는 메모리가 충분 하지 않습니다. |
|`WBEM_S_NO_ERROR` | 0 | 함수 호출이 성공 했습니다.  |
  
## <a name="remarks"></a>설명

이 함수에 대 한 호출을 래핑하는 [IWbemQualifierSet::BeginEnumeration](https://msdn.microsoft.com/library/aa391861(v=vs.85).aspx) 메서드.

모든 개체에는 한정자를 열거 하려면이 메서드를 처음 호출 하기 전에 호출 해야 [QualifierSet_Next](qualifierset-next.md)합니다. 한정자는 열거 순서를 지정 된 열거형에 대해 보장 됩니다.

로 전달 될 수 있는 플래그는 `lEnumFlags` 에 정의 된 인수는 *WbemCli.h* 헤더 파일 또는 있습니다를 정의할 수 상수로 코드입니다.   

|상수  |값  |설명  |
|---------|---------|---------|
|  | 0 | 모든 한정자의 이름을 반환 합니다. |
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | 현재 속성 또는 개체에 특정 한정자의 이름만 반환 합니다. <br/> 속성에 대 한: (재정의 포함), 속성에 특정 한정자만 반환 하 고 클래스 정의에서 이러한 한정자 하지 전파 합니다. <br/> 인스턴스에 대 한: 인스턴스별 한정자 이름만 반환 합니다. <br/> 클래스에 대 한: 파생 클래스 beiong 특정 한정자만 반환 합니다.
|`WBEM_FLAG_PROPAGATED_ONLY` | 0x20 | 반환이 한정자의 이름만 전파 다른 개체에서입니다. <br/> 속성에 대 한:에서 반환 한정자만 전파이 속성에는 클래스 정의 및 속성 자체에서 해당 하지 않습니다. <br/> 인스턴스에 대 한: 클래스 정의에서 이러한 한정자만 전파를 반환 합니다. <br/> 클래스에 대 한: 부모 클래스에서 상속 된 한정자 이름만 반환 합니다. |

## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** WMINet_Utils.idl  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고자료  
[WMI 및 성능 카운터 (관리 되지 않는 API 참조)](index.md)
