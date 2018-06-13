---
title: WMI Provider
ms.date: 03/30/2017
ms.assetid: 462f0db3-f4a4-4a4b-ac26-41fc25c670a4
ms.openlocfilehash: d135466c402fa21b6a1b11f208ca900f58748bdb
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33807308"
---
# <a name="wmi-provider"></a><span data-ttu-id="b3801-102">WMI Provider</span><span class="sxs-lookup"><span data-stu-id="b3801-102">WMI Provider</span></span>
<span data-ttu-id="b3801-103">이 샘플에서는 WCF에 포함 된 Windows Management Instrumentation (WMI) 공급자를 사용 하 여 런타임에 Windows Communication Foundation (WCF) 서비스에서 데이터를 수집 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b3801-103">This sample demonstrates how to gather data from Windows Communication Foundation (WCF) services at runtime by using the Windows Management Instrumentation (WMI) provider that is built into WCF.</span></span> <span data-ttu-id="b3801-104">또한 사용자 정의 WMI 개체를 서비스에 추가하는 방법도 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b3801-104">Also, this sample demonstrates how to add a user-defined WMI object to a service.</span></span> <span data-ttu-id="b3801-105">이 샘플에 대 한 WMI 공급자를 활성화는 [시작](../../../../docs/framework/wcf/samples/getting-started-sample.md) 에서 데이터를 수집 하는 방법을 보여 줍니다는 `ICalculator` 런타임에 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="b3801-105">The sample activates the WMI provider for the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) and demonstrates how to gather data from the `ICalculator` service at runtime.</span></span>  
  
 <span data-ttu-id="b3801-106">WMI는 Microsoft에서 구현한 WBEM(Web-Based Enterprise Management) 표준입니다.</span><span class="sxs-lookup"><span data-stu-id="b3801-106">WMI is Microsoft's implementation of the Web-Based Enterprise Management (WBEM) standard.</span></span> <span data-ttu-id="b3801-107">WMI SDK에 대 한 자세한 내용은 참조 [Windows Management Instrumentation](https://msdn.microsoft.com/library/aa394582.aspx)합니다.</span><span class="sxs-lookup"><span data-stu-id="b3801-107">For more information about the WMI SDK, see [Windows Management Instrumentation](https://msdn.microsoft.com/library/aa394582.aspx).</span></span> <span data-ttu-id="b3801-108">WBEM은 응용 프로그램에서 외부 관리 도구에 관리 계측을 노출하는 방법을 지정하는 산업 표준입니다.</span><span class="sxs-lookup"><span data-stu-id="b3801-108">WBEM is an industry standard for how applications expose management instrumentation to external management tools.</span></span>  
  
 <span data-ttu-id="b3801-109">WCF는 WMI 공급자를 WBEM 호환 인터페이스를 통해 런타임으로 계측을 노출 하는 구성 요소를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3801-109">WCF implements a WMI provider, a component that exposes instrumentation at runtime through a WBEM-compatible interface.</span></span> <span data-ttu-id="b3801-110">관리 도구는 런타임에 인터페이스를 통해 서비스에 연결될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3801-110">Management tools can connect to the services through the interface at runtime.</span></span> <span data-ttu-id="b3801-111">WCF는 서비스 주소, 바인딩, 동작 및 수신기와 같은 특성을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="b3801-111">WCF exposes attributes of services such as addresses, bindings, behaviors, and listeners.</span></span>  
  
 <span data-ttu-id="b3801-112">기본 제공 WMI 공급자는 응용 프로그램의 구성 파일에서 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="b3801-112">The built-in WMI provider is activated in the configuration file of the application.</span></span> <span data-ttu-id="b3801-113">이렇게는 `wmiProviderEnabled` 특성에는 [ \<진단 >](../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md) 에 [ \<system.serviceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) 섹션에서 다음 샘플에 나와 있는 것 처럼 구성:</span><span class="sxs-lookup"><span data-stu-id="b3801-113">This is done through the `wmiProviderEnabled` attribute of the [\<diagnostics>](../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md) in the [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) section, as shown in the following sample configuration:</span></span>  
  
