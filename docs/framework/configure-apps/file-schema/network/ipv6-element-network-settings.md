---
title: '&lt;ipv6&gt; 요소 (네트워크 설정)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/ipv6
- http://schemas.microsoft.com/.NetConfiguration/v2.0#ipv6
helpviewer_keywords:
- <ipv6> element
- ipv6 element
ms.assetid: 10b79aef-327b-4718-a892-e11f55e4d169
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 4b73e5d781829292513e809c39ac9de9dfc6d0e8
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32742486"
---
# <a name="ltipv6gt-element-network-settings"></a>&lt;ipv6&gt; 요소 (네트워크 설정)
인터넷 프로토콜 버전 6 (IPv6)의 사용 되지 않는 멤버의 응답은 <xref:System.Net.Dns> 클래스입니다.  
  
 \<configuration>  
\<system.net>  
\<settings>  
\<ipv6 >  
  
## <a name="syntax"></a>구문  
  
```xml  
<ipv6  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|**특성**|**설명**|  
|-------------------|---------------------|  
|`enabled`|지정 여부의 멤버는 <xref:System.Net.Dns> 클래스는 인터넷 프로토콜 버전 6 (IPv6) 주소를 반환 합니다. 기본값은 `false`입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|**요소**|**설명**|  
|-----------------|---------------------|  
|[settings](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<xref:System.Net> 네임스페이스에 대한 기본 네트워크 옵션을 구성합니다.|  
  
## <a name="remarks"></a>설명  
 이 설정을 통해 IPv6 지원의 사용 되지 않는 멤버에 대 한는 <xref:System.Net.Dns> 클래스: <xref:System.Net.Dns.BeginGetHostByName%2A>, <xref:System.Net.Dns.BeginResolve%2A>, <xref:System.Net.Dns.EndGetHostByName%2A>, <xref:System.Net.Dns.EndResolve%2A>, <xref:System.Net.Dns.GetHostByAddress%2A>, <xref:System.Net.Dns.GetHostByName%2A>, 및 <xref:System.Net.Dns.Resolve%2A>합니다. 다른 멤버에 대 한는 <xref:System.Net?displayProperty=nameWithType> 네임 스페이스, IPv6 주소 반환 될 수는 운영 체제에서 i p v 6을 설정한 경우.  
  
## <a name="configuration-files"></a>구성 파일  
 이 요소는 응용 프로그램 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 에 대 한 IPv6 지원을 사용 하도록 설정 하는 방법을 보여 주는 다음 예제는 <xref:System.Net.Dns> 클래스입니다.  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <ipv6 enabled="true"/>  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Net?displayProperty=nameWithType>  
 <xref:System.Net.Dns?displayProperty=nameWithType>  
 <xref:System.Net.Sockets.Socket.OSSupportsIPv6%2A?displayProperty=nameWithType>  
 [네트워크 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
