---
title: "WCF 웹 HTTP 형식 지정"
ms.date: 03/30/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
ms.assetid: e2414896-5463-41cd-b0a6-026a713eac2c
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 43732c6c2effd38b8bfdb49c1a5fbf8275eb15e3
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="wcf-web-http-formatting"></a><span data-ttu-id="e6448-102">WCF 웹 HTTP 형식 지정</span><span class="sxs-lookup"><span data-stu-id="e6448-102">WCF Web HTTP formatting</span></span>
<span data-ttu-id="e6448-103">WCF 웹 HTTP 프로그래밍 모델을 사용하면 서비스 작업의 응답을 반환하는 데 사용할 수 있는 가장 적절한 형식을 동적으로 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6448-103">The WCF Web HTTP programming model allows you to dynamically determine the best format for a service operation to return its response in.</span></span> <span data-ttu-id="e6448-104">적절한 형식을 결정하는 데 지원되는 방법은 자동 형식 지정과 명시적 형식 지정, 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6448-104">Two methods for determining an appropriate format are supported: automatic and explicit.</span></span>  
  
## <a name="automatic-formatting"></a><span data-ttu-id="e6448-105">자동 서식 지정</span><span class="sxs-lookup"><span data-stu-id="e6448-105">Automatic formatting</span></span>  
 <span data-ttu-id="e6448-106">자동 형식 지정을 사용하도록 설정하면 자동 형식 지정이 응답을 반환하는 가장 적절한 형식을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e6448-106">When enabled, automatic formatting chooses the best format in which to return the response.</span></span> <span data-ttu-id="e6448-107">자동 형식 지정은 다음을 순서대로 확인하여 가장 적절한 형식을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="e6448-107">It determines the best format by checking the following, in order:</span></span>  
  
1.  <span data-ttu-id="e6448-108">요청 메시지의 Accept 헤더에 있는 미디어 유형</span><span class="sxs-lookup"><span data-stu-id="e6448-108">The media types in the request message’s Accept header.</span></span>  
  
2.  <span data-ttu-id="e6448-109">요청 메시지의 콘텐츠 형식</span><span class="sxs-lookup"><span data-stu-id="e6448-109">The content-type of the request message.</span></span>  
  
3.  <span data-ttu-id="e6448-110">작업의 기본 형식 설정</span><span class="sxs-lookup"><span data-stu-id="e6448-110">The default format setting in the operation.</span></span>  
  
4.  <span data-ttu-id="e6448-111">WebHttpBehavior의 기본 형식 설정</span><span class="sxs-lookup"><span data-stu-id="e6448-111">The default format setting in the WebHttpBehavior.</span></span>  
  
 <span data-ttu-id="e6448-112">요청 메시지에 Accept 헤더가 포함되어 있으면 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 인프라는 Accept 헤더가 지원하는 형식을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="e6448-112">If the request message contains an Accept header the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] infrastructure searches for a type that it supports.</span></span> <span data-ttu-id="e6448-113">`Accept` 헤더가 해당 미디어 유형의 우선 순위를 지정하는 경우 이러한 우선 순위는 무시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e6448-113">If the `Accept` header specifies priorities for its media types, they are honored.</span></span> <span data-ttu-id="e6448-114">`Accept` 헤더에서 적절한 형식을 찾지 못할 경우 요청 메시지의 콘텐츠 형식이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6448-114">If no suitable format is found in the `Accept` header, the content-type of the request message is used.</span></span> <span data-ttu-id="e6448-115">적절한 콘텐츠 형식이 지정되지 않은 경우 작업의 기본 형식 설정이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6448-115">If no suitable content-type is specified, the default format setting for the operation is used.</span></span> <span data-ttu-id="e6448-116">기본 형식은 `ResponseFormat` 및 <xref:System.ServiceModel.Web.WebGetAttribute> 특성의 <xref:System.ServiceModel.Web.WebInvokeAttribute> 매개 변수를 사용하여 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6448-116">The default format is set with the `ResponseFormat` parameter of the <xref:System.ServiceModel.Web.WebGetAttribute> and <xref:System.ServiceModel.Web.WebInvokeAttribute> attributes.</span></span> <span data-ttu-id="e6448-117">작업의 기본 형식이 지정되지 않은 경우 <xref:System.ServiceModel.Description.WebHttpBehavior.DefaultOutgoingResponseFormat%2A> 속성의 값이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6448-117">If no default format is specified on the operation, the value of the <xref:System.ServiceModel.Description.WebHttpBehavior.DefaultOutgoingResponseFormat%2A> property is used.</span></span> <span data-ttu-id="e6448-118">자동 형식은 <xref:System.ServiceModel.Description.WebHttpBehavior.AutomaticFormatSelectionEnabled%2A> 속성에 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6448-118">Automatic formatting relies on the <xref:System.ServiceModel.Description.WebHttpBehavior.AutomaticFormatSelectionEnabled%2A> property.</span></span> <span data-ttu-id="e6448-119">이 속성이 `true`로 설정되면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 인프라가 사용할 가장 적절한 형식을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="e6448-119">When this property is set to `true`, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] infrastructure determines the best format to use.</span></span> <span data-ttu-id="e6448-120">기본적으로 자동 형식 선택은 이전 버전과의 호환성을 위해 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e6448-120">Automatic format selection is disabled by default for backwards compatibility.</span></span> <span data-ttu-id="e6448-121">자동 형식 선택은 프로그래밍 방식이나 구성을 통해 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6448-121">Automatic format selection can be enabled programmatically or through configuration.</span></span> <span data-ttu-id="e6448-122">다음 예제에서는 코드에서 자동 형식 선택을 사용하도록 설정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e6448-122">The following example shows how to enable automatic format selection in code.</span></span>  
  
