---
title: "일시 중단된 인스턴스 관리"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f5ca3faa-ba1f-4857-b92c-d927e4b29598
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 02c3d6b3a522dd4337dcdf22f884f63cdddd4aa4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="suspended-instance-management"></a><span data-ttu-id="592f7-102">일시 중단된 인스턴스 관리</span><span class="sxs-lookup"><span data-stu-id="592f7-102">Suspended Instance Management</span></span>
<span data-ttu-id="592f7-103">이 샘플에서는 일시 중단된 워크플로 인스턴스를 관리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="592f7-103">This sample demonstrates how to manage workflow instances that have been suspended.</span></span>  <span data-ttu-id="592f7-104"><xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>의 기본 동작은 `AbandonAndSuspend`입니다.</span><span class="sxs-lookup"><span data-stu-id="592f7-104">The default action for <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> is `AbandonAndSuspend`.</span></span> <span data-ttu-id="592f7-105">즉, 기본적으로 <xref:System.ServiceModel.WorkflowServiceHost>에서 호스트되는 워크플로 인스턴스에서 처리되지 않은 예외가 throw될 경우 인스턴스가 메모리에서 삭제(중단)되고 영속/지속적 버전의 인스턴스는 일시 중단된 인스턴스로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="592f7-105">This means that by default, unhandled exceptions thrown from a workflow instance hosted in the <xref:System.ServiceModel.WorkflowServiceHost> will cause the instance to be disposed from memory (abandoned) and the durable/persisted version of the instance to be marked as suspended.</span></span> <span data-ttu-id="592f7-106">일시 중단된 워크플로 인스턴스는 일시 중단이 해제될 때까지 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="592f7-106">A suspended workflow instance will not be able to run until it has been unsuspended.</span></span>  
  
 <span data-ttu-id="592f7-107">이 샘플에서는 일시 중단된 인스턴스를 쿼리하는 명령줄 유틸리티를 구현하는 방법과 사용자에게 해당 인스턴스를 다시 시작하거나 종료하는 옵션을 제공하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="592f7-107">The sample shows how a command-line utility can be implemented to query for suspended instances, and how to give the user the option to resume or terminate the instance.</span></span> <span data-ttu-id="592f7-108">이 샘플에서는 워크플로 서비스가 의도적으로 예외를 throw하여 일시 중단 상태가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="592f7-108">In this sample, a workflow service intentionally throws an exception, causing it to become suspended.</span></span> <span data-ttu-id="592f7-109">그런 다음 명령줄 유틸리티를 사용하여 인스턴스를 쿼리하고 이후에 인스턴스를 다시 시작하거나 종료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="592f7-109">The command-line utility can then be used to query for the instance and subsequently resume or terminate the instance.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="592f7-110">세부 항목</span><span class="sxs-lookup"><span data-stu-id="592f7-110">Demonstrates</span></span>  
 <span data-ttu-id="592f7-111"><xref:System.ServiceModel.WorkflowServiceHost>에서 <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> 및 <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>가 있는 [!INCLUDE[wf](../../../../includes/wf-md.md)]</span><span class="sxs-lookup"><span data-stu-id="592f7-111"><xref:System.ServiceModel.WorkflowServiceHost> with <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> and <xref:System.ServiceModel.Activities.WorkflowControlEndpoint> in [!INCLUDE[wf](../../../../includes/wf-md.md)].</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="592f7-112">토론</span><span class="sxs-lookup"><span data-stu-id="592f7-112">Discussion</span></span>  
 <span data-ttu-id="592f7-113">이 샘플에서 구현하는 명령줄 유틸리티는 [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]에서 제공되는 SQL 인스턴스 저장소 구현에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="592f7-113">The command-line utility implemented in this sample is specific to the SQL instance store implementation that ships in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span></span> <span data-ttu-id="592f7-114">인스턴스 저장소의 사용자 지정 구현이 있는 경우 샘플의 `WorkflowInstanceCommand` 구현을 현재 인스턴스 저장소와 관련된 구현으로 바꿔 이 유틸리티를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="592f7-114">If you have a custom implementation of the instance store, then you can adapt this utility by replacing the `WorkflowInstanceCommand` implementations in the sample with implementations that are specific to your instance store.</span></span>  
  
 <span data-ttu-id="592f7-115">제공된 구현에서는 SQL 인스턴스 저장소에 대해 직접 SQL 명령을 실행하여 일시 중단된 인스턴스를 나열하고, 인스턴스를 다시 시작하거나 종료하기 위해 <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>에 추가된 <xref:System.ServiceModel.WorkflowServiceHost>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="592f7-115">The provided implementation runs SQL commands against the SQL instance store directly to list suspended instances, and it relies on a <xref:System.ServiceModel.Activities.WorkflowControlEndpoint> added to the <xref:System.ServiceModel.WorkflowServiceHost> in order to resume or terminate the instances.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="592f7-116">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="592f7-116">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="592f7-117">이 샘플에는 다음과 같은 Windows 구성 요소를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="592f7-117">This sample requires that the following Windows components are enabled:</span></span>  
  
    1.  <span data-ttu-id="592f7-118">MSMQ(Microsoft Message Queue) Server</span><span class="sxs-lookup"><span data-stu-id="592f7-118">Microsoft Message Queues (MSMQ) Server</span></span>  
  
    2.  <span data-ttu-id="592f7-119">SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="592f7-119">SQL Server Express</span></span>  
  
