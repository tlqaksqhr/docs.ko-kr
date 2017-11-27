---
title: "ASP.NET을 사용하지 않고 WCF AJAX 서비스 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ba4a7d1b-e277-4978-9f62-37684e6dc934
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 70926e1deb9b4911a7d89d49280b9a0e6068cc42
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="creating-wcf-ajax-services-without-aspnet"></a><span data-ttu-id="aa41e-102">ASP.NET을 사용하지 않고 WCF AJAX 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="aa41e-102">Creating WCF AJAX Services without ASP.NET</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="aa41e-103"> AJAX 서비스는 ASP.NET AJAX가 없어도 모든 JavaScript 사용 웹 페이지에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa41e-103"> AJAX services can be accessed from any JavaScript-enabled Web page, without requiring ASP.NET AJAX.</span></span> <span data-ttu-id="aa41e-104">이 항목에서는 이런 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스를 만드는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="aa41e-104">This topic describes how to create such a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span>  
  
 <span data-ttu-id="aa41e-105">사용 하 여에 대 한 지침은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ASP.NET AJAX와 함께 참조 [ASP.NET AJAX 용 WCF 서비스를 만드는](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="aa41e-105">For instructions on using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] with ASP.NET AJAX, see [Creating WCF Services for ASP.NET AJAX](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md).</span></span>  
  
 <span data-ttu-id="aa41e-106">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] AJAX 서비스 만들기에 대한 세 가지 부분은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="aa41e-106">There are three parts to a creating a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] AJAX service:</span></span>  
  
-   <span data-ttu-id="aa41e-107">브라우저에서 액세스할 수 있는 AJAX 끝점 만들기</span><span class="sxs-lookup"><span data-stu-id="aa41e-107">Creating an AJAX endpoint that can be accessed from the browser.</span></span>  
  
-   <span data-ttu-id="aa41e-108">AJAX 호환 서비스 계약 만들기</span><span class="sxs-lookup"><span data-stu-id="aa41e-108">Creating an AJAX-compatible service contract.</span></span>  
  
-   <span data-ttu-id="aa41e-109">WCF AJAX 서비스 액세스</span><span class="sxs-lookup"><span data-stu-id="aa41e-109">Accessing WCF AJAX services.</span></span>  
  
## <a name="creating-an-ajax-endpoint"></a><span data-ttu-id="aa41e-110">AJAX 끝점 만들기</span><span class="sxs-lookup"><span data-stu-id="aa41e-110">Creating an AJAX Endpoint</span></span>  
 <span data-ttu-id="aa41e-111">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스에서 AJAX 지원을 사용 가능하게 하는 가장 간단한 방법은 다음 예제에서와 같이 서비스와 연결된 .svc 파일에서 <xref:System.ServiceModel.Activation.WebServiceHostFactory>를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="aa41e-111">The most basic way to enable AJAX support in a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service is to use the <xref:System.ServiceModel.Activation.WebServiceHostFactory> in the .svc file associated with the service, as in the following example.</span></span>  
  
