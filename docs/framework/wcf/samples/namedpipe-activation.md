---
title: NamedPipe 활성화
ms.date: 03/30/2017
ms.assetid: f3c0437d-006c-442e-bfb0-6b29216e4e29
ms.openlocfilehash: 46b59dab0f67c66ca364d9e880ef519386d0df94
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33806385"
---
# <a name="namedpipe-activation"></a><span data-ttu-id="8f4af-102">NamedPipe 활성화</span><span class="sxs-lookup"><span data-stu-id="8f4af-102">NamedPipe Activation</span></span>
<span data-ttu-id="8f4af-103">이 샘플에서는 WAS(Windows Process Activation Service)를 사용하는 서비스를 호스트하여 이름 파이프를 통해 통신하는 서비스를 활성화하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8f4af-103">This sample demonstrates hosting a service that uses Windows Process Activation Service (WAS) to activate a service that communicates over names pipes.</span></span> <span data-ttu-id="8f4af-104">이 샘플에 따라는 [시작](../../../../docs/framework/wcf/samples/getting-started-sample.md) 으로 이루어지며 [!INCLUDE[wv](../../../../includes/wv-md.md)] 실행 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f4af-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) and requires [!INCLUDE[wv](../../../../includes/wv-md.md)] to run.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8f4af-105">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f4af-105">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8f4af-106">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f4af-106">The samples may already be installed on your computer.</span></span> <span data-ttu-id="8f4af-107">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="8f4af-107">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="8f4af-108">이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="8f4af-108">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="8f4af-109">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f4af-109">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WASHost\NamedPipeActivation`  
  
## <a name="sample-details"></a><span data-ttu-id="8f4af-110">샘플 세부 정보</span><span class="sxs-lookup"><span data-stu-id="8f4af-110">Sample Details</span></span>  
 <span data-ttu-id="8f4af-111">이 샘플은 WAS(Windows Process Activation Services)에 의해 활성화된 작업자 프로세스에서 호스트되는 서비스 라이브러리(.dll) 및 클라이언트 콘솔 프로그램(.exe)으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f4af-111">The sample consists of a client console program (.exe) and a service library (.dll) hosted in a worker process activated by the Windows Process Activation Services (WAS).</span></span> <span data-ttu-id="8f4af-112">콘솔 창에는 클라이언트 동작이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f4af-112">Client activity is visible in the console window.</span></span>  
  
 <span data-ttu-id="8f4af-113">이 서비스는 요청-회신 통신 패턴을 정의하는 계약을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="8f4af-113">The service implements a contract that defines a request-reply communication pattern.</span></span> <span data-ttu-id="8f4af-114">계약은 다음 샘플 코드처럼 수학 연산(더하기, 빼기, 곱하기 및 나누기)을 노출시키는 `ICalculator` 인터페이스에서 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f4af-114">The contract is defined by the `ICalculator` interface, which exposes math operations (Add, Subtract, Multiply, and Divide), as shown in the following sample code.</span></span>  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface ICalculator  
{  
    [OperationContract]  
    double Add(double n1, double n2);  
    [OperationContract]  
    double Subtract(double n1, double n2);  
    [OperationContract]  
    double Multiply(double n1, double n2);  
    [OperationContract]  
    double Divide(double n1, double n2);  
}  
```  
  
 <span data-ttu-id="8f4af-115">클라이언트에서는 지정된 수학 연산을 동기적으로 요청하고 서비스 구현에서는 계산을 통해 올바른 결과를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8f4af-115">The client makes synchronous requests to a given math operation and the service implementation calculates and returns the appropriate result.</span></span>  
  
```  
// Service class that implements the service contract.  
public class CalculatorService : ICalculator  
{  
    public double Add(double n1, double n2)  
    {  
        return n1 + n2;  
    }  
    public double Subtract(double n1, double n2)  
    {  
        return n1 - n2;  
    }  
    public double Multiply(double n1, double n2)  
    {  
        return n1 * n2;  
    }  
    public double Divide(double n1, double n2)  
    {  
        return n1 / n2;  
    }  
}  
```  
  
 <span data-ttu-id="8f4af-116">샘플에서는 보안 없이 수정된 `netNamedPipeBinding` 바인딩을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8f4af-116">The sample uses a modified `netNamedPipeBinding` binding with no security.</span></span> <span data-ttu-id="8f4af-117">클라이언트 및 서비스 구성 파일에 바인딩이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f4af-117">The binding is specified in the configuration files for the client and service.</span></span> <span data-ttu-id="8f4af-118">서비스의 바인딩 형식은 다음 샘플 구성과 같이 끝점 요소의 `binding` 특성에 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f4af-118">The binding type for the service is specified in the endpoint element’s `binding` attribute as shown in the following sample configuration.</span></span>  
  
 <span data-ttu-id="8f4af-119">보안이 설정된 명명된 파이프 바인딩을 사용하려면 서버의 보안 모드를 원하는 보안 설정으로 변경하고 클라이언트에서 svcutil.exe를 다시 실행하여 업데이트된 클라이언트 구성 파일을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8f4af-119">If you want use a secured named pipe binding, change the server's security mode to the desired security setting and run svcutil.exe again on the client to obtain an updated client configuration file.</span></span>  
  
