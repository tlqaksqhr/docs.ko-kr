---
title: "ExecNotificationQueryWmi 함수 (관리 되지 않는 API 참조)"
description: "ExecNotificationQueryWmi 함수 이벤트를 수신 하는 쿼리를 실행 합니다."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: ExecNotificationQueryWmi
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: ExecNotificationQueryWmi
helpviewer_keywords: ExecNotificationQueryWmi function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d6dd0926d2262f8d0aa125b86755017a65a95a7f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
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
[in] Windows 관리에서 지원 되는 유효한 쿼리 언어에 사용 되는 문자열입니다. WMI 쿼리 언어에 대 한 약어 "WQL" 이어야 합니다.

`strQuery`  
[in] 쿼리 텍스트입니다. 이 매개 변수 여야 `null`합니다.

`lFlags`   
[in] 이 함수의 동작에 영향을 주는 다음과 같은 두 가지 플래그의 조합입니다. 이러한 값은 정의 *WbemCli.h* 헤더 파일 또는 있습니다를 정의할 수 상수로 코드입니다. 

| 상수 | 값  | 설명  |
|---------|---------|---------|
| `WBEM_FLAG_RETURN_IMMEDIATELY` | 0x10 | 플래그를 사용 하면 일부 동기 호출입니다. 이 플래그를 설정 하지 않으면 호출이 실패 합니다. 이므로 이벤트를 계속 받는 사용자에 반환 된 열거자 폴링해야 합니다. 즉입니다. 이 호출을 무기한으로 차단 하면는 불가능 합니다. |
| `WBEM_FLAG_FORWARD_ONLY` | 0x20 | 함수는 앞 으로만 이동 가능한 열거자를 반환합니다. 에 대 한 호출을 허용 하지 않습니다 앞 으로만 이동 가능한 열거자 빠르고 기본 열거자 보다 메모리를 적게 사용 되지만 일반적으로 [복제](clone.md)합니다. |

`pCtx`  
[in] 이 값은 일반적으로 `null`합니다. 그렇지 않은 경우에 대 한 포인터는 [IWbemContext](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx) 요청된 이벤트를 제공 하는 공급자가 사용할 수 있는 인스턴스. 

`ppEnum`  
[out] 오류가 발생 하는 경우 호출자는 쿼리 결과 집합의 인스턴스를 검색 하는 열거자에 대 한 포인터를 받습니다. 참조는 [주의](#remarks) 한 자세 합니다.

`authLevel`  
[in] 권한 부여 수준입니다.

`impLevel`[in] 가장 수준입니다.

`pCurrentNamespace`   
[in] 에 대 한 포인터는 [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) 현재 네임 스페이스를 나타내는 개체입니다.

`strUser`   
[in] 사용자 이름입니다. 참조는 [ConnectServerWmi](connectserverwmi.md) 자세한 정보에 대 한 함수입니다.

`strPassword`   
[in] 암호입니다. 참조는 [ConnectServerWmi](connectserverwmi.md) 자세한 정보에 대 한 함수입니다.

`strAuthority`   
[in] 사용자의 도메인 이름입니다. 참조는 [ConnectServerWmi](connectserverwmi.md) 자세한 정보에 대 한 함수입니다.

## <a name="return-value"></a>반환 값

이 함수에서 반환 되는 다음 값에 정의 된는 *WbemCli.h* 헤더 파일 또는 있습니다를 정의할 수 상수로 코드:

|상수  |값  |설명  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | 0x80041003 | 사용자에가 함수에서 반환할 수 있는 클래스를 하나 이상 볼 수 있는 권한이 없습니다. |
| `WBEM_E_FAILED` | 0 x 80041001 | 지정 되지 않은 오류가 발생 했습니다. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | 매개 변수가 올바르지 않습니다. |
| `WBEM_E_INVALID_CLASS` | 0x80041010 | 쿼리에서 존재 하지 않는 클래스를 지정 합니다. |
| `WBEMESS_E_REGISTRATION_TOO_PRECISE` | 0x80042002 | 이벤트의 배달 정밀 하 게 너무 많이 요청 되었습니다. 더 큰 폴링 허용 오차를 지정 해야 합니다. |
| `WBEMESS_E_REGISTRATION_TOO_BROAD` | 0x80042001 | 쿼리 requess Windows 관리 보다 더 많은 정보를 제공할 수 있습니다. 이 `HRESULT` 네임 스페이스의 모든 개체를 폴링 하려면 요청에서 이벤트 쿼리 결과 때 반환 됩니다. |
| `WBEM_E_INVALID_QUERY` | 0x80041017 | 쿼리 구문 오류가 발생을 했습니다. |
| `WBEM_E_INVALID_QUERY_TYPE` | 0x80041018 | 요청한 쿼리 언어는 지원 되지 않습니다. |
| `WBEM_E_QUOTA_VIOLATION` | 0x8004106c | 쿼리는 너무 복잡 합니다. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 작업을 완료 하려면 사용할 수 있는 메모리가 충분 하지 않습니다. |
| `WBEM_E_SHUTTING_DOWN` | 0x80041033 | WMI 아마도 중지 및 다시 시작 했습니다. 호출 [ConnectServerWmi](connectserverwmi.md) 다시 합니다. |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | 현재 프로세스 사이의 WMI 원격 프로시저 호출 (RPC) 연결 하지 못했습니다. |
| `WBEM_E_UNPARSABLE_QUERY` | 0x80041058 | 쿼리를 구문 분석할 수 없습니다. |
| `WBEM_S_NO_ERROR` | 0 | 함수 호출이 성공 했습니다.  |
  
## <a name="remarks"></a>설명

이 함수에 대 한 호출을 래핑하는 [IWbemServices::ExecNotificationQuery](https://msdn.microsoft.com/library/aa392105(v=vs.85).aspx) 메서드.

함수가 반환 되 면 호출자 주기적으로 전달할 반환 된 `ppEnum` 개체는 [다음](next.md) 함수를 사용할 수 있는 모든 이벤트를 참조 하십시오.

수에 제한이 `AND` 및 `OR` WQL 쿼리에서 사용할 수 있는 키워드입니다. 많은 수의 복잡 한 쿼리에서 사용 하는 WQL 키워드 반환 하기 위해 WMI를 발생할 수 있습니다는 `WBEM_E_QUOTA_VIOLATION` (또는 0x8004106c)으로 오류 코드는 `HRESULT` 값입니다. WQL 키워드 제한인 쿼리가 복잡 한 정도에 따라 다릅니다.

함수 호출에 실패 하는 경우 호출 하 여 추가 오류 정보를 얻을 수 있습니다는 [GetErrorInfo](geterrorinfo.md) 함수입니다.

## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** WMINet_Utils.idl  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고 항목  
[WMI 및 성능 카운터 (관리 되지 않는 API 참조)](index.md)
