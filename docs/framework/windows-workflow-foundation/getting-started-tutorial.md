---
title: "Tutorial2 시작"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WF [WF], getting started
- Windows Workflow Foundation [WF], getting started
ms.assetid: c2d3585f-6b1a-4d4f-9865-bd7cd31c5d42
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f25058071e041ac1e14de2c223750013c8ef1d30
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="getting-started-tutorial"></a><span data-ttu-id="13480-102">초보자를 위한 자습서</span><span class="sxs-lookup"><span data-stu-id="13480-102">Getting Started Tutorial</span></span>
<span data-ttu-id="13480-103">이 단원에는 [!INCLUDE[wf](../../../includes/wf-md.md)] 응용 프로그램 프로그래밍을 소개하는 연습 항목 집합이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13480-103">This section contains a set of walkthrough topics that introduce you to programming [!INCLUDE[wf](../../../includes/wf-md.md)] applications.</span></span> <span data-ttu-id="13480-104">이 항목의 절차를 진행하면서 빌드하는 응용 프로그램은 숫자 추측 게임입니다.</span><span class="sxs-lookup"><span data-stu-id="13480-104">By following the procedures in these topics, you will build an application that is a number guessing game.</span></span> <span data-ttu-id="13480-105">자습서의 첫째 항목에서는 워크플로에 필요한 사용자 지정 활동을 만드는 단계를 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="13480-105">The first topic in the tutorial leads you through the steps to create the custom activities required for the workflow.</span></span> <span data-ttu-id="13480-106">둘째 항목에서는 이러한 활동을 기본 제공 워크플로 활동과 함께 어셈블하여 순서도 워크플로를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="13480-106">In the second topic, these activities are assembled along with built-in workflow activities into a flowchart workflow.</span></span> <span data-ttu-id="13480-107">셋째 항목에서는 워크플로를 실행하기 위한 호스트 응용 프로그램을 구성하고, 넷째 항목에서는 지속성을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="13480-107">In the third topic, the host application is configured to run the workflow, and in the final topic persistence is introduced.</span></span> <span data-ttu-id="13480-108">이 과정의 각 단계는 그 이전 단계를 기반으로 진행되므로 각 단계를 순서대로 완료하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="13480-108">Each step in this process depends on the previous steps, so we recommend that you complete them in order.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="13480-109">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="13480-109">In This Section</span></span>  
 [<span data-ttu-id="13480-110">방법: 활동 만들기</span><span class="sxs-lookup"><span data-stu-id="13480-110">How to: Create an Activity</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md)  
 <span data-ttu-id="13480-111"><xref:System.Activities.NativeActivity%601>에서 파생되는 사용자 지정 활동을 만드는 방법을 설명하고, 활동 디자이너를 사용하여 이 활동과 기본 제공 활동을 하나의 복합 활동으로 구성하는 방법을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="13480-111">Describes how to create a custom activity that derives from <xref:System.Activities.NativeActivity%601>, and how to compose this activity along with a built-in activity into a composite activity using the activity designer.</span></span>  
  
 [<span data-ttu-id="13480-112">방법: 워크플로 만들기</span><span class="sxs-lookup"><span data-stu-id="13480-112">How to: Create a Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow.md)  
 <span data-ttu-id="13480-113">기본 제공 활동과 이전 자습서의 사용자 지정 활동을 사용하여 순서도, 순차 및 상태 시스템 워크플로를 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="13480-113">Describes how to create flowchart, sequential, and state machine workflows by using built-in activities and the custom activities from the preceding tutorial.</span></span>  
  
 [<span data-ttu-id="13480-114">방법: 워크플로 실행</span><span class="sxs-lookup"><span data-stu-id="13480-114">How to: Run a Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md)  
 <span data-ttu-id="13480-115">호스트 환경에서 워크플로를 호출하는 방법, 워크플로 안팎으로 데이터를 전달하는 방법 및 책갈피를 다시 시작하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="13480-115">Describes how to invoke a workflow from a host environment, pass data into and out of a workflow, and how to resume bookmarks.</span></span>  
  
 [<span data-ttu-id="13480-116">방법: 장기 실행 워크플로 만들기 및 실행</span><span class="sxs-lookup"><span data-stu-id="13480-116">How to: Create and Run a Long Running Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-create-and-run-a-long-running-workflow.md)  
 <span data-ttu-id="13480-117">워크플로 응용 프로그램에 지속성을 추가하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="13480-117">Describes how to add persistence to a workflow application.</span></span>  
  
 [<span data-ttu-id="13480-118">방법: 사용자 지정 추적 참가자 만들기</span><span class="sxs-lookup"><span data-stu-id="13480-118">How to: Create a Custom Tracking Participant</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-create-a-custom-tracking-participant.md)  
 <span data-ttu-id="13480-119">사용자 지정 추적 참가자와 추적 프로필을 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="13480-119">Describes how to create a custom tracking participant and tracking profile.</span></span>  
  
 [<span data-ttu-id="13480-120">방법: 여러 버전의 워크플로 Side-by-Side 호스트</span><span class="sxs-lookup"><span data-stu-id="13480-120">How to: Host Multiple Versions of a Workflow Side-by-Side</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md)  
 <span data-ttu-id="13480-121">`WorkflowIdentity`를 사용하여 여러 버전의 워크플로를 함께 호스트하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="13480-121">Describes how to use `WorkflowIdentity` to host multiple versions of a workflow side-by-side.</span></span>  
  
 [<span data-ttu-id="13480-122">방법: 실행 중인 워크플로 인스턴스의 정의 업데이트</span><span class="sxs-lookup"><span data-stu-id="13480-122">How to: Update the Definition of a Running Workflow Instance</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md)  
 <span data-ttu-id="13480-123">동적 업데이트를 사용하여 실행 중인 워크플로 인스턴스를 수정하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="13480-123">Describes how to use dynamic update to modify running workflow instances.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13480-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="13480-124">See Also</span></span>  
 [<span data-ttu-id="13480-125">Windows Workflow Foundation 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="13480-125">Windows Workflow Foundation Programming</span></span>](../../../docs/framework/windows-workflow-foundation/programming.md)
