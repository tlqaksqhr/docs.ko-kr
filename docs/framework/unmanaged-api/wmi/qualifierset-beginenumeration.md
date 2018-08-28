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
ms.openlocfilehash: 2d20701237501834c611c4e498c39597cf275176
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/27/2018
ms.locfileid: "43001465"
---
# <a name="qualifiersetbeginenumeration-function"></a>QualifierSet_BeginEnumeration 함수
열거형의 시작 부분에는 열거자 개체의 한정자를 다시 설정합니다.  

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
[in] 이 매개 변수 사용 되지 않습니다.

`ptr`   
[in] 에 대 한 포인터를 [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) 인스턴스.

`lFlags`   
[in] 플래그를 설명 하는 값의 비트 조합 합니다 [주의](#remarks) 열거형에 포함 하려면 한정자를 지정 하는 섹션입니다.

## <a name="return-value"></a>반환 값

이 함수에 의해 반환 되는 다음 값에 정의 된 합니다 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드:

|상수  |값  |설명  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | '(0x80041008 | `lFlags` 매개 변수가 올바르지 않습니다. |
|`WBEM_E_UNEXPECTED` | 0x8004101d | 두 번째 호출 `QualifierSet_BeginEnumeration` 에 대 한 중간 호출 없이 만들어진 [ `QualifierSet_EndEnumeration` ](qualifierset-endenumeration.md)합니다. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006(" | 새 열거형 시작에 사용할 있는 메모리가 충분 하지 않습니다. |
|`WBEM_S_NO_ERROR` | 0 | 함수 호출이 성공 했습니다.  |
  
## <a name="remarks"></a>설명

이 함수에 대 한 호출을 래핑하는 [IWbemQualifierSet::BeginEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-beginenumeration) 메서드.

모든 개체에 한정자를 열거 하려면이 메서드를 처음 호출 하기 전에 호출 해야 [QualifierSet_Next](qualifierset-next.md)합니다. 한정자를 열거 하는 순서를 지정 된 열거형에 대 한 변형 보장 됩니다.

로 전달 될 수 있는 플래그는 `lEnumFlags` 인수에 정의 된 합니다 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드.   

|상수  |값  |설명  |
|---------|---------|---------|
|  | 0 | 모든 한정자의 이름을 반환 합니다. |
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | 현재 속성 또는 개체에 특정 한정자의 이름만 반환 합니다. <br/> 속성: (재정의 포함), 속성에 특정 한정자만를 반환 하 고 클래스 정의에서 이러한 한정자가 없습니다 전파 합니다. <br/> 인스턴스에 대 한: 인스턴스별 한정자 이름만 반환 합니다. <br/> 클래스: 파생 된 클래스 beiong 특정 한정자만 반환 합니다.
|`WBEM_FLAG_PROPAGATED_ONLY` | 0x20 | 반환이 한정자의 이름에만 전파 다른 개체에서입니다. <br/> 속성: 한정자만 전파이 속성에서 반환 클래스 정의와 속성 자체에서 해당 되지 않습니다. <br/> 인스턴스에 대 한: 클래스 정의에서 이러한 한정자만 전파를 반환 합니다. <br/> 클래스: 부모 클래스에서 상속 한정자 이름만 반환 합니다. |

## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** WMINet_Utils.idl  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고자료  
[WMI 및 성능 카운터 (관리 되지 않는 API 참조)](index.md)
