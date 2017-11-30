---
title: "영속 이중"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4e76d1a1-f3d8-4a0f-8746-4a322cdff6eb
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d8beae85b2cee8956efd160b8540e76f04dd7ee7
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2017
---
# <a name="durable-duplex"></a><span data-ttu-id="505e7-102">영속 이중</span><span class="sxs-lookup"><span data-stu-id="505e7-102">Durable Duplex</span></span>
<span data-ttu-id="505e7-103">이 샘플에서는 [!INCLUDE[wf](../../../../includes/wf-md.md)]에서 메시징 활동을 사용하여 영속 이중 메시지 교환을 설정하고 구성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="505e7-103">This sample demonstrates how to set up and configure durable duplex message exchange using the messaging activities in [!INCLUDE[wf](../../../../includes/wf-md.md)].</span></span> <span data-ttu-id="505e7-104">영속 이중 메시지 교환은 오랜 기간 동안 발생하는 양방향 메시지 교환입니다.</span><span class="sxs-lookup"><span data-stu-id="505e7-104">A durable duplex message exchange is a two-way message exchange that takes place over a long period of time.</span></span> <span data-ttu-id="505e7-105">메시지 교환 수명 주기는 통신 채널 수명 주기와 서비스 인스턴스의 메모리 내 수명 주기보다 길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="505e7-105">The lifetime of the message exchange may be longer than the lifetime of the communication channel and the in-memory lifetime of the service instances.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="505e7-106">샘플 세부 정보</span><span class="sxs-lookup"><span data-stu-id="505e7-106">Sample Details</span></span>  
 <span data-ttu-id="505e7-107">이 샘플에서는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]를 사용하여 구현된 [!INCLUDE[wf2](../../../../includes/wf2-md.md)] 서비스 두 개가 영속 이중 메시지 교환을 포함하도록 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="505e7-107">In this sample, two [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] services implemented using [!INCLUDE[wf2](../../../../includes/wf2-md.md)] are configured to have a durable duplex message exchange.</span></span> <span data-ttu-id="505e7-108">영 속 이중 메시지 교환은 MSMQ를 통해 전송 하 고 사용 하 여 상관 관계가 지정 된 두 개의 단방향 메시지로 구성 된 [.NET Context Exchange](http://go.microsoft.com/fwlink/?LinkID=166059)합니다.</span><span class="sxs-lookup"><span data-stu-id="505e7-108">The durable duplex message exchange is composed from two one-way messages sent over MSMQ and correlated using [.NET Context Exchange](http://go.microsoft.com/fwlink/?LinkID=166059).</span></span> <span data-ttu-id="505e7-109">메시지는 <xref:System.ServiceModel.Activities.Send> 및 <xref:System.ServiceModel.Activities.Receive> 메시징 활동을 사용하여 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="505e7-109">The messages are sent using the <xref:System.ServiceModel.Activities.Send> and <xref:System.ServiceModel.Activities.Receive> messaging activities.</span></span> <span data-ttu-id="505e7-110">.NET Context Exchange는 보낸 메시지에 대한 콜백 주소를 지정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="505e7-110">.NET Context Exchange is use to specify the callback address on the sent messages.</span></span> <span data-ttu-id="505e7-111">두 서비스는 WAS(Windows Process Activation Service)를 사용하여 호스트되고 서비스 인스턴스의 지속성을 사용하도록 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="505e7-111">Both services are hosted using Windows Process Activation Services (WAS) and are configured to enable persistence of the services instances.</span></span>  
  
 <span data-ttu-id="505e7-112">첫 번째 서비스(Service1.xamlx)는 전송 서비스(Service2.xamlx)에 작업을 수행하도록 요청을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="505e7-112">The first service (Service1.xamlx) sends a request to the send service (Service2.xamlx) to do some work.</span></span> <span data-ttu-id="505e7-113">작업이 완료되면 Service2.xamlx가 Service1.xamlx에 작업이 완료되었음을 알립니다.</span><span class="sxs-lookup"><span data-stu-id="505e7-113">Once the work is completed, Service2.xamlx sends a notification back to Service1.xamlx to indicate that the work has been completed.</span></span> <span data-ttu-id="505e7-114">워크플로 콘솔 응용 프로그램은 서비스가 수신 대기하는 큐를 설정하고 초기 시작 메시지를 보내 Service1.xamlx를 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="505e7-114">A workflow console application sets up the queues that the services are listening on and sends the initial Start message to activate Service1.xamlx.</span></span> <span data-ttu-id="505e7-115">Service1.xamlx는 Service2.xamlx에서 요청한 작업이 완료되었음을 나타내는 알림을 받은 후 결과를 XML 파일로 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="505e7-115">Once Service1.xamlx receives the notification from Service2.xamlx that the requested work has been completed, Service1.xamlx saves the result to an XML file.</span></span> <span data-ttu-id="505e7-116">Service1.xamlx는 콜백 메시지를 기다리는 동안 기본 <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>를 사용하여 인스턴스 상태를 지속합니다.</span><span class="sxs-lookup"><span data-stu-id="505e7-116">While waiting for the callback message, Service1.xamlx persists its instance state using the default <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>.</span></span> <span data-ttu-id="505e7-117">Service2.xamlx는 Service1.xamlx에서 요청한 작업을 완료하는 과정의 일부로 인스턴스 상태를 지속합니다.</span><span class="sxs-lookup"><span data-stu-id="505e7-117">Service2.xamlx persists its instance state as part of completing the work requested by Service1.xamlx.</span></span>  
  
 <span data-ttu-id="505e7-118">서비스에서 MSMQ를 통해 .NET Context Exchange를 사용하도록 구성하기 위해 두 서비스에서 <xref:System.ServiceModel.Channels.ContextBindingElement>와 <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>로 구성된 사용자 지정 바인딩을 사용하도록 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="505e7-118">To configure the services to use .NET Context Exchange over MSMQ, both services are configured to use a custom binding that consists of the <xref:System.ServiceModel.Channels.ContextBindingElement> and the <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>.</span></span> <span data-ttu-id="505e7-119"><xref:System.ServiceModel.Channels.ContextBindingElement>를 사용하여 콜백 주소를 지정하고, 사용자 지정 바인딩을 사용하여 보낸 모든 메시지가 있는 콜백 컨텍스트 헤더에 이 주소를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="505e7-119">A callback address is specified with the <xref:System.ServiceModel.Channels.ContextBindingElement> and is included in a callback context header with all messages sent using a custom binding.</span></span> <span data-ttu-id="505e7-120">다음 코드 예제에서는 사용자 지정 바인딩을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="505e7-120">The following code example defines the custom binding.</span></span>  
  
```xml  
<configuration>  
     <system.serviceModel>  
          …  
          <bindings>  
               <customBinding>  
                    <binding name="netMsmqContextBinding">  
                         <context clientCallbackAddress="net.msmq://localhost/private/DurableDuplex/Service1.xamlx"/>  
                         <msmqTransport exactlyOnce="False">  
                              <msmqTransportSecurity msmqAuthenticationMode="None" msmqProtectionLevel="None"/>  
                         </msmqTransport>  
                    </binding>  
               </customBinding>  
          </bindings>  
          …  
     </system.serviceModel>  
</configuration>  
```  
  
> [!NOTE]
>  <span data-ttu-id="505e7-121">이 샘플에서 사용하는 바인딩은 보안 처리되어 있지 않으므로</span><span class="sxs-lookup"><span data-stu-id="505e7-121">The binding used by this sample is not secure.</span></span> <span data-ttu-id="505e7-122">응용 프로그램을 배포할 때 응용 프로그램의 보안 요구 사항에 따라 바인딩을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="505e7-122">When deploying your application you should configure your binding based on the security requirements of your application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="505e7-123">이 샘플에서 사용하는 큐는 트랜잭션이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="505e7-123">The queues used in this sample are not transactional.</span></span> <span data-ttu-id="505e7-124">설정 하는 방법을 보여 주는 샘플에 대 한 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 트랜잭션 큐를 사용 하 여 교환 메시지에서 참조는 [MSMQ 활성화](../../../../docs/framework/wcf/samples/msmq-activation.md) 샘플.</span><span class="sxs-lookup"><span data-stu-id="505e7-124">For a sample that shows how to set up [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] message exchanges using transaction queues, see the [MSMQ Activation](../../../../docs/framework/wcf/samples/msmq-activation.md) sample.</span></span>  
  
 <span data-ttu-id="505e7-125">Service1.xamlx에서 Service2.xamlx로 보내는 메시지는 Service2.xamlx의 주소로 구성된 클라이언트 끝점과 이전에 정의된 사용자 지정 바인딩을 사용하여 보내집니다.</span><span class="sxs-lookup"><span data-stu-id="505e7-125">The message sent by Service1.xamlx to Service2.xamlx is sent using a client endpoint configured with the address of Service2.xamlx and the custom binding defined previously.</span></span> <span data-ttu-id="505e7-126">Service2.xamlx에서 Service1.xamlx로의 콜백은 Service1.xamlx에서 보낸 콜백 컨텍스트에서 주소를 가져오므로 주소가 명시적으로 구성되지 않은 클라이언트 끝점을 사용하여 보내집니다.</span><span class="sxs-lookup"><span data-stu-id="505e7-126">The callback from Service2.xamlx to Service1.xamlx is sent using a client endpoint with no explicitly configured address because the address is taken from the callback context sent by Service1.xamlx.</span></span> <span data-ttu-id="505e7-127">다음 코드 예제에서는 클라이언트 끝점을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="505e7-127">The following code example defines the client endpoints.</span></span>  
  
```xml  
<?xml version="1.0"?>  
<configuration>  
     <system.serviceModel>  
          …  
          <client>  
               <endpoint address="net.msmq://localhost/private/DurableDuplex/Service2.xamlx" binding="customBinding" bindingConfiguration="netMsmqContextBinding" contract="IDoWork"/>  
               <endpoint binding="customBinding" bindingConfiguration="netMsmqContextBinding" contract="INotify"/>  
          </client>  
          …  
     </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="505e7-128">다음 코드 예제에서는 net.msmq 기본 주소에 대한 기본 프로토콜 매핑을 이 사용자 지정 바인딩을 사용하도록 변경하여 이 사용자 지정 바인딩을 통해 끝점을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="505e7-128">The following code example exposes endpoints using this custom binding by changing the default protocol mapping for net.msmq base addresses to use this custom binding.</span></span>  
  
```xml  
<configuration>  
     <system.serviceModel>  
          <protocolMapping>  
               <add scheme="net.msmq" binding="customBinding" bindingConfiguration="netMsmqContextBinding"/>  
          </protocolMapping>  
          …  
     </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="505e7-129">다음 코드 예제에서는 두 서비스에 <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> 동작을 추가하고 지속성 데이터베이스의 연결 문자열을 지정하여 두 서비스에 지속성을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="505e7-129">The following code example enables persistence for both services by adding the <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> behavior to both services and specifying the connection string for the persistence database.</span></span>  
  
```xml  
<?xml version="1.0"?>  
<configuration>  
    <system.serviceModel>  
          …  
          <behaviors>  
               <serviceBehaviors>  
                    <behavior>  
                         <serviceDebug includeExceptionDetailInFaults="True"/>  
                         <serviceMetadata httpGetEnabled="True"/>  
                         <sqlWorkflowInstanceStore connectionString="Data Source=.\SQLEXPRESS;Initial Catalog=DefaultSampleStore;Integrated Security=True"/>  
                    </behavior>  
               </serviceBehaviors>  
          </behaviors>  
     </system.serviceModel>  
</configuration>  
```  
  
## <a name="system-requirements"></a><span data-ttu-id="505e7-130">시스템 요구 사항</span><span class="sxs-lookup"><span data-stu-id="505e7-130">System Requirements</span></span>  
 <span data-ttu-id="505e7-131">이 샘플에 필요한 구성 요소는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="505e7-131">This sample requires the following components.</span></span>  
  
1.  <span data-ttu-id="505e7-132">인터넷 정보 서비스</span><span class="sxs-lookup"><span data-stu-id="505e7-132">Internet Information Services.</span></span>  
  
2.  <span data-ttu-id="505e7-133">인터넷 정보 서비스 -> IIS 6.0 관리 호환성 -> IIS 메타베이스 및 IIS 6.0 구성 호환성</span><span class="sxs-lookup"><span data-stu-id="505e7-133">Internet Information Services -> IIS 6.0 Management Compatibility -> IIS Metabase and IIS 6.0 configuration compatibility.</span></span>  
  
3.  <span data-ttu-id="505e7-134">World Wide Web 서비스 -> 응용 프로그램 개발 기능 -> ASP.NET</span><span class="sxs-lookup"><span data-stu-id="505e7-134">World Wide Web Services -> Application Development Features -> ASP.NET.</span></span>  
  
4.  <span data-ttu-id="505e7-135">MSMQ(Microsoft Message Queue) Server</span><span class="sxs-lookup"><span data-stu-id="505e7-135">Microsoft Message Queues (MSMQ) Server.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="505e7-136">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="505e7-136">To use this sample</span></span>  
  
1.  <span data-ttu-id="505e7-137">지속성 데이터베이스와 결과 디렉터리를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="505e7-137">Set up the persistence database and the results directory.</span></span>  
  
    1.  <span data-ttu-id="505e7-138">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 명령 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="505e7-138">Open a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt.</span></span>  
  
    2.  <span data-ttu-id="505e7-139">이 샘플에서 사용할 폴더로 이동하고 Setup.cmd를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="505e7-139">Navigate to the folder for this sample and run Setup.cmd.</span></span>  
  
2.  <span data-ttu-id="505e7-140">가상 응용 프로그램을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="505e7-140">Set up the virtual application.</span></span>  
  
    1.  <span data-ttu-id="505e7-141">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 명령 프롬프트에서 다음 명령을 실행하여 ASP.NET을 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="505e7-141">From a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt, register ASP.NET by running the following command.</span></span>  
  
        ```  
        aspnet_regiis -i  
        ```  
  
    2.  <span data-ttu-id="505e7-142">실행 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 마우스 오른쪽 단추로 클릭 하 여 관리자 권한으로 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 선택 하 고 **관리자 권한으로 실행**합니다.</span><span class="sxs-lookup"><span data-stu-id="505e7-142">Run [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] with administrator permissions by right-clicking [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] and selecting **Run as administrator**.</span></span>  
  
    3.  <span data-ttu-id="505e7-143">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]을 사용하여 DurableDuplex.sln 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="505e7-143">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the DurableDuplex.sln file.</span></span>  
  
