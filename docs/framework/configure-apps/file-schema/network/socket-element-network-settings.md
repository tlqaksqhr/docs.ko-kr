---
title: "&lt;socket&gt; 요소(네트워크 설정) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/socket"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#socket"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<socket> 요소"
  - "socket 요소"
ms.assetid: 366c634c-7d16-478f-aedf-053eda94a1a0
caps.latest.revision: 21
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 21
---
# &lt;socket&gt; 요소(네트워크 설정)
소켓 작업에 완료 포트가 사용될지 여부를 지정합니다.  
  
## 구문  
  
```  
  
      <socket  
  alwaysUseCompletionPortsForConnect="true|false"  
  alwaysUseCompletionPortsForAccept="true|false"  
  ipProtectionLevel ="EdgeRestricted|Restricted|Unrestricted|Unspecified"  
/socket>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|**특성**|**설명**|  
|------------|------------|  
|`alwaysUseCompletionPortsForAccept`|소켓이 항상 Accept 메서드 호출에 대해 완료 포트를 사용할지 여부를 나타냅니다.  기본값은 `false`입니다.|  
|`alwaysUseCompletionPortsForConnect`|소켓이 항상 Connect 메서드 호출에 대해 완료 포트를 사용할지 여부를 나타냅니다.  기본값은 `false`입니다.|  
|`ipProtectionLevel`|소켓에 사용하는 기본 <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=fullName>을 지정합니다.  기본값은 Windows 버전에 따라 달라집니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|**요소**|**설명**|  
|------------|------------|  
|[설정](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<xref:System.Net> 네임스페이스에 대한 기본 네트워크 옵션을 구성합니다.|  
  
## 설명  
 `alwaysUseCompletionPortsForAccept` 및 `alwaysUseCompletionPortsForConnect` 특성이 <xref:System.Net.Sockets?displayProperty=fullName> 네임스페이스에 있는 클래스에 의해 완료 포트의 사용과 관련된 기본 동작을 지정하는 데 사용됩니다.  고성능 서버 응용 프로그램에 권장됩니다.  
  
 `alwaysUseCompletionPortsForAccept` 및 `alwaysUseCompletionPortsForConnect` 특성의 기본값은 **false**입니다.  
  
 <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForAccept%2A>는 해당 구성 파일에서 `alwaysUseCompletionPortsForAccept` 특성의 현재 값을 가져오는 데 사용할 수 있습니다.  <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForConnect%2A>는 해당 구성 파일에서 `alwaysUseCompletionPortsForConnect` 특성의 현재 값을 가져오는 데 사용할 수 있습니다.  
  
 `ipProtectionLevel` 특성은 소켓에 사용하는 기본 <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=fullName>을 지정합니다.  <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> 속성을 IPv6 소켓 같은 링크 로컬 주소로 또는 사이트 로컬 접두사 \(예: 지정한 범위에 대한 제한 구성할 수 있도록 합니다.  이 옵션은 응용 프로그램으로 하여금 IPv6 소켓에 액세스 제한을 적용할 수 있도록 합니다.  이러한 제한을 사용하면 사설 LAN에서 실행되는 응용 프로그램을 간단하고 강력하게 외부 공격으로부터 보호할 수 있습니다.  이 옵션은 확대 또는 수신 대기 소켓 공용 및 개인 사용자를 적절한 경우 또는 필요한 만큼 같은 사이트에 대해서만 액세스를 제한하는 사용 무제한 액세스 범위를 좁힙니다.  
  
 `ipProtectionLevel` 특성 설정은 초기에 들어오는 트래픽에만 영향을 줍니다.  
  
-   소켓에서 들어오는 연결을 수신 대기하는 TCP 서버입니다.  
  
-   소켓에서 패킷을 받는 UDP 응용 프로그램입니다.  
  
 이 구성 설정은 이미 설정된 TCP 연결\(트래픽이 양방향으로 무제한\)에 영향을 미치지 않고 UDP 패킷을 보내는 응용 프로그램에 영향을 주지 않습니다.  
  
 `ipProtectionLevel` 특성 설정의 가능한 값은 다음과 같이 <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=fullName> 열거형에 지정된 정의된 보호 수준에 해당합니다.  
  
|||  
|-|-|  
|**특성 값**|**설명**|  
|EdgeRestricted|IP 보호 수준이 경계 제한됨입니다.  이 값은 인터넷을 통해 작동하도록 디자인된 응용 프로그램에서 사용됩니다.  이 설정은 Windows Teredo 구현을 사용하는 NAT\(Network Address Translation\) 통과를 허용하지 않습니다.  이러한 응용 프로그램에서는 IPv4 방화벽이 무시될 수 있으므로 열린 포트로 향하는 인터넷 공격을 막기 위해 응용 프로그램의 보안 기능을 강화해야 합니다.  Windows Server 2003 및 Windows XP에서는 소켓에 대한 IP 보호 수준이 기본적으로 경계 제한됨으로 설정됩니다.|  
|Restricted|IP 보호 수준이 제한됨입니다.  이 값은 인터넷 시나리오를 구현하지 않는 인트라넷 응용 프로그램에서 사용됩니다.  일반적으로 이러한 응용 프로그램은 인터넷형 공격에 대해 테스트되거나 보안이 강화되어 있지 않습니다.  이 설정은 링크 로컬에서만 트래픽을 받도록 제한합니다.|  
|무제한|IP 보호 수준이 제한하지 않음입니다.  이 값은 Windows에 구축된 IPv6 NAT 통과 기능\(예: Teredo\)을 이용하는 응용 프로그램을 비롯하여 인터넷을 통해 작동하도록 디자인된 응용 프로그램에서 사용됩니다.  이러한 응용 프로그램에서는 IPv4 방화벽이 무시될 수 있으므로 열린 포트로 향하는 인터넷 공격을 막기 위해 응용 프로그램의 보안 기능을 강화해야 합니다.  Windows Server 2008 R2 및 Windows Vista에서는 소켓에 대한 IP 보호 수준이 기본적으로 제한되지 않음으로 설정됩니다.|  
|지정하지 않습니다.|IP 보호 수준이 지정되지 않음입니다.  Windows 7 및 Windows Server 2008 R2에서는 소켓에 대한 IP 보호 수준이 기본적으로 지정되지 않음으로 설정됩니다.|  
  
 `ipProtectionLevel` 특성의 기본값은 **지정되지 않음**입니다.  
  
 <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> 속성은 해당 구성 파일에서 `ipProtectionLevel` 특성의 현재 값을 가져오는 데 사용할 수 있습니다.  
  
## 구성 파일  
 이 요소는 응용 프로그램 구성 파일이나 컴퓨터 구성 파일\(Machine.config\)에 사용할 수 있습니다.  
  
## 예제  
 다음 코드 예제에서는 완료 포트를 사용하고 기본 <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=fullName>이 제한이 없도록 지정하는 방법을 보여 줍니다.  
  
```  
<configuration>  
  <system.net>  
    <settings>  
      <socket  
        alwaysUseCompletionPortsForAccept="true"  
        alwaysUseCompletionPortsForConnect="true"  
        ipProtectionLevel="Unrestricted"  
       />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## 참고 항목  
 <xref:System.Net?displayProperty=fullName>   
 <xref:System.Net.Configuration.SocketElement?displayProperty=fullName>   
 <xref:System.Net.Sockets?displayProperty=fullName>   
 <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=fullName>   
 <xref:System.Net.Sockets.SocketOptionName?displayProperty=fullName>   
 [네트워크 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/network/index.md)