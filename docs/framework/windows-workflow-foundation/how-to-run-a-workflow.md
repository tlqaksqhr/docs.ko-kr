---
title: '방법: 워크플로 실행'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f814ff82-fe2b-4614-aebb-b768c3e61179
ms.openlocfilehash: 704527bde2ac6bf555d40db836baf938c0c5cd96
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33519521"
---
# <a name="how-to-run-a-workflow"></a>방법: 워크플로 실행
이 항목에서는 Windows Workflow Foundation 초보자를 위한 자습서에 포함된 일련의 항목 중 하나로, 워크플로 호스트를 만들고 이전 [How to: Create a Workflow](../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow.md) 항목에서 정의한 워크플로를 실행하는 방법을 설명합니다.  
  
> [!NOTE]
>  초보자를 위한 자습서의 각 항목은 이전 항목을 바탕으로 합니다. 이 항목을 진행하려면 먼저 [How to: Create an Activity](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md) 및 [How to: Create a Workflow](../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow.md)를 완료해야 합니다.  
  
> [!NOTE]
>  자습서의 전체 버전을 다운로드하려면 [Windows Workflow Foundation(WF45) - 초보자를 위한 자습서](http://go.microsoft.com/fwlink/?LinkID=248976)를 참조하세요.  
  
### <a name="to-create-the-workflow-host-project"></a>워크플로 호스트 프로젝트를 만들려면  
  
1.  이전 솔루션을 엽니다 [하는 방법: 활동 만들기](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md) 를 사용 하 여 항목 [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)]합니다.  
  
2.  **솔루션 탐색기** 에서 **WF45GettingStartedTutorial** 솔루션을 마우스 오른쪽 단추로 클릭하고 **추가**, **새 프로젝트**를 차례로 선택합니다.  
  
    > [!TIP]
    >  **솔루션 탐색기** 창이 표시되어 있지 않으면 **보기** 메뉴에서 **솔루션 탐색기** 를 선택합니다.  
  
3.  **설치됨** 노드에서 **Visual C#**, **워크플로** (또는 **Visual Basic**, **워크플로**)를 차례로 선택합니다.  
  
    > [!NOTE]
    >  **설치됨** 노드의 **다른 언어** 노드 아래에는 Visual Studio에서 기본 언어로 구성된 프로그래밍 언어에 따라 **Visual C#** 또는 **Visual Basic** 노드가 표시될 수 있습니다.  
  
     .NET Framework 버전 드롭다운 목록에서 **.NET Framework 4.5** 가 선택되어 있는지 확인합니다. **워크플로** 목록에서 **워크플로 콘솔 응용 프로그램** 을 선택합니다. `NumberGuessWorkflowHost` 이름 **상자에** 를 입력하고 **확인**을 클릭합니다. 이렇게 하면 기본 워크플로 호스팅 지원이 포함된 시작 워크플로 응용 프로그램이 만들어집니다. 이 기본 호스팅 코드를 수정하고 이를 사용하여 워크플로 응용 프로그램을 실행합니다.  
  
4.  **솔루션 탐색기** 에서 새로 추가한 **NumberGuessWorkflowHost** 프로젝트를 마우스 오른쪽 단추로 클릭하고 **참조 추가**를 선택합니다. **참조 추가** 목록에서 **솔루션** 을 선택하고 **NumberGuessWorkflowActivities**옆의 확인란을 선택한 다음 **확인**을 클릭합니다.  
  
5.  **솔루션 탐색기** 에서 **Workflow1.xaml** 을 마우스 오른쪽 단추로 클릭하고 **삭제**를 선택합니다. **확인** 을 클릭하여 확인합니다.  
  
### <a name="to-modify-the-workflow-hosting-code"></a>워크플로 호스팅 코드를 수정하려면  
  
