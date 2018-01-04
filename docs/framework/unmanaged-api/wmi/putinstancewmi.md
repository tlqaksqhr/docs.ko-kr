---
title: "PutInstanceWmi 함수 (관리 되지 않는 API 참조)"
description: "PutInstanceWmi 함수를 만들거나 기존 클래스의 인스턴스를 업데이트 합니다."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: PutInstanceWmi
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: PutInstanceWmi
helpviewer_keywords: PutInstanceWmi function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b1996103eea87562226537f9aa90dc337c56313c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="putinstancewmi-function"></a>PutInstanceWmi 함수
만들거나 기존 클래스의 인스턴스를 업데이트 합니다. 인스턴스는 WMI 리포지토리에 기록 됩니다. 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>구문  
  
```  
HRESULT PutInstanceWmi (
   [in] IWbemClassObject*    pInst,
   [in] long                 lFlags,
   [in] IWbemContext*        pCtx,
   [out] IWbemCallResult**   ppCallResult
); 
```  

## <a name="parameters"></a>매개 변수

`pInst`    
[in] 기록 된 인스턴스가에 대 한 포인터입니다.

`lFlags`   
[in] 이 함수의 동작에 영향을 주는 플래그의 조합입니다. 에 정의 된 다음 값은 *WbemCli.h* 헤더 파일 또는 있습니다를 정의할 수 상수로 코드: 

|상수  |값  |설명  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | 0 x 20000 | 경우 설정, WMI 저장 하지 않습니다와 한정자는 **Amended** 버전입니다. </br> 집합 가정이 개체에 지역화 되지 않으면 및 모든 한정자는 storedwith 하지 않은 경우이 인스턴스에 있습니다. |
| `WBEM_FLAG_CREATE_OR_UPDATE` | 0 | 존재 하거나 이미 있는 경우 덮어쓸 하지 않는 경우 인스턴스를 만듭니다. |
| `WBEM_FLAG_UPDATE_ONLY` | 1 | 인스턴스를 업데이트 합니다. 호출이 성공 인스턴스가 존재 해야 합니다. |
| `WBEM_FLAG_CREATE_ONLY` | 2 | 인스턴스를 만듭니다. 호출은 인스턴스가 이미 존재 하는 경우 실패 합니다. |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | 0x10 | 플래그를 사용 하면 일부 동기 호출입니다. |

