---
title: "사용자 지정 메시지 인터셉터"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 73f20972-53f8-475a-8bfe-c133bfa225b0
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: acac4baa5be68d042dd1b0a11d7acfe609169e10
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="custom-message-interceptor"></a><span data-ttu-id="20b5a-102">사용자 지정 메시지 인터셉터</span><span class="sxs-lookup"><span data-stu-id="20b5a-102">Custom Message Interceptor</span></span>
<span data-ttu-id="20b5a-103">이 샘플에서는 채널 확장성 모델의 사용 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="20b5a-103">This sample demonstrates the use of the channel extensibility model.</span></span> <span data-ttu-id="20b5a-104">특히 채널 팩터리 및 채널 수신기를 만드는 사용자 지정 바인딩 요소를 구현하여 런타임 스택의 특정 지점에서 들어오고 보내는 모든 메시지를 가로채는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="20b5a-104">In particular, it shows how to implement a custom binding element that creates channel factories and channel listeners to intercept all incoming and outgoing messages at a particular point in the run-time stack.</span></span> <span data-ttu-id="20b5a-105">또한 이 샘플에는 이 사용자 지정 팩터리의 사용을 보여 주는 클라이언트와 서버도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20b5a-105">The sample also includes a client and server that demonstrate the use of these custom factories.</span></span>  
  
 <span data-ttu-id="20b5a-106">이 샘플에서는 클라이언트와 서비스 모두가 콘솔 프로그램(.exe)입니다.</span><span class="sxs-lookup"><span data-stu-id="20b5a-106">In this sample, both the client and the service are console programs (.exe).</span></span> <span data-ttu-id="20b5a-107">클라이언트와 서비스 모두 사용자 지정 바인딩 요소 및 관련 런타임 개체를 포함하는 공용 라이브러리(.dll)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="20b5a-107">The client and service both make use of a common library (.dll) that contains the custom binding element and its associated run-time objects.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="20b5a-108">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20b5a-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="20b5a-109">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20b5a-109">The samples may already be installed on your machine.</span></span> <span data-ttu-id="20b5a-110">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="20b5a-110">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="20b5a-111">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="20b5a-111">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="20b5a-112">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20b5a-112">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\MessageInterceptor`  
  
 <span data-ttu-id="20b5a-113">이 샘플에서는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]에서 채널 프레임워크를 사용하고 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 모범 사례에 따라 사용자 지정 계층화된 채널을 만드는 권장 절차에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="20b5a-113">The sample describes the recommended procedure for creating a custom layered channel in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], by using the channel framework and following [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] best practices.</span></span> <span data-ttu-id="20b5a-114">사용자 지정 계층화된 채널을 만드는 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="20b5a-114">The steps to create a custom layered channel are as follows:</span></span>  
  
1.  <span data-ttu-id="20b5a-115">채널 팩터리 및 채널 수신기에서 지원할 채널 셰이프를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="20b5a-115">Decide which of the channel shapes your channel factory and channel listener will support.</span></span>  
  
2.  <span data-ttu-id="20b5a-116">채널 셰이프를 지원하는 채널 팩터리 및 채널 수신기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="20b5a-116">Create a channel factory and a channel listener that support your channel shapes.</span></span>  
  
3.  <span data-ttu-id="20b5a-117">사용자 지정 계층화된 채널을 채널 스택에 추가하는 바인딩 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="20b5a-117">Add a binding element that adds the custom layered channel to a channel stack.</span></span>  
  
4.  <span data-ttu-id="20b5a-118">새 바인딩 요소가 구성 시스템에 노출되도록 바인딩 요소 확장 섹션을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="20b5a-118">Add a binding element extension section to expose the new binding element to the configuration system.</span></span>  
  
## <a name="channel-shapes"></a><span data-ttu-id="20b5a-119">채널 셰이프</span><span class="sxs-lookup"><span data-stu-id="20b5a-119">Channel Shapes</span></span>  
 <span data-ttu-id="20b5a-120">사용자 지정 계층화된 채널을 작성하는 첫 번째 단계는 채널에 필요한 셰이프를 결정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="20b5a-120">The first step in writing a custom layered channel is to decide which shapes are required for the channel.</span></span> <span data-ttu-id="20b5a-121">메시지 검사자를 위해 아래의 계층이 지원하는 모든 셰이프를 지원합니다. 예를 들어, 아래의 계층이 <xref:System.ServiceModel.Channels.IOutputChannel> 및 <xref:System.ServiceModel.Channels.IDuplexSessionChannel>을 빌드할 수 있는 경우 <xref:System.ServiceModel.Channels.IOutputChannel> 및 <xref:System.ServiceModel.Channels.IDuplexSessionChannel>도 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="20b5a-121">For our message inspector, we support any shape that the layer below us supports (for example, if the layer below us can build <xref:System.ServiceModel.Channels.IOutputChannel> and <xref:System.ServiceModel.Channels.IDuplexSessionChannel>, then we also expose <xref:System.ServiceModel.Channels.IOutputChannel> and <xref:System.ServiceModel.Channels.IDuplexSessionChannel>).</span></span>  
  
## <a name="channel-factory-and-listener-factory"></a><span data-ttu-id="20b5a-122">채널 팩터리 및 수신기 팩터리</span><span class="sxs-lookup"><span data-stu-id="20b5a-122">Channel Factory and Listener Factory</span></span>  
 <span data-ttu-id="20b5a-123">사용자 지정 계층화된 채널을 작성하는 두 번째 단계는 클라이언트 채널을 위한 <xref:System.ServiceModel.Channels.IChannelFactory> 구현 및 서비스 채널을 위한 <xref:System.ServiceModel.Channels.IChannelListener> 구현을 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="20b5a-123">The next step in writing a custom layered channel is to create an implementation of <xref:System.ServiceModel.Channels.IChannelFactory> for client channels and of <xref:System.ServiceModel.Channels.IChannelListener> for service channels.</span></span>  
  
 <span data-ttu-id="20b5a-124">이 클래스는 내부 팩터리 및 수신기를 받고 `OnCreateChannel` 및 `OnAcceptChannel` 호출을 제외한 모두를 내부 팩터리 및 수신기에 위임합니다.</span><span class="sxs-lookup"><span data-stu-id="20b5a-124">These classes take an inner factory and listener, and delegate all but the `OnCreateChannel` and `OnAcceptChannel` calls to the inner factory and listener.</span></span>  
  
```  
class InterceptingChannelFactory<TChannel> : ChannelFactoryBase<TChannel>  
{ ... }  
class InterceptingChannelListener<TChannel> : ListenerFactoryBase<TChannel>  
{ ... }  
```  
  
## <a name="adding-a-binding-element"></a><span data-ttu-id="20b5a-125">바인딩 요소 추가</span><span class="sxs-lookup"><span data-stu-id="20b5a-125">Adding a Binding Element</span></span>  
 <span data-ttu-id="20b5a-126">이 샘플에서는 사용자 지정 바인딩 요소인 `InterceptingBindingElement`를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="20b5a-126">The sample defines a custom binding element: `InterceptingBindingElement`.</span></span> <span data-ttu-id="20b5a-127">`InterceptingBindingElement`사용는 `ChannelMessageInterceptor` 한 입력으로이 사용 하 여 `ChannelMessageInterceptor` 자신을 통과 하는 메시지를 조작할 수입니다.</span><span class="sxs-lookup"><span data-stu-id="20b5a-127">`InterceptingBindingElement` takes a `ChannelMessageInterceptor` as an input, and uses this `ChannelMessageInterceptor` to manipulate messages that pass through it.</span></span> <span data-ttu-id="20b5a-128">이는 public이어야 하는 유일한 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="20b5a-128">This is the only class that must be public.</span></span> <span data-ttu-id="20b5a-129">팩터리, 수신기 및 채널 모두 public 런타임 인터페이스의 내부 구현이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20b5a-129">The factory, listener, and channels can all be internal implementations of the public run-time interfaces.</span></span>  
  
```  
public class InterceptingBindingElement : BindingElement  
```  
  
## <a name="adding-configuration-support"></a><span data-ttu-id="20b5a-130">구성 지원 추가</span><span class="sxs-lookup"><span data-stu-id="20b5a-130">Adding Configuration Support</span></span>  
 <span data-ttu-id="20b5a-131">바인딩 구성과 통합하기 위해 라이브러리에서는 구성 섹션 처리기를 바인딩 요소 확장 섹션으로 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="20b5a-131">To integrate with binding configuration, the library defines a configuration section handler as a binding element extension section.</span></span> <span data-ttu-id="20b5a-132">클라이언트 및 서버 구성 파일은 구성 시스템에 바인딩 요소 확장을 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20b5a-132">The client and server configuration files must register the binding element extension with the configuration system.</span></span> <span data-ttu-id="20b5a-133">구성 시스템에 바인딩 요소를 노출하려는 구현자는 이 클래스에서 파생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20b5a-133">Implementers that want to expose their binding element to the configuration system can derive from this class.</span></span>  
  
```  
public abstract class InterceptingElement : BindingElementExtensionElement { ... }  
```  
  
## <a name="adding-policy"></a><span data-ttu-id="20b5a-134">정책 추가</span><span class="sxs-lookup"><span data-stu-id="20b5a-134">Adding Policy</span></span>  
 <span data-ttu-id="20b5a-135">정책 시스템과 통합하기 위해 `InterceptingBindingElement`는 IPolicyExportExtension을 구현하여 정책 생성에 참여해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="20b5a-135">To integrate with our policy system, `InterceptingBindingElement` implements IPolicyExportExtension to signal that we should participate in generating policy.</span></span> <span data-ttu-id="20b5a-136">생성된 클라이언트에 정책을 가져오는 것을 지원하기 위해 사용자는 `InterceptingBindingElementImporter`의 파생 클래스를 등록하고 해당 정책을 사용하는 `CreateMessageInterceptor` 클래스를 생성하도록 `ChannelMessageInterceptor`()를 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20b5a-136">To support importing policy on a generated client, the user can register a derived class of `InterceptingBindingElementImporter` and override `CreateMessageInterceptor`() to generate their policy-enabled `ChannelMessageInterceptor` class.</span></span>  
  
## <a name="example-droppable-message-inspector"></a><span data-ttu-id="20b5a-137">예제: 삭제 가능한 메시지 검사자</span><span class="sxs-lookup"><span data-stu-id="20b5a-137">Example: Droppable Message Inspector</span></span>  
 <span data-ttu-id="20b5a-138">메시지를 삭제하는 `ChannelMessageInspector`의 구현 예제가 샘플에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20b5a-138">Included in the sample is an example implementation of `ChannelMessageInspector` which drops messages.</span></span>  
  
```  
class DroppingServerElement : InterceptingElement  
{  
    protected override ChannelMessageInterceptor CreateMessageInterceptor()  
    {  
        return new DroppingServerInterceptor();  
    }  
}  
```  
  
 <span data-ttu-id="20b5a-139">다음과 같이 구성에서 이 예제에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20b5a-139">You can access it from configuration as follows:</span></span>  
  
```xml  
<configuration>  
    ...  
    <system.serviceModel>  
        ...  
        <extensions>  
            <bindingElementExtensions>  
                <add name="droppingInterceptor"   
                   type=  
          "Microsoft.ServiceModel.Samples.DroppingServerElement, library"/>  
            </bindingElementExtensions>  
        </extensions>  
    </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="20b5a-140">클라이언트와 서버 모두 이 새로 생성된 구성 섹션을 사용하여 런타임 채널 스택의 최하위(전송 수준 위)에 사용자 지정 팩터리를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="20b5a-140">The client and server both use this newly created configuration section to insert the custom factories into the lowest-level of their run-time channel stacks (above the transport level).</span></span>  
  
