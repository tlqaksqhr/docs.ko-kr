---
title: 사용자 지정 서비스 호스트
ms.date: 03/30/2017
ms.assetid: fe16ff50-7156-4499-9c32-13d8a79dc100
ms.openlocfilehash: c02ceb114a5346ea2a851f711f1ab9b50373cb75
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33806798"
---
# <a name="custom-service-host"></a><span data-ttu-id="9ec76-102">사용자 지정 서비스 호스트</span><span class="sxs-lookup"><span data-stu-id="9ec76-102">Custom Service Host</span></span>
<span data-ttu-id="9ec76-103">이 샘플에서는 <xref:System.ServiceModel.ServiceHost> 클래스의 사용자 지정 파생 항목을 사용하여 서비스의 런타임 동작을 변경하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9ec76-103">This sample demonstrates how to use a custom derivative of the <xref:System.ServiceModel.ServiceHost> class to alter the run-time behavior of a service.</span></span> <span data-ttu-id="9ec76-104">이 접근 방식을 사용하면 일반적인 방법으로 여러 서비스를 구성하는 대신 재사용 가능한 대체 방법이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ec76-104">This approach provides a reusable alternative to configuring a large number of services in a common way.</span></span> <span data-ttu-id="9ec76-105">또한 샘플에서는 <xref:System.ServiceModel.Activation.ServiceHostFactory> 클래스를 사용하여 IIS(인터넷 정보 서비스) 또는 WAS(Windows Process Activation Service) 호스팅 환경에서 사용자 지정 ServiceHost를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9ec76-105">The sample also demonstrates how to use the <xref:System.ServiceModel.Activation.ServiceHostFactory> class to use a custom ServiceHost in the Internet Information Services (IIS) or Windows Process Activation Service (WAS) hosting environment.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9ec76-106">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ec76-106">The samples may already be installed on your machine.</span></span> <span data-ttu-id="9ec76-107">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="9ec76-107">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="9ec76-108">이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="9ec76-108">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="9ec76-109">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ec76-109">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Hosting\CustomServiceHost`  
  
## <a name="about-the-scenario"></a><span data-ttu-id="9ec76-110">시나리오 정보</span><span class="sxs-lookup"><span data-stu-id="9ec76-110">About the Scenario</span></span>  
 <span data-ttu-id="9ec76-111">Windows Communication Foundation (WCF) 서비스에 대 한 기본 구성으로 잠재적으로 중요 한 서비스 메타 데이터가 실수로 공개를 방지 하려면 메타 데이터 게시를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ec76-111">To prevent unintentional disclosure of potentially sensitive service metadata, the default configuration for Windows Communication Foundation (WCF) services disables metadata publishing.</span></span> <span data-ttu-id="9ec76-112">이 동작은 기본적으로 안전하지만 구성에서 서비스의 메타데이터 게시 동작이 명시적으로 사용하도록 설정되어 있지 않은 경우 Svcutil.exe 등의 메타데이터 가져오기 도구를 사용하여 서비스를 호출하는 데 필요한 클라이언트 코드를 생성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9ec76-112">This behavior is secure by default, but also means that you cannot use a metadata import tool (such as Svcutil.exe) to generate the client code required to call the service unless the service’s metadata publishing behavior is explicitly enabled in configuration.</span></span>  
  
 <span data-ttu-id="9ec76-113">여러 서비스에 메타데이터 게시를 사용하도록 설정하면 각각의 개별 서비스에 동일한 구성 요소가 추가되어 기본적으로 동일한 구성 정보가 많이 생성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ec76-113">Enabling metadata publishing for a large number of services involves adding the same configuration elements to each individual service, which results in a large amount of configuration information that is essentially the same.</span></span> <span data-ttu-id="9ec76-114">각 서비스를 개별적으로 구성하는 대신 메타데이터 게시를 한 번 사용한 다음 여러 가지 다른 서비스에서 해당 코드를 다시 사용하도록 하는 명령 코드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ec76-114">As an alternative to configuring each service individually, it is possible to write the imperative code that enables metadata publishing once and then reuse that code across several different services.</span></span> <span data-ttu-id="9ec76-115">이 작업은 새 클래스를 만들어 수행합니다. 새 클래스는 <xref:System.ServiceModel.ServiceHost>에서 파생되며 `ApplyConfiguration`() 메서드를 재정의하여 메타데이터 게시 동작을 명령적으로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9ec76-115">This is accomplished by creating a new class that derives from <xref:System.ServiceModel.ServiceHost> and overrides the `ApplyConfiguration`() method to imperatively add the metadata publishing behavior.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9ec76-116">쉽게 구별할 수 있도록 이 샘플에서는 보안이 설정되지 않은 메타데이터 게시 끝점을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9ec76-116">For clarity, this sample demonstrates how to create an unsecured metadata publishing endpoint.</span></span> <span data-ttu-id="9ec76-117">이러한 끝점은 인증되지 않은 익명의 소비자가 사용할 수 있으므로 이러한 끝점을 배포하기 전에 서비스의 메타데이터를 공개하는 것이 적절한지 주의를 기울여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ec76-117">Such endpoints are potentially available to anonymous unauthenticated consumers and care must be taken before deploying such endpoints to ensure that publicly disclosing a service’s metadata is appropriate.</span></span>  
  
## <a name="implementing-a-custom-servicehost"></a><span data-ttu-id="9ec76-118">사용자 지정 ServiceHost 구현</span><span class="sxs-lookup"><span data-stu-id="9ec76-118">Implementing a Custom ServiceHost</span></span>  
 <span data-ttu-id="9ec76-119"><xref:System.ServiceModel.ServiceHost> 클래스는 상속자가 서비스의 런타임 동작을 변경하기 위해 재정의할 수 있는 여러 가지 유용한 가상 메서드를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="9ec76-119">The <xref:System.ServiceModel.ServiceHost> class exposes several useful virtual methods that inheritors can override to alter the run-time behavior of a service.</span></span> <span data-ttu-id="9ec76-120">예를 들어, `ApplyConfiguration`() 메서드는 구성 저장소에서 서비스 구성 정보를 읽고 그에 따라 호스트의 <xref:System.ServiceModel.Description.ServiceDescription>을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="9ec76-120">For example, the `ApplyConfiguration`() method reads service configuration information from the configuration store and alters the host's <xref:System.ServiceModel.Description.ServiceDescription> accordingly.</span></span> <span data-ttu-id="9ec76-121">기본 구현에서는 응용 프로그램의 구성 파일에서 구성을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="9ec76-121">The default implementation reads configuration from the application’s configuration file.</span></span> <span data-ttu-id="9ec76-122">사용자 지정 구현에서는 명령 코드를 사용하여 `ApplyConfiguration`을 추가로 변경하거나 기본 구성 저장소를 완전히 바꾸도록 <xref:System.ServiceModel.Description.ServiceDescription>()을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ec76-122">Custom implementations can override `ApplyConfiguration`() to further alter the <xref:System.ServiceModel.Description.ServiceDescription> using imperative code or even replace the default configuration store entirely.</span></span> <span data-ttu-id="9ec76-123">예를 들어, 응용 프로그램의 구성 파일 대신 데이터베이스에서 서비스의 끝점 구성을 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ec76-123">For example, to read a service’s endpoint configuration from a database instead of the application’s configuration file.</span></span>  
  
 <span data-ttu-id="9ec76-124">이 샘플에서는 메타데이터 게시를 사용하도록 설정하는 ServiceMetadataBehavior가 서비스의 구성 파일에 명시적으로 추가되지 않은 경우에도 이 동작을 추가하는 사용자 지정 ServiceHost를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="9ec76-124">In this sample, we want to build a custom ServiceHost that adds the ServiceMetadataBehavior, (which enables metadata publishing), even if this behavior is not explicitly added in the service’s configuration file.</span></span> <span data-ttu-id="9ec76-125"><xref:System.ServiceModel.ServiceHost>에서 상속되며 `ApplyConfiguration`()을 재정의하는 새 클래스를 만들어 이 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="9ec76-125">To accomplish this, we create a new class that inherits from <xref:System.ServiceModel.ServiceHost> and overrides `ApplyConfiguration`().</span></span>  
  
```  
class SelfDescribingServiceHost : ServiceHost  
{  
    public SelfDescribingServiceHost(Type serviceType, params Uri[] baseAddresses)  
        : base(serviceType, baseAddresses) { }  
  
