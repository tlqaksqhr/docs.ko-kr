---
title: GetPropertyQualifierSet 함수 (관리 되지 않는 API 참조)
description: GetPropertyQualifierSet 함수 속성에 설정할 한정자를 검색 합니다.
ms.date: 11/06/2017
api_name:
- GetPropertyQualifierSet
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetPropertyQualifierSet
helpviewer_keywords:
- GetPropertyQualifierSet function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fcddca2e435a3f5bf4b8d083784613254d9801a4
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2018
ms.locfileid: "42935702"
---
# <a name="getpropertyqualifierset-function"></a>GetPropertyQualifierSet 함수
특정 속성에 대해 설정할 한정자를 검색 합니다.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>구문  
  
```  
HRESULT GetPropertyQualifierSet (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszProperty,
   [out] IWbemQualifierSet  **ppQualSet
); 
```  

## <a name="parameters"></a>매개 변수

`vFunc`  
[in] 이 매개 변수 사용 되지 않습니다.

`ptr`  
[in] 에 대 한 포인터를 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스.

`wszMethod`  
[in] 속성 이름입니다. `wszProperty` 유효한 가리켜야 `LPCWSTR`합니다. 

`ppQualSet`  
[out] 속성의 한정자에 대 한 액세스를 허용 하는 인터페이스 포인터를 받습니다. `ppQualSet`가 `null`이 될 수 없는 경우 오류가 발생 하는 경우 새 개체를 반환 되지 않으면 및 포인터를 가리키도록 설정 되어 `null`입니다. 

## <a name="return-value"></a>반환 값

이 함수에 의해 반환 되는 다음 값에 정의 된 합니다 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드:

|상수  |값  |설명  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | 일반 오류가 발생이 했습니다. |
| `WBEM_E_NOT_FOUND` | 0x80041002 | 지정된 된 메서드가 존재 하지 않습니다. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006(" | 메모리가 부족 하 여 작업을 완료할 수 없습니다. |
|`WBEM_E_INVALID_PARAMETER` | '(0x80041008 | 매개 변수는 `null`합니다. |
| `WBEM_E_SYSTEM_PROPERTY` | 0x80041030 | 함수는 시스템 속성의 한정자를 가져오려고 시도 합니다. |
|`WBEM_S_NO_ERROR` | 0 | 함수 호출이 성공 했습니다.  |
  
## <a name="remarks"></a>설명

이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::GetPropertyQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getpropertyqualifierset) 메서드. 

이 함수에 대 한 호출에는 현재 개체가 CIM 클래스 정의 하는 경우에 지원 됩니다. 사용할 수 없는 메서드 조작 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) CIM 인스턴스를 가리키는 ponters 합니다.

각 메서드는 자체 한정자가 있을 수 있으므로 합니다 [IWbemQualifierSet 포인터](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) 호출자가 추가, 편집 또는 이러한 한정자를 삭제할 수 있습니다.

함수를 반환 하는 시스템 속성 한정자가 있으므로 `WBEM_E_SYSTEM_PROPERTY` 가져오려고 시도 하는 경우는 [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) 시스템 속성에 대 한 포인터입니다.

## <a name="requirements"></a>요구 사항  
**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** WMINet_Utils.idl  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고자료  
[WMI 및 성능 카운터 (관리 되지 않는 API 참조)](index.md)
