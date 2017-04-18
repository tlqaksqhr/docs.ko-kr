---
title: "개체 식별자를 암호화 알고리즘에 매핑 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "암호화 알고리즘"
  - "암호화, 개체 식별자 매핑"
  - "디지털 서명"
  - "식별자, 개체 식별자 매핑"
  - "개체 식별자 매핑"
ms.assetid: c9673f81-bf9e-47fd-bc6f-6bc1c1c4c15e
caps.latest.revision: 8
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 8
---
# 개체 식별자를 암호화 알고리즘에 매핑
디지털 서명은 데이터가 한 프로그램에서 다른 프로그램으로 보내졌을 때 훼손되지 않도록 보장해 줍니다.  일반적으로 디지털 서명은 서명할 데이터 해시에 수학적인 함수를 적용함으로써 계산됩니다.  서명할 해시 값의 형식을 지정할 때 형식 지정 작업의 일환으로 일부 디지털 서명 알고리즘에 ASN.1 개체 식별자\(OID\)가 추가됩니다.  OID는 해시를 계산할 때 사용했던 알고리즘을 식별합니다.  알고리즘을 개체 식별자에 매핑하여 암호화 메커니즘이 사용자 지정 알고리즘을 사용하도록 확장할 수 있습니다.  다음 예제에서는 개체 식별자를 새로운 해시 알고리즘에 매핑하는 방법을 보여 줍니다.  
  
```  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass MyNewHash="MyNewHashClass, MyAssembly  
                  Culture='en', PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="NewHash" class="MyNewHash"/>  
         </cryptoNameMapping>  
         <oidMap>  
            <oidEntry OID="1.3.14.33.42.46"  name="NewHash"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
 [\<oidEntry\> element](../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md) 는 두 가지 특성을 포함합니다.  **OID**특성은 개체 식별자 번호입니다.  **name**특성은 [\<nameEntry\> 요소](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md)에서 **name** 특성의 값입니다.  개체 식별자를 단순한 이름에 매핑하려면 먼저 알고리즘 이름을 클래스에 매핑해야 합니다.  
  
## 참고 항목  
 [암호화 클래스 구성](../../../docs/framework/configure-apps/configure-cryptography-classes.md)   
 [암호화 서비스](../../../docs/standard/security/cryptographic-services.md)