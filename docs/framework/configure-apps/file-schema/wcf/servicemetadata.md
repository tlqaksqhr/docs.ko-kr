---
title: '&lt;serviceMetadata&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2b4c3b4c-31d4-4908-a9b7-5bb411c221f2
caps.latest.revision: "28"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a771b3b89c9031a011185a579e70767081d20597
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltservicemetadatagt"></a>&lt;serviceMetadata&gt;
서비스 메타데이터 및 관련 정보의 게시를 지정합니다.  
  
\<system.serviceModel >  
\<동작 >  
\<serviceBehaviors >  
\<동작 >  
\<serviceMetadata >  
  
## <a name="syntax"></a>구문  
  
```xml
<serviceMetadata externalMetadataLocation="String"  
                 httpGetBinding="String" 
                 httpGetBindingConfiguration="String"  
                 httpGetEnabled="Boolean" 
                 httpGetUrl="String" 
                 httpsGetBinding="String" 
                 httpsGetBindingConfiguration="String"  
                 httpsGetEnabled="Boolean"   
                 httpsGetUrl="String"  
                 policyVersion="Policy12/Policy15" />  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|externalMetadataLocation|자동 생성된 WSDL 대신 WSDL 및 MEX 요청에 대한 응답으로 사용자에게 반환되는 WSDL 파일의 위치가 포함되는 URI입니다. 이 특성을 설정하지 않으면 기본 WSDL이 반환됩니다. 기본값은 빈 문자열입니다.|  
|httpGetBinding|HTTP GET을 통해 메타데이터 검색에 사용할 바인딩 형식을 지정하는 문자열입니다. 이 설정은 선택 사항입니다. 이 설정을 지정하지 않으면 기본 바인딩이 사용됩니다.<br /><br /> <xref:System.ServiceModel.Channels.IReplyChannel>을 지원하는 내부 바인딩 요소가 있는 바인딩만 지원됩니다. 또한 바인딩의 <xref:System.ServiceModel.Channels.MessageVersion> 속성은 <xref:System.ServiceModel.Channels.MessageVersion.None%2A>이어야 합니다.|  
|httpGetBindingConfiguration|이 바인딩의 추가 구성 정보를 참조하는 `httpGetBinding` 특성에 지정된 바인딩의 이름을 설정하는 문자열입니다. 이와 동일한 이름이 `<bindings>` 섹션에서 정의되어야 합니다.|  
|httpGetEnabled|HTTP/Get 요청을 사용하여 검색을 위해 서비스 메타데이터를 게시하는지 여부를 지정하는 부울 값입니다. 기본값은 `false`입니다.<br /><br /> httpGetUrl 특성이 지정되지 않을 경우 메타데이터가 게시되는 주소는 서비스 주소에 "?wsdl"을 붙인 것입니다. 예를 들어, 서비스 주소가 "http://localhost:8080/CalculatorService"라면 HTTP/Get 메타데이터 주소는 "http://localhost:8080/CalculatorService?wsdl"입니다.<br /><br /> 이 속성이 `false`, 서비스의 주소 기반 하지 않는 HTTP 또는 HTTPS로 또는 "? wsdl"이 무시 됩니다.|  
|httpGetUrl|HTTP/Get 요청을 사용하여 검색을 위해 메타데이터가 게시될 주소를 지정하는 URI입니다. 상대 URI가 지정되면 해당 URI는 서비스의 기본 주소에 상대적으로 처리됩니다.|  
|httpsGetBinding|HTTPS GET을 통해 메타데이터 검색에 사용할 바인딩 형식을 지정하는 문자열입니다. 이 설정은 선택 사항입니다. 이 설정을 지정하지 않으면 기본 바인딩이 사용됩니다.<br /><br /> <xref:System.ServiceModel.Channels.IReplyChannel>을 지원하는 내부 바인딩 요소가 있는 바인딩만 지원됩니다. 또한 바인딩의 <xref:System.ServiceModel.Channels.MessageVersion> 속성은 <xref:System.ServiceModel.Channels.MessageVersion.None%2A>이어야 합니다.|  
|httpsGetBindingConfiguration|이 바인딩의 추가 구성 정보를 참조하는 `httpsGetBinding` 특성에 지정된 바인딩의 이름을 설정하는 문자열입니다. 이와 동일한 이름이 `<bindings>` 섹션에서 정의되어야 합니다.|  
|httpsGetEnabled|HTTPS/Get 요청을 사용하여 검색을 위해 서비스 메타데이터를 게시하는지 여부를 지정하는 부울 값입니다. 기본값은 `false`입니다.<br /><br /> httpsGetUrl 특성이 지정되지 않을 경우 메타데이터가 게시되는 주소는 서비스 주소에 "?wsdl"를 붙인 것입니다. 예를 들어, 서비스 주소가 "https://localhost:8080/CalculatorService"라면 HTTP/Get 메타데이터 주소는 "https://localhost:8080/CalculatorService?wsdl"입니다.<br /><br /> 이 속성이 `false`, 서비스의 주소 기반 하지 않는 HTTP 또는 HTTPS로 또는 "? wsdl"이 무시 됩니다.|  
|httpsGetUrl|HTTPS/Get 요청을 사용하여 검색을 위해 메타데이터가 게시될 주소를 지정하는 URI입니다.|  
|policyVersion|사용 중인 WS-Policy 사양의 버전을 지정하는 문자열입니다. 이 특성은 <xref:System.ServiceModel.Description.PolicyVersion> 형식입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<동작 >](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|동작 요소를 지정합니다.|  
  
## <a name="remarks"></a>설명  
 이 구성 요소를 사용하면 서비스의 메타데이터 게시 기능을 제어할 수 있습니다. 중요한 서비스 메타데이터를 실수로 공개하지 않도록 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 서비스의 기본 구성에서는 메타데이터 게시를 사용하지 않도록 설정합니다. 이 동작은 기본적으로 안전하지만 구성에서 서비스의 메타데이터 게시 동작이 명시적으로 사용하도록 설정되어 있지 않은 경우 Svcutil.exe 등의 메타데이터 가져오기 도구를 사용하여 서비스를 호출하는 데 필요한 클라이언트 코드를 생성할 수 없습니다. 이 구성 요소를 사용하면 서비스에 대해 이 게시 동작을 사용하도록 설정할 수 있습니다.  
  
 이 동작 구성의 자세한 예제를 보려면 [메타 데이터 게시 동작이](../../../../../docs/framework/wcf/samples/metadata-publishing-behavior.md)합니다.  
  
 선택적 `httpGetBinding` 및 `httpsGetBinding` 특성을 사용하면 HTTP GET 또는 HTTPS GET을 통해 메타데이터 검색에 사용되는 바인딩을 구성할 수 있습니다. 바인딩을 지정하지 않으면 메타데이터 검색에 기본 바인딩(HTTP의 경우 `HttpTransportBindingElement`, HTTPS의 경우 `HttpsTransportBindingElement`)이 적절하게 사용됩니다. 기본 제공 WCF 바인딩에는 이러한 특성을 사용할 수 없습니다. <xref:System.ServiceModel.Channels.IReplyChannel>을 지원하는 내부 바인딩 요소가 있는 바인딩만 지원됩니다. 또한 바인딩의 <xref:System.ServiceModel.Channels.MessageVersion> 속성은 <xref:System.ServiceModel.Channels.MessageVersion.None%2A>이어야 합니다.  
  
 악의적인 사용자에 대한 서비스 노출을 줄이기 위해 HTTPS(HTTP를 통한 SSL) 메커니즘을 사용하여 전송 보안을 유지할 수 있습니다. 이렇게 하려면 먼저 적절한 X.509 인증서를 서비스를 호스트하는 컴퓨터의 특정 포트에 바인딩해야 합니다. ([!INCLUDE[crdefault](../../../../../includes/crdefault-md.md)] [인증서 작업](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).) 그런 다음 이 요소를 서비스 구성에 추가하고 `httpsGetEnabled` 특성을 `true`로 설정합니다. 마지막으로 다음 예제와 같이 `httpsGetUrl` 특성을 서비스 메타데이터 끝점의 URL로 설정합니다.  
  
```xml
<behaviors>  
  <serviceBehaviors>  
    <behavior name="NewBehavior">  
      <serviceMetadata httpsGetEnabled="true"   
                       httpsGetUrl="https://myComputerName/myEndpoint" />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="example"></a>예제  
 다음 예제에서는 구성 서비스를 사용 하 여 메타 데이터를 노출 하는 \<serviceMetadata > 요소입니다. 또한 `IMetadataExchange` 계약을 WS-MetadataExchange(MEX) 프로토콜의 구현으로 노출하도록 끝점을 구성합니다. 예제에서는 `mexHttpBinding`에 해당하는 편의 표준 바인딩인 `wsHttpBinding`을 `None`으로 설정된 보안 모드와 함께 사용합니다. "mex"의 상대 주소는 끝점에 사용되는데, 이를 서비스의 기본 주소와 비교하여 확인하는 경우 끝점 주소가 http://localhost/servicemodelsamples/service.svc/mex가 됩니다.  
  
