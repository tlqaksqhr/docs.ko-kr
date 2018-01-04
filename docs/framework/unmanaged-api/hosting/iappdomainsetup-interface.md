---
title: "IAppDomainSetup 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IAppDomainSetup
api_location: mscoree.dll
api_type: COM
f1_keywords: IAppDomainSetup
helpviewer_keywords: IAppDomainSetup interface [.NET Framework hosting]
ms.assetid: 1844da85-c031-40bf-bea4-1a3d12a36c8c
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9db1b787015231b3d9053d4ed316cb70c5db96ec
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iappdomainsetup-interface"></a>IAppDomainSetup 인터페이스
구성할 수 있는 속성을 제공는 <xref:System.AppDomain?displayProperty=nameWithType> 유형 호출 하기 전에 [icorruntimehost:: Createdomainex](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) 메서드를 만듭니다.  
  
## <a name="properties"></a>속성  
  
|속성|설명|  
|--------------|-----------------|  
|<xref:System.AppDomainSetup.ApplicationBase%2A>|응용 프로그램을 포함 하는 디렉터리의 이름을 가져오거나 설정 합니다.|  
|<xref:System.AppDomainSetup.ApplicationName%2A>|응용 프로그램의 이름을 가져오거나 설정합니다.|  
|<xref:System.AppDomainSetup.CachePath%2A>|영역 이름을 관련 가져오거나 응용 프로그램에 파일을 섀도 복사 합니다.|  
|<xref:System.AppDomainSetup.ConfigurationFile%2A>|응용 프로그램에 대 한 구성 파일의 이름을 가져오거나 설정 합니다.|  
|<xref:System.AppDomainSetup.DynamicBase%2A>|동적으로 생성 되는 파일 저장 및 액세스 되는 디렉터리의 이름을 가져오거나 설정 합니다.|  
|<xref:System.AppDomainSetup.LicenseFile%2A>|이 도메인과 연결 된 라이선스 파일의 경로 가져오거나 설정 합니다.|  
|<xref:System.AppDomainSetup.PrivateBinPath%2A>|와 결합 하는 디렉터리 목록을 가져오거나 설정 합니다.는 <xref:System.AppDomainSetup.ApplicationBase%2A> 디렉터리를 전용 어셈블리를 조사 합니다.|  
|<xref:System.AppDomainSetup.PrivateBinPathProbe%2A>|포함 또는 제외 하는 문자열 값을 가져오거나 설정 합니다. <xref:System.AppDomainSetup.ApplicationBase%2A> 응용 프로그램에 대 한 검색 경로에서 합니다.|  
|<xref:System.AppDomainSetup.ShadowCopyDirectories%2A>|어셈블리 섀도 복사를 포함 하는 디렉터리의 이름을 가져오거나 설정 합니다.|  
|<xref:System.AppDomainSetup.ShadowCopyFiles%2A>|섀도 복사 설정 되어 있는지 여부 또는 해제 여부를 나타내는 문자열을 가져오거나 설정 합니다. 유효한 값은 "true" 또는 "false"입니다.|  
  
## <a name="remarks"></a>설명  
 `IAppDomainSetup` 인터페이스의 관리 되는 해당 <xref:System.IAppDomainSetup> 인터페이스는 <xref:System.AppDomainSetup> 구현을 입력 합니다. 참조 <xref:System.IAppDomainSetup?displayProperty=nameWithType> 에 대 한 해당 속성에 자세히 설명 합니다.  
  
 `IAppDomainSetup`에 추가할 수 있는 어셈블리 바인딩 정보를 나타내는 <xref:System.AppDomain> 만들어지기 전에 인스턴스. 예를 들어 호스트를 설정할 수는 <xref:System.AppDomainSetup.ApplicationBase%2A> 관리 되는 어셈블리 속성을 공용 언어 런타임 (CLR)를 검색 되는 루트 디렉터리를 설정 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MSCorEE.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.AppDomain>  
 <xref:System.AppDomainSetup>  
 <xref:System.IAppDomainSetup>  
 [호스팅 인터페이스](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
