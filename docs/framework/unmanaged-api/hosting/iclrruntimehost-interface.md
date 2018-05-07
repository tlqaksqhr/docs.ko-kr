---
title: ICLRRuntimeHost 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost
helpviewer_keywords:
- ICLRRuntimeHost interface [.NET Framework hosting]
ms.assetid: cb0c5f65-3791-47bc-b833-2f84f4101ba5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 95dd084520d1e93803a91f0c4d01214ed0d3744d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="iclrruntimehost-interface"></a>ICLRRuntimeHost 인터페이스
유사한 기능을 제공 된 [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) 다음과 같이 변경 된 버전 1,.NET Framework에서 제공 되는 인터페이스:  
  
-   추가 [SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md) 호스트 컨트롤 인터페이스를 설정 하는 방법은 합니다.  
  
-   제공 하는 몇 가지 방법 중 생략 `ICorRuntimeHost`합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[ExecuteApplication 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md)|ClickOnce 배포 매니페스트 기반 시나리오에서 새 도메인의 활성화 될 응용 프로그램을 지정 하는 데 사용 합니다.|  
|[ExecuteInAppDomain 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeinappdomain-method.md)|지정 된 <xref:System.AppDomain> 지정 된 관리 코드를 실행 하는 합니다.|  
|[ExecuteInDefaultAppDomain 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeindefaultappdomain-method.md)|지정된 된 어셈블리에 지정 된 형식의 지정된 된 메서드를 호출합니다.|  
|[GetCLRControl 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getclrcontrol-method.md)|형식의 인터페이스 포인터를 가져옵니다 [ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) 호스트 공용 언어 런타임 (CLR)의 측면을 사용자 지정 하는 데 사용할 수 있는 합니다.|  
|[GetCurrentAppDomainId 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md)|숫자 식별자를 가져옵니다는 <xref:System.AppDomain> 현재 실행 중인 합니다.|  
|[SetHostControl 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md)|호스트 컨트롤 인터페이스를 설정합니다. 호출 해야 `SetHostControl` 호출 하기 전에 `Start`합니다.|  
|[Start 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)|프로세스에 CLR을 초기화합니다.|  
|[Stop 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-stop-method.md)|런타임에 의해 코드 실행을 중지합니다.|  
|[UnloadAppDomain 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-unloadappdomain-method.md)|언로드는 <xref:System.AppDomain> 지정된 된 숫자 식별자에 해당 하는 합니다.|  
  
## <a name="remarks"></a>설명  
 부터는 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]를 사용 하 여는 [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md) 에 대 한 포인터를 가져올 인터페이스는 [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) 인터페이스를 하 고 호출 하는 [iclrruntimeinfo:: Getinterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md) 에 대 한 포인터를 가져올 메서드를 `ICLRRuntimeHost`합니다. .NET Framework의 이전 버전에서 호스트에 대 한 포인터를 가져옵니다는 `ICLRRuntimeHost` 호출 하 여 인스턴스 [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) 또는 [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)합니다. 를 제공 하기 위해.NET Framework 버전 2.0에서에서 제공 된 기술을의 구현을 사용 해야 `ICLRRuntimeHost` 대신 `ICorRuntimeHost`합니다.  
  
> [!IMPORTANT]
>  호출 하지 마십시오는 [시작](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) 메서드 호출 하기 전에 [ExecuteApplication](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-executeapplication-method.md) 메서드 매니페스트 기반 응용 프로그램을 활성화 합니다. 경우는 `Start` 메서드는 먼저는 `ExecuteApplication` 메서드 호출이 실패 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [CorBindToCurrentRuntime 함수](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)  
 [CorBindToRuntimeEx 함수](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 [ICLRControl 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [ICorRuntimeHost 인터페이스](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)  
 [호스팅 인터페이스](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [CLRRuntimeHost Coclass](../../../../docs/framework/unmanaged-api/hosting/clrruntimehost-coclass.md)
