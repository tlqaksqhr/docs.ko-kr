---
title: "워크플로 인스턴스 만들기 및 실행"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 19d27f47-0491-4569-8f53-51bc1d940e80
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3d6dd2f27a6db9770231a5c947c98614d4f6f175
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="creating-and-running-a-workflow-instance"></a><span data-ttu-id="5cf9b-102">워크플로 인스턴스 만들기 및 실행</span><span class="sxs-lookup"><span data-stu-id="5cf9b-102">Creating and Running a Workflow Instance</span></span>
<span data-ttu-id="5cf9b-103">이 샘플에서는 워크플로 인스턴스를 실행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5cf9b-103">This sample shows how to run a workflow instance.</span></span> <span data-ttu-id="5cf9b-104">동기적 실행 방법과 비동기적 실행 방법을 모두 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5cf9b-104">It shows how to execute it synchronously and asynchronously.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="5cf9b-105">세부 항목</span><span class="sxs-lookup"><span data-stu-id="5cf9b-105">Demonstrates</span></span>  
 <span data-ttu-id="5cf9b-106"><xref:System.Activities.WorkflowInvoker>, <xref:System.Activities.WorkflowApplication>.</span><span class="sxs-lookup"><span data-stu-id="5cf9b-106"><xref:System.Activities.WorkflowInvoker>, <xref:System.Activities.WorkflowApplication>.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="5cf9b-107">토론</span><span class="sxs-lookup"><span data-stu-id="5cf9b-107">Discussion</span></span>  
 <span data-ttu-id="5cf9b-108">샘플의 첫 번째 부분에서는 <xref:System.Activities.WorkflowInvoker.Invoke%2A>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5cf9b-108">The first part of the sample uses <xref:System.Activities.WorkflowInvoker.Invoke%2A>.</span></span> <span data-ttu-id="5cf9b-109">이는 워크플로를 실행하는 가장 기본적인 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="5cf9b-109">This is the most basic way to execute a workflow.</span></span> <span data-ttu-id="5cf9b-110"><xref:System.Activities.WorkflowInvoker.Invoke%2A>를 사용할 경우 워크플로를 동기적으로 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cf9b-110">Workflows executed with <xref:System.Activities.WorkflowInvoker.Invoke%2A> are executed synchronously.</span></span>  
  
 <span data-ttu-id="5cf9b-111">샘플의 다음 부분에서는 <xref:System.Activities.WorkflowApplication> 클래스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5cf9b-111">The second part of the sample uses the <xref:System.Activities.WorkflowApplication> class.</span></span> <span data-ttu-id="5cf9b-112"><xref:System.Activities.WorkflowApplication> 클래스를 사용하면 실행 중인 워크플로와 상호 작용하고 워크플로를 비동기적으로 실행하는 등 각 인스턴스를 보다 효과적으로 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cf9b-112"><xref:System.Activities.WorkflowApplication> enables you to have more control over each instance, including the ability to interact with the running workflow and to run the workflow asynchronously.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5cf9b-113">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cf9b-113">The samples may already be installed on your machine.</span></span> <span data-ttu-id="5cf9b-114">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="5cf9b-114">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="5cf9b-115">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="5cf9b-115">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="5cf9b-116">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cf9b-116">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\CreatingWorkflowInstances`  
  
## <a name="see-also"></a><span data-ttu-id="5cf9b-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5cf9b-117">See Also</span></span>  
 [<span data-ttu-id="5cf9b-118">WorkflowInvoker 및 WorkflowApplication 사용</span><span class="sxs-lookup"><span data-stu-id="5cf9b-118">Using WorkflowInvoker and WorkflowApplication</span></span>](../../../../docs/framework/windows-workflow-foundation/using-workflowinvoker-and-workflowapplication.md)
