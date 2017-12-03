---
title: 'How to: Create a Workflow'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 87234108-8e21-4cb3-9340-4a1a13f3f98c
caps.latest.revision: "34"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b20ca4258204f938d611f431abc5668b88f167b1
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-create-a-workflow"></a><span data-ttu-id="7a0d8-102">How to: Create a Workflow</span><span class="sxs-lookup"><span data-stu-id="7a0d8-102">How to: Create a Workflow</span></span>
<span data-ttu-id="7a0d8-103">기본 제공 활동뿐 아니라 사용자 지정 활동에서도 워크플로를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a0d8-103">Workflows can be constructed from built-in activities as well as from custom activities.</span></span> <span data-ttu-id="7a0d8-104">이 섹션 단계와 같은 기본 제공 활동을 모두 사용 하는 워크플로 만드는 과정에서이 항목의 <xref:System.Activities.Statements.Flowchart> 활동과 이전 사용자 지정 활동 [하는 방법: 활동 만들기](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md) 항목.</span><span class="sxs-lookup"><span data-stu-id="7a0d8-104">This topics in this section step through creating a workflow that uses both built-in activities such as the <xref:System.Activities.Statements.Flowchart> activity, and the custom activities from the previous [How to: Create an Activity](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md) topic.</span></span> <span data-ttu-id="7a0d8-105">이 워크플로는 숫자 추측 게임을 모델링합니다.</span><span class="sxs-lookup"><span data-stu-id="7a0d8-105">The workflow models a number guessing game.</span></span> <span data-ttu-id="7a0d8-106">자습서를 완료하려면 이 단원의 한 항목만 필요합니다. 원하는 스타일을 선택하고 해당 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="7a0d8-106">Only one of the topics in this section is required to complete the tutorial; you should pick the style that interests you and follow that step.</span></span> <span data-ttu-id="7a0d8-107">하지만 원할 경우 모든 항목을 완료할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a0d8-107">However, you may complete all of the topics if desired.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7a0d8-108">초보자를 위한 자습서의 각 항목은 이전 항목을 바탕으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a0d8-108">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="7a0d8-109">이 항목을 완료 하려면 먼저 완료 해야 [하는 방법: 활동 만들기](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7a0d8-109">To complete this topic, you must first complete [How to: Create an Activity](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7a0d8-110">자습서의 전체 버전을 다운로드하려면 [Windows Workflow Foundation(WF45) - 초보자를 위한 자습서](http://go.microsoft.com/fwlink/?LinkID=248976)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7a0d8-110">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](http://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7a0d8-111">단원 내용</span><span class="sxs-lookup"><span data-stu-id="7a0d8-111">In This Section</span></span>  
 [<span data-ttu-id="7a0d8-112">방법: 순차 워크플로 만들기</span><span class="sxs-lookup"><span data-stu-id="7a0d8-112">How to: Create a Sequential Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-create-a-sequential-workflow.md)  
 <span data-ttu-id="7a0d8-113"><xref:System.Activities.Statements.Sequence> 활동을 사용하여 순차 워크플로를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7a0d8-113">Describes how to create a sequential workflow using the <xref:System.Activities.Statements.Sequence> activity.</span></span>  
  
 [<span data-ttu-id="7a0d8-114">방법: 순서도 워크플로 만들기</span><span class="sxs-lookup"><span data-stu-id="7a0d8-114">How to: Create a Flowchart Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-create-a-flowchart-workflow.md)  
 <span data-ttu-id="7a0d8-115"><xref:System.Activities.Statements.Flowchart> 활동을 사용하여 순서도 워크플로를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7a0d8-115">Describes how to create a flowchart workflow using the <xref:System.Activities.Statements.Flowchart> activity.</span></span>  
  
 [<span data-ttu-id="7a0d8-116">방법: 상태 시스템 워크플로 만들기</span><span class="sxs-lookup"><span data-stu-id="7a0d8-116">How to: Create a State Machine Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-create-a-state-machine-workflow.md)  
 <span data-ttu-id="7a0d8-117"><xref:System.Activities.Statements.StateMachine> 활동을 사용하여 상태 시스템 워크플로를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7a0d8-117">Describes how to create a state machine workflow using the <xref:System.Activities.Statements.StateMachine> activity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a0d8-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7a0d8-118">See Also</span></span>  
 [<span data-ttu-id="7a0d8-119">Windows Workflow Foundation 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="7a0d8-119">Windows Workflow Foundation Programming</span></span>](../../../docs/framework/windows-workflow-foundation/programming.md)
