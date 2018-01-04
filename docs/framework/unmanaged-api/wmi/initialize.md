---
title: "Initialize 함수 (관리 되지 않는 API 참조)"
description: "Initialize 함수 WMI 초기화를 수행합니다."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: Initialize
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: Initialize
helpviewer_keywords: Initialize function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d62d959c5dfeac237abb20b86df87ae07a077dbd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="initialize-function"></a>Initialize 함수
WMI 초기화를 수행 합니다.  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>구문 
```  
HRESULT Initialize(
   [in] boolean bAllowIManagementObjectQI
); 
```  
## <a name="parameters"></a>매개 변수

`bAllowIManagementObjectQI`   
[in] `true` WMI 개체에서 QueryInterface 호출할 수 있도록; 나타내기 위해 `false` 그렇지 않은 경우.

## <a name="return-value"></a>반환 값

함수는 항상 반환 `S_OK` (0).
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** WMINet_Utils.def  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고 항목  
[WMI 및 성능 카운터 (관리 되지 않는 API 참조)](index.md)
