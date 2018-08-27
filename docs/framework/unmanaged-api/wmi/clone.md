---
title: 복제 함수 (관리 되지 않는 API 참조)
description: 복제 함수는 현재 전체 복제본 인 새 개체를 반환 합니다.
ms.date: 11/06/2017
api_name:
- Clone
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Clone
helpviewer_keywords:
- Clone function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5cd87cb619ef2dc1e0548c7553585b7e51e94c4f
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/25/2018
ms.locfileid: "42924777"
---
# <a name="clone-function"></a>복제 함수
현재 개체의 전체 복제본 인 새 개체를 반환 합니다.   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>구문  
  
```  
HRESULT Clone (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [out] IWbemClassObject**  ppCopy
); 
```  

## <a name="parameters"></a>매개 변수

`vFunc`  
[in] 이 매개 변수 사용 되지 않습니다.

`ptr`  
[in] 에 대 한 포인터를 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 인스턴스.

`ppCopy`  
[out] 완료 된 새 개체의 유일한 `ptr`합니다. 두이 일 수 없습니다 `null` 현재 개체의 복사본을 수신 하는 경우.

## <a name="return-value"></a>반환 값

이 함수에 의해 반환 되는 다음 값에 정의 된 합니다 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드:

|상수  |값  |설명  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | 일반 오류가 발생이 했습니다. |
| `WBEM_E_INVALID_PARAMETER` | '(0x80041008 | `null` 매개 변수로 지정 된이 사용이 적합 하지 않습니다. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006(" | 개체를 복제에 사용할 있는 메모리가 충분 하지 않습니다. |
| `WBEM_S_NO_ERROR` | 0 | 함수 호출이 성공 했습니다.  |
  
## <a name="remarks"></a>설명

이 함수에 대 한 호출을 래핑하는 [IWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) 메서드.

복제 된 개체는는 COM 개체에는 참조 횟수가 1입니다.

## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** WMINet_Utils.idl  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고자료  
[WMI 및 성능 카운터 (관리 되지 않는 API 참조)](index.md)