```csharp
// This code assumes the service name is MyService and the service contract is IMyContract     
Uri baseAddress = new Uri("http://localhost:8000");  
  
WebServiceHost host = new WebServiceHost(typeof(MyService), baseAddress)  
try  
{  
   ServiceEndpoint sep = host.AddServiceEndpoint(typeof(IMyContract), new WebHttpBinding(), "");  
   // Check it see if the WebHttpBehavior already exists  
   WebHttpBehavior whb = sep.Behaviors.Find<WebHttpBehavior>();  
  
   if (whb != null)  
   {  
      whb.AutomaticFormatSelectionEnabled = true;  
   }  
   else  
   {  
      WebHttpBehavior webBehavior = new WebHttpBehavior();  
      webBehavior.AutomaticFormatSelectionEnabled = true;  
      sep.Behaviors.Add(webBehavior);  
   }  
         // Open host to start listening for messages  
   host.Open();        
  
  // ...  
}  
  catch(CommunicationException ex)  
  {  
     Console.WriteLine("An exception occurred: " + ex.Message());  
  }  
```  
  
 <span data-ttu-id="e6448-123">구성을 통해 자동 형식 지정을 사용하도록 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6448-123">Automatic formatting can also be enabled through configuration.</span></span> <span data-ttu-id="e6448-124"><xref:System.ServiceModel.Description.WebHttpBehavior.AutomaticFormatSelectionEnabled%2A> 속성을 <xref:System.ServiceModel.Description.WebHttpBehavior>에 직접 설정하거나 <xref:System.ServiceModel.Description.WebHttpEndpoint>를 사용하여 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6448-124">You can set the <xref:System.ServiceModel.Description.WebHttpBehavior.AutomaticFormatSelectionEnabled%2A> property directly on the <xref:System.ServiceModel.Description.WebHttpBehavior> or using the <xref:System.ServiceModel.Description.WebHttpEndpoint>.</span></span> <span data-ttu-id="e6448-125">다음 예제에서는 <xref:System.ServiceModel.Description.WebHttpBehavior>에서 자동 형식 선택을 사용하도록 설정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e6448-125">The following example shows how to enable the automatic format selection on the <xref:System.ServiceModel.Description.WebHttpBehavior>.</span></span>  
  
