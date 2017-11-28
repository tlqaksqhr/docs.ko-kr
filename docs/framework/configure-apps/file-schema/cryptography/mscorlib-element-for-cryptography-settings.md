---
title: "&lt;mscorlib&gt; 암호화 설정에 대 한 요소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#mscorlib
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib
helpviewer_keywords:
- mscorlib element
- <mscorlib> element
ms.assetid: d549668f-31f1-4b92-8021-a9135c09ca3c
caps.latest.revision: "13"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 992e62575dccae3f68df27fb7dd027dceab91ffc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltmscorlibgt-element-for-cryptography-settings"></a>&lt;mscorlib&gt; 암호화 설정에 대 한 요소
포함 된 [ \<cryptographySettings > 요소](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md)합니다.  
  
 \<configuration>  
\<mscorlib >  
  
## <a name="syntax"></a>구문  
  
```xml  
      <mscorlib>   
</mscorlib>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
 없음  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`cryptographySettings`|암호화 설정이 포함되어 있습니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
  
## <a name="example"></a>예제  
 사용 하는 방법을 보여 주는 다음 예제는  **\<mscorlib >** 암호화 클래스를 참조 하 고 런타임을 구성 하는 요소입니다. "RSA" 문자열을 전달할 수 있습니다는 <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> 메서드 및 사용법은 <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> 반환 하는 메서드는 `MyCryptoRSAClass` 개체입니다.  
  
```xml  
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
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A>  
 <xref:System.Security.Cryptography>  
 [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [암호화 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 [암호화 서비스](../../../../../docs/standard/security/cryptographic-services.md)  
 [암호화 클래스 구성](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
