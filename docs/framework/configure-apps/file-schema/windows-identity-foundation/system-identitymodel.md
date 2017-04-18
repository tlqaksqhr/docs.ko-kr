---
title: "&lt;system.identityModel&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 210ce7e9-d07b-400c-800f-5f525dcf95e8
caps.latest.revision: 5
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 5
---
# &lt;system.identityModel&gt;
응용 프로그램에서 Windows Identity 파운데이션 \(싸 우 자\) 옵션을 사용 하는 구성을 제공 합니다.  
  
 \<system.identityModel\>  
  
## 구문  
  
```  
<system.identityModel>  
</system.identityModel>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
 없음  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|서비스 수준 id 설정을 지정합니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|`<configuration>`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
  
## 설명  
 추가 된 `<system.identityModel>` 서비스 또는 Windows Identity 파운데이션 \(싸 우 자\)를 사용 하는 응용 프로그램을 구성 하는 구성 파일의 섹션입니다.  `<system.identityModel>` 요소가 표시 되는 <xref:System.IdentityModel.Configuration.SystemIdentityModelSection> 클래스입니다.  
  
## 예제  
 추가 하는 방법 다음 예제는 `<system.identityModel>` 구성 파일의 섹션.  먼저 아래 구성 섹션 및 네임 스페이스 선언을 추가 해야 해당 `<configSections>` 요소입니다.  추가 하 여 다음의 `<system.IdentityModel>` 구성 파일 지정할 하나 이상의 identity 구성 요소입니다.  
  
```  
<configuration>  
  <configSections>  
    <!--WIF 4.5 sections -->  
    <section name="system.identityModel" type="System.IdentityModel.Configuration.SystemIdentityModelSection, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089"/>  
    <section name="system.identityModel.services" type="System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089"/>  
  </configSections>  
  
  ...  
  
  <system.identityModel>  
    <identityConfiguration>  
      <audienceUris>  
        <add value="http://localhost/WebApplication1/" />  
      </audienceUris>  
      <issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089">  
        <trustedIssuers>  
          <add thumbprint="313D3B … 9106A9EC" name="SelfSTS" />  
        </trustedIssuers>  
      </issuerNameRegistry>  
      <certificateValidation certificateValidationMode="None"/>  
    </identityConfiguration>  
  </system.identityModel>  
  
  ...  
  
</configuration>  
```  
  
## 참고 항목  
 <xref:System.IdentityModel.Configuration.SystemIdentityModelSection>