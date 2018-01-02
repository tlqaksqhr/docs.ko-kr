---
title: '&lt;channelPoolSettings&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4755f3d3-4213-4c68-ae7f-45b67d744459
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 09496add0adcc11756b6aae01a0236fe590f819f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltchannelpoolsettingsgt"></a>&lt;channelPoolSettings&gt;
사용자 지정 바인딩의 채널 풀 설정을 지정합니다.  
  
 \<system.serviceModel >  
\<바인딩 >  
\<customBinding >  
\<바인딩 >  
\<oneWay >  
\<channelPoolSettings >  
  
## <a name="syntax"></a>구문  
  
```xml  
<channelPoolSettings  
    idleTimeout"TimeSpan"  
        leaseTimeout"TimeSpan"  
    maxOutboundConnectionsPerEndpopint="Integer" />  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`idleTimeout`|연결이 끊어지기 전에 풀의 채널이 유휴 상태를 유지할 수 있는 최대 시간을 지정하는 <xref:System.TimeSpan>(양수)입니다. 기본값은 00:02:00입니다.|  
|`leaseTimeout`|채널이 풀에 반환될 때 해당 기간이 경과하면 채널이 닫히는 시간 간격을 지정하는 <xref:System.TimeSpan>입니다. 기본값은 00:10:00입니다.|  
|`maxOutboundChannelsPerEndpoint`|각 원격 끝점에 대해 풀에 저장할 수 있는 최대 채널 수를 지정하는 양의 정수입니다. 기본값은 10입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<oneWay >](../../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)|사용자 지정 바인딩에 대한 패킷 라우팅을 활성화합니다.|  
  
## <a name="remarks"></a>설명  
 할당량은 과도한 리소스 소비를 방지하기 위한 정책 메커니즘으로 사용됩니다. 할당량은 악의적이거나 의도하지 않은 DOS(서비스 거부) 공격을 방지합니다. 사용자 지정 채널에서 채널 할당량을 설정할 때 이 요소를 사용합니다.  
  
 `ChannelPoolSettings`는 다음 세 가지 할당량을 지정합니다.  
  
-   `idleTimeout` 할당량을 사용하면 장기간 동안 제한된 리소스를 사용하는 서버에 대한 DOS(서비스 거부) 공격을 줄일 수 있습니다. 클라이언트에서 정확한 값을 설정하면 서비스 연결 안정성을 높일 수 있습니다. 기본값은 신중하고 적당한 리소스 할당을 기준으로 합니다. 이 값은 개발 환경 및 소규모 설치 시나리오에 적합합니다. 설치로 인해 리소스가 부족해지거나 추가 리소스를 사용할 수 있더라도 연결이 제한되는 경우 서비스 관리자는 이 값을 검토해야 합니다.  
  
-   `leaseTimeout` 할당량을 사용하면 부하 균형 도구와 통합되어 안정성을 향상시킬 수 있습니다. 기본값은 신중한 리소스 할당을 기준으로 합니다. 이 값은 개발 환경 및 소규모 설치 시나리오에 적합합니다. 설치로 인해 리소스가 부족해지거나 추가 리소스를 사용할 수 있더라도 연결이 제한되는 경우 서비스 관리자는 이 값을 검토해야 합니다.  
  
-   `maxOutboundChannelsPerEndpoint` 할당량은 서버와 클라이언트 양쪽에 캐시 제한을 설정하며 이를 사용하여 안정성을 향상시킬 수 있습니다. 기본값은 개발 환경 및 소규모 설치 시나리오에 적합한 신중하고 적당한 리소스 할당을 기준으로 합니다. 설치로 인해 리소스가 부족해지거나 추가 리소스를 사용할 수 있더라도 연결이 제한되는 경우 서비스 관리자는 이 값을 검토해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Channels.OneWayBindingElement.ChannelPoolSettings%2A>  
 <xref:System.ServiceModel.Channels.ChannelPoolSettings>  
 <xref:System.ServiceModel.Configuration.OneWayElement.ChannelPoolSettings%2A>  
 <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [\<oneWay >](../../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)  
 [바인딩](../../../../../docs/framework/wcf/bindings.md)  
 [바인딩 확장](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [사용자 지정 바인딩](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [\<customBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
