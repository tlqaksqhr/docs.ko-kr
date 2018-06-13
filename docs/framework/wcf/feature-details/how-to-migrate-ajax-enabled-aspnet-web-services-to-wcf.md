---
title: '방법: AJAX 사용 ASP.NET 웹 서비스를 WCF로 마이그레이션'
ms.date: 03/30/2017
ms.assetid: 1428df4d-b18f-4e6d-bd4d-79ab3dd5147c
ms.openlocfilehash: 048408adf8678c243a225a233cb1173c9b7f869f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33495553"
---
# <a name="how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf"></a><span data-ttu-id="e5bf0-102">방법: AJAX 사용 ASP.NET 웹 서비스를 WCF로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="e5bf0-102">How to: Migrate AJAX-Enabled ASP.NET Web Services to WCF</span></span>
<span data-ttu-id="e5bf0-103">이 항목에서는 기본 ASP.NET AJAX 서비스는 해당 하는 AJAX 사용 WCF Windows Communication Foundation () 서비스를 마이그레이션하는 절차를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5bf0-103">This topic outlines procedures to migrate a basic ASP.NET AJAX service to an equivalent AJAX-enabled Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="e5bf0-104">ASP.NET AJAX 서비스의 기능적으로 동일한 WCF 버전을 작성 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e5bf0-104">It shows how to create a functionally equivalent WCF version of an ASP.NET AJAX service.</span></span> <span data-ttu-id="e5bf0-105">두 서비스는 함께 사용할 수 있습니다 또는 WCF 서비스는 ASP.NET AJAX 서비스를 바꾸는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5bf0-105">The two services can then be used side by side, or the WCF service can be used to replace the ASP.NET AJAX service.</span></span>  
  
 <span data-ttu-id="e5bf0-106">기존 ASP.NET AJAX 마이그레이션 WCF AJAX 서비스에 서비스 제공 다음과 같은 이점을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5bf0-106">Migrating an existing ASP.NET AJAX service to a WCF AJAX service gives you the following benefits:</span></span>  
  
-   <span data-ttu-id="e5bf0-107">최소의 추가 구성만으로 AJAX 서비스를 SOAP 서비스로 노출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5bf0-107">You can expose your AJAX service as a SOAP service with minimal extra configuration.</span></span>  
  
-   <span data-ttu-id="e5bf0-108">추적을 같은 WCF 기능에서 이점을 얻을 수 있으며 등 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5bf0-108">You can benefit from WCF features such as tracing, and so on.</span></span>  
  
 <span data-ttu-id="e5bf0-109">다음 절차에서는 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]을 사용하고 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="e5bf0-109">The following procedures assume that you are using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span></span>  
  
 <span data-ttu-id="e5bf0-110">이 항목에서 간략히 설명된 절차에서 얻어진 코드는 다음 예제에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5bf0-110">The code that results from the procedures outlined in this topic is provided in the example following the procedures.</span></span>  
  
 <span data-ttu-id="e5bf0-111">AJAX 사용 끝점을 통해 WCF 서비스를 노출 하는 방법에 대 한 자세한 내용은 참조는 [하는 방법: ASP.NET AJAX 끝점 추가를 사용 하 여 구성](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md) 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="e5bf0-111">For more information about exposing a WCF service through an AJAX-enabled endpoint, see the [How to: Use Configuration to Add an ASP.NET AJAX Endpoint](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md) topic.</span></span>  
  
### <a name="to-create-and-test-the-aspnet-web-service-application"></a><span data-ttu-id="e5bf0-112">ASP.NET 웹 서비스 응용 프로그램을 만들고 테스트하려면</span><span class="sxs-lookup"><span data-stu-id="e5bf0-112">To create and test the ASP.NET Web service application</span></span>  
  
