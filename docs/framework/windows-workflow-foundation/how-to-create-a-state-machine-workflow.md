---
title: "방법: 상태 시스템 워크플로 만들기"
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
ms.assetid: 3ec60e8f-fad4-493e-a426-e7962d7aee8c
caps.latest.revision: "15"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 797cdc425c0f3088aa2b75c0285ca6bea2dd425b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-state-machine-workflow"></a><span data-ttu-id="485cf-102">방법: 상태 시스템 워크플로 만들기</span><span class="sxs-lookup"><span data-stu-id="485cf-102">How to: Create a State Machine Workflow</span></span>
<span data-ttu-id="485cf-103">기본 제공 활동뿐 아니라 사용자 지정 활동에서도 워크플로를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-103">Workflows can be constructed from built-in activities as well as from custom activities.</span></span> <span data-ttu-id="485cf-104">이 항목의 단계와 같은 기본 제공 활동을 모두 사용 하는 워크플로 만드는 따라는 <xref:System.Activities.Statements.StateMachine> 활동과 이전 사용자 지정 활동 [하는 방법: 활동 만들기](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md) 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-104">This topic steps through creating a workflow that uses both built-in activities such as the <xref:System.Activities.Statements.StateMachine> activity, and the custom activities from the previous [How to: Create an Activity](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md) topic.</span></span> <span data-ttu-id="485cf-105">이 워크플로는 숫자 추측 게임을 모델링합니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-105">The workflow models a number guessing game.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="485cf-106">초보자를 위한 자습서의 각 항목은 이전 항목을 바탕으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-106">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="485cf-107">이 항목을 완료 하려면 먼저 완료 해야 [하는 방법: 활동 만들기](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-107">To complete this topic, you must first complete [How to: Create an Activity](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="485cf-108">자습서의 전체 버전을 다운로드하려면 [Windows Workflow Foundation(WF45) - 초보자를 위한 자습서](http://go.microsoft.com/fwlink/?LinkID=248976)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="485cf-108">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](http://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
### <a name="to-create-the-workflow"></a><span data-ttu-id="485cf-109">워크플로를 만들려면</span><span class="sxs-lookup"><span data-stu-id="485cf-109">To create the workflow</span></span>  
  
1.  <span data-ttu-id="485cf-110">마우스 오른쪽 단추로 클릭 **NumberGuessWorkflowActivities** 에 **솔루션 탐색기** 선택 **추가**, **새 항목**합니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-110">Right-click **NumberGuessWorkflowActivities** in **Solution Explorer** and select **Add**, **New Item**.</span></span>  
  
2.  <span data-ttu-id="485cf-111">에 **설치 됨**, **공통 항목** 노드를 **워크플로**합니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-111">In the **Installed**, **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="485cf-112">선택 **활동** 에서 **워크플로** 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-112">Select **Activity** from the **Workflow** list.</span></span>  
  
3.  <span data-ttu-id="485cf-113">형식 `StateMachineNumberGuessWorkflow` 에 **이름** 상자 한 클릭 **추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-113">Type `StateMachineNumberGuessWorkflow` into the **Name** box and click **Add**.</span></span>  
  
4.  <span data-ttu-id="485cf-114">끌어서는 **StateMachine** 활동을는 **상태 시스템** 의 섹션은 **도구 상자** 놓습니다는 **여기에 작업 놓기** 에 레이블 워크플로 디자인 화면입니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-114">Drag a **StateMachine** activity from the **State Machine** section of the **Toolbox** and drop it onto the **Drop activity here** label on the workflow design surface.</span></span>  
  
### <a name="to-create-the-workflow-variables-and-arguments"></a><span data-ttu-id="485cf-115">워크플로 변수와 인수를 만들려면</span><span class="sxs-lookup"><span data-stu-id="485cf-115">To create the workflow variables and arguments</span></span>  
  
1.  <span data-ttu-id="485cf-116">두 번 클릭 **StateMachineNumberGuessWorkflow.xaml** 에 **솔루션 탐색기** 에 표시 되지 않은 경우 워크플로 디자이너를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-116">Double-click **StateMachineNumberGuessWorkflow.xaml** in **Solution Explorer** to display the workflow in the designer, if it is not already displayed.</span></span>  
  
2.  <span data-ttu-id="485cf-117">클릭 **인수** 표시 하려면 워크플로 디자이너 왼쪽 아래에에서는 **인수** 창.</span><span class="sxs-lookup"><span data-stu-id="485cf-117">Click **Arguments** in the lower-left side of the workflow designer to display the **Arguments** pane.</span></span>  
  
3.  <span data-ttu-id="485cf-118">클릭 **인수 만들기**합니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-118">Click **Create Argument**.</span></span>  
  
4.  <span data-ttu-id="485cf-119">형식 `MaxNumber` 에 **이름** 상자 **에** 에서 **방향** 드롭 다운 목록 **Int32** 는 에서**인수 형식이** 드롭 다운 목록 및 다음 인수를 저장 하는 ENTER 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-119">Type `MaxNumber` into the **Name** box, select **In** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER to save the argument.</span></span>  
  
5.  <span data-ttu-id="485cf-120">클릭 **인수 만들기**합니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-120">Click **Create Argument**.</span></span>  
  
6.  <span data-ttu-id="485cf-121">형식 `Turns` 에 **이름** 새로 추가 된 아래에 있는 상자 `MaxNumber` 인수를 **아웃** 에서 **방향** 드롭 다운 목록에서  **Int32** 에서 **인수 형식이** 드롭 다운 목록 및 다음 ENTER 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-121">Type `Turns` into the **Name** box that is below the newly added `MaxNumber` argument, select **Out** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER.</span></span>  
  
7.  <span data-ttu-id="485cf-122">클릭 **인수** 를 닫으려면 활동 디자이너 왼쪽 아래에에서는 **인수** 창.</span><span class="sxs-lookup"><span data-stu-id="485cf-122">Click **Arguments** in the lower-left side of the activity designer to close the **Arguments** pane.</span></span>  
  
8.  <span data-ttu-id="485cf-123">클릭 **변수** 표시 하려면 워크플로 디자이너 왼쪽 아래에에서는 **변수** 창.</span><span class="sxs-lookup"><span data-stu-id="485cf-123">Click **Variables** in the lower-left side of the workflow designer to display the **Variables** pane.</span></span>  
  
9. <span data-ttu-id="485cf-124">클릭 **변수를 만들고**합니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-124">Click **Create Variable**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="485cf-125">되지 않은 경우 **변수 만들기** 상자가 표시 됩니다을 클릭는 <xref:System.Activities.Statements.StateMachine> 활동을 워크플로 디자이너 화면을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-125">If no **Create Variable** box is displayed, click the <xref:System.Activities.Statements.StateMachine> activity on the workflow designer surface to select it.</span></span>  
  
10. <span data-ttu-id="485cf-126">형식 `Guess` 에 **이름** 상자 **Int32** 에서 **변수 형식** 드롭 다운 목록 및 다음 변수를 저장 하는 ENTER 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-126">Type `Guess` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
11. <span data-ttu-id="485cf-127">클릭 **변수를 만들고**합니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-127">Click **Create Variable**.</span></span>  
  
12. <span data-ttu-id="485cf-128">형식 `Target` 에 **이름** 상자 **Int32** 에서 **변수 형식** 드롭 다운 목록 및 다음 변수를 저장 하는 ENTER 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-128">Type `Target` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
13. <span data-ttu-id="485cf-129">클릭 **변수** 를 닫으려면 활동 디자이너 왼쪽 아래에에서는 **변수** 창.</span><span class="sxs-lookup"><span data-stu-id="485cf-129">Click **Variables** in the lower-left side of the activity designer to close the **Variables** pane.</span></span>  
  
### <a name="to-add-the-workflow-activities"></a><span data-ttu-id="485cf-130">워크플로 활동을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="485cf-130">To add the workflow activities</span></span>  
  
1.  <span data-ttu-id="485cf-131">클릭 **State1** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-131">Click **State1** to select it.</span></span> <span data-ttu-id="485cf-132">에 **속성 창**, 변경 된 **DisplayName** 를 `Initialize Target`합니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-132">In the **Properties Window**, change the **DisplayName** to `Initialize Target`.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="485cf-133">경우는 **속성 창** 가 표시 되지 않는 select **속성 창** 에서 **보기** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="485cf-133">If the **Properties Window** is not displayed, select **Properties Window** from the **View** menu.</span></span>  
  
2.  <span data-ttu-id="485cf-134">이름을 새로 변경한를 두 번 클릭 **Initialize Target** 하 여 확장 워크플로 디자이너의 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-134">Double-click the newly renamed **Initialize Target** state in the workflow designer to expand it.</span></span>  
  
3.  <span data-ttu-id="485cf-135">끌어서는 **할당** 활동을는 **기본 형식** 섹션은 **도구 상자** 놓습니다는 **항목** 상태 섹션.</span><span class="sxs-lookup"><span data-stu-id="485cf-135">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and drop it onto the **Entry** section of the state.</span></span> <span data-ttu-id="485cf-136">형식 `Target` 에 **를** 상자와에 다음 식을 **C# 식 입력** 또는 **VB 식 입력** 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-136">Type `Target` into the **To** box and the following expression into the **Enter a C# expression** or **Enter a VB expression** box.</span></span>  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    >  <span data-ttu-id="485cf-137">경우는 **도구 상자** 창이 표시 되지 않으면, 선택 **도구 상자** 에서 **보기** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="485cf-137">If the **Toolbox** window is not displayed, select **Toolbox** from the **View** menu.</span></span>  
  
4.  <span data-ttu-id="485cf-138">전체 돌아갑니다 상태 워크플로 디자이너에서 컴퓨터 보기를 클릭 하 여 **StateMachine** 워크플로 디자이너의 맨 위에 표시 된 이동 경로에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-138">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
5.  <span data-ttu-id="485cf-139">끌어서는 **상태** 활동을는 **상태 시스템** 의 섹션은 **도구 상자** 워크플로 디자이너에 위로 가져갑니다는 **Initialize Target** 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-139">Drag a **State** activity from the **State Machine** section of the **Toolbox** onto the workflow designer and hover it over the **Initialize Target** state.</span></span> <span data-ttu-id="485cf-140">참고 주위에 삼각형 4 개가 표시 됩니다는 **Initialize Target** 상태 위에 새 상태가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-140">Note that four triangles will appear around the **Initialize Target** state when the new state is over it.</span></span> <span data-ttu-id="485cf-141">Drop 바로 아래에 있는 삼각형에 새 상태는 **Initialize Target** 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-141">Drop the new state on the triangle that is immediately below the **Initialize Target** state.</span></span> <span data-ttu-id="485cf-142">새 상태가 워크플로에 배치 하 고에서 전환을 만듭니다.이 **Initialize Target** 새 상태로 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-142">This places the new state onto the workflow and creates a transition from the **Initialize Target** state to the new state.</span></span>  
  
6.  <span data-ttu-id="485cf-143">클릭 **State1** 를 선택 하려면 변경는 **DisplayName** 를 `Enter Guess`, 다음을 확장 하려면 워크플로 디자이너의 상태를 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-143">Click **State1** to select it, change the **DisplayName** to `Enter Guess`, and then double-click the state in the workflow designer to expand it.</span></span>  
  
7.  <span data-ttu-id="485cf-144">끌어서는 **WriteLine** 활동을는 **기본 형식** 섹션은 **도구 상자** 놓습니다는 **항목** 상태 섹션.</span><span class="sxs-lookup"><span data-stu-id="485cf-144">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it onto the **Entry** section of the state.</span></span>  
  
8.  <span data-ttu-id="485cf-145">에 다음 식을 입력는 **텍스트** 의 속성 상자는 **WriteLine**합니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-145">Type the following expression into the **Text** property box of the **WriteLine**.</span></span>  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
9. <span data-ttu-id="485cf-146">끌어서는 **할당** 활동을는 **기본 형식** 섹션은 **도구 상자** 끌어다 놓으십시오는 **종료** 상태 섹션.</span><span class="sxs-lookup"><span data-stu-id="485cf-146">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and drop onto the **Exit** section of the state.</span></span>  
  
10. <span data-ttu-id="485cf-147">형식 `Turns` 에 **를** 상자 및 `Turns + 1` 에 **C# 식 입력** 또는 **VB 식 입력** 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-147">Type `Turns` into the **To** box and `Turns + 1` into the **Enter a C# expression** or **Enter a VB expression** box.</span></span>  
  
11. <span data-ttu-id="485cf-148">전체 돌아갑니다 상태 워크플로 디자이너에서 컴퓨터 보기를 클릭 하 여 **StateMachine** 워크플로 디자이너의 맨 위에 표시 된 이동 경로에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-148">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
12. <span data-ttu-id="485cf-149">끌어서는 **FinalState** 활동을는 **상태 시스템** 의 섹션은 **도구 상자**, 위로 마우스를 가져가고는 **Enter Guess** 상태로 끌어 놓은 오른쪽에 나타나는 삼각형에는 **Enter Guess** 상태 간의 전환을 만들어지도록 **Enter Guess** 및 **FinalState**합니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-149">Drag a **FinalState** activity from the **State Machine** section of the **Toolbox**, hover it over the **Enter Guess** state, and drop it onto the triangle that appears to the right of the **Enter Guess** state so that a transition is created between **Enter Guess** and **FinalState**.</span></span>  
  
13. <span data-ttu-id="485cf-150">전환의 기본 이름은 **T2**합니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-150">The default name of the transition is **T2**.</span></span> <span data-ttu-id="485cf-151">선택 하 고 설정 하려면 워크플로 디자이너에서 전환을 클릭 하 여 해당 **DisplayName** 를 **Guess Correct**합니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-151">Click the transition in the workflow designer to select it, and set its **DisplayName** to **Guess Correct**.</span></span> <span data-ttu-id="485cf-152">그런 다음를 클릭 하 고 선택 된 **FinalState**, 두 상태 중 어느 쪽도 겹치지 없이 표시 되도록 전체 전환 이름에 대 한 공간이 있도록 오른쪽으로 끕니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-152">Then click and select the **FinalState**, and drag it to the right so that there is room for the full transition name to be displayed without overlaying either of the two states.</span></span> <span data-ttu-id="485cf-153">이렇게 하면 자습서의 나머지 단계를 보다 쉽게 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-153">This will make it easier to complete the remaining steps in the tutorial.</span></span>  
  
14. <span data-ttu-id="485cf-154">이름을 새로 변경한를 두 번 클릭 **Guess Correct** 하 여 확장 워크플로 디자이너에서 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-154">Double-click the newly renamed **Guess Correct** transition in the workflow designer to expand it.</span></span>  
  
15. <span data-ttu-id="485cf-155">끌어서는 **ReadInt** 활동을는 **NumberGuessWorkflowActivities** 섹션은 **도구 상자** 놓습니다는 **트리거** 섹션 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-155">Drag a **ReadInt** activity from the **NumberGuessWorkflowActivities** section of the **Toolbox** and drop it in the **Trigger** section of the transition.</span></span>  
  
16. <span data-ttu-id="485cf-156">에 **속성 창** 에 대 한는 **ReadInt** 활동, 형식 `"EnterGuess"` 따옴표를 포함 하는 **BookmarkName** 속성 값 상자 및 형식 `Guess`에 **결과** 속성 값 상자</span><span class="sxs-lookup"><span data-stu-id="485cf-156">In the **Properties Window** for the **ReadInt** activity, type `"EnterGuess"` including the quotes into the **BookmarkName** property value box, and type `Guess` into the **Result** property value box</span></span>  
  
17. <span data-ttu-id="485cf-157">에 다음 식을 입력는 **Guess Correct** 전환의 **조건** 속성 값 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-157">Type the following expression into the **Guess Correct** transition’s **Condition** property value box.</span></span>  
  
    ```vb  
    Guess = Target  
    ```  
  
    ```csharp  
    Guess == Target  
    ```  
  
18. <span data-ttu-id="485cf-158">전체 돌아갑니다 상태 워크플로 디자이너에서 컴퓨터 보기를 클릭 하 여 **StateMachine** 워크플로 디자이너의 맨 위에 표시 된 이동 경로에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-158">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="485cf-159">트리거 이벤트를 받고 <xref:System.Activities.Statements.Transition.Condition%2A>이 `True`인 경우 전환이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-159">A transition occurs when the trigger event is received and the <xref:System.Activities.Statements.Transition.Condition%2A>, if present, evaluates to `True`.</span></span> <span data-ttu-id="485cf-160">이 변환에 대 한 경우 사용자의 `Guess` 임의로 생성 된 일치 `Target`, 만든 다음 컨트롤에 전달 된 **FinalState** 워크플로가 완료 되 고 합니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-160">For this transition, if the user’s `Guess` matches the randomly generated `Target`, then control passes to the **FinalState** and the workflow completes.</span></span>  
  
19. <span data-ttu-id="485cf-161">추측이 올바른지 여부를 따라 워크플로의 전환 되어야 하는 **FinalState** 또는 돌아가기는 **Enter Guess** 시도할 합니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-161">Depending on whether the guess is correct, the workflow should transition either to the **FinalState** or back to the **Enter Guess** state for another try.</span></span> <span data-ttu-id="485cf-162">두 전환 모두 사용자의 추측을 통해 받을 때까지 기다리는 동일한 트리거를 공유는 **ReadInt** 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-162">Both transitions share the same trigger of waiting for the user’s guess to be received via the **ReadInt** activity.</span></span> <span data-ttu-id="485cf-163">이를 공유 전환이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-163">This is called a shared transition.</span></span> <span data-ttu-id="485cf-164">공유 전환을 만들려면의 시작을 나타내는 원을 클릭 하 여 **Guess Correct** 전환 하 고 원하는 상태로 끕니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-164">To create a shared transition, click the circle that indicates the start of the **Guess Correct** transition and drag it to the desired state.</span></span> <span data-ttu-id="485cf-165">시작점을 끌어 하므로,이 경우 전환은 자체 전환을가 **Guess Correct** 전환 다시 놓습니다 맨 아래에 **Enter Guess** 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-165">In this case the transition is a self-transition, so drag the start point of the **Guess Correct** transition and drop it back onto the bottom of the **Enter Guess** state.</span></span> <span data-ttu-id="485cf-166">전환을 만든 후 워크플로 디자이너에서 선택 하 고 설정의 **DisplayName** 속성을 **Guess Incorrect**합니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-166">After creating the transition, select it in the workflow designer and set its **DisplayName** property to **Guess Incorrect**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="485cf-167">공유 전환을 만들 수도 있습니다에서 전환 디자이너 내에서 클릭 하 여 **공유 트리거 전환 추가** 전환 디자이너 한 다음 원하는 대상 상태를 선택 하 고 맨 아래에  **연결에 사용할 상태** 드롭 다운 합니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-167">Shared transitions can also be created from within the transition designer by clicking **Add shared trigger transition** at the bottom of the transition designer, and then selecting the desired target state from the **Available states to connect** drop-down.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="485cf-168">전환의 <xref:System.Activities.Statements.Transition.Condition%2A>이 `false`가 되거나 모든 공유 트리거 전환 조건이 `false`가 되는 경우에는 전환이 일어나지 않으며 해당 상태로부터의 모든 전환에 대한 모든 트리거가 다시 예약됩니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-168">Note that if the <xref:System.Activities.Statements.Transition.Condition%2A> of a transition evaluates to `false` (or all of the conditions of a shared trigger transition evaluate to `false`), the transition will not occur and all triggers for all the transitions from the state will be rescheduled.</span></span> <span data-ttu-id="485cf-169">이 자습서에서는 조건이 구성된 방식(추측이 올바른지 또는 잘못되었는지에 따라 특정 동작이 지정됨) 때문에 이러한 상황이 발생할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-169">In this tutorial, this situation cannot happen because of the way the conditions are configured (we have specific actions for whether the guess is correct or incorrect).</span></span>  
  
20. <span data-ttu-id="485cf-170">두 번 클릭 하 고 **Guess Incorrect** 전환 하 여 확장 워크플로 디자이너에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-170">Double-click the **Guess Incorrect** transition in the workflow designer to expand it.</span></span> <span data-ttu-id="485cf-171">**트리거** 동일 하 게 이미 설정 되어 **ReadInt** 활동에서 사용 하는 **Guess Correct** 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-171">Note that the **Trigger** is already set to the same **ReadInt** activity that was used by the **Guess Correct** transition.</span></span>  
  
21. <span data-ttu-id="485cf-172">에 다음 식을 입력는 **조건** 속성 값 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-172">Type the following expression into the **Condition** property value box.</span></span>  
  
    ```vb  
    Guess <> Target  
    ```  
  
    ```csharp  
    Guess != Target  
    ```  
  
22. <span data-ttu-id="485cf-173">끌어서는 **경우** 활동을는 **제어 흐름** 섹션은 **도구 상자** 에 놓습니다는 **동작** 전환의 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-173">Drag an **If** activity from the **Control Flow** section of the **Toolbox** and drop it in the **Action** section of the transition.</span></span>  
  
23. <span data-ttu-id="485cf-174">에 다음 식을 입력는 **경우** 활동의 **조건** 속성 값 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-174">Type the following expression into the **If** activity’s **Condition** property value box.</span></span>  
  
    ```
    Guess < Target  
    ```  
  
24. <span data-ttu-id="485cf-175">두 개 **WriteLine** 활동을는 **기본 형식** 의 섹션은 **도구 상자** 하나에 삭제할는 **다음** 의 섹션 **경우** 활동, 또 하나는 **Else** 섹션.</span><span class="sxs-lookup"><span data-stu-id="485cf-175">Drag two **WriteLine** activities from the **Primitives** section of the **Toolbox** and drop them so that one is in the **Then** section of the **If** activity, and one is in the **Else** section.</span></span>  
  
25. <span data-ttu-id="485cf-176">클릭는 **WriteLine** 활동에는 **다음** 섹션을 선택 하 고에 다음 식을 입력는 **텍스트** 속성 값 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-176">Click the **WriteLine** activity in the **Then** section to select it, and type the following expression into the **Text** property value box.</span></span>  
  
    ```
    "Your guess is too low."  
    ```  
  
26. <span data-ttu-id="485cf-177">클릭는 **WriteLine** 활동에는 **Else** 섹션을 선택 하 고에 다음 식을 입력는 **텍스트** 속성 값 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-177">Click the **WriteLine** activity in the **Else** section to select it, and type the following expression into the **Text** property value box.</span></span>  
  
    ```
    "Your guess is too high."  
    ```  
  
27. <span data-ttu-id="485cf-178">전체 돌아갑니다 상태 워크플로 디자이너에서 컴퓨터 보기를 클릭 하 여 **StateMachine** 워크플로 디자이너의 맨 위에 표시 된 이동 경로에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-178">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
     <span data-ttu-id="485cf-179">다음 예제에서는 완료된 워크플로를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-179">The following example illustrates the completed workflow.</span></span>  
  
     <span data-ttu-id="485cf-180">![완료 된 상태 시스템 워크플로](../../../docs/framework/windows-workflow-foundation/media/wfstatemachinegettingstartedtutorialcomplete.JPG "WFStateMachineGettingStartedTutorialComplete")</span><span class="sxs-lookup"><span data-stu-id="485cf-180">![Completed State Machine Workflow](../../../docs/framework/windows-workflow-foundation/media/wfstatemachinegettingstartedtutorialcomplete.JPG "WFStateMachineGettingStartedTutorialComplete")</span></span>  
  
### <a name="to-build-the-workflow"></a><span data-ttu-id="485cf-181">워크플로를 빌드하려면</span><span class="sxs-lookup"><span data-stu-id="485cf-181">To build the workflow</span></span>  
  
1.  <span data-ttu-id="485cf-182">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-182">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
     <span data-ttu-id="485cf-183">워크플로 실행 하는 방법에 대 한 지침은 다음 항목을 참조 하십시오 [하는 방법: 워크플로 실행](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-183">For instructions on how to run the workflow, please see the next topic, [How to: Run a Workflow](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md).</span></span> <span data-ttu-id="485cf-184">이미 완료 된 경우는 [하는 방법: 워크플로 실행](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md) 워크플로의 다른 스타일이 적용 된 단계와이 단계에서 상태 시스템 워크플로 사용 하 여 실행 하려면,으로 바로 이동 하는 [빌드하고응용프로그램을실행하려면](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md#BKMK_ToRunTheApplication) 섹션 [하는 방법: 워크플로 실행](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="485cf-184">If you have already completed the [How to: Run a Workflow](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md) step with a different style of workflow and wish to run it using the state machine workflow from this step, skip ahead to the [To build and run the application](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md#BKMK_ToRunTheApplication) section of [How to: Run a Workflow](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="485cf-185">참고 항목</span><span class="sxs-lookup"><span data-stu-id="485cf-185">See Also</span></span>  
 <xref:System.Activities.Statements.Flowchart>  
 <xref:System.Activities.Statements.FlowDecision>  
 [<span data-ttu-id="485cf-186">Windows Workflow Foundation 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="485cf-186">Windows Workflow Foundation Programming</span></span>](../../../docs/framework/windows-workflow-foundation/programming.md)  
 [<span data-ttu-id="485cf-187">워크플로 디자인</span><span class="sxs-lookup"><span data-stu-id="485cf-187">Designing Workflows</span></span>](../../../docs/framework/windows-workflow-foundation/designing-workflows.md)  
 [<span data-ttu-id="485cf-188">초보자를 위한 자습서</span><span class="sxs-lookup"><span data-stu-id="485cf-188">Getting Started Tutorial</span></span>](../../../docs/framework/windows-workflow-foundation/getting-started-tutorial.md)  
 [<span data-ttu-id="485cf-189">방법: 활동 만들기</span><span class="sxs-lookup"><span data-stu-id="485cf-189">How to: Create an Activity</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md)  
 [<span data-ttu-id="485cf-190">방법: 워크플로 실행</span><span class="sxs-lookup"><span data-stu-id="485cf-190">How to: Run a Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md)
