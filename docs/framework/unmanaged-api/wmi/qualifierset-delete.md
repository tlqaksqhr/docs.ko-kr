---
title: QualifierSet_Delete 함수 (관리 되지 않는 API 참조)
description: QualifierSet_Delete 함수 이름별 한정자를 삭제합니다.
ms.date: 11/06/2017
api_name:
- QualifierSet_Delete
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Delete
helpviewer_keywords:
- QualifierSet_Delete function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7ca4cc9fb65d1a4bd8713f969bbda5551ce5a2e2
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2018
ms.locfileid: "42929784"
---
# <a name="qualifiersetdelete-function"></a>QualifierSet_Delete 함수
이름으로 지정된 된 한정자를 삭제합니다.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>구문  
  
```  
HRESULT QualifierSet_Delete (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LPCWSTR              wszName
); 
```  

## <a name="parameters"></a>매개 변수

`vFunc`  
[in] 이 매개 변수 사용 되지 않습니다.

`ptr`   
[in] 에 대 한 포인터를 [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) 인스턴스.

`wszName`   
[in] 삭제 하는 데 사용할 한정자의 이름입니다.

## <a name="return-value"></a>반환 값

이 함수에 의해 반환 되는 다음 값에 정의 된 합니다 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드:

|상수  |값  |설명  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | '(0x80041008 | `wszName` 매개 변수가 올바르지 않습니다. |
|`WBEM_E_INVALID_OPERATION` | 0x80041016 | 이 한정자를 삭제 하는 중 잘못 되었습니다. |
|`WBEM_E_NOT_FOUND` | 0x80041002 | 지정된 된 한정자를 찾을 수 없습니다. |
|`WBEM_S_NO_ERROR` | 0 | 함수 호출이 성공 했습니다.  |
| `WBEM_S_RESET_TO_DEFAULT` | 0x40002 | 로컬 재정의 삭제 하 고 부모 개체의 원래 한정자가 범위를 다시 시작 합니다. |

## <a name="remarks"></a>설명

이 함수에 대 한 호출을 래핑하는 [IWbemQualifierSet::Delete](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-delete) 메서드.

한정자 전파 규칙으로 인해 특정 한정자 수 다른 개체 로부터 상속 되었으며 단순히 인스턴스를 현재 클래스에서 재정의 된 합니다. 이 경우에 `QualifierSet_Delete` 메서드 다시 원래 상속 된 값으로 한정자를 설정 합니다. 함수에는 경우 상태 코드를 반환 합니다 `WBEM_S_RESET_TO_DEFAULT`합니다.

## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** WMINet_Utils.idl  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고자료  
[WMI 및 성능 카운터 (관리 되지 않는 API 참조)](index.md)
