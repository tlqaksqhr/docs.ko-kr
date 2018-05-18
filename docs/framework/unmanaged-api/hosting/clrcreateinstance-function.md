---
title: CLRCreateInstance 함수
ms.date: 03/30/2017
api_name:
- CLRCreateInstance
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- COM
f1_keywords:
- CLRCreateInstance
helpviewer_keywords:
- CLRCreateInstance function [.NET Framework hosting]
ms.assetid: 5de13327-96c6-4697-a89e-b8bf40717855
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4ab16d78b210c2824bf6172f80d1b15e3533a05b
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2018
---
# <a name="clrcreateinstance-function"></a>CLRCreateInstance 함수
세 가지 인터페이스 중 하나를 제공: [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md), [ICLRMetaHostPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md), 또는 [ICLRDebugging](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-interface.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT CLRCreateInstance(  
    [in]  REFCLSID  clsid,  
    [in]  REFIID     riid,  
    [out] LPVOID  * ppInterface  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `clsid`  
 [in] 세 가지 클래스 식별자 중 하나: CLSID_CLRMetaHost, CLSID_CLRMetaHostPolicy, 또는 CLSID_CLRDebugging 합니다.  
  
 `riid`  
 [in] 세 가지 인터페이스 식별자 (Iid) 중 하나: IID_ICLRMetaHost, IID_ICLRMetaHostPolicy, 또는 IID_ICLRDebugging 합니다.  
  
 `ppInterface`  
 [out] 세 가지 인터페이스 중 하나: [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md), [ICLRMetaHostPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md), 또는 [ICLRDebugging](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-interface.md)합니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|메서드가 완료되었습니다.|  
|E_POINTER|`ppInterface`가 null인 경우|  
  
## <a name="remarks"></a>설명  
 다음 표에서 지원 되는 조합을 `clsid` 및 `riid`합니다.  
  
|`clsid`|`riid`|  
|--------------|------------|  
|CLSID_CLRMetaHost|IID_ICLRMetaHost|  
|CLSID_CLRMetaHostPolicy|IID_ICLRMetaHostPolicy|  
|CLSID_CLRDebugging|IID_ICLRDebugging|  
  
 다음 코드를 사용 하는 방법을 보여 줍니다 `CLRCreateInstance` 모든 세 가지 인터페이스를 얻으려고 합니다.  
  
```  
#include <metahost.h>  
#pragma comment(lib, "mscoree.lib")  
  
ICLRMetaHost       *pMetaHost       = NULL;  
ICLRMetaHostPolicy *pMetaHostPolicy = NULL;  
ICLRDebugging      *pCLRDebugging   = NULL;  
HRESULT hr;  
hr = CLRCreateInstance(CLSID_CLRMetaHost, IID_ICLRMetaHost,  
                    (LPVOID*)&pMetaHost);  
hr = CLRCreateInstance (CLSID_CLRMetaHostPolicy, IID_ICLRMetaHostPolicy,  
                    (LPVOID*)&pMetaHostPolicy);  
hr = CLRCreateInstance (CLSID_CLRDebugging, IID_ICLRDebugging,  
                    (LPVOID*)&pCLRDebugging);  
```  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MetaHost.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [호스팅](../../../../docs/framework/unmanaged-api/hosting/index.md)