3.  <span data-ttu-id="505e7-144">서비스 큐를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="505e7-144">Set up the service queues.</span></span>  
  
    1.  <span data-ttu-id="505e7-145">F5 키를 눌러 DurableDuplex 클라이언트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="505e7-145">To run the DurableDuplex client, press F5.</span></span>  
  
    2.  <span data-ttu-id="505e7-146">열기는 **컴퓨터 관리** 콘솔을 실행 하 여 `Compmgmt.msc` 명령 프롬프트에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="505e7-146">Open the **Computer Management** console by running `Compmgmt.msc` from a command prompt.</span></span>  
  
    3.  <span data-ttu-id="505e7-147">확장 **서비스 및 응용 프로그램**, **메시지 큐**합니다.</span><span class="sxs-lookup"><span data-stu-id="505e7-147">Expand **Service and Applications**, **Message Queuing**.</span></span> <span data-ttu-id="505e7-148">**개인 큐**합니다.</span><span class="sxs-lookup"><span data-stu-id="505e7-148">**Private Queues**.</span></span>  
  
    4.  <span data-ttu-id="505e7-149">Durableduplex/service1.xamlx 및 durableduplex/service2.xamlx 큐를 마우스 오른쪽 단추로 클릭 하 고 선택 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="505e7-149">Right-click the durableduplex/service1.xamlx and durableduplex/service2.xamlx queues and select **Properties**.</span></span>  
  
    5.  <span data-ttu-id="505e7-150">선택 된 **보안** 탭 하 고 허용 **Everyone이 메시지 받기**, **메시지 보기** 및 **메시지 보내기** 두 큐에 대 한 권한을 합니다.</span><span class="sxs-lookup"><span data-stu-id="505e7-150">Select the **Security** tab and allow **Everyone Receive Message**, **Peek Message** and **Send Message** permissions for both queues.</span></span>  
  
    6.  <span data-ttu-id="505e7-151">IIS 관리자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="505e7-151">Open Internet Information Services (IIS) Manager.</span></span>  
  
    7.  <span data-ttu-id="505e7-152">찾아 **서버**, **사이트**, **기본 웹 사이트**, **개인**, **영 속 이중** 선택 **고급 옵션**합니다.</span><span class="sxs-lookup"><span data-stu-id="505e7-152">Browse to **Server**, **Sites**, **Default Web site**, **private**, **Durable Duplex** and select **Advanced Options**.</span></span>  
  
    8.  <span data-ttu-id="505e7-153">변경 된 **사용할 수 있는 프로토콜** 를 **http, net.msmq**합니다.</span><span class="sxs-lookup"><span data-stu-id="505e7-153">Change the **Enabled Protocols** to **http,net.msmq**.</span></span>  
  
