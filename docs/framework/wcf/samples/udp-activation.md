---
title: "UDP 활성화"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4b0ccd10-0dfb-4603-93f9-f0857c581cb7
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 32c452042ffee0a09143042900d24b7429234bec
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="udp-activation"></a><span data-ttu-id="95abd-102">UDP 활성화</span><span class="sxs-lookup"><span data-stu-id="95abd-102">UDP Activation</span></span>
<span data-ttu-id="95abd-103">이 샘플에 따라는 [전송: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) 샘플.</span><span class="sxs-lookup"><span data-stu-id="95abd-103">This sample is based on the [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) sample.</span></span> <span data-ttu-id="95abd-104">확장 된 [전송: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) 샘플은 WAS Windows Process Activation Service ()를 사용 하 여 프로세스 활성화를 지원 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="95abd-104">It extends the [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) sample to support process activation using the Windows Process Activation Service (WAS).</span></span>  
  
 <span data-ttu-id="95abd-105">이 샘플은 크게 세 부분으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="95abd-105">The sample consists of three major pieces:</span></span>  
  
-   <span data-ttu-id="95abd-106">UDP 프로토콜 활성기(활성화할 응용 프로그램을 대신하여 UDP 메시지를 수신하는 독립 실행형 프로세스)</span><span class="sxs-lookup"><span data-stu-id="95abd-106">A UDP Protocol Activator, a standalone process that receives UDP messages on behalf of applications that are to be activated.</span></span>  
  
-   <span data-ttu-id="95abd-107">UDP 사용자 지정 전송을 사용하여 메시지를 보내는 클라이언트</span><span class="sxs-lookup"><span data-stu-id="95abd-107">A client that uses the UDP custom transport to send messages.</span></span>  
  
-   <span data-ttu-id="95abd-108">WAS에서 활성화한 작업자 프로세스에서 호스팅되고 UDP 사용자 지정 전송을 통해 메시지를 수신하는 서비스</span><span class="sxs-lookup"><span data-stu-id="95abd-108">A service (hosted in a worker process activated by WAS) that receives messages over the UDP custom transport.</span></span>  
  
## <a name="udp-protocol-activator"></a><span data-ttu-id="95abd-109">UDP 프로토콜 활성기</span><span class="sxs-lookup"><span data-stu-id="95abd-109">UDP Protocol Activator</span></span>  
 <span data-ttu-id="95abd-110">UDP 프로토콜 활성기는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트와 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스 간을 연결해 주는 역할을 하며</span><span class="sxs-lookup"><span data-stu-id="95abd-110">The UDP Protocol Activator is a bridge between the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client and the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span> <span data-ttu-id="95abd-111">전송 계층에서 UDP 프로토콜을 통한 데이터 통신을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="95abd-111">It provides data communication through the UDP protocol at the transport layer.</span></span> <span data-ttu-id="95abd-112">주요 기능 두 가지는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="95abd-112">It has two major functions:</span></span>  
  
-   <span data-ttu-id="95abd-113">WAS LA(수신기 어댑터) - 들어오는 메시지에 대한 응답으로 WAS와 공동 작업하여 프로세스를 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="95abd-113">WAS Listener Adapter (LA), which collaborates with WAS to activate processes in response to incoming messages.</span></span>  
  
-   <span data-ttu-id="95abd-114">UDP 프로토콜 수신기 - 활성화할 응용 프로그램을 대신하여 UDP 메시지를 수락합니다.</span><span class="sxs-lookup"><span data-stu-id="95abd-114">UDP Protocol Listener, which accepts UDP messages on behalf of applications that are to be activated.</span></span>  
  
 <span data-ttu-id="95abd-115">활성기는 서버 컴퓨터에서 독립 실행형 프로그램으로 실행되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95abd-115">The activator must be running as a standalone program on the server machine.</span></span> <span data-ttu-id="95abd-116">일반적으로 NetTcpActivator 및 NetPipeActivator와 같은 WAS 수신기 어댑터는 장기간 실행되는 Windows 서비스에서 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="95abd-116">Normally, WAS listener adapters (such as the NetTcpActivator and the NetPipeActivator) are implemented in long-running Windows services.</span></span> <span data-ttu-id="95abd-117">그러나 이 샘플에서는 단순성을 위해 프로토콜 활성기를 독립 실행형 응용 프로그램으로 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="95abd-117">However, for simplicity and clarity, this sample implements the protocol activator as a standalone application.</span></span>  
  