```xml  
<system.serviceModel>  
        <services>  
            <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
               behaviorConfiguration="CalculatorServiceBehavior">  
  
        <!-- This endpoint is exposed at the base address provided by host: net.pipe://localhost/servicemodelsamples/service.svc  -->  
        <endpoint address=""   
                  binding="netNamedPipeBinding"  
                  bindingConfiguration="Binding1"   
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />  
        <!-- the mex endpoint is explosed at net.pipe://localhost/servicemodelsamples/service.svc/mex -->  
        <endpoint address="mex"  
                  binding="mexNamedPipeBinding"  
                  contract="IMetadataExchange" />  
      </service>  
        </services>      
        <bindings>  
            <netNamedPipeBinding>  
                <binding name="Binding1" >  
                    <security mode = "None">  
                    </security>  
                </binding >  
            </netNamedPipeBinding>  
        </bindings>  
  
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="CalculatorServiceBehavior">  
          <serviceMetadata />  
          <serviceDebug includeExceptionDetailInFaults="False" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  
  </system.serviceModel>  
```  
  
 <span data-ttu-id="8f4af-120">클라이언트의 끝점 정보는 다음 샘플 코드와 같이 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f4af-120">The client’s endpoint information is configured as shown in the following sample code.</span></span>  
  
```xml  
<system.serviceModel>  
  
    <client>  
      <endpoint name=""  
                          address="net.pipe://localhost/servicemodelsamples/service.svc"   
                          binding="netNamedPipeBinding"   
                          bindingConfiguration="Binding1"   
                          contract="Microsoft.ServiceModel.Samples.ICalculator" />  
    </client>  
  
    <bindings>  
  
      <!--  Following is the expanded configuration section for a NetNamedPipeBinding.  
            Each property is configured with the default value.   -->  
  
      <netNamedPipeBinding>  
        <binding name="Binding1"   
                         maxBufferSize="65536"  
                         maxConnections="10">  
          <security mode = "None">  
          </security>  
        </binding >  
  
      </netNamedPipeBinding>  
    </bindings>  
  
  </system.serviceModel>  
```  
  
 <span data-ttu-id="8f4af-121">샘플을 실행하면 작업 요청 및 응답이 클라이언트 콘솔 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f4af-121">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="8f4af-122">클라이언트를 종료하려면 클라이언트 창에서 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="8f4af-122">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="8f4af-123">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="8f4af-123">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="8f4af-124">[!INCLUDE[iisver](../../../../includes/iisver-md.md)]이 설치되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8f4af-124">Ensure that [!INCLUDE[iisver](../../../../includes/iisver-md.md)] is installed.</span></span> [!INCLUDE[iisver](../../../../includes/iisver-md.md)]<span data-ttu-id="8f4af-125">은 WAS 활성화에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8f4af-125"> is required for WAS activation.</span></span>  
  
2.  <span data-ttu-id="8f4af-126">수행 했는지 확인는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8f4af-126">Ensure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
     <span data-ttu-id="8f4af-127">또한 WCF NON-HTTP activation 구성 요소를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f4af-127">In addition, you must install the WCF non-HTTP activation components:</span></span>  
  
    1.  <span data-ttu-id="8f4af-128">**시작** 메뉴 선택 **제어판**합니다.</span><span class="sxs-lookup"><span data-stu-id="8f4af-128">From the **Start** menu, choose **Control Panel**.</span></span>  
  
    2.  <span data-ttu-id="8f4af-129">선택 **프로그램 및 기능**합니다.</span><span class="sxs-lookup"><span data-stu-id="8f4af-129">Select **Programs and Features**.</span></span>  
  
    3.  <span data-ttu-id="8f4af-130">클릭 **Windows 구성 요소를 켜거나 끄려면**합니다.</span><span class="sxs-lookup"><span data-stu-id="8f4af-130">Click **Turn Windows Components on or Off**.</span></span>  
  
    4.  <span data-ttu-id="8f4af-131">확장 된 **Microsoft.NET Framework 3.0** 노드와 검사는 **Windows Communication Foundation 비-HTTP 활성화** 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="8f4af-131">Expand the **Microsoft .NET Framework 3.0** node and check the **Windows Communication Foundation Non-HTTP Activation** feature.</span></span>  
  