```xml
<configuration>  
  <system.serviceModel>  
    <services>  
      <service name="Microsoft.ServiceModel.Samples.CalculatorService" 
               behaviorConfiguration="CalculatorServiceBehavior">  
        <!-- This endpoint is exposed at the base address provided by the host: http://localhost/servicemodelsamples/service.svc -->  
        <endpoint address=""  
                  binding="wsHttpBinding"  
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />  
        <!-- The mex endpoint is exposed at http://localhost/servicemodelsamples/service.svc/mex   
             To expose the IMetadataExchange contract, you must enable the serviceMetadata behavior as demonstrated below. -->  
        <endpoint address="mex"  
                  binding="mexHttpBinding"  
                  contract="IMetadataExchange" />  
      </service>  
    </services>  

    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="CalculatorServiceBehavior">  
          <!-- The serviceMetadata behavior publishes metadata through   
               the IMetadataExchange contract. When this behavior is   
               present, you can expose this contract through an endpoint   
               as shown above. Setting httpGetEnabled to true publishes   
               the service's WSDL at the <baseaddress>?wsdl  
               eg. http://localhost/servicemodelsamples/service.svc?wsdl -->  
          <serviceMetadata httpGetEnabled="True"/>  
          <serviceDebug includeExceptionDetailInFaults="False" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Configuration.ServiceMetadataPublishingElement>  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>  
 [보안 동작](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [메타 데이터 게시 동작](../../../../../docs/framework/wcf/samples/metadata-publishing-behavior.md)