### <a name="was-listener-adapter"></a><span data-ttu-id="95abd-118">WAS 수신기 어댑터</span><span class="sxs-lookup"><span data-stu-id="95abd-118">WAS Listener Adapter</span></span>  
 <span data-ttu-id="95abd-119">UDP용 WAS 수신기 어댑터는 `UdpListenerAdapter` 클래스에서 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="95abd-119">The WAS Listener Adapter for UDP is implemented in the `UdpListenerAdapter` class.</span></span> <span data-ttu-id="95abd-120">이는 WAS와 상호 작용하여 UDP 프로토콜의 응용 프로그램 활성화를 수행하는 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="95abd-120">It is the module that interacts with WAS to perform application activation for the UDP protocol.</span></span> <span data-ttu-id="95abd-121">이 작업은 다음과 같은 Webhost API를 호출하여 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="95abd-121">This is achieved by calling the following Webhost APIs:</span></span>  
  
-   `WebhostRegisterProtocol`  
  
-   `WebhostUnregisterProtocol`  
  
-   `WebhostOpenListenerChannelInstance`  
  
-   `WebhostCloseAllListenerChannelInstances`  
  
 <span data-ttu-id="95abd-122">처음에 `WebhostRegisterProtocol`을 호출한 후 수신기 어댑터는 %windir%\system32\inetsrv에 있는 applicationHost.config에 등록된 모든 응용 프로그램에 대해 WAS로부터 `ApplicationCreated` 콜백을 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="95abd-122">After initially calling `WebhostRegisterProtocol`, the listener adapter receives the callback `ApplicationCreated` from WAS for all of the applications registered in applicationHost.config (located in %windir%\system32\inetsrv).</span></span> <span data-ttu-id="95abd-123">이 샘플에서는 UDP 프로토콜(프로토콜 ID: "net.udp")을 사용하는 응용 프로그램만 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="95abd-123">In this sample, we only handle the applications with the UDP protocol (with the protocol id as "net.udp") enabled.</span></span> <span data-ttu-id="95abd-124">다른 구현에서는 응용 프로그램의 동적 구성 변경 사항(예: 사용 안 함에서 사용으로의 응용 프로그램 전환)에 응답하는 경우 이를 다르게 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95abd-124">Other implementations may handle this differently if such implementations respond to dynamic configuration changes to the application (for example, an application transition from disabled to enabled).</span></span>  
  
 <span data-ttu-id="95abd-125">`ConfigManagerInitializationCompleted` 콜백이 수신되면 이는 WAS가 프로토콜의 초기화에 대한 모든 알림을 완료했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="95abd-125">When the callback `ConfigManagerInitializationCompleted` is received, it indicates that WAS has finished all of the notifications for the initialization of the protocol.</span></span> <span data-ttu-id="95abd-126">이때 수신기 어댑터는 활성화 요청을 처리할 준비가 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95abd-126">At this time, the listener adapter is ready to process activation requests.</span></span>  
  
 <span data-ttu-id="95abd-127">응용 프로그램에 대해 처음으로 새 요청이 들어올 때 수신기 어댑터는 `WebhostOpenListenerChannelInstance`를 WAS로 호출하고 WAS는 작업자 프로세스를 시작합니다(아직 시작되지 않은 경우).</span><span class="sxs-lookup"><span data-stu-id="95abd-127">When a new request comes in the first time for an application, the listener adapter calls `WebhostOpenListenerChannelInstance` into WAS, which starts the worker process if it is not started yet.</span></span> <span data-ttu-id="95abd-128">그런 다음 프로토콜 처리기가 로드되고 수신기 어댑터와 가상 응용 프로그램 간의 통신이 시작될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95abd-128">Then the protocol handlers are loaded and the communication between the listener adapter and the virtual application can start.</span></span>  
  
 <span data-ttu-id="95abd-129">수신기 어댑터에서 %SystemRoot%\System32\inetsrv\ApplicationHost.config에 등록 되어는 <`listenerAdapters`> 다음과 같이 섹션:</span><span class="sxs-lookup"><span data-stu-id="95abd-129">The listener adapter is registered in the %SystemRoot%\System32\inetsrv\ApplicationHost.config in the <`listenerAdapters`> section as following:</span></span>  
  
```xml  
<add name="net.udp" identity="S-1-5-21-2127521184-1604012920-1887927527-387045" />  
```  
  
