---
title: "버퍼링되는 수신"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9d46d9b9-96c9-4531-9695-ab526b4d704a
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a7a486d3fbfb520ffe3b32c392566e5147c5dfcc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="buffered-receive"></a><span data-ttu-id="2c7df-102">버퍼링되는 수신</span><span class="sxs-lookup"><span data-stu-id="2c7df-102">Buffered Receive</span></span>
<span data-ttu-id="2c7df-103">이 샘플에서는 [!INCLUDE[wf](../../../../includes/wf-md.md)]에서 버퍼링된 수신 기능을 설정하고 구성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2c7df-103">This sample demonstrates how to set up and configure the buffered receive feature in [!INCLUDE[wf](../../../../includes/wf-md.md)].</span></span> <span data-ttu-id="2c7df-104">버퍼링된 수신 기능을 사용하면 워크플로 작성자가 메시지의 수신 순서에 신경을 쓰지 않고 워크플로를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7df-104">Buffered receive allows the workflow author to create a workflow without having to worry about the order in which messages are received.</span></span> <span data-ttu-id="2c7df-105">버퍼링된 수신 기능은 메시지를 로컬로 버퍼링하고 워크플로에서 메시지를 받을 준비가 되었을 때 이를 전달하는 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7df-105">The buffered receive feature buffers messages locally and delivers them when the workflow is ready to receive them.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="2c7df-106">세부 항목</span><span class="sxs-lookup"><span data-stu-id="2c7df-106">Demonstrates</span></span>  
 <span data-ttu-id="2c7df-107">메시징 활동에 버퍼링된 수신 기능을 사용하여 순서에 상관없이 메시지 처리</span><span class="sxs-lookup"><span data-stu-id="2c7df-107">Out-of-order message processing using buffered receive with messaging activities.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2c7df-108">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7df-108">The samples may already be installed on your machine.</span></span> <span data-ttu-id="2c7df-109">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="2c7df-109">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="2c7df-110">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="2c7df-110">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="2c7df-111">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7df-111">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\BufferedReceive`  
  
## <a name="discussion"></a><span data-ttu-id="2c7df-112">토론</span><span class="sxs-lookup"><span data-stu-id="2c7df-112">Discussion</span></span>  
 <span data-ttu-id="2c7df-113">이 샘플에서 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 서비스는 [!INCLUDE[wf1](../../../../includes/wf1-md.md)]에 의해 구현되며 일련의 <xref:System.ServiceModel.Activities.Receive> 활동을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7df-113">In this sample, a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service is implemented using [!INCLUDE[wf1](../../../../includes/wf1-md.md)] and has a sequence of <xref:System.ServiceModel.Activities.Receive> activities.</span></span> <span data-ttu-id="2c7df-114">이 워크플로는 간단한 대출 승인 프로세스를 모델링하며, 승인 여부를 결정해야 할 대출에 대한 알림 세 건을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7df-114">This workflow models a simple loan approval process where the workflow expects three notifications for a loan to be approved.</span></span> <span data-ttu-id="2c7df-115">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 클라이언트 응용 프로그램은 서비스에서 예상하는 순서와는 반대로 대출 관련 알림 세 건을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="2c7df-115">A [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] client application sends three correlated notifications in the reverse order of what the service expects.</span></span> <span data-ttu-id="2c7df-116">그러나 이 서비스에서는 버퍼링된 수신 기능을 사용하므로 순서가 맞지 않는 각 메시지를 버퍼링한 후 워크플로에서 해당 메시지를 받을 준비가 되었을 때 이를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7df-116">Because the buffered receive feature is turned on at the service, each out-of-order message is buffered at the service and processed as the workflow becomes ready to receive it.</span></span>  
  
 <span data-ttu-id="2c7df-117">버퍼링된 수신 기능을 사용하려면 바인딩을 통해 <xref:System.ServiceModel.Activities.ReceiveContent>가 지원되어야 하므로 이 서비스에서는 <xref:System.ServiceModel.NetMsmqBinding>을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7df-117">The buffered receive feature requires <xref:System.ServiceModel.Activities.ReceiveContent> support from the binding, therefore the service uses <xref:System.ServiceModel.NetMsmqBinding>.</span></span> <span data-ttu-id="2c7df-118">이 바인딩에는 특별한 구성이 필요하지 않으므로 기본 설정이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c7df-118">No special configuration is required for the binding, so the defaults are used.</span></span>  
  
