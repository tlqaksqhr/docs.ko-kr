---
title: JSON 및 XML 샘플을 포함한 AJAX 서비스
ms.date: 03/30/2017
ms.assetid: 8ea5860d-0c42-4ae9-941a-e07efdd8e29c
ms.openlocfilehash: 32964c287b0064daf529aa4c1e28f0927d29a6d5
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33807347"
---
# <a name="ajax-service-with-json-and-xml-sample"></a><span data-ttu-id="db08b-102">JSON 및 XML 샘플을 포함한 AJAX 서비스</span><span class="sxs-lookup"><span data-stu-id="db08b-102">AJAX Service with JSON and XML Sample</span></span>
<span data-ttu-id="db08b-103">이 샘플에서는 개체 JSON (JavaScript Notation) 또는 XML 데이터를 반환 하는 Asynchronous JavaScript and XML (AJAX) 서비스를 만들려면 Windows Communication Foundation (WCF)를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="db08b-103">This sample demonstrates how to use Windows Communication Foundation (WCF) to create an Asynchronous JavaScript and XML (AJAX) service that returns either JavaScript Object Notation (JSON) or XML data.</span></span> <span data-ttu-id="db08b-104">웹 브라우저 클라이언트에서 JavaScript 코드를 사용하여 AJAX 서비스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db08b-104">You can access an AJAX service by using JavaScript code from a Web browser client.</span></span> <span data-ttu-id="db08b-105">기반으로 하는이 샘플은 [기본 AJAX 서비스](../../../../docs/framework/wcf/samples/basic-ajax-service.md) 샘플.</span><span class="sxs-lookup"><span data-stu-id="db08b-105">This sample builds on the [Basic AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md) sample.</span></span>  
  
 <span data-ttu-id="db08b-106">다른 AJAX 샘플과 달리 이 샘플에서는 ASP.NET AJAX 및 <xref:System.Web.UI.ScriptManager> 컨트롤을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="db08b-106">Unlike the other AJAX samples, this sample does not use ASP.NET AJAX and the <xref:System.Web.UI.ScriptManager> control.</span></span> <span data-ttu-id="db08b-107">몇 가지 추가 구성이 JavaScript 통해 모든 HTML 페이지에서 WCF AJAX 서비스에 액세스할 수 및이 시나리오는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="db08b-107">With some additional configuration, WCF AJAX services can be accessed from any HTML page through JavaScript, and this scenario is shown here.</span></span> <span data-ttu-id="db08b-108">ASP.NET AJAX와 함께 WCF를 사용 하는 예제를 참조 하십시오. [AJAX 샘플과](http://msdn.microsoft.com/library/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e)합니다.</span><span class="sxs-lookup"><span data-stu-id="db08b-108">For an example of using WCF with ASP.NET AJAX, see [AJAX Samples](http://msdn.microsoft.com/library/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e).</span></span>  
  
 <span data-ttu-id="db08b-109">이 샘플에서는 작업의 응답 형식을 JSON과 XML 간에 전환하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="db08b-109">This sample shows how to switch the response type of an operation between JSON and XML.</span></span> <span data-ttu-id="db08b-110">이 기능은 서비스가 ASP.NET AJAX에서 액세스하도록 구성되었는지 아니면 HTML/JavaScript 클라이언트 페이지에서 액세스하도록 구성되었는지 여부에 관계없이 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db08b-110">This functionality is available regardless of whether the service is configured to be accessed by ASP.NET AJAX or by an HTML/JavaScript client page.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="db08b-111">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db08b-111">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="db08b-112">ASP.NET 이외의 AJAX 클라이언트를 사용할 수 있도록 설정하려면 .svc 파일에서 <xref:System.ServiceModel.Activation.WebServiceHostFactory>가 아닌 <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="db08b-112">To enable the use of non-ASP.NET AJAX clients, use <xref:System.ServiceModel.Activation.WebServiceHostFactory> (not <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>) in the .svc file.</span></span> <span data-ttu-id="db08b-113"><xref:System.ServiceModel.Activation.WebServiceHostFactory>는 <xref:System.ServiceModel.Description.WebHttpEndpoint> 표준 끝점을 서비스에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="db08b-113"><xref:System.ServiceModel.Activation.WebServiceHostFactory> adds a <xref:System.ServiceModel.Description.WebHttpEndpoint> standard endpoint to the service.</span></span> <span data-ttu-id="db08b-114">끝점은.svc 파일;을 기준으로 빈 주소에 구성 됩니다. 즉, 서비스 주소가 http://localhost/ServiceModelSamples/service.svc와 작업 이름이 아닌 추가 접미사 없습니다.</span><span class="sxs-lookup"><span data-stu-id="db08b-114">The endpoint is configured at an empty address relative to the .svc file; this means that the address of the service is http://localhost/ServiceModelSamples/service.svc, with no additional suffixes other than the operation name.</span></span>  
  
```svc
<%@ServiceHost language="c#" Debug="true" Service="Microsoft.Samples.XmlAjaxService.CalculatorService" Factory="System.ServiceModel.Activation.WebServiceHostFactory" %>  
```  
  
 <span data-ttu-id="db08b-115">Web.config의 다음 섹션은 끝점에 대한 추가 구성 변경 작업을 수행하는 데 사용할 수 있으며</span><span class="sxs-lookup"><span data-stu-id="db08b-115">The following section in Web.config can be used to make additional configuration changes to the endpoint.</span></span> <span data-ttu-id="db08b-116">추가 변경이 필요하지 않은 경우 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db08b-116">It can be removed if no extra changes are needed.</span></span>  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>  
    <webHttpEndpoint>  
      <!-- Use this element to configure the endpoint -->  
      <standardEndpoint name="" />  
    </webHttpEndpoint>  
  </standardEndpoints>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="db08b-117">기본 데이터 형식은 <xref:System.ServiceModel.Description.WebHttpEndpoint> 는 XML에 대 한 기본 데이터 형식을 동안 <xref:System.ServiceModel.Description.WebScriptEndpoint> 은 JSON입니다.</span><span class="sxs-lookup"><span data-stu-id="db08b-117">The default data format for <xref:System.ServiceModel.Description.WebHttpEndpoint> is XML, while the default data format for <xref:System.ServiceModel.Description.WebScriptEndpoint> is JSON.</span></span> <span data-ttu-id="db08b-118">자세한 내용은 참조 [ASP.NET 하지 않고 WCF AJAX 서비스 만들기](../../../../docs/framework/wcf/feature-details/creating-wcf-ajax-services-without-aspnet.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="db08b-118">For more information, see [Creating WCF AJAX Services without ASP.NET](../../../../docs/framework/wcf/feature-details/creating-wcf-ajax-services-without-aspnet.md).</span></span>  
  
 <span data-ttu-id="db08b-119">다음 샘플에서 서비스는 두 개의 작업는 표준 WCF 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="db08b-119">The service in the following sample is a standard WCF service with two operations.</span></span> <span data-ttu-id="db08b-120">두 작업 모두 <xref:System.ServiceModel.Web.WebMessageBodyStyle.Wrapped> 또는 <xref:System.ServiceModel.Web.WebGetAttribute> 특성에서 <xref:System.ServiceModel.Web.WebInvokeAttribute> 본문 스타일을 필요로 합니다. 이는 `webHttp` 동작과 관련이 있으며 JSON/XML 데이터 형식 전환과는 관계가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="db08b-120">Both operations require the <xref:System.ServiceModel.Web.WebMessageBodyStyle.Wrapped> body style on the <xref:System.ServiceModel.Web.WebGetAttribute> or <xref:System.ServiceModel.Web.WebInvokeAttribute> attributes, which is specific to the `webHttp` behavior and has no bearing on the JSON/XML data format switch.</span></span>  

```csharp
[OperationContract]  
[WebInvoke(ResponseFormat = WebMessageFormat.Xml, BodyStyle = WebMessageBodyStyle.Wrapped)]  
MathResult DoMathXml(double n1, double n2);  
```

 <span data-ttu-id="db08b-121">기본 설정인 XML로 작업에 대 한 응답 형식을 지정에 대 한 설정에서 [ \<webHttp >](../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md) 동작 합니다.</span><span class="sxs-lookup"><span data-stu-id="db08b-121">The response format for the operation is specified as XML, which is the default setting for the [\<webHttp>](../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md) behavior.</span></span> <span data-ttu-id="db08b-122">그러나 응답 형식을 명시적으로 지정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="db08b-122">However, it is good practice explicitly specify the response format.</span></span>  
  
 <span data-ttu-id="db08b-123">다른 작업에서는 `WebInvokeAttribute` 특성을 사용하고 응답에 대해 XML 대신 명시적으로 JSON을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="db08b-123">The other operation uses the `WebInvokeAttribute` attribute and explicitly specifies JSON instead of XML for the response.</span></span>  

```csharp
[OperationContract]  
[WebInvoke(ResponseFormat = WebMessageFormat.Json, BodyStyle = WebMessageBodyStyle.Wrapped)]  
MathResult DoMathJson(double n1, double n2);  
```

 <span data-ttu-id="db08b-124">두 경우 모두 작업 반환 복합 형식을 `MathResult`, 표준 WCF 데이터 계약 형식인 합니다.</span><span class="sxs-lookup"><span data-stu-id="db08b-124">Note that in both cases the operations return a complex type, `MathResult`, which is a standard WCF data contract type.</span></span>  
  
 <span data-ttu-id="db08b-125">클라이언트 웹 페이지 XmlAjaxClientPage.htm에는 사용자가 클릭할 때 위의 두 작업 중 하나를 호출 하는 JavaScript 코드가 포함 되어는 **(return JSON) 계산을 수행할** 또는 **계산 (return XML)**  페이지 단추를 합니다.</span><span class="sxs-lookup"><span data-stu-id="db08b-125">The client Web page XmlAjaxClientPage.htm contains JavaScript code that invokes one of the preceding two operations when the user clicks the **Perform calculation (return JSON)** or **Perform calculation (return XML)** buttons on the page.</span></span> <span data-ttu-id="db08b-126">서비스를 호출하는 코드는 JSON 본문을 만든 다음 HTTP POST를 사용하여 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="db08b-126">The code to invoke the service constructs a JSON body and sends it using HTTP POST.</span></span> <span data-ttu-id="db08b-127">요청을 만들 수동으로 JavaScript에서와 달리는 [기본 AJAX 서비스](../../../../docs/framework/wcf/samples/basic-ajax-service.md) 샘플 및 ASP.NET AJAX를 사용 하 여 다른 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="db08b-127">The request is created manually in JavaScript, unlike the [Basic AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md) sample and the other samples using ASP.NET AJAX.</span></span>  

```csharp
// Create HTTP request  
var xmlHttp;  
// Request instantiation code omitted…  
// Result handler code omitted…  
  
// Build the operation URL  
var url = "service.svc/ajaxEndpoint/";  
url = url + operation;  
  
// Build the body of the JSON message  
var body = '{"n1":';  
body = body + document.getElementById("num1").value + ',"n2":';  
body = body + document.getElementById("num2").value + '}';  
  
// Send the HTTP request  
xmlHttp.open("POST", url, true);  
xmlHttp.setRequestHeader("Content-type", "application/json");  
xmlHttp.send(body);  
```

 <span data-ttu-id="db08b-128">서비스가 응답하면 페이지의 텍스트 상자에서 더 이상의 처리 작업 없이 응답이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="db08b-128">When the service responds, the response is displayed without any further processing in a textbox on the page.</span></span> <span data-ttu-id="db08b-129">이는 사용된 XML 및 JSON 데이터 형식을 직접 확인할 수 있도록 데모용으로 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="db08b-129">This is implemented for demonstration purposes to allow you to directly observe the XML and JSON data formats used.</span></span>  

```javascript
// Create result handler   
xmlHttp.onreadystatechange=function(){  
     if(xmlHttp.readyState == 4){  
          document.getElementById("result").value = xmlHttp.responseText;  
     }  
}  
```

> [!IMPORTANT]
>  <span data-ttu-id="db08b-130">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db08b-130">The samples may already be installed on your machine.</span></span> <span data-ttu-id="db08b-131">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="db08b-131">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="db08b-132">이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="db08b-132">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="db08b-133">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db08b-133">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\AJAX\XmlAjaxService`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="db08b-134">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="db08b-134">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="db08b-135">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="db08b-135">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="db08b-136">에 설명 된 대로 XmlAjaxService.sln 솔루션을 구축 [Windows Communication Foundation 샘플 빌드](../../../../docs/framework/wcf/samples/building-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="db08b-136">Build the solution XmlAjaxService.sln as described in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="db08b-137">로 이동 http://localhost/ServiceModelSamples/XmlAjaxClientPage.htm (열지 마십시오 XmlAjaxClientPage.htm 브라우저의 프로젝트 디렉터리에서).</span><span class="sxs-lookup"><span data-stu-id="db08b-137">Navigate to http://localhost/ServiceModelSamples/XmlAjaxClientPage.htm (do not open XmlAjaxClientPage.htm in the browser from the project directory).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db08b-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="db08b-138">See Also</span></span>  
 [<span data-ttu-id="db08b-139">HTTP POST를 사용하는 AJAX 서비스</span><span class="sxs-lookup"><span data-stu-id="db08b-139">AJAX Service Using HTTP POST</span></span>](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md)
