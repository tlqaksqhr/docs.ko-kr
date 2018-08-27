---
title: ExecNotificationQueryWmi 함수 (관리 되지 않는 API 참조)
description: ExecNotificationQueryWmi 함수 이벤트를 수신 하는 쿼리를 실행 합니다.
ms.date: 11/06/2017
api_name:
- ExecNotificationQueryWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- ExecNotificationQueryWmi
helpviewer_keywords:
- ExecNotificationQueryWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d314d85e7c1297636e8dd5cecaf050a527151518
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2018
ms.locfileid: "42932801"
---
# <a name="execnotificationquerywmi-function"></a>ExecNotificationQueryWmi 함수
이벤트를 수신 하는 쿼리를 실행 합니다. 호출이 즉시 반환 하 고 호출자에 게 도착 했을 때 반환 된 이벤트에 대 한 열거자를 폴링할 수 있습니다. 쿼리를 취소 반환 된 열거자를 해제 합니다.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>구문  
  
```  
HRESULT ExecNotificationQueryWmi (
   [in] BSTR                    strQueryLanguage,
   [in] BSTR                    strQuery,
   [in] long                    lFlags,
   [in] IWbemContext*           pCtx,
   [out] IEnumWbemClassObject** ppEnum,
   [in] DWORD                   authLevel,
   [in] DWORD                   impLevel,
   [in] IWbemServices*          pCurrentNamespace,
   [in] BSTR                    strUser,
   [in] BSTR                    strPassword,
   [in] BSTR                    strAuthority
); 
```  

## <a name="parameters"></a>매개 변수

`strQueryLanguage`    
[in] Windows 관리를 지 원하는 올바른 쿼리 언어를 사용 하 여 사용 되는 문자열입니다. WMI 쿼리 언어에 대 한 약칭 "WQL" 이어야 합니다.

`strQuery`  
[in] 쿼리의 텍스트입니다. 이 매개 변수 수 없습니다 `null`합니다.

`lFlags`   
[in] 이 함수의 동작에 영향을 주는 두 플래그의 조합입니다. 이러한 값은 정의 된 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드입니다. 

| 상수 | 값  | 설명  |
|---------|---------|---------|
| `WBEM_FLAG_RETURN_IMMEDIATELY` | 0x10 | 플래그를 사용 하면 일부 동기 호출입니다. 이 플래그를 설정 하지 않으면 호출이 실패 합니다. 왜냐하면 이벤트가 지속적으로 수신 되는 사용자에 반환 된 열거자 폴링해야 합니다. 즉입니다. 이 호출을 무기한으로 차단 하면는 불가능 합니다. |
| `WBEM_FLAG_FORWARD_ONLY` | 0x20 | 함수에는 정방향 전용 열거자를 반환합니다. 일반적으로 앞 으로만 이동 가능한 열거자 빠르고 기본 열거자 보다 적은 메모리를 사용 하지만 호출을 허용 하지 않습니다 [복제](clone.md)합니다. |

`pCtx`  
[in] 이 값은 일반적으로 `null`입니다. 그렇지 않을 경우에 대 한 포인터를 [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) 요청된 이벤트를 제공 하는 공급자가 사용할 수 있는 인스턴스. 

