---
title: "&lt;cookieHandler&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: bfdc127f-8d94-4566-8bef-f583c6ae7398
caps.latest.revision: 5
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 5
---
# &lt;cookieHandler&gt;
구성의 <xref:System.IdentityModel.Services.CookieHandler> 에 <xref:System.IdentityModel.Services.SessionAuthenticationModule> \(SAM\)를 사용 하 여 읽기 및 쓰기 쿠키.  
  
## 구문  
  
```  
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
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|name|기록 되는 쿠키에 대 한 기본 이름을 지정 합니다.  기본값은 "FedAuth"입니다.|  
|path|작성 된 모든 쿠키의 경로 값을 지정 합니다.  기본값은 "HttpRuntime.AppDomainAppVirtualPath"입니다.|  
|mode|중 하나는 <xref:System.IdentityModel.Services.CookieHandlerMode> 쿠키 처리기를 사용 하 여 SAM의 종류를 지정 하는 값입니다.  다음 값을 사용할 수 있습니다.<br /><br /> -   "기본"\-"청크"와 같은.<br />-   "청크 분할"\-인스턴스를 사용 하 여 <xref:System.IdentityModel.Services.ChunkedCookieHandler> 클래스입니다.  이 쿠키 처리기 개별 쿠키 설정 된 최대 크기를 초과 하지 않도록 보장 합니다.  잠재적으로 "하나의 논리 쿠키 쿠키 와이어의 숫자로 청크 에서" 수행 합니다.<br />-   "사용자 지정" 등에서 파생 된 사용자 지정 클래스의 인스턴스를 사용 하 여 <xref:System.IdentityModel.Services.CookieHandler>.  파생된 클래스에서 참조 되는 `<customCookieHandler>` 자식 요소입니다.<br /><br /> 기본값은 "기본"입니다.|  
|persistentSessionLifetime|영구 세션의 수명을 지정합니다.  0 이면 임시 세션 항상 사용 됩니다.  기본값은 "임시 세션을 지정 하는 0"에 있습니다.  "365 일 세션을 지정 하는 365:0:0", 최대 값을입니다.  값에 따라 다음과 같은 제한을 지정 해야: `<xs:pattern value="([0-9.]+:){0,1}([0-9]+:){0,1}[0-9.]+" />`, 어디 날 왼쪽에 있는 값을 지정, 시간, 중간 값 \(있는 경우\)를 지정 및 분 오른쪽 값 \(있는 경우\)을 지정 합니다.|  
|requireSsl|"보안" 플래그 작성에 대 한 모든 쿠키 생성 될 여부를 지정 합니다.  이 값이 설정 되어 있으면 로그인 세션 쿠키만 HTTPS를 통해 사용할 수 있습니다.  기본값은 "true"입니다.|  
|hideFromScript|"HttpOnly" 플래그 작성에 대 한 모든 쿠키 생성 될 여부를 제어 합니다.  특정 웹 브라우저 쿠키 값 액세스에서 클라이언트측 스크립트를 유지 하 여이 플래그를 우선시 합니다.  기본값은 "true"입니다.|  
|domain|작성 한 쿠키의 도메인 값입니다.  기본값은 ""입니다.|  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[\<chunkedCookieHandler\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/chunkedcookiehandler.md)|구성의 <xref:System.IdentityModel.Services.ChunkedCookieHandler>.  만이 요소가 있을 수 있습니다 경우는 `mode` 의 특성은 `<cookieHandler>` 요소인 "Default" 또는 "청크 분할".|  
|[\<customCookieHandler\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/customcookiehandler.md)|사용자 지정 쿠키 처리기 형식을 설정합니다.  이 요소가 있어야 경우는 `mode` 의 특성은 `<cookieHandler>` 요소인 "Custom".  다른 값에 대해 있을 수 있는 `mode` 특성.  지정 된 형식에서 파생 되어야 합니다는 <xref:System.IdentityModel.Services.CookieHandler> 클래스입니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<federationConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|구성 설정이 포함의 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> \(WSFAM\)와 <xref:System.IdentityModel.Services.SessionAuthenticationModule> \(SAM\).|  
  
## 설명  
 <xref:System.IdentityModel.Services.CookieHandler> 수준 읽기 및 쓰기 원시 쿠키에는 HTTP 프로토콜을 담당 합니다.  하나를 구성할 수 있습니다는 <xref:System.IdentityModel.Services.ChunkedCookieHandler> 또는 파생 된 사용자 지정 쿠키 처리기는 <xref:System.IdentityModel.Services.CookieHandler> 클래스.  
  
 청크 분할된 쿠키 처리기를 구성 하려면 "청크" 또는 "기본" 모드 특성을 설정 합니다.  기본 청크 크기가 2000 바이트 이지만 포함 하 여 다른 청크 크기를 선택적으로 지정할 수 있습니다 한 `<chunkedCookieHandler>` 자식 요소입니다.  
  
 쿠키를 사용자 지정 처리기를 구성 하려면 "사용자 지정" 모드 특성을 설정 합니다.  또한 지정 해야는 `<customCookieHandler>` 의 사용자 지정 처리기 형식을 참조 하는 자식 요소입니다.  
  
 `<cookieHandler>` 요소가 표시 되는 <xref:System.IdentityModel.Services.CookieHandlerElement> 클래스입니다.  구성에 지정 된 쿠키 처리기에서 사용할 수 있는 <xref:System.IdentityModel.Services.Configuration.FederationConfiguration.CookieHandler%2A> 속성의는 <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> 개체에 설정는 <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=fullName> 속성.  
  
## 예제  
 다음 XML 표시는 `<cookieHandler>` 요소입니다.  이 예제에서는 때문에 `mode` 속성이 지정 되지 않은 경우 기본 쿠키 처리기 SAM에서 사용 됩니다.  이의 인스턴스는 <xref:System.IdentityModel.Services.ChunkedCookieHandler> 클래스입니다.  때문에 `<chunkedCookieHandler>` 자식 요소가 지정 되지 않은 경우 기본 청크 크기 사용 됩니다.  HTTPS 되지 않습니다 필요 하기 때문에 `requireSsl` 특성이 설정 되어 `false`.  
  
> [!WARNING]
>  이 예제에서는 HTTPS 세션 쿠키를 쓸 필요는 없습니다.  이 있기 때문입니다 있는 `requireSsl` 특성에 `<cookieHandler>` 요소 설정 되어 `false`.  이 설정은 대부분의 프로덕션 환경에 대 한 권장에 따라이 보안 위험이 존재할 수 있습니다.  
  
```  
<cookieHandler requireSsl="false" />  
```  
  
## 참고 항목  
 <xref:System.IdentityModel.Services.CookieHandler>   
 <xref:System.IdentityModel.Services.ChunkedCookieHandler>   
 <xref:System.IdentityModel.Services.SessionAuthenticationModule>