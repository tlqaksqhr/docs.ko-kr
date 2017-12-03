---
title: '&lt;baseAddressPrefixFilters&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8cab2a9a-c51f-4283-bb60-2ad0c274fd46
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 39ceaf3377f1da7f3f953024e1207618df84bf1d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="ltbaseaddressprefixfiltersgt"></a>&lt;baseAddressPrefixFilters&gt;
IIS에서 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 응용 프로그램을 호스트할 때 적합한 IIS(인터넷 정보 서비스) 바인딩을 선택하기 위한 메커니즘을 제공할 통과 필터를 지정하는 구성 요소의 컬렉션을 나타냅니다.  
  
> [!WARNING]
>  \<baseAddressPrefixFilters > 대신 정규화 된 컴퓨터 이름을 사용 하 여, "localhost"를 인식 하지 않습니다.  
  
 \<시스템입니다. ServiceModel >  
\<ServiceHostingEnvironment >  
  
## <a name="syntax"></a>구문  
  
```xml  
<serviceHostingEnvironment>  
     <baseAddressPrefixFilters>  
        <add prefix="string"/>  
     </baseAddressPrefixFilters>  
</serviceHostingEnvironment>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
 없음  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-baseaddressprefixfilter.md)|서비스 호스트에서 사용하는 기본 주소에 대한 접두사 필터를 지정하는 구성 요소를 추가합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<serviceHostingEnvironment >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|특정 전송을 위해 서비스 호스팅 환경에서 인스턴스화하는 형식을 정의합니다.|  
  
## <a name="remarks"></a>설명  
 접두사 필터는 공유 호스팅 공급자가 서비스에 사용될 URI를 지정하는 방법을 제공합니다. 이 방법을 사용하면 공유 호스트가 동일한 사이트의 동일한 체계에 대해 기본 주소가 다른 여러 응용 프로그램을 호스트할 수 있습니다.  
  
 IIS 웹 사이트는 가상 디렉터리를 포함하는 가상 응용 프로그램의 컨테이너입니다. 사이트의 응용 프로그램은 하나 이상의 IIS 바인딩을 통해 액세스될 수 있습니다. IIS 바인딩은 바인딩 프로토콜과 바인딩 정보라는 두 가지 정보를 제공합니다. 바인딩 프로토콜(예: HTTP)은 통신이 이루어지는 체계를 정의하며, 바인딩 정보(예: IP 주소, 포트, Hostheader)는 사이트 액세스에 사용되는 데이터를 포함합니다.  
  
 IIS에서는 각 사이트에 대해 여러 개의 IIS 바인딩을 지정할 수 있으므로, 각 체계에 대해 여러 개의 기본 주소가 생성됩니다. 사이트에서 호스트되는 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 서비스는 체계별로 단 하나의 기본 주소에 대한 바인딩만 허용하므로 접두사 필터 기능을 사용하면 호스트되는 서비스에 대해 필요한 기본 주소를 선택할 수 있습니다. IIS에서 제공하는 들어오는 기본 주소는 선택적 접두사 목록 필터를 기반으로 필터링됩니다.  
  
 예를 들어, 사이트에서 다음 기본 주소를 포함할 수 있습니다.  
  
```  
http://testl.fabrikam.com/Service.svc  
http://test2.fabrikam.com/Service.svc  
```  
  
 다음 구성 파일을 사용하여 appdomain 수준에서 접두사 필터를 지정할 수 있습니다.  
  
```xml  
<system.serviceModel>  
  <serviceHostingEnvironment>  
     <baseAddressPrefixFilters>  
        <add prefix="net.tcp://test1.fabrikam.com:8000"/>  
        <add prefix="http://test2.fabrikam.com:9000"/>  
    </baseAddressPrefixFilters>  
  </serviceHostingEnvironment>  
</system.serviceModel>  
```  
  
 이 예제에서 `net.tcp://test1.fabrikam.com:8000` 및 `http://test2.fabrikam.com:9000`은 해당 체계에서 통과되도록 허용된 유일한 기본 주소입니다.  
  
 기본적으로, 접두사가 지정되지 않으면 모든 주소가 통과됩니다. 접두사를 지정하면 해당 체계에서 일치하는 기본 주소만 통과됩니다.  
  
> [!NOTE]
>  필터는 와일드카드를 지원하지 않습니다. 또한 IIS에서 제공하는 baseAddress는 `baseAddressPrefixFilters` 목록에 없는 다른 체계에 바인딩되는 주소를 가질 수 있습니다. 이러한 주소는 필터링되지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Configuration.BaseAddressPrefixFilterElementCollection>  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>  
 <xref:System.ServiceModel.ServiceHostingEnvironment>  
 [호스팅](../../../../../docs/framework/wcf/feature-details/hosting.md)
