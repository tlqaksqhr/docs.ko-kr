---
title: ASP.NET을 사용하지 않고 WCF AJAX 서비스 만들기
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ba4a7d1b-e277-4978-9f62-37684e6dc934
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b652bcd522a8eea81b3d1218fbd054ee0b2caea8
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="creating-wcf-ajax-services-without-aspnet"></a>ASP.NET을 사용하지 않고 WCF AJAX 서비스 만들기
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] AJAX 서비스는 ASP.NET AJAX가 없어도 모든 JavaScript 사용 웹 페이지에서 액세스할 수 있습니다. 이 항목에서는 이런 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스를 만드는 방법에 대해 설명합니다.  
  
 사용 하 여에 대 한 지침은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ASP.NET AJAX와 함께 참조 [ASP.NET AJAX 용 WCF 서비스를 만드는](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)합니다.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] AJAX 서비스 만들기에 대한 세 가지 부분은 다음과 같습니다.  
  
-   브라우저에서 액세스할 수 있는 AJAX 끝점 만들기  
  
-   AJAX 호환 서비스 계약 만들기  
  
-   WCF AJAX 서비스 액세스  
  
## <a name="creating-an-ajax-endpoint"></a>AJAX 끝점 만들기  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스에서 AJAX 지원을 사용 가능하게 하는 가장 간단한 방법은 다음 예제에서와 같이 서비스와 연결된 .svc 파일에서 <xref:System.ServiceModel.Activation.WebServiceHostFactory>를 사용하는 것입니다.  
  
```  
<%ServiceHost   
    language=c#  
    Debug="true"  
    Service="Microsoft.Ajax.Samples.CityService"  
    Factory=System.ServiceModel.Activation.WebServiceHostFactory  
%>  
```  
  
 또는 구성을 사용하여 AJAX 끝점을 추가할 수도 있습니다. 서비스 끝점에서 <xref:System.ServiceModel.WebHttpBinding>을 사용하고 해당 끝점을 다음 코드 조각에 표시된 것처럼 <xref:System.ServiceModel.Description.WebHttpBehavior>로 구성합니다.  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="AjaxBehavior">  
          <webHttp/>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    <services>  
      <service name="Microsoft.Ajax.Samples.CityService">  
        <endpoint   
          address="ajaxEndpoint"  
          behaviorConfiguration="AjaxBehavior"  
          binding="webHttpBinding"  
          contract="Microsoft.Ajax.Samples.ICityService" />  
      </service>  
    </services>  
  </system.serviceModel>  
</configuration>  
```  
  
 작업 예제를 참조 하십시오.는 [JSON 및 XML을 포함 한 AJAX 서비스](../../../../docs/framework/wcf/samples/ajax-service-with-json-and-xml-sample.md)합니다.  
  
## <a name="creating-an-ajax-compatible-service-contract"></a>AJAX 호환 서비스 계약 만들기  
 기본적으로 AJAX 끝점을 통해 노출된 서비스 계약은 데이터를 XML 형식으로 반환합니다. 또한 기본적으로 서비스 작업은 다음 예제에서처럼 HTTP POST 요청을 통해 끝점 주소 다음에 작업 이름이 오는 URL에 액세스할 수 있습니다.  
  
```  
[OperationContract]  
string[] GetCities(string firstLetters);  
```  
  
 이 작업은 HTTP POST를 사용 하 여 액세스할 `http://serviceaddress/endpointaddress/GetCities` XML 메시지를 반환 합니다.  
  
 전체 웹 프로그래밍 모델을 사용하여 이러한 기본 측면을 사용자 지정할 수 있습니다. 예를 들어 <xref:System.ServiceModel.Web.WebGetAttribute> 또는 <xref:System.ServiceModel.Web.WebInvokeAttribute> 특성을 사용하여 작업이 응답하는 HTTP 동사를 제어하거나 이러한 각 특성의 `UriTemplate` 속성을 사용하여 사용자 지정 URI를 지정할 수 있습니다. 자세한 내용은 참조는 [WCF 웹 HTTP 프로그래밍 모델](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md) 항목입니다.  
  
 JSON 데이터 형식은 AJAX 서비스에서 주로 사용됩니다. XML 대신 JSON을 반환하는 작업을 만들려면 <xref:System.ServiceModel.Web.WebGetAttribute.ResponseFormat%2A> (또는 <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A>) 속성을 <xref:System.ServiceModel.Web.WebMessageFormat.Json>으로 설정합니다. [독립 실행형 JSON Serialization](../../../../docs/framework/wcf/feature-details/stand-alone-json-serialization.md) 항목에서는 JSON에 어떻게 기본 제공.NET 유형 및 데이터 계약 형식 지도 보여 줍니다.  
  
 일반적으로 JSON 요청 및 응답은 하나의 항목으로만 구성됩니다. 앞의 `GetCities` 작업의 경우 요청은 다음 문과 유사하고.  
  
```  
"na"  
```  
  
 해당 요청에 대한 응답은 다음 문과 유사합니다.  
  
```  
["Nairobi", "Naples", "Nashville"]  
```  
  
 작업에서 추가 매개 변수를 가져올 경우 요청 스타일은 단일 JSON 개체에서 두 매개 변수를 래핑하기 위해 래핑되어야 합니다. 이 스타일 JSON 메시지의 예는 다음 예제에 나와 있습니다.  
  
```json  
{"firstLetters": "na", "maxNumber": 2}  
```  
  
 다음 계약이 이 메시지를 받습니다.  
  
```  
[WebInvoke(BodyStyle=WebMessageBodyStyle.WrappedRequest, ResponseFormat=WebMessageFormat.Json)]  
[OperationContract]  
string[] GetCities(string firstLetters, int maxNumber);  
```  
  
## <a name="accessing-ajax-services"></a>AJAX 서비스 액세스  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] AJAX 끝점은 항상 JSON 및 XML 요청 모두를 수락합니다.  
  
 "응용 프로그램/json"의 콘텐츠 형식으로 HTTP POST 요청은 JSON으로 되며 XML (예를 들어 "텍스트/xml")을 나타내는 콘텐츠 형식이 있는 XML로 처리 됩니다.  
  
 HTTP GET 요청에는 URL 자체의 모든 요청 매개 변수가 포함되어 있습니다.  
  
 끝점에 대한 HTTP 요청을 만드는 방법을 결정하는 것은 사용자의 몫입니다. 또한 사용자는 요청 본문을 형성하는 JSON 생성에 대한 전체 제어 권한을 가집니다. JavaScript에서 요청을 만드는 예를 참조 하십시오.는 [JSON 및 XML을 포함 한 AJAX 서비스](../../../../docs/framework/wcf/samples/ajax-service-with-json-and-xml-sample.md)합니다.
