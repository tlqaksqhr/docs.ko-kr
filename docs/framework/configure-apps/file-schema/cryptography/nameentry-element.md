---
title: "&lt;nameEntry&gt; 요소 | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#nameEntry"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/nameEntry"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<nameEntry> 요소"
  - "nameEntry 요소"
ms.assetid: 7d7535e9-4b4a-4b8c-82e2-e40dff5a7821
caps.latest.revision: 14
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 13
---
# &lt;nameEntry&gt; 요소
클래스 이름을 알고리즘 이름에 매핑하며, 하나의 클래스를 여러 이름에 매핑할 수 있습니다.  
  
## 구문  
  
```  
<nameEntry name="friendly name" Class="class name" />  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|**name**|필수 특성입니다.<br /><br /> 암호화 클래스가 구현하는 알고리즘의 이름을 지정합니다.|  
|**class**|필수 특성입니다.<br /><br /> [\<cryptoClass\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md) 요소에 있는 **name** 특성의 값을 지정합니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`system.web`|ASP.NET 구성 섹션의 루트 요소를 지정합니다.|  
  
## 설명  
 **name** 특성은 <xref:System.Security.Cryptography> 네임스페이스에 있는 추상 클래스 중 하나의 이름일 수 있습니다.  추상 암호화 클래스에 있는 **Create** 메서드를 호출하면 해당 추상 클래스 이름이 [Security.CryptoConfig.CreateFromName](frlrfSystemSecurityCryptographyCryptoConfigClassCreateFromNameTopic) 메서드에 전달됩니다.  **CreateFromName**은 **class** 특성으로 지정된 형식의 인스턴스를 반환합니다.  **name** 특성이 RSA 등의 약식 이름이면 **CreateFromName** 메서드를 호출할 때 이 이름을 사용할 수 있습니다.  
  
## 예제  
 다음 예제에서는 **\<nameEntry\>** 요소를 사용하여 암호화 클래스를 참조하고 런타임을 구성하는 방법을 보여 줍니다.  그런 다음 <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=fullName> 메서드에 문자열 "RSA"를 전달하고 <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> 메서드를 사용하여 `MyCryptoRSAClass` 개체를 반환할 수 있습니다.  
  
```  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCryptoRSA="MyCryptoRSAClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="RSA" class="MyCryptoRSA"/>  
            <nameEntry name="System.Security.Cryptography.AsymmetricAlgorithm"  
                       class="MyCryptoRSA"/>  
         </cryptoNameMapping>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## 참고 항목  
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [암호화 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)   
 [암호화 서비스](../../../../../docs/standard/security/cryptographic-services.md)   
 [암호화 클래스 구성](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)