    //Overriding ApplyConfiguration() allows us to   
    //alter the ServiceDescription prior to opening  
    //the service host.   
    protected override void ApplyConfiguration()  
    {  
        //First, we call base.ApplyConfiguration()  
        //to read any configuration that was provided for  
        //the service we're hosting. After this call,  
        //this.Description describes the service  
        //as it was configured.  
        base.ApplyConfiguration();       
  
        //(rest of implementation elided for clarity)  
    }  
}  
```  
  
 <span data-ttu-id="9ec76-126">응용 프로그램의 구성 파일에 제공된 구성을 무시하지 않으므로 `ApplyConfiguration`()을 재정의하는 경우 제일 먼저 기본 구현이 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ec76-126">Because we do not want to ignore any configuration that has been provided in the application’s configuration file, the first thing our override of `ApplyConfiguration`() does is call the base implementation.</span></span> <span data-ttu-id="9ec76-127">이 메서드가 완료되면 다음 명령 코드를 사용하여 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>를 명령적으로 설명에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ec76-127">Once this method completes, we can imperatively add the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> to the description using the following imperative code.</span></span>  
  
```  
ServiceMetadataBehavior mexBehavior = this.Description.Behaviors.Find<ServiceMetadataBehavior>();  
if (mexBehavior == null)  
{  
    mexBehavior = new ServiceMetadataBehavior();  
    this.Description.Behaviors.Add(mexBehavior);  
}  
else  
{  
    //Metadata behavior has already been configured,   
    //so we do not have any work to do.  
    return;  
}  
```  
  
 <span data-ttu-id="9ec76-128">마지막으로 `ApplyConfiguration`()을 재정의하기 위해 기본 메타데이터 끝점을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9ec76-128">The last thing our `ApplyConfiguration`() override must do is add the default metadata endpoint.</span></span> <span data-ttu-id="9ec76-129">규칙에 따라 서비스 호스트의 BaseAddresses 컬렉션에 각 URI마다 메타데이터 끝점이 하나씩 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ec76-129">By convention, one metadata endpoint is created for each URI in the service host’s BaseAddresses collection.</span></span>  
  
```  
//Add a metadata endpoint at each base address  
//using the "/mex" addressing convention  
foreach (Uri baseAddress in this.BaseAddresses)  
{  
    if (baseAddress.Scheme == Uri.UriSchemeHttp)  
    {  
        mexBehavior.HttpGetEnabled = true;  
        this.AddServiceEndpoint(ServiceMetadataBehavior.MexContractName,  
                                MetadataExchangeBindings.CreateMexHttpBinding(),  
                                "mex");  
    }  
    else if (baseAddress.Scheme == Uri.UriSchemeHttps)  
    {  
        mexBehavior.HttpsGetEnabled = true;  
        this.AddServiceEndpoint(ServiceMetadataBehavior.MexContractName,  
                                MetadataExchangeBindings.CreateMexHttpsBinding(),  
                                "mex");  
    }  
    else if (baseAddress.Scheme == Uri.UriSchemeNetPipe)  
    {  
        this.AddServiceEndpoint(ServiceMetadataBehavior.MexContractName,  
                                MetadataExchangeBindings.CreateMexNamedPipeBinding(),  
                                "mex");  
    }  
    else if (baseAddress.Scheme == Uri.UriSchemeNetTcp)  
    {  
        this.AddServiceEndpoint(ServiceMetadataBehavior.MexContractName,  
                                MetadataExchangeBindings.CreateMexTcpBinding(),  
                                "mex");  
    }  
}  
```  
  
## <a name="using-a-custom-servicehost-in-self-host"></a><span data-ttu-id="9ec76-130">자체 호스팅 환경에서 사용자 지정 ServiceHost 사용</span><span class="sxs-lookup"><span data-stu-id="9ec76-130">Using a custom ServiceHost in self-host</span></span>  
 <span data-ttu-id="9ec76-131">이제 사용자 지정 ServiceHost 구현을 완료했으므로 `SelfDescribingServiceHost`의 인스턴스 내부에 해당 서비스를 호스트하여 모든 서비스에 메타데이터 게시 동작을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ec76-131">Now that we have completed our custom ServiceHost implementation, we can use it to add metadata publishing behavior to any service by hosting that service inside of an instance of our `SelfDescribingServiceHost`.</span></span> <span data-ttu-id="9ec76-132">다음 코드에서는 자체 호스팅 시나리오에서 해당 서비스를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9ec76-132">The following code shows how to use it in the self-host scenario.</span></span>  
  
```  
SelfDescribingServiceHost host =   
         new SelfDescribingServiceHost( typeof( Calculator ) );  
