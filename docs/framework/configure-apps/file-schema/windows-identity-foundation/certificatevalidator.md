---
title: "&lt;certificateValidator&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 86161897-c20f-4ad8-9d7f-050c247251bf
caps.latest.revision: 6
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 5
---
# &lt;certificateValidator&gt;
인증서 유효성 검사에 대 한 사용자 지정 형식을 지정합니다.  이 이와 같은 경우에 사용 되는 `certificateValidationMode` 의 특성의 [\<certificateValidation\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) 요소 "사용자 지정"으로 설정 됩니다.  
  
## 구문  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <certificateValidation>  
      <certificateValidator type=xs:string>  
      </certificateValidator>  
    </certificateValidation>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|type|파생 되는 사용자 지정 형식 지정은 <xref:System.IdentityModel.Selectors.X509CertificateValidator> 클래스입니다.  설정의 `certificateValidationMode` 의 특성은 [\<certificateValidation\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) 요소에이 형식을 사용 하려면 "Custom".  지정 하는 방법에 대 한 자세한 내용은 `type` 특성, 볼 [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md#BKMK_CustomTypeReferences).  선택적 요소.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<certificateValidation\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|토큰 처리기를 사용 하 여 인증서의 유효성을 검사 하는 설정을 제어 합니다.|  
  
## 예제  
  
```  
<certificateValidation certificateValidationMode="Custom"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine">  
    <certificateValidator type="MyNamespace.CustomValidator, MyAssembly" />    
</certificateValidation>        
```