```xml  
<endpoint address ="net.msmq://localhost/private/LoanService/Service1.xamlx"  
                  binding="netMsmqBinding"  
                  contract="ILoanService"/>  
```  
  
 <span data-ttu-id="2c7df-119">이 서비스에서는 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>를 사용하여 서비스에 대한 메타데이터도 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7df-119">The service also exposes metadata for the service using <xref:System.ServiceModel.Description.ServiceMetadataBehavior>.</span></span>  
  
 <span data-ttu-id="2c7df-120">마찬가지로, 클라이언트 끝점은 <xref:System.ServiceModel.NetMsmqBinding>을 사용하여 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c7df-120">Similarly, the client endpoint is configured using <xref:System.ServiceModel.NetMsmqBinding>.</span></span> <span data-ttu-id="2c7df-121">클라이언트 코드 및 구성을 사용 하 여 생성 되는 **서비스 참조 추가** 의 기능 [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7df-121">The client code and configuration is generated by using the **Add Service Reference** feature of [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].</span></span> <span data-ttu-id="2c7df-122">다음 예제에서는 App.config 파일에 생성된 클라이언트 끝점을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2c7df-122">The following example is the generated client endpoint in the App.config file.</span></span>  
  
```xml  
<endpoint address="net.msmq://localhost/private/LoanService/Service1.xamlx"  
                binding="netMsmqBinding" bindingConfiguration="NetMsmqBinding_ILoanService"  
                contract="ServiceReference1.ILoanService" name="NetMsmqBinding_ILoanService" />  
```  
  
 <span data-ttu-id="2c7df-123">이 샘플에는 다음과 같은 Windows 구성 요소를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7df-123">This sample requires that the following Windows components are enabled:</span></span>  
  
1.  [!INCLUDE[iis60](../../../../includes/iis60-md.md)]  
  
2.  [!INCLUDE[iis60](../../../../includes/iis60-md.md)]<span data-ttu-id="2c7df-124"> 관리 호환성, 메타베이스 및 구성 호환성</span><span class="sxs-lookup"><span data-stu-id="2c7df-124"> Management Compatibility, Metabase, and Configuration Compatibility</span></span>  
  
3.  <span data-ttu-id="2c7df-125">World Wide Web 서비스, 응용 프로그램 개발 기능 및 ASP.NET</span><span class="sxs-lookup"><span data-stu-id="2c7df-125">World Wide Web Services, Application Development Features, and ASP.NET</span></span>  
  
4.  <span data-ttu-id="2c7df-126">MSMQ(Microsoft Message Queue) Server</span><span class="sxs-lookup"><span data-stu-id="2c7df-126">Microsoft Message Queues (MSMQ) Server</span></span>  
  
#### <a name="to-set-up-and-build-the-sample"></a><span data-ttu-id="2c7df-127">샘플을 설치하고 빌드하려면</span><span class="sxs-lookup"><span data-stu-id="2c7df-127">To set up, and build the sample</span></span>  
  
1.  <span data-ttu-id="2c7df-128">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 명령 프롬프트에서 `aspnet_regiis –I`을 입력하여 ASP.NET을 등록하고 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="2c7df-128">At a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt, register ASP.NET by typing `aspnet_regiis –I` and press ENTER.</span></span>  
  
2.  <span data-ttu-id="2c7df-129">관리자 권한으로 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7df-129">Run [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] as an Administrator.</span></span>  
  
3.  <span data-ttu-id="2c7df-130">LoanService.sln을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2c7df-130">Open LoanService.sln.</span></span>  
  
4.  <span data-ttu-id="2c7df-131">LoanService 프로젝트에 대 한 가상 디렉터리를 만드는 원하면 선택 묻는 메시지가 나타나면 **예**합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7df-131">When asked if you would like to create the virtual directories for the LoanService project, select **Yes**.</span></span>  
  
#### <a name="to-set-up-the-service-queues"></a><span data-ttu-id="2c7df-132">서비스 큐를 설정하려면</span><span class="sxs-lookup"><span data-stu-id="2c7df-132">To set up the service queues</span></span>  
  
1.  <span data-ttu-id="2c7df-133">F5 키를 눌러 LoanClient 응용 프로그램을 실행합니다. 이 응용 프로그램은 큐를 만들고 Service1.xamlx에 정의되어 있는 서비스를 활성화하는 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7df-133">Press F5 to run the LoanClient application that creates the queues and activates the service defined in Service1.xamlx.</span></span>  
  
