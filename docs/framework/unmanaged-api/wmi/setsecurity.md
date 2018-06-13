---
title: SetSecurity 함수 (관리 되지 않는 API 참조)
description: SetSecurity 함수는 현재 스레드의 가장 토큰을 검색합니다.
ms.date: 11/06/2017
api_name:
- SetSecurity
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- SetSecurity
helpviewer_keywords:
- SetSecurity function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0fd354e1103832abee7f634eace3dd6defa8b646
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33458753"
---
# <a name="setsecurity-function"></a>SetSecurity 함수
현재 스레드와 연결 된 가장 토큰을 검색 합니다.   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>구문  
  
```  
HRESULT SetSecurity (
   [out] boolean* pNeedToReset, 
   [out] HANDLE* pCurrentThreadToken
); 
```  

## <a name="parameters"></a>매개 변수

`pNeedToReset` [out] 함수에서 반환에 대 한 포인터를 포함 한 `boolean` 호출 하 여 토큰을 다시 설정할지 여부를 나타내는 [ResetSecurity](resetsecurity.md) 함수입니다.  

`token`  
[out] 함수가 반환 될 때 현재 스레드와 연결 된 가장 토큰 핸들에 대 한 포인터를 포함 합니다. 해당 값으로 가능 `null` 현재 스레드와 연결 된 토큰이 없는 경우. 

## <a name="return-value"></a>반환 값

함수가 성공 하면 반환 값은 `S_OK` (0).

함수가 실패 하면 반환 값은 0이 아닌 오류 코드입니다. 확장 정보를 가져오려면 오류를 호출 하는 [GetErrorInfo](geterrorinfo.md) 함수입니다.
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** WMINet_Utils.idl  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고자료  
[WMI 및 성능 카운터 (관리 되지 않는 API 참조)](index.md)
