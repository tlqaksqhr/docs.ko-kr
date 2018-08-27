---
title: CreateClassEnumWmi 함수 (관리 되지 않는 API 참조)
description: CreateClassEnumWmi 함수는 지정 된 조건을 충족 하는 모든 클래스에 대 한 열거자를 반환 합니다.
ms.date: 11/06/2017
api_name:
- CreateClassEnumWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- CreateClassEnumWmi
helpviewer_keywords:
- CreateClassEnumWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b38e4753105932d2464bf78797a6979aeb0a0aee
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/24/2018
ms.locfileid: "42908185"
---
# <a name="createclassenumwmi-function"></a>CreateClassEnumWmi 함수
지정된 된 선택 조건을 충족 하는 모든 클래스에 대 한 열거자를 반환 합니다.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>구문  
  
```  
HRESULT CreateClassEnumWmi (
   [in] BSTR                    strSuperclass,
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

`strSuperclass`    
[in] 그렇지 않은 경우 `null` 빈, 부모 클래스의 이름을 지정 하거나 열거자만이 클래스의 서브 클래스를 반환 합니다. 있으면 `null` 또는 빈 및 `lFlags` WBEM_FLAG_SHALLOW를 최상위 클래스 (부모 클래스가 없는 클래스)를 반환 합니다. 있으면 `null` 또는 빈 및 `lFlags` 는 `WBEM_FLAG_DEEP`, 네임 스페이스의 모든 클래스를 반환 합니다.

`lFlags`   
[in] 이 함수의 동작에 영향을 주는 플래그의 조합입니다. 에 정의 된 다음 값을 *WbemCli.h* 헤더 파일에서 정의할 수 상수로 코드: 

|상수  |값  |설명  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | 0x20000 | 경우 집합 함수는 현재 연결의 로캘의 지역화 된 네임 스페이스에 저장 된 수정 된 한정자를 검색 합니다. <br/> 그렇지 않은 경우 집합 함수를 즉시 네임 스페이스에 저장 된 한정자만 검색 합니다. |
| `WBEM_FLAG_DEEP` | 0 | 열거형이이 클래스가 아닌 계층에서 모든 하위 클래스를 포함합니다. |
| `WBEM_FLAG_SHALLOW` | 1 | 이 클래스의 순수 인스턴스만 포함이 클래스에 없는 속성을 제공 하는 서브 클래스의 모든 인스턴스를 제외 하는 열거형입니다. |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | 0x10 | 플래그를 사용 하면 일부 동기 호출입니다. |
| `WBEM_FLAG_FORWARD_ONLY` | 0x20 | 함수에는 정방향 전용 열거자를 반환합니다. 일반적으로 앞 으로만 이동 가능한 열거자 빠르고 기본 열거자 보다 적은 메모리를 사용 하지만 호출을 허용 하지 않습니다 [복제](clone.md)합니다. |
| `WBEM_FLAG_BIDIRECTIONAL` | 0 | WMI가 릴리스될 때까지 enumration의 개체에 대 한 포인터를 유지 합니다. | 

권장 되는 플래그가 `WBEM_FLAG_RETURN_IMMEDIATELY` 고 `WBEM_FLAG_FORWARD_ONLY` 최상의 성능을 위해.

`pCtx`  
[in] 이 값은 일반적으로 `null`입니다. 그렇지 않을 경우에 대 한 포인터를 [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) 요청 된 클래스를 제공 하는 공급자가 사용할 수 있는 인스턴스. 

`ppEnum`  
[out] 열거자에 대 한 포인터를 받습니다.

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
| `WBEM_E_INVALID_CLASS` | 0x80041010 | `strSuperClass`가 없는 경우 |
| `WBEM_E_INVALID_PARAMETER` | '(0x80041008 | 매개 변수가 잘못 되었습니다. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006(" | 메모리가 부족 하 여 작업을 완료할 수 없습니다. |
| `WBEM_E_SHUTTING_DOWN` | 0x80041033 | WMI는 아마도 중지 및 다시 시작 했습니다. 호출 [ConnectServerWmi](connectserverwmi.md) 다시 합니다. |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | 현재 프로세스와 WMI 원격 프로시저 호출 (RPC) 연결 하지 못했습니다. |
|`WBEM_S_NO_ERROR` | 0 | 함수 호출이 성공 했습니다.  |
  
## <a name="remarks"></a>설명

이 함수에 대 한 호출을 래핑하는 [IWbemServices::CreateClassEnum](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-createclassenum) 메서드.

함수 호출에 실패 하는 경우 호출 하 여 추가 오류 정보를 얻을 수 있습니다 합니다 [GetErrorInfo](geterrorinfo.md) 함수입니다.

## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** WMINet_Utils.idl  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고자료  
[WMI 및 성능 카운터 (관리 되지 않는 API 참조)](index.md)
