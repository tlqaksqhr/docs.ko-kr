---
title: BlessIWbemServices 함수 (관리 되지 않는 API 참조)
description: BlessIWbemServices 함수는 사용자 자격 증명 IWbemServices 클래스에 대 한 액세스를 허용 하는지 여부를 나타냅니다.
ms.date: 11/06/2017
api_name:
- BlessIWbemServices
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- BlessIWbemServices
helpviewer_keywords:
- BlessIWbemServices function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a65c3c14507b2520c69875a1bc101ce826ace7ba
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2018
ms.locfileid: "42934306"
---
# <a name="blessiwbemservices-function"></a>BlessIWbemServices 함수
사용자 자격 증명을 지정 된 액세스를 허용 하는지 여부를 나타냅니다 [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) 클래스입니다.   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>구문  
  
```  
HRESULT BlessIWbemServices (
   [in] IWbemServices* pIWbemServices,
   [in] BSTR strUser, 
   [in] BSTR strPassword, 
   [in] BSTR strAuthority, 
   [in] DWORD impLevel, 
   [in] DWORD authnLevel
);
```  

## <a name="parameters"></a>매개 변수

`pIWbemServices`  
[in] 에 대 한 포인터를 [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) 개체는 권한이 필요 합니다.

`strUser`  
[in] 사용자 이름입니다.

`strPassword`  
[in] 연결 된 암호 `strUser`합니다.

`strAuthority` [in] 사용자의 도메인 이름입니다. 참조 된 [ConnectServerWmi](connectserverwmi.md) 자세한 함수입니다.

`impLevel` [in] 가장 수준입니다.

`authnLevel` [in] 권한 부여 수준입니다.

## <a name="return-value"></a>반환 값

이 함수에 의해 반환 되는 다음 값에 정의 된 합니다 *WinError.h* 헤더 파일에서 정의할 수 상수로 코드:

|상수  |값  |설명  |
|---------|---------|---------|
| `E_INVALIDARG` | 0x80070057 | 하나 이상의 인수가 잘못 되었습니다. |
| `E_POINTER` | 0x80004003 | `pIWbemServices`가 `null`인 경우 | 
| `E_FAIL` | 0x80000008 | 지정 되지 않은 오류가 발생 했습니다. |
| `E_OUTOFMEMORY` | 0x80000002 | 메모리가 부족 하 여 작업을 수행할 수 있는 경우 | 
| `S_OK` | 0 | 함수 호출이 성공 했습니다. | 

## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** WMINet_Utils.idl  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고자료  
[WMI 및 성능 카운터 (관리 되지 않는 API 참조)](index.md)