4.  <span data-ttu-id="505e7-154">샘플을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="505e7-154">Run the sample.</span></span>  
  
    1.  <span data-ttu-id="505e7-155">http://localhost/private/durableduplex/service1.xamlx 및 http://localhost/private/durableduplex/service2.xamlx로 이동하여 두 서비스가 실행되고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="505e7-155">Browse to http://localhost/private/durableduplex/service1.xamlx and http://localhost/private/durableduplex/service2.xamlx to ensure that both services are running.</span></span>  
  
    2.  <span data-ttu-id="505e7-156">F5 키를 눌러 DurableDuplexClient를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="505e7-156">Press F5 to run DurableDuplexClient.</span></span>  
  
         <span data-ttu-id="505e7-157">영속 이중 메시지 교환이 완료되면 result.xml 파일이 C:\Inbox 폴더에 저장되고 메시지 교환 결과를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="505e7-157">When the durable duplex message exchange completes a result.xml file is saved to the C:\Inbox folder and contains the result of the message exchange.</span></span>  
  
#### <a name="to-cleanup-optional"></a><span data-ttu-id="505e7-158">정리하려면(옵션)</span><span class="sxs-lookup"><span data-stu-id="505e7-158">To cleanup (Optional)</span></span>  
  
1.  <span data-ttu-id="505e7-159">Cleanup.cmd를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="505e7-159">Run Cleanup.cmd.</span></span>  
  
    1.  <span data-ttu-id="505e7-160">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 명령 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="505e7-160">Open a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt.</span></span>  
  
    2.  <span data-ttu-id="505e7-161">이 샘플에서 사용할 폴더로 이동하고 Cleanup.cmd를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="505e7-161">Navigate to the folder for this sample and run Cleanup.cmd.</span></span>  
  