1.  <span data-ttu-id="e5bf0-113">[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e5bf0-113">Open [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span></span>  
  
2.  <span data-ttu-id="e5bf0-114">**파일** 메뉴 선택 **새로**, 다음 **프로젝트**, 다음 **웹**를 선택한 후 **ASP.NET 웹 서비스 응용 프로그램** .</span><span class="sxs-lookup"><span data-stu-id="e5bf0-114">From the **File** menu, select **New**, then **Project**, then **Web**, and then select **ASP.NET Web Service Application**.</span></span>  
  
3.  <span data-ttu-id="e5bf0-115">프로젝트 이름을 `ASPHello` 클릭 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="e5bf0-115">Name the project `ASPHello` and click **OK**.</span></span>  
  
4.  <span data-ttu-id="e5bf0-116">이 서비스에서 AJAX를 사용하려면 Service1.asmx.cs 파일에서 `System.Web.Script.Services.ScriptService]`가 포함된 행의 주석 처리를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="e5bf0-116">Uncomment the line in the Service1.asmx.cs file that contains `System.Web.Script.Services.ScriptService]` to enable AJAX for this service.</span></span>  
  
5.  <span data-ttu-id="e5bf0-117">**빌드** 메뉴 선택 **솔루션 빌드**합니다.</span><span class="sxs-lookup"><span data-stu-id="e5bf0-117">From the **Build** menu, select **Build Solution**.</span></span>  
  
6.  <span data-ttu-id="e5bf0-118">**디버그** 메뉴 선택 **디버깅 하지 않고 시작**합니다.</span><span class="sxs-lookup"><span data-stu-id="e5bf0-118">From the **Debug** menu, select **Start Without Debugging**.</span></span>  
  
7.  <span data-ttu-id="e5bf0-119">생성된 웹 페이지에서 `HelloWorld` 작업을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e5bf0-119">On the Web page generated, select the `HelloWorld` operation.</span></span>  
  
8.  <span data-ttu-id="e5bf0-120">클릭는 **Invoke** 단추는 `HelloWorld` 테스트 페이지.</span><span class="sxs-lookup"><span data-stu-id="e5bf0-120">Click the **Invoke** button on the `HelloWorld` test page.</span></span> <span data-ttu-id="e5bf0-121">다음과 같은 XML 응답을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5bf0-121">You should receive the following XML response.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <string xmlns="http://tempuri.org/">Hello World</string>  
    ```  
  
9. <span data-ttu-id="e5bf0-122">이 응답을 통해 현재 ASP.NET AJAX 서비스가 작동 중임을 확인할 수 있으며, 특히 해당 서비스가 Service1.asmx/HelloWorld에서 HTTP POST 요청에 응답하는 끝점을 노출하고 XML을 반환함을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5bf0-122">This response confirms that you now have a functioning ASP.NET AJAX service and, in particular, that the service has now exposed an endpoint at Service1.asmx/HelloWorld that responds to HTTP POST requests and returns XML.</span></span>  
  
     <span data-ttu-id="e5bf0-123">이제 WCF AJAX 서비스를 사용 하도록이 서비스를 변환 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e5bf0-123">Now you are ready to convert this service to use a WCF AJAX service.</span></span>  
  
### <a name="to-create-an-equivalent-wcf-ajax-service-application"></a><span data-ttu-id="e5bf0-124">동등한 WCF AJAX 서비스 응용 프로그램을 만들려면</span><span class="sxs-lookup"><span data-stu-id="e5bf0-124">To create an equivalent WCF AJAX service application</span></span>  
  
1.  <span data-ttu-id="e5bf0-125">마우스 오른쪽 단추로 클릭는 **ASPHello** 프로젝트를 마우스 선택 **추가**, 다음 **새 항목**, 차례로 **AJAX 사용 WCF 서비스**합니다.</span><span class="sxs-lookup"><span data-stu-id="e5bf0-125">Right-click the **ASPHello** project and select **Add**, then **New Item**, and then **AJAX-enabled WCF Service**.</span></span>  
  
2.  <span data-ttu-id="e5bf0-126">서비스 이름을 `WCFHello` 클릭 **추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="e5bf0-126">Name the service `WCFHello` and click **Add**.</span></span>  
  
3.  <span data-ttu-id="e5bf0-127">WCFHello.svc.cs 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e5bf0-127">Open the WCFHello.svc.cs file.</span></span>  
  
4.  <span data-ttu-id="e5bf0-128">Service1.asmx.cs에서 다음 구현과 복사는 `HelloWorld` 작업 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5bf0-128">From Service1.asmx.cs, copy the following implementation of the `HelloWorld` operation.</span></span>  
  
    ```  
    public string HelloWorld()  
    {  
         return "Hello World";  
    }  
    ```  
  
5.  <span data-ttu-id="e5bf0-129">붙여넣기 구현을 `HelloWorld` WCFHello.svc.cs 파일에 다음 코드 대신에 작업을 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5bf0-129">Paste to copied implementation of the `HelloWorld` operation into the WCFHello.svc.cs file in place of the following code.</span></span>  
  
    ```  
    public void DoWork()  
    {  
          // Add your operation implementation here  
          return;  
    }  
    ```  
  
6.  <span data-ttu-id="e5bf0-130">지정 된 `Namespace` 특성 <xref:System.ServiceModel.ServiceContractAttribute> 으로 `WCFHello`합니다.</span><span class="sxs-lookup"><span data-stu-id="e5bf0-130">Specify the `Namespace` attribute for <xref:System.ServiceModel.ServiceContractAttribute> as `WCFHello`.</span></span>  
  
    ```  
    [ServiceContract(Namespace="WCFHello")]  
    [AspNetCompatibilityRequirements(RequirementsMode=AspNetCompatibilityRequirementsMode.Required)]  
    public class WCFHello  
    { … }  
    ```  
  
7.  <span data-ttu-id="e5bf0-131">추가 <xref:System.ServiceModel.Web.WebInvokeAttribute> 에 `HelloWorld` 작업 집합과 <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A> 반환할 속성 <xref:System.ServiceModel.Web.WebMessageFormat.Xml>합니다.</span><span class="sxs-lookup"><span data-stu-id="e5bf0-131">Add the <xref:System.ServiceModel.Web.WebInvokeAttribute> to the `HelloWorld` operation and set the <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A> property to return <xref:System.ServiceModel.Web.WebMessageFormat.Xml>.</span></span> <span data-ttu-id="e5bf0-132">이 속성을 설정하지 않은 경우 기본 반환 형식은 <xref:System.ServiceModel.Web.WebMessageFormat.Json>입니다.</span><span class="sxs-lookup"><span data-stu-id="e5bf0-132">Note that, if not set, the default return type is <xref:System.ServiceModel.Web.WebMessageFormat.Json>.</span></span>  
  
    ```  
    [OperationContract]  
    [WebInvoke(ResponseFormat=WebMessageFormat.Xml)]  
    public string HelloWorld()  
    {  
        return "Hello World";  
    }  
    ```  
  
8.  <span data-ttu-id="e5bf0-133">**빌드** 메뉴 선택 **솔루션 빌드**합니다.</span><span class="sxs-lookup"><span data-stu-id="e5bf0-133">From the **Build** menu, select **Build Solution**.</span></span>  
  
9. <span data-ttu-id="e5bf0-134">WCFHello.svc 파일을 열고 들어오고는 **디버그** 메뉴 선택 **디버깅 하지 않고 시작**합니다.</span><span class="sxs-lookup"><span data-stu-id="e5bf0-134">Open the WCFHello.svc file and from the **Debug** menu, select **Start Without Debugging**.</span></span>  
  
10. <span data-ttu-id="e5bf0-135">서비스는 끝점을 노출 이제 `WCFHello.svc/HelloWorld`, HTTP POST 요청에 응답 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5bf0-135">The service now exposes an endpoint at `WCFHello.svc/HelloWorld`, which responds to HTTP POST requests.</span></span> <span data-ttu-id="e5bf0-136">HTTP POST 요청은 브라우저에서 테스트할 수 없지만 끝점은 다음과 같은 XML을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e5bf0-136">HTTP POST requests cannot be tested from the browser, but the endpoint returns XML following XML.</span></span>  
  
    ```xml  
    <string xmlns="http://schemas.microsoft.com/2003/10/Serialization/">Hello World</string>  
    ```  
  
11. <span data-ttu-id="e5bf0-137">`WCFHello.svc/HelloWorld` 및 `Service1.aspx/HelloWorld` 끝점은 현재 기능적으로 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5bf0-137">The `WCFHello.svc/HelloWorld` and the `Service1.aspx/HelloWorld` endpoints are now functionally equivalent.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e5bf0-138">예제</span><span class="sxs-lookup"><span data-stu-id="e5bf0-138">Example</span></span>  
 <span data-ttu-id="e5bf0-139">이 항목에서 간략히 설명된 절차에서 얻어진 코드는 다음 예제에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5bf0-139">The code that results from the procedures outlined in this topic is provided in the following example.</span></span>  
  
```  
//This is the ASP.NET code in the Service1.asmx.cs file.  
  
using System;  
using System.Collections;  
using System.ComponentModel;  
using System.Data;  
using System.Linq;  
using System.Web;  
using System.Web.Services;  
using System.Web.Services.Protocols;  
using System.Xml.Linq;  
using System.Web.Script.Services;  
  
namespace ASPHello  
{  
    /// <summary>  
    /// Summary description for Service1.  
    /// </summary>  
    [WebService(Namespace = "http://tempuri.org/")]  
    [WebServiceBinding(ConformsTo = WsiProfiles.BasicProfile1_1)]  
    [ToolboxItem(false)]  
    // To allow this Web Service to be called from script, using ASP.NET AJAX, uncomment the following line.   
    [System.Web.Script.Services.ScriptService]  
    public class Service1 : System.Web.Services.WebService  
    {  
  
        [WebMethod]  
        public string HelloWorld()  
        {  
            return "Hello World";  
        }  
    }  
}   
  
//This is the WCF code in the WCFHello.svc.cs file.  
using System;  
using System.Linq;  
using System.Runtime.Serialization;  
using System.ServiceModel;  
using System.ServiceModel.Activation;  
using System.ServiceModel.Web;  
  
namespace ASPHello  
{  
    [ServiceContract(Namespace = "WCFHello")]  
    [AspNetCompatibilityRequirements(RequirementsMode = AspNetCompatibilityRequirementsMode.Allowed)]  
    public class WCFHello  
    {  
        // Add [WebInvoke] attribute to use HTTP GET.  
        [OperationContract]  
        [WebInvoke(ResponseFormat=WebMessageFormat.Xml)]  
        public string HelloWorld()  
        {  
            return "Hello World";  
        }  
  
        // Add more operations here and mark them with [OperationContract].  
    }  
}  
```  
  
 <span data-ttu-id="e5bf0-140"><xref:System.Xml.XmlDocument> 형식은 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>를 통해 serialize할 수 없으므로 <xref:System.Xml.Serialization.XmlSerializer>에서 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e5bf0-140">The <xref:System.Xml.XmlDocument> type is not supported by the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> because it is not serializable by the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="e5bf0-141">대신 <xref:System.Xml.Linq.XDocument> 형식을 사용하거나 <xref:System.Xml.XmlDocument.DocumentElement%2A>를 serialize할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5bf0-141">You can use either an <xref:System.Xml.Linq.XDocument> type, or serialize the <xref:System.Xml.XmlDocument.DocumentElement%2A> instead.</span></span>  
  
 <span data-ttu-id="e5bf0-142">ASMX 웹 서비스 업그레이드 하는-함께 WCF 서비스를 마이그레이션할 경우 클라이언트에서 같은 이름의 두 형식 매핑 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="e5bf0-142">If ASMX Web services are being upgraded and migrated side-by-side to WCF services, avoid mapping two types to the same name on the client.</span></span> <span data-ttu-id="e5bf0-143">이 경우 같은 형식을 <xref:System.Web.Services.WebMethodAttribute> 및 <xref:System.ServiceModel.ServiceContractAttribute>에서 사용하면 serializer에 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="e5bf0-143">This causes an exception in serializers if the same type is used in a <xref:System.Web.Services.WebMethodAttribute> and a <xref:System.ServiceModel.ServiceContractAttribute>:</span></span>  
  
-   <span data-ttu-id="e5bf0-144">WCF 서비스가 먼저 추가 되 면에서 예외가 발생 ASMX 웹 서비스에 대 한 메서드 호출 <xref:System.Web.UI.ObjectConverter.ConvertValue%28System.Object%2CSystem.Type%2CSystem.String%29> WCF 스타일 정의 순서가 프록시 우선 하기 때문에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5bf0-144">If WCF service is added first, invoking the method on ASMX Web Service causes exception in <xref:System.Web.UI.ObjectConverter.ConvertValue%28System.Object%2CSystem.Type%2CSystem.String%29> because the WCF style definition of the order in the proxy takes precedence.</span></span>  
  
-   <span data-ttu-id="e5bf0-145">ASMX 웹 서비스는 먼저 추가 되 면 WCF 서비스에서 메서드를 호출 하면에서 예외가 발생 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 웹 서비스 스타일 정의 순서가 프록시 우선 하기 때문에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5bf0-145">If ASMX Web Service is added first, invoking method on WCF service causes exception in <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> because the Web Service style definition of the order in the proxy takes precedence.</span></span>  
  
 <span data-ttu-id="e5bf0-146"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>와 ASP.NET AJAX <xref:System.Web.Script.Serialization.JavaScriptSerializer>의 동작에는 상당한 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5bf0-146">There are significant differences in behavior between the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> and the ASP.NET AJAX <xref:System.Web.Script.Serialization.JavaScriptSerializer>.</span></span> <span data-ttu-id="e5bf0-147">예를 들어, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>는 키/값 쌍의 배열로 사전을 나타내고, ASP.NET AJAX <xref:System.Web.Script.Serialization.JavaScriptSerializer>는 실제 JSON 개체로 사전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e5bf0-147">For example, the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> represents a dictionary as an array of key/value pairs, whereas the ASP.NET AJAX <xref:System.Web.Script.Serialization.JavaScriptSerializer> represents a dictionary as actual JSON objects.</span></span> <span data-ttu-id="e5bf0-148">따라서 ASP.NET AJAX에서 사전은 다음과 같이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="e5bf0-148">So the following is the dictionary represented in ASP.NET AJAX.</span></span>  
  
```  
Dictionary<string, int> d = new Dictionary<string, int>();  
d.Add("one", 1);  
d.Add("two", 2);  
```  
  
 <span data-ttu-id="e5bf0-149">이 사전은 다음 목록에 표시된 것처럼 JSON 개체로 표현됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5bf0-149">This dictionary is represented in JSON objects as shown in the following list:</span></span>  
  
-   <span data-ttu-id="e5bf0-150"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>에 의한 [{"Key":"one","Value":1},{"Key":"two","Value":2}]</span><span class="sxs-lookup"><span data-stu-id="e5bf0-150">[{"Key":"one","Value":1},{"Key":"two","Value":2}] by the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer></span></span>  
  
-   <span data-ttu-id="e5bf0-151">{"one": 1, "two": 2} ASP.NET ajax <xref:System.Web.Script.Serialization.JavaScriptSerializer></span><span class="sxs-lookup"><span data-stu-id="e5bf0-151">{"one":1,"two":2} by the ASP.NET AJAX <xref:System.Web.Script.Serialization.JavaScriptSerializer></span></span>  
  
 <span data-ttu-id="e5bf0-152"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>는 키 유형이 문자열이 아닌 사전을 처리할 수 있다는 점에서 훨씬 강력합니다. 반면 <xref:System.Web.Script.Serialization.JavaScriptSerializer>는 키 유형이 문자열이 아닌 사전을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e5bf0-152">The <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> is more powerful in the sense that it can handle dictionaries where the key type is not string, while the <xref:System.Web.Script.Serialization.JavaScriptSerializer> cannot.</span></span> <span data-ttu-id="e5bf0-153">그러나 후자가 JSON에 더 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="e5bf0-153">But the latter is more JSON-friendly.</span></span>  
  
 <span data-ttu-id="e5bf0-154">이 두 serializer의 중요한 차이점이 다음 표에 요약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5bf0-154">The significant differences between these serializers are summarized in the following table.</span></span>  
  
|<span data-ttu-id="e5bf0-155">차이의 범주</span><span class="sxs-lookup"><span data-stu-id="e5bf0-155">Category of Differences</span></span>|<span data-ttu-id="e5bf0-156">DataContractJsonSerializer</span><span class="sxs-lookup"><span data-stu-id="e5bf0-156">DataContractJsonSerializer</span></span>|<span data-ttu-id="e5bf0-157">ASP.NET AJAX JavaScriptSerializer</span><span class="sxs-lookup"><span data-stu-id="e5bf0-157">ASP.NET AJAX JavaScriptSerializer</span></span>|  
|-----------------------------|--------------------------------|---------------------------------------|  
|<span data-ttu-id="e5bf0-158">빈 버퍼(새 바이트[0])를 <xref:System.Object> 또는 <xref:System.Uri> 또는 다른 클래스로 deserialize함</span><span class="sxs-lookup"><span data-stu-id="e5bf0-158">Deserializing the empty buffer (new byte[0]) into <xref:System.Object> (or <xref:System.Uri>, or some other classes).</span></span>|<span data-ttu-id="e5bf0-159">SerializationException</span><span class="sxs-lookup"><span data-stu-id="e5bf0-159">SerializationException</span></span>|<span data-ttu-id="e5bf0-160">null</span><span class="sxs-lookup"><span data-stu-id="e5bf0-160">null</span></span>|  
|<span data-ttu-id="e5bf0-161"><xref:System.DBNull.Value>의 serialization</span><span class="sxs-lookup"><span data-stu-id="e5bf0-161">Serialization of <xref:System.DBNull.Value></span></span>|<span data-ttu-id="e5bf0-162">{} (또는 {"__type": "#System"})</span><span class="sxs-lookup"><span data-stu-id="e5bf0-162">{} (or {"__type":"#System"})</span></span>|<span data-ttu-id="e5bf0-163">Null</span><span class="sxs-lookup"><span data-stu-id="e5bf0-163">Null</span></span>|  
|<span data-ttu-id="e5bf0-164">[Serializable] 형식의 private 멤버 serialization</span><span class="sxs-lookup"><span data-stu-id="e5bf0-164">Serialization of the private members of [Serializable] types.</span></span>|<span data-ttu-id="e5bf0-165">serialize됨</span><span class="sxs-lookup"><span data-stu-id="e5bf0-165">serialized</span></span>|<span data-ttu-id="e5bf0-166">serialize되지 않음</span><span class="sxs-lookup"><span data-stu-id="e5bf0-166">not serialized</span></span>|  
|<span data-ttu-id="e5bf0-167"><xref:System.Runtime.Serialization.ISerializable> 형식의 .public 속성 serialization</span><span class="sxs-lookup"><span data-stu-id="e5bf0-167">Serialization of the public properties of <xref:System.Runtime.Serialization.ISerializable> types.</span></span>|<span data-ttu-id="e5bf0-168">serialize되지 않음</span><span class="sxs-lookup"><span data-stu-id="e5bf0-168">not serialized</span></span>|<span data-ttu-id="e5bf0-169">serialize됨</span><span class="sxs-lookup"><span data-stu-id="e5bf0-169">serialized</span></span>|  
|<span data-ttu-id="e5bf0-170">JSON "확장"</span><span class="sxs-lookup"><span data-stu-id="e5bf0-170">"Extensions" of JSON</span></span>|<span data-ttu-id="e5bf0-171">개체 멤버 이름({"a":"hello"})에 따옴표를 사용해야 하는 JSON 사양 준수</span><span class="sxs-lookup"><span data-stu-id="e5bf0-171">Adheres to the JSON specification, which requires quotes on object member names ({"a":"hello"}).</span></span>|<span data-ttu-id="e5bf0-172">따옴표가 없는 개체 멤버 이름({a:"hello"}) 지원</span><span class="sxs-lookup"><span data-stu-id="e5bf0-172">Supports the names of object members without quotes ({a:"hello"}).</span></span>|  
|<span data-ttu-id="e5bf0-173"><xref:System.DateTime> UTC(협정 세계시)</span><span class="sxs-lookup"><span data-stu-id="e5bf0-173"><xref:System.DateTime> Coordinated Universal Time (UTC)</span></span>|<span data-ttu-id="e5bf0-174">형식을 지원 하지 않습니다 "\\/Date(123456789U)\\/" 또는 "\\/Date\\(\d+ (U&#124;(\\+\\-[\d{4}]))?\\) \\\\/)".</span><span class="sxs-lookup"><span data-stu-id="e5bf0-174">Does not support format "\\/Date(123456789U)\\/" or "\\/Date\\(\d+(U&#124;(\\+\\-[\d{4}]))?\\)\\\\/)".</span></span>|<span data-ttu-id="e5bf0-175">지원 형식 "\\/Date(123456789U)\\/" 및 "\\/Date\\(\d+ (U&#124;(\\+\\-[\d{4}]))?\\) \\ \\/) "형식을 DateTime 값으로.</span><span class="sxs-lookup"><span data-stu-id="e5bf0-175">Supports format "\\/Date(123456789U)\\/" and "\\/Date\\(\d+(U&#124;(\\+\\-[\d{4}]))?\\)\\\\/)" as DateTime values.</span></span>|  
|<span data-ttu-id="e5bf0-176">사전의 표현</span><span class="sxs-lookup"><span data-stu-id="e5bf0-176">Representation of dictionaries</span></span>|<span data-ttu-id="e5bf0-177">KeyValuePair의 배열\<K, V >, 문자열이 아닌 키 유형을 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5bf0-177">An array of KeyValuePair\<K,V>, handles key types that are not strings.</span></span>|<span data-ttu-id="e5bf0-178">실제 JSON 개체로 문자열인 키 유형만 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="e5bf0-178">As actual JSON objects - but only handles key types that are strings.</span></span>|  
|<span data-ttu-id="e5bf0-179">이스케이프된 문자</span><span class="sxs-lookup"><span data-stu-id="e5bf0-179">Escaped characters</span></span>|<span data-ttu-id="e5bf0-180">항상 이스케이프 슬래시(/)가 포함되고, "\n"과 같이 이스케이프되지 않은 잘못된 JSON 문자는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e5bf0-180">Always with an escape forward slash (/); never allows un-escaped invalid JSON characters, such as "\n".</span></span>|<span data-ttu-id="e5bf0-181">DateTime 값에 이스케이프 슬래시(/)가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5bf0-181">With an escape forward slash (/) for DateTime values.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e5bf0-182">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e5bf0-182">See Also</span></span>  
 [<span data-ttu-id="e5bf0-183">방법: 구성을 사용하여 ASP.NET AJAX 끝점 추가</span><span class="sxs-lookup"><span data-stu-id="e5bf0-183">How to: Use Configuration to Add an ASP.NET AJAX Endpoint</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md)
