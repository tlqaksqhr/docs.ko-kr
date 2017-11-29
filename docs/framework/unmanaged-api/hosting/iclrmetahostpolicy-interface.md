---
title: "ICLRMetaHostPolicy 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRMetaHostPolicy
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRMetaHostPolicy
helpviewer_keywords: ICLRMetaHostPolicy interface [.NET Framework hosting]
ms.assetid: 1bdeccb6-0698-4c97-ad69-eae2b69e59f1
topic_type: apiref
caps.latest.revision: "23"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6b8cbe1d397e1214cfa4d3f4cbc3d6cdf2d3ccd5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="iclrmetahostpolicy-interface"></a>ICLRMetaHostPolicy 인터페이스
제공 된 [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) 메서드, 정책 조건에 따라 공용 언어 런타임 (CLR) 인터페이스에 대 한 포인터를 반환 하는 어셈블리, 버전 및 구성 파일을 관리 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetRequestedRuntime 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)|기본 CLR 인터페이스 정책 조건에 따라, 어셈블리, 버전 및 구성 파일을 관리를 제공 합니다.|  
  
## <a name="remarks"></a>설명  
 호출 하 여이 인터페이스에 대 한 참조를 가져올 수 있습니다는 [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) 다음 코드에 나와 있는 것 처럼 작동 합니다.  
  
```  
ICLRMetaHostPolicy *pMetaHostPolicy = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHostPolicy,  
                   IID_ICLRMetaHostPolicy, (LPVOID*)&pMetaHostPolicy);  
```  
  
> [!NOTE]
>  이 인터페이스를 로드 하거나 CLR, 하지만 기본 CLR 버전 설치 되거나 로드 된 사용 가능한 버전에 따라 반환 활성화 실제로 않습니다.  
  
 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] API를 호스팅하는 특정 요구 사항이 있는 호스트가 헤드 의도 하지 않은 저하 없이 기본 기능을 사용할 수 있도록 정책을 통합 합니다. 예를 들어 다양 한 방법으로 MSCorEE.dll 내보내기에 바인딩됩니다 특정 CLR 메서드 수 필요 하지 않지만 논리적으로 것입니다. [METAHOST_POLICY_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md) 열거형은 대부분의 호스트에 공통적으로 적용 하는 바인딩 정책을 제공 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MetaHost.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [4 및 4.5.NET Framework에 추가 된 CLR 호스팅 인터페이스](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 [호스팅 인터페이스](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [호스팅](../../../../docs/framework/unmanaged-api/hosting/index.md)
