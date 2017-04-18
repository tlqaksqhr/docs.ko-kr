---
title: "&lt;oidMap&gt; 요소 | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#oidMap"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/oidMap"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<oidMap> 요소"
  - "oidMap 요소"
ms.assetid: 7f0c2246-c070-4748-b96a-2f66a296c539
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# &lt;oidMap&gt; 요소
ASN.1 OID\(Object Identifier\)와 클래스의 매핑이 포함됩니다.  
  
## 구문  
  
```  
<oidMap>   
</oidMap>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
 없음  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[\<oidEntry\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md)|ASN.1 OID를 이름에 매핑합니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`cryptographySettings`|암호화 설정이 포함됩니다.|  
|`mscorlib`|`cryptographySettings`  요소를 포함합니다.|  
  
## 예제  
 다음 예제에서는 **\<oidMap\>** 요소를 사용하여 RIPEMD\-160 해시 알고리즘의 OID와 해당 해시 알고리즘 구현의 매핑을 포함하는 방법을 보여 줍니다.  
  
```  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCrypto="MyCryptoClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="RIPEMD-160" class="MyCrypto"/>  
         </cryptoNameMapping>  
         <oidMap>  
            <oidEntry OID="1.3.36.3.2.1"  name="MyCryptoClass"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## 참고 항목  
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [암호화 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)   
 [암호화 서비스](../../../../../docs/standard/security/cryptographic-services.md)   
 [암호화 클래스 구성](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)   
 [개체 식별자를 암호화 알고리즘에 매핑](../../../../../docs/framework/configure-apps/map-object-identifiers-to-cryptography-algorithms.md)