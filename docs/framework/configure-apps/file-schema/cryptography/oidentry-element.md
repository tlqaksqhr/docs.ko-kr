---
title: "&lt;oidEntry&gt; 요소 | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/oidMap/oidEntry"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#oidEntry"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<oidEntry> 요소"
  - "oidEntry 요소"
ms.assetid: 22fb88b0-bf27-489c-9ca0-e65950ac136c
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# &lt;oidEntry&gt; 요소
ASN.1 OID\(Object Identifier\)를 이름에 매핑합니다.  
  
## 구문  
  
```  
<oidEntry OID="object identifier number" name="friendly name" />  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|**OID**|필수 특성입니다.<br /><br /> 사용자의 클래스가 구현하는 알고리즘에 대응하는 ASN.1 OID를 지정합니다.|  
|**name**|필수 특성입니다.<br /><br /> **이름**특성의 값을 지정합니다. 이 특성은 [\<nameEntry\>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) 태그에 있습니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`cryptographySettings`|암호화 설정이 포함됩니다.|  
|`mscorlib`|`cryptographySettings` 요소를 포함합니다.|  
|`oidMap`|ASN.1 OID\(Object Identifier\)와 클래스의 매핑이 포함됩니다.|  
  
## 설명  
 ASN.1 개체 식별자는 일부 암호화 형식에서 알고리즘을 식별합니다.  식별할 알고리즘의 이름에 개체 식별자를 매핑할 수 있습니다.  개체 식별자에 대한 자세한 내용은 MSDN Library를 참조하십시오.  
  
## 예제  
 다음 예제에서는 **\<oidEntry\>** 요소를 사용하여 RIPEMD\-160 해시 알고리즘의 개체 식별자를 해당 해시 알고리즘의 구현에 매핑하는 방법을 보여 줍니다.  
  
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
            <oidEntry OID="1.3.36.3.2.1"   name="MyCryptoClass"/>  
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