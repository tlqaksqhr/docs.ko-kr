---
title: ICLRDomainManager::SetAppDomainManagerType 메서드
ms.date: 03/30/2017
api_name:
- ICLRDomainManager.SetAppDomainManagerType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDomainManager::SetAppDomainManagerType
helpviewer_keywords:
- SetAppDomainManagerType method, ICLRDomainManager interface [.NET Framework hosting]
- ICLRDomainManager::SetAppDomainManagerType method [.NET Framework hosting]
ms.assetid: ee91abb0-cb74-41dd-927b-e117fb8ffdf4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ea10f9b7d23d8ca6a94d05cac6e586b434c000d5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="iclrdomainmanagersetappdomainmanagertype-method"></a>ICLRDomainManager::SetAppDomainManagerType 메서드
파생 된 형식을 지정 된 <xref:System.AppDomainManager?displayProperty=nameWithType> 기본 응용 프로그램 도메인을 초기화 하는 데 사용할 응용 프로그램 도메인 관리자의 클래스입니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT SetAppDomainManagerType(  
    [in] LPCWSTR wszAppDomainManagerAssembly,  
    [in] LPCWSTR wszAppDomainManagerType,  
    [in] EInitializeNewDomainFlags dwInitializeDomainFlags  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `wszAppDomainManagerAssembly`  
 [in] 응용 프로그램 도메인 관리자 형식을; 포함 하는 어셈블리의 표시 이름 예: "AdMgrExample, Version = 1.0.0.0, Culture = neutral, PublicKeyToken = 6856bccf150f00b3"입니다.  
  
 `wszAppDomainManagerType`  
 [in] 네임 스페이스를 포함 하는 응용 프로그램 도메인 관리자의 형식 이름입니다.  
  
 `dwInitializeDomainFlags`  
 [in] 조합을 [EInitializeNewDomainFlags](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md) 응용 프로그램 도메인 관리자에 대 한 정보를 제공 하는 열거형 값입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|메서드가 완료되었습니다.|  
|HOST_E_CLRNOTAVAILABLE|공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.|  
  
## <a name="remarks"></a>설명  
 현재 유일한 정의 대 한 값 `dwInitializeDomainFlags` 은 `eInitializeNewDomainFlags_NoSecurityChanges`, 공용 언어 런타임 (CLR)을 설정 하는 응용 프로그램 도메인 관리자 실행 하는 동안 보안 설정을 수정 하지 것입니다이 알려주는 <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> 메서드. 이렇게 하면 조건부가 있는 어셈블리 로드를 최적화 하기 위해 CLR <xref:System.Security.AllowPartiallyTrustedCallersAttribute> 특성 (APTCA). 이 어셈블리 집합의 전이적 closure 크면 시작 시간에 크게 향상 될 수 있습니다.  
  
> [!IMPORTANT]
>  호스트를 지정 하는 경우 `eInitializeNewDomainFlags_NoSecurityChanges` 응용 프로그램 도메인 관리자에 대 한는 <xref:System.InvalidOperationException> 응용 프로그램 도메인의 보안을 수정 하 려 하는 경우에 throw 됩니다.  
  
 호출 된 [iclrcontrol:: Setappdomainmanagertype](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)호출 하는 것과 같습니다 `ICLRDomainManager::SetAppDomainManagerType` 와 `eInitializeNewDomainFlags_None`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** MetaHost.h  
  
 **라이브러리:** MSCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [호스팅](../../../../docs/framework/unmanaged-api/hosting/index.md)  
 [ICLRDomainManager 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)  
 [EInitializeNewDomainFlags 열거형](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md)