### <a name="protocol-listener"></a><span data-ttu-id="95abd-130">프로토콜 수신기</span><span class="sxs-lookup"><span data-stu-id="95abd-130">Protocol Listener</span></span>  
 <span data-ttu-id="95abd-131">UDP 프로토콜 수신기는 가상 응용 프로그램을 대신하여 UDP 끝점에서 수신 대기하는 프로토콜 활성기 내에 있는 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="95abd-131">The UDP protocol listener is a module inside the protocol activator that listens at a UDP endpoint on behalf of the virtual application.</span></span> <span data-ttu-id="95abd-132">이 수신기는 `UdpSocketListener` 클래스에서 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="95abd-132">It is implemented in the class `UdpSocketListener`.</span></span> <span data-ttu-id="95abd-133">끝점은 사이트의 프로토콜 바인딩에서 포트 번호가 추출되는 `IPEndpoint`로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="95abd-133">The endpoint is represented as `IPEndpoint` for which the port number is extracted from the binding of the protocol for the site.</span></span>  
  
### <a name="control-service"></a><span data-ttu-id="95abd-134">제어 서비스</span><span class="sxs-lookup"><span data-stu-id="95abd-134">Control Service</span></span>  
 <span data-ttu-id="95abd-135">이 샘플에서는 활성기와 WAS 작업자 프로세스 간에 통신하는 데 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="95abd-135">In this sample, we use [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] to communicate between the activator and the WAS worker process.</span></span> <span data-ttu-id="95abd-136">활성기에 상주하는 서비스를 제어 서비스라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="95abd-136">The service that resides in the activator is called the Control Service.</span></span>  
  
## <a name="protocol-handlers"></a><span data-ttu-id="95abd-137">프로토콜 처리기</span><span class="sxs-lookup"><span data-stu-id="95abd-137">Protocol Handlers</span></span>  
 <span data-ttu-id="95abd-138">수신기 어댑터가 `WebhostOpenListenerChannelInstance`를 호출한 후 WAS 프로세스 관리자는 작업자 프로세스를 시작합니다(시작되지 않은 경우).</span><span class="sxs-lookup"><span data-stu-id="95abd-138">After the listener adapter calls `WebhostOpenListenerChannelInstance`, the WAS process manager starts the worker process if it is not started.</span></span> <span data-ttu-id="95abd-139">그런 다음 작업자 프로세스 내부의 응용 프로그램 관리자는 해당 `ListenerChannelId`에 대한 요청과 함께 UDP PPH(프로세스 프로토콜 처리기)를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="95abd-139">The application manager inside the worker process then loads the UDP Process Protocol Handler (PPH) with the request for that `ListenerChannelId`.</span></span> <span data-ttu-id="95abd-140">호출에는 PPH `IAdphManager`합니다.`StartAppDomainProtocolListenerChannel`</span><span class="sxs-lookup"><span data-stu-id="95abd-140">The PPH in turns calls `IAdphManager`.`StartAppDomainProtocolListenerChannel`</span></span> <span data-ttu-id="95abd-141">UDP AppDomain 프로토콜 처리기 ADPH ()를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="95abd-141">to start the UDP AppDomain Protocol Handler (ADPH).</span></span>  
  
## <a name="hostedudptransportconfiguration"></a><span data-ttu-id="95abd-142">HostedUDPTransportConfiguration</span><span class="sxs-lookup"><span data-stu-id="95abd-142">HostedUDPTransportConfiguration</span></span>  
 <span data-ttu-id="95abd-143">이 정보는 다음과 같이 Web.config에 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="95abd-143">The information is registered in the Web.config as follows:</span></span>  
  
```xml  
<serviceHostingEnvironment>  
<add name="net.udp" transportConfigurationType="Microsoft.ServiceModel.Samples.Hosting.HostedUdpTransportConfiguration, UdpActivation, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6fa904d2da1848d6" />  
</serviceHostingEnvironment>  
```  
  
## <a name="special-setup-for-this-sample"></a><span data-ttu-id="95abd-144">이 샘플의 특수 설치 절차</span><span class="sxs-lookup"><span data-stu-id="95abd-144">Special Setup for This Sample</span></span>  
 <span data-ttu-id="95abd-145">이 샘플은 Windows Vista, Windows Server 2008 또는 Windows 7에서만 빌드하고 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95abd-145">This sample can be only built and run on Windows Vista, Windows Server 2008, or Windows 7.</span></span> <span data-ttu-id="95abd-146">샘플을 실행하려면 먼저 모든 구성 요소가 올바르게 설치되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95abd-146">To run the sample, you must first get all of the components set up correctly.</span></span> <span data-ttu-id="95abd-147">다음 단계에 따라 샘플을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="95abd-147">Use the following steps to install the sample.</span></span>  
  
