---
title: "표준 끝점 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ecd6a62f-9619-4778-a497-6f888087a9ea
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 85dda1619fe3a77c4716806de2467cb96287b2f9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="usage-of-standard-endpoints"></a><span data-ttu-id="666ce-102">표준 끝점 사용</span><span class="sxs-lookup"><span data-stu-id="666ce-102">Usage of Standard Endpoints</span></span>
<span data-ttu-id="666ce-103">이 샘플에서는 서비스 구성 파일에서 표준 끝점을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="666ce-103">This sample demonstrates how to use standard endpoints in service configuration files.</span></span> <span data-ttu-id="666ce-104">표준 끝점을 사용하면 사용자는 주소, 바인딩 및 계약 조합을 설명하는 단일 속성과 끝점에 관련된 추가 속성을 사용하여 끝점 정의를 단순화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="666ce-104">A standard endpoint allows the user to simplify endpoint definitions by using a single property to describe an address, binding and contract combination with additional properties associated to it.</span></span> <span data-ttu-id="666ce-105">이 샘플에서는 사용자 지정 표준 끝점을 정의 및 구현하는 방법과 끝점의 특정 속성을 정의하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="666ce-105">This sample demonstrates how to define and implement a custom standard endpoint and how to define specific properties in the endpoint.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="666ce-106">샘플 세부 정보</span><span class="sxs-lookup"><span data-stu-id="666ce-106">Sample Details</span></span>  
 <span data-ttu-id="666ce-107">서비스 끝점은 주소, 바인딩 및 계약의 세 매개 변수를 제공하여 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="666ce-107">Service endpoints can be specified by supplying three parameters: address, binding and contract.</span></span> <span data-ttu-id="666ce-108">제공할 수 있는 다른 매개 변수로는 동작 구성, 헤더 및 수신 대기 URI 등이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="666ce-108">Other parameters that can be supplied include behavior configuration, headers, listen URI, and so on.</span></span> <span data-ttu-id="666ce-109">일부 경우에는 주소, 바인딩 및 계약의 일부 또는 모두에 변경할 수 없는 값이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="666ce-109">In some cases, any or all of addresses, bindings and contracts have values that cannot change.</span></span> <span data-ttu-id="666ce-110">이러한 이유로 표준 끝점을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="666ce-110">For this reason, it is possible to use standard endpoints.</span></span> <span data-ttu-id="666ce-111">이러한 끝점의 몇 가지 예로는 메타데이터 교환 끝점과 검색 끝점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="666ce-111">Some examples of such endpoints include metadata exchange endpoints and discovery endpoints.</span></span> <span data-ttu-id="666ce-112">표준 끝점을 사용하면 고정 특성의 정보를 제공하거나 고유한 표준 끝점을 만들 필요 없이 서비스 끝점의 구성을 그대로 사용하여 유용성을 향상시킬 수도 있습니다. 예를 들어 적절한 기본값 집합을 제공하여 구성 파일의 복잡성을 줄임으로써 유용성을 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="666ce-112">Standard endpoints also improve usability by allowing configuration of service endpoints without having to provide information of a fixed nature or to create their own standard endpoints, for example to improve usability by supplying a reasonable set of default values and thus reducing the verbosity of configuration files.</span></span>  
  
 <span data-ttu-id="666ce-113">이 샘플은 두 개의 표준 끝점을 정의하는 서비스 및 이 서비스와 통신하는 클라이언트의 두 프로젝트로 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="666ce-113">This sample consists of two projects: the service that defines two standard endpoints and the client that communicates with the service.</span></span> <span data-ttu-id="666ce-114">구성 파일에서 서비스에 대한 표준 끝점이 정의되는 방법은 다음 예제와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="666ce-114">The way the standard endpoints are defined for the service in the configuration file is show in the following example.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <system.serviceModel>  
    <extensions>  
      <endpointExtensions>  
        <add name="customEndpoint" type="Microsoft.Samples.StandardEndpoints.CustomEndpointCollectionElement, service" />  
      </endpointExtensions>  
    </extensions>  
    <services>  
      <service name="Microsoft.Samples.StandardEndpoints.CalculatorService">  
        <endpoint address="http://localhost:8000/Samples/Service.svc/customEndpoint" contract="Microsoft.Samples.StandardEndpoints.ICalculator" kind="customEndpoint" />  
        <endpoint kind="mexEndpoint" />  
      </service>  
    </services>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <standardEndpoints>  
      <customEndpoint>  
        <standardEndpoint property="True" />  
      </customEndpoint>  
    </standardEndpoints>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="666ce-115">서비스에 대해 정의되는 첫 번째 끝점은 `customEndpoint` 종류로, `<standardEndpoints>` 섹션에서 해당 정의를 볼 수 있으며 `property` 속성 값은 `true`로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="666ce-115">The first endpoint defined for the service is of kind `customEndpoint`, whose definition can be seen in the `<standardEndpoints>` section, in which the property `property` is given the value `true`.</span></span> <span data-ttu-id="666ce-116">이 끝점은 새 속성으로 사용자 지정된 끝점입니다.</span><span class="sxs-lookup"><span data-stu-id="666ce-116">This is the case of an endpoint customized with a new property.</span></span> <span data-ttu-id="666ce-117">두 번째 끝점은 주소, 바인딩 및 계약의 값이 고정된 메타데이터 끝점에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="666ce-117">The second endpoint corresponds to a metadata endpoint, in which the values for address, binding and contract are fixed.</span></span>  
  
 <span data-ttu-id="666ce-118">표준 끝점 요소를 정의하려면 `StandardEndpointElement`에서 파생된 클래스를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="666ce-118">To define the standard endpoint element, a class that derives from `StandardEndpointElement` must be created.</span></span> <span data-ttu-id="666ce-119">이 샘플에서는 `CustomEndpointElement`가 다음 예제와 같이 정의되었습니다.</span><span class="sxs-lookup"><span data-stu-id="666ce-119">In the case of this sample, the `CustomEndpointElement` class has been defined as shown in the following example.</span></span>  
  
