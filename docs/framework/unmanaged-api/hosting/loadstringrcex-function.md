---
title: "LoadStringRCEx 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: LoadStringRCEx
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: LoadStringRCEx
helpviewer_keywords: LoadStringRCEx function [.NET Framework hosting]
ms.assetid: bc789636-ca14-4f07-8f77-9305874d7495
topic_type: apiref
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3467ebcd0b821c2313f3535c5b594ef664546e4a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="loadstringrcex-function"></a>LoadStringRCEx 함수
HRESULT 값을 지정된 된 문화권에 대 한 적절 한 오류 메시지를 변환합니다.  
  
 이 함수에 더 이상 사용 되지는 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT LoadStringRCEx (  
    [in]  LCID    lcid,   
    [in]  UINT    iResouceID,   
    [out] LPWSTR  szBuffer,   
    [in]  int     iMax,   
    [in]  int     bQuiet,   
    [out] int    *pcwchUsed  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `lcid`  
 [in] 문화권 식별자입니다. -1을 전달 `lcid` 기본 문화권을 사용 하도록 합니다.  
  
 `iResourceID`  
 [in] HRESULT 값입니다.  
  
 `szBuffer`  
 [out] 완료 되 면 오류 메시지를 포함 하는 버퍼입니다.  
  
 `iMax`  
 [in] 오류 메시지 버퍼의 크기입니다.  
  
 `bQuiet`  
 [in] 무시 됩니다.  
  
 `pcwchUsed`  
 [out] 오류 메시지의 길이에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 다음 값 외에도 WinError.h에 정의 된 대로 표준 COM 오류 코드를 반환 합니다.  
  
|반환 코드|설명|  
|-----------------|-----------------|  
|S_OK|메서드가 완료되었습니다.|  
|E_INVALIDARG|`szBuffer`매개 변수가 null 이면 또는 `iMax` 은 영 (0).|  
  
## <a name="remarks"></a>설명  
 메서드가 성공적으로 완료 되지 않으면 `szBuffer` 빈 문자열을 포함 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Globalization.CultureInfo.LCID%2A?displayProperty=nameWithType>  
 [LoadStringRC 함수](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)  
 [사용 되지 않는 CLR 호스팅 함수](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