host.Open();  
```  
  
 <span data-ttu-id="9ec76-133">사용자 지정 호스트는 기본 <xref:System.ServiceModel.ServiceHost> 클래스를 사용하여 서비스를 호스트한 경우처럼 응용 프로그램 구성 파일에서 서비스의 끝점 구성을 계속 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="9ec76-133">Our custom host still reads the service’s endpoint configuration from the application’s configuration file, just as if we had used the default <xref:System.ServiceModel.ServiceHost> class to host the service.</span></span> <span data-ttu-id="9ec76-134">그러나 사용자 지정 호스트의 내부에서 메타데이터 게시를 사용하도록 설정하는 논리를 추가했으므로 구성에서 메타데이터 게시 동작을 더 이상 명시적으로 사용하도록 설정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9ec76-134">However, because we added the logic to enable metadata publishing inside of our custom host, we no longer must explicitly enable the metadata publishing behavior in configuration.</span></span> <span data-ttu-id="9ec76-135">이 접근 방식을 사용하면 여러 서비스가 포함된 응용 프로그램을 빌드할 때 같은 구성 요소를 반복해서 작성하지 않고도 각 서비스에서 메타데이터 게시를 사용하도록 설정할 수 있다는 장점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ec76-135">This approach has a distinct advantage when you are building an application that contains several services and you want to enable metadata publishing on each of them without writing the same configuration elements over and over.</span></span>  
  
## <a name="using-a-custom-servicehost-in-iis-or-was"></a><span data-ttu-id="9ec76-136">IIS 또는 WAS 환경에서 사용자 지정 ServiceHost 사용</span><span class="sxs-lookup"><span data-stu-id="9ec76-136">Using a Custom ServiceHost in IIS or WAS</span></span>  
 <span data-ttu-id="9ec76-137">자체 호스팅 시나리오에서는 결국 응용 프로그램 코드를 통해 서비스 호스트 인스턴스를 만들고 여는 작업을 수행하므로 사용자 지정 서비스 호스트 사용이 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="9ec76-137">Using a custom service host in self-host scenarios is straightforward, because it is your application code that is ultimately responsible for creating and opening the service host instance.</span></span> <span data-ttu-id="9ec76-138">하지만 IIS 또는 WAS 호스팅 환경 WCF 인프라가 동적으로 인스턴스화합니다 들어오는 메시지에 대 한 응답으로 서비스의 호스트를입니다.</span><span class="sxs-lookup"><span data-stu-id="9ec76-138">In the IIS or WAS hosting environment, however, the WCF infrastructure is dynamically instantiating your service’s host in response to incoming messages.</span></span> <span data-ttu-id="9ec76-139">이 호스팅 환경에서 사용자 지정 서비스 호스트를 사용할 수도 있지만 ServiceHostFactory 형식의 추가 코드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9ec76-139">Custom service hosts can also be used in this hosting environment, but they require some additional code in the form of a ServiceHostFactory.</span></span> <span data-ttu-id="9ec76-140">다음 코드에서는 사용자 지정 <xref:System.ServiceModel.Activation.ServiceHostFactory>의 인스턴스를 반환하는 `SelfDescribingServiceHost`의 파생 항목을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9ec76-140">The following code shows a derivative of <xref:System.ServiceModel.Activation.ServiceHostFactory> that returns instances of our custom `SelfDescribingServiceHost`.</span></span>  
  
```  
public class SelfDescribingServiceHostFactory : ServiceHostFactory  
{  
    protected override ServiceHost CreateServiceHost(Type serviceType,   
     Uri[] baseAddresses)  
    {  
        //All the custom factory does is return a new instance  
        //of our custom host class. The bulk of the custom logic should  
        //live in the custom host (as opposed to the factory)   
        //for maximum  
        //reuse value outside of the IIS/WAS hosting environment.  
        return new SelfDescribingServiceHost(serviceType,     
                                             baseAddresses);  
    }  
}  
```  
  
 <span data-ttu-id="9ec76-141">이 샘플에서 볼 수 있듯이 사용자 지정 ServiceHostFactory 구현은 매우 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="9ec76-141">As you can see, implementing a custom ServiceHostFactory is very straightforward.</span></span> <span data-ttu-id="9ec76-142">모든 사용자 지정 논리는 ServiceHost 구현 내에 있고 팩터리는 파생 클래스의 인스턴스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9ec76-142">All of the custom logic resides inside of the ServiceHost implementation; the factory returns an instance of the derived class.</span></span>  
  
 <span data-ttu-id="9ec76-143">서비스 구현에서 사용자 지정 팩터리를 사용하려면 서비스의 .svc 파일에 일부 메타데이터를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ec76-143">To use a custom factory with a service implementation, we must add some additional metadata to the service’s .svc file.</span></span>  
  
```  
<%@ServiceHost Service="Microsoft.ServiceModel.Samples.CalculatorService"  
               Factory="Microsoft.ServiceModel.Samples.SelfDescribingServiceHostFactory"  
               language=c# Debug="true" %>  
