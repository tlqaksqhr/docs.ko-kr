---
title: "ExecQueryWmi 함수 (관리 되지 않는 API 참조)"
description: "ExecQueryWmi 함수 개체를 검색 하는 쿼리를 실행 합니다."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- ExecQueryWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- ExecQueryWmi
helpviewer_keywords:
- ExecQueryWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 872109cb0472a8404c492c2867429fe783f898eb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="execquerywmi-function"></a>ExecQueryWmi 함수
개체를 검색 하는 쿼리를 실행 합니다.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>구문  
  
```  
HRESULT ExecQueryWmi (
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
[in] 이 함수의 동작에 영향을 주는 플래그의 조합입니다. 에 정의 된 다음 값은 *WbemCli.h* 헤더 파일 또는 있습니다를 정의할 수 상수로 코드: 

| 상수 | 값  | 설명  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | 0 x 20000 | 경우 집합 함수는 현재 연결의 로캘의 지역화 된 네임 스페이스에 저장 된 수정 된 한정자를 검색 합니다. <br/> 그렇지 않은 경우 집합 함수 즉시 네임 스페이스에 저장 된 한정자만 검색 합니다. |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | 0x10 | 플래그를 사용 하면 일부 동기 호출입니다. |
| `WBEM_FLAG_FORWARD_ONLY` | 0x20 | 함수는 앞 으로만 이동 가능한 열거자를 반환합니다. 에 대 한 호출을 허용 하지 않습니다 앞 으로만 이동 가능한 열거자 빠르고 기본 열거자 보다 메모리를 적게 사용 되지만 일반적으로 [복제](clone.md)합니다. |
| `WBEM_FLAG_BIDIRECTIONAL` | 0 | WMI 회수 될 때까지 enumration의 개체에 대 한 포인터를 유지 합니다. | 
| `WBEM_FLAG_ENSURE_LOCATABLE` | 0x100 | 반환 된 개체에 대 한 충분 한 정보가 있으므로 사용 하면 해당 시스템 속성 같은 **__PATH**, **__RELPATH**, 및 **__SERVER**, 없는 `null`합니다. |
| `WBEM_FLAG_PROTOTYPE` | 2 | 이 플래그는 프로토타입 생성에 사용 됩니다. 쿼리를 실행 하지 않는 하 고 대신 다음과 같은 일반적인 결과 개체는 개체를 반환 합니다. |
| `WBEM_FLAG_DIRECT_READ` | 0x200 | 원인을 직접 부모 클래스 또는 서브 클래스에 관계 없이 지정 된 클래스에 대 한 공급자에 액세스 합니다. |

권장 되는 플래그를 `WBEM_FLAG_RETURN_IMMEDIATELY` 및 `WBEM_FLAG_FORWARD_ONLY` 최상의 성능을 위해.

`pCtx`  
[in] 이 값은 일반적으로 `null`합니다. 그렇지 않은 경우에 대 한 포인터는 [IWbemContext](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx) 요청 된 클래스를 제공 하는 공급자가 사용할 수 있는 인스턴스. 

`ppEnum`  
[out] 오류가 발생 하는 경우 호출자는 쿼리 결과 집합의 인스턴스를 검색 하는 열거자에 대 한 포인터를 받습니다. 쿼리 결과 집합을 제로 인스턴스를 가질 수 있습니다. 참조는 [주의](#remarks) 한 자세 합니다.

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
| `WBEM_E_INVALID_QUERY` | 0x80041017 | 쿼리 구문 오류가 발생을 했습니다. |
| `WBEM_E_INVALID_QUERY_TYPE` | 0x80041018 | 요청한 쿼리 언어는 지원 되지 않습니다. |
| `WBEM_E_QUOTA_VIOLATION` | 0x8004106c | 쿼리는 너무 복잡 합니다. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 작업을 완료 하려면 사용할 수 있는 메모리가 충분 하지 않습니다. |
| `WBEM_E_SHUTTING_DOWN` | 0x80041033 | WMI 아마도 중지 및 다시 시작 했습니다. 호출 [ConnectServerWmi](connectserverwmi.md) 다시 합니다. |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | 현재 프로세스 사이의 WMI 원격 프로시저 호출 (RPC) 연결 하지 못했습니다. |
| `WBEM_E_NOT_FOUND` | 0x80041002 | 쿼리에서 존재 하지 않는 클래스를 지정 합니다. |
| `WBEM_S_NO_ERROR` | 0 | 함수 호출이 성공 했습니다.  |
  
## <a name="remarks"></a>설명

이 함수에 대 한 호출을 래핑하는 [IWbemServices::ExecQuery](https://msdn.microsoft.com/library/aa392107(v=vs.85).aspx) 메서드.

이 함수에 지정 된 쿼리 처리는 `strQuery` 매개 변수는 호출자에 게 쿼리 결과 액세스할 수 있는 열거자를 만듭니다. 열거자가에 대 한 포인터는 [IEnumWbemClassObject](https://msdn.microsoft.com/library/aa390857(v=vs.85).aspx) 인터페이스; 쿼리 결과 통해 사용할 수 있는 클래스 개체의 인스턴스는 [IWbemClassObject](https://msdn.microsoft.com/library/aa391433(v=vs.85).aspx) 인터페이스입니다.

수에 제한이 `AND` 및 `OR` WQL 쿼리에서 사용할 수 있는 키워드입니다. 많은 수의 복잡 한 쿼리에서 사용 하는 WQL 키워드 반환 하기 위해 WMI를 발생할 수 있습니다는 `WBEM_E_QUOTA_VIOLATION` (또는 0x8004106c)으로 오류 코드는 `HRESULT` 값입니다. WQL 키워드 제한인 쿼리가 복잡 한 정도에 따라 다릅니다.

함수 호출에 실패 하는 경우 호출 하 여 추가 오류 정보를 얻을 수 있습니다는 [GetErrorInfo](geterrorinfo.md) 함수입니다.

## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** WMINet_Utils.idl  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고 항목  
[WMI 및 성능 카운터 (관리 되지 않는 API 참조)](index.md)
