---
title: "&lt;localClientSettings&gt; 요소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4680ace5-f4e1-4fcb-b9d8-a4a4af5cd7ae
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cabde7eb9dd122c2f7060b2f2e2c16f5949dc1f3
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="ltlocalclientsettingsgt-element"></a>&lt;localClientSettings&gt; 요소
이 바인딩에 대한 로컬 클라이언트의 보안 설정을 지정합니다.  
  
 \<system.serviceModel >  
\<바인딩 >  
\<customBinding >  
\<바인딩 >  
\<보안 >  
  
## <a name="syntax"></a>구문  
  
```xml  
<security>  
   <localClientSettings cacheCookies="Boolean"  
      cookieRenewalThresholdPercentage="Integer"  
      detectReplays="Boolean"  
      maxClockSkew="TimeSpan"  
      maxCookieCachingTime="TimeSpan"  
      reconnectTransportOnFailure="Boolean"  
      replayCacheSize="Integer"  
      replayWindow="TimeSpan"  
      sessionKeyRenewalInterval="TimeSpan"  
      sessionKeyRolloverInterval="TimeSpan"  
      timestampValidityDuration="TimeSpan" />  
</security>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`cacheCookies`|쿠키 캐싱 활성화 여부를 나타내는 부울 값입니다. 기본값은 `false`입니다.|  
|`cookieRenewalThresholdPercentage`|갱신할 수 있는 최대 쿠키 백분율을 지정하는 정수입니다. 이 값은 0 이상 100 이하여야 합니다. 기본값은 90입니다.|  
|`detectReplays`|채널에 대한 재생 공격이 검색되어 자동으로 처리되는지 여부를 지정하는 부울 값입니다. 기본값은 `false`입니다.|  
|`maxClockSkew`|서로 통신하는 양쪽의 시스템 클록 간의 최대 시간 차이를 지정하는 <xref:System.TimeSpan>입니다. 기본값은 "00:05:00"입니다.<br /><br /> 이 값을 기본값으로 설정하면 수신자는 메시지를 받은 시간을 기준으로 보낸 시간 타임스탬프가 전후 5분 이내인 메시지를 수신 허용합니다. 보낸 시간 테스트를 통과하지 못한 메시지는 거부됩니다. 이 설정은 `replayWindow` 특성과 함께 사용됩니다.|  
|`maxCookieCachingTime`|쿠키의 최대 수명을 지정하는 <xref:System.TimeSpan>입니다. 기본값은 "10675199.02:48:05.4775807"입니다.|  
|`reconnectTransportOnFailure`|WS-Reliable Messaging을 사용하는 연결에서 전송 실패 후 다시 연결을 시도할지 여부를 지정하는 부울 값입니다. 기본값은 `true`로, 다시 연결이 무한히 시도된다는 의미입니다. 이 순환은 비활성 제한 시간이 초과되어야만 중단되며, 이 경우 채널에서 다시 연결할 수 없으면 예외가 throw됩니다.|  
|`replayCacheSize`|재생 검색에 사용되는 캐시된 Nonce의 수를 지정하는 양의 정수입니다. 이 제한을 초과하면 가장 오래된 Nonce가 제거되고 새 메시지에 대해 새로운 Nonce가 만들어집니다. 기본값은 500000입니다.|  
|`replayWindow`|개별 메시지 Nonce의 유효 기간을 지정하는 <xref:System.TimeSpan>입니다.<br /><br /> 이 속성에서 지정한 시간이 지나면 이전에 보낸 메시지와 동일한 Nonce를 갖는 메시지는 허용되지 않습니다. 이 특성은 `maxClockSkew` 특성과 함께 사용되어 재생 공격을 방지합니다. 메시지 재생 창이 만료된 후에 공격자가 그 메시지를 재생할 수 있습니다. 그러나 이 메시지는 `maxClockSkew` 테스트를 통과하지 못합니다. 해당 테스트는 메시지의 보낸 시간 타임스탬프가 메시지를 받은 시간보다 지정된 시간 이상으로 늦거나 빠르면 그 메시지를 거부합니다.|  
|`sessionKeyRenewalInterval`|개시자가 보안 세션을 위해 키를 갱신하는 시간 간격을 지정하는 <xref:System.TimeSpan>입니다. 기본값은 "10:00:00"입니다.|  
|`sessionKeyRolloverInterval`|키 갱신 중에 들어오는 메시지에서 이전 세션 키를 사용할 수 있는 시간 간격을 지정하는 <xref:System.TimeSpan>입니다. 기본값은 "00:05:00"입니다.<br /><br /> 키 갱신 중에 클라이언트와 서버는 반드시 사용 가능한 최신 키를 사용하여 메시지를 보내야 합니다. 양쪽 모두 롤오버 시간이 만료될 때까지는 이전 세션 키를 사용하여 보안되는 메시지를 수락할 수 있습니다.|  
|`timestampValidityDuration`|타임스탬프의 유효 기간을 지정하는 <xref:System.TimeSpan>(양수)입니다. 기본값은 "00:15:00"입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<보안 >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)|사용자 지정 바인딩에 대한 보안 옵션을 지정합니다.|  
|[\<secureConversationBootstrap >](../../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)|보안 대화 서비스 개시에 사용되는 기본값을 지정합니다.|  
  
## <a name="remarks"></a>설명  
 이 설정은 서비스의 보안 정책에서 파생되는 설정이 아니므로 로컬 설정에 속합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Configuration.LocalClientSecuritySettingsElement>  
 <xref:System.ServiceModel.Configuration.SecurityElementBase.LocalClientSettings%2A>  
 <xref:System.ServiceModel.Channels.SecurityBindingElement.LocalClientSettings%2A>  
 <xref:System.ServiceModel.Channels.LocalClientSecuritySettings>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [바인딩](../../../../../docs/framework/wcf/bindings.md)  
 [바인딩 확장](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [사용자 지정 바인딩](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [\<customBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [방법: SecurityBindingElement를 사용 하 여 사용자 지정 바인딩을 만들려면](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [사용자 지정 바인딩 보안](../../../../../docs/framework/wcf/samples/custom-binding-security.md)
