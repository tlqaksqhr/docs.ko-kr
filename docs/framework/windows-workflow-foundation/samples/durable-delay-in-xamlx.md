---
title: XAMLX의 지속적 지연
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: efc38df4-2d34-453c-8e59-2c21d1307354
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8fa5a9e4287bcbcb490754b84a8b5060d321f779
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2018
---
# <a name="durable-delay-in-xamlx"></a><span data-ttu-id="a9095-102">XAMLX의 지속적 지연</span><span class="sxs-lookup"><span data-stu-id="a9095-102">Durable Delay in XAMLX</span></span>
<span data-ttu-id="a9095-103">이 샘플에서는 지속적 지연을 사용하는 방법을 보여 줍니다. 지속적 지연은 지연되는 동안 워크플로를 영구적인 장치에 유지하는 지연입니다.</span><span class="sxs-lookup"><span data-stu-id="a9095-103">This sample demonstrates how to use a durable delay, which is a delay that persists the workflow to a durable device during the delay.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a9095-104">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9095-104">The samples may already be installed on your machine.</span></span> <span data-ttu-id="a9095-105">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="a9095-105">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="a9095-106">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="a9095-106">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a9095-107">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9095-107">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\DurableDelayXamlx`  
  
## <a name="discussion"></a><span data-ttu-id="a9095-108">토론</span><span class="sxs-lookup"><span data-stu-id="a9095-108">Discussion</span></span>  
 <span data-ttu-id="a9095-109">샘플 워크플로에는 로컬 파일에 대해 지연으로 구분되는 두 메시지가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9095-109">The sample workflow contains two messages to a local file that are separated by a delay.</span></span> <span data-ttu-id="a9095-110">지연이 트리거되면 워크플로가 언로드된 다음 메모리에 다시 로드되기 전에 워크플로 인스턴스 저장소에서 5초 동안 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="a9095-110">When the delay is triggered, the workflow is unloaded and waits 5 seconds in the workflow instance store before being reloaded in memory.</span></span>  
  
 <span data-ttu-id="a9095-111">.Xamlx 파일은 Visual Studio에서 호스트 된 워크플로 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="a9095-111">The .xamlx file is a workflow service that is hosted in Visual Studio.</span></span> <span data-ttu-id="a9095-112">Visual Studio 워크플로 호스트 하는 워크플로 서비스를 사용 하는 Cassini를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9095-112">Visual Studio uses Cassini that uses a workflow service host to host the workflow.</span></span>  
  
 <span data-ttu-id="a9095-113">워크플로 서비스는 워크플로를 호스트하는 외에도 워크플로 인스턴스를 로드하거나 언로드하는 등의 방법으로 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="a9095-113">In addition to hosting the workflow, the workflow service host manages the workflow instances by loading and unloading them.</span></span> <span data-ttu-id="a9095-114">워크플로 서비스 호스트에서 Windows WF (Workflow Foundation) 정의의 인스턴스를 시작 하려면 메시지를 보내는 클라이언트를 설정의 <xref:System.ServiceModel.Activities.Receive> 워크플로의 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="a9095-114">To start an instance of the Windows Workflow Foundation (WF) definition (on the workflow service host), set a client that sends a message to the <xref:System.ServiceModel.Activities.Receive> activity in the workflow.</span></span> <span data-ttu-id="a9095-115">이 <xref:System.ServiceModel.Activities.Receive>의 <xref:System.ServiceModel.Activities.Receive.CanCreateInstance%2A> 속성은 `true`로 설정되어 있으므로, 메시지를 받으면 워크플로의 새 인스턴스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9095-115">This <xref:System.ServiceModel.Activities.Receive> has its <xref:System.ServiceModel.Activities.Receive.CanCreateInstance%2A> property set to `true`, enabling it to create a new instance of the workflow once it receives a message.</span></span>  
  
 <span data-ttu-id="a9095-116">초기화하는 동안 인스턴스 언로드 동작이 구성 파일에 추가됩니다. 이 구성 파일은 인스턴스를 지속성 저장소(데이터베이스)에 언로드해야 하는 워크플로 서비스 호스트에 지정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9095-116">During initialization, an unload instance behavior is added to the configuration file that specifies to the workflow service host under which it should unload an instance to the persistence store (database).</span></span> <span data-ttu-id="a9095-117">이 샘플의 경우 지연이 트리거되어 워크플로가 유휴 상태가 되는 직후 인스턴스를 언로드합니다.</span><span class="sxs-lookup"><span data-stu-id="a9095-117">For this sample, it unloads the instance immediately after the workflow goes idle (when the delay is triggered).</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="a9095-118">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="a9095-118">To use this sample</span></span>  
  
1.  <span data-ttu-id="a9095-119">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 명령 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a9095-119">Open a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt.</span></span>  
  
2.  <span data-ttu-id="a9095-120">DurableDelayXamlx\CS 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="a9095-120">Navigate to the DurableDelayXamlx\CS folder.</span></span>  
  
3.  <span data-ttu-id="a9095-121">Setup.cmd.를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a9095-121">Run Setup.cmd.</span></span>  
  
4.  <span data-ttu-id="a9095-122">관리자 권한으로 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a9095-122">Run [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] as an administrator.</span></span>  
  
5.  <span data-ttu-id="a9095-123">DurableDelayXamlx.sln 솔루션 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a9095-123">Open the DurableDelayXamlx.sln solution file.</span></span>  
  
6.  <span data-ttu-id="a9095-124">**솔루션 탐색기**솔루션을 마우스 오른쪽 단추로 클릭 하 고 선택 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="a9095-124">In **Solution Explorer**, right-click the solution and select **Properties**.</span></span>  
  
7.  <span data-ttu-id="a9095-125">선택 **여러 개의 시작 프로젝트** 두 프로젝트 설정 하 고 **시작**합니다.</span><span class="sxs-lookup"><span data-stu-id="a9095-125">Select **Multiple startup projects** and set both projects to **Start**.</span></span>  
  
8.  <span data-ttu-id="a9095-126">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="a9095-126">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
9. <span data-ttu-id="a9095-127">Ctrl+F5를 눌러 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a9095-127">To run the solution, press CTRL+F5.</span></span>  
  
#### <a name="to-uninstall-this-sample"></a><span data-ttu-id="a9095-128">이 샘플을 제거하려면</span><span class="sxs-lookup"><span data-stu-id="a9095-128">To uninstall this sample</span></span>  
  
1.  <span data-ttu-id="a9095-129">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 명령 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a9095-129">Open a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt.</span></span>  
  
2.  <span data-ttu-id="a9095-130">DurableDelayXamlx\CS 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="a9095-130">Navigate to the DurableDelayXamlx\CS folder.</span></span>  
  
3.  <span data-ttu-id="a9095-131">Cleanup.cmd를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a9095-131">Run Cleanup.cmd.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a9095-132">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9095-132">The samples may already be installed on your machine.</span></span> <span data-ttu-id="a9095-133">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="a9095-133">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="a9095-134">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="a9095-134">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a9095-135">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9095-135">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\DurableDelayXamlX`
