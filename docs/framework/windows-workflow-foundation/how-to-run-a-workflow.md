---
title: "방법: 워크플로 실행"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: f814ff82-fe2b-4614-aebb-b768c3e61179
caps.latest.revision: "33"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2a41bf5c1f7a12e98ac10295af5b2608c8bf3a46
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-run-a-workflow"></a><span data-ttu-id="dd9a0-102">방법: 워크플로 실행</span><span class="sxs-lookup"><span data-stu-id="dd9a0-102">How to: Run a Workflow</span></span>
<span data-ttu-id="dd9a0-103">이 항목에서는 Windows Workflow Foundation 초보자를 위한 자습서에 포함된 일련의 항목 중 하나로, 워크플로 호스트를 만들고 이전 [How to: Create a Workflow](../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow.md) 항목에서 정의한 워크플로를 실행하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9a0-103">This topic is a continuation of the Windows Workflow Foundation Getting Started tutorial and discusses how to create a workflow host and run the workflow defined in the previous [How to: Create a Workflow](../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow.md) topic.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dd9a0-104">초보자를 위한 자습서의 각 항목은 이전 항목을 바탕으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9a0-104">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="dd9a0-105">이 항목을 진행하려면 먼저 [How to: Create an Activity](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md) 및 [How to: Create a Workflow](../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow.md)를 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9a0-105">To complete this topic you must first complete [How to: Create an Activity](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md) and [How to: Create a Workflow](../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dd9a0-106">자습서의 전체 버전을 다운로드하려면 [Windows Workflow Foundation(WF45) - 초보자를 위한 자습서](http://go.microsoft.com/fwlink/?LinkID=248976)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dd9a0-106">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](http://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
### <a name="to-create-the-workflow-host-project"></a><span data-ttu-id="dd9a0-107">워크플로 호스트 프로젝트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="dd9a0-107">To create the workflow host project</span></span>  
  
1.  <span data-ttu-id="dd9a0-108">이전 솔루션을 엽니다 [하는 방법: 활동 만들기](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md) 를 사용 하 여 항목 [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9a0-108">Open the solution from the previous [How to: Create an Activity](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md) topic by using [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)].</span></span>  
  
2.  <span data-ttu-id="dd9a0-109">**솔루션 탐색기** 에서 **WF45GettingStartedTutorial** 솔루션을 마우스 오른쪽 단추로 클릭하고 **추가**, **새 프로젝트**를 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9a0-109">Right-click the **WF45GettingStartedTutorial** solution in **Solution Explorer** and select **Add**, **New Project**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="dd9a0-110">**솔루션 탐색기** 창이 표시되어 있지 않으면 **보기** 메뉴에서 **솔루션 탐색기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9a0-110">If the **Solution Explorer** window is not displayed, select **Solution Explorer** from the **View** menu.</span></span>  
  
3.  <span data-ttu-id="dd9a0-111">**설치됨** 노드에서 **Visual C#**, **워크플로** (또는 **Visual Basic**, **워크플로**)를 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9a0-111">In the **Installed** node, select **Visual C#**, **Workflow** (or **Visual Basic**, **Workflow**).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="dd9a0-112">**설치됨** 노드의 **다른 언어** 노드 아래에는 Visual Studio에서 기본 언어로 구성된 프로그래밍 언어에 따라 **Visual C#** 또는 **Visual Basic** 노드가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9a0-112">Depending on which programming language is configured as the primary language in Visual Studio, the **Visual C#** or **Visual Basic** node may be under the **Other Languages** node in the **Installed** node.</span></span>  
  
     <span data-ttu-id="dd9a0-113">.NET Framework 버전 드롭다운 목록에서 **.NET Framework 4.5** 가 선택되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9a0-113">Ensure that **.NET Framework 4.5** is selected in the .NET Framework version drop-down list.</span></span> <span data-ttu-id="dd9a0-114">**워크플로** 목록에서 **워크플로 콘솔 응용 프로그램** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9a0-114">Select **Workflow Console Application** from the **Workflow** list.</span></span> <span data-ttu-id="dd9a0-115">`NumberGuessWorkflowHost` 이름 **상자에** 를 입력하고 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9a0-115">Type `NumberGuessWorkflowHost` into the **Name** box and click **OK**.</span></span> <span data-ttu-id="dd9a0-116">이렇게 하면 기본 워크플로 호스팅 지원이 포함된 시작 워크플로 응용 프로그램이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="dd9a0-116">This creates a starter workflow application with basic workflow hosting support.</span></span> <span data-ttu-id="dd9a0-117">이 기본 호스팅 코드를 수정하고 이를 사용하여 워크플로 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9a0-117">This basic hosting code is modified and used to run the workflow application.</span></span>  
  
4.  <span data-ttu-id="dd9a0-118">**솔루션 탐색기** 에서 새로 추가한 **NumberGuessWorkflowHost** 프로젝트를 마우스 오른쪽 단추로 클릭하고 **참조 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9a0-118">Right-click the newly added **NumberGuessWorkflowHost** project in **Solution Explorer** and select **Add Reference**.</span></span> <span data-ttu-id="dd9a0-119">**참조 추가** 목록에서 **솔루션** 을 선택하고 **NumberGuessWorkflowActivities**옆의 확인란을 선택한 다음 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9a0-119">Select **Solution** from the **Add Reference** list, check the checkbox beside **NumberGuessWorkflowActivities**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="dd9a0-120">**솔루션 탐색기** 에서 **Workflow1.xaml** 을 마우스 오른쪽 단추로 클릭하고 **삭제**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9a0-120">Right-click **Workflow1.xaml** in **Solution Explorer** and choose **Delete**.</span></span> <span data-ttu-id="dd9a0-121">**확인** 을 클릭하여 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9a0-121">Click **OK** to confirm.</span></span>  
  
### <a name="to-modify-the-workflow-hosting-code"></a><span data-ttu-id="dd9a0-122">워크플로 호스팅 코드를 수정하려면</span><span class="sxs-lookup"><span data-stu-id="dd9a0-122">To modify the workflow hosting code</span></span>  
  
1.  <span data-ttu-id="dd9a0-123">**솔루션 탐색기** 에서 **Program.cs** 또는 **Module1.vb** 를 두 번 클릭하여 코드를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9a0-123">Double-click **Program.cs** or **Module1.vb** in **Solution Explorer** to display the code.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="dd9a0-124">**솔루션 탐색기** 창이 표시되어 있지 않으면 **보기** 메뉴에서 **솔루션 탐색기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9a0-124">If the **Solution Explorer** window is not displayed, select **Solution Explorer** from the **View** menu.</span></span>  
  
     <span data-ttu-id="dd9a0-125">이 프로젝트는 **워크플로 콘솔 응용 프로그램** 템플릿을 사용하여 만들었기 때문에 **Program.cs** 또는 **Module1.vb** 에 다음과 같은 기본 워크플로 호스팅 코드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9a0-125">Because this project was created by using the **Workflow Console Application** template, **Program.cs** or **Module1.vb** contains the following basic workflow hosting code.</span></span>  
  
    ```vb  
    ' Create and cache the workflow definition  
    Activity workflow1 = new Workflow1()  
    WorkflowInvoker.Invoke(workflow1)  
    ```  
  
    ```csharp  
    // Create and cache the workflow definition  
    Activity workflow1 = new Workflow1();  
    WorkflowInvoker.Invoke(workflow1);  
    ```  
  
     <span data-ttu-id="dd9a0-126">이 생성된 호스팅 코드에서는 <xref:System.Activities.WorkflowInvoker>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9a0-126">This generated hosting code uses <xref:System.Activities.WorkflowInvoker>.</span></span> <span data-ttu-id="dd9a0-127"><xref:System.Activities.WorkflowInvoker> 는 메서드 호출과 같은 방식으로 워크플로를 호출하기 위한 간단한 방법을 제공하며, 지속성을 사용하지 않는 워크플로에만 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9a0-127"><xref:System.Activities.WorkflowInvoker> provides a simple way for invoking a workflow as if it were a method call and can be used only for workflows that do not use persistence.</span></span> <span data-ttu-id="dd9a0-128"><xref:System.Activities.WorkflowApplication> 은 수명 주기 이벤트 알림, 실행 제어, 책갈피 다시 시작 및 지속성을 비롯한 다양한 워크플로 실행 모델을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9a0-128"><xref:System.Activities.WorkflowApplication> provides a richer model for executing workflows that includes notification of life-cycle events, execution control, bookmark resumption, and persistence.</span></span> <span data-ttu-id="dd9a0-129">이 예제에서는 책갈피를 사용하며 <xref:System.Activities.WorkflowApplication> 을 사용하여 워크플로를 호스트합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9a0-129">This example uses bookmarks and <xref:System.Activities.WorkflowApplication> is used for hosting the workflow.</span></span> <span data-ttu-id="dd9a0-130">기존 `using` using **또는** Imports **문 아래의** Program.cs **또는** Module1.vb **위에 다음** 또는 **Imports** 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9a0-130">Add the following `using` or **Imports** statement at the top of **Program.cs** or **Module1.vb** below the existing **using** or **Imports** statements.</span></span>  
  
    ```vb  
    Imports NumberGuessWorkflowActivities  
    Imports System.Threading  
    ```  
  
    ```csharp  
    using NumberGuessWorkflowActivities;  
    using System.Threading;  
    ```  
  
     <span data-ttu-id="dd9a0-131"><xref:System.Activities.WorkflowInvoker> 를 사용하는 코드 행을 다음과 같은 기본 <xref:System.Activities.WorkflowApplication> 호스팅 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="dd9a0-131">Replace the lines of code that use <xref:System.Activities.WorkflowInvoker> with the following basic <xref:System.Activities.WorkflowApplication> hosting code.</span></span> <span data-ttu-id="dd9a0-132">이 샘플 호스팅 코드는 워크플로를 호스팅 및 호출하기 위한 기본 단계를 보여 주지만 이 항목에서 워크플로를 실행하는 기능은 아직 포함하고 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9a0-132">This sample hosting code demonstrates the basic steps for hosting and invoking a workflow, but does not yet contain the functionality to successfully run the workflow from this topic.</span></span> <span data-ttu-id="dd9a0-133">다음 단계에서는 응용 프로그램이 완료될 때까지 이 기본 코드를 수정하고 기능을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9a0-133">In the following steps, this basic code is modified and additional features are added until the application is complete.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="dd9a0-134">이러한 예제의 `Workflow1` 을 이전 `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`, `StateMachineNumberGuessWorkflow`또는 [How to: Create a Workflow](../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow.md) 로 바꾸세요.</span><span class="sxs-lookup"><span data-stu-id="dd9a0-134">Please replace `Workflow1` in these examples with `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`, or `StateMachineNumberGuessWorkflow`, depending on which workflow you completed in the previous [How to: Create a Workflow](../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow.md) step.</span></span> <span data-ttu-id="dd9a0-135">`Workflow1` 을 바꾸지 않으면 워크플로를 빌드하거나 실행할 때 빌드 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9a0-135">If you do not replace `Workflow1` then you will get build errors when you try and build or run the workflow.</span></span>  
  
     [!code-csharp[CFX_WF_GettingStarted#4](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/extrasnippets.cs#4)]
     [!code-vb[CFX_WF_GettingStarted#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/extrasnippets.vb#4)]  
  
     <span data-ttu-id="dd9a0-136">이 코드는 <xref:System.Activities.WorkflowApplication>을 만들고 세 가지 워크플로 수명 주기 이벤트를 구독한 다음 <xref:System.Activities.WorkflowApplication.Run%2A>을 호출하여 워크플로를 시작하고 워크플로가 완료될 때까지 대기합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9a0-136">This code creates a <xref:System.Activities.WorkflowApplication>, subscribes to three workflow life-cycle events, starts the workflow with a call to <xref:System.Activities.WorkflowApplication.Run%2A>, and then waits for the workflow to complete.</span></span> <span data-ttu-id="dd9a0-137">워크플로가 완료되면 <xref:System.Threading.AutoResetEvent> 가 설정되고 호스트 응용 프로그램이 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd9a0-137">When the workflow completes, the <xref:System.Threading.AutoResetEvent> is set and the host application completes.</span></span>  
  
### <a name="to-set-input-arguments-of-a-workflow"></a><span data-ttu-id="dd9a0-138">워크플로의 입력 인수를 설정하려면</span><span class="sxs-lookup"><span data-stu-id="dd9a0-138">To set input arguments of a workflow</span></span>  
  
1.  <span data-ttu-id="dd9a0-139">**Program.cs** 또는 **Module1.vb** 맨 위의 기존 `using` 또는 `Imports` 문 아래에 다음 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9a0-139">Add the following statement at the top of **Program.cs** or **Module1.vb** below the existing `using` or `Imports` statements.</span></span>  
  
     [!code-csharp[CFX_WF_GettingStarted#5](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#5)]
     [!code-vb[CFX_WF_GettingStarted#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#5)]  
  
2.  <span data-ttu-id="dd9a0-140">새로운 <xref:System.Activities.WorkflowApplication> 을 만드는 코드 행을 코드 생성 시 매개 변수 사전을 만들어 워크플로에 전달하는 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="dd9a0-140">Replace the line of code that creates the new <xref:System.Activities.WorkflowApplication> with the following code that creates and passes a dictionary of parameters to the workflow when it is created.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="dd9a0-141">이러한 예제의 `Workflow1` 을 이전 `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`, `StateMachineNumberGuessWorkflow`또는 [How to: Create a Workflow](../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow.md) 로 바꾸세요.</span><span class="sxs-lookup"><span data-stu-id="dd9a0-141">Please replace `Workflow1` in these examples with `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`, or `StateMachineNumberGuessWorkflow`, depending on which workflow you completed in the previous [How to: Create a Workflow](../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow.md) step.</span></span> <span data-ttu-id="dd9a0-142">`Workflow1` 을 바꾸지 않으면 워크플로를 빌드하거나 실행할 때 빌드 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9a0-142">If you do not replace `Workflow1` then you will get build errors when you try and build or run the workflow.</span></span>  
  
     [!code-csharp[CFX_WF_GettingStarted#6](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#6)]
     [!code-vb[CFX_WF_GettingStarted#6](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#6)]  
  
     <span data-ttu-id="dd9a0-143">이 사전에는 `MaxNumber`키와 함께 요소 하나가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9a0-143">This dictionary contains one element with a key of `MaxNumber`.</span></span> <span data-ttu-id="dd9a0-144">입력 사전의 키는 워크플로 루트 활동의 입력 인수에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9a0-144">Keys in the input dictionary correspond to input arguments on the root activity of the workflow.</span></span> <span data-ttu-id="dd9a0-145">`MaxNumber` 는 워크플로에서 임의로 생성되는 숫자의 상한을 결정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd9a0-145">`MaxNumber` is used by the workflow to determine the upper bound for the randomly generated number.</span></span>  
  
### <a name="to-retrieve-output-arguments-of-a-workflow"></a><span data-ttu-id="dd9a0-146">워크플로의 출력 인수를 검색하려면</span><span class="sxs-lookup"><span data-stu-id="dd9a0-146">To retrieve output arguments of a workflow</span></span>  
  
1.  <span data-ttu-id="dd9a0-147"><xref:System.Activities.WorkflowApplication.Completed%2A> 처리기를 수정하여 워크플로에서 사용된 횟수를 검색하고 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9a0-147">Modify the <xref:System.Activities.WorkflowApplication.Completed%2A> handler to retrieve and display the number of turns used by the workflow.</span></span>  
  
     [!code-csharp[CFX_WF_GettingStarted#7](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#7)]
     [!code-vb[CFX_WF_GettingStarted#7](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#7)]  
  
### <a name="to-resume-a-bookmark"></a><span data-ttu-id="dd9a0-148">책갈피를 다시 시작하려면</span><span class="sxs-lookup"><span data-stu-id="dd9a0-148">To resume a bookmark</span></span>  
  
1.  <span data-ttu-id="dd9a0-149">기존 `Main` 선언 바로 뒤 <xref:System.Threading.AutoResetEvent> 메서드 위에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9a0-149">Add the following code at the top of the `Main` method just after the existing <xref:System.Threading.AutoResetEvent> declaration.</span></span>  
  
     [!code-csharp[CFX_WF_GettingStarted#8](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#8)]
     [!code-vb[CFX_WF_GettingStarted#8](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#8)]  
  
2.  <span data-ttu-id="dd9a0-150"><xref:System.Activities.WorkflowApplication.Idle%2A> 에서 세 개의 기존 워크플로 수명 주기 처리기 바로 아래에 다음 `Main`처리기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9a0-150">Add the following <xref:System.Activities.WorkflowApplication.Idle%2A> handler just below the existing three workflow life-cycle handlers in `Main`.</span></span>  
  
     [!code-csharp[CFX_WF_GettingStarted#9](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#9)]
     [!code-vb[CFX_WF_GettingStarted#9](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#9)]  
  
     <span data-ttu-id="dd9a0-151">워크플로가 다음 추측을 대기하는 유휴 상태가 될 때마다 이 처리기가 호출되고 `idleAction` <xref:System.Threading.AutoResetEvent> 가 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd9a0-151">Each time the workflow becomes idle waiting for the next guess, this handler is called and the `idleAction` <xref:System.Threading.AutoResetEvent> is set.</span></span> <span data-ttu-id="dd9a0-152">다음 단계의 코드에서는 `idleEvent` 와 `syncEvent` 를 사용하여 워크플로가 다음 추측을 대기하고 있는지 아니면 완료되었는지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9a0-152">The code in the following step uses `idleEvent` and `syncEvent` to determine whether the workflow is waiting for the next guess or is complete.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="dd9a0-153">이 예제에서는 호스트 응용 프로그램이 <xref:System.Activities.WorkflowApplication.Completed%2A> 및 <xref:System.Activities.WorkflowApplication.Idle%2A> 처리기에서 자동 재설정 이벤트를 사용하여 호스트 응용 프로그램을 워크플로 진행률과 동기화합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9a0-153">In this example, the host application uses auto-reset events in the <xref:System.Activities.WorkflowApplication.Completed%2A> and <xref:System.Activities.WorkflowApplication.Idle%2A> handlers to synchronize the host application with the progress of the workflow.</span></span> <span data-ttu-id="dd9a0-154">책갈피를 다시 시작하기 전에 워크플로를 차단하고 워크플로가 유휴 상태가 될 때까지 기다릴 필요는 없지만, 이 예제에서는 호스트에서 워크플로가 완료되었는지 아니면 <xref:System.Activities.Bookmark>를 사용하여 추가 사용자 입력을 대기하고 있는지 확인하기 위해 동기화 이벤트가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9a0-154">It is not necessary to block and wait for the workflow to become idle before resuming a bookmark, but in this example the synchronization events are required so the host knows whether the workflow is complete or whether it is waiting on more user input by using the <xref:System.Activities.Bookmark>.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="dd9a0-155"> [Bookmarks](../../../docs/framework/windows-workflow-foundation/bookmarks.md)를 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9a0-155"> [Bookmarks](../../../docs/framework/windows-workflow-foundation/bookmarks.md).</span></span>  
  
3.  <span data-ttu-id="dd9a0-156">`WaitOne`호출을 제거한 다음, 사용자 입력을 수집하고 <xref:System.Activities.Bookmark>를 다시 시작하는 코드로 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9a0-156">Remove the call to `WaitOne`, and replace it with code to gather input from the user and resume the <xref:System.Activities.Bookmark>.</span></span>  
  
     <span data-ttu-id="dd9a0-157">다음 코드 행을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9a0-157">Remove the following line of code.</span></span>  
  
     [!code-csharp[CFX_WF_GettingStarted#10](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/extrasnippets.cs#10)]
     [!code-vb[CFX_WF_GettingStarted#10](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/extrasnippets.vb#10)]  
  
     <span data-ttu-id="dd9a0-158">코드 행을 다음 예로 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9a0-158">Replace it with the following example.</span></span>  
  
     [!code-csharp[CFX_WF_GettingStarted#11](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#11)]
     [!code-vb[CFX_WF_GettingStarted#11](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#11)]  
  
##  <a name="BKMK_ToRunTheApplication"></a> <span data-ttu-id="dd9a0-159">응용 프로그램을 빌드하고 실행하려면</span><span class="sxs-lookup"><span data-stu-id="dd9a0-159">To build and run the application</span></span>  
  
1.  <span data-ttu-id="dd9a0-160">**솔루션 탐색기** 에서 **NumberGuessWorkflowHost** 를 마우스 오른쪽 단추로 클릭하고 **시작 프로젝트로 설정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9a0-160">Right-click **NumberGuessWorkflowHost** in **Solution Explorer** and select **Set as StartUp Project**.</span></span>  
  
2.  <span data-ttu-id="dd9a0-161">Ctrl+F5를 눌러 응용 프로그램을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9a0-161">Press CTRL+F5 to build and run the application.</span></span> <span data-ttu-id="dd9a0-162">가능한 한 적은 횟수로 숫자를 추측해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="dd9a0-162">Try to guess the number in as few turns as possible.</span></span>  
  
     <span data-ttu-id="dd9a0-163">다른 스타일의 워크플로 중 하나로 응용 프로그램을 시도하려면 `Workflow1` 을 만드는 코드의 <xref:System.Activities.WorkflowApplication> 을 원하는 워크플로 스타일에 따라 `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`또는 `StateMachineNumberGuessWorkflow`로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="dd9a0-163">To try the application with one of the other styles of workflow, replace `Workflow1` in the code that creates the <xref:System.Activities.WorkflowApplication> with `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`, or `StateMachineNumberGuessWorkflow`, depending on which workflow style you desire.</span></span>  
  
     [!code-csharp[CFX_WF_GettingStarted#6](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#6)]
     [!code-vb[CFX_WF_GettingStarted#6](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#6)]  
  
     <span data-ttu-id="dd9a0-164">워크플로 응용 프로그램에 지속성을 추가하는 방법은 다음 항목 [How to: Create and Run a Long Running Workflow](../../../docs/framework/windows-workflow-foundation/how-to-create-and-run-a-long-running-workflow.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dd9a0-164">For instructions about how to add persistence to a workflow application, see the next topic, [How to: Create and Run a Long Running Workflow](../../../docs/framework/windows-workflow-foundation/how-to-create-and-run-a-long-running-workflow.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="dd9a0-165">예</span><span class="sxs-lookup"><span data-stu-id="dd9a0-165">Example</span></span>  
 <span data-ttu-id="dd9a0-166">다음 예는 `Main` 메서드에 대한 완전한 코드 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="dd9a0-166">The following example is the complete code listing for the `Main` method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dd9a0-167">이러한 예제의 `Workflow1` 을 이전 `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`, `StateMachineNumberGuessWorkflow`또는 [How to: Create a Workflow](../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow.md) 로 바꾸세요.</span><span class="sxs-lookup"><span data-stu-id="dd9a0-167">Please replace `Workflow1` in these examples with `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`, or `StateMachineNumberGuessWorkflow`, depending on which workflow you completed in the previous [How to: Create a Workflow](../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow.md) step.</span></span> <span data-ttu-id="dd9a0-168">`Workflow1` 을 바꾸지 않으면 워크플로를 빌드하거나 실행할 때 빌드 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9a0-168">If you do not replace `Workflow1` then you will get build errors when you try and build or run the workflow.</span></span>  
  
 [!code-csharp[CFX_WF_GettingStarted#12](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#12)]
 [!code-vb[CFX_WF_GettingStarted#12](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#12)]  
  
## <a name="see-also"></a><span data-ttu-id="dd9a0-169">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dd9a0-169">See Also</span></span>  
 <xref:System.Activities.WorkflowApplication>  
 <xref:System.Activities.Bookmark>  
 [<span data-ttu-id="dd9a0-170">Windows Workflow Foundation 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="dd9a0-170">Windows Workflow Foundation Programming</span></span>](../../../docs/framework/windows-workflow-foundation/programming.md)  
 [<span data-ttu-id="dd9a0-171">초보자를 위한 자습서</span><span class="sxs-lookup"><span data-stu-id="dd9a0-171">Getting Started Tutorial</span></span>](../../../docs/framework/windows-workflow-foundation/getting-started-tutorial.md)  
 [<span data-ttu-id="dd9a0-172">방법: 워크플로 만들기</span><span class="sxs-lookup"><span data-stu-id="dd9a0-172">How to: Create a Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow.md)  
 [<span data-ttu-id="dd9a0-173">방법: 장기 실행 워크플로 만들기 및 실행</span><span class="sxs-lookup"><span data-stu-id="dd9a0-173">How to: Create and Run a Long Running Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-create-and-run-a-long-running-workflow.md)  
 [<span data-ttu-id="dd9a0-174">워크플로에서 입력 대기</span><span class="sxs-lookup"><span data-stu-id="dd9a0-174">Waiting for Input in a Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/waiting-for-input-in-a-workflow.md)  
 [<span data-ttu-id="dd9a0-175">워크플로 호스팅</span><span class="sxs-lookup"><span data-stu-id="dd9a0-175">Hosting Workflows</span></span>](../../../docs/framework/windows-workflow-foundation/hosting-workflows.md)