```  
<%ServiceHost   
    language=c#  
    Debug="true"  
    Service="Microsoft.Ajax.Samples.CityService"  
    Factory=System.ServiceModel.Activation.WebServiceHostFactory  
%>  
```  
  
 <span data-ttu-id="aa41e-112">또는 구성을 사용하여 AJAX 끝점을 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa41e-112">Alternatively, you can also use configuration to add an AJAX endpoint.</span></span> <span data-ttu-id="aa41e-113">서비스 끝점에서 <xref:System.ServiceModel.WebHttpBinding>을 사용하고 해당 끝점을 다음 코드 조각에 표시된 것처럼 <xref:System.ServiceModel.Description.WebHttpBehavior>로 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="aa41e-113">Use the <xref:System.ServiceModel.WebHttpBinding> on the service endpoint and configure that endpoint with the <xref:System.ServiceModel.Description.WebHttpBehavior> as shown in the following code snippet.</span></span>  
  
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
  
 <span data-ttu-id="aa41e-114">작업 예제를 참조 하십시오.는 [JSON 및 XML을 포함 한 AJAX 서비스](../../../../docs/framework/wcf/samples/ajax-service-with-json-and-xml-sample.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="aa41e-114">For a working example, see the [AJAX Service with JSON and XML](../../../../docs/framework/wcf/samples/ajax-service-with-json-and-xml-sample.md).</span></span>  
  
## <a name="creating-an-ajax-compatible-service-contract"></a><span data-ttu-id="aa41e-115">AJAX 호환 서비스 계약 만들기</span><span class="sxs-lookup"><span data-stu-id="aa41e-115">Creating an AJAX-Compatible Service Contract</span></span>  
 <span data-ttu-id="aa41e-116">기본적으로 AJAX 끝점을 통해 노출된 서비스 계약은 데이터를 XML 형식으로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="aa41e-116">By default, service contracts exposed over an AJAX endpoint return data in the XML format.</span></span> <span data-ttu-id="aa41e-117">또한 기본적으로 서비스 작업은 다음 예제에서처럼 HTTP POST 요청을 통해 끝점 주소 다음에 작업 이름이 오는 URL에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa41e-117">Also, by default service operations are accessible through HTTP POST requests to URLs that include the endpoint address followed by the operation name, as shown in the following example.</span></span>  
  
```  
[OperationContract]  
string[] GetCities(string firstLetters);  
```  
  
 <span data-ttu-id="aa41e-118">이 작업은 HTTP POST를 사용 하 여 액세스할 `http://serviceaddress/endpointaddress/GetCities` XML 메시지를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa41e-118">This operation is accessible using an HTTP POST to `http://serviceaddress/endpointaddress/GetCities` and return an XML message.</span></span>  
  
 <span data-ttu-id="aa41e-119">전체 웹 프로그래밍 모델을 사용하여 이러한 기본 측면을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa41e-119">You can use the full Web Programming Model to customize these basic aspects.</span></span> <span data-ttu-id="aa41e-120">예를 들어 <xref:System.ServiceModel.Web.WebGetAttribute> 또는 <xref:System.ServiceModel.Web.WebInvokeAttribute> 특성을 사용하여 작업이 응답하는 HTTP 동사를 제어하거나 이러한 각 특성의 `UriTemplate` 속성을 사용하여 사용자 지정 URI를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa41e-120">For example, you can use the <xref:System.ServiceModel.Web.WebGetAttribute> or <xref:System.ServiceModel.Web.WebInvokeAttribute> attributes to control the HTTP verb to which the operation responds or use the `UriTemplate` property of these respective attributes to specify custom URIs.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="aa41e-121">[WCF 웹 HTTP 프로그래밍 모델](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md) 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="aa41e-121"> the [WCF Web HTTP Programming Model](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md) topic.</span></span>  
  
 <span data-ttu-id="aa41e-122">JSON 데이터 형식은 AJAX 서비스에서 주로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa41e-122">The JSON data format is often used in AJAX services.</span></span> <span data-ttu-id="aa41e-123">XML 대신 JSON을 반환하는 작업을 만들려면 <xref:System.ServiceModel.Web.WebGetAttribute.ResponseFormat%2A> (또는 <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A>) 속성을 <xref:System.ServiceModel.Web.WebMessageFormat.Json>으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="aa41e-123">To create an operation that returns JSON instead of XML, set the <xref:System.ServiceModel.Web.WebGetAttribute.ResponseFormat%2A> (or the <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A>) property to <xref:System.ServiceModel.Web.WebMessageFormat.Json>.</span></span> <span data-ttu-id="aa41e-124">[독립 실행형 JSON Serialization](../../../../docs/framework/wcf/feature-details/stand-alone-json-serialization.md) 항목에서는 JSON에 어떻게 기본 제공.NET 유형 및 데이터 계약 형식 지도 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="aa41e-124">The [Stand-Alone JSON Serialization](../../../../docs/framework/wcf/feature-details/stand-alone-json-serialization.md) topic shows how built-in .NET types and data contract types map to JSON.</span></span>  
  
 <span data-ttu-id="aa41e-125">일반적으로 JSON 요청 및 응답은 하나의 항목으로만 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa41e-125">Normally, JSON requests and responses consist of just one item.</span></span> <span data-ttu-id="aa41e-126">앞의 `GetCities` 작업의 경우 요청은 다음 문과 유사하고.</span><span class="sxs-lookup"><span data-stu-id="aa41e-126">For the preceding `GetCities` operation, the request resembles the following statement.</span></span>  
  
```  
"na"  
```  
  
 <span data-ttu-id="aa41e-127">해당 요청에 대한 응답은 다음 문과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="aa41e-127">The response to that request resembles the following statement.</span></span>  
  
```  
["Nairobi", "Naples", "Nashville"]  
```  
  
 <span data-ttu-id="aa41e-128">작업에서 추가 매개 변수를 가져올 경우 요청 스타일은 단일 JSON 개체에서 두 매개 변수를 래핑하기 위해 래핑되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa41e-128">If the operation takes an extra parameter, the request style must be wrapped to wrap both parameters in a single JSON object.</span></span> <span data-ttu-id="aa41e-129">이 스타일 JSON 메시지의 예는 다음 예제에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa41e-129">An example of this style JSON message is in the following example.</span></span>  
  
```json  
{"firstLetters": "na", "maxNumber": 2}  
```  
  
 <span data-ttu-id="aa41e-130">다음 계약이 이 메시지를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="aa41e-130">The following contract accepts this message.</span></span>  
  
```  
[WebInvoke(BodyStyle=WebMessageBodyStyle.WrappedRequest, ResponseFormat=WebMessageFormat.Json)]  
[OperationContract]  
string[] GetCities(string firstLetters, int maxNumber);  
```  
  
## <a name="accessing-ajax-services"></a><span data-ttu-id="aa41e-131">AJAX 서비스 액세스</span><span class="sxs-lookup"><span data-stu-id="aa41e-131">Accessing AJAX Services</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="aa41e-132"> AJAX 끝점은 항상 JSON 및 XML 요청 모두를 수락합니다.</span><span class="sxs-lookup"><span data-stu-id="aa41e-132"> AJAX endpoints always accept both JSON and XML requests.</span></span>  
  
 <span data-ttu-id="aa41e-133">"응용 프로그램/json"의 콘텐츠 형식으로 HTTP POST 요청은 JSON으로 되며 XML (예를 들어 "텍스트/xml")을 나타내는 콘텐츠 형식이 있는 XML로 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa41e-133">HTTP POST requests with a content-type of "application/json" are treated as JSON, and those with content-type that indicate XML (for example, "text/xml") are treated as XML.</span></span>  
  
 <span data-ttu-id="aa41e-134">HTTP GET 요청에는 URL 자체의 모든 요청 매개 변수가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa41e-134">HTTP GET requests contain all the request parameters in the URL itself.</span></span>  
  
 <span data-ttu-id="aa41e-135">끝점에 대한 HTTP 요청을 만드는 방법을 결정하는 것은 사용자의 몫입니다.</span><span class="sxs-lookup"><span data-stu-id="aa41e-135">It is up to the user to decide how to create the HTTP request to the endpoint.</span></span> <span data-ttu-id="aa41e-136">또한 사용자는 요청 본문을 형성하는 JSON 생성에 대한 전체 제어 권한을 가집니다.</span><span class="sxs-lookup"><span data-stu-id="aa41e-136">Also, the user has full control over constructing the JSON that forms the body of the request.</span></span> <span data-ttu-id="aa41e-137">JavaScript에서 요청을 만드는 예를 참조 하십시오.는 [JSON 및 XML을 포함 한 AJAX 서비스](../../../../docs/framework/wcf/samples/ajax-service-with-json-and-xml-sample.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="aa41e-137">For an example of creating a request from JavaScript, see the [AJAX Service with JSON and XML](../../../../docs/framework/wcf/samples/ajax-service-with-json-and-xml-sample.md).</span></span>
