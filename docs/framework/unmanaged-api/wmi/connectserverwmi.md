---
title: "ConnectServerWmi 함수 (관리 되지 않는 API 참조)"
description: "ConnectServerWmi 함수 DCOM를 사용 하 여 WMI 네임 스페이스에 대 한 연결을 만듭니다."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- ConnectServerWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- ConnectServerWmi
helpviewer_keywords:
- ConnectServerWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: dc821bddf1d33ea1144fef0821b81cf027d8f92f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="connectserverwmi-function"></a>ConnectServerWmi 함수
지정된 된 컴퓨터에서 DCOM 통해 WMI 네임 스페이스에 연결을 만듭니다.  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>구문  
  
```  
HRESULT ConnectServerWmi (
   [in] BSTR               strNetworkResource,
   [in] BSTR               strUser,
   [in] BSTR               strPassword,
   [in] BSTR               strLocale,
   [in] long               lSecurityFlags,
   [in] BSTR               strAuthority,
   [in] IWbemContext*      pCtx,
   [out] IWbemServices**   ppNamespace,
   [in] DWORD              impLevel, 
   [in] DWORD              authLevel
);
```  
## <a name="parameters"></a>매개 변수

`strNetworkResource`[in] 포인터를 올바른 `BSTR` 올바른 WMI 네임 스페이스의 개체 경로 포함 하는 합니다. 참조는 [주의](#remarks) 한 자세 합니다.

`strUser`[in] 에 대 한 포인터를 올바른 `BSTR` 사용자 이름이 들어 있는입니다. A `null` 값 현재 보안 컨텍스트를 나타냅니다. 사용자가을 현재 보다 다른 도메인의 경우 `strUser` 백슬래시로 구분 된 도메인과 사용자 이름을 포함할 수도 있습니다. `strUser`수 사용자에서 계정 이름 (UPN)의 형식을 지정할 수도,으로 suhc  *userName@domainName* 합니다. 참조는 [주의](#remarks) 한 자세 합니다.

`strPassword`[in] 에 대 한 포인터를 올바른 `BSTR` 암호가 포함 된 합니다. A `null` 현재 보안 컨텍스트를 나타냅니다. 빈 문자열 ("") 유효한 빈 암호를 나타냅니다.

`strLocale`[in] 에 대 한 포인터를 올바른 `BSTR` 정보 검색에 대 한 올바른 로캘을 나타내는입니다. Microsoft 로캘 식별자에 대 한 문자열의 형식은 "MS\_*xxx*" 여기서 *xxx* 로캘 식별자 (LCID)를 나타내는 16 진수 형식 문자열입니다. 잘못 된 로캘 지정 되 면 메서드가 반환 `WBEM_E_INVALID_PARAMETER` 제외 Windows 7, 서버에서 기본 로캘을 대신 사용 됩니다. 경우 ' null1, 현재 로캘을 사용 됩니다. 
 
`lSecurityFlags`[in] 플래그를 전달 하는 `ConnectServerWmi` 메서드. 에 대 한 호출에서 값이이 매개 변수에 대해 영 (0) 이면 `ConnectServerWmi` 서버에 연결 된 후에 반환 합니다. 이 인해 응답 하지 않는 무기한 끊어진 경우는 응용 프로그램 될 수 있습니다. 다른 유효한 값은:

| 상수  | 값  | 설명  |
|---------|---------|---------|
| `CONNECT_REPOSITORY_ONLY` | 0x40 | 내부용으로 예약됩니다. 사용하지 마십시오. |
| `WBEM_FLAG_CONNECT_USE_MAX_WAIT` | 0x80 | `ConnectServerWmi`2 분 이내에 반환합니다. |

`strAuthority`[in] 사용자의 도메인 이름입니다. 다음 값을 가질 수 있습니다.

| 값 | 설명 |
|---------|---------|
| 비어 있음 | NTLM 인증을 사용 하 고 현재 사용자의 NTLM 도메인 사용 됩니다. 경우 `strUser` 도메인 (권장된 위치)를 지정 합니다. 여기 지정 되지 해야 합니다. 함수 반환 `WBEM_E_INVALID_PARAMETER` 매개 변수가 모두에서 도메인을 지정 합니다. |
| Kerberos:*사용자 이름* | Kerberos 인증을 사용 하 고이 매개 변수에 Kerberos 사용자 이름을 포함 합니다. |
| NTLMDOMAIN:*도메인 이름* | NT LAN Manager 인증을 사용 하 고이 매개 변수에 NTLM 도메인 이름을 포함 합니다. |

`pCtx`   
[in] 일반적으로이 매개 변수는 `null`합니다. 그렇지 않은 경우에 대 한 포인터는 [IWbemContext](https://msdn.microsoft.com/library/aa391465%28v=vs.85%29.aspx) 개체가 하나 이상의 동적 클래스 공급자가 필요 합니다. 

`ppNamespace`  
[out] 함수가 반환할 때 수신에 대 한 포인터는 [IWbemServices](https://msdn.microsoft.com/library/aa392093(v=vs.85).aspx) 개체가 지정된 된 네임 스페이스에 연결 합니다. 가리키도록 설정 되어 `null` 때 오류가 발생 했습니다.

`impLevel`  
[in] 가장 수준입니다.

`authLevel`  
[in] 권한 부여 수준입니다.

## <a name="return-value"></a>반환 값

이 함수에서 반환 되는 다음 값에 정의 된는 *WbemCli.h* 헤더 파일 또는 있습니다를 정의할 수 상수로 코드:

|상수  |값  |설명  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0 x 80041001 | 일반 오류가 발생이 했습니다. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | 매개 변수가 올바르지 않습니다. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 작업을 완료 하려면 사용할 수 있는 메모리가 충분 하지 않습니다. |
| `WBEM_S_NO_ERROR` | 0 | 함수 호출이 성공 했습니다.  |
  
## <a name="remarks"></a>설명

이 함수에 대 한 호출을 래핑하는 [IWbemLocator::ConnectServer](https://msdn.microsoft.com/libraryaa391769%28v=vs.85%29.aspx) 메서드.

 기본 네임 스페이스에 대 한 로컬 액세스에 대 한 `strNetworkResource` 단순 개체 경로일 수 있습니다: "root\default" 또는 "\\.\root\default"입니다. COM 또는 Microsoft 호환 네트워킹을 사용 하 여 원격 컴퓨터에서 기본 네임 스페이스에 대 한 액세스에 대 한 컴퓨터 이름을 포함할: "\\myserver\root\default"입니다. 또한 컴퓨터 이름을 DNS 이름 또는 IP 주소 수 있습니다. `ConnectServerWmi` 함수 i p v 6을 실행 하는 컴퓨터와 연결할 수도 IPv6 주소를 사용 합니다.

`strUser`빈 문자열일 수 없습니다. 에 도메인을 지정 하는 경우 `strAuthority`, 것도 포함 해서도 안에 `strUser`, 함수 반환 또는 `WBEM_E_INVALID_PARAMETER`합니다.


## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** WMINet_Utils.idl  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고 항목  
[WMI 및 성능 카운터 (관리 되지 않는 API 참조)](index.md)
