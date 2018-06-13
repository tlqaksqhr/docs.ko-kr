---
title: ICLRMetaHost 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRMetaHost
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost
helpviewer_keywords:
- ICLRMetaHost interface [.NET Framework hosting]
ms.assetid: c627fcdd-fc4f-4b1c-8e91-df8536f627d8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9e4db5f3c7deb300a9666182cb6b712eacf42cfa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436230"
---
# <a name="iclrmetahost-interface"></a>ICLRMetaHost 인터페이스
특정 버전의 공용 언어 런타임 (CLR) 버전 번호에 따라 반환, 모든 설치 된 Clr 목록, 지정된 된 프로세스에 로드 되는 모든 런타임 목록, 어셈블리로 컴파일, 프로세스를 종료 하는 데 사용 된 CLR 버전을 검색 하는 메서드를 제공 합니다. 정상적인 런타임 종료 및 레거시 API 바인딩을 쿼리 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[EnumerateInstalledRuntimes 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-enumerateinstalledruntimes-method.md)|유효한를 포함 하는 열거형을 반환 [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) 하는 컴퓨터에 설치 되어 있는 각 CLR 버전에 대 한 인터페이스 포인터입니다.|  
|[EnumerateLoadedRuntimes 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-enumerateloadedruntimes-method.md)|유효한를 포함 하는 열거형을 반환 [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) 지정된 된 프로세스에 로드 된 각 CLR에 대 한 인터페이스 포인터입니다. 이 메서드를 대체 [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)합니다.|  
|[ExitProcess 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md)|모든 로드 된 런타임을 정상적으로 종료 하 고 프로세스를 종료 합니다. 대체는 [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md) 함수입니다.|  
|[GetRuntime 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getruntime-method.md)|가져옵니다는 [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) 특정 CLR 버전에 해당 하는 인터페이스입니다. 이 메서드를 대체는 [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) 사용한 함수는 [STARTUP_LOADER_SAFEMODE](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) 플래그입니다.|  
|[GetVersionFromFile 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getversionfromfile-method.md)|어셈블리의.NET Framework 컴파일 원본이 (메타 데이터에 저장 됨)을 지정 된 파일 경로 가져옵니다. 이 메서드를 대체 [GetFileVersion](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md)합니다.|  
|[QueryLegacyV2RuntimeBinding 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-querylegacyv2runtimebinding-method.md)|레거시 활성화 정책이 바인딩된, 예를 사용 하 여 런타임을 나타내는 인터페이스를 반환 된 `useLegacyV2RuntimeActivationPolicy` 특성에 [ \<시작 > 요소](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) 직접 사용 하 여 구성 파일 항목 레거시 활성화 Api 호출 하거나는 [iclrruntimeinfo:: Bindaslegacyv2runtime](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-bindaslegacyv2runtime-method.md) 메서드.|  
|[RequestRuntimeLoadedNotification 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-requestruntimeloadednotification-method.md)|CLR 버전은 처음 로드 되었지만 아직 시작 되지 않았을 때 지정 된 함수 포인터에 대 한 콜백을 보장 합니다. 이 메서드를 대체 [LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)|  
  
## <a name="remarks"></a>설명  
 유일한 방법은이 인터페이스의 인스턴스를 호출 하 여 것은 [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) 다음과 같이 작동 합니다.  
  
```  
ICLRMetaHost *pMetaHost = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHost,  
                   IID_ICLRMetaHost, (LPVOID*)&pMetaHost);  
```  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MetaHost.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [호스팅 인터페이스](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [호스팅](../../../../docs/framework/unmanaged-api/hosting/index.md)
