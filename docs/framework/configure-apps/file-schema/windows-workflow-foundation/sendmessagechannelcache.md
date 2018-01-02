---
title: '&lt;sendMessageChannelCache&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 241e428e-5030-4b13-8a0a-69f05288d3d9
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0a2fe2fbeb82ea4412a85a4503a5ae950639a659
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltsendmessagechannelcachegt"></a>&lt;sendMessageChannelCache&gt;
캐시 공유 수준, 채널 팩터리 캐시 설정 및 송신 메시징 활동을 사용 하 여 서비스 끝점으로 메시지를 보내는 워크플로 위한 채널 캐시 설정을 사용자 지정할 수 있는 서비스 동작입니다.  
  
\<시스템입니다. ServiceModel >  
\<동작 >  
\<serviceBehaviors >  
\<동작 >  
\<sendMessageChannelCache >  
  
## <a name="syntax"></a>구문  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <sendMessageChannelCache allowUnsafeCaching="Boolean">
        <channelSettings idleTimeout="TimeSpan"
                         leaseTimeout="TimeSpan" 
                         maxItemsInCache="Integer" />
        <factorySettings idleTimeout="TimeSpan" 
                         leaseTimeout="TimeSpan" 
                         maxItemsInCache="Integer" />
      </sendMessageChannelCache>
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|allowUnsafeCaching|캐시 설정 여부를 나타내는 부울 값입니다. 워크플로 서비스에 사용자 지정 바인딩 또는 사용자 지정 동작이 있는 경우 캐싱이 안전하지 않을 수 있으므로 기본적으로 사용되지 않도록 설정됩니다. 그러나 기능을 사용할 경우 캐싱에이 속성을 설정 **true**합니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<channelSettings >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/channelsettings.md)|채널 캐시의 설정을 지정합니다.|  
|[\<factorySettings >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/factorysettings.md)|채널 팩터리 캐시의 설정을 지정합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<동작 >의 \<serviceBehaviors >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|동작 요소를 지정합니다.|  
  
## <a name="remarks"></a>설명  
 이 서비스 동작은 서비스 끝점에 메시지를 전송하는 워크플로를 위한 것입니다. 이러한 워크플로는 일반적으로 클라이언트 워크플로이지만 <xref:System.ServiceModel.WorkflowServiceHost>에서 호스팅되는 워크플로 서비스일 수도 있습니다.  
  
 기본적으로 <xref:System.ServiceModel.WorkflowServiceHost>에서 호스팅되는 워크플로에서 <xref:System.ServiceModel.Activities.Send> 메시징 활동에 사용되는 캐시는 <xref:System.ServiceModel.WorkflowServiceHost>의 모든 워크플로 인스턴스에서 공유됩니다(호스트 수준 캐싱). <xref:System.ServiceModel.WorkflowServiceHost>에서 호스팅되지 않는 클라이언트 워크플로의 경우 워크플로 인스턴스에서만 캐시를 사용할 수 있습니다(인스턴스 수준 캐싱). 구성에 정의된 끝점이 있는 워크플로의 경우 기본적으로 Send 활동에 캐싱을 사용하지 않도록 설정되어 있습니다.  
  
 [!INCLUDE[crabout](../../../../../includes/crabout-md.md)]기본 캐시 공유 수준을 변경 하 고 캐시 채널 팩터리 및 채널 캐시에 대 한 설정을 참조 하는 방법 [보내기 활동에 대 한 캐시 공유 수준 변경](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)합니다.  
  
## <a name="example"></a>예  
 호스팅된 워크플로 서비스의 경우 응용 프로그램 구성 파일에서 팩터리 캐시 및 채널 캐시 설정을 지정할 수 있습니다. 이렇게 하려면 팩터리 및 채널 캐시의 캐시 설정을 포함하는 서비스 동작을 추가하고 이 서비스 동작을 서비스에 추가합니다. 다음 예제에서는 포함 된 구성 파일의 내용이 표시는 **MyChannelCacheBehavior** 서비스 동작을 사용자 지정 팩터리 캐시 및 채널 캐시 설정을 사용 합니다. 이 서비스 동작을 통해 서비스에 추가 **behaviorConfiguarion** 특성입니다.  
  
```xml  
<configuration>    
  <system.serviceModel>  
    <!-- List of other config sections here -->   
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="MyChannelCacheBehavior">  
          <sendMessageChannelCache allowUnsafeCaching ="false" >  
            <!-- Control only the host level settings -->   
            <factorySettings maxItemsInCache = "8" idleTimeout = "00:05:00" leaseTimeout="10:00:00" />  
            <channelSettings maxItemsInCache = "32" idleTimeout = "00:05:00" leaseTimeout="00:06:00" />  
          </sendMessageChannelCache>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service name="MyService" behaviorConfiguration="MyChannelCacheBehavior" />  
    </services>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Activities.SendMessageChannelCache>  
 <xref:System.ServiceModel.Activities.Configuration.SendMessageChannelCacheElement>  
 <xref:System.ServiceModel.Activities.Send>  
 [Send 작업의 캐시 공유 수준 변경](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)
