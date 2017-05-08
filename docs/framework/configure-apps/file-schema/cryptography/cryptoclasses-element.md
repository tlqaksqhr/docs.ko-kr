---
title: "&lt;cryptoClasses&gt; 요소 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/cryptoClasses"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoClasses"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<cryptoClasses> 요소"
  - "cryptoClasses 요소"
ms.assetid: 290d5f96-946d-4f02-babb-1d31ec0b8295
caps.latest.revision: 16
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 15
---
# &lt;cryptoClasses&gt; 요소
[\<nameEntry\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) 요소에 있는 이름에 매핑되는 암호화 클래스의 목록이 포함됩니다.  
  
## 구문  
  
```  
<cryptoClasses>   
</cryptoClasses>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
 없음  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[\<cryptoClass\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md)|**\<nameEntry\>** 요소에 있는 이름에 매핑되는 암호화 클래스가 포함됩니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`cryptographySettings`|암호화 설정이 포함됩니다.|  
|`cryptoNameMapping`|클래스와 이름의 매핑이 포함됩니다.|  
|`mscorlib`|`cryptographySettings` 요소를 포함합니다.|  
  
## 예제  
 다음 예제에서는 **\<cryptoClass\>** 요소를 사용하여 암호화 클래스를 참조하고 런타임을 구성하는 방법을 보여 줍니다.  그런 다음 <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=fullName> 메서드에 문자열 "RSA"를 전달하고 <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> 메서드를 사용하여 `MyCryptoRSAClass` 개체를 반환할 수 있습니다.  
  
```  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCryptoRSA="MyCryptoRSAClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
               <!-- Other cryptography classes go here. -->  
            </cryptoClasses>  
            <nameEntry name="RSA" class="MyCryptoRSA"/>  
            <nameEntry name="System.Security.Cryptography.AsymmetricAlgorithm"  
                       class="MyCryptoRSA"/>  
             <!-- Mappings to other cryptography classes go here. -->  
         </cryptoNameMapping>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## 참고 항목  
 <xref:System.Security.Cryptography>   
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [암호화 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)   
 [암호화 서비스](../../../../../docs/standard/security/cryptographic-services.md)   
 [System.Security.Cryptography.CryptoConfig.CreateFromName](frlrfSystemSecurityCryptographyCryptoConfigClassCreateFromNameTopic)   
 [암호화 클래스 구성](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)