```xml  
<system.serviceModel>  
    ...  
    <diagnostics wmiProviderEnabled="true" />  
    ...  
</system.serviceModel>  
```  
  
 <span data-ttu-id="b3801-114">이 구성 항목은 WMI 인터페이스를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="b3801-114">This configuration entry exposes a WMI interface.</span></span> <span data-ttu-id="b3801-115">관리 응용 프로그램이 이 인터페이스를 통해 연결하여 응용 프로그램의 관리 계측에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3801-115">Management applications can now connect through this interface and access the management instrumentation of the application.</span></span>  
  
## <a name="custom-wmi-object"></a><span data-ttu-id="b3801-116">사용자 지정 WMI 개체</span><span class="sxs-lookup"><span data-stu-id="b3801-116">Custom WMI Object</span></span>  
 <span data-ttu-id="b3801-117">서비스에 WMI 개체를 추가하면 기본 제공 WMI 공급자 정보와 함께 사용자 정의 정보를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3801-117">Adding WMI objects to a service makes it possible to reveal user-defined information along with the built-in WMI provider information.</span></span> <span data-ttu-id="b3801-118">그러려면 Installutil.exe 응용 프로그램을 사용하여 WMI에 서비스의 스키마를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="b3801-118">This is accomplished by publishing the schema of the service to WMI by using the Installutil.exe application.</span></span> <span data-ttu-id="b3801-119">이 작업을 수행하기 위한 지침과 자세한 설명은 항목 끝 부분에 있는 설치 지침을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b3801-119">Instructions to accomplish this, along with more details can be found in the setup instructions at the end of the topic.</span></span>  
  
## <a name="accessing-wmi-information"></a><span data-ttu-id="b3801-120">WMI 정보 액세스</span><span class="sxs-lookup"><span data-stu-id="b3801-120">Accessing WMI Information</span></span>  
 <span data-ttu-id="b3801-121">다양한 방식으로 WMI 데이터에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3801-121">WMI data can be accessed many different ways.</span></span> <span data-ttu-id="b3801-122">스크립트, Visual Basic 응용 프로그램, c + + 응용 프로그램에 대 한 WMI Api를 제공 하는 Microsoft 및 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] (http://msdn.microsoft.com/library/default.asp?url=/library/wmisdk/wmi/using_wmi.asp)합니다.</span><span class="sxs-lookup"><span data-stu-id="b3801-122">Microsoft provides WMI APIs for scripts, Visual Basic applications, C++ applications, and the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] (http://msdn.microsoft.com/library/default.asp?url=/library/wmisdk/wmi/using_wmi.asp).</span></span>  
  
 <span data-ttu-id="b3801-123">이 샘플에서는 두 개의 Java 스크립트를 사용합니다. 하나는 컴퓨터에서 실행 중인 서비스를 속성과 함께 나열하고, 다른 하나는 사용자 정의 WMI 데이터를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="b3801-123">This sample uses two Java scripts: one to enumerate services running on the computer along with some of their properties and the second to view user-defined WMI data.</span></span> <span data-ttu-id="b3801-124">스크립트에서는 WMI 공급자에 대한 연결을 열고, 데이터를 구문 분석하고, 수집된 데이터를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="b3801-124">The script opens a connection to the WMI provider, parses data, and displays the data gathered.</span></span>  
  
 <span data-ttu-id="b3801-125">WCF 서비스의 실행 중인 인스턴스를 만들기 위한 샘플을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3801-125">Start the sample to create a running instance of a WCF service.</span></span> <span data-ttu-id="b3801-126">서비스가 실행 중인 동안 명령 프롬프트에서 다음 명령을 사용하여 각 Java 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b3801-126">While the service is running, run each Java script by using the following command at the command prompt:</span></span>  
  
