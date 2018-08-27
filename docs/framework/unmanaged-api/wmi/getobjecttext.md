---
title: GetObjectText 함수 (관리 되지 않는 API 참조)
description: GetObjectText 함수 MOF 구문에서 개체의 텍스트 렌더링을 반환 합니다.
ms.date: 11/06/2017
api_name:
- GetObjectText
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetObjectText
helpviewer_keywords:
- GetObjectText function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 24ba4b37cc8221df4e018d172996c0910ec07f7d
ms.sourcegitcommit: a1e35d4e94edab384a63406c0a5438306873031b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2018
ms.locfileid: "42754458"
---
# <a name="getobjecttext-function"></a>GetObjectText 함수
관리 되는 개체 형식 (MOF) 구문에서 개체의 텍스트 렌더링을 반환합니다.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>구문  
  
```  
HRESULT GetObjectText (
   [in] int                vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LONG                lFlags,
   [out] BSTR*              pstrObjectText
); 
```  

## <a name="parameters"></a>매개 변수

`vFunc`  
[in] 이 매개 변수 사용 되지 않습니다.

`ptr`  
[in] 에 대 한 포인터를 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스.

`lFlags`  
[in] 일반적으로 0입니다. 경우 `WBEM_FLAG_NO_FLAVORS` (또는 0x1)를 지정 하면 한정자가 전파 하거나 버전 정보 없이 포함 됩니다.

`pstrObjectText`   
[out] 에 대 한 포인터를 `null` 항목입니다. 반환 시 새로 할당 된 `BSTR` 포함 하는 개체의 MOF 구문 렌더링 합니다.  

## <a name="return-value"></a>반환 값

이 함수에 의해 반환 되는 다음 값에 정의 된 합니다 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드:

|상수  |값  |설명  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | 일반 오류가 발생이 했습니다. |
|`WBEM_E_INVALID_PARAMETER` | '(0x80041008 | 매개 변수가 잘못 되었습니다. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006(" | 메모리가 부족 하 여 작업을 완료할 수 없습니다. |
|`WBEM_S_NO_ERROR` | 0 | 함수 호출이 성공 했습니다.  |
  
## <a name="remarks"></a>설명

이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::GetObjectText](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getobjecttext) 메서드.

개체에 대 한 모든 정보 하지만 원래 개체를 다시 만들 수 있게 되기를 MOF 컴파일러에 대 한 충분 한 정보만 반환 하는 MOF 텍스트를 포함 하지 않습니다. 예를 들어, 부모 클래스 속성 없거나 전파 된 한정자가 포함 됩니다.

다음 알고리즘을 메서드의 매개 변수와의 텍스트를 다시 만드는 데 사용 됩니다.

1. 매개 변수는 해당 식별자 값 순서 대로 resequenced 됩니다.
1. 으로 지정 된 매개 변수 `[in]` 고 `[out]` 단일 매개 변수를 결합 됩니다.
 
`pstrObjectText` 에 대 한 포인터 여야 합니다는 `null` 함수를 호출할 때는 하지 포인터를 취소할 수 없습니다 때문에 메서드 호출 하기 전에 잘못 된 문자열을 가리키도록 해야 합니다.

## <a name="requirements"></a>요구 사항  
**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** WMINet_Utils.idl  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고자료  
[WMI 및 성능 카운터 (관리 되지 않는 API 참조)](index.md)
