---
title: PutClassWmi 함수 (관리 되지 않는 API 참조)
description: PutClassWmi 함수 새 클래스를 만들거나 기존 계정을 업데이트 합니다.
ms.date: 11/06/2017
api_name:
- PutClassWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- PutClassWmi
helpviewer_keywords:
- PutClassWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: de08662a825a84f19a40863cf73481d89364ebd0
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2018
ms.locfileid: "42930507"
---
# <a name="putclasswmi-function"></a>PutClassWmi 함수
새 클래스를 만들거나 기존 계정을 업데이트 합니다.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>구문  
  
```  
HRESULT PutClassWmi (
   [in] IWbemClassObject*    pObject,
   [in] long                 lFlags,
   [in] IWbemContext*        pCtx,
   [out] IWbemCallResult**   ppCallResult
); 
```  

## <a name="parameters"></a>매개 변수

`pObject`    
[in] 올바른 클래스 정의에 대 한 포인터입니다. 모든 필수 속성 값을 사용 하 여 올바르게 초기화 해야 합니다.

`lFlags`   
[in] 이 함수의 동작에 영향을 주는 플래그의 조합입니다. 에 정의 된 다음 값을 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드: 

|상수  |값  |설명  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | 0x20000 | 경우 설정, WMI는 수정 된 버전을 사용 하 여 모든 한정자를 저장 하지 않습니다. </br> 집합 가정는이 개체에 지역화 되지 않으면 모든 한정자는 storedwith 그렇지 않은 경우이 인스턴스. |
| `WBEM_FLAG_CREATE_OR_UPDATE` | 0 | 존재 하거나 이미 있으면 덮어 쓸까요 하지 않는 경우에 클래스를 만듭니다. |
| `WBEM_FLAG_UPDATE_ONLY` | 1 | 클래스를 업데이트 합니다. 클래스는 성공에 대 한 호출에 대 한 존재 해야 합니다. |
| `WBEM_FLAG_CREATE_ONLY` | 2 | 클래스를 만듭니다. 클래스가 이미 존재 하는 경우 호출은 실패 합니다. |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | 0x10 | 플래그를 사용 하면 일부 동기 호출입니다. |
| `WBEM_FLAG_OWNER_UPDATE` | 0x10000 | 푸시 공급자를 호출할 때이 플래그를 지정 해야 `PutClassWmi` 나타내려면이 클래스가 변경 되었습니다. |
| `WBEM_FLAG_UPDATE_COMPATIBLE` | 0 | 클래스를 없는 파생 된 클래스와 해당 클래스의 인스턴스가 없는 경우 업데이트할 수 있습니다. 또한 변경 되는 경우 설명 한정자와 같은 중요 하지 않은 한정자를 모든 경우에 업데이트를 허용 합니다. 클래스에는 인스턴스 또는 중요 한 한정자는 변경 하는 경우 업데이트가 실패 합니다. |
| `WBEM_FLAG_UPDATE_SAFE_MODE` | 0x20 | 자식 클래스를 가지으로 자식 클래스를 사용 하 여 변경 충돌이 발생 하지 않습니다 하는 경우에 클래스의 업데이트를 허용 합니다. 예를 들어,이 플래그는 자식 클래스 중 하나에서 이전에 언급 되지 않은 기본 클래스에 추가 하는 새 속성이 있습니다. 클래스의 인스턴스가 업데이트가 실패 합니다. |
| `WBEM_FLAG_UPDATE_FORCE_MODE` | 0x40 | 충돌 하는 자식 클래스는 존재할 때 클래스의 업데이트를 강제로 수행 합니다. 예를 들어, 클래스 한정자는 자식 클래스에 정의 되어 있으며 기본 클래스 하나를 기존 thte와 충돌 하는 동일한 한정자를 추가 하려고 하는 경우이 플래그 강제로 업데이트 합니다. 강제 모드에서 자식 클래스에 충돌 하는 한정자를 삭제 하 여이 충돌이 해결 됩니다. |

`pCtx`  
[in] 이 값은 일반적으로 `null`입니다. 그렇지 않을 경우에 대 한 포인터를 [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) 요청 된 클래스를 제공 하는 공급자가 사용할 수 있는 인스턴스. 

`ppCallResult`  
[out] 경우 `null`,이 매개 변수 사용 되지 않습니다. 하는 경우 `lFlags` 포함 `WBEM_FLAG_RETURN_IMMEDIATELY`, 함수에서 사용 하 여 즉시 반환 `WBEM_S_NO_ERROR`합니다. 합니다 `ppCallResult` 매개 변수는 새 포인터를 받습니다 [IWbemCallResult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult) 개체입니다.

## <a name="return-value"></a>반환 값

이 함수에 의해 반환 되는 다음 값에 정의 된 합니다 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드:

|상수  |값  |설명  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | 0x80041003 | 사용자를 만들거나 클래스를 수정할 수 있는 권한이 없습니다. |
| `WBEM_E_FAILED` | 0x80041001 | 지정 되지 않은 오류가 발생 했습니다. |
| `WBEM_E_INVALID_CLASS` | 0x80041010 | 지정 된 클래스가 올바르지 않습니다. 일반적으로이 나타내는 `pObject` 인스턴스 개체를 지정 합니다. |
| `WBEM_E_INVALID_PARAMETER` | '(0x80041008 | 매개 변수가 잘못 되었습니다. |
| `WBEM_E_INVALID OPERATION` | 0x80041016 | 지정 된 클래스 이름이 잘못 되었습니다. |
| `WBEM_E_CLASS_HAS_CHILDREN` | 0x80041025 | 서브 클래스를 무효화 하는 변경 하려고 했습니다. |
| `WBEM_E_ALREADY_EXISTS` | 0x80041019 | `WBEM_FLAG_CREATE_ONLY` 플래그를 지정 하지만 클래스가 이미 존재 합니다. |
| `WBEM_E_NOT_FOUND` | 0x80041002 | `WBEM_FLAG_UPDATE_ONLY` 에 지정 된 `lFlags`, 클래스를 찾을 수 없습니다. |
| `WBEM_E_INCOMPLETE_CLASS` | 0x80041020 | 클래스에 대 한 필수 속성이 모두 설정 되었습니다. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006(" | 메모리가 부족 하 여 작업을 완료할 수 없습니다. |
| `WBEM_E_SHUTTING_DOWN` | 0x80041033 | WMI는 아마도 중지 및 다시 시작 했습니다. 호출 [ConnectServerWmi](connectserverwmi.md) 다시 합니다. |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | 현재 프로세스와 WMI 원격 프로시저 호출 (RPC) 연결 하지 못했습니다. |
| `WBEM_S_NO_ERROR` | 0 | 함수 호출이 성공 했습니다.  |
  
## <a name="remarks"></a>설명

이 함수에 대 한 호출을 래핑하는 [IWbemServices::PutClass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putclass) 메서드.

사용자 클래스는 밑줄 chacater로 시작 하거나 끝날 수 있는 이름으로 만들 수 없습니다.

함수 호출에 실패 하는 경우 호출 하 여 추가 오류 정보를 얻을 수 있습니다 합니다 [GetErrorInfo](geterrorinfo.md) 함수입니다.

## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** WMINet_Utils.idl  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고자료  
[WMI 및 성능 카운터 (관리 되지 않는 API 참조)](index.md)
