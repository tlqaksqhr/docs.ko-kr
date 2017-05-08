---
title: "&lt;securityTokenHandlerConfiguration&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
caps.latest.revision: 8
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 8
---
# &lt;securityTokenHandlerConfiguration&gt;
토큰 처리기의 컬렉션에 대 한 구성을 제공합니다.  
  
## 구문  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration saveBootstrapContext=xs:boolean  
          maximumClockSkew=TimeSpan>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|saveBootstrapContext|부트스트랩 하는 토큰의 세션 토큰이 포함 되는지 여부를 지정 합니다.  값을 설정 하 여도 토큰 처리기 컬렉션에 설정할 수 있습니다는 `saveBootstrapContext` 특성에 있는 [\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) 요소입니다.  토큰 처리기 컬렉션에 설정한 값은 서비스에 설정 된 값 보다 우선 합니다.|  
|maximumClockSkew|A <xref:System.TimeSpan> 는 허용 되는 최대 클럭 기울이기를 지정 합니다.  허용 되는 최대 클럭 기울이기 로그인 세션의 만료 시간을 확인 하는 것과 같은 시간에 민감한 작업을 수행 하는 경우를 제어 합니다.  기본값은 5 분입니다 "00: 05: 00"입니다.  지정 하는 방법에 대 한 자세한 내용은 <xref:System.TimeSpan> 값을 참조 하십시오. [Timespan Values](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md#BKMK_TimespanValues).  최대 시계 기울이기를 서비스 수준에서 설정 하 여 설정 해야는 `maximumClockSkew` 특성에 있는 [\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) 요소.  토큰 처리기 컬렉션에 설정한 값은 서비스에 설정 된 값 보다 우선 합니다.|  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[\<audienceUris\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/audienceuris.md)|식별자는 상대가이 허용 되는 Uri 집합을 지정 합니다.  선택적 요소.|  
|[\<caches\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|세션 토큰 및 토큰 재생 검색에 사용 되는 캐시를 등록 합니다.  보안 토큰 처리기 컬렉션 또는 서비스 수준에서 지정할 수 있습니다.  선택적 요소.|  
|[\<certificateValidation\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|토큰 처리기를 사용 하 여 인증서의 유효성을 검사 하는 설정을 제어 합니다.  보안 토큰 처리기 컬렉션 또는 서비스 수준에서 지정할 수 있습니다.  특정 처리기 자체 유효성 검사기로 구성 된 경우이 설정은 무시 됩니다.  선택적 요소.|  
|[\<issuerNameRegistry\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)|발급자 이름 레지스트리 사용 하 여 컬렉션에 있는 토큰 처리기 처리기를 구성 합니다.  선택적 요소.|  
|[\<issuerTokenResolver\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuertokenresolver.md)|사용 하 여 컬렉션에 있는 토큰 처리기 처리기 발급자 토큰 확인자를 등록 합니다.  토큰 확인 자가 발급자는 들어오는 토큰 및 메시지 서명 토큰을 확인 하는 데 사용 됩니다.  선택적 요소.|  
|[\<serviceTokenResolver\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicetokenresolver.md)|토큰 처리기 컬렉션에 대 한 처리기에서 사용 되는 서비스 토큰 확인자를 등록 합니다.  토큰 확인자 서비스는 들어오는 토큰 및 메시지 암호화 토큰을 확인 하는 데 사용 됩니다.  선택적 요소.|  
|[\<tokenReplayDetection\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)|토큰 재생 검색을 사용 하 고 토큰에 대 한 만료 시간을 지정 합니다.  보안 토큰 처리기 컬렉션 또는 서비스 수준에서 지정할 수 있습니다.  선택적 요소.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<securityTokenHandlers\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|끝점을 등록 하는 보안 토큰 처리기의 컬렉션을 지정 합니다.|  
  
## 설명  
 이 단원에서는 속성 값을 제공 된 <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> 개체.  이 섹션의 구성 설정 서비스에 구성 된 설정을 무시 합니다.  이러한 설정 중 일부 처리기 보안 토큰 처리기 컬렉션에 추가 될 때 지정 된 설정을 통해 결과적으로 재정의 될 수 있습니다.  
  
## 예제  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>   
      <securityTokenHandlerConfiguration>  
  
        <audienceUris>  
          <clear/>  
          <add value="http://www.example.com/myapp/" />  
        </audienceUris>  
  
        <issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel">  
          <trustedIssuers>  
            <add thumbprint="97249e1a … 4c9158de" name="contoso.com" />  
          </trustedIssuers>  
        </issuerNameRegistry>  
  
        <issuerTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
  
        <serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```