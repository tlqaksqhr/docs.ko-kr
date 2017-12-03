---
title: '&lt;serviceActivations&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 97e665b6-1c51-410b-928a-9bb42c954ddb
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 43461f23476d1c387cec06f9aee893defa634201
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="ltserviceactivationsgt"></a>&lt;serviceActivations&gt;
[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 서비스 형식에 매핑되는 가상 서비스 활성화 설정을 정의하는 설정을 추가할 수 있는 구성 요소입니다. .svc 파일 없이도 WAS/IIS에서 호스트되는 서비스를 활성화할 수 있습니다.  
  
 \<시스템입니다. ServiceModel >  
\<serviceHostingEnvironment >  
\<serviceActivations >  
  
## <a name="syntax"></a>구문  
  
```xml  
<serviceHostingEnvironment>   
   <serviceActivations>  
      <add factory="String"  
           service="String"/>  
   </serviceActivations>  
</serviceHostingEnvironment>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
 없음  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-serviceactivations.md)|서비스 응용 프로그램의 활성화를 지정하는 구성 요소를 추가합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<serviceHostingEnvironment >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|특정 전송을 위해 서비스 호스팅 환경에서 인스턴스화하는 형식을 정의합니다.|  
  
## <a name="remarks"></a>설명  
 다음 예제에서는 web.config 파일 내에서 활성화 설정을 구성하는 방법을 보여 줍니다.  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <serviceHostingEnvironment>  
      <serviceActivations>  
        <add service="GreetingService"/>  
      </serviceActivations>  
    </serviceHostingEnvironment>  
  </system.serviceModel>  
</configuration>  
```  
  
 이 구성을 사용하여 .svc 파일을 사용하지 않고도 GreetingService를 활성화할 수 있습니다.  
  
 `<serviceHostingEnvironment>`는 응용 프로그램 수준 구성입니다. 구성을 포함하는 `web.config`를 가상 응용 프로그램의 루트 아래에 배치해야 합니다. 또한 `serviceHostingEnvironment`는 machinetoApplication 상속 가능 섹션입니다. 컴퓨터의 루트에 단일 서비스를 등록하는 경우 응용 프로그램의 모든 서비스가 이 서비스를 상속합니다.  
  
 구성 기반 활성화는 http 및 http가 아닌 프로토콜을 통한 활성화를 모두 지원합니다. 이를 위해 relatativeAddress의 확장 즉 .svc, .xoml 또는 .xamlx가 필요합니다. 직접 작성한 확장을 알려진 buildProviders에 매핑할 수 있으며, 이렇게 하면 모든 확장에서 서비스를 활성화할 수 있습니다. 충돌이 발생하면 `<serviceActivations>` 섹션이 .svc 등록을 재정의합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Configuration.ServiceActivationElementCollection>  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>  
 <xref:System.ServiceModel.ServiceHostingEnvironment>