2.  <span data-ttu-id="592f7-120">SQL Server 데이터베이스를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="592f7-120">Set up the SQL Server database.</span></span>  
  
    1.  <span data-ttu-id="592f7-121">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 명령 프롬프트에서 다음 SuspendedInstanceManagement 샘플 디렉터리에서 "setup.cmd"를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="592f7-121">From a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt, run "setup.cmd" from the SuspendedInstanceManagement sample directory, which does the following:</span></span>  
  
        1.  <span data-ttu-id="592f7-122">SQL Server Express를 사용하여 지속성 데이터베이스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="592f7-122">Creates a persistence database using SQL Server Express.</span></span> <span data-ttu-id="592f7-123">지속성 데이터베이스가 이미 있으면 삭제된 다음 다시 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="592f7-123">If the persistence database already exists, then it is dropped and re-created</span></span>  
  
        2.  <span data-ttu-id="592f7-124">지속성 데이터베이스를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="592f7-124">Sets up the database for persistence.</span></span>  
  
        3.  <span data-ttu-id="592f7-125">지속성 데이터베이스를 설정할 때 정의된 InstanceStoreUsers 역할에 IIS APPPOOL\DefaultAppPool 및 NT AUTHORITY\Network Service를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="592f7-125">Adds IIS APPPOOL\DefaultAppPool and NT AUTHORITY\Network Service to the InstanceStoreUsers role that was defined when setting up the database for persistence.</span></span>  
  
3.  <span data-ttu-id="592f7-126">서비스 큐를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="592f7-126">Set up the service queue.</span></span>  
  
    1.  <span data-ttu-id="592f7-127">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]를 마우스 오른쪽 단추로 클릭는 **SampleWorkflowApp** 프로젝트 **시작 프로젝트로 설정**합니다.</span><span class="sxs-lookup"><span data-stu-id="592f7-127">In [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], right-click the **SampleWorkflowApp** project and click **Set as Startup Project**.</span></span>  
  
    2.  <span data-ttu-id="592f7-128">컴파일 및 키를 눌러 SampleWorkflowApp 실행 **F5**합니다.</span><span class="sxs-lookup"><span data-stu-id="592f7-128">Compile and run the SampleWorkflowApp by pressing **F5**.</span></span> <span data-ttu-id="592f7-129">이렇게 하면 필요한 큐가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="592f7-129">This will create the required queue.</span></span>  
  
    3.  <span data-ttu-id="592f7-130">키를 눌러 **Enter** SampleWorkflowApp를 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="592f7-130">Press **Enter** to stop the SampleWorkflowApp.</span></span>  
  
    4.  <span data-ttu-id="592f7-131">명령 프롬프트에서 Compmgmt.msc를 실행하여 컴퓨터 관리 콘솔을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="592f7-131">Open the Computer Management console by running Compmgmt.msc from a command prompt.</span></span>  
  
    5.  <span data-ttu-id="592f7-132">확장 **서비스 및 응용 프로그램**, **메시지 큐**, **개인 큐**합니다.</span><span class="sxs-lookup"><span data-stu-id="592f7-132">Expand **Service and Applications**, **Message Queuing**, **Private Queues**.</span></span>  
  
    6.  <span data-ttu-id="592f7-133">마우스 오른쪽 단추로 클릭는 **ReceiveTx** 큐에 대기 하 고 선택 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="592f7-133">Right click the **ReceiveTx** queue and select **Properties**.</span></span>  
  
    7.  <span data-ttu-id="592f7-134">선택 된 **보안** 탭 하 고 허용 **Everyone** 수 있는 권한이 있어야 **메시지 받기**, **메시지 보기**, 및  **메시지 보내기**합니다.</span><span class="sxs-lookup"><span data-stu-id="592f7-134">Select the **Security** tab and allow **Everyone** to have permissions to **Receive Message**, **Peek Message**, and **Send Message**.</span></span>  
  
