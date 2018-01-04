---
title: "ICLRRuntimeInfo::GetDefaultStartupFlags 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeInfo.GetDefaultStartupFlags
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeInfo::GetDefaultStartupFlags
helpviewer_keywords:
- ICLRRuntimeInfo::GetDefaultStartupFlags method [.NET Framework hosting]
- GetDefaultStartupFlags method [.NET Framework hosting]
ms.assetid: 35c2173e-3b0b-4b2a-950d-e0a01c6df052
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8b278a791c7e5418322a80bc6478f75791a35af8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrruntimeinfogetdefaultstartupflags-method"></a>ICLRRuntimeInfo::GetDefaultStartupFlags 메서드
시작 플래그와 런타임을 시작 하는 호스트 구성 파일을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetDefaultStartupFlags(  
     [out]  DWORD *pdwStartupFlags,  
     [out, size_is(*pcchHostConfigFile)] LPWSTR pwzHostConfigFile,  
     [in, out]  DWORD *pcchHostConfigFile);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pdwStartupFlags`  
 [out] 현재 설정 되어 있는 호스트 시작 플래그에 대 한 포인터입니다.  
  
 `pwzHostConfigFile`  
 [out] 현재 호스트 구성 파일의 디렉터리 경로에 대 한 포인터입니다.  
  
 `pcchHostConfigFile`  
 [out에서] 입력에 크기 `pwzHostConfigFile`버퍼 오버런을 방지 하려면. 경우 `pwzHostConfigFile` 가 null 인 메서드가 필요한 크기의 `pwzHostConfigFile` 사전 할당에 대 한 합니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 다음과 같은 특정 HRESULT를 반환 합니다. 메서드 오류를 나타내는 HRESULT 오류도 있습니다.  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|메서드가 완료되었습니다.|  
  
## <a name="remarks"></a>설명  
 이 메서드는 기본 플래그 값을 반환 (`STARTUP_CONCURRENT_GC` 및 `NULL`), 또는 대 한 이전 호출에서 제공 하는 값은 [iclrruntimeinfo:: Setdefaultstartupflags 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-setdefaultstartupflags-method.md), 또는 중 하나에 의해 설정 값은 `CorBind*` 메서드를이 런타임에 바인딩된 경우를 포함 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MetaHost.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICLRRuntimeInfo 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [호스팅 인터페이스](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [호스팅](../../../../docs/framework/unmanaged-api/hosting/index.md)
