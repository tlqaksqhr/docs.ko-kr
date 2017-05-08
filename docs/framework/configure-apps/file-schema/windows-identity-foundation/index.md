---
title: "Windows Identity Foundation 구성 스키마 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4d4f6d76-49a5-4bad-b345-097b2e2844e9
caps.latest.revision: 6
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 6
---
# Windows Identity Foundation 구성 스키마
이 단원의 항목에서는 Windows Identity 파운데이션 \(싸 우 자\)의 구성 스키마에 대 한 정보를 제공합니다.  싸 우 자 사용 하 여 프레임 워크에서 노출 하는 클래스를 통해 응용 프로그램이 구성할 수도 있습니다.  이러한 클래스는 관련 요소를 스키마에서 처리 되는 섹션에서 언급 되어 있습니다.  싸 우 자 구성 스키마에 노출 된 구조를 태그를 기본 XML 다음 보여 줍니다.  특성이 생략 됩니다.  강조 표시 된 주석 스키마의 주요 구성 요소를 나타냅니다.  
  
```  
<system.identityModel>  
    <!-- Service Configuration -->  
    <identityConfiguration>  
        <caches>  
            <sessionSecurityTokenCache />  
            <tokenReplayCache />  
        </caches>  
  
        <certificateValidation>  
            <certificateValidator />   
        </certificateValidation>  
  
        <claimsAuthenticationManager />  
  
        <claimsAuthorizationManager>  
            <optionalConfigurationElement>  
        </claimsAuthorizationManager>  
  
        <claimTypeRequired>  
            <claimType />   
        </claimTypeRequired>  
  
        <tokenReplayDetection />  
  
        <!-- Security Token Handler Collection Configuration -->  
        <securityTokenHandlers>  
            <add>  
                <!-- Can take an optional configuration element which can be one of  
                     the following or a custom element -->  
                <samlSecurityTokenHandlerRequirement>  
                    <nameClaimType>  
                    <roleClaimType>   
                </samlSecurityTokenHandlerRequirement>  
  
                <sessionSecurityTokenHandlerRequirement />  
                <x509SecurityTokenHandlerRequirement />  
                <userNameSecurityTokenHandlerRequirement />  
            </add>  
            <clear />  
            <remove />  
            <securityTokenHandlerConfiguration>  
                <audienceUris>  
                    <add>  
                    <clear>  
                    <remove>  
                </audienceUris>  
  
                <caches>  
                    <sessionSecurityTokenCache />  
                    <tokenReplayCache />  
                </caches>  
  
                <certificateValidation>  
                    <certificateValidator>   
                </certificateValidation>  
  
                <issuerNameRegistry>  
                    <!-- Can take an optional configuration element which can be   
                         the <trustedIssuers> element to configure a configuration-based  
                         issuer name registry or can be a custom element -->  
                    <trustedIssuers>  
                        <add>  
                        <clear>  
                        <remove>  
                    </trustedIssuers>  
                </issuerNameRegistry>  
  
                <issuerTokenResolver />  
                <serviceTokenResolver />  
                <tokenReplayDetection />  
            </securityTokenHandlerConfiguration>  
        </securityTokenHandlers>  
    </identityConfiguration>  
</system.identityModel>  
  
<system.identityModel.services>  
    <!-- Federation Authentication Configuration -->  
    <federatedAuthentication>  
        <cookieHandler>  
            <chunkedCookieHandler />  
            <customCookieHandler />  
        </cookieHandler>  
  
        <serviceCertificate>  
            <certificateReference>  
        </serviceCertificate>  
  
        <wsFederation />  
    </federatedAuthentication>  
</system.identityModel.services>  
```  
  
## 단원 내용  
 [\<system.identityModel\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md)싸 우 자 옵션을 응용 프로그램에서 사용 하는 구성을 제공 합니다.  
  
 [\<system.identityModel.services\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md)싸 우 자 사용 하는 패시브 페더레이션 구성을 제공 합니다.  세션 인증 모듈 \(SAM\) 및 페더레이션된 인증 모듈 \(WSFAM\)를 구성합니다.  
  
## 관련 단원  
 [Configuration, Administration, And Management](http://msdn.microsoft.com/ko-kr/1e03c389-de2c-4096-aaff-86b087e1bea0)싸 우 자 응용 프로그램 및 서비스를 관리 하 고 구성 하는 방법에 설명 합니다.