4.  <span data-ttu-id="592f7-135">이제 샘플을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="592f7-135">Now, run the sample.</span></span>  
  
    1.  <span data-ttu-id="592f7-136">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]를 눌러 디버깅 없이 SampleWorkflowApp 프로젝트를 다시 실행 **Ctrl + f 5**합니다.</span><span class="sxs-lookup"><span data-stu-id="592f7-136">In [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], run the SampleWorkflowApp project again without debugging by pressing **Ctrl+F5**.</span></span> <span data-ttu-id="592f7-137">두 끝점 주소가 콘솔 창에 출력됩니다. 이 주소 중 하나를 응용 프로그램 끝점에 대한 주소이고, 다른 하나는 <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="592f7-137">Two endpoint addresses will be printed in the console window: one for the application endpoint and then other from the <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>.</span></span> <span data-ttu-id="592f7-138">그런 다음 워크플로 인스턴스가 만들어지고, 해당 인스턴스에 대한 추적 레코드가 콘솔 창에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="592f7-138">A workflow instance is then created, and tracking records for that instance will appear in the console window.</span></span> <span data-ttu-id="592f7-139">워크플로 인스턴스를 예외를 throw하며, 인스턴스가 일시 중단되고 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="592f7-139">The workflow instance will throw an exception causing the instance to be suspended and aborted.</span></span>  
  
    2.  <span data-ttu-id="592f7-140">명령줄 유틸리티를 사용하여 모든 인스턴스에 대해 추가 동작을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="592f7-140">The command-line utility can then be used to take further action on any of these instances.</span></span> <span data-ttu-id="592f7-141">명령줄 인수에 대한 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="592f7-141">The syntax for command line arguments is as follows::</span></span>  
  
         `SuspendedInstanceManagement -Command:[CommandName] -Server:[ServerName] -Database:[DatabaseName] -InstanceId:[InstanceId]`  
  
         <span data-ttu-id="592f7-142">지원되는 명령은 `Query`, `Resume` 및 `Terminate`이며,</span><span class="sxs-lookup"><span data-stu-id="592f7-142">The supported commands are: `Query`, `Resume`, and `Terminate`.</span></span>  <span data-ttu-id="592f7-143">InstanceId 스위치는 `Resume` 및 `Terminate` 작업에만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="592f7-143">The InstanceId switch is only required for `Resume` and `Terminate` operations.</span></span>  
  
#### <a name="to-cleanup-optional"></a><span data-ttu-id="592f7-144">정리하려면(옵션)</span><span class="sxs-lookup"><span data-stu-id="592f7-144">To cleanup (Optional)</span></span>  
  
1.  <span data-ttu-id="592f7-145">`vs2010` 명령 프롬프트에서 Compmgmt.msc를 실행하여 컴퓨터 관리 콘솔을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="592f7-145">Open the Computer Management console by running Compmgmt.msc from a `vs2010` command prompt.</span></span>  
  
2.  <span data-ttu-id="592f7-146">확장 **서비스 및 응용 프로그램**, **메시지 큐**, **개인 큐**합니다.</span><span class="sxs-lookup"><span data-stu-id="592f7-146">Expand **Service and Applications**, **Message Queuing**, **Private Queues**.</span></span>  
  
3.  <span data-ttu-id="592f7-147">삭제 된 **ReceiveTx** 큐입니다.</span><span class="sxs-lookup"><span data-stu-id="592f7-147">Delete the **ReceiveTx** queue.</span></span>  
  
4.  <span data-ttu-id="592f7-148">지속성 데이터베이스를 제거하려면 cleanup.cmd를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="592f7-148">To remove the persistence database, run cleanup.cmd.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="592f7-149">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="592f7-149">The samples may already be installed on your machine.</span></span> <span data-ttu-id="592f7-150">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="592f7-150">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="592f7-151">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="592f7-151">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="592f7-152">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="592f7-152">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Application\SuspendedInstanceManagement`