`ppEnum`  
[out] 오류가 발생 하는 경우 호출자가 쿼리의 결과 집합의 인스턴스를 검색할 수 있도록 하는 열거자에 대 한 포인터를 받습니다. 참조 된 [주의](#remarks) 자세한 내용은 섹션입니다.

`authLevel`  
[in] 권한 부여 수준입니다.

`impLevel` [in] 가장 수준입니다.

`pCurrentNamespace`   
[in] 에 대 한 포인터를 [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) 현재 네임 스페이스를 나타내는 개체입니다.

`strUser`   
[in] 사용자 이름입니다. 참조 된 [ConnectServerWmi](connectserverwmi.md) 자세한 함수입니다.

`strPassword`   
[in] 암호입니다. 참조 된 [ConnectServerWmi](connectserverwmi.md) 자세한 함수입니다.

`strAuthority`   
[in] 사용자의 도메인 이름입니다. 참조 된 [ConnectServerWmi](connectserverwmi.md) 자세한 함수입니다.

## <a name="return-value"></a>반환 값

이 함수에 의해 반환 되는 다음 값에 정의 된 합니다 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드:

|상수  |값  |설명  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | 0x80041003 | 사용자 함수를 반환할 수 있는 클래스 중 하나 이상을 볼 수 있는 권한이 없습니다. |
| `WBEM_E_FAILED` | 0x80041001 | 지정 되지 않은 오류가 발생 했습니다. |
| `WBEM_E_INVALID_PARAMETER` | '(0x80041008 | 매개 변수가 잘못 되었습니다. |
| `WBEM_E_INVALID_CLASS` | 0x80041010 | 쿼리는 존재 하지 않는 클래스를 지정 합니다. |
| `WBEMESS_E_REGISTRATION_TOO_PRECISE` | 0x80042002 | 이벤트 전달 정확 하 게 너무 많이 요청 되었습니다. 더 큰 폴링 허용 오차를 지정 해야 합니다. |
| `WBEMESS_E_REGISTRATION_TOO_BROAD` | 0x80042001 | 쿼리 requess Windows 관리 보다 더 많은 정보를 제공할 수 있습니다. 이 `HRESULT` 네임 스페이스의 모든 개체를 폴링 하려면 요청에서 이벤트 쿼리 결과 반환 됩니다. |
| `WBEM_E_INVALID_QUERY` | 0x80041017 | 쿼리 구문 오류가 발생을 했습니다. |
| `WBEM_E_INVALID_QUERY_TYPE` | 0x80041018 | 요청한 쿼리 언어는 지원 되지 않습니다. |
| `WBEM_E_QUOTA_VIOLATION` | 0x8004106c | 쿼리는 너무 복잡 합니다. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006(" | 메모리가 부족 하 여 작업을 완료할 수 없습니다. |
| `WBEM_E_SHUTTING_DOWN` | 0x80041033 | WMI는 아마도 중지 및 다시 시작 했습니다. 호출 [ConnectServerWmi](connectserverwmi.md) 다시 합니다. |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | 현재 프로세스와 WMI 원격 프로시저 호출 (RPC) 연결 하지 못했습니다. |
| `WBEM_E_UNPARSABLE_QUERY` | 0x80041058 | 쿼리를 구문 분석할 수 없습니다. |
| `WBEM_S_NO_ERROR` | 0 | 함수 호출이 성공 했습니다.  |
  
## <a name="remarks"></a>설명

이 함수에 대 한 호출을 래핑하는 [IWbemServices::ExecNotificationQuery](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-execnotificationquery) 메서드.

함수가 반환 되 면 호출자가 정기적으로 전달할 반환 된 `ppEnum` 개체를 [다음](next.md) 함수를 사용할 수 있는 모든 이벤트.

수에 제한이 `AND` 및 `OR` WQL 쿼리에서 사용할 수 있는 키워드입니다. 많은 복잡 한 쿼리를 사용 하는 WQL 키워드를 반환 하기 위해 WMI를 발생할 수 있습니다 합니다 `WBEM_E_QUOTA_VIOLATION` (또는 0x8004106c) 오류 코드는 `HRESULT` 값입니다. WQL 키워드 제한 방법을 복잡 한 쿼리는에 따라 달라 집니다.

함수 호출에 실패 하는 경우 호출 하 여 추가 오류 정보를 얻을 수 있습니다 합니다 [GetErrorInfo](geterrorinfo.md) 함수입니다.

## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** WMINet_Utils.idl  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고자료  
[WMI 및 성능 카운터 (관리 되지 않는 API 참조)](index.md)
