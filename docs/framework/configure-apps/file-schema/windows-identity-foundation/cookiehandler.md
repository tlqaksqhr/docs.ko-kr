---
title: '&lt;cookieHandler&gt;'
ms.date: 03/30/2017
ms.assetid: bfdc127f-8d94-4566-8bef-f583c6ae7398
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 7fcdf1e89c3b68daa36ee80fe7234737c61a5a3c
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltcookiehandlergt"></a>&lt;cookieHandler&gt;
구성에서 <xref:System.IdentityModel.Services.CookieHandler> 하는 <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) 읽기 / 쓰기 쿠키를 사용 하 여 합니다.  
  
 \<system.identityModel.services >  
\<federationConfiguration >  
\<cookieHandler >  
  
## <a name="syntax"></a>구문  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <cookieHandler name=xs:string  
        path=Path  
        mode="Chunked||Custom||Default"  
        persistentSessionLifetime=xs:string  
        hideFromScript=xs:boolean  
        requireSSL=xs:boolean  
        domain=xs:string  
      <chunkedCookieHandler size=xs:int />  
      <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
    </cookieHandler>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|name|작성 된 쿠키에 대 한 기본 이름을 지정 합니다. 기본값은 "FedAuth".|  
|path|작성 된 쿠키에 대 한 경로 값을 지정 합니다. 기본값은 "HttpRuntime.AppDomainAppVirtualPath".|  
|모드|중 하나는 <xref:System.IdentityModel.Services.CookieHandlerMode> SAM 사용 하는 쿠키 처리기의 종류를 지정 하는 값입니다. 다음 값을 사용할 수 있습니다.<br /><br /> -"Default"-"Chunked"와 동일 합니다.<br />-"청크 방식"-에서 사용 하는 <xref:System.IdentityModel.Services.ChunkedCookieHandler> 클래스입니다. 이 쿠키 처리기 개별 쿠키 설정 된 최대 크기를 초과 하지 않는 것을 보장 합니다. 잠재적으로 "청크" 하나의 논리 쿠키 여러 개의 쿠키 실시간으로 하 여 수행 합니다.<br />-"Custom"-에서 파생 된 사용자 지정 클래스의 인스턴스를 사용 하 여 <xref:System.IdentityModel.Services.CookieHandler>합니다. 파생된 클래스에서 참조 되는 `<customCookieHandler>` 자식 요소입니다.<br /><br /> 기본값은 "Default"입니다.|  
|persistentSessionLifetime|영구 세션의 수명을 지정합니다. 0 이면 임시 세션 항상 사용 됩니다. 기본값은 "0:0:0" 임시 세션을 지정 합니다. 최대 값은 "365:0:0" 365 일의 세션을 지정 합니다. 다음과 같은 제한 사항이 따라 값을 지정 해야: `<xs:pattern value="([0-9.]+:){0,1}([0-9]+:){0,1}[0-9.]+" />`, 여기서 일 수를 지정 하는 왼쪽 값, 중간 값 (있는 경우) 지정 시간 및 분을 지정 하는 오른쪽 값 (있는 경우).|  
|RequireSsl|작성 된 쿠키에 대 한 "Secure" 플래그는 내보내집니다 있는지 여부를 지정 합니다. 이 값은 설정 로그인 세션 쿠키 내용을 HTTPS를 통해 사용할 수만 있습니다. 기본값은 "true"입니다.|  
|hideFromScript|작성 된 쿠키에 대 한 "HttpOnly" 플래그는 내보내집니다 있는지 여부를 제어 합니다. 특정 웹 브라우저 쿠키 값에 액세스할 수 없게 클라이언트 쪽 스크립트를 유지 하 여이 플래그를 인식 합니다. 기본값은 "true"입니다.|  
|도메인|작성 된 쿠키에 대 한 도메인 값입니다. 기본값은 ""입니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<chunkedCookieHandler >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/chunkedcookiehandler.md)|구성에서 <xref:System.IdentityModel.Services.ChunkedCookieHandler>합니다. 이 요소를 사용할 수만 있습니다 하는 경우는 `mode` 특성에는 `<cookieHandler>` 요소는 "Default" 또는 "청크 방식"입니다.|  
|[\<customCookieHandler >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/customcookiehandler.md)|사용자 지정 쿠키 처리기 유형을 설정합니다. 이 요소가 있어야 하는 경우는 `mode` 의 특성은 `<cookieHandler>` 요소는 "Custom"입니다. 다른 값에 있을 수 없습니다는 `mode` 특성입니다. 사용자 지정 형식에서 파생 되어야 합니다는 <xref:System.IdentityModel.Services.CookieHandler> 클래스입니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<federationConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|구성 하는 설정이 포함 된 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) 및 <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).|  
  
## <a name="remarks"></a>설명  
 <xref:System.IdentityModel.Services.CookieHandler> 는 읽기 및 쓰기 원시 쿠키는 http 프로토콜 수준에 대해 책임이 있습니다. 구성할 수 있습니다는 <xref:System.IdentityModel.Services.ChunkedCookieHandler> 또는에서 파생 된 사용자 지정 쿠키 처리기는 <xref:System.IdentityModel.Services.CookieHandler> 클래스입니다.  
  
 청크 분할된 쿠키가 처리기를 구성 하려면 "이 Chunked" 또는 "Default"를 모드 특성을 설정 합니다. 기본 청크 크기는 2000 바이트를 포함 하 여 필요에 따라 다른 청크 크기를 지정할 수 있지만 한 `<chunkedCookieHandler>` 자식 요소입니다.  
  
 사용자 지정 쿠키 처리기를 구성 하려면 mode 특성을 "Custom"를 설정 합니다. 도 지정 해야는 `<customCookieHandler>` 사용자 지정 오류 처리기의 형식을 참조 하는 자식 요소입니다.  
  
 `<cookieHandler>` 에서 요소가 표시 되는 <xref:System.IdentityModel.Services.CookieHandlerElement> 클래스입니다. 구성에 지정 된 쿠키 처리기는에서 사용할 수는 <xref:System.IdentityModel.Services.Configuration.FederationConfiguration.CookieHandler%2A> 의 속성은 <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> 에 설정 하는 개체는 <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> 속성.  
  
## <a name="example"></a>예제  
 XML은 다음 한 `<cookieHandler>` 요소입니다. 이 예제에서는 때문에 `mode` 특성 지정 하지 않으면, 기본 쿠키 처리기 SAM에서 사용 됩니다. 인스턴스는 <xref:System.IdentityModel.Services.ChunkedCookieHandler> 클래스입니다. 때문에 `<chunkedCookieHandler>` 자식 요소를 지정 하지 않으면, 기본 청크 크기 사용 됩니다. HTTPS 됩니다 필요 하기 때문에 `requireSsl` 특성이 설정 되어 `false`합니다.  
  
> [!WARNING]
>  이 예제에서는 HTTPS 세션 쿠키를 작성 하지 않아도 됩니다. 때문에 이것이 `requireSsl` 특성에 `<cookieHandler>` 로 설정 된 `false`합니다. 이 설정은 보안 위험이 있습니다 대로 하지 대부분의 프로덕션 환경에 좋습니다.  
  
```xml  
<cookieHandler requireSsl="false" />  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.IdentityModel.Services.CookieHandler>  
 <xref:System.IdentityModel.Services.ChunkedCookieHandler>  
 <xref:System.IdentityModel.Services.SessionAuthenticationModule>