#### <a name="to-set-up-this-sample"></a><span data-ttu-id="95abd-148">이 샘플을 설치하려면</span><span class="sxs-lookup"><span data-stu-id="95abd-148">To set up this sample</span></span>  
  
1.  <span data-ttu-id="95abd-149">다음 명령을 사용하여 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="95abd-149">Install [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 using the following command.</span></span>  
  
    ```  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2.  <span data-ttu-id="95abd-150">Windows Vista에서 프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="95abd-150">Build the project on Windows Vista.</span></span> <span data-ttu-id="95abd-151">컴파일이 끝나면 빌드 후 단계에서 다음 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="95abd-151">After compilation, it also performs the following operations in the post-build phase:</span></span>  
  
    -   <span data-ttu-id="95abd-152">"Default Web Site" 사이트에 UDP 바인딩을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="95abd-152">Installs the UDP binding to the site "Default Web Site".</span></span>  
  
    -   <span data-ttu-id="95abd-153">가상 응용 프로그램 "ServiceModelSamples"를 만들어 실제 경로인 "%SystemDrive%\inetpub\wwwroot\servicemodelsamples"를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="95abd-153">Creates the virtual application "ServiceModelSamples" to point to the physical path: "%SystemDrive%\inetpub\wwwroot\servicemodelsamples".</span></span>  
  
    -   <span data-ttu-id="95abd-154">또한 이 가상 응용 프로그램에 대해 "net.udp" 프로토콜을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="95abd-154">It also enables "net.udp" protocol for this virtual application.</span></span>  
  
3.  <span data-ttu-id="95abd-155">사용자 인터페이스 응용 프로그램인 "WasNetActivator.exe"를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="95abd-155">Start the user interface application "WasNetActivator.exe".</span></span> <span data-ttu-id="95abd-156">클릭는 **설치** 탭, 다음 확인란을 확인 한 다음 클릭 **설치** 설치:</span><span class="sxs-lookup"><span data-stu-id="95abd-156">Click the **Setup** tab, check the following check boxes and then click **Install** to install them:</span></span>  
  
    -   <span data-ttu-id="95abd-157">UDP Listener Adapter</span><span class="sxs-lookup"><span data-stu-id="95abd-157">UDP Listener Adapter</span></span>  
  
    -   <span data-ttu-id="95abd-158">UDP Protocol Handlers</span><span class="sxs-lookup"><span data-stu-id="95abd-158">UDP Protocol Handlers</span></span>  
  
4.  <span data-ttu-id="95abd-159">클릭는 **활성화** 사용자 인터페이스 응용 프로그램 "WasNetActivator.exe"를 탭 합니다.</span><span class="sxs-lookup"><span data-stu-id="95abd-159">Click the **Activation** tab of the user interface application "WasNetActivator.exe".</span></span> <span data-ttu-id="95abd-160">클릭는 **시작** 수신기 어댑터를 시작 하려면 합니다.</span><span class="sxs-lookup"><span data-stu-id="95abd-160">Click the **Start** button to start the listener adapter.</span></span> <span data-ttu-id="95abd-161">이제 프로그램을 실행할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="95abd-161">Now you are ready to run the program.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="95abd-162">이 샘플 사용을 마친 다음에는 Cleanup.bat를 실행하여 "Default Web Site"에서 net.udp 바인딩을 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95abd-162">When you are finished with this sample, you must run Cleanup.bat to remove the net.udp binding from the "Default Web Site".</span></span>  
  
## <a name="sample-usage"></a><span data-ttu-id="95abd-163">샘플 사용</span><span class="sxs-lookup"><span data-stu-id="95abd-163">Sample Usage</span></span>  
 <span data-ttu-id="95abd-164">컴파일 후에는 다음과 같이 네 개의 다른 이진 파일이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="95abd-164">After compilation, there are four different binaries generated:</span></span>  
  
-   <span data-ttu-id="95abd-165">Client.exe: 클라이언트 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="95abd-165">Client.exe: The client code.</span></span> <span data-ttu-id="95abd-166">App.config는 클라이언트 구성 파일 Client.exe.config로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="95abd-166">The App.config is compiled into the client configuration file Client.exe.config.</span></span>  
  
-   <span data-ttu-id="95abd-167">UDPActivation.dll: 모든 주요 UDP 구현이 포함된 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="95abd-167">UDPActivation.dll: the library that contains all of the major UDP implementations.</span></span>  
  
-   <span data-ttu-id="95abd-168">Service.dll: 서비스 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="95abd-168">Service.dll: The service code.</span></span> <span data-ttu-id="95abd-169">이 파일은 가상 응용 프로그램 ServiceModelSamples의 \bin 디렉터리에 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="95abd-169">This is copied to the \bin directory of the virtual application ServiceModelSamples.</span></span> <span data-ttu-id="95abd-170">서비스 파일은 Service.svc이고 구성 파일은 Web.config입니다. 컴파일 후 이러한 파일은 %SystemDrive%\Inetpub\wwwroot\ServiceModelSamples 위치에 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="95abd-170">The service file is Service.svc and the configuration file is Web.config. After compilation, they are copied to the following location: %SystemDrive%\Inetpub\wwwroot\ServiceModelSamples.</span></span>  
  
-   <span data-ttu-id="95abd-171">WasNetActivator: UDP 활성기 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="95abd-171">WasNetActivator: The UDP activator program.</span></span>  
  
-   <span data-ttu-id="95abd-172">필요한 모든 요소가 올바르게 설치되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="95abd-172">Ensure that all of the required pieces are installed correctly.</span></span> <span data-ttu-id="95abd-173">다음 단계에서는 샘플을 실행하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="95abd-173">The following steps show how to run the sample:</span></span>  
  
1.  <span data-ttu-id="95abd-174">다음과 같은 Windows 서비스가 시작되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="95abd-174">Ensure that the following Windows services have been started:</span></span>  
  
    -   <span data-ttu-id="95abd-175">WAS(Windows Process Activation Service)</span><span class="sxs-lookup"><span data-stu-id="95abd-175">Windows Process Activation Service (WAS).</span></span>  
  
    -   <span data-ttu-id="95abd-176">IIS(Internet Information Services): W3SVC.</span><span class="sxs-lookup"><span data-stu-id="95abd-176">Internet Information Services (IIS): W3SVC.</span></span>  
  
2.  <span data-ttu-id="95abd-177">그런 다음 활성기인 WasNetActivator.exe를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="95abd-177">Then start the activator, WasNetActivator.exe.</span></span> <span data-ttu-id="95abd-178">아래는 **활성화** 탭, 유일한 프로토콜 **UDP**, 드롭 다운 목록에서에서 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="95abd-178">Under the **Activation** tab, the only protocol, **UDP**, is selected in the drop down list.</span></span> <span data-ttu-id="95abd-179">클릭는 **시작** 활성기를 시작 하려면 합니다.</span><span class="sxs-lookup"><span data-stu-id="95abd-179">Click the **Start** button to start the activator.</span></span>  
  
3.  <span data-ttu-id="95abd-180">활성기가 시작되었으면 명령 창에서 Client.exe를 실행하여 클라이언트 코드를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95abd-180">Once the activator is started, you can run the client code by running Client.exe from a command window.</span></span> <span data-ttu-id="95abd-181">다음은 샘플 출력입니다.</span><span class="sxs-lookup"><span data-stu-id="95abd-181">The following is the sample output:</span></span>  
  
    ```  
    Testing Udp Activation.  
    Start the status service.  
    Sending UDP datagrams.  
    Type a word that you want to say to the server: Hello, world!  
        Sending datagram: Hello, world![0]  
        Sending datagram: Hello, world![1]  
        Sending datagram: Hello, world![2]  
        Sending datagram: Hello, world![3]  
        Sending datagram: Hello, world![4]  
    Calling UDP duplex contract (ICalculatorContract).  
        0 + 0 = 0  
        1 + 2 = 3  
        2 + 4 = 6  
        3 + 6 = 9  
        4 + 8 = 12  
    Getting status and dump server traces:  
        Operation 'Hello' is called: Hello, world![0]  
        Operation 'Hello' is called: Hello, world![1]  
        Operation 'Hello' is called: Hello, world![2]  
        Operation 'Hello' is called: Hello, world![3]  
        Operation 'Hello' is called: Hello, world![4]  
        Operation 'Add' is called: 0 + 0  
        Operation 'Add' is called: 1 + 2  
        Operation 'Add' is called: 2 + 4  
        Operation 'Add' is called: 3 + 6  
        Operation 'Add' is called: 4 + 8  
    Press <ENTER> to complete test.  
    ```  
  
> [!IMPORTANT]
>  <span data-ttu-id="95abd-182">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95abd-182">The samples may already be installed on your machine.</span></span> <span data-ttu-id="95abd-183">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="95abd-183">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="95abd-184">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="95abd-184">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="95abd-185">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95abd-185">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Transport\UdpActivation`  
  
## <a name="see-also"></a><span data-ttu-id="95abd-186">참고 항목</span><span class="sxs-lookup"><span data-stu-id="95abd-186">See Also</span></span>
