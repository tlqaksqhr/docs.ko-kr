---
title: Durable Delay
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 220ec240-b958-430c-81ff-b734a6aa97ae
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3b8afc9de0369a440ba9aa7cdacc4a43066ec2ff
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2017
---
# <a name="durable-delay"></a><span data-ttu-id="3fe4f-102">Durable Delay</span><span class="sxs-lookup"><span data-stu-id="3fe4f-102">Durable Delay</span></span>
<span data-ttu-id="3fe4f-103">이 샘플에서는 지속적 지연을 사용하는 방법을 보여 줍니다. 지속적 지연은 지연되는 동안 워크플로를 영구적인 장치에 유지하는 지연입니다.</span><span class="sxs-lookup"><span data-stu-id="3fe4f-103">This sample demonstrates how to use a durable delay, which is a delay that persists the workflow to a durable device during the delay.</span></span> <span data-ttu-id="3fe4f-104">샘플 워크플로에는 지연으로 구분되는 콘솔 대상의 두 메시지가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fe4f-104">The sample workflow contains two messages to the console that are separated by a delay.</span></span> <span data-ttu-id="3fe4f-105">지연이 트리거되면 워크플로가 언로드된 다음 메모리에 다시 로드되기 전에 워크플로 인스턴스 저장소에서 5초 동안 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="3fe4f-105">When the delay is triggered, the workflow is unloaded and waits 5 seconds in the workflow instance store before being reloaded in memory.</span></span>  
  
## <a name="workflow-details"></a><span data-ttu-id="3fe4f-106">워크플로 세부 정보</span><span class="sxs-lookup"><span data-stu-id="3fe4f-106">Workflow Details</span></span>  
 <span data-ttu-id="3fe4f-107">워크플로 서비스 호스트에서는 워크플로를 호스트할 뿐 아니라 워크플로 인스턴스를 로드하거나 언로드하여 워크플로 인스턴스를 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="3fe4f-107">The workflow service host hosts the workflow and manages the workflow instances by loading and unloading them.</span></span> <span data-ttu-id="3fe4f-108">워크플로 정의의 인스턴스를 시작하기 위해 이 샘플에서는 워크플로의 <xref:System.ServiceModel.Activities.Receive> 활동에 메시지를 보내는 프록시를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3fe4f-108">To start an instance of the workflow definition, the sample sets a proxy that sends a message to the <xref:System.ServiceModel.Activities.Receive> activity in the workflow.</span></span> <span data-ttu-id="3fe4f-109"><xref:System.ServiceModel.Activities.Receive.CanCreateInstance%2A> 속성이 `true`로 설정되어 있으므로 이 활동에서는 메시지를 받으면 워크플로의 새 인스턴스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fe4f-109">The <xref:System.ServiceModel.Activities.Receive.CanCreateInstance%2A> property is set to `true`, enabling it to create a new instance of the workflow once it receives a message.</span></span>  
  
 <span data-ttu-id="3fe4f-110">다음 목록에서는 초기화 중 워크플로 서비스에 의한 설정 과정을 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3fe4f-110">The following list details the set-up by the workflow service host during initialization.</span></span>  
  
1.  <span data-ttu-id="3fe4f-111">주소가 http://localhost:8080/Client인 서비스 호스트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3fe4f-111">Creates a service host with an address (http://localhost:8080/Client).</span></span>  
  
2.  <span data-ttu-id="3fe4f-112">워크플로 내의 <xref:System.ServiceModel.Activities.Receive> 활동과 통신할 수 있도록 서비스 호스트에 끝점을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3fe4f-112">Creates an endpoint in the service host to enable communication with the <xref:System.ServiceModel.Activities.Receive> activity inside the workflow.</span></span>  
  
3.  <span data-ttu-id="3fe4f-113">SQL 인스턴스 저장소를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3fe4f-113">Sets up a SQL instance store.</span></span>  
  
