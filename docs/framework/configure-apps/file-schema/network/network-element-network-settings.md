---
title: '&lt;네트워크&gt; 요소 (네트워크 설정)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#network
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp/network
helpviewer_keywords:
- <network> element
- network element
ms.assetid: 2c2c6ad4-ed11-48ab-b28e-2bc0ba9b42c7
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: e53d39f15a01f751a93c5531b3079d77bf0040e4
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32744670"
---
# <a name="ltnetworkgt-element-network-settings"></a>&lt;네트워크&gt; 요소 (네트워크 설정)
외부 메일 전송 SMTP (Simple Protocol) 서버에 대 한 네트워크 옵션을 구성 합니다.  
  
 \<configuration>  
\<system.net>  
\<mailSettings>  
\<smtp>  
\<network>  
  
## <a name="syntax"></a>구문  
  
```xml  
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
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`clientDomain`|SMTP 메일 서버에 연결 하는 초기 SMTP 프로토콜 요청에 사용할 클라이언트 도메인 이름을 지정 합니다. 기본값은 요청을 보내는 로컬 컴퓨터의 로컬 호스트 이름입니다.|  
|`defaultCredentials`|SMTP 트랜잭션에 SMTP 메일 서버에 액세스 하는 기본 사용자 자격 증명을 사용할 것인지 여부를 지정 합니다. 기본값은 `false`입니다.|  
|`enableSsl`|SMTP 메일 서버에 액세스 하려면 SSL을 사용할지를 지정 합니다. 기본값은 `false`입니다.|  
|`host`|SMTP 트랜잭션에 사용할 SMTP 메일 서버의 호스트 이름을 지정 합니다. 이 특성에 기본값이 없습니다.|  
|`password`|SMTP 메일 서버에 인증에 사용할 암호를 지정 합니다. 이 특성에 기본값이 없습니다.|  
|`port`|SMTP 메일 서버에 연결 하는 데 사용할 포트 번호를 지정 합니다. 기본값은 25입니다.|  
|`targetName`|SMTP 트랜잭션에 대 한 확장 된 보호를 사용 하는 경우 인증에 사용할 서비스 공급자 이름 (SPN)을 지정 합니다. 이 특성에 기본값이 없습니다.|  
|`userName`|SMTP 메일 서버에 인증에 사용할 사용자 이름을 지정 합니다. 이 특성에 기본값이 없습니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<smtp > 요소 (네트워크 설정)](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|전송 프로토콜 SMTP (Simple Mail) 메일 보내기 옵션을 구성 합니다.|  
  
## <a name="remarks"></a>설명  
 일부 SMTP 서버에서 직접 인증을 사용 하기 전에 서버에 필요 합니다. 기본 네트워크 자격 증명을 사용 하 여 호스트에서 직접 인증을 설정 하려는 경우는 `defaultCredentials` 특성을 `true`합니다. <xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType> 속성의 현재 값을 가져오는 데 사용할 수는 `defaultCredentials` 해당 구성 파일에서 특성입니다.  
  
 (한 사용자 이름 및 암호)에서 SMTP 서버에 자신을 인증 하는 기본 인증도 사용할 수 있습니다. 이 옵션을 사용 하려면 유효한 사용자 이름 및 지정된 된 SMTP 서버에 대 한 암호를 지정 해야 합니다.  
  
> [!NOTE]
>  기본 인증은 보냅니다는 `userName` 및 `password` 암호화 되지 않은 서버에는 값입니다. 네트워크 트래픽을 모니터링 하는 모든 자격 증명을 볼 수 있으며 서버에 연결 하는 데 사용. Kerberos 또는 NT LAN Manager (NTLM) 같은 더 안전한 인증 메커니즘을 사용 하는 것이 좋습니다. 경우 `defaultCredentials` 은 `true`, Kerberos 또는 NTLM 경우 사용 되는 서버는 이러한 프로토콜을 지원 합니다.  
  
 기본 인증 및 기본 네트워크 자격 증명 옵션은 함께 사용할 수 없습니다. 설정한 경우 `defaultCredentials` 를 `true` 사용자 이름 및 암호를 지정 하 고 기본 네트워크 자격 증명을 사용 및 기본 인증 데이터는 무시 됩니다.  
  
 지정 하는 경우 기본 인증에 대 한 한 `userName`도 지정 해야는 `password` 인증 메일 서버에 직접 합니다.  
  
 <xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType> 속성의 현재 값을 가져오는 데 사용할 수는 `userName` 해당 구성 파일에서 특성입니다. <xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType> 속성의 현재 값을 가져오는 데 사용할 수는 `password` 해당 구성 파일에서 특성입니다. A `password` 은 특성 일반적으로 보안상의 이유로 구성 파일에 입력 되지 않습니다.  
  
 `clientDomain` 특성이 SMTP 서버에 초기 SMTP 프로토콜 요청에 사용 되는 클라이언트 도메인 이름을 변경 합니다. `clientDomain` 특성 기본적으로 사용 되는 로컬 호스트 이름이 아니라 로컬 컴퓨터의 정규화 된 도메인 이름으로 설정할 수 있습니다. 큰 SMTP 프로토콜 표준 준수를 제공합니다. 기본값은 요청을 보내는 로컬 컴퓨터의 로컬 호스트 이름입니다. <xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType> 속성의 현재 값을 가져오는 데 사용할 수는 `clientDomain` 해당 구성 파일에서 특성입니다.  
  
 `targetName` 특성은 확장 된 보호를 사용 하는 경우 인증에 사용 됩니다. 폼의 기본값은 "SMTPSVC /\<호스트 >" 여기서 \<호스트 > SMTP 메일 서버의 호스트 이름입니다. <xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType> 속성의 현재 값을 가져오는 데 사용할 수는 `targetName` 해당 구성 파일에서 특성입니다.  
  
 `enableSsl` 특성 SMTP 메일 서버에 액세스 하려면 SSL을 사용할지를 지정 합니다. <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType> 클래스 SMTP 서비스 확장에 대해서만 지원 SMTP Secure Transport Layer Security를 통해 3207 RFC에에서 정의 된 대로 합니다. 이 모드에서는 암호화 되지 않은 채널에 SMTP 세션 시작 후 STARTTLS 명령을 전환 SSL을 사용 하 여 보안 통신 하려면 서버에 클라이언트에서 발급 됩니다. RFC 3207 게시 하 여는 Task Force IETF (Internet Engineering)에 대 한 자세한 내용은 참조 하십시오.  
  
 대체 연결 방법은 명령이 전송 되는 모든 프로토콜 하기 전에 SSL 세션이 들겠지만 하 게 설정 하는 것입니다. 이 연결 방법은 SMTPS 라고도 하 고 기본적으로 포트 465를 사용 합니다. 이 대체 연결 방법은 SSL을 사용 하 여 현재 지원 되지 않습니다.  
  
 <xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType> 속성의 현재 값을 가져오는 데 사용할 수는 `enableSsl` 해당 구성 파일에서 특성입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 기본 네트워크 자격 증명을 사용 하 여 전자 메일을 보내는 적절 한 SMTP 매개 변수를 지정 합니다.  
  
```xml  
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
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Net.Configuration.SmtpNetworkElement?displayProperty=nameWithType>  
 <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>  
 <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>  
 [네트워크 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