2.  <span data-ttu-id="2c7df-134">열기는 **컴퓨터 관리** 명령 프롬프트에서 Compmgmt.msc를 실행 하 여 콘솔.</span><span class="sxs-lookup"><span data-stu-id="2c7df-134">Open the **Computer Management** console by running Compmgmt.msc from a command prompt.</span></span>  
  
3.  <span data-ttu-id="2c7df-135">에 **컴퓨터 관리** 콘솔에서 **서비스**, **응용 프로그램**, **메시지 큐**, **개인 큐** .</span><span class="sxs-lookup"><span data-stu-id="2c7df-135">In the **Computer Management** console, expand **Service**, **Applications**, **Message Queuing**, **Private Queues**.</span></span>  
  
4.  <span data-ttu-id="2c7df-136">Loanservice/service1.xamlx 큐를 마우스 오른쪽 단추로 클릭 하 고 선택 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7df-136">Right-click the loanservice/service1.xamlx queue and select **Properties**.</span></span>  
  
5.  <span data-ttu-id="2c7df-137">선택 된 **보안** 탭을 추가 **누구나 메시지 받기**, **메시지 보기** 및 **메시지 보내기** 사용 권한.</span><span class="sxs-lookup"><span data-stu-id="2c7df-137">Select the **Security** tab, and add **Everyone Receives Message**, **Peek Message** and **Send Message** permissions.</span></span>  
  
6.  <span data-ttu-id="2c7df-138">[!INCLUDE[iis60](../../../../includes/iis60-md.md)] 관리자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2c7df-138">Open the [!INCLUDE[iis60](../../../../includes/iis60-md.md)] Manager.</span></span>  
  
7.  <span data-ttu-id="2c7df-139">찾아 **서버**, **사이트**, **기본 웹 사이트**, **개인**, **LoanService** 선택 **고급 옵션**</span><span class="sxs-lookup"><span data-stu-id="2c7df-139">Browse to **Server**, **Sites**, **Default Web site**, **Private**, **LoanService** and select **Advanced Options**</span></span>  
  
8.  <span data-ttu-id="2c7df-140">변경 된 **사용할 수 있는 프로토콜** 되도록 **http**, **net.msmq**합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7df-140">Change the **Enabled Protocols** to be **http**, **net.msmq**.</span></span>  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="2c7df-141">이 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="2c7df-141">To run the sample</span></span>  
  
1.  <span data-ttu-id="2c7df-142">http://localhost/private/loanservice/service1.xamlx로 이동하여 서비스가 실행되고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7df-142">Browse to http://localhost/private/loanservice/service1.xamlx to ensure that the service is running.</span></span>  
  
2.  <span data-ttu-id="2c7df-143">F5 키를 눌러 LoanClient 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7df-143">Press F5 to run the LoanClient application.</span></span> <span data-ttu-id="2c7df-144">워크플로를 완료하면 메시지 교환 결과가 포함된 out.txt 파일이 C:\Inbox에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c7df-144">Once the workflow is complete, an out.txt file should be saved to C:\Inbox that contains the result of the message exchange.</span></span>  
  
#### <a name="to-clean-up"></a><span data-ttu-id="2c7df-145">정리하려면</span><span class="sxs-lookup"><span data-stu-id="2c7df-145">To clean up</span></span>  
  
1.  <span data-ttu-id="2c7df-146">열기는 **컴퓨터 관리** 명령 프롬프트에서 Compmgmt.msc를 실행 하 여 콘솔.</span><span class="sxs-lookup"><span data-stu-id="2c7df-146">Open the **Computer Management** console by running Compmgmt.msc from a command prompt.</span></span>  
  
2.  <span data-ttu-id="2c7df-147">확장 **서비스** 및 **응용 프로그램**, **메시지 큐**, **개인 큐**합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7df-147">Expand **Service** and **Applications**, **Message Queuing**, **Private Queues**.</span></span>  
  
3.  <span data-ttu-id="2c7df-148">loanservice/service1.xamlx 큐를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7df-148">Delete the loanservice/service1.xamlx queue.</span></span>  
  
4.  <span data-ttu-id="2c7df-149">C:\Inbox 디렉터리를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="2c7df-149">Remove the C:\Inbox directory.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2c7df-150">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7df-150">The samples may already be installed on your machine.</span></span> <span data-ttu-id="2c7df-151">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="2c7df-151">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="2c7df-152">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="2c7df-152">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="2c7df-153">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c7df-153">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\BufferedReceive`
