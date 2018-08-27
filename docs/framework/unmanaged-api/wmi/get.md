---
title: Get 함수 (관리 되지 않는 API 참조)
description: Get 함수는 지정된 된 속성 값을 검색합니다.
ms.date: 11/06/2017
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
ms.openlocfilehash: cb7475623961fe2ee5fc821c5f237f0a2acfae1a
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2018
ms.locfileid: "42933335"
---
# <a name="get-function"></a>Get 함수
존재 하는 경우 지정된 된 속성 값을 검색 합니다.

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
[in] 이 매개 변수 사용 되지 않습니다.

`ptr`  
[in] 에 대 한 포인터를 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스.

`wszName`  
[in] 속성의 이름입니다.

`lFlags` [in] 예약 되어 있습니다. 이 매개 변수는 0 이어야 합니다.

`pVal` [out] 함수가 성공적으로 반환 하는 경우의 값이 포함 된 `wszName` 속성입니다. `pval` 인수는 올바른 형식 및 한정자의 값에 할당 됩니다.

`pvtType` [out] 함수가 성공적으로 반환 하는 경우 포함 된 [CIM 형식 상수](/windows/desktop/api/wbemcli/ne-wbemcli-tag_cimtype_enumeration) 속성 형식을 나타내는입니다. 해당 값을 수도 있습니다 `null`합니다. 

`plFlavor` [out] 함수가 성공적으로 반환 하는 경우 속성의 원본에 대 한 정보를 받습니다. 해당 값이 될 수 있습니다 `null`, 또는에 정의 된 다음 WBEM_FLAVOR_TYPE 상수 중 하나는 *WbemCli.h* 헤더 파일: 

|상수  |값  |설명  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | 0x40 | 속성에는 표준 시스템 속성이입니다. |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | 0x20 | 클래스: 속성은 부모 클래스에서 상속 됩니다. </br> 인스턴스에 대 한: 속성을 부모 클래스에서 상속 하는 동안 수정 되지 않은 인스턴스가 있습니다.  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | 0 | 클래스: 속성이 파생된 클래스에 속합니다. </br> 인스턴스에 대 한: 인스턴스에서; 속성이 수정 됩니다 즉, 값이 제공 된 또는 한정자를 추가 또는 수정 합니다. |

## <a name="return-value"></a>반환 값

이 함수에 의해 반환 되는 다음 값에 정의 된 합니다 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드:

|상수  |값  |설명  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | 일반 오류가 발생이 했습니다. |
|`WBEM_E_INVALID_PARAMETER` | '(0x80041008 | 하나 이상의 매개 변수가 올바르지 않습니다. |
|`WBEM_E_NOT_FOUND` | 0x80041002 | 지정된 된 속성을 찾을 수 없습니다. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006(" | 메모리가 부족 하 여 작업을 완료할 수 없습니다. |
|`WBEM_S_NO_ERROR` | 0 | 함수 호출이 성공 했습니다.  |
  
## <a name="remarks"></a>설명

이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-get) 메서드.

`Get` 함수 시스템 속성을 반환할 수도 있습니다.

합니다 `pVal` 인수는 올바른 형식 및 한정자 및 COM에 대 한 값에 할당 됩니다 [VariantInit](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-variantinit) 함수

## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** WMINet_Utils.idl  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고자료  
[WMI 및 성능 카운터 (관리 되지 않는 API 참조)](index.md)