1.  **솔루션 탐색기** 에서 **Program.cs** 또는 **Module1.vb** 를 두 번 클릭하여 코드를 표시합니다.  
  
    > [!TIP]
    >  **솔루션 탐색기** 창이 표시되어 있지 않으면 **보기** 메뉴에서 **솔루션 탐색기** 를 선택합니다.  
  
     이 프로젝트는 **워크플로 콘솔 응용 프로그램** 템플릿을 사용하여 만들었기 때문에 **Program.cs** 또는 **Module1.vb** 에 다음과 같은 기본 워크플로 호스팅 코드가 포함되어 있습니다.  
  
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
  
     이 생성된 호스팅 코드에서는 <xref:System.Activities.WorkflowInvoker>를 사용합니다. <xref:System.Activities.WorkflowInvoker> 는 메서드 호출과 같은 방식으로 워크플로를 호출하기 위한 간단한 방법을 제공하며, 지속성을 사용하지 않는 워크플로에만 사용될 수 있습니다. <xref:System.Activities.WorkflowApplication> 은 수명 주기 이벤트 알림, 실행 제어, 책갈피 다시 시작 및 지속성을 비롯한 다양한 워크플로 실행 모델을 제공합니다. 이 예제에서는 책갈피를 사용하며 <xref:System.Activities.WorkflowApplication> 을 사용하여 워크플로를 호스트합니다. 기존 `using` using **또는** Imports **문 아래의** Program.cs **또는** Module1.vb **위에 다음** 또는 **Imports** 문을 추가합니다.  
  
    ```vb  
    Imports NumberGuessWorkflowActivities  
    Imports System.Threading  
    ```  
  
    ```csharp  
    using NumberGuessWorkflowActivities;  
    using System.Threading;  
    ```  
  
     <xref:System.Activities.WorkflowInvoker> 를 사용하는 코드 행을 다음과 같은 기본 <xref:System.Activities.WorkflowApplication> 호스팅 코드로 바꿉니다. 이 샘플 호스팅 코드는 워크플로를 호스팅 및 호출하기 위한 기본 단계를 보여 주지만 이 항목에서 워크플로를 실행하는 기능은 아직 포함하고 있지 않습니다. 다음 단계에서는 응용 프로그램이 완료될 때까지 이 기본 코드를 수정하고 기능을 추가합니다.  
  
    > [!NOTE]
    >  이러한 예제의 `Workflow1` 을 이전 `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`, `StateMachineNumberGuessWorkflow`또는 [How to: Create a Workflow](../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow.md) 로 바꾸세요. `Workflow1` 을 바꾸지 않으면 워크플로를 빌드하거나 실행할 때 빌드 오류가 발생합니다.  
  
     [!code-csharp[CFX_WF_GettingStarted#4](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/extrasnippets.cs#4)]
     [!code-vb[CFX_WF_GettingStarted#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/extrasnippets.vb#4)]  
  
     이 코드는 <xref:System.Activities.WorkflowApplication>을 만들고 세 가지 워크플로 수명 주기 이벤트를 구독한 다음 <xref:System.Activities.WorkflowApplication.Run%2A>을 호출하여 워크플로를 시작하고 워크플로가 완료될 때까지 대기합니다. 워크플로가 완료되면 <xref:System.Threading.AutoResetEvent> 가 설정되고 호스트 응용 프로그램이 완료됩니다.  
  
### <a name="to-set-input-arguments-of-a-workflow"></a>워크플로의 입력 인수를 설정하려면  
  
1.  **Program.cs** 또는 **Module1.vb** 맨 위의 기존 `using` 또는 `Imports` 문 아래에 다음 문을 추가합니다.  
  
     [!code-csharp[CFX_WF_GettingStarted#5](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#5)]
     [!code-vb[CFX_WF_GettingStarted#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#5)]  
  
2.  새로운 <xref:System.Activities.WorkflowApplication> 을 만드는 코드 행을 코드 생성 시 매개 변수 사전을 만들어 워크플로에 전달하는 다음 코드로 바꿉니다.  
  
    > [!NOTE]
    >  이러한 예제의 `Workflow1` 을 이전 `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`, `StateMachineNumberGuessWorkflow`또는 [How to: Create a Workflow](../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow.md) 로 바꾸세요. `Workflow1` 을 바꾸지 않으면 워크플로를 빌드하거나 실행할 때 빌드 오류가 발생합니다.  
  
     [!code-csharp[CFX_WF_GettingStarted#6](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#6)]
     [!code-vb[CFX_WF_GettingStarted#6](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#6)]  
  
     이 사전에는 `MaxNumber`키와 함께 요소 하나가 있습니다. 입력 사전의 키는 워크플로 루트 활동의 입력 인수에 해당합니다. `MaxNumber` 는 워크플로에서 임의로 생성되는 숫자의 상한을 결정하는 데 사용됩니다.  
  
### <a name="to-retrieve-output-arguments-of-a-workflow"></a>워크플로의 출력 인수를 검색하려면  
  
1.  <xref:System.Activities.WorkflowApplication.Completed%2A> 처리기를 수정하여 워크플로에서 사용된 횟수를 검색하고 표시합니다.  
  
     [!code-csharp[CFX_WF_GettingStarted#7](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#7)]
     [!code-vb[CFX_WF_GettingStarted#7](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#7)]  
  
### <a name="to-resume-a-bookmark"></a>책갈피를 다시 시작하려면  
  
1.  기존 `Main` 선언 바로 뒤 <xref:System.Threading.AutoResetEvent> 메서드 위에 다음 코드를 추가합니다.  
  
     [!code-csharp[CFX_WF_GettingStarted#8](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#8)]
     [!code-vb[CFX_WF_GettingStarted#8](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#8)]  
  
2.  <xref:System.Activities.WorkflowApplication.Idle%2A> 에서 세 개의 기존 워크플로 수명 주기 처리기 바로 아래에 다음 `Main`처리기를 추가합니다.  
  
     [!code-csharp[CFX_WF_GettingStarted#9](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#9)]
     [!code-vb[CFX_WF_GettingStarted#9](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#9)]  
  
     워크플로가 다음 추측을 대기하는 유휴 상태가 될 때마다 이 처리기가 호출되고 `idleAction` <xref:System.Threading.AutoResetEvent> 가 설정됩니다. 다음 단계의 코드에서는 `idleEvent` 와 `syncEvent` 를 사용하여 워크플로가 다음 추측을 대기하고 있는지 아니면 완료되었는지를 확인합니다.  
  
    > [!NOTE]
    >  이 예제에서는 호스트 응용 프로그램이 <xref:System.Activities.WorkflowApplication.Completed%2A> 및 <xref:System.Activities.WorkflowApplication.Idle%2A> 처리기에서 자동 재설정 이벤트를 사용하여 호스트 응용 프로그램을 워크플로 진행률과 동기화합니다. 책갈피를 다시 시작하기 전에 워크플로를 차단하고 워크플로가 유휴 상태가 될 때까지 기다릴 필요는 없지만, 이 예제에서는 호스트에서 워크플로가 완료되었는지 아니면 <xref:System.Activities.Bookmark>를 사용하여 추가 사용자 입력을 대기하고 있는지 확인하기 위해 동기화 이벤트가 필요합니다. 자세한 내용은 참조 [책갈피](../../../docs/framework/windows-workflow-foundation/bookmarks.md)합니다.  
  
3.  `WaitOne`호출을 제거한 다음, 사용자 입력을 수집하고 <xref:System.Activities.Bookmark>를 다시 시작하는 코드로 대체합니다.  
  
     다음 코드 행을 제거합니다.  
  
     [!code-csharp[CFX_WF_GettingStarted#10](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/extrasnippets.cs#10)]
     [!code-vb[CFX_WF_GettingStarted#10](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/extrasnippets.vb#10)]  
  
     코드 행을 다음 예로 대체합니다.  
  
     [!code-csharp[CFX_WF_GettingStarted#11](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#11)]
     [!code-vb[CFX_WF_GettingStarted#11](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#11)]  
  
##  <a name="BKMK_ToRunTheApplication"></a> 응용 프로그램을 빌드하고 실행하려면  
  
1.  **솔루션 탐색기** 에서 **NumberGuessWorkflowHost** 를 마우스 오른쪽 단추로 클릭하고 **시작 프로젝트로 설정**을 선택합니다.  
  
2.  Ctrl+F5를 눌러 응용 프로그램을 빌드하고 실행합니다. 가능한 한 적은 횟수로 숫자를 추측해 봅니다.  
  
     다른 스타일의 워크플로 중 하나로 응용 프로그램을 시도하려면 `Workflow1` 을 만드는 코드의 <xref:System.Activities.WorkflowApplication> 을 원하는 워크플로 스타일에 따라 `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`또는 `StateMachineNumberGuessWorkflow`로 바꿉니다.  
  
     [!code-csharp[CFX_WF_GettingStarted#6](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#6)]
     [!code-vb[CFX_WF_GettingStarted#6](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#6)]  
  
     워크플로 응용 프로그램에 지속성을 추가하는 방법은 다음 항목 [How to: Create and Run a Long Running Workflow](../../../docs/framework/windows-workflow-foundation/how-to-create-and-run-a-long-running-workflow.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 다음 예는 `Main` 메서드에 대한 완전한 코드 목록입니다.  
  
> [!NOTE]
>  이러한 예제의 `Workflow1` 을 이전 `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`, `StateMachineNumberGuessWorkflow`또는 [How to: Create a Workflow](../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow.md) 로 바꾸세요. `Workflow1` 을 바꾸지 않으면 워크플로를 빌드하거나 실행할 때 빌드 오류가 발생합니다.  
  
 [!code-csharp[CFX_WF_GettingStarted#12](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#12)]
 [!code-vb[CFX_WF_GettingStarted#12](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#12)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Activities.WorkflowApplication>  
 <xref:System.Activities.Bookmark>  
 [Windows Workflow Foundation 프로그래밍](../../../docs/framework/windows-workflow-foundation/programming.md)  
 [초보자를 위한 자습서](../../../docs/framework/windows-workflow-foundation/getting-started-tutorial.md)  
 [방법: 워크플로 만들기](../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow.md)  
 [방법: 장기 실행 워크플로 만들기 및 실행](../../../docs/framework/windows-workflow-foundation/how-to-create-and-run-a-long-running-workflow.md)  
 [워크플로에서 입력 대기](../../../docs/framework/windows-workflow-foundation/waiting-for-input-in-a-workflow.md)  
 [워크플로 호스팅](../../../docs/framework/windows-workflow-foundation/hosting-workflows.md)