`pCtx`  
[in] 이 값은 일반적으로 `null`합니다. 그렇지 않은 경우에 대 한 포인터는 [IWbemContext](https://msdn.microsoft.com/library/aa391465(v=vs.85).aspx) 요청 된 클래스를 제공 하는 공급자가 사용할 수 있는 인스턴스. 

`ppCallResult`  
[out] 경우 `null`,이 매개 변수는 사용 되지 않습니다. 경우 `lFlags` 포함 `WBEM_FLAG_RETURN_IMMEDIATELY`, 함수는와 함께 즉시 반환 `WBEM_S_NO_ERROR`합니다. `ppCallResult` 매개 변수가 새에 대 한 포인터를 받습니다. [IWbemCallResult](https://msdn.microsoft.com/library/aa391425(v=vs.85).aspx) 개체입니다.

## <a name="return-value"></a>반환 값

이 함수에서 반환 되는 다음 값에 정의 된는 *WbemCli.h* 헤더 파일 또는 있습니다를 정의할 수 상수로 코드:

|상수  |값  |설명  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | 0x80041003 | 사용자에가 지정된 된 클래스의 인스턴스를 업데이트할 수 없습니다. |
| `WBEM_E_FAILED` | 0 x 80041001 | 지정 되지 않은 오류가 발생 했습니다. |
| `WBEM_E_INVALID_CLASS` | 0x80041010 | 이 인스턴스를 지 원하는 클래스가 올바르지 않습니다. |
| `WBEM_E_ILLEGAL_NULL` | 0x80041028 | `null` 될 수 없는 속성에 대해 지정 된 `null`로 표시 된 속성과 같이 **인덱싱됨** 또는 **Not_Null** 한정자입니다. |
| `WBEM_E_INVALID_OBJECT` | 0x8004100f | 지정 된 인스턴스가 올바르지 않습니다. (예를 들어 호출 `PutInstanceWmi` 클래스와 함께이 값을 반환 합니다.) |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | 매개 변수가 올바르지 않습니다. |
| `WBEM_E_ALREADY_EXISTS` | 0x80041019 | `WBEM_FLAG_CREATE_ONLY` 플래그 지정 했지만 인스턴스가 이미 존재 합니다. |
| `WBEM_E_NOT_FOUND` | 0x80041002 | `WBEM_FLAG_UPDATE_ONLY`에 지정 된 `lFlags`, 되지만 인스턴스가 존재 하지 않습니다. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 작업을 완료 하려면 사용할 수 있는 메모리가 충분 하지 않습니다. |
| `WBEM_E_SHUTTING_DOWN` | 0x80041033 | WMI 아마도 중지 및 다시 시작 했습니다. 호출 [ConnectServerWmi](connectserverwmi.md) 다시 합니다. |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | 현재 프로세스 사이의 WMI 원격 프로시저 호출 (RPC) 연결 하지 못했습니다. |
| `WBEM_S_NO_ERROR` | 0 | 함수 호출이 성공 했습니다. |
  
## <a name="remarks"></a>설명

이 함수에 대 한 호출을 래핑하는 [IWbemServices::PutInstance](https://msdn.microsoft.com/library/aa392115(v=vs.85).aspx) 메서드.

`PutInstanceWmi` 함수에서는 인스턴스를 만들고만 기존 클래스의 인스턴스를 업데이트 합니다.  방식에 따라 `pCtx` 매개 변수를 설정, 일부 또는 모든 인스턴스의 속성이 업데이트 됩니다. 

인스턴스의 경우에서 가리키는 `pInst` 호출 하위 클래스에서 파생 되는 클래스에 대 한 책임 모든 공급자를 Windows 관리 하위 클래스에 속합니다. 이러한 공급자의 모든 원본에 대 한 필수 `PutInstanceWmi` 요청이 성공할 수 있습니다. 계층의 맨 위에 있는 클래스를 지 원하는 공급자를 먼저 호출 됩니다. 호출 하는 순서 맨 위에 있는 클래스의 서브 클래스를 계속 하 고 Windows 관리에서 가리키는 인스턴스를 소유 하는 클래스에 대 한 공급자에 도달할 때까지 위에서 아래로 진행 `pInst`합니다.
Windows 관리 자식 클래스의 인스턴스 중 하나에 대 한 공급자를 호출 하지 않습니다. 

응용 프로그램 클래스 계층 구조에 속하는 인스턴스를 업데이트 해야 하는 경우는 `pInst` 매개 변수 속성을 수정할 수를 포함 하는 인스턴스를 가리켜야 합니다. 즉,에 속하는 대상 인스턴스를 고려 **ClassB**합니다. **ClassB** 에서 파생 되는 인스턴스 **ClassA**, 및 **ClassA** 속성을 정의 **PropA**합니다. 응용 프로그램의 값을 변경 하려는 경우 **PropA** 에 **ClassB** 설정 해야 인스턴스에 `pInst` 인스턴스의 보다는 해당 인스턴스를 **ClassA** .

호출 `PutInstanceWmi` 추상 클래스의 인스턴스를 사용할 수 없습니다.

함수 호출에 실패 하는 경우 호출 하 여 추가 오류 정보를 얻을 수 있습니다는 [GetErrorInfo](geterrorinfo.md) 함수입니다.

## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** WMINet_Utils.idl  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고 항목  
[WMI 및 성능 카운터 (관리 되지 않는 API 참조)](index.md)
