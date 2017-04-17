---
title: "방법: 상태 시스템 워크플로 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3ec60e8f-fad4-493e-a426-e7962d7aee8c
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# 방법: 상태 시스템 워크플로 만들기
기본 제공 활동뿐 아니라 사용자 지정 활동에서도 워크플로를 구성할 수 있습니다.이 항목에서는 <xref:System.Activities.Statements.StateMachine> 활동과 같은 기본 제공 활동 및 이전 [방법: 활동 만들기](../../../docs/framework/windows-workflow-foundation//how-to-create-an-activity.md) 항목의 사용자 지정 활동을 모두 사용하는 워크플로를 만드는 방법을 단계별로 설명합니다.이 워크플로는 숫자 추측 게임을 모델링합니다.  
  
> [!NOTE]
>  초보자를 위한 자습서의 각 항목은 이전 항목을 바탕으로 합니다.이 항목을 완료하려면 먼저 [방법: 활동 만들기](../../../docs/framework/windows-workflow-foundation//how-to-create-an-activity.md)를 완료해야 합니다.  
  
> [!NOTE]
>  자습서의 전체 버전을 다운로드하려면 [Windows Workflow Foundation\(WF45\) \- 초보자를 위한 자습서](http://go.microsoft.com/fwlink/?LinkID=248976)를 참조하십시오.  
  
### 워크플로를 만들려면  
  
1.  **솔루션 탐색기**에서 **NumberGuessWorkflowActivities**를 마우스 오른쪽 단추로 클릭하고 **추가**, **새 항목**을 차례로 선택합니다.  
  
2.  **설치됨**, **공통 항목** 노드에서 **워크플로**를 선택합니다.**워크플로** 목록에서 **활동**을 선택합니다.  
  
3.  **이름** 상자에 `StateMachineNumberGuessWorkflow`를 입력하고 **추가**를 클릭합니다.  
  
4.  **도구 상자**의 **상태 시스템** 섹션에서 **StateMachine** 활동을 끌어 워크플로 디자인 화면의 **여기에 작업 놓기** 레이블에 놓습니다.  
  
### 워크플로 변수와 인수를 만들려면  
  
1.  워크플로가 아직 표시되어 있지 않은 경우 **솔루션 탐색기**에서 **StateMachineNumberGuessWorkflow.xaml**을 두 번 클릭하여 디자이너에 워크플로를 표시합니다.  
  
2.  Workflow Designer 왼쪽 아래에 있는 **인수**를 클릭하여 **인수** 창을 표시합니다.  
  
3.  **인수 만들기**를 클릭합니다.  
  
4.  **이름** 상자에 `MaxNumber`를 입력하고 **방향** 드롭다운 목록에서 **입력**을 선택한 다음 **인수 형식** 드롭다운 목록에서 **Int32**를 선택하고 Enter 키를 눌러 인수를 저장합니다.  
  
5.  **인수 만들기**를 클릭합니다.  
  
6.  새로 추가된 `MaxNumber` 인수 아래에 있는 **이름** 상자에 `Turns`를 입력하고 **방향** 드롭다운 목록에서 **출력**을 선택한 다음 **인수 형식** 드롭다운 목록에서 **Int32**를 선택하고 Enter 키를 누릅니다.  
  
7.  활동 디자이너 왼쪽 아래에 있는 **인수**를 클릭하여 **인수** 창을 닫습니다.  
  
8.  Workflow Designer 왼쪽 아래에 있는 **변수**를 클릭하여 **변수** 창을 표시합니다.  
  
9. **변수 만들기**를 클릭합니다.  
  
    > [!TIP]
    >  **변수 만들기** 상자가 표시되어 있지 않으면 Workflow Designer 화면에서 <xref:System.Activities.Statements.StateMachine> 활동을 클릭하여 선택합니다.  
  
10. **이름** 상자에 `Guess`를 입력하고 **변수 형식** 드롭다운 목록에서 **Int32**를 선택한 다음 Enter 키를 눌러 변수를 저장합니다.  
  
11. **변수 만들기**를 클릭합니다.  
  
12. **이름** 상자에 `Target`을 입력하고 **변수 형식** 드롭다운 목록에서 **Int32**를 선택한 다음 Enter 키를 눌러 변수를 저장합니다.  
  
13. 활동 디자이너 왼쪽 아래에 있는 **변수**를 클릭하여 **변수** 창을 닫습니다.  
  
### 워크플로 활동을 추가하려면  
  
1.  **State1**을 클릭하여 선택합니다.**속성 창**에서 **DisplayName**을 `Initialize Target`으로 변경합니다.  
  
    > [!TIP]
    >  **속성 창**이 표시되지 않은 경우 **보기** 메뉴에서 **속성 창**을 선택합니다.  
  
2.  Workflow Designer에서 이름을 새로 변경한 **Initialize Target** 상태를 두 번 클릭하여 확장합니다.  
  
3.  **도구 상자**의 **기본 형식** 섹션에서 **Assign** 활동을 끌어 상태의 **항목** 섹션에 놓습니다.**대상** 상자에 `Target`을 입력하고 **C\# 식 입력** 또는 **VB 식 입력** 상자에 다음 식을 입력합니다.  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    >  **도구 상자** 창이 표시되어 있지 않으면 **보기** 메뉴에서 **도구 상자**를 선택합니다.  
  
4.  Workflow Designer 맨 위에 표시된 이동 경로에서 **StateMachine**을 클릭하여 Workflow Designer의 전체 상태 시스템 뷰로 돌아갑니다.  
  
5.  **도구 상자**의 **상태 시스템** 섹션에서 **State** 활동을 Workflow Designer로 끌어 **Initialize Target** 상태 위에 놓습니다.**Initialize Target** 상태 위에 새 상태가 놓이면 주위에 삼각형 네 개가 표시됩니다.**Initialize Target** 상태 바로 아래의 삼각형에 새 상태를 놓습니다.그러면 새 상태가 워크플로에 배치되고 **Initialize Target** 상태에서 새 상태로의 전환이 만들어집니다.  
  
6.  **State1**을 클릭하여 선택하고 **DisplayName**을 `Enter Guess`로 변경한 후 Workflow Designer의 상태를 두 번 클릭하여 확장합니다.  
  
7.  **도구 상자**의 **기본 형식** 섹션에서 **WriteLine** 활동을 끌어 상태의 **항목** 섹션에 놓습니다.  
  
8.  **WriteLine**의 **Text** 속성 상자에 다음 식을 입력합니다.  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
9. **도구 상자**의 **기본 형식** 섹션에서 **Assign** 활동을 끌어 상태의 **종료** 섹션에 놓습니다.  
  
10. **대상** 상자에 `Turns`를 입력하고 **C\# 식 입력** 또는 **VB 식 입력** 상자에 `Turns + 1`을 입력합니다.  
  
11. Workflow Designer 맨 위에 표시된 이동 경로에서 **StateMachine**을 클릭하여 Workflow Designer의 전체 상태 시스템 뷰로 돌아갑니다.  
  
12. **도구 상자**의 **상태 시스템** 섹션에서 **FinalState** 활동을 끌어 **Enter Guess** 상태 위로 가져간 후 **Enter Guess** 상태 오른쪽에 나타나는 삼각형에 놓으면 **Enter Guess**와 **FinalState** 사이에 전환이 만들어집니다.  
  
13. 전환의 기본 이름은 **T2**입니다.Workflow Designer에서 전환을 클릭하여 선택하고 **DisplayName**을 **Guess Correct**로 설정합니다.그런 다음 **FinalState**를 클릭하여 선택하고 오른쪽으로 끌면 두 상태 중 어느 쪽도 겹치지 않고 전체 전환 이름을 표시할 공간이 생깁니다.이렇게 하면 자습서의 나머지 단계를 보다 쉽게 진행할 수 있습니다.  
  
14. Workflow Designer에서 이름을 새로 변경한 **Guess Correct** 전환을 두 번 클릭하여 확장합니다.  
  
15. **도구 상자**의 **NumberGuessWorkflowActivities** 섹션에서 **ReadInt** 활동을 끌어 전환의 **트리거** 섹션에 놓습니다.  
  
16. **ReadInt** 활동의 **속성 창**에서 **BookmarkName** 속성 값 상자에 `"EnterGuess"`를 따옴표를 포함하여 입력하고 **Result** 속성 값 상자에 `Guess`를 입력합니다.  
  
17. **Guess Correct** 전환의 **Condition** 속성 값 상자에 다음 식을 입력합니다.  
  
    ```vb  
    Guess = Target  
    ```  
  
    ```csharp  
    Guess == Target  
    ```  
  
18. Workflow Designer 맨 위에 표시된 이동 경로에서 **StateMachine**을 클릭하여 Workflow Designer의 전체 상태 시스템 뷰로 돌아갑니다.  
  
    > [!NOTE]
    >  트리거 이벤트를 받고 <xref:System.Activities.Statements.Transition.Condition%2A>이 `True`인 경우 전환이 발생합니다.이 전환의 경우 사용자의 `Guess`가 임의로 생성된 `Target`과 일치하면 제어가 **FinalState**로 전달되고 워크플로가 완료됩니다.  
  
19. 다시 시도할 경우 추측이 올바른지 여부에 따라 워크플로가 **FinalState**로 전환되거나 **Enter Guess**로 다시 전환되어야 합니다.두 전환 모두 **ReadInt** 활동을 통해 사용자의 추측을 받을 때까지 기다리는 동일한 트리거를 공유합니다.이를 공유 전환이라고 합니다.공유 전환을 만들려면 **Guess Correct** 전환의 시작을 나타내는 원을 클릭한 다음 원하는 상태로 끕니다.이 경우 전환은 자체 전환이므로 **Guess Correct** 전환의 시작점을 끌어 **Enter Guess** 상태의 맨 아래에 다시 놓습니다.전환을 만든 후에는 Workflow Designer에서 해당 전환을 선택하고 **DisplayName** 속성을 **Guess Incorrect**로 설정합니다.  
  
    > [!NOTE]
    >  전환 디자이너에서 아래쪽의 **공유 트리거 전환 추가**를 클릭한 다음 **연결에 사용할 상태** 드롭다운에서 원하는 대상 상태를 선택하여 공유 전환을 만들 수도 있습니다.  
  
    > [!NOTE]
    >  전환의 <xref:System.Activities.Statements.Transition.Condition%2A>이 `false`가 되거나 모든 공유 트리거 전환 조건이 `false`가 되는 경우에는 전환이 일어나지 않으며 해당 상태로부터의 모든 전환에 대한 모든 트리거가 다시 예약됩니다.이 자습서에서는 조건이 구성된 방식\(추측이 올바른지 또는 잘못되었는지에 따라 특정 동작이 지정됨\) 때문에 이러한 상황이 발생할 수 없습니다.  
  
20. Workflow Designer에서 **Guess Incorrect** 전환을 두 번 클릭하여 확장합니다.**트리거**는 **Guess Correct** 전환에서 사용된 것과 동일한 **ReadInt** 활동으로 이미 설정되어 있습니다.  
  
21. **Condition** 속성 값 상자에 다음 식을 입력합니다.  
  
    ```vb  
    Guess <> Target  
    ```  
  
    ```csharp  
    Guess != Target  
    ```  
  
22. **도구 상자**의 **제어 흐름** 섹션에서 **If** 활동을 끌어 전환의 **동작** 섹션에 놓습니다.  
  
23. **If** 활동의 **Condition** 속성 값 상자에 다음 식을 입력합니다.  
  
    ```vb-c#  
    Guess < Target  
    ```  
  
24. **도구 상자**의 **기본 형식** 섹션에서 두 **WriteLine** 활동을 끌어 하나는 **If** 활동의 **Then** 섹션에, 또 하나는 **Else** 섹션에 놓습니다.  
  
25. **Then** 섹션에서 **WriteLine** 활동을 클릭하여 선택하고 **Text** 속성 값 상자에 다음 식을 입력합니다.  
  
    ```vb-c#  
    "Your guess is too low."  
    ```  
  
26. **Else** 섹션에서 **WriteLine** 활동을 클릭하여 선택하고 **Text** 속성 값 상자에 다음 식을 입력합니다.  
  
    ```vb-c#  
    "Your guess is too high."  
    ```  
  
27. Workflow Designer 맨 위에 표시된 이동 경로에서 **StateMachine**을 클릭하여 Workflow Designer의 전체 상태 시스템 뷰로 돌아갑니다.  
  
     다음 예제에서는 완료된 워크플로를 보여 줍니다.  
  
     ![완료된 상태 시스템 워크플로](../../../docs/framework/windows-workflow-foundation//media/wfstatemachinegettingstartedtutorialcomplete.JPG "WFStateMachineGettingStartedTutorialComplete")  
  
### 워크플로를 빌드하려면  
  
1.  Ctrl\+Shift\+B를 눌러 솔루션을 빌드합니다.  
  
     워크플로를 실행하는 방법에 대한 지침은 다음 항목 [방법: 워크플로 실행](../../../docs/framework/windows-workflow-foundation//how-to-run-a-workflow.md)을 참조하십시오.워크플로의 다른 스타일로 [방법: 워크플로 실행](../../../docs/framework/windows-workflow-foundation//how-to-run-a-workflow.md) 단계를 이미 수행했고 이 단계에서 상태 시스템 워크플로를 사용하여 이 워크플로를 실행하려고 할 경우 [방법: 워크플로 실행](../../../docs/framework/windows-workflow-foundation//how-to-run-a-workflow.md)의 [응용 프로그램을 빌드하고 실행하려면](../../../docs/framework/windows-workflow-foundation//how-to-run-a-workflow.md#BKMK_ToRunTheApplication) 단원으로 건너뛰십시오.  
  
## 참고 항목  
 <xref:System.Activities.Statements.Flowchart>   
 <xref:System.Activities.Statements.FlowDecision>   
 [Windows Workflow Foundation 프로그래밍](../../../docs/framework/windows-workflow-foundation//programming.md)   
 [워크플로 디자인](../../../docs/framework/windows-workflow-foundation//designing-workflows.md)   
 [초보자를 위한 자습서](../../../docs/framework/windows-workflow-foundation//getting-started-tutorial.md)   
 [방법: 활동 만들기](../../../docs/framework/windows-workflow-foundation//how-to-create-an-activity.md)   
 [방법: 워크플로 실행](../../../docs/framework/windows-workflow-foundation//how-to-run-a-workflow.md)