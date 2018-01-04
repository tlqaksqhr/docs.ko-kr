---
title: "WorkflowHostingEndpoint 다시 시작 책갈피"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a708064f-50b0-4751-b44e-d5410d08d451
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 140ff5282447c2a2307dee325645fc1f3f0497fe
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="workflowhostingendpoint-resume-bookmark"></a><span data-ttu-id="2e693-102">WorkflowHostingEndpoint 다시 시작 책갈피</span><span class="sxs-lookup"><span data-stu-id="2e693-102">WorkflowHostingEndpoint Resume Bookmark</span></span>
<span data-ttu-id="2e693-103">이 샘플에서는 <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint>를 <xref:System.ServiceModel.Activities.WorkflowServiceHost>와 함께 사용하여 워크플로 인스턴스를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2e693-103">This sample demonstrates how the <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> can be used with <xref:System.ServiceModel.Activities.WorkflowServiceHost> to create workflow instances.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="2e693-104">세부 항목</span><span class="sxs-lookup"><span data-stu-id="2e693-104">Demonstrates</span></span>  
 <span data-ttu-id="2e693-105"><xref:System.ServiceModel.Activities.WorkflowHostingEndpoint>, <xref:System.ServiceModel.Activities.WorkflowServiceHost></span><span class="sxs-lookup"><span data-stu-id="2e693-105"><xref:System.ServiceModel.Activities.WorkflowHostingEndpoint>, <xref:System.ServiceModel.Activities.WorkflowServiceHost></span></span>  
  
## <a name="discussion"></a><span data-ttu-id="2e693-106">토론</span><span class="sxs-lookup"><span data-stu-id="2e693-106">Discussion</span></span>  
 <span data-ttu-id="2e693-107">이 샘플에서는 <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint>를 사용하여 워크플로 인스턴스를 만듭니다. 이 워크플로 인스턴스는 <xref:System.ServiceModel.Activities.WorkflowServiceHost>를 통해 호스트됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e693-107">This sample uses the <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> to create a workflow instance hosted using <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span> <span data-ttu-id="2e693-108"><xref:System.ServiceModel.Activities.WorkflowHostingEndpoint>는 다음 시나리오에 사용할 수 있는 <xref:System.ServiceModel.Activities.WorkflowServiceHost>에 대한 확장성 지점입니다.</span><span class="sxs-lookup"><span data-stu-id="2e693-108"><xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> is an extensibility point for <xref:System.ServiceModel.Activities.WorkflowServiceHost> that can be used in the following scenarios:</span></span>  
  
-   <span data-ttu-id="2e693-109">새 워크플로 인스턴스 만들기</span><span class="sxs-lookup"><span data-stu-id="2e693-109">Creating new workflow instances.</span></span>  
  
-   <span data-ttu-id="2e693-110"><xref:System.ServiceModel.Activities.WorkflowServiceHost>에 호스트되는 워크플로 인스턴스에 대한 책갈피 다시 시작</span><span class="sxs-lookup"><span data-stu-id="2e693-110">Resuming bookmarks on a workflow instance hosted in a <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span>  
  
 <span data-ttu-id="2e693-111">여기에 포함되어 있는 샘플 끝점은 워크플로를 만들고 인스턴스 ID를 반환하거나 특정 ID의 인스턴스를 만드는 작업을 제공하는 계약을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="2e693-111">The sample endpoint that is included exposes a contract that provides operations to create a workflow and return an instance ID, or to create an instance with a specific ID.</span></span> <span data-ttu-id="2e693-112">샘플 콘솔 응용 프로그램에서는 기본 워크플로 정의를 사용하여 <xref:System.ServiceModel.Activities.WorkflowServiceHost> 인스턴스를 만들고 호스트에 `CreationEndpoint`를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2e693-112">The sample console application creates a <xref:System.ServiceModel.Activities.WorkflowServiceHost> instance with a basic workflow definition, and adds a `CreationEndpoint` to the host.</span></span> <span data-ttu-id="2e693-113">그런 다음 끝점에 대해 `Create` 작업을 호출하여 새 워크플로 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2e693-113">It then calls the `Create` operation on the endpoint to create a new workflow instance.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="2e693-114">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="2e693-114">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="2e693-115">솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="2e693-115">Build the solution.</span></span>  
  
2.  <span data-ttu-id="2e693-116">응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2e693-116">Run the application.</span></span> <span data-ttu-id="2e693-117">워크플로 인스턴스를 만들 때 인스턴스 ID를 포함하는 메시지가 `CreationEndpoint` 콘솔에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e693-117">The `CreationEndpoint` console shows a message that includes the instance ID when the workflow instance is created.</span></span> <span data-ttu-id="2e693-118">"Hello World!" 메시지</span><span class="sxs-lookup"><span data-stu-id="2e693-118">The message "Hello World!"</span></span> <span data-ttu-id="2e693-119">가 성공적으로 다시 시작 책갈피의 워크플로 통해 인쇄 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e693-119">is printed by the workflow on successful resumption of the bookmark.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2e693-120">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e693-120">The samples may already be installed on your machine.</span></span> <span data-ttu-id="2e693-121">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="2e693-121">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="2e693-122">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="2e693-122">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="2e693-123">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e693-123">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\ResumeBookmarkEndpoint`