2.  <span data-ttu-id="505e7-162">서비스의 가상 응용 프로그램을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="505e7-162">Remove the virtual application for the services.</span></span>  
  
    1.  <span data-ttu-id="505e7-163">실행 하 여 인터넷 정보 서비스 (IIS) 관리자를 열고 `Inetmgr.exe` 명령 프롬프트에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="505e7-163">Open the Internet Information Services (IIS) Manager by running `Inetmgr.exe` from a command prompt.</span></span>  
  
    2.  <span data-ttu-id="505e7-164">기본 웹 사이트를 찾아 제거는 **개인** 가상 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="505e7-164">Browse to the default Web site and remove the **private** virtual directory.</span></span>  
  
3.  <span data-ttu-id="505e7-165">이 샘플에 사용하기 위해 설정한 큐를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="505e7-165">Remove the queues set up for this sample.</span></span>  
  
    1.  <span data-ttu-id="505e7-166">실행 하 여 컴퓨터 관리 콘솔을 열고 `Compmgmt.msc` 명령 프롬프트에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="505e7-166">Open the Computer Management console by running `Compmgmt.msc` from a command prompt.</span></span>  
  
    2.  <span data-ttu-id="505e7-167">확장 **서비스 및 응용 프로그램**, **메시지 큐**, **개인 큐**합니다.</span><span class="sxs-lookup"><span data-stu-id="505e7-167">Expand **Service and Applications**, **Message Queuing**, **Private Queues**.</span></span>  
  
    3.  <span data-ttu-id="505e7-168">durableduplex/service1.xamlx 및 durableduplex/service2.xamlx 큐를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="505e7-168">Delete the durableduplex/service1.xamlx and durableduplex/service2.xamlx queues.</span></span>  
  
4.  <span data-ttu-id="505e7-169">C:\Inbox 디렉터리를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="505e7-169">Remove the C:\Inbox directory.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="505e7-170">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="505e7-170">The samples may already be installed on your machine.</span></span> <span data-ttu-id="505e7-171">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="505e7-171">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="505e7-172">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="505e7-172">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="505e7-173">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="505e7-173">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\DurableDuplex`