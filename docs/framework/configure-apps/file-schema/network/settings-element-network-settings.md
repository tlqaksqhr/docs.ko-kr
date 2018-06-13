---
title: '&lt;설정&gt; 요소 (네트워크 설정)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#settings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings
helpviewer_keywords:
- settings element
- <settings> element
ms.assetid: 189ce989-c39b-427d-b004-6b82a668b931
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 3f717705a6cd4cc29fe333f5012c7fec466d350b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32752480"
---
# <a name="ltsettingsgt-element-network-settings"></a>&lt;설정&gt; 요소 (네트워크 설정)
<xref:System.Net?displayProperty=nameWithType> 네임스페이스에 대한 기본 네트워크 옵션을 구성합니다.  
  
 \<configuration>  
\<system.net>  
\<settings>  
  
## <a name="syntax"></a>구문  
  
```xml  
<settings>  
  <httpListener> … </httpListener>  
  <httpWebRequest> … </httpWebRequest>  
  <ipv6> … </ipv6>  
  <performanceCounters> … </performanceCounters>  
  <servicePointManager> … </servicePointManager>  
  <socket> … </socket>  
  <webProxyScript> … </webProxyScript>  
</settings>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
 없음  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[HttpListener](../../../../../docs/framework/configure-apps/file-schema/network/httplistener-element-network-settings.md)|사용 하는 매개 변수를 사용자 지정은 <xref:System.Net.HttpListener> 클래스입니다.|  
|[httpWebRequest](../../../../../docs/framework/configure-apps/file-schema/network/httpwebrequest-element-network-settings.md)|웹 요청 매개 변수를 사용자 지정합니다.|  
|[i p v 6](../../../../../docs/framework/configure-apps/file-schema/network/ipv6-element-network-settings.md)|인터넷 프로토콜 버전 6 (IPv6)을 지원 합니다.|  
|[\<performanceCounter > 요소 (네트워크 설정)](../../../../../docs/framework/configure-apps/file-schema/network/performancecounter-element-network-settings.md)|네트워크 성능 카운터를 사용 하도록 설정 합니다.|  
|[servicePointManager](../../../../../docs/framework/configure-apps/file-schema/network/servicepointmanager-element-network-settings.md)|네트워크 리소스에 대 한 연결을 구성합니다.|  
|[소켓](../../../../../docs/framework/configure-apps/file-schema/network/socket-element-network-settings.md)|소켓 작업 완료 포트를 사용 하는지 여부를 지정 합니다.|  
|[\<webProxyScript > 요소 (네트워크 설정)](../../../../../docs/framework/configure-apps/file-schema/network/webproxyscript-element-network-settings.md)|웹 프록시 검색에 사용 되는 스크립트의 특성을 구성 합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[system.net](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|.NET Framework의 네트워크 연결 방법을 지정하는 설정을 포함합니다.|  
  
## <a name="remarks"></a>설명  
  
## <a name="configuration-files"></a>구성 파일  
 이 요소는 응용 프로그램 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Net?displayProperty=nameWithType>  
 [네트워크 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
