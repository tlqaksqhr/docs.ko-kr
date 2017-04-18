---
title: "방법: 순서도 워크플로 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 185d7aea-68a6-4bd8-adde-45050f33170a
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# 방법: 순서도 워크플로 만들기
기본 제공 활동뿐 아니라 사용자 지정 활동에서도 워크플로를 구성할 수 있습니다.이 항목에서는 <xref:System.Activities.Statements.Flowchart> 활동과 같은 기본 제공 활동 및 이전 [방법: 활동 만들기](../../../docs/framework/windows-workflow-foundation//how-to-create-an-activity.md) 항목의 사용자 지정 활동을 모두 사용하는 워크플로를 만드는 방법을 단계별로 설명합니다.이 워크플로는 숫자 추측 게임을 모델링합니다.  
  
> [!NOTE]
>  초보자를 위한 자습서의 각 항목은 이전 항목을 바탕으로 합니다.이 항목을 완료하려면 먼저 [방법: 활동 만들기](../../../docs/framework/windows-workflow-foundation//how-to-create-an-activity.md)를 완료해야 합니다.  
  
> [!NOTE]
>  자습서의 전체 버전을 다운로드하려면 [Windows Workflow Foundation\(WF45\) \- 초보자를 위한 자습서](http://go.microsoft.com/fwlink/?LinkID=248976)를 참조하십시오.  
  
### 워크플로를 만들려면  
  
1.  **솔루션 탐색기**에서 **NumberGuessWorkflowActivities**를 마우스 오른쪽 단추로 클릭하고 **추가**, **새 항목**을 차례로 선택합니다.  
  
2.  **설치됨**, **공통 항목** 노드에서 **워크플로**를 선택합니다.**워크플로** 목록에서 **활동**을 선택합니다.  
  
3.  **이름** 상자에 `FlowchartNumberGuessWorkflow`를 입력하고 **추가**를 클릭합니다.  
  
4.  **도구 상자**의 **순서도** 섹션에서 **Flowchart** 활동을 끌어 워크플로 디자인 화면의 **여기에 작업 놓기** 레이블에 놓습니다.  
  
### 워크플로 변수와 인수를 만들려면  
  
1.  워크플로가 아직 표시되어 있지 않은 경우 **솔루션 탐색기**에서 **FlowchartNumberGuessWorkflow.xaml**을 두 번 클릭하여 디자이너에 워크플로를 표시합니다.  
  
2.  Workflow Designer 왼쪽 아래에 있는 **인수**를 클릭하여 **인수** 창을 표시합니다.  
  
3.  **인수 만들기**를 클릭합니다.  
  
4.  **이름** 상자에 `MaxNumber`를 입력하고 **방향** 드롭다운 목록에서 **입력**을 선택한 다음 **인수 형식** 드롭다운 목록에서 **Int32**를 선택하고 Enter 키를 눌러 인수를 저장합니다.  
  
5.  **인수 만들기**를 클릭합니다.  
  
6.  새로 추가된 `MaxNumber` 인수 아래에 있는 **이름** 상자에 `Turns`를 입력하고 **방향** 드롭다운 목록에서 **출력**을 선택한 다음 **인수 형식** 드롭다운 목록에서 **Int32**를 선택하고 Enter 키를 누릅니다.  
  
7.  활동 디자이너 왼쪽 아래에 있는 **인수**를 클릭하여 **인수** 창을 닫습니다.  
  
8.  Workflow Designer 왼쪽 아래에 있는 **변수**를 클릭하여 **변수** 창을 표시합니다.  
  
9. **변수 만들기**를 클릭합니다.  
  
    > [!TIP]
    >  **변수 만들기** 상자가 표시되어 있지 않으면 Workflow Designer 화면에서 <xref:System.Activities.Statements.Flowchart> 활동을 클릭하여 선택합니다.  
  
10. **이름** 상자에 `Guess`를 입력하고 **변수 형식** 드롭다운 목록에서 **Int32**를 선택한 다음 Enter 키를 눌러 변수를 저장합니다.  
  
11. **변수 만들기**를 클릭합니다.  
  
12. **이름** 상자에 `Target`을 입력하고 **변수 형식** 드롭다운 목록에서 **Int32**를 선택한 다음 Enter 키를 눌러 변수를 저장합니다.  
  
13. 활동 디자이너 왼쪽 아래에 있는 **변수**를 클릭하여 **변수** 창을 닫습니다.  
  
### 워크플로 활동을 추가하려면  
  
1.  **도구 상자**의 **기본 형식** 섹션에서 **Assign** 활동을 끌어 순서도의 맨 위에 있는 **시작** 노드 위에 놓습니다.**Assign** 활동이 **시작** 노드 위에 있으면 **시작** 노드 주위에 삼각형 세 개가 표시됩니다.**시작** 노드 바로 아래에 있는 삼각형에 **Assign** 활동을 놓습니다.그러면 두 항목이 서로 연결되고 **Assign** 활동이 순서도의 첫 번째 활동으로 지정됩니다.  
  
    > [!NOTE]
    >  시작 노드에 활동을 직접 연결하여 워크플로에서 해당 활동을 시작 활동으로 나타낼 수도 있습니다.이렇게 하려면 마우스를 **시작** 노드 위로 가져가서 마우스가 **시작** 노드 위에 있을 때 나타나는 사각형 중 하나를 클릭하고 연결선을 원하는 활동 아래로 끌어 나타나는 사각형 중 하나 위에 놓습니다.활동을 마우스 오른쪽 단추로 클릭하고 **시작 노드로 설정**을 선택하여 해당 활동을 시작 활동으로 지정할 수도 있습니다.  
  
2.  **대상** 상자에 `Target`을 입력하고 **C\# 식 입력** 또는 **VB 식 입력** 상자에 다음 식을 입력합니다.  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    >  **도구 상자** 창이 표시되어 있지 않으면 **보기** 메뉴에서 **도구 상자**를 선택합니다.  
  
3.  **도구 상자**의 **NumberGuessWorkflowActivities** 섹션에서 **Prompt** 활동을 끌어 이전 단계의 **Assign** 활동 아래에 놓고 **Prompt** 활동을 **Assign** 활동에 연결합니다.두 활동을 연결하는 방법에는 세 가지가 있습니다.첫 번째 방법은 워크플로에 **Prompt** 활동을 놓을 때 두 활동을 연결하는 것입니다.**Prompt** 활동을 워크플로로 끌 때 **Assign** 활동 위에 마우스를 놓고 **Prompt** 활동이 **Assign** 활동 위에 있을 때 나타나는 삼각형 네 개 중 하나에 놓습니다.두 번째 방법은 **Prompt** 활동을 워크플로의 원하는 위치에 놓는 것입니다.그런 다음 마우스를 **Assign** 활동 위에 놓고 **Prompt** 활동 아래에 나타나는 사각형 중 하나를 끕니다.**Assign** 활동의 연결선이 **Prompt** 활동의 사각형 중 하나에 연결되도록 마우스를 끌고 마우스 단추를 놓습니다.세 번째 방법은 첫 번째와 매우 유사합니다. **도구 상자**에서 **Prompt** 활동을 끄는 대신 워크플로 디자인 화면의 해당 위치에서 활동을 끌어 **Assign** 활동 위로 가져간 다음 나타나는 삼각형 중 하나에 놓습니다.  
  
4.  **Prompt** 활동의 **속성 창**에서 **BookmarkName** 속성 값 상자에 `"EnterGuess"`를 따옴표를 포함하여 입력합니다.**결과** 속성 값 상자에 `Guess`를 입력하고 **텍스트** 속성 상자에 다음 식을 입력합니다.  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
    > [!TIP]
    >  **속성 창**이 표시되지 않은 경우 **보기** 메뉴에서 **속성 창**을 선택합니다.  
  
5.  **도구 상자**의 **기본 형식** 섹션에서 **Assign** 활동을 끌어 온 다음 이전 단계에서 설명한 방법 중 하나를 사용하여 이 활동이 **Prompt** 활동 아래에 오도록 연결합니다.  
  
6.  **대상** 상자에 `Turns`를 입력하고 **C\# 식 입력** 또는 **VB 식 입력** 상자에 `Turns + 1`을 입력합니다.  
  
7.  **도구 상자**의 **순서도** 섹션에서 **FlowDecision**을 끌어 **Assign** 활동 아래에 연결합니다.**속성 창**의 **조건** 속성 값 상자에 다음 식을 입력합니다.  
  
    ```vb  
    Guess = Target  
    ```  
  
    ```csharp  
    Guess == Target  
    ```  
  
8.  **도구 상자**에서 다른 **FlowDecision** 활동을 끌어 첫 번째 활동 아래에 놓습니다.**FlowDecision** 활동 맨 위의 **False** 레이블이 있는 사각형에서 두 번째 **FlowDecision** 활동 맨 위의 사각형으로 끌어 두 활동을 연결합니다.  
  
    > [!TIP]
    >  **FlowDecision**에 **True** 및 **False** 레이블이 표시되어 있지 않으면 마우스로 **FlowDecision**을 가리킵니다.  
  
9. 두 번째 **FlowDecision** 활동을 클릭하여 선택합니다.**속성 창**의 **조건** 속성 값 상자에 다음 식을 입력합니다.  
  
    ```vb-c#  
    Guess < Target  
    ```  
  
10. **도구 상자**의 **기본 형식** 섹션에서 두 **WriteLine** 활동을 끌어 두 **FlowDecision** 활동 아래에 나란히 놓습니다.**FlowDecision** 활동의 **True** 동작을 맨 왼쪽 **WriteLine** 활동에 연결하고 **False** 동작을 맨 오른쪽 **WriteLine** 활동에 연결합니다.  
  
11. 맨 왼쪽 **WriteLine** 활동을 클릭하여 선택하고 **속성 창**의 **텍스트** 속성 값 상자에 다음 식을 입력합니다.  
  
    ```vb-c#  
    "Your guess is too low."  
    ```  
  
12. **WriteLine**을 위에 있는 **프롬프트** 활동 왼쪽에 연결합니다.  
  
13. 맨 오른쪽 **WriteLine** 활동을 클릭하여 선택하고 **속성 창**의 **텍스트** 속성 값 상자에 다음 식을 입력합니다.  
  
    ```vb-c#  
    "Your guess is too high."  
    ```  
  
14. **WriteLine** 활동을 위에 있는 **프롬프트** 활동 오른쪽에 연결합니다.  
  
     다음 예제에서는 완료된 워크플로를 보여 줍니다.  
  
     ![완료된 Windows Workflow Foundation](../../../docs/framework/windows-workflow-foundation//media/gettingstartedtutorialcompletedflowchart.PNG "GettingStartedTutorialCompletedFlowchart")  
  
### 워크플로를 빌드하려면  
  
1.  Ctrl\+Shift\+B를 눌러 솔루션을 빌드합니다.  
  
     워크플로를 실행하는 방법에 대한 지침은 다음 항목 [방법: 워크플로 실행](../../../docs/framework/windows-workflow-foundation//how-to-run-a-workflow.md)을 참조하십시오.워크플로의 다른 스타일로 [방법: 워크플로 실행](../../../docs/framework/windows-workflow-foundation//how-to-run-a-workflow.md) 단계를 이미 수행했고 이 단계에서 순서도 워크플로를 사용하여 이 워크플로를 실행하려고 할 경우 [방법: 워크플로 실행](../../../docs/framework/windows-workflow-foundation//how-to-run-a-workflow.md)의 [응용 프로그램을 빌드하고 실행하려면](../../../docs/framework/windows-workflow-foundation//how-to-run-a-workflow.md#BKMK_ToRunTheApplication) 단원으로 건너뛰십시오.  
  
## 참고 항목  
 <xref:System.Activities.Statements.Flowchart>   
 <xref:System.Activities.Statements.FlowDecision>   
 [Windows Workflow Foundation 프로그래밍](../../../docs/framework/windows-workflow-foundation//programming.md)   
 [워크플로 디자인](../../../docs/framework/windows-workflow-foundation//designing-workflows.md)   
 [초보자를 위한 자습서](../../../docs/framework/windows-workflow-foundation//getting-started-tutorial.md)   
 [방법: 활동 만들기](../../../docs/framework/windows-workflow-foundation//how-to-create-an-activity.md)   
 [방법: 워크플로 실행](../../../docs/framework/windows-workflow-foundation//how-to-run-a-workflow.md)