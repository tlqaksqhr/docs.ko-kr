---
title: "&lt;network&gt; 요소(네트워크 설정) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#network"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp/network"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<network> 요소"
  - "network 요소"
ms.assetid: 2c2c6ad4-ed11-48ab-b28e-2bc0ba9b42c7
caps.latest.revision: 13
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 13
---
# &lt;network&gt; 요소(네트워크 설정)
외부 SMTP\(Simple Mail Transport Protocol\) 서버에 대한 네트워크 옵션을 구성합니다.  
  
## 구문  
  
```  
  
      <network  
  clientDomain="string"   
  defaultCredentials="true|false"  
  enableSsl="true|false"  
  host="string"   
  password="string"  
  port="integer"   
  targetName="string"  
  userName="string"  
/>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`clientDomain`|SMTP 메일 서버에 연결하기 위해 초기 SMTP 프로토콜 요청에 사용되는 클라이언트 도메인 이름을 지정합니다.  기본값은 요청을 보내는 로컬 컴퓨터의 로컬 호스트 이름입니다.|  
|`defaultCredentials`|SMTP 트랜잭션을 위해 SMTP 메일서버에 액세스하는 데 기본 사용자 자격 증명을 사용해야 하는지 여부를 지정합니다.  기본값은 `false`입니다.|  
|`enableSsl`|SMTP 메일 서버에 액세스하는 데 SSL을 사용할지 여부를 지정합니다.  기본값은 `false`입니다.|  
|`host`|SMTP 트랜잭션에 사용할 SMTP 메일 서버의 호스트 이름을 지정합니다.  이 특성에는 기본값이 없습니다.|  
|`password`|SMTP 메일 서버에 인증하는 데 사용하는 암호를 지정합니다.  이 특성에는 기본값이 없습니다.|  
|`port`|SMTP 메일 서버에 연결하는 데 사용하는 포트 번호를 지정합니다.  기본값은 25입니다.|  
|`targetName`|SMTP 트랜잭션에 확장 보호를 사용하는 경우 인증에 사용할 SPN\(서비스 공급자 이름\)을 지정합니다.  이 특성에는 기본값이 없습니다.|  
|`userName`|SMTP 메일 서버에 인증하는 데 사용하는 사용자 이름을 지정합니다.  이 특성에는 기본값이 없습니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<smtp\> 요소\(네트워크 설정\)](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|SMTP\(Simple Mail Transport Protocol\) 메일 보내기 옵션을 구성합니다.|  
  
## 설명  
 일부 SMTP 서버에서는 사용자가 서버에서 직접 인증을 받아야 합니다.  호스트의 기본 네트워크 자격 증명을 사용하여 직접 인증을 받으려면 `defaultCredentials` 특성을 `true`로 설정합니다.  <xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=fullName> 속성은 해당 구성 파일에서 `defaultCredentials` 특성의 현재 값을 가져오는 데 사용할 수 있습니다.  
  
 또한 기본 인증\(사용자 이름과 암호\)을 사용하여 SMTP 서버에서 직접 인증을 받을 수도 있습니다.  이 옵션을 사용하려면 지정된 SMTP 서버에 대한 유효한 사용자 이름과 암호를 지정해야 합니다.  
  
> [!NOTE]
>  기본 인증은 `userName` 및 `password` 값을 암호화되지 않은 상태로 서버에 보냅니다.  이 경우 네트워크 트래픽을 모니터링하는 다른 모든 사용자가 사용자의 자격 증명을 보고 이를 사용하여 서버에 연결할 수 있습니다.  따라서 Kerberos나 NTLM\(NT LAN 관리자\) 같은 좀 더 안전한 인증 메커니즘을 사용해야 합니다. `defaultCredentials`가 `true`이면 서버에서 Kerberos 또는 NTLM 프로토콜을 지원할 경우 이러한 프로토콜이 사용됩니다.  
  
 기본 인증 및 기본 네트워크 자격 증명 옵션을 함께 사용할 수 없습니다. 따라서 `defaultCredentials`를 `true`로 설정하고 사용자 이름과 암호를 지정하면 기본 네트워크 자격 증명이 사용되고 기본 인증 데이터는 무시됩니다.  
  
 기본 인증을 위해 `userName`을 지정할 경우 메일 서버로 직접 인증하도록 `password`도 지정해야 합니다.  
  
 <xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=fullName> 속성은 해당 구성 파일에서 `userName` 특성의 현재 값을 가져오는 데 사용할 수 있습니다.  <xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=fullName> 속성은 해당 구성 파일에서 `password` 특성의 현재 값을 가져오는 데 사용할 수 있습니다.  `password` 특성은 보안상의 이유로 구성 파일에 정상적으로 입력되지 않습니다.  
  
 `clientDomain` 특성은 초기 SMTP 프로토콜 요청에 사용되는 클라이언트 도메인 이름을 SMTP 서버로 변경합니다.  `clientDomain` 특성은 기본적으로 사용되는 로컬 호스트 이름이 아닌 로컬 컴퓨터의 정규화된 도메인 이름으로 설정할 수 있습니다.  이것은 SMTP 프로토콜 표준에 대한 보다 높은 준수를 제공합니다.  기본값은 요청을 보내는 로컬 컴퓨터의 로컬 호스트 이름입니다.  <xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=fullName> 속성은 해당 구성 파일에서 `clientDomain` 특성의 현재 값을 가져오는 데 사용할 수 있습니다.  
  
 확장 보호를 사용할 때 `targetName` 특성이 인증에 사용됩니다.  기본 값은 "SMTPSVC\/\<host\>" where \<host\> 가 SMTP 메일 서버의 호스트 이름의 형식입니다.  <xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=fullName> 속성은 해당 구성 파일에서 `targetName` 특성의 현재 값을 가져오는 데 사용할 수 있습니다.  
  
 `enableSsl` 특성은 SMTP 메일 서버에 액세스하기 위해 SSL을 사용할지 여부를 지정합니다.  <xref:System.Net.Mail.SmtpClient?displayProperty=fullName> 클래스는 RFC 3207에 정의된 대로 Transport Layer Security에서 보안 SMTP에 대한 SMTP 서비스 확장만 지원합니다.  이 모드에서 SMTP 세션은 암호화되지 않은 채널에서 시작한 다음 STARTTLS 명령이 클라이언트에서 서버로 실행되어 SSL을 사용한 보안 통신으로 전환됩니다.  자세한 내용은 IETF\(Internet Engineering Task Force\)에서 게시한 RFC 3207을 참조하십시오.  
  
 대체 연결 메서드는 프로토콜 명령을 보내기 전에 SSL 세션이 설정되는 곳입니다.  이 연결 메서드는 SMTPS라고도 하며 기본적으로 포트 465를 사용합니다.  SSL을 사용하는 이 대체 연결 메서드는 현재 지원되지 않습니다.  
  
 <xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=fullName> 속성은 해당 구성 파일에서 `enableSsl` 특성의 현재 값을 가져오는 데 사용할 수 있습니다.  
  
## 예제  
 다음 코드 예제에서는 기본 네트워크 자격 증명을 사용하여 전자 메일을 보내도록 적절한 SMTP 매개 변수를 지정합니다.  
  
```  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="network">  
        <network  
          clientDomain="www.contoso.com"  
          defaultCredentials="true"  
          enableSsl="false"  
          host="mail.contoso.com"  
          port="25"  
        />  
      </smtp>  
    </mailSettings>  
  </system.net>  
</configuration>  
```  
  
## 참고 항목  
 <xref:System.Net.Configuration.SmtpNetworkElement?displayProperty=fullName>   
 <xref:System.Net.Configuration.SmtpSection?displayProperty=fullName>   
 <xref:System.Net.Mail.SmtpClient?displayProperty=fullName>   
 [네트워크 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/network/index.md)