4.  <span data-ttu-id="3fe4f-114">워크플로 서비스 호스트에서 워크플로 인스턴스를 SQL 지속성 저장소로 언로드할 조건을 지정하는 언로드 인스턴스 동작을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3fe4f-114">Adds an unload instance behavior that specifies the conditions under which the workflow service host should unload a workflow instance to the SQL persistence store.</span></span> <span data-ttu-id="3fe4f-115">이 샘플의 경우 지연이 트리거되어 워크플로가 유휴 상태가 되는 직후 인스턴스를 언로드합니다.</span><span class="sxs-lookup"><span data-stu-id="3fe4f-115">For this sample, it unloads the instance immediately after the workflow goes idle (when the delay is triggered).</span></span>  
  
5.  <span data-ttu-id="3fe4f-116">워크플로의 <xref:System.ServiceModel.Activities.Receive> 활동에 메시지를 보내는 프록시를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3fe4f-116">Creates the proxy that sends a message to the <xref:System.ServiceModel.Activities.Receive> activity in the workflow.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="3fe4f-117">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="3fe4f-117">To use this sample</span></span>  
  
1.  <span data-ttu-id="3fe4f-118">지속성 데이터베이스를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="3fe4f-118">Set up the persistence database.</span></span>  
  
    1.  <span data-ttu-id="3fe4f-119">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 명령 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3fe4f-119">Open a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt.</span></span>  
  
    2.  <span data-ttu-id="3fe4f-120">로 이동 된 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 디렉터리 (C:\Windows\Microsoft.NET\Framework\v4 합니다. X\\).</span><span class="sxs-lookup"><span data-stu-id="3fe4f-120">Navigate to the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] directory (C:\Windows\Microsoft.NET\Framework\v4.X\\).</span></span>  
  
    3.  <span data-ttu-id="3fe4f-121">WorkflowManagementService.exe.config 파일을 편집하고 다음 연결 문자열을 <`database`> 요소 내에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3fe4f-121">Edit the WorkflowManagementService.exe.config file and add the following connection string inside the <`database`> element.</span></span>  
  
        ```xml  
        <database connectionString="Data Source=localhost\SQLEXPRESS;Initial Catalog=DefaultSampleStore;Integrated Security=True;Asynchronous Processing=True" />  
        ```  
  
    4.  <span data-ttu-id="3fe4f-122">DurableDelay\CS 디렉터리로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3fe4f-122">Navigate to the DurableDelay\CS directory.</span></span>  
  
    5.  <span data-ttu-id="3fe4f-123">Setup.cmd.를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3fe4f-123">Run Setup.cmd.</span></span>  
  
2.  <span data-ttu-id="3fe4f-124">실행 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 마우스 오른쪽 단추로 클릭 하 여 승격 된 권한을 사용 하는 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 아이콘을 선택 하면 **관리자 권한으로 실행**합니다.</span><span class="sxs-lookup"><span data-stu-id="3fe4f-124">Run [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] using elevated permissions by right-clicking the [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] icon and selecting **Run as administrator**.</span></span>  
  
3.  <span data-ttu-id="3fe4f-125">Delay.sln 솔루션 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3fe4f-125">Open the Delay.sln solution file.</span></span>  
  
4.  <span data-ttu-id="3fe4f-126">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="3fe4f-126">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
5.  <span data-ttu-id="3fe4f-127">Ctrl+F5를 눌러 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3fe4f-127">Press CTRL+F5 to run the solution.</span></span>  
  
#### <a name="to-uninstall-this-sample"></a><span data-ttu-id="3fe4f-128">이 샘플을 제거하려면</span><span class="sxs-lookup"><span data-stu-id="3fe4f-128">To uninstall this sample</span></span>  
  
1.  <span data-ttu-id="3fe4f-129">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 명령 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3fe4f-129">Open a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt.</span></span>  
  
2.  <span data-ttu-id="3fe4f-130">DurableDelay\CS 디렉터리로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3fe4f-130">Navigate to the DurableDelay\CS directory.</span></span>  
  
3.  <span data-ttu-id="3fe4f-131">Cleanup.cmd를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3fe4f-131">Run Cleanup.cmd.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3fe4f-132">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fe4f-132">The samples may already be installed on your machine.</span></span> <span data-ttu-id="3fe4f-133">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="3fe4f-133">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="3fe4f-134">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="3fe4f-134">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="3fe4f-135">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fe4f-135">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\DurableDelay`