3.  <span data-ttu-id="8f4af-132">명명된 파이프 활성화를 지원하도록 WAS(Windows Process Activation Service)를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="8f4af-132">Configure the Windows Process Activation Service (WAS) to support named pipe activation.</span></span>  
  
     <span data-ttu-id="8f4af-133">편의를 위해 다음 두 단계는 샘플 디렉터리에 있는 AddNetPipeSiteBinding.cmd라는 배치 파일에서 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="8f4af-133">As a convenience, the following two steps are implemented in a batch file called AddNetPipeSiteBinding.cmd located in the sample directory.</span></span>  
  
    1.  <span data-ttu-id="8f4af-134">net. pipe 활성화를 지원하려면 먼저 기본 웹 사이트를 net. pipe 프로토콜에 바인딩해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f4af-134">To support net.pipe activation, the default Web site must first be bound to the net.pipe protocol.</span></span> <span data-ttu-id="8f4af-135">이 작업은 IIS 7.0 관리 도구 집합과 함께 설치되는 appcmd.exe를 사용하여 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f4af-135">This can be done using appcmd.exe, which is installed with the IIS 7.0 management toolset.</span></span> <span data-ttu-id="8f4af-136">권한이 높은 명령 프롬프트에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8f4af-136">From an elevated (administrator) command prompt, run the following command.</span></span>  
  
        ```  
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"   
        -+bindings.[protocol='net.pipe',bindingInformation='*']  
        ```  
  
        > [!NOTE]
        >  <span data-ttu-id="8f4af-137">이 명령은 줄 바꿈 없이 한 줄로 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f4af-137">This command is a single line of text.</span></span>  
  
         <span data-ttu-id="8f4af-138">이 명령은 기본 웹 사이트에 net.pipe 사이트 바인딩을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8f4af-138">This command adds a net.pipe site binding to the default Web site.</span></span>  
  
    2.  <span data-ttu-id="8f4af-139">사이트 내의 모든 응용 프로그램에서 공통된 net.pipe 바인딩을 공유하지만 각 응용 프로그램에서 net.pipe 지원을 개별적으로 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f4af-139">Although all applications within a site share a common net.pipe binding, each application can enable net.pipe support individually.</span></span> <span data-ttu-id="8f4af-140">/servicemodelsamples 응용 프로그램에서 net.pipe를 사용하도록 설정하려면 권한이 높은 명령 프롬프트에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8f4af-140">To enable net.pipe for the /servicemodelsamples application, run the following command from an elevated command prompt.</span></span>  
  
        ```  
        %windir%\system32\inetsrv\appcmd.exe set app "Default Web Site/servicemodelsamples" /enabledProtocols:http,net.pipe  
        ```  
  
        > [!NOTE]
        >  <span data-ttu-id="8f4af-141">이 명령은 줄 바꿈 없이 한 줄로 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f4af-141">This command is a single line of text.</span></span>  
  
         <span data-ttu-id="8f4af-142">이 명령은 /servicemodelsamples 응용 프로그램에 모두 사용 하 여 액세스를 활성화 http://localhost/servicemodelsamples 및 net.tcp://localhost/servicemodelsamples 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f4af-142">This command enables the /servicemodelsamples application to be accessed using both http://localhost/servicemodelsamples and net.tcp://localhost/servicemodelsamples.</span></span>  
  
4.  <span data-ttu-id="8f4af-143">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="8f4af-143">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
5.  <span data-ttu-id="8f4af-144">이 샘플에 대해 추가한 net. pipe 사이트 바인딩을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8f4af-144">Remove the net.pipe site binding you added for this sample.</span></span>  
  
     <span data-ttu-id="8f4af-145">편의를 위해 다음 두 단계는 샘플 디렉터리에 있는 RemoveNetPipeSiteBinding.cmd라는 배치 파일에서 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="8f4af-145">As a convenience, the following two steps are implemented in a batch file called RemoveNetPipeSiteBinding.cmd located in the sample directory:</span></span>  
  
    1.  <span data-ttu-id="8f4af-146">권한이 높은 명령 프롬프트에서 다음 명령을 실행하여 사용된 프로토콜 목록에서 net.tcp를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8f4af-146">Remove net.tcp from the list of enabled protocols by running the following command from an elevated command prompt.</span></span>  
  
        ```  
        %windir%\system32\inetsrv\appcmd.exe set app "Default Web Site/servicemodelsamples" /enabledProtocols:http  
        ```  
  
        > [!NOTE]
        >  <span data-ttu-id="8f4af-147">이 명령은 줄 바꿈 없이 한 줄로 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f4af-147">This command must be entered as a single line of text.</span></span>  
  
    2.  <span data-ttu-id="8f4af-148">권한이 높은 명령 프롬프트에서 다음 명령을 실행하여 net.tcp 사이트 바인딩을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8f4af-148">Remove the net.tcp site binding by running the following command from an elevated command prompt.</span></span>  
  
        ```  
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site" --bindings.[protocol='net.pipe',bindingInformation='*']  
        ```  
  
        > [!NOTE]
        >  <span data-ttu-id="8f4af-149">이 명령은 줄 바꿈 없이 한 줄로 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f4af-149">This command must be typed in as a single line of text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f4af-150">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8f4af-150">See Also</span></span>  
 [<span data-ttu-id="8f4af-151">AppFabric 호스팅 및 지 속성 샘플</span><span class="sxs-lookup"><span data-stu-id="8f4af-151">AppFabric Hosting and Persistence Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193961)
