---
title: "GetRequestedRuntimeVersion 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetRequestedRuntimeVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: GetRequestedRuntimeVersion
helpviewer_keywords: GetRequestedRuntimeVersion function [.NET Framework hosting]
ms.assetid: 82f596a4-483d-4509-b0c5-a84c53c3da1b
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bfac4e32841b8a8332a1f4124c1326f1ef7da1f8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="getrequestedruntimeversion-function"></a>GetRequestedRuntimeVersion 함수
지정된 된 응용 프로그램에서 요청한 공용 언어 런타임 (CLR)의 버전 번호를 가져옵니다. 해당 버전이 설치 되지 않은 경우 요청 된 버전 이전에 설치 된 최신 버전을 가져옵니다.  
  
 이 함수에 더 이상 사용 되지는 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetRequestedRuntimeVersion (  
    [in]  LPWSTR  pExe,   
    [out] LPWSTR  pVersion,   
    [in]  DWORD   cchBuffer,   
    [out] DWORD  *pdwLength  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pExe`  
 [in] 응용 프로그램의 이름입니다.  
  
 `pVersion`  
 [out] 완료 되 면 버전 번호 문자열을 포함 하는 버퍼입니다.  
  
 `cchBuffer`  
 [in] 버전 버퍼의 길이입니다.  
  
 `pdwLength`  
 [out] 버전 번호 문자열의 길이에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 다음 값 외에도 WinError.h에 정의 된 대로 표준 구성 요소 개체 모델 (COM) 오류 코드를 반환 합니다.  
  
|반환 코드|설명|  
|-----------------|-----------------|  
|S_OK|메서드가 완료되었습니다.|  
|ERROR_INSUFFICIENT_BUFFER|버전 버퍼가 버전 문자열을 저장 하기에 충분 합니다.|  
|E_POINTER|`pdwLength`가 null인 경우|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [GetRequestedRuntimeInfo 함수](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)  
 [GetVersionFromProcess 함수](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)  
 [사용 되지 않는 CLR 호스팅 함수](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