```xml  
<system.serviceModel>  
  <behaviors>  
    <endpointBehaviors>  
      <behavior>  
        <webHttp automaticFormatSelectionEnabled="true" />  
      </behavior>  
    </endpointBehaviors>  
  </behaviors>  
  <standardEndpoints>  
    <webHttpEndpoint>  
      <!-- the "" standard endpoint is used by WebServiceHost for auto creating a web endpoint. -->  
      <standardEndpoint name="" helpEnabled="true" />  
    </webHttpEndpoint>  
  </standardEndpoints>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="e6448-126">다음 예제에서는 <xref:System.ServiceModel.Description.WebHttpEndpoint>를 사용하여 자동 형식 선택을 사용하도록 설정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e6448-126">The following example shows how to enable automatic format selection using <xref:System.ServiceModel.Description.WebHttpEndpoint>.</span></span>  
  
```xml  
<system.serviceModel>  
    <standardEndpoints>  
      <webHttpEndpoint>  
        <!-- the "" standard endpoint is used by WebServiceHost for auto creating a web endpoint. -->  
        <standardEndpoint name="" helpEnabled="true" automaticFormatSelectionEnabled="true"  />  
      </webHttpEndpoint>  
    </standardEndpoints>  
  </system.serviceModel>  
```  
  
## <a name="explicit-formatting"></a><span data-ttu-id="e6448-127">명시적 형식 지정</span><span class="sxs-lookup"><span data-stu-id="e6448-127">Explicit formatting</span></span>  
 <span data-ttu-id="e6448-128">이름에서 알 수 있듯이 명시적 형식 지정에서는 개발자가 작업 코드 내에서 사용할 가장 적절한 형식을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="e6448-128">As the name implies, in explicit formatting the developer determines the best format to use within the operation code.</span></span> <span data-ttu-id="e6448-129">가장 적절한 형식이 XML 또는 JSON이면 개발자는 <xref:System.ServiceModel.Web.OutgoingWebResponseContext.Format%2A> 을 <xref:System.ServiceModel.Web.WebMessageFormat.Xml> 또는 <xref:System.ServiceModel.Web.WebMessageFormat.Json>으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e6448-129">If the best format is XML or JSON the developer sets <xref:System.ServiceModel.Web.OutgoingWebResponseContext.Format%2A> to either <xref:System.ServiceModel.Web.WebMessageFormat.Xml> or <xref:System.ServiceModel.Web.WebMessageFormat.Json>.</span></span> <span data-ttu-id="e6448-130"><xref:System.ServiceModel.Web.OutgoingWebResponseContext.Format%2A> 속성이 명시적으로 설정되지 않으면 작업의 기본 형식이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6448-130">If the <xref:System.ServiceModel.Web.OutgoingWebResponseContext.Format%2A> property is not explicitly set, then the operation’s default format is used.</span></span>  
  
 <span data-ttu-id="e6448-131">다음 예제에서는 사용할 형식에 대한 형식 쿼리 문자열 매개 변수를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e6448-131">The following example checks the format query string parameter for a format to use.</span></span> <span data-ttu-id="e6448-132">이 매개 변수가 지정되어 있으면 <xref:System.ServiceModel.Web.OutgoingWebResponseContext.Format%2A>을 사용하여 작업의 형식이 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6448-132">If it has been specified, it sets the operation’s format using <xref:System.ServiceModel.Web.OutgoingWebResponseContext.Format%2A>.</span></span>  
  
```csharp
public class Service : IService  
{  
    [WebGet]  
     public string EchoWithGet(string s)  
    {  
         // if a format query string parameter has been specified, set the response format to that. If no such  
         // query string parameter exists the Accept header will be used  
        string formatQueryStringValue = WebOperationContext.Current.IncomingRequest.UriTemplateMatch.QueryParameters["format"];  
        if (!string.IsNullOrEmpty(formatQueryStringValue))  
        {  
             if (formatQueryStringValue.Equals("xml", System.StringComparison.OrdinalIgnoreCase))  
             {  
                  WebOperationContext.Current.OutgoingResponse.Format = WebMessageFormat.Xml;  
             }  
             else if (formatQueryStringValue.Equals("json", System.StringComparison.OrdinalIgnoreCase))  
            {  
                WebOperationContext.Current.OutgoingResponse.Format = WebMessageFormat.Json;  
            }  
            else  
            {  
                 throw new WebFaultException<string>(string.Format("Unsupported format '{0}'", formatQueryStringValue), HttpStatusCode.BadRequest);  
            }  
        }  
        return "You said " + s;  
    }  
```  
  
 <span data-ttu-id="e6448-133">XML 또는 JSON 이외의 다른 형식을 지원해야 하는 경우 반환 형식이 <xref:System.ServiceModel.Channels.Message>인 작업을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="e6448-133">If you need to support formats other than XML or JSON, define your operation to have a return type of <xref:System.ServiceModel.Channels.Message>.</span></span> <span data-ttu-id="e6448-134">작업 코드 내에서 사용할 적절한 형식을 결정하고 다음 메서드 중 하나를 사용하여 <xref:System.ServiceModel.Channels.Message> 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e6448-134">Within the operation code, determine the appropriate format to use and then create a <xref:System.ServiceModel.Channels.Message> object using one of the following methods:</span></span>  
  
-   `WebOperationContext.CreateAtom10Response`  
  
-   `WebOperationContext.CreateJsonResponse`  
  
-   `WebOperationContext.CreateStreamResponse`  
  
-   `WebOperationContext.CreateTextResponse`  
  
-   `WebOperationContext.CreateXmlResponse`  
  
 <span data-ttu-id="e6448-135">이러한 각 메서드는 콘텐츠를 사용하여 적절한 형식의 메시지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e6448-135">Each of these methods takes content and creates a message with the appropriate format.</span></span> <span data-ttu-id="e6448-136">`WebOperationContext.Current.IncomingRequest.GetAcceptHeaderElements` 메서드를 사용하면 선호도가 높은 것부터 낮은 것 순으로 클라이언트가 선호하는 형식의 목록을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6448-136">The `WebOperationContext.Current.IncomingRequest.GetAcceptHeaderElements` method can be used to get a list of formats preferred by the client in order of decreasing preference.</span></span> <span data-ttu-id="e6448-137">다음 예제에서는 `WebOperationContext.Current.IncomingRequest.GetAcceptHeaderElements`를 사용하여 사용할 형식을 결정한 다음 적절한 응답 만들기 메서드를 사용하여 응답 메시지를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e6448-137">The following example shows how to use `WebOperationContext.Current.IncomingRequest.GetAcceptHeaderElements` to determine the format to use and then uses the appropriate create response method to create the response message.</span></span>  
  
```csharp
public class Service : IService  
{  
    public Message EchoListWithGet(string list)  
    {  
        List<string> returnList = new List<string>(list.Split(new char[] { ',' }, StringSplitOptions.RemoveEmptyEntries));  
        IList<ContentType> acceptHeaderElements = WebOperationContext.Current.IncomingRequest.GetAcceptHeaderElements();  
        for (int x = 0; x < acceptHeaderElements.Count; x++)  
        {  
            string normalizedMediaType = acceptHeaderElements[x].MediaType.ToLowerInvariant();  
            switch (normalizedMediaType)  
            {  
                case "image/jpeg": return CreateJpegResponse(returnList);  
                case "application/xhtml+xml": return CreateXhtmlResponse(returnList);  
                case "application/atom+xml": return CreateAtom10Response(returnList);  
                case "application/xml": return CreateXmlResponse(returnList);  
                case "application/json": return CreateJsonResponse(returnList);  
          }  
    }  
  
    // Default response format is XML  
    return CreateXmlResponse(returnList);  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="e6448-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e6448-138">See also</span></span>  
 <xref:System.UriTemplate>  
 <xref:System.UriTemplateMatch>  
 [<span data-ttu-id="e6448-139">WCF 웹 HTTP 프로그래밍 모델</span><span class="sxs-lookup"><span data-stu-id="e6448-139">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)  
 [<span data-ttu-id="e6448-140">UriTemplate 및 UriTemplateTable</span><span class="sxs-lookup"><span data-stu-id="e6448-140">UriTemplate and UriTemplateTable</span></span>](../../../../docs/framework/wcf/feature-details/uritemplate-and-uritemplatetable.md)  
 [<span data-ttu-id="e6448-141">WCF 웹 HTTP 프로그래밍 모델 개요</span><span class="sxs-lookup"><span data-stu-id="e6448-141">WCF Web HTTP Programming Model Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model-overview.md)  
 [<span data-ttu-id="e6448-142">WCF 웹 HTTP 프로그래밍 개체 모델</span><span class="sxs-lookup"><span data-stu-id="e6448-142">WCF Web HTTP Programming Object Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-object-model.md)