```  
cscript EnumerateServices.js  
```  
  
 <span data-ttu-id="b3801-127">스크립트에서는 서비스에 포함된 계측에 액세스하여 다음 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="b3801-127">The script accesses the instrumentation contained in the service and produces the following output:</span></span>  
  
```  
Microsoft (R) Windows Script Host Version 5.6  
Copyright © Microsoft Corporation 1996-2001. All rights reserved.  
  
1 service(s) found.  
|-PID:           5776  
|-DistinguishedName:  CalculatorService@http://localhost/ServiceModelSamples/service.svc  
|-Endpoints:     1 endpoints  
  |-CalculatorService.ICalculator@http://localhost/ServiceModelSamples/service.svc  
    |-Address:                        http://localhost/ServiceModelSamples/service.svc  
    |-CounterInstanceName:  
    |-AddressHeaders:                 0  
    |-ContractType:                   Contract.Name='ICalculator'  
    |-BindingElements:                4 bindings  
      |-BindingElements[0]  
        |-Type:                       TransactionFlowBindingElement  
      |-BindingElements[1]  
        |-Type:                       SymmetricSecurityBindingElement  
      |-BindingElements[2]  
        |-Type:                       TextMessageEncodingBindingElement  
        |-MaxReadPoolSize:            64  
        |-MaxWritePoolSize:           16  
      |-BindingElements[3]  
        |-Type:                       HttpTransportBindingElement  
        |-ManualAddressing:           false  
        |-MaxBufferSize:              65536  
        |-AllowCookies:               false  
        |-AuthenticationScheme:       Anonymous  
        |-BypassProxyOnLocal:         false  
        |-HostNameComparisonMode:     StrongWildcard  
        |-ProxyAddress:               null  
        |-ProxyAuthenticationScheme:  Anonymous  
        |-Realm:  
        |-TransferMode:               Buffered  
        |-UseDefaultWebProxy:         true  
|-Behaviors:     5 behaviors  
      |-Behavior[0]  
      |-Type:                       ServiceBehaviorAttribute  
        |-AddressFilterMode:               Exact  
        |-AutomaticSessionShutdown:        true  
        |-ConcurrencyMode:                 Single  
        |-IncludeExceptionDetailInFaults:  false  
        |-InstanceContextMode:             PerSession  
        |-TransactionIsolationLevel:       Unspecified  
        |-TransactionTimeout:              null  
        |-ValidateMustUnderstand:          true  
      |-Behavior[1]  
      |-Type:                       AspNetCompatibilityRequirementsAttribute  
      |-Behavior[2]  
      |-Type:                       ServiceDebugBehavior  
      |-Behavior[3]  
      |-Type:                       ServiceAuthorizationBehavior  
      |-Behavior[4]  
      |-Type:                       Behavior  
```  
  
 <span data-ttu-id="b3801-128">다음으로 두 번째 Java Script를 실행하여 사용자 정의 WMI 데이터를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="b3801-128">Next, run the second Java Script to display the user-defined WMI data:</span></span>  
  
```  
cscript EnumerateCustomObjects.js  
```  
  
 <span data-ttu-id="b3801-129">스크립트에서는 서비스에 포함된 사용자 정의 계측에 액세스하여 다음 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="b3801-129">The script accesses the user-defined instrumentation contained in the services and produces the following output:</span></span>  
  
