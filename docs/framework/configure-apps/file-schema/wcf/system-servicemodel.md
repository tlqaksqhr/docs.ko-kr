---
title: '&lt;system.serviceModel&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.ServiceModel
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel
helpviewer_keywords:
- <system.serviceModel> element
- system.serviceModel element
ms.assetid: 78519531-ad7a-40d3-b3e7-42f1103d8854
caps.latest.revision: "26"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 16a3b9b361048344993fdc338544b6b0ceb95387
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="ltsystemservicemodelgt"></a>&lt;system.serviceModel&gt;
이 구성 섹션에는 모든 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] ServiceModel 구성 요소가 포함됩니다.  
  
## <a name="syntax"></a>구문  
  
```xml  
<system.serviceModel>  
  <behaviors>  
  </behaviors>  
  <bindings>  
  </bindings>  
  <client>  
  </client>  
  <comContracts>  
  </comContracts>  
  <commonBehaviors>  
  </commonBehaviors>  
  <diagnostics>  
  </diagnostics>  
  <extensions>  
  </extensions>
  <protocolMapping>
  </protocolMapping>
  <routing>
  </routing>  
  <serviceHostingEnvironment>  
  </serviceHostingEnvironment>  
  <services>  
  </services>
  <standardEndpoints>  
  </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
 없음  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<동작 >](../../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)|이 섹션은 두 자식 컬렉션 `endpointBehaviors` 및 `serviceBehaviors`를 정의합니다.  각 컬렉션은 끝점 및 서비스가 사용하는 동작 요소를 각각 정의합니다. 각 동작 요소는 고유한 `name` 특성으로 식별됩니다.|  
|[\<바인딩 >](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|이 섹션에는 표준 및 사용자 지정 바인딩 컬렉션이 포함됩니다. 각 항목은 고유한 `name`으로 식별됩니다. 서비스에서는 `name`을 통해 바인딩을 연결하여 바인딩을 사용합니다.|  
|[\<클라이언트 >](../../../../../docs/framework/configure-apps/file-schema/wcf/client.md)|이 섹션에는 클라이언트가 서비스에 연결하는 데 사용하는 끝점의 목록이 포함됩니다.|  
|[\<comContracts >](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)|이 섹션은 WCF 및 COM interop에 사용하도록 설정된 COM 계약을 정의합니다.|  
|[\<c o m m >](../../../../../docs/framework/configure-apps/file-schema/wcf/commonbehaviors.md)|이 섹션은 machine.config 파일에서만 정의할 수 있습니다. 이 섹션은 두 자식 컬렉션 `endpointBehaviors` 및 `serviceBehaviors`를 정의합니다.  각 컬렉션은 컴퓨터의 모든 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 끝점 및 서비스가 사용하는 동작 요소를 각각 정의합니다.  동작을 둘 다에 정의 된 경우 `<commonBehaviors>` 및 `<behaviors>` 섹션의 동작이 \<동작 > 섹션 우선 합니다.|  
|[\<확장 >](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions-section.md)|이 섹션에는 사용자 정의 바인딩, 동작 및 확장의 기타 측면을 만들 수 있도록 하는 확장명 컬렉션이 포함됩니다.|  
|[\<진단 >](../../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md)|이 섹션에는 WCF의 진단 기능에 대한 설정이 포함됩니다. 사용자는 추적, 성능 카운터 및 WMI 공급자를 사용하거나 사용하지 않도록 설정하고 사용자 지정 메시지 필터를 추가할 수 있습니다.|  
|[\<protocolMapping >](../../../../../docs/framework/configure-apps/file-schema/wcf/protocolmapping.md)|이 섹션에는 전송 프로토콜 체계 (예: http, net.tcp, net.pipe 등) 및 WCF 바인딩 간의 기본 프로토콜 매핑 집합을 정의합니다.|  
|[\<라우팅 >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|이 섹션은 들어오는 메시지 및 필터가 일치할 때 메시지를 보낼 대상 끝점을 정의하는 라우팅 테이블을 평가할 때 사용되는 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> 형식을 결정하는 라우팅 필터 집합을 정의합니다.|  
|[\<serviceHostingEnvironment >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|이 섹션은 특정 전송을 위해 서비스 호스팅 환경에서 인스턴스화하는 형식을 정의합니다. 이 섹션이 비어 있으면 기본 형식이 사용됩니다.|  
|[\<서비스 >](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md)|이 섹션에는 서비스의 컬렉션이 포함됩니다. 이 요소에는 어셈블리에 정의된 서비스별로 서비스의 설정을 지정하는 `service` 요소가 포함됩니다.|  
|[\<d a r d >](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|이 섹션은 다시 사용할 수 있는 미리 구성된 끝점인 표준 끝점의 컬렉션을 정의합니다. 표준 끝점에는 고정 값으로 설정된 하나 이상의 주소, 바인딩 및 계약 특성이 있습니다. 예를 들어 검색 끝점에서는 계약이 고정됩니다. 표준 끝점을 사용자 지정 바인딩 정의와 유사한 새 속성과 함께 사용하여 서비스 끝점을 확장할 수도 있습니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|\<configuration>|.NET 구성 파일에 있는 모든 구성 요소의 루트 요소입니다.|  
  
## <a name="remarks"></a>설명  
 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]에서는 다른 제품의 구성 섹션에 요소를 추가하지 않습니다.  
  
 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 서비스는 구성 파일의 `services` 섹션에 정의됩니다. 어셈블리에는 여러 개의 서비스가 포함될 수 있습니다. 서비스별로 해당 `service` 구성 섹션이 있습니다. 해당 단원 및 내용에서는 특정 서비스의 서비스 계약, 동작 및 끝점을 정의합니다.  
  
 서비스의 `name` 특성만 필수입니다.  기본적으로 서비스 이름은 서비스를 구현하는 데 사용되는 기본 CLR 형식을 설명하지만 <xref:System.ServiceModel.ServiceContractAttribute>에서 ConfigurationName 속성을 변경하여 CLR 형식 요구 사항을 재정의할 수 있습니다.  
  
 `behaviorConfiguration` 특성은 선택 사항이며 이 특성은 서비스에 사용되는 서비스 동작을 식별합니다. 이 특성에 지정된 동작은 동일한 파일이나 부모 파일과 같은 동일한 구성 파일의 범위에 정의된 서비스 동작에 연결되어야 합니다.  
  
 각 서비스는 `endpoint` 요소에 정의된 하나 이상의 끝점을 노출합니다. 각 끝점에는 고유한 주소와 바인딩이 있습니다. 구성 파일 내에서 사용되는 모든 바인딩은 파일 범위 내에서 정의되어야 합니다.  
  
 바인딩은 `name` 및 `bindingConfiguration` 특성을 조합하여 끝점에 연결됩니다. `binding` 특성은 바인딩이 정의된 섹션을 정의합니다. `bindingConfiguration` 특성은 바인딩 섹션에서 사용되는 구성된 바인딩을 정의합니다. 바인딩 섹션에서는 여러 개의 구성된 바인딩을 정의할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음은 WCF 구성 파일의 예제입니다.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
    <system.serviceModel>  
        <behaviors>  
           <!-- List of Behaviors -->  
        </behaviors>  
        <client>  
           <!-- List of Endpoints -->  
        </client>  
        <diagnostics wmiProviderEnabled="false" performanceCountersEnabled="false" tracingEnabled="false">  
        </diagnostics>  
        <serviceHostingEnvironment>  
           <!-- List of entries -->  
        </serviceHostingEnvironment>  
        <comContracts>  
           <!-- List of COM+ Contracts -->  
        </comContracts>          
        <services>  
           <!-- List of Services -->  
        </services>  
        <bindings>  
           <!-- List of Bindings -->  
        </bindings>  
    </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Configuration.ServiceModelSectionGroup>
