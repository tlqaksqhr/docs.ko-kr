---
title: "ICorRuntimeHost 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorRuntimeHost
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorRuntimeHost
helpviewer_keywords: ICorRuntimeHost interface [.NET Framework hosting]
ms.assetid: 4369533d-7834-4497-bc37-bfea0ad737b1
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 844648cd2cfafc561e27bea870703ee3a55fb404
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icorruntimehost-interface"></a>ICorRuntimeHost 인터페이스
시작 하 고를 만들고 기본 도메인에 액세스 하 고 프로세스에서 실행 중인 모든 도메인을 열거 하는 응용 프로그램 도메인을 구성 하려면 공용 언어 런타임 (CLR)를 명시적으로 중지할 호스트를 사용할 수 있는 메서드를 제공 합니다.  
  
 .NET Framework 버전 2.0에서에서이 인터페이스는 의해 대체 [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[CloseEnum 메서드](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-closeenum-method.md)|도메인 목록의 시작 부분으로 다시 도메인 열거자를 설정 합니다.|  
|[CreateDomain 메서드](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md)|응용 프로그램 도메인을 만듭니다. 호출자가 형식의 인터페이스 포인터를 받을 <xref:System._AppDomain> 형식의 인스턴스로 <xref:System.AppDomain?displayProperty=nameWithType>합니다.|  
|[CreateDomainEx 메서드](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md)|응용 프로그램 도메인을 만듭니다. 이 메서드를 사용 하면 호출자가 반환 된 추가 기능을 구성을 IAppDomainSetup 인스턴스를 전달 하 여 <xref:System._AppDomain> 인스턴스.|  
|[CreateDomainSetup 메서드](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainsetup-method.md)|형식의 인터페이스 포인터를 가져옵니다 `IAppDomainSetup` 에 <xref:System.AppDomainSetup> 인스턴스. `IAppDomainSetup`만들기 전에 응용 프로그램 도메인의 측면을 구성 하는 메서드를 제공 합니다.|  
|[CreateEvidence 메서드](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md)|형식의 인터페이스 포인터를 가져옵니다 <xref:System.Security.Principal.IIdentity>, 보안 증명 정보에 전달할를 만들 호스트를 허용 하는 [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) 또는 [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md)합니다.|  
|[CreateLogicalThreadState 메서드](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createlogicalthreadstate-method.md)|사용하지 마십시오.|  
|[CurrentDomain 메서드](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-currentdomain-method.md)|형식의 인터페이스 포인터를 가져옵니다 <xref:System._AppDomain> 현재 스레드에서 로드 도메인을 나타내는입니다.|  
|[DeleteLogicalThreadState 메서드](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-deletelogicalthreadstate-method.md)|사용하지 마십시오.|  
|[EnumDomains 메서드](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-enumdomains-method.md)|현재 프로세스에서 도메인에 대 한 열거자를 가져옵니다.|  
|[GetConfiguration 메서드](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-getconfiguration-method.md)|호스트가 CLR의 콜백 구성을 지정할 수 있도록 하는 개체를 가져옵니다.|  
|[GetDefaultDomain 메서드](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-getdefaultdomain-method.md)|형식의 인터페이스 포인터를 가져옵니다 <xref:System._AppDomain> 현재 프로세스에 대 한 기본 도메인을 나타내는입니다.|  
|[LocksHeldByLogicalThread 메서드](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-locksheldbylogicalthread-method.md)|사용하지 마십시오.|  
|[MapFile 메서드](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-mapfile-method.md)|지정된 된 파일을 메모리에 매핑합니다. 이 메서드는 사용되지 않습니다.|  
|[NextDomain 메서드](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-nextdomain-method.md)|다음 도메인으로 열거형에 대 한 인터페이스 포인터를 가져옵니다.|  
|[Start 메서드](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-start-method.md)|CLR을 시작합니다.|  
|[Stop 메서드](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-stop-method.md)|현재 프로세스에 대해 런타임에서 코드의 실행을 중지합니다.|  
|[SwitchInLogicalThreadState 메서드](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-switchinlogicalthreadstate-method.md)|사용하지 마십시오.|  
|[SwitchOutLogicalThreadState 메서드](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-switchoutlogicalthreadstate-method.md)|사용하지 마십시오.|  
|[UnloadDomain 메서드](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-unloaddomain-method.md)|현재 프로세스에서 지정 된 응용 프로그램 도메인을 언로드합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:** 1.0, 1.1  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.AppDomain>  
 [호스팅](../../../../docs/framework/unmanaged-api/hosting/index.md)  
 [ICLRRuntimeHost 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)  
 [런타임 호스트](http://msdn.microsoft.com/en-us/99d9246a-b994-4fe5-985c-8588d1d59998)  
 [호스팅 인터페이스](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [CorRuntimeHost Coclass](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
