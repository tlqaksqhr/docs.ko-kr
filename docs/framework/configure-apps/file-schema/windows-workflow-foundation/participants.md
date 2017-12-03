---
title: "&lt;참가자&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 560dd0bb-f9fb-423c-8857-2101a3654b06
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e20cc8ed26feccf6fcf7fae40d2a219cd103dbb0
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="ltparticipantsgt"></a>&lt;참가자&gt;
런타임에서 내보내지는 추적 레코드를 수신하는 추적 참가자의 목록을 직접 구성하고 구성된 방식대로 처리합니다. 여기에는 특정 출력(예: 파일, 콘솔, ETW)에 쓰기, 레코드 처리/집계 또는 필요한 기타 조합이 포함됩니다.  
  
 워크플로 추적 및 추적 참가자에 대 한 자세한 내용은 참조 하십시오. [워크플로 추적 및 트레이싱](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) 및 [추적 참가자](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md)합니다.  
  
\<system.serviceModel >  
\<추적 >  
\<참가자 >  
  
## <a name="syntax"></a>구문  
  
```xml
<tracking>
  <participants>
    <add name="String" 
         profileName="String" 
         type="String" />
  </participants>
</tracking>   
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
 없음  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/add-of-participants.md)|추적 참가자에 대한 설정을 포함합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<추적 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/tracking.md)|워크플로 서비스에 대한 추적 설정을 정의하기 위한 구성 섹션을 나타냅니다.|  
  
## <a name="remarks"></a>설명  
 추적 참가자는 워크플로에서 내보내지는 추적 데이터를 가져오고 이 데이터를 다른 미디어에 저장하기 위해 사용됩니다. 마찬가지로 추적 레코드에 대한 모든 사후 처리를 추적 참가자 내에서 수행할 수도 있습니다.  
  
 여러 추적 참가자가 추적 이벤트를 동시에 사용할 수 있습니다. 각 추적 참가자는 서로 다른 추적 프로필과 연결될 수 있습니다.  
  
 ETW 세션에 추적 레코드를 작성하는 표준 추적 참가자가 제공됩니다. 추적 참가자는 워크플로 서비스에서 구성 파일에 추적별 동작을 추가하여 구성할 수 있습니다. ETW 추적 참가자를 사용하여 이벤트 뷰어에서 추적 레코드를 볼 수 있습니다. 표준 참가자가 요구 사항에 맞지 않는 경우 사용자 지정 추적 참가자를 작성할 수도 있습니다.  
  
## <a name="example"></a>예제  
 다음 구성 예제에서는 Web.config 파일에서 구성되는 표준 ETW 추적 참가자를 보여 줍니다.  
  
 ETW 추적 참가자에서 ETW에 추적 레코드를 쓰기 위해 사용 하는 공급자 Id에 정의 된  **\<진단 >** 섹션. 추적 참가자에는 구독하는 추적 레코드를 지정하기 위해 연결된 프로필이 있습니다. 이 정의한는 **profileName** 특성에는  **\<추가 >** 요소입니다. 추적 참가자에 추가 되 고, 정의 되 면는  **\<etwTracking >** 서비스 동작입니다. 이렇게 하면 선택된 추적 참가자가 워크플로 인스턴스의 확장에 추가되어 추적 레코드를 받기 시작합니다.  
  
```xml
<configuration>   
  <system.web>   
    <compilation targetFrameworkMoniker=".NETFramework,Version=v4.0"/>   
  </system.web>   
  <system.serviceModel>   
    <diagnostics etwProviderId="52A3165D-4AD9-405C-B1E8-7D9A257EAC9F" />                
    <tracking>   
      <participants>   
        <add name="EtwTrackingParticipant"   
             type="System.Activities.Tracking.EtwTrackingParticipant, System.Activities, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"   
             profileName="HealthMonitoring_Tracking_Profile"/>   
      </participants>   
    </tracking>   
    <behaviors>   
      <serviceBehaviors>   
        <behavior>   
          <etwTracking profileName="Sample Tracking Profile"/>  
        </behavior>   
      </serviceBehaviors>   
    </behaviors>   
  </system.serviceModel>   
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection>  
 <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>  
 <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>  
 [워크플로 추적](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [추적 참가자](../../../../../docs/framework/windows-workflow-foundation/tracking-participants.md)