```csharp  
public class CustomEndpointElement : StandardEndpointElement  
{  
    public bool Property  
    {  
        get { return (bool)base["property"]; }  
        set { base["property"] = value; }  
    }  
  
    protected override ConfigurationPropertyCollection Properties  
    {  
        get  
        {  
            ConfigurationPropertyCollection properties = base.Properties;  
            properties.Add(new ConfigurationProperty("property", typeof(bool), false, ConfigurationPropertyOptions.None));  
            return properties;  
        }  
    }  
  
    protected override Type EndpointType  
    {  
        get { return typeof(CustomEndpoint); }  
    }  
  
    protected override ServiceEndpoint CreateServiceEndpoint(ContractDescription contract)  
    {  
        return new CustomEndpoint();  
    }  
  
    protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ServiceEndpointElement serviceEndpointElement)  
    {  
        CustomEndpoint customEndpoint = (CustomEndpoint)endpoint;  
        customEndpoint.Property = this.Property;  
    }  
  
    protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ChannelEndpointElement channelEndpointElement)  
    {  
        CustomEndpoint customEndpoint = (CustomEndpoint)endpoint;  
        customEndpoint.Property = this.Property;  
    }  
  
    protected override void OnInitializeAndValidate(ServiceEndpointElement serviceEndpointElement)  
    {  
    }  
  
    protected override void OnInitializeAndValidate(ChannelEndpointElement channelEndpointElement)  
    {  
    }  
}  
```  
  
 <span data-ttu-id="666ce-120">`CreateServiceEndpoint` 함수에서는 `CustomEndpoint` 개체가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="666ce-120">In the `CreateServiceEndpoint` function, a `CustomEndpoint` object is created.</span></span> <span data-ttu-id="666ce-121">해당 정의는 다음 예제와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="666ce-121">Its definition is shown in the following example.</span></span>  
  
