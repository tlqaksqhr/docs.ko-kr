---
title: "보안 유효성 검사"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 48dcd496-0c4f-48ce-8b9b-0e25b77ffa58
caps.latest.revision: "35"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 4e8e8ff9a99c362fb5e2a6f5ef1161f48df86ceb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="security-validation"></a><span data-ttu-id="ac89c-102">보안 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="ac89c-102">Security Validation</span></span>
<span data-ttu-id="ac89c-103">이 샘플에서는 사용자 지정 동작을 통해 컴퓨터에 있는 서비스의 유효성을 검사하여 특정 기준을 충족하는지 확인하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ac89c-103">This sample demonstrates how to use a custom behavior to validate services on a computer to ensure they meet specific criteria.</span></span> <span data-ttu-id="ac89c-104">이 샘플에서는 서비스의 각 끝점을 검사하여 보안 바인딩 요소가 포함되어 있는지 확인하는 방식으로 사용자 지정 동작을 통해 서비스의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="ac89c-104">In this sample, services are validated by the custom behavior by scanning through each endpoint on the service and checking to see whether they contain secure binding elements.</span></span> <span data-ttu-id="ac89c-105">이 샘플에 따라는 [시작](../../../../docs/framework/wcf/samples/getting-started-sample.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ac89c-105">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ac89c-106">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac89c-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
## <a name="endpoint-validation-custom-behavior"></a><span data-ttu-id="ac89c-107">끝점 유효성 검사 사용자 지정 동작</span><span class="sxs-lookup"><span data-stu-id="ac89c-107">Endpoint Validation Custom Behavior</span></span>  
 <span data-ttu-id="ac89c-108">`Validate` 인터페이스에 포함된 <xref:System.ServiceModel.Description.IServiceBehavior> 메서드에 사용자 코드를 추가함으로써 서비스 또는 끝점에 사용자 지정 동작을 제공하여 사용자 정의 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac89c-108">By adding user code to the `Validate` method contained in the <xref:System.ServiceModel.Description.IServiceBehavior> interface, custom behavior can be given to a service or endpoint to perform user-defined actions.</span></span> <span data-ttu-id="ac89c-109">다음 코드는 서비스에 포함된 각 끝점을 루프하여 바인딩 컬렉션에서 보안 바인딩을 검색하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac89c-109">The following code is used to loop through each endpoint contained in a service, which searches through their binding collections for secure bindings.</span></span>  
  
```  
public void Validate(ServiceDescription serviceDescription,   
                                       ServiceHostBase serviceHostBase)  
{  
    // Loop through each endpoint individually gathering their    
       binding elements.  
    foreach (ServiceEndpoint endpoint in serviceDescription.Endpoints)  
    {  
        secureElementFound = false;  
  
        // Retrieve the endpoint's binding element collection.  
        BindingElementCollection bindingElements =   
            endpoint.Binding.CreateBindingElements();  
  
        // Look to see if the binding elements collection contains any   
        // secure binding elements. Transport, Asymmetric, and Symmetric      
        // binding elements are all derived from SecurityBindingElement.  
        if ((bindingElements.Find<SecurityBindingElement>() != null) || (bindingElements.Find<HttpsTransportBindingElement>() != null) || (bindingElements.Find<WindowsStreamSecurityBindingElement>() != null) || (bindingElements.Find<SslStreamSecurityBindingElement>() != null))  
        {  
            secureElementFound = true;  
        }  
  
    // Send a message to the system event viewer when an endpoint is deemed insecure.  
    if (!secureElementFound)  
        throw new Exception(System.DateTime.Now.ToString() + ": The endpoint \"" + endpoint.Name + "\" has no secure bindings.");  
    }  
}  
```  
  
 <span data-ttu-id="ac89c-110">Web.config 파일에 다음 코드를 추가하면 서비스가 인식할 수 있는 `serviceValidate` 동작 확장이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac89c-110">Adding the following code to Web.config file adds the `serviceValidate` behavior extension for the service to recognize.</span></span>  
  
```xml  
<system.serviceModel>  
    <extensions>  
        <behaviorExtensions>  
            <add name="endpointValidate" type="Microsoft.ServiceModel.Samples.EndpointValidateElement, endpointValidate, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null" />  
        </behaviorExtensions>  
    </extensions>  
...  
```  
  
 <span data-ttu-id="ac89c-111">동작 확장이 서비스에 추가되었으면 Web.config 파일의 동작 목록과 서비스에 `endpointValidate` 동작을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac89c-111">Once the behavior extension is added to the service, it is now possible to add the `endpointValidate` behavior to the list of behaviors in the Web.config file and thus, to the service.</span></span>  
  
