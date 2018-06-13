---
title: '방법: 관리되는 Windows 서비스에서 WCF 서비스 호스팅'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8e37363b-4dad-4fb6-907f-73c30fac1d9a
ms.openlocfilehash: c6c3e057fd07569d462f1bf25d1c283e42024a8b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33497219"
---
# <a name="how-to-host-a-wcf-service-in-a-managed-windows-service"></a><span data-ttu-id="f22d2-102">방법: 관리되는 Windows 서비스에서 WCF 서비스 호스팅</span><span class="sxs-lookup"><span data-stu-id="f22d2-102">How to: Host a WCF Service in a Managed Windows Service</span></span>
<span data-ttu-id="f22d2-103">이 항목에서는 Windows 서비스에서 호스팅하는 Windows Communication Foundation (WCF) 서비스를 만드는 데 필요한 기본 단계에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f22d2-103">This topic outlines the basic steps required to create a Windows Communication Foundation (WCF) service that is hosted by a Windows Service.</span></span> <span data-ttu-id="f22d2-104">관리 되는 Windows 서비스 호스팅 옵션을 활성화 메시지를 보안 환경에서는 인터넷 정보 서비스 (IIS) 외부에서 호스팅되는 장기 실행 WCF 서비스에서 사용할 수 있는 시나리오</span><span class="sxs-lookup"><span data-stu-id="f22d2-104">The scenario is enabled by the managed Windows service hosting option that is a long-running WCF service hosted outside of Internet Information Services (IIS) in a secure environment that is not message activated.</span></span> <span data-ttu-id="f22d2-105">서비스 수명은 대신 운영 체제에 의해 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="f22d2-105">The lifetime of the service is controlled instead by the operating system.</span></span> <span data-ttu-id="f22d2-106">모든 버전의 Windows에서 이 호스팅 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f22d2-106">This hosting option is available in all versions of Windows.</span></span>  
  
 <span data-ttu-id="f22d2-107">Windows 서비스는 MMC(Microsoft Management Console)의 Microsoft.ManagementConsole.SnapIn을 통해 관리되고 시스템 부팅 시 자동으로 시작되도록 구성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f22d2-107">Windows services can be managed with the Microsoft.ManagementConsole.SnapIn in Microsoft Management Console (MMC) and can be configured to start up automatically when the system boots up.</span></span> <span data-ttu-id="f22d2-108">이 호스팅 옵션은 서비스의 프로세스 수명은 Windows 서비스에 대 한 서비스 제어 관리자 (SCM)으로 제어 됩니다를 Windows 서비스로 관리 되는 WCF 서비스를 호스트 하는 응용 프로그램 도메인 (AppDomain) 등록으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f22d2-108">This hosting option consists of registering the application domain (AppDomain) that hosts a WCF service as a managed Windows service so that the process lifetime of the service is controlled by the Service Control Manager (SCM) for Windows services.</span></span>  
  
 <span data-ttu-id="f22d2-109">서비스 코드에는 서비스 계약에 대한 서비스 구현, Windows 서비스 클래스 및 설치 관리자 클래스가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f22d2-109">The service code includes a service implementation of the service contract, a Windows Service class, and an installer class.</span></span> <span data-ttu-id="f22d2-110">서비스 구현 클래스 `CalculatorService`, WCF 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="f22d2-110">The service implementation class, `CalculatorService`, is a WCF service.</span></span> <span data-ttu-id="f22d2-111">`CalculatorWindowsService`는 Windows 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="f22d2-111">The `CalculatorWindowsService` is a Windows service.</span></span> <span data-ttu-id="f22d2-112">Windows 서비스로 정규화하기 위해 클래스가 `ServiceBase`에서 상속되고 `OnStart` 및 `OnStop` 메서드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="f22d2-112">To qualify as a Windows service, the class inherits from `ServiceBase` and implements the `OnStart` and `OnStop` methods.</span></span> <span data-ttu-id="f22d2-113">`OnStart`에서 <xref:System.ServiceModel.ServiceHost> 형식에 대한 `CalculatorService`가 만들어지고 열립니다.</span><span class="sxs-lookup"><span data-stu-id="f22d2-113">In `OnStart`, a <xref:System.ServiceModel.ServiceHost> is created for the `CalculatorService` type and opened.</span></span> <span data-ttu-id="f22d2-114">`OnStop`에서 서비스가 중지되고 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="f22d2-114">In `OnStop`, the service is stopped and disposed.</span></span> <span data-ttu-id="f22d2-115">또한 호스트는 응용 프로그램 설정에서 구성된 대로 기본 주소를 서비스 호스트에 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f22d2-115">The host is also responsible for providing a base address to the service host, which has been configured in application settings.</span></span> <span data-ttu-id="f22d2-116"><xref:System.Configuration.Install.Installer>에서 상속되는 설치 관리자 클래스를 사용하면 프로그램을 Installutil.exe 도구를 통해 Windows 서비스로 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f22d2-116">The installer class, which inherits from <xref:System.Configuration.Install.Installer>, allows the program to be installed as a Windows service by the Installutil.exe tool.</span></span>  
  