```  
public class CustomEndpoint : ServiceEndpoint  
    {  
        public CustomEndpoint()  
            : this(string.Empty)  
        {  
        }  
  
        public CustomEndpoint(string address)  
            : this(address, ContractDescription.GetContract(typeof(ICalculator)))  
        {  
        }  
  
        public CustomEndpoint(string address, ContractDescription contract)  
            : base(contract)  
        {  
            this.Binding = new BasicHttpBinding();  
            this.IsSystemEndpoint = false;  
        }  
  
        public bool Property  
        {  
            get;  
            set;  
        }  
    }  
```  
  
 <span data-ttu-id="666ce-122">서비스와 클라이언트 간의 통신을 수행하기 위해 서비스에 대한 서비스 참조가 클라이언트에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="666ce-122">To perform the communication between service and client, a service reference is created in the client to the service.</span></span> <span data-ttu-id="666ce-123">샘플이 빌드되어 실행되면 서비스가 실행되고 클라이언트가 서비스와 통신합니다.</span><span class="sxs-lookup"><span data-stu-id="666ce-123">When the sample is built and executed, the service executes and the client communicates with it.</span></span> <span data-ttu-id="666ce-124">서비스 참조는 서비스에 변경 사항이 있을 때마다 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="666ce-124">Note that the service reference should be updated every time there is some change in the service.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="666ce-125">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="666ce-125">To use this sample</span></span>  
  
1.  <span data-ttu-id="666ce-126">[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]에서 StandardEndpoints.sln 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="666ce-126">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the StandardEndpoints.sln file.</span></span>  
  
2.  <span data-ttu-id="666ce-127">여러 개의 프로젝트가 시작되도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="666ce-127">Enable multiple projects to start up.</span></span>  
  
    1.  <span data-ttu-id="666ce-128">**솔루션 탐색기**을 Standard Endpoints 솔루션을 마우스 오른쪽 단추로 클릭 한 다음 선택 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="666ce-128">In **Solution Explorer**, right-click the Standard Endpoints solution and then select **Properties**.</span></span>  
  
    2.  <span data-ttu-id="666ce-129">**공용 속성**선택, **시작 프로젝트**, 클릭 하 고 **여러 개의 시작 프로젝트**합니다.</span><span class="sxs-lookup"><span data-stu-id="666ce-129">In **Common Properties**, select **Startup Project**, and then click **Multiple Startup Projects**.</span></span>  
  
    3.  <span data-ttu-id="666ce-130">와 함께 서비스 프로젝트를 목록의 시작 부분으로 이동 된 **동작** 로 설정 **시작**합니다.</span><span class="sxs-lookup"><span data-stu-id="666ce-130">Move the Service project to the beginning of the list, with the **Action** set to **Start**.</span></span>  
  
    4.  <span data-ttu-id="666ce-131">와 함께 클라이언트 프로젝트를 Service 프로젝트 다음에 이동는 **동작** 로 설정 **시작**합니다.</span><span class="sxs-lookup"><span data-stu-id="666ce-131">Move the Client project after the Service project, also with the **Action** set to **Start**.</span></span>  
  
         <span data-ttu-id="666ce-132">이렇게 하면 Client 프로젝트가 Service 프로젝트 다음에 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="666ce-132">This specifies that the Client project is executed after the Service project.</span></span>  
  
3.  <span data-ttu-id="666ce-133">F5 키를 눌러 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="666ce-133">To run the solution, press F5.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="666ce-134">이러한 단계가 제대로 수행되지 않으면 다음 단계를 따라 사용 환경이 올바르게 설정되었는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="666ce-134">If these steps do not work, then make sure that your environment has been properly set up, using the following steps.</span></span>  
>   
>  1.  <span data-ttu-id="666ce-135">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="666ce-135">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
> 2.  <span data-ttu-id="666ce-136">지침에 따라 솔루션을 빌드하려면 [Windows Communication Foundation 샘플 빌드](../../../../docs/framework/wcf/samples/building-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="666ce-136">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
> 3.  <span data-ttu-id="666ce-137">지침에 따라 단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="666ce-137">To run the sample in a single or multiple computer configurations, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="666ce-138">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="666ce-138">The samples may already be installed on your machine.</span></span> <span data-ttu-id="666ce-139">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="666ce-139">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="666ce-140">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="666ce-140">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="666ce-141">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="666ce-141">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\StandardEndpoints`  
  
## <a name="see-also"></a><span data-ttu-id="666ce-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="666ce-142">See Also</span></span>