```  
  
 <span data-ttu-id="9ec76-144">여기서는 `Factory` 지시문에 추가 `@ServiceHost` 특성을 추가하고 사용자 지정 팩터리의 CLR 형식 이름을 특성의 값으로 전달했습니다.</span><span class="sxs-lookup"><span data-stu-id="9ec76-144">Here we have added an additional `Factory` attribute to the `@ServiceHost` directive, and passed the CLR type name of our custom factory as the attribute’s value.</span></span> <span data-ttu-id="9ec76-145">WCF 호스팅 인프라 IIS 또는 WAS이이 서비스에 대 한 메시지를 받으면 먼저 ServiceHostFactory의 인스턴스를 만든 하 고 다음 호출 하 여 서비스 호스트 자체를 인스턴스화합니다 `ServiceHostFactory.CreateServiceHost()`합니다.</span><span class="sxs-lookup"><span data-stu-id="9ec76-145">When IIS or WAS receives a message for this service, the WCF hosting infrastructure first creates an instance of the ServiceHostFactory and then instantiate the service host itself by calling `ServiceHostFactory.CreateServiceHost()`.</span></span>  
  
## <a name="running-the-sample"></a><span data-ttu-id="9ec76-146">샘플 실행</span><span class="sxs-lookup"><span data-stu-id="9ec76-146">Running the Sample</span></span>  
 <span data-ttu-id="9ec76-147">이 샘플에서는 완전한 기능을 갖춘 클라이언트 및 서비스 구현을 제공하지만 샘플의 핵심은 사용자 지정 호스트를 사용하여 서비스의 런타임 동작을 변경하는 방법을 보여 주는 것이므로 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="9ec76-147">Although this sample does provide a fully-functional client and service implementation, the point of the sample is to illustrate how to alter a service’s run-time behavior by means of a custom host., do the following steps:</span></span>  
  
#### <a name="to-observe-the-effect-of-the-custom-host"></a><span data-ttu-id="9ec76-148">사용자 지정 호스트의 효과를 확인하려면</span><span class="sxs-lookup"><span data-stu-id="9ec76-148">To observe the effect of the custom host</span></span>  
  
1.  <span data-ttu-id="9ec76-149">서비스의 Web.config 파일을 열고 서비스에서 메타데이터를 사용하도록 명시적으로 설정하는 구성이 없는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9ec76-149">Open the service’s Web.config file and observe that there is no configuration explicitly enabling metadata for the service.</span></span>  
  
2.  <span data-ttu-id="9ec76-150">서비스의.svc 파일을 열고는 해당 @ServiceHost 지시문에 사용자 지정 ServiceHostFactory의 이름을 지정 하는 Factory 특성이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ec76-150">Open the service’s .svc file and observe that its @ServiceHost directive contains a Factory attribute that specifies the name of a custom ServiceHostFactory.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="9ec76-151">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="9ec76-151">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="9ec76-152">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9ec76-152">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="9ec76-153">지침에 따라 솔루션을 빌드하려면 [Windows Communication Foundation 샘플 빌드](../../../../docs/framework/wcf/samples/building-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9ec76-153">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="9ec76-154">솔루션을 빌드한 후 Setup.bat를 실행하여 [!INCLUDE[iisver](../../../../includes/iisver-md.md)]에 ServiceModelSamples 응용 프로그램을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="9ec76-154">After the solution has been built, run Setup.bat to set up the ServiceModelSamples Application in [!INCLUDE[iisver](../../../../includes/iisver-md.md)].</span></span> <span data-ttu-id="9ec76-155">이제 ServiceModelSamples 디렉터리가 [!INCLUDE[iisver](../../../../includes/iisver-md.md)] 응용 프로그램으로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="9ec76-155">The ServiceModelSamples directory should now appear as an [!INCLUDE[iisver](../../../../includes/iisver-md.md)] Application.</span></span>  
  
4.  <span data-ttu-id="9ec76-156">지침에 따라 단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9ec76-156">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
5.  <span data-ttu-id="9ec76-157">[!INCLUDE[iisver](../../../../includes/iisver-md.md)] 응용 프로그램을 제거하려면 Cleanup.bat를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9ec76-157">To remove the [!INCLUDE[iisver](../../../../includes/iisver-md.md)] application, run Cleanup.bat.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ec76-158">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9ec76-158">See Also</span></span>  
 [<span data-ttu-id="9ec76-159">방법: IIS에서 WCF 서비스 호스트</span><span class="sxs-lookup"><span data-stu-id="9ec76-159">How to: Host a WCF Service in IIS</span></span>](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md)
