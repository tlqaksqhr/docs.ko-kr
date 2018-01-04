---
title: "ResetSecurity 함수 (관리 되지 않는 API 참조)"
description: "ResetSecurity 함수를 현재 스레드에서 가장 토큰을 지정합니다."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: ResetSecurity
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: ResetSecurity
helpviewer_keywords: ResetSecurity function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bacee65633d25e705d978d3902a6804516a88bf4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="resetsecurity-function"></a>ResetSecurity 함수
현재 스레드의에 제공 된 가장 토큰을 지정합니다.   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>구문  
  
```  
HRESULT ResetSecurity (
   [in] HANDLE token
); 
```  

## <a name="parameters"></a>매개 변수

`token`  
[in] 현재 스레드와 연결할 가장 토큰입니다. 이 값은 `null`일 수 있습니다. 

## <a name="return-value"></a>반환 값

함수가 성공 하면 반환 값은 `S_OK` (0).

함수가 실패 하면 반환 값은 0이 아닌 오류 코드입니다. 확장 정보를 가져오려면 오류를 호출 하는 [GetErrorInfo](geterrorinfo.md) 함수입니다.
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** WMINet_Utils.idl  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고 항목  
[WMI 및 성능 카운터 (관리 되지 않는 API 참조)](index.md)