### <a name="construct-the-service-and-provide-the-hosting-code"></a><span data-ttu-id="f22d2-117">서비스 생성 및 호스팅 코드 제공</span><span class="sxs-lookup"><span data-stu-id="f22d2-117">Construct the service and provide the hosting code</span></span>  
  
1.  <span data-ttu-id="f22d2-118">“Service”라는 새 Visual Studio 콘솔 응용 프로그램 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f22d2-118">Create a new Visual Studio Console Application project called "Service".</span></span>  
  
2.  <span data-ttu-id="f22d2-119">Program.cs의 이름을 Service.cs로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="f22d2-119">Rename Program.cs to Service.cs.</span></span>  
  
3.  <span data-ttu-id="f22d2-120">네임스페이스를 Microsoft.ServiceModel.Samples로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="f22d2-120">Change the namespace to Microsoft.ServiceModel.Samples.</span></span>  
  
4.  <span data-ttu-id="f22d2-121">다음 어셈블리에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f22d2-121">Add references to the following assemblies.</span></span>  
  
    -   <span data-ttu-id="f22d2-122">System.ServiceModel.dll</span><span class="sxs-lookup"><span data-stu-id="f22d2-122">System.ServiceModel.dll</span></span>  
  
    -   <span data-ttu-id="f22d2-123">System.ServiceProcess.dll</span><span class="sxs-lookup"><span data-stu-id="f22d2-123">System.ServiceProcess.dll</span></span>  
  
    -   <span data-ttu-id="f22d2-124">System.Configuration.Install.dll</span><span class="sxs-lookup"><span data-stu-id="f22d2-124">System.Configuration.Install.dll</span></span>  
  