```xml  
<behaviors>  
    <serviceBehaviors>  
        <behavior name="CalcServiceSEB1">  
            <serviceMetadata httpGetEnabled="true" />  
            <endpointValidate />  
        </behavior>  
    </serviceBehaviors>  
</behaviors>  
```  
  
 <span data-ttu-id="ac89c-112">Web.config 파일에 추가된 동작 및 동작 확장은 개별 서비스에 동작을 적용하며, Machine.config 파일에 추가된 경우에는 컴퓨터의 모든 활성 서비스에 동작을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="ac89c-112">Behaviors and their extensions that are added to the Web.config file apply behavior to individual services, while when added to the Machine.config file apply behavior to every service active on the computer.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ac89c-113">모든 서비스에 동작을 추가할 경우에는 내용을 변경하기 전에 Machine.config 파일을 백업하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ac89c-113">When adding behavior to all services, it is suggested to backup the Machine.config file before making any change.</span></span>  
  
 <span data-ttu-id="ac89c-114">이제 이 샘플의 client\bin 디렉터리에 제공된 클라이언트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ac89c-114">Now run the client provided in the client\bin directory of this sample.</span></span> <span data-ttu-id="ac89c-115">"요청된 서비스 'http://localhost/servicemodelsamples/service.svc'을(를) 활성화할 수 없습니다."라는 메시지와 함께 예외가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="ac89c-115">An exception has occurs with the following message: "The requested service, 'http://localhost/servicemodelsamples/service.svc' could not be activated."</span></span> <span data-ttu-id="ac89c-116">이 예외는 동작의 유효성을 검사하는 끝점에 의해 끝점이 안전하지 않은 것으로 간주되어 서비스가 시작하지 못하도록 하기 때문에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="ac89c-116">This is expected because an endpoint is considered insecure by the endpoint validating behavior and prevents the service from being started.</span></span> <span data-ttu-id="ac89c-117">이 동작은 또한 안전하지 않은 끝점을 설명하는 내부 예외를 throw하고 시스템 이벤트 뷰어의 "System.ServiceModel 4.0.0.0" 소스 및 "WebHost" 범주 아래에 메시지를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="ac89c-117">The behavior also throws an internal exception that describes which endpoint is insecure and writes a message to the system Event Viewer under the "System.ServiceModel 4.0.0.0" source and the "WebHost" category.</span></span> <span data-ttu-id="ac89c-118">또한 이 샘플에서 서비스에 대한 추적을 켤 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac89c-118">It is also possible to turn on tracing on the service in this sample.</span></span> <span data-ttu-id="ac89c-119">이 경우 사용자는 Service Trace Viewer 도구에서 결과 서비스 추적을 열어 동작의 유효성을 검사하는 끝점에서 throw한 예외를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac89c-119">This allows the user to view the exceptions thrown by endpoint validating behavior by opening the resulting service traces using the Service Trace Viewer tool.</span></span>  
  
#### <a name="to-view-failed-endpoint-validation-exception-messages-in-the-event-viewer"></a><span data-ttu-id="ac89c-120">이벤트 뷰어에서 실패한 끝점 유효성 검사 예외 메시지를 보려면</span><span class="sxs-lookup"><span data-stu-id="ac89c-120">To view failed endpoint validation exception messages in the Event Viewer</span></span>  
  
1.  <span data-ttu-id="ac89c-121">클릭는 **시작** 메뉴와 선택 **실행...** .</span><span class="sxs-lookup"><span data-stu-id="ac89c-121">Click the **Start** menu and select **Run…**.</span></span>  
  
2.  <span data-ttu-id="ac89c-122">형식 `eventvwr` 클릭 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="ac89c-122">Type `eventvwr` and click **OK**.</span></span>  
  
3.  <span data-ttu-id="ac89c-123">이벤트 뷰어 창에서 클릭 **응용 프로그램**합니다.</span><span class="sxs-lookup"><span data-stu-id="ac89c-123">In the Event Viewer window, click **Application**.</span></span>  
  
4.  <span data-ttu-id="ac89c-124">"WebHost" 범주 아래에서 최근에 추가 된 "System.ServiceModel 4.0.0.0" 이벤트를 두 번의 **응용 프로그램** 창 안전 하지 않은 끝점 메시지를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac89c-124">Double-click the recently added "System.ServiceModel 4.0.0.0" event under the "WebHost" category in the **Application** window to view insecure endpoint messages.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="ac89c-125">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="ac89c-125">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="ac89c-126">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ac89c-126">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="ac89c-127">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="ac89c-127">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="ac89c-128">지침에 따라 단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ac89c-128">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ac89c-129">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac89c-129">The samples may already be installed on your computer.</span></span> <span data-ttu-id="ac89c-130">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="ac89c-130">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="ac89c-131">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="ac89c-131">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ac89c-132">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac89c-132">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ServiceValidation`  
  
## <a name="see-also"></a><span data-ttu-id="ac89c-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ac89c-133">See Also</span></span>  
 [<span data-ttu-id="ac89c-134">AppFabric 모니터링 샘플</span><span class="sxs-lookup"><span data-stu-id="ac89c-134">AppFabric Monitoring Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193959)
