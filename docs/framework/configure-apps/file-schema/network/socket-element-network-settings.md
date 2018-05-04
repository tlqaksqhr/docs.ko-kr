---
title: '&lt;소켓&gt; 요소 (네트워크 설정)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/socket
- http://schemas.microsoft.com/.NetConfiguration/v2.0#socket
helpviewer_keywords:
- <socket> element
- socket element
ms.assetid: 366c634c-7d16-478f-aedf-053eda94a1a0
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 995a89dd67664fd6a408f88f20f6837d2dbaaad4
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltsocketgt-element-network-settings"></a>&lt;소켓&gt; 요소 (네트워크 설정)
소켓 작업 완료 포트를 사용 하는지 여부를 지정 합니다.  
  
 \<configuration>  
\<system.net>  
\<settings>  
\<소켓 >  
  
## <a name="syntax"></a>구문  
  
```xml  
<socket  
  alwaysUseCompletionPortsForConnect="true|false"  
  alwaysUseCompletionPortsForAccept="true|false"  
  ipProtectionLevel="EdgeRestricted|Restricted|Unrestricted|Unspecified"  
/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|**특성**|**설명**|  
|-------------------|---------------------|  
|`alwaysUseCompletionPortsForAccept`|소켓 항상에 대 한 Accept 메서드 호출이 완료 포트를 사용할지 여부를 나타냅니다. 기본값은 `false`입니다.|  
|`alwaysUseCompletionPortsForConnect`|소켓 항상 Connect 메서드 호출에 대 한 완료 포트를 사용할지 여부를 나타냅니다. 기본값은 `false`입니다.|  
|`ipProtectionLevel`|기본 지정 <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> 소켓의 경우 사용 하도록 합니다. 기본값의 Windows 버전에 따라 달라 집니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|**요소**|**설명**|  
|-----------------|---------------------|  
|[settings](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<xref:System.Net> 네임스페이스에 대한 기본 네트워크 옵션을 구성합니다.|  
  
## <a name="remarks"></a>설명  
 `alwaysUseCompletionPortsForAccept` 및 `alwaysUseCompletionPortsForConnect` 특성이 <xref:System.Net.Sockets?displayProperty=nameWithType> 네임스페이스에 있는 클래스에 의해 완료 포트의 사용과 관련된 기본 동작을 지정하는 데 사용됩니다. 완료 포트는 고성능 서버 응용 프로그램에 권장 됩니다.  
  
 기본값은 `alwaysUseCompletionPortsForAccept` 및 `alwaysUseCompletionPortsForConnect` 특성을 **false**합니다.  
  
 <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForAccept%2A> 의 현재 값을 가져오는 데 사용할 수는 `alwaysUseCompletionPortsForAccept` 해당 구성 파일에서 특성입니다. <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForConnect%2A> 의 현재 값을 가져오는 데 사용할 수는 `alwaysUseCompletionPortsForConnect` 해당 구성 파일에서 특성입니다.  
  
 `ipProtectionLevel` 기본값을 지정 하는 특성 <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> 소켓의 경우 사용 하도록 합니다. <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> 주소 같은 링크 로컬 또는 사이트 로컬 접두사와 같은 속성에 지정된 된 범위에 IPv6 소켓에 대 한 제한 구성할 수 있도록 합니다. 이 옵션에는 응용 프로그램을 IPv6 소켓에 대 한 액세스 제한을 적용할 수 있습니다. 이러한 제한을 사용하면 사설 LAN에서 실행되는 응용 프로그램을 간단하고 강력하게 외부 공격으로부터 보호할 수 있습니다. 이 옵션은 확대 또는 적절 한 경우 공용 및 개인 사용자 하거나, 필요에 따라 같은 사이트로 액세스를 제한의 무제한 액세스를 사용할 수 있도록와 여 수신 소켓의 범위를 좁힙니다.  
  
 이 `ipProtectionLevel` 특성 설정은 초기 들어오는 트래픽을 영향을 줍니다.  
  
-   TCP 소켓에서 들어오는 연결을 수신 대기 서버입니다.  
  
-   UDP 소켓에서 패킷을 받는 응용 프로그램입니다.  
  
 이 구성 설정은 이미 설정 된 TCP 연결 (트래픽 모두에 무제한으로)에 영향을 주지 UDP 패킷을 보내는 응용 프로그램에 영향을 주지 않습니다.  
  
 에 가능한 값은 고 `ipProtectionLevel` 특성 설정에 지정 된 정의 된 보호 수준이 해당는 <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> 다음과 같이 열거형:  
  
|**특성 값**|**설명**|  
|-|-|  
|EdgeRestricted|IP 보호 수준은 가장자리 제한 합니다. 이 값은 인터넷을 통해 작동 하도록 디자인 된 응용 프로그램에서 사용 됩니다. 이 설정은 Windows Teredo 구현을 사용 하 여 네트워크 주소 변환 (NAT) 통과 허용 하지 않습니다. 열린 포트로 향하는 인터넷 공격 응용 프로그램을 확정 해야 하므로 이러한 응용 프로그램 IPv4 방화벽을 건너뛸 수 있습니다. Windows Server 2003 및 Windows XP 소켓에서 IP 보호 수준에 대 한 기본 값은 가장자리 제한 합니다.|  
|제한|IP 보호 수준이 사용할 수 없습니다. 이 값은 인터넷 시나리오를 구현 하지 않는 인트라넷 응용 프로그램에서 사용 됩니다. 이러한 응용 프로그램은 일반적으로 테스트 말거나 인터넷 유형의 공격에 대 한 합니다. 이 설정은 트래픽이 받도록된 링크-로컬만 제한 됩니다.|  
|제한 없음|IP 보호 수준이 제한 되지 않습니다. 이 값은 기본 제공 되는 IPv6 NAT 통과 기능을 활용 하기 위해 응용 프로그램을 포함 하 여 인터넷을 통해 작동 하도록 설계 된 응용 프로그램에서 사용 될 windows (예: Teredo). 열린 포트로 향하는 인터넷 공격 응용 프로그램을 확정 해야 하므로 이러한 응용 프로그램 IPv4 방화벽을 건너뛸 수 있습니다. Windows Server 2008 R2 및 Windows Vista에서 소켓 IP 보호 수준에 대 한 기본값 제한 되지 않습니다.|  
|지정되지 않음|IP 보호 수준이 지정 되지 않았습니다. Windows 7 및 Windows Server 2008 r 2에서 소켓에서 IP 보호 수준에 대 한 기본값 지정 되지 않았습니다.|  
  
 기본값은 `ipProtectionLevel` 특성은 **Unspecified**합니다.  
  
 <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> 속성의 현재 값을 가져오는 데 사용할 수는 `ipProtectionLevel` 해당 구성 파일에서 특성입니다.  
  
## <a name="configuration-files"></a>구성 파일  
 이 요소는 응용 프로그램 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 완료 포트를 사용 해야 함을 지정 하는 방법을 지정 하 고 있는 기본 <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> 제한 해야 합니다.  
  
```xml  
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
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Net?displayProperty=nameWithType>  
 <xref:System.Net.Configuration.SocketElement?displayProperty=nameWithType>  
 <xref:System.Net.Sockets?displayProperty=nameWithType>  
 <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType>  
 <xref:System.Net.Sockets.SocketOptionName.IPProtectionLevel?displayProperty=nameWithType>  
 [네트워크 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