5.  <span data-ttu-id="f22d2-125">다음 using 문을 Service.cs에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f22d2-125">Add the following using statements to Service.cs.</span></span>  
  
     [!code-csharp[c_HowTo_HostInNTService#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#0)]
     [!code-vb[c_HowTo_HostInNTService#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#0)]  
  
6.  <span data-ttu-id="f22d2-126">다음 코드와 같이 `ICalculator` 서비스 계약을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f22d2-126">Define the `ICalculator` service contract as shown in the following code.</span></span>  
  
     [!code-csharp[c_HowTo_HostInNTService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#1)]
     [!code-vb[c_HowTo_HostInNTService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#1)]  
  
7.  <span data-ttu-id="f22d2-127">다음 코드와 같이 `CalculatorService` 클래스에서 서비스 계약을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="f22d2-127">Implement the service contract in a class called `CalculatorService` as shown in the following code.</span></span>  
  
     [!code-csharp[c_HowTo_HostInNTService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#2)]
     [!code-vb[c_HowTo_HostInNTService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#2)]  
  
8.  <span data-ttu-id="f22d2-128">`CalculatorWindowsService` 클래스에서 상속되는 <xref:System.ServiceProcess.ServiceBase> 클래스를 새로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f22d2-128">Create a new class called `CalculatorWindowsService` that inherits from the <xref:System.ServiceProcess.ServiceBase> class.</span></span> <span data-ttu-id="f22d2-129">`serviceHost` 인스턴스를 참조하는 <xref:System.ServiceModel.ServiceHost> 로컬 변수를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f22d2-129">Add a local variable called `serviceHost` to reference the <xref:System.ServiceModel.ServiceHost> instance.</span></span> <span data-ttu-id="f22d2-130">`Main`을 호출하는 `ServiceBase.Run(new CalculatorWindowsService)` 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f22d2-130">Define the `Main` method that calls `ServiceBase.Run(new CalculatorWindowsService)`</span></span>  
  
     [!code-csharp[c_HowTo_HostInNTService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#3)]
     [!code-vb[c_HowTo_HostInNTService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#3)]  
  
9. <span data-ttu-id="f22d2-131">다음 코드와 같이 새 <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29> 인스턴스를 만든 다음 열어서 <xref:System.ServiceModel.ServiceHost> 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f22d2-131">Override the <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29> method by creating and opening a new <xref:System.ServiceModel.ServiceHost> instance as shown in the following code.</span></span>  
  
     [!code-csharp[c_HowTo_HostInNTService#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#4)]
     [!code-vb[c_HowTo_HostInNTService#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#4)]  
  
10. <span data-ttu-id="f22d2-132">다음 코드와 같이 <xref:System.ServiceProcess.ServiceBase.OnStop%2A>를 닫는 <xref:System.ServiceModel.ServiceHost> 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f22d2-132">Override the <xref:System.ServiceProcess.ServiceBase.OnStop%2A> method closing the <xref:System.ServiceModel.ServiceHost> as shown in the following code.</span></span>  
  
     [!code-csharp[c_HowTo_HostInNTService#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#5)]
     [!code-vb[c_HowTo_HostInNTService#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#5)]  
  
11. <span data-ttu-id="f22d2-133">`ProjectInstaller`에서 상속되며 <xref:System.Configuration.Install.Installer>로 설정된  <xref:System.ComponentModel.RunInstallerAttribute>로 표시되는 `true` 클래스를 새로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f22d2-133">Create a new class called `ProjectInstaller` that inherits from <xref:System.Configuration.Install.Installer> and that is marked with the <xref:System.ComponentModel.RunInstallerAttribute> set to `true`.</span></span> <span data-ttu-id="f22d2-134">그러면 Installutil.exe 도구를 통해 Windows 서비스를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f22d2-134">This allows the Windows service to be installed by the Installutil.exe tool.</span></span>  
  
     [!code-csharp[c_HowTo_HostInNTService#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#6)]
     [!code-vb[c_HowTo_HostInNTService#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#6)]  
  
12. <span data-ttu-id="f22d2-135">프로젝트를 만들 때 생성된 `Service` 클래스를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f22d2-135">Remove the `Service` class that was generated when you created the project.</span></span>  
  
13. <span data-ttu-id="f22d2-136">프로젝트에 응용 프로그램 구성 파일을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f22d2-136">Add an application configuration file to the project.</span></span> <span data-ttu-id="f22d2-137">파일의 내용을 다음 구성 XML로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="f22d2-137">Replace the contents of the file with the following configuration XML.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <system.serviceModel>    <services>  
          <!-- This section is optional with the new configuration model  
               introduced in .NET Framework 4. -->  
          <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
                   behaviorConfiguration="CalculatorServiceBehavior">  
            <host>  
              <baseAddresses>  
                <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>  
              </baseAddresses>  
            </host>  
            <!-- this endpoint is exposed at the base address provided by host: http://localhost:8000/ServiceModelSamples/service  -->  
            <endpoint address=""  
                      binding="wsHttpBinding"  
                      contract="Microsoft.ServiceModel.Samples.ICalculator" />  
            <!-- the mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex -->  
            <endpoint address="mex"  
                      binding="mexHttpBinding"  
                      contract="IMetadataExchange" />  
          </service>  
        </services>  
        <behaviors>  
          <serviceBehaviors>  
            <behavior name="CalculatorServiceBehavior">  
              <serviceMetadata httpGetEnabled="true"/>  
              <serviceDebug includeExceptionDetailInFaults="False"/>  
            </behavior>  
          </serviceBehaviors>  
        </behaviors>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
     <span data-ttu-id="f22d2-138">App.config 파일을 마우스 오른쪽 단추로 클릭는 **솔루션 탐색기** 선택 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="f22d2-138">Right click the App.config file in the **Solution Explorer** and select **Properties**.</span></span> <span data-ttu-id="f22d2-139">아래 **출력 디렉터리로 복사** 선택 **변경 된 내용만 복사**합니다.</span><span class="sxs-lookup"><span data-stu-id="f22d2-139">Under **Copy to Output Directory** select **Copy if Newer**.</span></span>  
  
     <span data-ttu-id="f22d2-140">다음 예제에서는 구성 파일의 끝점을 명시적으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f22d2-140">This example explicitly specifies endpoints in the configuration file.</span></span> <span data-ttu-id="f22d2-141">서비스에 끝점을 추가하지 않으면 런타임에서 기본 끝점을 자동으로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f22d2-141">If you do not add any endpoints to the service, the runtime adds default endpoints for you.</span></span> <span data-ttu-id="f22d2-142">이 예제에서는 서비스의 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>가 `true`로 설정되어 있으므로 서비스의 메타데이터 게시 기능도 사용하도록 설정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f22d2-142">In this example, because the service has a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> set to `true`, your service also has publishing metadata enabled.</span></span> <span data-ttu-id="f22d2-143">기본 끝점, 바인딩 및 동작에 대 한 자세한 내용은 참조 [단순화 된 구성](../../../../docs/framework/wcf/simplified-configuration.md) 및 [WCF 서비스에 대 한 구성을 단순화](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f22d2-143">For more information about default endpoints, bindings, and behaviors, see [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
### <a name="install-and-run-the-service"></a><span data-ttu-id="f22d2-144">서비스를 설치하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f22d2-144">Install and run the service</span></span>  
  
1.  <span data-ttu-id="f22d2-145">솔루션을 빌드하여 `Service.exe` 실행 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f22d2-145">Build the solution to create the `Service.exe` executable.</span></span>  
  
2.  <span data-ttu-id="f22d2-146">[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 명령 프롬프트를 열고 프로젝트 디렉터리로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="f22d2-146">Open the [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] command prompt and navigate to the project directory.</span></span> <span data-ttu-id="f22d2-147">명령 프롬프트에서 `installutil bin\service.exe`를 입력하여 Windows 서비스를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="f22d2-147">Type `installutil bin\service.exe` at the command prompt to install the Windows service.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f22d2-148">[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 명령 프롬프트를 사용하지 않는 경우에는 `%WinDir%\Microsoft.NET\Framework\v4.0.<current version>` 디렉터리가 시스템 경로에 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f22d2-148">If you do not use the [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] command prompt, make sure that the `%WinDir%\Microsoft.NET\Framework\v4.0.<current version>` directory is in the system path.</span></span>  
  
     <span data-ttu-id="f22d2-149">명령 프롬프트에서 `services.msc`를 입력하여 SCM(서비스 제어 관리자)에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="f22d2-149">Type `services.msc` at the command prompt to access the Service Control Manager (SCM).</span></span> <span data-ttu-id="f22d2-150">Windows 서비스는 서비스에서 "WCFWindowsServiceSample"로 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f22d2-150">The Windows service should appear in Services as "WCFWindowsServiceSample".</span></span> <span data-ttu-id="f22d2-151">WCF 서비스 Windows 서비스가 실행 중인 경우에 클라이언트에 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f22d2-151">The WCF service can only respond to clients if the Windows service is running.</span></span> <span data-ttu-id="f22d2-152">서비스를 시작 하려면 SCM 및 선택 "시작" 또는 형식 단추로 **net 시작 WCFWindowsServiceSample** 명령 프롬프트입니다.</span><span class="sxs-lookup"><span data-stu-id="f22d2-152">To start the service, right-click it in the SCM and select "Start", or type **net start WCFWindowsServiceSample** at the command prompt.</span></span>  
  
3.  <span data-ttu-id="f22d2-153">서비스를 변경하려면 먼저 서비스를 중지하고 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f22d2-153">If you make changes to the service, you must first stop it and uninstall it.</span></span> <span data-ttu-id="f22d2-154">서비스를 중지 SCM에서 서비스를 마우스 오른쪽 단추로 클릭 하 고 "중지"를 선택 하려면 또는 **형식 net stop WCFWindowsServiceSample** 명령 프롬프트입니다.</span><span class="sxs-lookup"><span data-stu-id="f22d2-154">To stop the service, right-click the service in the SCM and select "Stop", or **type net stop WCFWindowsServiceSample** at the command prompt.</span></span> <span data-ttu-id="f22d2-155">Windows 서비스를 중지한 다음 클라이언트를 실행할 경우 클라이언트가 서비스에 액세스하려고 할 때 <xref:System.ServiceModel.EndpointNotFoundException> 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="f22d2-155">Note that if you stop the Windows service and then run a client, an <xref:System.ServiceModel.EndpointNotFoundException> exception occurs when a client attempts to access the service.</span></span> <span data-ttu-id="f22d2-156">Windows 서비스 유형 제거에 **installutil /u bin\service.exe** 명령 프롬프트입니다.</span><span class="sxs-lookup"><span data-stu-id="f22d2-156">To uninstall the Windows service type **installutil /u bin\service.exe** at the command prompt.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f22d2-157">예제</span><span class="sxs-lookup"><span data-stu-id="f22d2-157">Example</span></span>  
 <span data-ttu-id="f22d2-158">다음은 이 항목에서 사용되는 전체 코드 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="f22d2-158">The following is a complete listing of the code used by this topic.</span></span>  
  
 [!code-csharp[c_HowTo_HostInNTService#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#8)]
 [!code-vb[c_HowTo_HostInNTService#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#8)]  
  
 <span data-ttu-id="f22d2-159">"자체 호스팅" 옵션과 같이 Windows 서비스 호스팅 환경에서는 일부 호스팅 코드를 응용 프로그램의 일부로 작성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f22d2-159">Like the "Self-Hosting" option, the Windows service hosting environment requires that some hosting code be written as part of the application.</span></span> <span data-ttu-id="f22d2-160">서비스는 콘솔 응용 프로그램으로 구현되고 자체 호스팅 코드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f22d2-160">The service is implemented as a console application and contains its own hosting code.</span></span> <span data-ttu-id="f22d2-161">다른 호스팅 환경의 경우 IIS(인터넷 정보 서비스)의 WAS(Windows Process Activation Service) 호스팅과 같이 개발자가 호스팅 코드를 작성할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f22d2-161">In other hosting environments, such as Windows Process Activation Service (WAS) hosting in Internet Information Services (IIS), it is not necessary for developers to write hosting code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f22d2-162">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f22d2-162">See Also</span></span>  
 [<span data-ttu-id="f22d2-163">단순화된 구성</span><span class="sxs-lookup"><span data-stu-id="f22d2-163">Simplified Configuration</span></span>](../../../../docs/framework/wcf/simplified-configuration.md)  
 [<span data-ttu-id="f22d2-164">관리되는 응용 프로그램에서의 호스팅</span><span class="sxs-lookup"><span data-stu-id="f22d2-164">Hosting in a Managed Application</span></span>](../../../../docs/framework/wcf/feature-details/hosting-in-a-managed-application.md)  
 [<span data-ttu-id="f22d2-165">서비스 호스팅</span><span class="sxs-lookup"><span data-stu-id="f22d2-165">Hosting Services</span></span>](../../../../docs/framework/wcf/hosting-services.md)  
 [<span data-ttu-id="f22d2-166">Windows Server App Fabric 호스팅 기능</span><span class="sxs-lookup"><span data-stu-id="f22d2-166">Windows Server App Fabric Hosting Features</span></span>](http://go.microsoft.com/fwlink/?LinkId=201276)