```xml  
<customBinding>  
  <binding name="sampleBinding">  
    <droppingInterceptor/>  
    <httpTransport/>  
  </binding>  
</customBinding>  
```  
  
 <span data-ttu-id="20b5a-141">클라이언트에서는 `MessageInterceptor` 라이브러리를 사용하여 사용자 지정 헤더를 짝수 번호의 메시지에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="20b5a-141">The client uses the `MessageInterceptor` library to add a custom header to even numbered messages.</span></span> <span data-ttu-id="20b5a-142">한편 서비스는 `MessageInterceptor` 라이브러리를 사용하여 이 특수 헤더가 없는 메시지를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="20b5a-142">The service on the other hand uses `MessageInterceptor` library to drop any messages that do not have this special header.</span></span>  
  
 <span data-ttu-id="20b5a-143">서비스와 클라이언트를 차례로 실행한 후 다음과 같은 클라이언트 출력이 나타나야 합니다.</span><span class="sxs-lookup"><span data-stu-id="20b5a-143">You should see the following client output after running the service and then the client.</span></span>  
  
```  
Reporting the next 10 wind speed  
100 kph  
Server dropped a message.  
90 kph  
80 kph  
Server dropped a message.  
70 kph  
60 kph  
Server dropped a message.  
50 kph  
40 kph  
Server dropped a message.  
30 kph  
20 kph  
Server dropped a message.  
10 kph  
Press ENTER to shut down client  
```  
  
 <span data-ttu-id="20b5a-144">클라이언트가 서로 다른 10가지 풍속을 서비스에 보고하지만, 그 중 절반에만 특수 헤더를 태그합니다.</span><span class="sxs-lookup"><span data-stu-id="20b5a-144">The client reports 10 different wind speeds to the service, but only tags half of them with the special header.</span></span>  
  
 <span data-ttu-id="20b5a-145">서비스에서는 다음과 같이 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="20b5a-145">On the service, you should see the following output:</span></span>  
  
```  
Press ENTER to exit.  
Dangerous wind detected! Reported speed (90) is greater than 64 kph.  
Dangerous wind detected! Reported speed (70) is greater than 64 kph.  
5 wind speed reports have been received.  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="20b5a-146">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="20b5a-146">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="20b5a-147">다음 명령을 사용하여 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="20b5a-147">Install [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 using the following command.</span></span>  
  
    ```  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2.  <span data-ttu-id="20b5a-148">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="20b5a-148">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
3.  <span data-ttu-id="20b5a-149">지침에 따라 솔루션을 빌드하려면 [Windows Communication Foundation 샘플 빌드](../../../../docs/framework/wcf/samples/building-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="20b5a-149">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4.  <span data-ttu-id="20b5a-150">지침에 따라 단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="20b5a-150">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
5.  <span data-ttu-id="20b5a-151">먼저 Service.exe를 실행한 다음 Client.exe를 실행하고 두 콘솔 창의 출력을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="20b5a-151">Run Service.exe first then run Client.exe and watch both console windows for output.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20b5a-152">참고 항목</span><span class="sxs-lookup"><span data-stu-id="20b5a-152">See Also</span></span>
