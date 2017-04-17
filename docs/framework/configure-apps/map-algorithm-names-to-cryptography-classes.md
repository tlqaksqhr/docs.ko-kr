---
title: "알고리즘 이름을 암호화 클래스에 매핑 | Microsoft Docs"
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
  - "암호화, 알고리즘 이름 매핑"
  - "알고리즘 이름 매핑"
  - "이름[.NET Framework], 알고리즘 매핑"
ms.assetid: 01327c69-c5e1-4ef6-b73f-0a58351f0492
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 10
---
# 알고리즘 이름을 암호화 클래스에 매핑
개발자가  [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)]를 사용하여 암호화 개체를 만드는 방법에는 네 가지가 있습니다.  
  
-   **new** 연산자를 사용하여 개체 만들기  
  
-   해당 알고리즘의 추상 클래스에 대해 **Create** 메서드를 호출함으로써 특정 암호화 알고리즘을 구현하는 개체 만들기  
  
-   [System.Security.Cryptography.CryptoConfig.CreateFromName](frlrfSystemSecurityCryptographyCryptoConfigClassCreateFromNameTopic)메서드를 호출함으로써 특정 알고리즘을 구현하는 개체 만들기  
  
-   <xref:System.Security.Cryptography.SymmetricAlgorithm>과 같은 해당 유형 알고리즘의 추상 클래스에 대해 **Create** 메서드를 호출함으로써 대칭 블록 암호와 같은 암호화 알고리즘 클래스를 구현하는 개체 만들기  
  
 예를 들어, 개발자가 일련의 바이트에 대해 SHA1 해시를 계산한다고 가정합시다.  <xref:System.Security.Cryptography> 네임스페이스에는 두 가지 SHA1 알고리즘 구현이 포함되어 있는데, 그 중 하나는 순수하게 관리되는 구현이고 다른 하나는 CryptoAPI를 래핑합니다.  개발자는**new** 연산자를 호출하여 [SHA1Managed 클래스](frlrfSystemSecurityCryptographySHA1ManagedClassTopic)와 같은 특정  SHA1 구현을 인스턴스화할 수 있습니다.  그러나, 공용 언어 런타임에 어떤 클래스가 로드되는지에 관계없이 클래스가 SHA1 해시 알고리즘을 구현하기만 하면 되는 경우라면 개발자는 [System.Security.Cryptography.SHA1.Create](frlrfSystemSecurityCryptographySHA1ClassCreateTopic) 메서드를 호출하여 개체를 만들 수 있습니다.  이메서드는 **System.Security.Cryptography.CryptoConfig.CreateFromName\("System.Security.Cryptography.SHA1"\)**을 호출하는데, 이것은 SHA1 해시 알고리즘을 반환해야 합니다.  
  
 기본적으로 암호화 구성에는 .NET Framework에서 제공하는 알고리즘의 약식 이름이 포함되어 있기 때문에 개발자는 **System.Security.Cryptography.CryptoConfig.CreateFromName\("SHA1"\)**을 호출할 수도 있습니다.  
  
 어떠한 해시 알고리즘을 사용하든지 상관없다면 개발자는 해시 변환을 구현하는 개체를 반환하는 [System.Security.Cryptography.HashAlgorithm.Create](frlrfSystemSecurityCryptographyHashAlgorithmClassCreateTopic)메서드를 호출할 수 있습니다.  
  
## 구성 파일에서 알고리즘 이름 매핑  
 네 가지 시나리오는 모두 런타임에 [System.Security.Cryptography.SHA1CryptoServiceProvider 클래스](frlrfSystemSecurityCryptographySHA1CryptoServiceProviderClassTopic) 개체를 반환하도록 기본 설정되어 있습니다.  그러나 컴퓨터 관리자는 마지막 두 시나리오가 반환하는 개체의 형식을 변경할 수 있습니다.  이렇게 하려면 컴퓨터 구성 파일인 Machine.config에서 알고리즘 이름을 사용할 클래스 이름에 매핑해야 합니다.  
  
 다음 예제에서는 **System.Security.Cryptography.SHA1.Create**, **System.Security.CryptoConfig.CreateFromName\("SHA1"\)** 및 **System.Security.Cryptography.HashAlgorithm.Create**가 `MySHA1HashClass` 개체를 반환하도록 런타임을 구성하는 방법을 보여 줍니다.  
  
```  
<configuration>  
   <!-- Other configuration settings. -->  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass MySHA1Hash="MySHA1HashClass, MyAssembly  
                  Culture='en', PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="SHA1" class="MySHA1Hash"/>  
            <nameEntry name="System.Security.Cryptography.SHA1"  
                       class="MySHA1Hash"/>  
            <nameEntry name="System.Security.Cryptography.HashAlgorithm"  
                       class="MySHA1Hash"/>  
         </cryptoNameMapping>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
 특성의 이름을 [\<cryptoClass\>요소](../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md)로 지정합니다. \(앞의 예제에서는 특성을 `MySHA1Hash` 라고 명명했습니다.\)  **\<cryptoClass\>** 요소의 특성 값은 공용 언어 런타임에서 클래스를 찾기 위해 사용하는 문자열입니다.  [정규화된 형식 이름 지정](../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)에 지정된 요구 사항을 만족시키는 모든 문자열을 사용할 수 있습니다.  
  
 여러 알고리즘 이름을 동일한 클래스에 매핑할 수 있습니다.  [\<nameEntry\>](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) 요소는 클래스에 한 개의 알고리즘 이름을 매핑합니다.  **name** 특성은 **System.Security.Cryptography.CryptoConfig.CreateFromName** 메서드를 호출할 때 사용하는 문자열일 수도 있고 <xref:System.Security.Cryptography> 네임스페이스에 있는 추상 암호화 클래스 이름일 수도 있습니다.  **class** 특성의 값은 **\<cryptoClass\>** 요소의 특성 이름입니다.  
  
> [!NOTE]
>  [System.Security.Cryptography.SHA1.Create](frlrfSystemSecurityCryptographySHA1ClassCreateTopic) 또는 **Security.CryptoConfig.CreateFromName\("SHA1"\)** 메서드를 호출함으로써 SHA1 알고리즘을 가져올 수 있습니다.  각 메서드는 SHA1 알고리즘을 구현하는 개체의 반환만을 보증합니다.  구성 파일에서 알고리즘의 모든 이름을 동일한 클래스에 매핑하지 않아도 됩니다.  
  
 기본 이름 및 이 이름이 매핑되는 클래스 목록을 보려면 [CryptoConfig 클래스](frlrfSystemSecurityCryptographyCryptoConfigClassTopic)를 참조하십시오.  
  
## 참고 항목  
 [암호화 서비스](../../../docs/standard/security/cryptographic-services.md)   
 [암호화 클래스 구성](../../../docs/framework/configure-apps/configure-cryptography-classes.md)