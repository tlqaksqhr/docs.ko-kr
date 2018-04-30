---
title: 클라이언트 구성
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5da5bd3b-65d9-43b7-91b9-cc9e989b1350
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c2c0d17c7274cc9fdaf1b5080950ddb4f69f539a
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/30/2018
---
# <a name="client-configuration"></a>클라이언트 구성
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 클라이언트 구성을 사용하여 클라이언트에서 서비스 끝점에 연결하는 데 사용하는 클라이언트 끝점의 "ABC" 속성인 계약, 바인딩 동작 및 주소를 지정할 수 있습니다. [ \<클라이언트 >](../../../../docs/framework/configure-apps/file-schema/wcf/client.md) 요소에는 [ \<끝점 >](http://msdn.microsoft.com/library/13aa23b7-2f08-4add-8dbf-a99f8127c017) 해당 특성이 끝점 Abc를 구성 하는 데는 요소입니다. 이러한 특성에 대해서는 이 항목의 "끝점 구성" 단원에 설명되어 있습니다.  
  
 [ \<끝점 >](http://msdn.microsoft.com/library/13aa23b7-2f08-4add-8dbf-a99f8127c017) 포함 한 [ \<메타 데이터 >](../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md) 가져오기 및 내보내기 메타 데이터에 대 한 설정을 지정 하는 데 사용 되는 요소는 [ \<헤더 >](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) 사용자 지정 주소 헤더의 컬렉션을 포함 하는 요소 및 [ \<identity >](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) 다른 끝점에서 끝점을 인증할 수 있도록 하는 요소 메시지를 교환 합니다. [ \<헤더 >](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) 및 [ \<identity >](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) 의 일부인 요소는 <xref:System.ServiceModel.EndpointAddress> 에서 설명 하는 [주소](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md) 항목입니다. 메타데이터 확장명 사용을 설명하는 항목에 대한 링크가 이 항목의 메타데이터 구성 하위 단원에 제공됩니다.  
  
## <a name="configuring-endpoints"></a>끝점 구성  
 클라이언트 구성은 클라이언트가 하나를 지정할 수 있도록 설계 되었습니다 또는 각각 고유한 이름, 더 많은 끝점 주소 및 계약을 참조는 [ \<바인딩 >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) 및 [ \< 동작 >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) 해당 끝점을 구성 하는 데 사용할 클라이언트 구성 요소입니다. 클라이언트 구성 파일의 이름은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 런타임에 예상하는 이름인 App.config"로 지정되어야 합니다. 다음 예제에서는 클라이언트 구성 파일을 보여 줍니다.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
        <client>  
          <endpoint  
            name="endpoint1"  
            address="http://localhost/ServiceModelSamples/service.svc"  
            binding="wsHttpBinding"  
            bindingConfiguration="WSHttpBinding_IHello"  
            behaviorConfiguration="IHello_Behavior"  
            contract="IHello" >  
  
            <metadata>  
              <wsdlImporters>  
                <extension  
                  type="Microsoft.ServiceModel.Samples.WsdlDocumentationImporter, WsdlDocumentation"/>  
              </wsdlImporters>  
            </metadata>  
  
            <identity>  
              <servicePrincipalName value="host/localhost" />  
            </identity>  
          </endpoint>  
// Add another endpoint by adding another <endpoint> element.  
          <endpoint  
            name="endpoint2">  
           //Configure another endpoint here.  
          </endpoint>  
        </client>  
  
//The bindings section references by the bindingConfiguration endpoint attribute.  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_IHello"   
                 bypassProxyOnLocal="false"   
                 hostNameComparisonMode="StrongWildcard">  
          <readerQuotas maxDepth="32"/>  
          <reliableSession ordered="true"   
                           enabled="false" />  
          <security mode="Message">  
           //Security settings go here.  
          </security>  
        </binding>  
        <binding name="Another Binding"  
        //Configure this binding here.  
        </binding>  
          </wsHttpBinding>  
        </bindings>  
  
//The behavior section references by the behaviorConfiguration endpoint attribute.  
        <behaviors>  
            <endpointBehaviors>  
                <behavior name=" IHello_Behavior ">  
                    <clientVia />  
                </behavior>  
            </endpointBehaviors>  
        </behaviors>  
  
    </system.serviceModel>  
</configuration>  
```  
  
 선택적 `name` 특성은 지정된 계약의 끝점을 고유하게 식별합니다. 이 특성은 <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A> 또는 <xref:System.ServiceModel.ClientBase%601.%23ctor%2A>가 서비스에 대한 채널을 만들 때 로드해야 하는 대상 끝점을 클라이언트 구성에서 지정하는 데 사용됩니다. 와일드카드 끝점 구성 이름 "*"를 사용 가능하며 이 와일드카드는 정확하게 하나의 사용 가능한 끝점 구성이 있으면 파일에서 끝점 구성을 로드해야 하고 그렇지 않으면 예외를 throw해야 함을 <xref:System.ServiceModel.ChannelFactory.ApplyConfiguration%2A> 메서드에 알려줍니다. 이 특성을 생략하면 해당하는 끝점이 지정된 계약 형식과 연결된 기본 끝점으로 사용됩니다. `name` 특성의 기본값은 다른 이름과 마찬가지로 일치되는 빈 문자열입니다.  
  
 모든 끝점에는 해당 끝점을 찾아서 식별할 수 있는 연결된 주소가 있어야 합니다. `address` 특성을 사용하면 끝점의 위치를 제공하는 URL을 지정할 수 있습니다. URI(Uniform Resource Identifier)를 만든 다음 <xref:System.ServiceModel.ServiceHost> 메서드 중 하나를 사용하여 <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>에 추가하여 서비스 끝점의 주소를 코드로 지정할 수도 있습니다. 자세한 내용은 참조 [주소](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md)합니다. 소개에 표시 된 대로 [ \<헤더 >](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) 및 [ \<identity >](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md) 의 일부인 요소는 <xref:System.ServiceModel.EndpointAddress> 에서도 설명 하 고는 [ 주소](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md) 항목입니다.  
  
 `binding` 특성은 서비스에 연결할 때 사용할 끝점 바인딩 형식을 나타냅니다. 형식에 등록된 구성 섹션이 있어야 형식을 참조할 수 있습니다. 이 이전 예에서 [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) 나타냅니다 끝점을 사용 하는 섹션은 <xref:System.ServiceModel.WSHttpBinding>합니다. 그러나 끝점에서 사용할 수 있는 지정된 형식의 바인딩이 여러 개 있을 수도 있습니다. 이러한 각 항목에 자체 [ \<바인딩 >](../../../../docs/framework/misc/binding.md) 요소 (바인딩) 형식 요소입니다. `bindingconfiguration` 특성은 동일한 형식의 바인딩을 구분하는 데 사용됩니다. 해당 값과 일치는 `name` 특성에는 [ \<바인딩 >](../../../../docs/framework/misc/binding.md) 요소입니다. 클라이언트를 구성 하는 방법에 대 한 자세한 내용은 참조 구성을 사용 하 여 바인딩 [하는 방법: 구성에서 클라이언트 바인딩 지정](../../../../docs/framework/wcf/how-to-specify-a-client-binding-in-configuration.md)합니다.  
  
 `behaviorConfiguration` 특성을 지정 합니다. 사용 [ \<동작 >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) 의 [ \<endpointBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md) 끝점에서 사용 해야 합니다. 해당 값과 일치는 `name` 특성에는 [ \<동작 >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) 요소입니다. 구성을 사용 하 여 클라이언트 동작을 지정 하는 예제를 보려면 [클라이언트 동작 구성](../../../../docs/framework/wcf/configuring-client-behaviors.md)합니다.  
  
 `contract` 특성은 끝점이 공개하는 계약을 지정합니다. 이 값은 <xref:System.ServiceModel.ServiceContractAttribute.ConfigurationName%2A>의 <xref:System.ServiceModel.ServiceContractAttribute>에 매핑됩니다. 기본값은 서비스를 구현하는 클래스의 전체 형식 이름입니다.  
  
### <a name="configuring-metadata"></a>메타데이터 구성  
 [ \<메타 데이터 >](../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md) 메타 데이터를 등록 하는 데 사용 되는 설정을 가져오기 확장을 지정 하려면 요소를 사용 합니다. 메타 데이터 시스템 확장에 대 한 자세한 내용은 참조[메타 데이터 시스템 확장](../../../../docs/framework/wcf/extending/extending-the-metadata-system.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [끝점: 주소, 바인딩 및 계약](../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)  
 [클라이언트 동작 구성](../../../../docs/framework/wcf/configuring-client-behaviors.md)