```  
1 WMIObject(s) found.  
|-PID:           30285bfd-9d66-4c4e-9be2-310499c5cef5  
|-InstanceId:    3839  
|-WMIInfo:       User Defined WMI Information.  
```  
  
 <span data-ttu-id="b3801-130">컴퓨터에서 단일 서비스가 실행되고 있다는 것이 출력에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3801-130">The output shows that there is a single service running on the computer.</span></span> <span data-ttu-id="b3801-131">서비스에서는 `ICalculator` 계약을 구현하는 끝점 하나를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="b3801-131">The service exposes one endpoint that implements the `ICalculator` contract.</span></span> <span data-ttu-id="b3801-132">끝점에서 구현하는 동작 및 바인딩 설정은 메시징 스택에 있는 개별 요소의 합으로 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3801-132">The settings of the behavior and binding that are implemented by the endpoint are listed as the sum of individual elements of the messaging stack.</span></span>  
  
 <span data-ttu-id="b3801-133">WMI는 WCF 인프라의 관리 계측을 노출 하는 데 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b3801-133">WMI is not limited to exposing the management instrumentation of the WCF infrastructure.</span></span> <span data-ttu-id="b3801-134">같은 메커니즘을 통해 자체 도메인별 데이터 항목을 노출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3801-134">The application can expose its own domain-specific data items through the same mechanism.</span></span> <span data-ttu-id="b3801-135">WMI는 웹 서비스의 검사 및 제어를 위한 통합 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="b3801-135">WMI is a unified mechanism for inspection and control of a Web service.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="b3801-136">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="b3801-136">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="b3801-137">수행 했는지 확인는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b3801-137">Ensure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="b3801-138">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="b3801-138">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="b3801-139">호스팅 디렉터리에 있는 service.dll 파일에서 InstallUtil.exe(기본 위치는 "%WINDIR%\Microsoft.NET\Framework\v4.0.30319")를 실행하여 WMI에 서비스 스키마를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="b3801-139">Publish the services schema to WMI by running the InstallUtil.exe (the default locations for InstallUtil.exe is "%WINDIR%\Microsoft.NET\Framework\v4.0.30319") on the service.dll file in the hosting directory.</span></span> <span data-ttu-id="b3801-140">이 단계는 service.dll 파일이 수정된 경우에만 수행되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3801-140">This step only needs to be executed when changes have been made to the service.dll file.</span></span> <span data-ttu-id="b3801-141">자세한 내용은에서 응용 프로그램을 계측 하 여 관리 정보 제공을 참조 하십시오.: http://msdn2.microsoft.com/library/ms186147.aspx "어떻게를:: 게시의 체계를 WMI에 대 한 계측 된 응용 프로그램" 섹션에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3801-141">For more information, see Providing Management Information by Instrumenting Applications at: http://msdn2.microsoft.com/library/ms186147.aspx in the "How To: Publish the Scheme to WMI for an Instrumented Application" section.</span></span>  
  
4.  <span data-ttu-id="b3801-142">지침에 따라 단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b3801-142">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b3801-143">"%WINDIR%\ 실행 되도록 할 수 ASP.NET 설치 후 WCF를 설치한 경우 Microsoft.Net\Framework\v3.0\Windows Communication Foundation\servicemodelreg.exe "-r-x WMI 개체를 게시 하는 ASPNET 계정 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3801-143">If you installed WCF after installing ASP.NET, you may need to run "%WINDIR%\ Microsoft.Net\Framework\v3.0\Windows Communication Foundation\servicemodelreg.exe " -r -x to give the ASPNET account permission to publish WMI objects.</span></span>  
  
5.  <span data-ttu-id="b3801-144">`cscript EnumerateServices.js` 또는 `cscript EnumerateCustomObjects.js` 명령을 사용하여 WMI를 통해 표시된 샘플의 데이터를 봅니다.</span><span class="sxs-lookup"><span data-stu-id="b3801-144">View data from the sample surfaced through WMI by using the commands: `cscript EnumerateServices.js` or `cscript EnumerateCustomObjects.js`.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b3801-145">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3801-145">The samples may already be installed on your computer.</span></span> <span data-ttu-id="b3801-146">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="b3801-146">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="b3801-147">이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="b3801-147">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b3801-148">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3801-148">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\WMIProvider`  
  
## <a name="see-also"></a><span data-ttu-id="b3801-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b3801-149">See Also</span></span>  
 [<span data-ttu-id="b3801-150">AppFabric 모니터링 샘플</span><span class="sxs-lookup"><span data-stu-id="b3801-150">AppFabric Monitoring Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193959)
