---
title: Initialize 함수 (관리 되지 않는 API 참조)
description: Initialize 함수 WMI 초기화를 수행합니다.
ms.date: 11/06/2017
api_name:
- Initialize
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Initialize
helpviewer_keywords:
- Initialize function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 01de35a0cd4d359dfba0375a85fbce017e44b9f8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455757"
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
  
 **.NET framework 버전:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>참고자료  
[WMI 및 성능 카운터 (관리 되지 않는 API 참조)](index.md)
