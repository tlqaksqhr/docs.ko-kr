---
title: '방법: 구성을 사용하지 않고 ASP.NET AJAX 끝점 추가'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b05c1742-8d0a-4673-9d71-725b18a3008e
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b8d9d9b55bbeade5aa337719ba19ea9f386dfd6a
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-add-an-aspnet-ajax-endpoint-without-using-configuration"></a><span data-ttu-id="1e140-102">방법: 구성을 사용하지 않고 ASP.NET AJAX 끝점 추가</span><span class="sxs-lookup"><span data-stu-id="1e140-102">How to: Add an ASP.NET AJAX Endpoint Without Using Configuration</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="1e140-103">를 통해 클라이언트 웹 사이트의 JavaScript에서 호출할 수 있는 ASP.NET AJAX 사용 끝점을 노출하는 서비스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e140-103"> allows you to create a service that exposes an ASP.NET AJAX-enabled endpoint that can be called from JavaScript on a client Web site.</span></span> <span data-ttu-id="1e140-104">이와 같은 끝점을 만들려면 다른 모든 WCF 끝점에서처럼 구성 파일을 사용하거나 구성 요소가 필요하지 않은 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e140-104">To create such an endpoint, you can either use a configuration file, as with all other WCF endpoints, or use a method that does not require any configuration elements.</span></span> <span data-ttu-id="1e140-105">이 항목에서는 두 번째 접근 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1e140-105">This topic demonstrates the second approach.</span></span>  
  
 <span data-ttu-id="1e140-106">구성 없이 ASP.NET AJAX 끝점을 사용하여 서비스를 만들려면 서비스는 IIS(인터넷 정보 서비스)에 의해 호스팅되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e140-106">To create services with ASP.NET AJAX endpoints without configuration, the services must be hosted by Internet Information Services (IIS).</span></span> <span data-ttu-id="1e140-107">이 방식을 사용 하 여 ASP.NET AJAX 끝점을 활성화 하려면 지정 된 <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> 에서 공장 매개 변수로 [ @ServiceHost ](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) .svc 파일에 지시문.</span><span class="sxs-lookup"><span data-stu-id="1e140-107">To activate an ASP.NET AJAX endpoint using this approach, specify the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> as the Factory parameter in the [@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) directive in the .svc file.</span></span> <span data-ttu-id="1e140-108">이 사용자 지정 팩터리는 클라이언트 웹 사이트의 JavaScript에서 호출할 수 있도록 ASP.NET AJAX 끝점을 자동으로 구성하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="1e140-108">This custom factory is the component that automatically configures an ASP.NET AJAX endpoint so that it can be called from JavaScript on a client Web site.</span></span>  
  
 <span data-ttu-id="1e140-109">작업 예제를 참조 하십시오.는 [구성 하지 않고 AJAX 서비스](../../../../docs/framework/wcf/samples/ajax-service-without-configuration.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1e140-109">For a working example, see the [AJAX Service Without Configuration](../../../../docs/framework/wcf/samples/ajax-service-without-configuration.md).</span></span>  
  
 <span data-ttu-id="1e140-110">구성 요소를 사용 하 여 ASP.NET AJAX 끝점을 구성 하는 방법의 개요를 참조 하십시오. [하는 방법: ASP.NET AJAX 끝점 추가를 사용 하 여 구성](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1e140-110">For an outline of how to configure an ASP.NET AJAX endpoint using configuration elements, see [How to: Use Configuration to Add an ASP.NET AJAX Endpoint](../../../../docs/framework/wcf/feature-details/how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md).</span></span>  
  
### <a name="to-create-a-basic-wcf-service"></a><span data-ttu-id="1e140-111">기본 WCF 서비스를 만들려면</span><span class="sxs-lookup"><span data-stu-id="1e140-111">To create a basic WCF service</span></span>  
  
1.  <span data-ttu-id="1e140-112">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 특성으로 표시된 인터페이스를 사용하여 기본 <xref:System.ServiceModel.ServiceContractAttribute> 서비스 계약을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1e140-112">Define a basic [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service contract with an interface marked with the <xref:System.ServiceModel.ServiceContractAttribute> attribute.</span></span> <span data-ttu-id="1e140-113">각 작업을 <xref:System.ServiceModel.OperationContractAttribute>로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="1e140-113">Mark each operation with the <xref:System.ServiceModel.OperationContractAttribute>.</span></span> <span data-ttu-id="1e140-114"><xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A> 속성을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e140-114">Be sure to set the <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A> property.</span></span>  
  
    ```csharp  
    [ServiceContract(Namespace = "MyService")]]  
    public interface ICalculator  
    {  
        [OperationContract]  
        // This operation returns the sum of d1 and d2.  
        double Add(double n1, double n2);  
  
        //Other operations omitted…  
  
    }  
    ```  
  
2.  <span data-ttu-id="1e140-115">`ICalculator`를 사용하여 `CalculatorService` 서비스 계약을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="1e140-115">Implement the `ICalculator` service contract with a `CalculatorService`.</span></span>  
  
    ```csharp  
    public class CalculatorService : ICalculator  
    {  
        public double Add(double n1, double n2)  
        {  
            return n1 + n2;  
        }  
  
    //Other operations omitted…  
    ```  
  
3.  <span data-ttu-id="1e140-116">네임스페이스 블록에 `ICalculator` 및 `CalculatorService` 구현을 래핑하여 이러한 구현에 대한 네임스페이스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1e140-116">Define a namespace for the `ICalculator` and `CalculatorService` implementations by wrapping them in a namespace block.</span></span>  
  
    ```csharp  
    Namespace Microsoft.Ajax.Samples  
    {  
        //Include the code for ICalculator and Caculator here.  
    }  
    ```  
  
### <a name="to-host-the-service-in-internet-information-services-without-configuration"></a><span data-ttu-id="1e140-117">구성 없이 인터넷 정보 서비스에서 서비스를 호스팅하려면</span><span class="sxs-lookup"><span data-stu-id="1e140-117">To host the service in Internet Information Services without configuration</span></span>  
  
1.  <span data-ttu-id="1e140-118">응용 프로그램에서 .svc 확장명이 있는 service라는 새 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1e140-118">Create a new file named service with a .svc extension in the application.</span></span> <span data-ttu-id="1e140-119">적절 한 추가 하 여이 파일을 편집 [ @ServiceHost ](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) 서비스에 대 한 지시문 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="1e140-119">Edit this file by adding the appropriate [@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) directive information for the service.</span></span> <span data-ttu-id="1e140-120">지정 하는 <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> 에 사용 되는 [ @ServiceHost ](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) 지시문을 자동으로 ASP.NET AJAX 끝점을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e140-120">Specify that the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> is to be used in the [@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) directive to automatically configure an ASP.NET AJAX endpoint.</span></span>  
  
    ```  
    <%@ServiceHost   
        language=c#   
        Debug="true"   
        Service="Microsoft.Ajax.Samples.CalculatorService"  
        Factory=System.ServiceModel.Activation.WebScriptServiceHostFactory  
    %>  
    ```  
  
2.  <span data-ttu-id="1e140-121">서비스를 빌드하고 클라이언트에서 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="1e140-121">Build the service and call it from the client.</span></span> <span data-ttu-id="1e140-122">호출하면 IIS(인터넷 정보 서비스)가 해당 서비스를 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="1e140-122">Internet Information Services (IIS) activates the service when called.</span></span> <span data-ttu-id="1e140-123">IIS에서 호스팅하는 방법에 대 한 자세한 내용은 참조 [하는 방법: IIS에서 WCF 서비스 호스팅](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1e140-123">For more information about hosting in IIS, see [How to: Host a WCF Service in IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md).</span></span>  
  
### <a name="to-call-the-service"></a><span data-ttu-id="1e140-124">서비스를 호출하려면</span><span class="sxs-lookup"><span data-stu-id="1e140-124">To call the service</span></span>  
  
1.  <span data-ttu-id="1e140-125">서비스를 사용 하 고 요청을 보내서 전송 하 여 호출할 수 있도록 끝점은.svc 파일을 기준으로 빈 주소에 구성 됩니다\<작업 >-예를 들어에 대 한 service.svc/Add는 `Add` 작업 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e140-125">The endpoint is configured at an empty address relative to the .svc file, so the service is now available and can be invoked by sending requests to service.svc/\<operation> - for example, service.svc/Add for the `Add` operation.</span></span> <span data-ttu-id="1e140-126">서비스 URL을 ASP.NET AJAX Script Manager 컨트롤의 스크립트 컬렉션에 입력하여 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e140-126">You can use it by entering the service URL into the Scripts collection of the ASP.NET AJAX Script Manager control.</span></span> <span data-ttu-id="1e140-127">예를 들어 참조는 [구성 하지 않고 AJAX 서비스](../../../../docs/framework/wcf/samples/ajax-service-without-configuration.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1e140-127">For an example, see the [AJAX Service Without Configuration](../../../../docs/framework/wcf/samples/ajax-service-without-configuration.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1e140-128">예제</span><span class="sxs-lookup"><span data-stu-id="1e140-128">Example</span></span>  
  
 <span data-ttu-id="1e140-129">자동으로 구성된 끝점은 기본 URL을 기준으로 비어 있는 주소에 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e140-129">The automatically-configured endpoint is created at an empty address relative to the base URL.</span></span> <span data-ttu-id="1e140-130">또한 구성 파일을 추가하여 이 접근 방법으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e140-130">A configuration file can also be added and used with this approach.</span></span> <span data-ttu-id="1e140-131">구성 파일에 끝점 정의가 포함된 경우 이러한 끝점은 자동으로 구성된 끝점에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e140-131">If the configuration file contains endpoint definitions, these endpoints are added to the automatically-configured endpoint.</span></span>  
  
 <span data-ttu-id="1e140-132">예를 들어, service.svc는 <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>를 사용하고 서비스 디렉터리에는 "soap" 상대 주소에서 <xref:System.ServiceModel.BasicHttpBinding>을 사용하여 동일한 서비스에 대해 끝점을 정의하는 Web.config 파일이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e140-132">For example, service.svc uses the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> and the service directory contains a Web.config file that defines an endpoint for the same service using the <xref:System.ServiceModel.BasicHttpBinding> at the "soap" relative address.</span></span> <span data-ttu-id="1e140-133">이 경우 서비스는 두 개의 끝점을 포함합니다. 한 끝점은 ASP.NET AJAX 요청에 응답하는 service.svc에 위치하고 다른 끝점은 SOAP 요청에 응답하는 service.svc/soap에 위치합니다.</span><span class="sxs-lookup"><span data-stu-id="1e140-133">In this case, the service contains two endpoints: one at service.svc (which responds to ASP.NET AJAX requests) and another at service.svc/soap (which responds to SOAP requests).</span></span>  
  
 <span data-ttu-id="1e140-134">구성 파일이 비어 있는 상대 주소에 끝점을 정의하고 <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>가 사용되는 경우 예외가 throw되어 서비스를 시작할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1e140-134">If the configuration file defines an endpoint at an empty relative address and the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> is used, an exception is thrown and the service fails to start.</span></span>  
  
 <span data-ttu-id="1e140-135">구성을 사용하여 자동으로 구성된 끝점에서 설정을 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1e140-135">You cannot use configuration to modify settings on the automatically-configured endpoint.</span></span> <span data-ttu-id="1e140-136">판독기 할당량과 같은 설정을 수정해야 하는 경우 .svc 파일에서 <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>를 제거하고 끝점에 대한 구성 항목을 만들어 구성을 사용하지 않는 접근 방법을 사용하지 말아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e140-136">If any setting (such as a reader quota) must be modified, you must not use the configuration-free approach by removing the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> from the .svc file and creating a configuration entry for the endpoint.</span></span>  
  
 <span data-ttu-id="1e140-137">서비스를 사용하려면 ASP.NET 호환 모드가 필요합니다. 예를 들어, <xref:System.Web.HttpContext> 클래스 또는 ASP.NET 인증 메커니즘을 사용하는 경우 이 모드를 사용하도록 설정하려면 구성 파일이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1e140-137">If your service requires ASP.NET Compatibility Mode - for example, if it uses the <xref:System.Web.HttpContext> class or ASP.NET authorization mechanisms - a configuration file is still required to turn on this mode.</span></span> <span data-ttu-id="1e140-138">필수 구성 요소는 [ \<serviceHostingEnvironment >](../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) 요소를 다음과 같이 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e140-138">The configuration element required is the [\<serviceHostingEnvironment>](../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) element, which must be added as follows.</span></span>  
  
 `<system.serviceModel>`  
  
 `<serviceHostingEnvironment aspNetCompatibilityEnabled="true" /> </system.serviceModel>`  
  
 <span data-ttu-id="1e140-139">자세한 내용은 참조는 [WCF 서비스 및 ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md) 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="1e140-139">For more information, see the [WCF Services and ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md) topic.</span></span>  
  
 <span data-ttu-id="1e140-140"><xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> 클래스가 <xref:System.ServiceModel.Activation.ServiceHostFactory>의 파생 클래스인 경우</span><span class="sxs-lookup"><span data-stu-id="1e140-140">The <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> class is a derived class of <xref:System.ServiceModel.Activation.ServiceHostFactory>.</span></span> <span data-ttu-id="1e140-141">서비스 호스트 팩터리 메커니즘에 대 한 자세한 내용은 참조 하십시오.는 [호스팅를 사용 하 여 ServiceHostFactory 확장](../../../../docs/framework/wcf/extending/extending-hosting-using-servicehostfactory.md) 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="1e140-141">For a detailed explanation of the service host factory mechanism, see the [Extending Hosting Using ServiceHostFactory](../../../../docs/framework/wcf/extending/extending-hosting-using-servicehostfactory.md) topic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e140-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1e140-142">See Also</span></span>  
 [<span data-ttu-id="1e140-143">ASP.NET AJAX용 WCF 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="1e140-143">Creating WCF Services for ASP.NET AJAX</span></span>](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)  
 [<span data-ttu-id="1e140-144">방법: AJAX 사용 ASP.NET 웹 서비스를 WCF로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="1e140-144">How to: Migrate AJAX-Enabled ASP.NET Web Services to WCF</span></span>](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)
