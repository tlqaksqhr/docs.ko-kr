---
title: "방법: 순차 워크플로 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5280e816-ae17-48c4-8de0-a1e6895dd8f0
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# 방법: 순차 워크플로 만들기
기본 제공 활동뿐 아니라 사용자 지정 활동에서도 워크플로를 구성할 수 있습니다.이 항목에서는 <xref:System.Activities.Statements.Sequence> 활동과 같은 기본 제공 활동 및 이전 [방법: 활동 만들기](../../../docs/framework/windows-workflow-foundation//how-to-create-an-activity.md) 항목의 사용자 지정 활동을 모두 사용하는 워크플로를 만드는 방법을 단계별로 설명합니다.이 워크플로는 숫자 추측 게임을 모델링합니다.  
  
> [!NOTE]
>  초보자를 위한 자습서의 각 항목은 이전 항목을 바탕으로 합니다.이 항목을 완료하려면 먼저 [방법: 활동 만들기](../../../docs/framework/windows-workflow-foundation//how-to-create-an-activity.md)를 완료해야 합니다.  
  
> [!NOTE]
>  자습서의 전체 버전을 다운로드하려면 [Windows Workflow Foundation\(WF45\) \- 초보자를 위한 자습서](http://go.microsoft.com/fwlink/?LinkID=248976)를 참조하십시오.  
  
### 워크플로를 만들려면  
  
1.  **솔루션 탐색기**에서 **NumberGuessWorkflowActivities**를 마우스 오른쪽 단추로 클릭하고 **추가**, **새 항목**을 차례로 선택합니다.  
  
2.  **설치됨**, **공통 항목** 노드에서 **워크플로**를 선택합니다.**워크플로** 목록에서 **활동**을 선택합니다.  
  
3.  **이름** 상자에 `SequentialNumberGuessWorkflow`를 입력하고 **추가**를 클릭합니다.  
  
4.  **도구 상자**의 **제어 흐름** 섹션에서 **Sequence** 활동을 끌어 워크플로 디자인 화면의 **여기에 작업 놓기** 레이블에 놓습니다.  
  
### 워크플로 변수와 인수를 만들려면  
  
1.  워크플로가 아직 표시되어 있지 않은 경우 **솔루션 탐색기**에서 **SequentialNumberGuessWorkflow.xaml**을 두 번 클릭하여 디자이너에 워크플로를 표시합니다.  
  
2.  Workflow Designer 왼쪽 아래에 있는 **인수**를 클릭하여 **인수** 창을 표시합니다.  
  
3.  **인수 만들기**를 클릭합니다.  
  
4.  **이름** 상자에 `MaxNumber`를 입력하고 **방향** 드롭다운 목록에서 **입력**을 선택한 다음 **인수 형식** 드롭다운 목록에서 **Int32**를 선택하고 Enter 키를 눌러 인수를 저장합니다.  
  
5.  **인수 만들기**를 클릭합니다.  
  
6.  새로 추가된 `MaxNumber` 인수 아래에 있는 **이름** 상자에 `Turns`를 입력하고 **방향** 드롭다운 목록에서 **출력**을 선택한 다음 **인수 형식** 드롭다운 목록에서 **Int32**를 선택하고 Enter 키를 누릅니다.  
  
7.  활동 디자이너 왼쪽 아래에 있는 **인수**를 클릭하여 **인수** 창을 닫습니다.  
  
8.  Workflow Designer 왼쪽 아래에 있는 **변수**를 클릭하여 **변수** 창을 표시합니다.  
  
9. **변수 만들기**를 클릭합니다.  
  
    > [!TIP]
    >  **변수 만들기** 상자가 표시되어 있지 않으면 Workflow Designer 화면에서 **Sequence** 활동을 클릭하여 선택합니다.  
  
10. **이름** 상자에 `Guess`를 입력하고 **변수 형식** 드롭다운 목록에서 **Int32**를 선택한 다음 Enter 키를 눌러 변수를 저장합니다.  
  
11. **변수 만들기**를 클릭합니다.  
  
12. **이름** 상자에 `Target`을 입력하고 **변수 형식** 드롭다운 목록에서 **Int32**를 선택한 다음 Enter 키를 눌러 변수를 저장합니다.  
  
13. 활동 디자이너 왼쪽 아래에 있는 **변수**를 클릭하여 **변수** 창을 닫습니다.  
  
### 워크플로 활동을 추가하려면  
  
1.  **도구 상자**의 **기본 형식** 섹션에서 **Assign** 활동을 끌어 **Sequence** 활동에 놓습니다.**대상** 상자에 `Target`을 입력하고 **C\# 식 입력** 또는 **VB 식 입력** 상자에 다음 식을 입력합니다.  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    >  **도구 상자** 창이 표시되어 있지 않으면 **보기** 메뉴에서 **도구 상자**를 선택합니다.  
  
2.  **도구 상자**의 **제어 흐름** 섹션에서 **DoWhile** 활동을 끌어 워크플로의 **Assign** 활동 아래에 놓습니다.  
  
3.  **DoWhile** 활동의 **Condition** 속성 값 상자에 다음 식을 입력합니다.  
  
    ```vb  
    Guess <> Target  
    ```  
  
    ```csharp  
    Guess != Target  
    ```  
  
     <xref:System.Activities.Statements.DoWhile> 활동은 자식 활동을 실행한 다음 해당 <xref:System.Activities.Statements.DoWhile.Condition%2A>을 확인합니다.<xref:System.Activities.Statements.DoWhile.Condition%2A>이 `True`로 확인되면 <xref:System.Activities.Statements.DoWhile>의 활동이 다시 실행됩니다.이 예제에서는 사용자의 추측 값을 확인하여 추측이 올바를 때까지 <xref:System.Activities.Statements.DoWhile>이 계속됩니다.  
  
4.  **도구 상자**의 **NumberGuessWorkflowActivities** 섹션에서 **Prompt** 활동을 끌어 이전 단계의 **DoWhile** 활동에 놓습니다.  
  
5.  **속성 창**에서 **Prompt** 활동의 **BookmarkName** 속성 값 상자에 `"EnterGuess"`를 따옴표를 포함하여 입력합니다.**결과** 속성 값 상자에 `Guess`를 입력하고 **텍스트** 속성 상자에 다음 식을 입력합니다.  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
    > [!TIP]
    >  **속성 창**이 표시되지 않은 경우 **보기** 메뉴에서 **속성 창**을 선택합니다.  
  
6.  **도구 상자**의 **기본 형식** 섹션에서 **Assign** 활동을 **DoWhile** 활동으로 끌어 와 **Prompt** 활동 다음에 놓이도록 합니다.  
  
    > [!NOTE]
    >  **Assign** 활동을 놓으면 Workflow Designer는 **Prompt** 활동과 새로 추가된 **Assign** 활동을 모두 포함하도록 **Sequence** 활동을 자동으로 추가합니다.  
  
7.  **대상** 상자에 `Turns`를 입력하고 **C\# 식 입력** 또는 **VB 식 입력** 상자에 `Turns + 1`을 입력합니다.  
  
8.  **도구 상자**의 **제어 흐름** 섹션에서 **If** 활동을 **Sequence** 활동으로 끌어 와 새로 추가된 **Assign** 활동 다음에 놓이도록 합니다.  
  
9. **If** 활동의 **Condition** 속성 값 상자에 다음 식을 입력합니다.  
  
    ```vb  
    Guess <> Target  
    ```  
  
    ```csharp  
    Guess != Target  
    ```  
  
10. **도구 상자**의 **제어 흐름** 섹션에서 다른 **If** 활동을 끌어 와 첫 번째 **If** 활동의 **Then** 섹션에 놓습니다.  
  
11. 새로 추가된 **If** 활동의 **Condition** 속성 값 상자에 다음 식을 입력합니다.  
  
    ```vb-c#  
    Guess < Target  
    ```  
  
12. **도구 상자**의 **기본 형식** 섹션에서 두 **WriteLine** 활동을 끌어 하나는 새로 추가된 **If** 활동의 **Then** 섹션에, 또 하나는 **Else** 섹션에 놓습니다.  
  
13. **Then** 섹션에서 **WriteLine** 활동을 클릭하여 선택하고 **Text** 속성 값 상자에 다음 식을 입력합니다.  
  
    ```vb  
    "Your guess is too low."  
    ```  
  
14. **Else** 섹션에서 **WriteLine** 활동을 클릭하여 선택하고 **Text** 속성 값 상자에 다음 식을 입력합니다.  
  
    ```vb  
    "Your guess is too high."  
    ```  
  
     다음 예제에서는 완료된 워크플로를 보여 줍니다.  
  
     ![완료된 순차 워크플로](../../../docs/framework/windows-workflow-foundation//media/wfsequentialgettingstartedtutorialcomplete.JPG "WFSequentialGettingStartedTutorialComplete")  
  
### 워크플로를 빌드하려면  
  
1.  Ctrl\+Shift\+B를 눌러 솔루션을 빌드합니다.  
  
     워크플로를 실행하는 방법에 대한 지침은 다음 항목 [방법: 워크플로 실행](../../../docs/framework/windows-workflow-foundation//how-to-run-a-workflow.md)을 참조하십시오.워크플로의 다른 스타일로 [방법: 워크플로 실행](../../../docs/framework/windows-workflow-foundation//how-to-run-a-workflow.md) 단계를 이미 수행했고 이 단계에서 순차 워크플로를 사용하여 이 워크플로를 실행하려고 할 경우 [방법: 워크플로 실행](../../../docs/framework/windows-workflow-foundation//how-to-run-a-workflow.md)의 [응용 프로그램을 빌드하고 실행하려면](../../../docs/framework/windows-workflow-foundation//how-to-run-a-workflow.md#BKMK_ToRunTheApplication) 단원으로 건너뛰십시오.  
  
## 참고 항목  
 <xref:System.Activities.Statements.Flowchart>   
 <xref:System.Activities.Statements.FlowDecision>   
 [Windows Workflow Foundation 프로그래밍](../../../docs/framework/windows-workflow-foundation//programming.md)   
 [워크플로 디자인](../../../docs/framework/windows-workflow-foundation//designing-workflows.md)   
 [초보자를 위한 자습서](../../../docs/framework/windows-workflow-foundation//getting-started-tutorial.md)   
 [방법: 활동 만들기](../../../docs/framework/windows-workflow-foundation//how-to-create-an-activity.md)   
 [방법: 워크플로 실행](../../../docs/framework/windows-workflow-foundation//how-to-run-a-workflow.md)