---
title: "GetRequestedRuntimeVersionForCLSID 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetRequestedRuntimeVersionForCLSID
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: GetRequestedRuntimeVersionForCLSID
helpviewer_keywords: GetRequestedRuntimeVersionForCLSID function [.NET Framework hosting]
ms.assetid: 5bb12f9a-0612-434b-b4ed-2db636a20bec
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4a5b9e4b186b6c9b91c1182e8700268f0e1c038f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="getrequestedruntimeversionforclsid-function"></a>GetRequestedRuntimeVersionForCLSID 함수
적절 한 공용 언어 런타임 정보를 가져옵니다 (CLR) 버전 지정 된 클래스에 대 한 `CLSID`합니다.  
  
 이 함수에 더 이상 사용 되지는 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetRequestedRuntimeVersionForCLSID (  
    [in]  REFCLSID   rclsid,   
    [out]  LPWSTR     pVersion,   
    [in]  DWORD      cchBuffer,   
    [out] DWORD*     dwLength,   
    [in]  CLSID_RESOLUTION_FLAGS dwResolutionFlags  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `rclsid`  
 [in]  `CLSID` 의 구성 요소입니다.  
  
 `pVersion`  
 [out]  완료 되 면 버전 번호 문자열을 포함 하는 버퍼입니다.  
  
 `cchBuffer`  
 [in]  와이드 문자에서 크기의는 `pVersion` 버퍼입니다.  
  
 `dwLength`  
 [out] 반환된 된 버퍼의 길이 (바이트)를 합니다.  
  
 `dwResolutionFlags`  
 [in]  CLSID_RESOLUTION_FLAGS 값 중 하나입니다. 다음 값이 지원 됩니다.  
  
-   CLSID_RESOLUTION_DEFAULT: (0x0) 해당 기본 interop 동작을 지정 해야 사용 합니다.  
  
-   CLSID_RESOLUTION_REGISTERED: (0x1) 레지스트리를 검색 하 고 정책 shim을 지정 해야 적용 됩니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|함수 반환 되었습니다.|  
|E_INVALIDARG|매개 변수 중 하나는 잘못 된 유형 또는 미디어 형식에 있습니다.|  
|ERROR_INSUFFICIENT_BUFFER|`pVersion` 버퍼를 전체 버전 문자열을 보관할 만큼 크지 않습니다.|  
|REGDB_E_CLASSNOTREG|등록 된 지정 된 클래스가 없습니다 `CLSID`합니다.|  
|E_POINTER|`dwLength`매개 변수가 null 이면 또는 `cchBuffer` 버전 문자열을 저장할 수 있도록 충분히 큰 있지만 `pVersion` null입니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [사용 되지 않는 CLR 호스팅 함수](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
