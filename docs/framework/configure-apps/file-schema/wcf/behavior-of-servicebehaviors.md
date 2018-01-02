---
title: "&lt;serviceBehaviors&gt;의 &lt;behavior&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 78fc0a08-55de-416a-ac12-a5e6ffc9a987
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b86d685cd3b5fc26f2df2d3e722a908c04422d50
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltbehaviorgt-of-ltservicebehaviorsgt"></a>&lt;serviceBehaviors&gt;의 &lt;behavior&gt;
`behavior` 요소는 서비스의 동작에 대한 설정 컬렉션을 포함합니다. 각 동작은 해당 `name`으로 인덱싱됩니다. 서비스 사용 하 여이 이름을 통해 각 동작에 연결할 수는 `behaviorConfiguration` 특성에는 [ \<끝점 >](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) 요소입니다. 따라서 설정을 다시 정의하지 않고도 끝점에서 일반 동작 구성을 공유할 수 있습니다. [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)]부터는 바인딩 및 동작에 이름이 필요하지 않습니다. 기본 구성 및 이름이 없는 바인딩 및 동작에 대 한 자세한 내용은 참조 [단순화 된 구성](../../../../../docs/framework/wcf/simplified-configuration.md) 및 [WCF 서비스에 대 한 구성을 단순화](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)합니다.  
  
> [!NOTE]
>  Windows 워크플로 활동에는 동작 요소와 같은 [ \<sendMessageChannelCache >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/sendmessagechannelcache.md) 요소는에 설명 되어는 [ \<동작 >의 \< serviceBehaviors >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md) 페이지.  
  
 \<시스템입니다. ServiceModel >  
\<동작 >  
\<serviceBehaviors >  
\<동작 >  
  
## <a name="syntax"></a>구문  
  
```xml  
<system.ServiceModel>  
  <behaviors>  
    <serviceBehaviors>  
       <behavior name="String" />  
    </serviceBehaviors>  
  </behaviors>  
</system.ServiceModel>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|name|동작의 구성 이름을 포함하는 고유 문자열입니다. 이 값은 요소의 식별 문자열 역할을 하므로 고유한 사용자 정의 문자열이어야 합니다. [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)]부터는 바인딩 및 동작에 이름이 필요하지 않습니다. 기본 구성 및 이름이 없는 바인딩 및 동작에 대 한 자세한 내용은 참조 [단순화 된 구성](../../../../../docs/framework/wcf/simplified-configuration.md) 및 [WCF 서비스에 대 한 구성을 단순화](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)합니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)|DataContractSerializer에 대한 구성 데이터가 들어 있습니다.|  
|[\<persistenceProvider >](../../../../../docs/framework/configure-apps/file-schema/wcf/persistenceprovider.md)|사용할 지속성 공급자 구현 형식 및 지속성 작업에 사용할 제한 시간을 지정합니다.|  
|[\<라우팅 >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing-of-servicebehavior.md)|라우팅 서비스에 대한 런타임 액세스를 제공하여 라우팅 구성의 동적 수정을 허용합니다.|  
|[\<a g e r >](../../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthenticationmanager.md)|서비스 수준에서 전송, 메시지 또는 송신자의 유효성을 설정하는 워크플로 구성 요소를 제공합니다.|  
|[\<serviceAuthorization >](../../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md)|서비스 작업에 대한 액세스 권한을 부여하는 설정을 지정합니다.|  
|[\<serviceCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|서비스를 인증하는 데 사용되는 자격 증명 및 클라이언트 자격 증명 유효성 검사 관련 설정을 지정합니다.|  
|[\<serviceDebug >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicedebug.md)|[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 서비스의 디버깅 및 도움말 정보 기능을 지정합니다.|  
|[\<serviceDiscovery >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md)|서비스 끝점의 검색 기능을 지정합니다.|  
|[\<serviceMetadata >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicemetadata.md)|서비스 메타데이터 및 관련 정보의 게시를 지정합니다.|  
|[\<serviceSecurityAudit >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicesecurityaudit.md)|서비스 작업 중에 보안 이벤트의 감사를 사용하도록 하는 설정을 지정합니다.|  
|[\<serviceThrottling >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicethrottling.md)|[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 서비스의 스로틀 메커니즘을 지정합니다.|  
|[\<serviceTimeouts >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicetimeouts.md)|서비스에 대한 제한 시간을 지정합니다.|  
|[\<workflowRuntime >](../../../../../docs/framework/configure-apps/file-schema/wcf/workflowruntime.md)|워크플로 기반 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 서비스를 호스트하기 위해 WorkflowRuntime의 인스턴스에 대한 설정을 지정합니다.|  
|[\<useRequestHeadersForMetadataAddress >](../../../../../docs/framework/configure-apps/file-schema/wcf/userequestheadersformetadataaddress.md)|요청 메시지 헤더에서 메타데이터 주소 정보를 검색할 수 있도록 합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<serviceBehaviors >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md)|서비스 동작 요소의 컬렉션입니다.|
