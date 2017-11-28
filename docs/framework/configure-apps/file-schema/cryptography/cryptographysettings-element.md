---
title: "&lt;cryptographySettings&gt; 요소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptographySettings
helpviewer_keywords:
- cryptographySettings element
- <cryptographySettings> element
ms.assetid: 6201b7da-bcb7-49f7-b9f5-ba1fe05573b9
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 0f023dbc3049f558acfc0fb83056f462d390fa7b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltcryptographysettingsgt-element"></a>&lt;cryptographySettings&gt; 요소
암호화 설정이 포함되어 있습니다.  
  
 \<configuration>  
\<mscorlib >  
\<cryptographySettings >  
  
## <a name="syntax"></a>구문  
  
```xml  
      <cryptographySettings>   
</cryptographySettings>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
 없음  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<cryptoNameMapping >](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptonamemapping-element.md)|이름에 대한 클래스의 매핑이 포함되어 있습니다.|  
|[\<oidMap >](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidmap-element.md)|클래스에 ASN.1 개체 식별자 (OID) 매핑을 포함합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`mscorlib`|포함 된 `cryptographySettings` 요소입니다.|  
  
## <a name="example"></a>예제  
 다음 방법을 보여 주는 예제는  **\<cryptographySettings >** 암호화 이름 매핑 및 OID 매핑을 포함 하는 요소입니다. 이 예제에서는 런타임에 구성 되도록 <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> 반환는 `MyHashClass` 개체 및 `MyCryptoClass` 클래스 1.3.36.2.1 개체 식별자에 매핑됩니다.  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyHash="MyHashClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
               <cryptoClass   MyCrypto="MyCryptoClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="System.Security.Cryptography.HashAlgorithm"  
                       class="MyHash"/>  
         </cryptoNameMapping>  
         <oidMap>  
            <oidEntry OID="1.3.36.3.2.1"   name="MyCryptoClass"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목  
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [암호화 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 [암호화 서비스](../../../../../docs/standard/security/cryptographic-services.md)
