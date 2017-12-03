---
title: "방법: 순서도 워크플로 만들기"
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
ms.assetid: 185d7aea-68a6-4bd8-adde-45050f33170a
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3df93a876522ccdc001bc3f6bc8c780bc80dc21b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-create-a-flowchart-workflow"></a>방법: 순서도 워크플로 만들기
기본 제공 활동뿐 아니라 사용자 지정 활동에서도 워크플로를 구성할 수 있습니다. 이 항목의 단계와 같은 기본 제공 활동을 모두 사용 하는 워크플로 만드는 따라는 <xref:System.Activities.Statements.Flowchart> 활동과 이전 사용자 지정 활동 [하는 방법: 활동 만들기](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md) 항목입니다. 이 워크플로는 숫자 추측 게임을 모델링합니다.  
  
> [!NOTE]
>  초보자를 위한 자습서의 각 항목은 이전 항목을 바탕으로 합니다. 이 항목을 완료 하려면 먼저 완료 해야 [하는 방법: 활동 만들기](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md)합니다.  
  
> [!NOTE]
>  자습서의 전체 버전을 다운로드하려면 [Windows Workflow Foundation(WF45) - 초보자를 위한 자습서](http://go.microsoft.com/fwlink/?LinkID=248976)를 참조하세요.  
  
### <a name="to-create-the-workflow"></a>워크플로를 만들려면  
  
1.  마우스 오른쪽 단추로 클릭 **NumberGuessWorkflowActivities** 에 **솔루션 탐색기** 선택 **추가**, **새 항목**합니다.  
  
2.  에 **설치 됨**, **공통 항목** 노드를 **워크플로**합니다. 선택 **활동** 에서 **워크플로** 목록입니다.  
  
3.  형식 `FlowchartNumberGuessWorkflow` 에 **이름** 상자 한 클릭 **추가**합니다.  
  
4.  끌어서는 **순서도** 활동을는 **순서도** 의 섹션은 **도구 상자** 놓습니다는 **여기에 작업 놓기** 에 레이블는 워크플로 디자인 화면입니다.  
  
### <a name="to-create-the-workflow-variables-and-arguments"></a>워크플로 변수와 인수를 만들려면  
  
1.  두 번 클릭 **FlowchartNumberGuessWorkflow.xaml** 에 **솔루션 탐색기** 에 표시 되지 않은 경우 워크플로 디자이너를 표시 합니다.  
  
2.  클릭 **인수** 표시 하려면 워크플로 디자이너 왼쪽 아래에에서는 **인수** 창.  
  
3.  클릭 **인수 만들기**합니다.  
  
4.  형식 `MaxNumber` 에 **이름** 상자 **에** 에서 **방향** 드롭 다운 목록 **Int32** 는 에서**인수 형식이** 드롭 다운 목록 및 다음 인수를 저장 하는 ENTER 누릅니다.  
  
5.  클릭 **인수 만들기**합니다.  
  
6.  형식 `Turns` 에 **이름** 새로 추가 된 아래에 있는 상자 `MaxNumber` 인수를 **아웃** 에서 **방향** 드롭 다운 목록에서  **Int32** 에서 **인수 형식이** 드롭 다운 목록 및 다음 ENTER 누릅니다.  
  
7.  클릭 **인수** 를 닫으려면 활동 디자이너 왼쪽 아래에에서는 **인수** 창.  
  
8.  클릭 **변수** 표시 하려면 워크플로 디자이너 왼쪽 아래에에서는 **변수** 창.  
  
9. 클릭 **변수를 만들고**합니다.  
  
    > [!TIP]
    >  되지 않은 경우 **변수 만들기** 상자가 표시 됩니다을 클릭는 <xref:System.Activities.Statements.Flowchart> 활동을 워크플로 디자이너 화면을 선택 합니다.  
  
10. 형식 `Guess` 에 **이름** 상자 **Int32** 에서 **변수 형식** 드롭 다운 목록 및 다음 변수를 저장 하는 ENTER 누릅니다.  
  
11. 클릭 **변수를 만들고**합니다.  
  
12. 형식 `Target` 에 **이름** 상자 **Int32** 에서 **변수 형식** 드롭 다운 목록 및 다음 변수를 저장 하는 ENTER 누릅니다.  
  
13. 클릭 **변수** 를 닫으려면 활동 디자이너 왼쪽 아래에에서는 **변수** 창.  
  
### <a name="to-add-the-workflow-activities"></a>워크플로 활동을 추가하려면  
  
1.  끌어서는 **할당** 활동을는 **기본 형식** 의 섹션은 **도구 상자** 위로 가져갑니다는 **시작** 의 위쪽에 있는 노드는 순서도입니다. 경우는 **할당** 활동 스타일러스가 **시작** 노드를 주위에 삼각형 세 개가 표시 됩니다는 **시작** 노드. 삭제는 **할당** 바로 아래에 있는 삼각형에 활동의 **시작** 노드. 이 두 항목을 함께 연결 됩니다 하 고은 **할당** 순서도의 첫 번째 활동으로 작업 합니다.  
  
    > [!NOTE]
    >  시작 노드에 활동을 직접 연결하여 워크플로에서 해당 활동을 시작 활동으로 나타낼 수도 있습니다. 이렇게 하려면 위로 마우스를 가져가고는 **시작** 노드를 마우스를 위로 가져갈 때 나타나는 사각형 중 하나를 클릭는 **시작** 노드와 연결 된 아래로 끌어 원하는 활동 중 하나에 놓는 나타나는 사각형입니다. 또한 지정할 수 있습니다 및 it를 마우스 오른쪽 단추로 클릭 하 고 선택 하 여 활동을 시작 활동으로 활동 **시작 노드로 설정**합니다.  
  
2.  형식 `Target` 에 **를** 상자와에 다음 식을 **C# 식 입력** 또는 **VB 식 입력** 상자입니다.  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    >  경우는 **도구 상자** 창이 표시 되지 않으면, 선택 **도구 상자** 에서 **보기** 메뉴.  
  
3.  끌어서는 **프롬프트** 활동을는 **NumberGuessWorkflowActivities** 의 섹션은 **도구 상자**, 아래에 놓습니다는 **할당** 활동 이전 단계별로 실행 하며 연결 된 **프롬프트** 활동을는 **할당** 활동입니다. 두 활동을 연결하는 방법에는 세 가지가 있습니다. 첫 번째 방법은 놓을 때 연결 하는 **프롬프트** 워크플로에 활동입니다. 로 끌는 **프롬프트** 워크플로에 활동 위로 마우스를 가져가고는 **할당** 활동 때 표시 되는 4 개의 삼각형 중 하나에 놓습니다는 **프롬프트** 활동은 위에 **할당** 활동입니다. 두 번째 방법은 삭제 하는 **프롬프트** 활동을 워크플로의 원하는 위치에 놓으면 됩니다. 그런 다음 위로 마우스를 가져가고는 **할당** 활동 및 아래에 나타나는 사각형 중 하나는 끌어서는 **프롬프트** 활동입니다. 연결선이 되도록 마우스를 끌어는 **할당** 활동의 사각형 중 하나에 연결는 **프롬프트** 작업을 선택한 다음 마우스 단추를 놓습니다. 세 번째 방법은 매우 비슷합니다 끌어오는 방법 대신 점을 제외 하 고 첫 번째 방법은 **프롬프트** 활동을는 **도구 상자**, 워크플로 디자인 화면의 해당 위치에서 끌어는 위로마우스를가져가고 **할당** 활동에 나타나는 삼각형 중 하나에 놓습니다.  
  
4.  에 **속성 창** 에 대 한는 **프롬프트** 활동, 형식 `"EnterGuess"` 따옴표를 포함 하는 **BookmarkName** 속성 값 상자입니다. 형식 `Guess` 에 **결과** 속성 값 상자에 다음 식을 입력 하 고는 **텍스트** 속성 상자입니다.  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
    > [!TIP]
    >  경우는 **속성 창** 가 표시 되지 않는 select **속성 창** 에서 **보기** 메뉴.  
  
5.  끌어서는 **할당** 활동을는 **기본 형식** 의 섹션은 **도구 상자** 는 아래에이전단계에서설명하는방법중하나를사용하여연결하고 **Prompt** 활동입니다.  
  
6.  형식 `Turns` 에 **를** 상자 및 `Turns + 1` 에 **C# 식 입력** 또는 **VB 식 입력** 상자입니다.  
  
7.  끌어서는 **FlowDecision** 에서 **순서도** 의 섹션은 **도구 상자** 아래에 연결 하 고는 **할당** 활동입니다. 에 **속성 창**에 다음 식을 입력는 **조건** 속성 값 상자입니다.  
  
    ```vb  
    Guess = Target  
    ```  
  
    ```csharp  
    Guess == Target  
    ```  
  
8.  다른 **FlowDecision** 활동을는 **도구 상자** 첫 번째 아래에 놓습니다. 레이블이 있는 사각형에서 끌어 두 활동을 연결 **False** 상단 **FlowDecision** 사각형에 두 번째 맨 위에 있는 활동 **FlowDecision**활동입니다.  
  
    > [!TIP]
    >  표시 되지 않으면는 **True** 및 **False** 레이블의 **FlowDecision**, 위로 마우스를 가져가고는 **FlowDecision**합니다.  
  
9. 두 번째 클릭 **FlowDecision** 활동을 선택 합니다. 에 **속성 창**에 다음 식을 입력는 **조건** 속성 값 상자입니다.  
  
    ```
    Guess < Target  
    ```  
  
10. 두 개 **WriteLine** 활동을는 **기본 형식** 의 섹션은 **도구 상자** 있도록 함께 두 아래에 놓으면 **FlowDecision**  활동입니다. 연결의 **True** 맨 **FlowDecision** 활동을 맨 왼쪽 **WriteLine** 활동 및 **False** 동작을는 맨 오른쪽 **WriteLine** 활동입니다.  
  
11. 가장 왼쪽에 있는 클릭 **WriteLine** 활동을 선택 하 고에 다음 식을 입력는 **텍스트** 속성 값 상자에 **속성 창**합니다.  
  
    ```
    "Your guess is too low."  
    ```  
  
12. 연결 된 **WriteLine** 의 왼쪽에는 **프롬프트** 그 보다 상위 활동입니다.  
  
13. 맨 오른쪽 클릭 **WriteLine** 활동을 선택 하 고에 다음 식을 입력는 **텍스트** 속성 값 상자에 **속성 창**합니다.  
  
    ```
    "Your guess is too high."  
    ```  
  
14. 연결의 **WriteLine** 활동의 오른쪽에는 **프롬프트** 상위 활동입니다.  
  
     다음 예제에서는 완료된 워크플로를 보여 줍니다.  
  
     ![Windows Workflow Foundation 완료](../../../docs/framework/windows-workflow-foundation/media/gettingstartedtutorialcompletedflowchart.PNG "GettingStartedTutorialCompletedFlowchart")  
  
### <a name="to-build-the-workflow"></a>워크플로를 빌드하려면  
  
1.  Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.  
  
     워크플로 실행 하는 방법에 대 한 지침은 다음 항목을 참조 하십시오 [하는 방법: 워크플로 실행](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md)합니다. 이미 완료 된 경우는 [하는 방법: 워크플로 실행](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md) 워크플로의 다른 스타일이 적용 된 단계와이 단계에서 순서도 워크플로 사용 하 여 실행 하려면,으로 바로 이동 하는 [빌드하고응용프로그램을실행하려면](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md#BKMK_ToRunTheApplication)섹션 [하는 방법: 워크플로 실행](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Activities.Statements.Flowchart>  
 <xref:System.Activities.Statements.FlowDecision>  
 [Windows Workflow Foundation 프로그래밍](../../../docs/framework/windows-workflow-foundation/programming.md)  
 [워크플로 디자인](../../../docs/framework/windows-workflow-foundation/designing-workflows.md)  
 [초보자를 위한 자습서](../../../docs/framework/windows-workflow-foundation/getting-started-tutorial.md)  
 [방법: 활동 만들기](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md)  
 [방법: 워크플로 실행](../../../docs/framework/windows-workflow-foundation/how-to-run-a-workflow.md)
