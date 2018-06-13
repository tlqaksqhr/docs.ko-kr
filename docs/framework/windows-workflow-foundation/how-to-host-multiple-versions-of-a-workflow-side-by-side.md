---
title: '방법: 여러 버전의 워크플로를 함께 호스팅'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 09c575df-e0a3-4f3b-9e01-a7ac59d65287
ms.openlocfilehash: d8fef8523f827ab91729054ee87544879b1f1aa3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33520489"
---
# <a name="how-to-host-multiple-versions-of-a-workflow-side-by-side"></a>방법: 여러 버전의 워크플로를 함께 호스팅
`WorkflowIdentity`는 워크플로 응용 프로그램 개발자에게 이름 및 버전을 워크플로 정의에 연결하는 방법을 제공하며, 이러한 정보는 지속형 워크플로 인스턴스와 연결됩니다. 이 ID 정보는 워크플로 응용 프로그램 개발자가 여러 버전의 워크플로 정의를 side-by-side로 실행하는 경우와 같은 시나리오를 가능하도록 하는 데 사용될 수 있으며 동적 업데이트와 같은 다른 기능의 토대를 제공합니다. 자습서의 이 단계에서는 `WorkflowIdentity`를 사용하여 여러 버전의 워크플로를 동시에 호스트하는 방법을 보여 줍니다.  
  
> [!NOTE]
>  를 전체 버전을 다운로드 하거나이 자습서의 비디오 연습을 보려면 참조 [Windows Workflow Foundation (WF45)-초보자를 위한 자습서](http://go.microsoft.com/fwlink/?LinkID=248976)합니다.  
  
## <a name="in-this-topic"></a>항목 내용  
 자습서의 이 단계에서는 추가 정보를 제공하도록 워크플로의 `WriteLine` 활동을 수정하고 새 `WriteLine` 활동을 추가합니다. 원래 워크플로와 업데이트된 워크플로를 모두 동시에 실행할 수 있도록 원래 워크플로 어셈블리의 복사본을 저장하고 호스트 응용 프로그램을 업데이트합니다.  
  
-   [NumberGuessWorkflowActivities 프로젝트의 복사본을 만들려면](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_BackupCopy)  
  
-   [워크플로 업데이트 하려면](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateWorkflows)  
  
    -   [StateMachine 워크플로 업데이트 하려면](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateStateMachine)  
  
    -   [순서도 워크플로 업데이트 하려면](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateFlowchart)  
  
    -   [순차 워크플로 업데이트 하려면](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateSequential)  
  
-   [이전 워크플로 버전을 포함 하도록 WorkflowVersionMap을 업데이트.](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_UpdateWorkflowVersionMap)  
  
-   [작성 하 고 응용 프로그램 실행](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md#BKMK_BuildAndRun)  
  
> [!NOTE]
>  이 항목의 단계를 수행하기 전에 응용 프로그램을 실행하고 각 유형의 여러 워크플로를 시작한 후 각 워크플로마다 한두 개의 숫자를 추측하세요. 이러한 지속 된 워크플로이 단계와 다음 단계에 사용 되 [하는 방법: 실행 중인 워크플로 인스턴스의 정의 업데이트](../../../docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md)합니다.  
  
> [!NOTE]
>  초보자를 위한 자습서의 각 단계는 이전 단계를 바탕으로 합니다. 이전 단계를 완료 하지 않은 경우에에서 자습서의 전체 버전을 다운로드할 수 있습니다 [Windows Workflow Foundation (WF45)-초보자를 위한 자습서](http://go.microsoft.com/fwlink/?LinkID=248976)합니다.  
  
###  <a name="BKMK_BackupCopy"></a> NumberGuessWorkflowActivities 프로젝트의 복사본을 만들려면  
  
1.  열기는 **WF45GettingStartedTutorial** 에서 솔루션 [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] 열려 있지 않으면입니다.  
  
2.  Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.  
  
3.  닫기는 **WF45GettingStartedTutorial** 솔루션입니다.  
  
4.  Windows 탐색기를 열고 및 자습서 솔루션 파일과 프로젝트 폴더가 있는 폴더로 이동합니다.  
  
5.  라는 새 폴더 만들기 **PreviousVersions** 와 같은 폴더에 **NumberGuessWorkflowHost** 및 **NumberGuessWorkflowActivities**합니다. 이 폴더는 이후 자습서 단계에서 사용되는 다른 버전의 워크플로가 포함된 어셈블리를 포함하는 데 사용됩니다.  
  
6.  탐색 하 고 **NumberGuessWorkflowActivities\bin\debug** 폴더 (또는 **bin\release** 프로젝트 설정에 따라). 복사 **NumberGuessWorkflowActivities.dll** 복사한는 **PreviousVersions** 폴더입니다.  
  
7.  이름 바꾸기 **NumberGuessWorkflowActivities.dll** 에 **PreviousVersions** 폴더를 **NumberGuessWorkflowActivities_v1.dll**합니다.  
  
    > [!NOTE]
    >  이 항목의 단계에서는 여러 버전의 워크플로를 포함하는 데 사용되는 어셈블리를 관리하는 한 가지 방법을 보여 줍니다. 어셈블리에 강력한 이름을 지정하거나 어셈블리를 전역 어셈블리 캐시에 등록하는 등의 다른 방법을 사용할 수도 있습니다.  
  
8.  라는 새 폴더 만들기 **NumberGuessWorkflowActivities_du** 와 같은 폴더에 **NumberGuessWorkflowHost**, **NumberGuessWorkflowActivities**, 및 새로 추가 **PreviousVersions** 폴더를 모든 파일과 하위 폴더를 복사 하 고는 **NumberGuessWorkflowActivities** 새 폴더  **NumberGuessWorkflowActivities_du** 폴더입니다. 활동의 초기 버전에 대 한 프로젝트의 백업 복사본이는 [하는 방법: 실행 중인 워크플로 인스턴스의 정의 업데이트](../../../docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md)합니다.  
  
9. 다시 열어는 **WF45GettingStartedTutorial** 에서 솔루션 [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)]합니다.  
  
###  <a name="BKMK_UpdateWorkflows"></a> 워크플로 업데이트 하려면  
 이 단원에서는 워크플로 정의를 업데이트합니다. 즉, 사용자의 추측에 대한 피드백을 제공하는 두 개의 `WriteLine` 활동을 업데이트하고, 숫자가 추측된 후 게임에 대한 추가 정보를 제공하는 새로운 `WriteLine` 활동을 추가합니다.  
  
####  <a name="BKMK_UpdateStateMachine"></a> StateMachine 워크플로 업데이트 하려면  
  
1.  **솔루션 탐색기**아래는 **NumberGuessWorkflowActivities** 두 번 클릭 **StateMachineNumberGuessWorkflow.xaml**합니다.  
  
2.  두 번 클릭은 **Guess Incorrect** 상태 시스템에서 전환 합니다.  
  
3.  `Text` 활동에서 맨 왼쪽 `WriteLine`의 `If`를 업데이트합니다.  
  
    ```vb  
    Guess & " is too low."  
    ```  
  
    ```csharp  
    Guess + " is too low."  
    ```  
  
4.  `Text` 활동에서 맨 오른쪽 `WriteLine`의 `If`를 업데이트합니다.  
  
    ```vb  
    Guess & " is too high."  
    ```  
  
    ```csharp  
    Guess + " is too high."  
    ```  
  
5.  전체 돌아갑니다 상태 워크플로 디자이너에서 컴퓨터 보기를 클릭 하 여 **StateMachine** 워크플로 디자이너의 맨 위에 표시 된 이동 경로에 있습니다.  
  
6.  두 번 클릭은 **Guess Correct** 상태 시스템에서 전환 합니다.  
  
7.  끌어서는 **WriteLine** 활동을는 **기본 형식** 섹션은 **도구 상자** 놓습니다는 **동작 작업 놓기 여기** 의 레이블을 전환 해야 합니다.  
  
8.  `Text` 속성 상자에 다음 식을 입력합니다.  
  
    ```vb  
    Guess & " is correct. You guessed it in " & Turns & " turns."  
    ```  
  
    ```csharp  
    Guess + " is correct. You guessed it in " + Turns + " turns."  
    ```  
  
####  <a name="BKMK_UpdateFlowchart"></a> 순서도 워크플로 업데이트 하려면  
  
1.  **솔루션 탐색기**아래는 **NumberGuessWorkflowActivities** 두 번 클릭 **FlowchartNumberGuessWorkflow.xaml**합니다.  
  
2.  맨 왼쪽 `Text` 활동의 `WriteLine`를 업데이트합니다.  
  
    ```vb  
    Guess & " is too low."  
    ```  
  
    ```csharp  
    Guess + " is too low."  
    ```  
  
3.  맨 오른쪽 `Text` 활동의 `WriteLine`를 업데이트합니다.  
  
    ```vb  
    Guess & " is too high."  
    ```  
  
    ```csharp  
    Guess + " is too high."  
    ```  
  
4.  끌어서는 **WriteLine** 활동을는 **기본 형식** 의 섹션은 **도구 상자** 의 놓기 지점에 놓습니다는 `True` 맨 위의의 동작 `FlowDecision` . `WriteLine` 활동이 순서도에 추가되고 `True`의 `FlowDecision` 동작에 연결됩니다.  
  
5.  `Text` 속성 상자에 다음 식을 입력합니다.  
  
    ```vb  
    Guess & " is correct. You guessed it in " & Turns & " turns."  
    ```  
  
    ```csharp  
    Guess + " is correct. You guessed it in " + Turns + " turns."  
    ```  
  
####  <a name="BKMK_UpdateSequential"></a> 순차 워크플로 업데이트 하려면  
  
1.  **솔루션 탐색기**아래는 **NumberGuessWorkflowActivities** 두 번 클릭 **SequentialNumberGuessWorkflow.xaml**합니다.  
  
2.  `Text` 활동에서 맨 왼쪽 `WriteLine`의 `If`를 업데이트합니다.  
  
    ```vb  
    Guess & " is too low."  
    ```  
  
    ```csharp  
    Guess + " is too low."  
    ```  
  
3.  `Text` 활동에서 맨 오른쪽 `WriteLine` 활동의 `If`를 업데이트합니다.  
  
    ```vb  
    Guess & " is too high."  
    ```  
  
    ```csharp  
    Guess + " is too high."  
    ```  
  
4.  끌어서는 **WriteLine** 활동을는 **기본 형식** 의 섹션은 **도구 상자** 후 놓습니다는 **DoWhile** 활동 있도록는  **WriteLine** 루트에 있는 마지막 활동은 `Sequence` 활동입니다.  
  
5.  `Text` 속성 상자에 다음 식을 입력합니다.  
  
    ```vb  
    Guess & " is correct. You guessed it in " & Turns & " turns."  
    ```  
  
    ```csharp  
    Guess + " is correct. You guessed it in " + Turns + " turns."  
    ```  
  
###  <a name="BKMK_UpdateWorkflowVersionMap"></a> 이전 워크플로 버전을 포함 하도록 WorkflowVersionMap을 업데이트.  
  
1.  두 번 클릭 **WorkflowVersionMap.cs** (또는 **WorkflowVersionMap.vb**)에서 고 **NumberGuessWorkflowHost** 프로젝트를 엽니다.  
  
2.  다음 `using`(또는 `Imports`) 문을 파일의 맨 위에 다른 `using`(또는 `Imports`) 문과 함께 추가합니다.  
  
    ```vb  
    Imports System.Reflection  
    Imports System.IO  
    ```  
  
    ```csharp  
    using System.Reflection;  
    using System.IO;  
    ```  
  
3.  세 개의 기존 워크플로 ID 선언 바로 아래에 세 개의 새 워크플로 ID를 추가합니다. 이러한 새 `v1` 워크플로 ID는 업데이트가 수행되기 전에 시작된 워크플로에 올바른 워크플로 정의를 제공하는 데 사용됩니다.  
  
    ```vb  
    'Current version identities.  
    Public StateMachineNumberGuessIdentity As WorkflowIdentity  
    Public FlowchartNumberGuessIdentity As WorkflowIdentity  
    Public SequentialNumberGuessIdentity As WorkflowIdentity  
  
    'v1 Identities.  
    Public StateMachineNumberGuessIdentity_v1 As WorkflowIdentity  
    Public FlowchartNumberGuessIdentity_v1 As WorkflowIdentity  
    Public SequentialNumberGuessIdentity_v1 As WorkflowIdentity  
    ```  
  
    ```csharp  
    // Current version identities.  
    static public WorkflowIdentity StateMachineNumberGuessIdentity;  
    static public WorkflowIdentity FlowchartNumberGuessIdentity;  
    static public WorkflowIdentity SequentialNumberGuessIdentity;  
  
    // v1 identities.  
    static public WorkflowIdentity StateMachineNumberGuessIdentity_v1;  
    static public WorkflowIdentity FlowchartNumberGuessIdentity_v1;  
    static public WorkflowIdentity SequentialNumberGuessIdentity_v1;  
    ```  
  
4.  `WorkflowVersionMap` 생성자에서 현재 워크플로 ID 세 개의 `Version` 속성을 `2.0.0.0`으로 업데이트합니다.  
  
    ```vb  
    'Add the current workflow version identities.  
    StateMachineNumberGuessIdentity = New WorkflowIdentity With  
    {  
        .Name = "StateMachineNumberGuessWorkflow",  
        .Version = New Version(2, 0, 0, 0)  
    }  
  
    FlowchartNumberGuessIdentity = New WorkflowIdentity With  
    {  
        .Name = "FlowchartNumberGuessWorkflow",  
        .Version = New Version(2, 0, 0, 0)  
    }  
  
    SequentialNumberGuessIdentity = New WorkflowIdentity With  
    {  
        .Name = "SequentialNumberGuessWorkflow",  
        .Version = New Version(2, 0, 0, 0)  
    }  
  
    map.Add(StateMachineNumberGuessIdentity, New StateMachineNumberGuessWorkflow())  
    map.Add(FlowchartNumberGuessIdentity, New FlowchartNumberGuessWorkflow())  
    map.Add(SequentialNumberGuessIdentity, New SequentialNumberGuessWorkflow())  
    ```  
  
    ```csharp  
    // Add the current workflow version identities.  
    StateMachineNumberGuessIdentity = new WorkflowIdentity  
    {  
        Name = "StateMachineNumberGuessWorkflow",  
        // Version = new Version(1, 0, 0, 0),  
        Version = new Version(2, 0, 0, 0)  
    };  
  
    FlowchartNumberGuessIdentity = new WorkflowIdentity  
    {  
        Name = "FlowchartNumberGuessWorkflow",  
        // Version = new Version(1, 0, 0, 0),  
        Version = new Version(2, 0, 0, 0)  
    };  
  
    SequentialNumberGuessIdentity = new WorkflowIdentity  
    {  
        Name = "SequentialNumberGuessWorkflow",  
        // Version = new Version(1, 0, 0, 0),  
        Version = new Version(2, 0, 0, 0)  
    };  
  
    map.Add(StateMachineNumberGuessIdentity, new StateMachineNumberGuessWorkflow());  
    map.Add(FlowchartNumberGuessIdentity, new FlowchartNumberGuessWorkflow());  
    map.Add(SequentialNumberGuessIdentity, new SequentialNumberGuessWorkflow());  
    ```  
  
     사전에 현재 버전의 워크플로를 추가하는 코드에서는 프로젝트에서 참조되는 현재 버전을 사용하므로 워크플로 정의를 초기화하는 코드를 업데이트할 필요가 없습니다.  
  
5.  생성자에서 사전에 현재 버전을 추가하는 코드 바로 뒤에 다음 코드를 추가합니다.  
  
    ```vb  
    'Initialize the previous workflow version identities.  
    StateMachineNumberGuessIdentity_v1 = New WorkflowIdentity With  
    {  
        .Name = "StateMachineNumberGuessWorkflow",  
        .Version = New Version(1, 0, 0, 0)  
    }  
  
    FlowchartNumberGuessIdentity_v1 = New WorkflowIdentity With  
    {  
        .Name = "FlowchartNumberGuessWorkflow",  
        .Version = New Version(1, 0, 0, 0)  
    }  
  
    SequentialNumberGuessIdentity_v1 = New WorkflowIdentity With  
    {  
        .Name = "SequentialNumberGuessWorkflow",  
        .Version = New Version(1, 0, 0, 0)  
    }  
    ```  
  
    ```csharp  
    // Initialize the previous workflow version identities.  
    StateMachineNumberGuessIdentity_v1 = new WorkflowIdentity  
    {  
        Name = "StateMachineNumberGuessWorkflow",  
        Version = new Version(1, 0, 0, 0)  
    };  
  
    FlowchartNumberGuessIdentity_v1 = new WorkflowIdentity  
    {  
        Name = "FlowchartNumberGuessWorkflow",  
        Version = new Version(1, 0, 0, 0)  
    };  
  
    SequentialNumberGuessIdentity_v1 = new WorkflowIdentity  
    {  
        Name = "SequentialNumberGuessWorkflow",  
        Version = new Version(1, 0, 0, 0)  
    };  
    ```  
  
     이러한 워크플로 ID는 해당 워크플로 정의의 초기 버전과 연결됩니다.  
  
6.  다음에는 워크플로 정의의 초기 버전이 포함된 어셈블리를 로드하고 해당 워크플로 정의를 만들어 사전에 추가합니다.  
  
    ```vb  
    'Add the previous version workflow identities to the dictionary along with  
    'the corresponding workflow definitions loaded from the v1 assembly.  
    'Assembly.LoadFile requires an absolute path so convert this relative path  
    'to an absolute path.  
    Dim v1AssemblyPath As String = "..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v1.dll"  
    v1AssemblyPath = Path.GetFullPath(v1AssemblyPath)  
    Dim v1Assembly As Assembly = Assembly.LoadFile(v1AssemblyPath)  
  
    map.Add(StateMachineNumberGuessIdentity_v1,  
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow"))  
  
    map.Add(SequentialNumberGuessIdentity_v1,  
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow"))  
  
    map.Add(FlowchartNumberGuessIdentity_v1,  
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow"))  
    ```  
  
    ```csharp  
    // Add the previous version workflow identities to the dictionary along with  
    // the corresponding workflow definitions loaded from the v1 assembly.  
    // Assembly.LoadFile requires an absolute path so convert this relative path  
    // to an absolute path.  
    string v1AssemblyPath = @"..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v1.dll";  
    v1AssemblyPath = Path.GetFullPath(v1AssemblyPath);  
    Assembly v1Assembly = Assembly.LoadFile(v1AssemblyPath);  
  
    map.Add(StateMachineNumberGuessIdentity_v1,  
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow") as Activity);  
  
    map.Add(SequentialNumberGuessIdentity_v1,  
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow") as Activity);  
  
    map.Add(FlowchartNumberGuessIdentity_v1,  
        v1Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow") as Activity);  
    ```  
  
     다음 예제에서는 업데이트된 전체 `WorkflowVersionMap` 클래스를 보여 줍니다.  
  
    ```vb  
    Public Module WorkflowVersionMap  
        Dim map As Dictionary(Of WorkflowIdentity, Activity)  
  
        'Current version identities.  
        Public StateMachineNumberGuessIdentity As WorkflowIdentity  
        Public FlowchartNumberGuessIdentity As WorkflowIdentity  
        Public SequentialNumberGuessIdentity As WorkflowIdentity  
  
        'v1 Identities.  
        Public StateMachineNumberGuessIdentity_v1 As WorkflowIdentity  
        Public FlowchartNumberGuessIdentity_v1 As WorkflowIdentity  
        Public SequentialNumberGuessIdentity_v1 As WorkflowIdentity  
  
        Sub New()  
            map = New Dictionary(Of WorkflowIdentity, Activity)  
  
            'Add the current workflow version identities.  
            StateMachineNumberGuessIdentity = New WorkflowIdentity With  
            {  
                .Name = "StateMachineNumberGuessWorkflow",  
                .Version = New Version(2, 0, 0, 0)  
            }  
  
            FlowchartNumberGuessIdentity = New WorkflowIdentity With  
            {  
                .Name = "FlowchartNumberGuessWorkflow",  
                .Version = New Version(2, 0, 0, 0)  
            }  
  
            SequentialNumberGuessIdentity = New WorkflowIdentity With  
            {  
                .Name = "SequentialNumberGuessWorkflow",  
                .Version = New Version(2, 0, 0, 0)  
            }  
  
            map.Add(StateMachineNumberGuessIdentity, New StateMachineNumberGuessWorkflow())  
            map.Add(FlowchartNumberGuessIdentity, New FlowchartNumberGuessWorkflow())  
            map.Add(SequentialNumberGuessIdentity, New SequentialNumberGuessWorkflow())  
  
            'Initialize the previous workflow version identities.  
            StateMachineNumberGuessIdentity_v1 = New WorkflowIdentity With  
            {  
                .Name = "StateMachineNumberGuessWorkflow",  
                .Version = New Version(1, 0, 0, 0)  
            }  
  
            FlowchartNumberGuessIdentity_v1 = New WorkflowIdentity With  
            {  
                .Name = "FlowchartNumberGuessWorkflow",  
                .Version = New Version(1, 0, 0, 0)  
            }  
  
            SequentialNumberGuessIdentity_v1 = New WorkflowIdentity With  
            {  
                .Name = "SequentialNumberGuessWorkflow",  
                .Version = New Version(1, 0, 0, 0)  
            }  
  
            'Add the previous version workflow identities to the dictionary along with  
            'the corresponding workflow definitions loaded from the v1 assembly.  
            'Assembly.LoadFile requires an absolute path so convert this relative path  
            'to an absolute path.  
            Dim v1AssemblyPath As String = "..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v1.dll"  
            v1AssemblyPath = Path.GetFullPath(v1AssemblyPath)  
            Dim v1Assembly As Assembly = Assembly.LoadFile(v1AssemblyPath)  
  
            map.Add(StateMachineNumberGuessIdentity_v1,  
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow"))  
  
            map.Add(SequentialNumberGuessIdentity_v1,  
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow"))  
  
            map.Add(FlowchartNumberGuessIdentity_v1,  
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow"))  
        End Sub  
  
        Public Function GetWorkflowDefinition(identity As WorkflowIdentity) As Activity  
            Return map(identity)  
        End Function  
  
        Public Function GetIdentityDescription(identity As WorkflowIdentity) As String  
            Return identity.ToString()  
        End Function  
    End Module  
    ```  
  
    ```csharp  
    public static class WorkflowVersionMap  
    {  
        static Dictionary<WorkflowIdentity, Activity> map;  
  
        // Current version identities.  
        static public WorkflowIdentity StateMachineNumberGuessIdentity;  
        static public WorkflowIdentity FlowchartNumberGuessIdentity;  
        static public WorkflowIdentity SequentialNumberGuessIdentity;  
  
        // v1 identities.  
        static public WorkflowIdentity StateMachineNumberGuessIdentity_v1;  
        static public WorkflowIdentity FlowchartNumberGuessIdentity_v1;  
        static public WorkflowIdentity SequentialNumberGuessIdentity_v1;  
  
        static WorkflowVersionMap()  
        {  
            map = new Dictionary<WorkflowIdentity, Activity>();  
  
            // Add the current workflow version identities.  
            StateMachineNumberGuessIdentity = new WorkflowIdentity  
            {  
                Name = "StateMachineNumberGuessWorkflow",  
                // Version = new Version(1, 0, 0, 0),  
                Version = new Version(2, 0, 0, 0)  
            };  
  
            FlowchartNumberGuessIdentity = new WorkflowIdentity  
            {  
                Name = "FlowchartNumberGuessWorkflow",  
                // Version = new Version(1, 0, 0, 0),  
                Version = new Version(2, 0, 0, 0)  
            };  
  
            SequentialNumberGuessIdentity = new WorkflowIdentity  
            {  
                Name = "SequentialNumberGuessWorkflow",  
                // Version = new Version(1, 0, 0, 0),  
                Version = new Version(2, 0, 0, 0)  
            };  
  
            map.Add(StateMachineNumberGuessIdentity, new StateMachineNumberGuessWorkflow());  
            map.Add(FlowchartNumberGuessIdentity, new FlowchartNumberGuessWorkflow());  
            map.Add(SequentialNumberGuessIdentity, new SequentialNumberGuessWorkflow());  
  
            // Initialize the previous workflow version identities.  
            StateMachineNumberGuessIdentity_v1 = new WorkflowIdentity  
            {  
                Name = "StateMachineNumberGuessWorkflow",  
                Version = new Version(1, 0, 0, 0)  
            };  
  
            FlowchartNumberGuessIdentity_v1 = new WorkflowIdentity  
            {  
                Name = "FlowchartNumberGuessWorkflow",  
                Version = new Version(1, 0, 0, 0)  
            };  
  
            SequentialNumberGuessIdentity_v1 = new WorkflowIdentity  
            {  
                Name = "SequentialNumberGuessWorkflow",  
                Version = new Version(1, 0, 0, 0)  
            };  
  
            // Add the previous version workflow identities to the dictionary along with  
            // the corresponding workflow definitions loaded from the v1 assembly.  
            // Assembly.LoadFile requires an absolute path so convert this relative path  
            // to an absolute path.  
            string v1AssemblyPath = @"..\..\..\PreviousVersions\NumberGuessWorkflowActivities_v1.dll";  
            v1AssemblyPath = Path.GetFullPath(v1AssemblyPath);  
            Assembly v1Assembly = Assembly.LoadFile(v1AssemblyPath);  
  
            map.Add(StateMachineNumberGuessIdentity_v1,  
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.StateMachineNumberGuessWorkflow") as Activity);  
  
            map.Add(SequentialNumberGuessIdentity_v1,  
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.SequentialNumberGuessWorkflow") as Activity);  
  
            map.Add(FlowchartNumberGuessIdentity_v1,  
                v1Assembly.CreateInstance("NumberGuessWorkflowActivities.FlowchartNumberGuessWorkflow") as Activity);  
        }  
  
        public static Activity GetWorkflowDefinition(WorkflowIdentity identity)  
        {  
            return map[identity];  
        }  
  
        public static string GetIdentityDescription(WorkflowIdentity identity)  
        {  
            return identity.ToString();  
        }  
    }  
    ```  
  
###  <a name="BKMK_BuildAndRun"></a> 작성 하 고 응용 프로그램 실행  
  
1.  Ctrl+Shift+B를 눌러 응용 프로그램을 빌드하고 Ctrl+F5를 눌러 시작합니다.  
  
2.  클릭 하 여 새 워크플로 시작 **새 게임**합니다. 워크플로의 버전이 상태 창에 표시되고 연결된 `WorkflowIdentity`에서 업데이트된 버전이 반영됩니다. 완료 시 워크플로 추적 파일을 볼 수 있도록 `InstanceId`를 적어 두고 게임이 완료될 때까지 추측 값을 입력합니다. 상태 창에 표시된 정보에 사용자의 추측 값이 나타나는 방식은 `WriteLine` 활동에 대한 업데이트에 따라 달라집니다.  
  
 **1과 10 사이의 숫자를 입력 하십시오.**  
**5 너무 높습니다.**   
**1과 10 사이의 숫자를 입력 하십시오.**   
**3 너무 높습니다.**   
**1과 10 사이의 숫자를 입력 하십시오.**   
**1 너무 낮습니다.**   
**1과 10 사이의 숫자를 입력 하십시오.**   
**축, 4 결과적으로 숫자를 추측 했습니다.**    
    > [!NOTE]
    >  `WriteLine` 활동에서 업데이트된 텍스트는 표시되지만 이 항목에서 추가된 최종 `WriteLine` 활동의 출력은 표시되지 않습니다. 상태 창은 `PersistableIdle` 처리기에 의해 업데이트되기 때문입니다. 워크플로는 완료 및 최종 활동 후에도 유휴 상태가 되지 않으므로 `PersistableIdle` 처리기가 호출되지 않습니다. 그러나 `Completed` 처리기에 의해 유사한 메시지가 상태 창에 표시됩니다. 필요한 경우 `Completed`에서 텍스트를 추출하여 상태 창에 표시하도록 `StringWriter` 처리기에 코드를 추가할 수 있습니다.  
  
3.  Windows 탐색기를 열고 탐색 하 고 **NumberGuessWorkflowHost\bin\debug** 폴더 (또는 **bin\release** 프로젝트 설정에 따라) 해당 하는 메모장을 사용 하 여 추적 파일을 열면 완료 된 워크플로에 합니다. 메모를 확인 하지 않은 경우는 `InstanceId`를 사용 하 여 올바른 추적 파일을 식별할 수 있습니다는 **수정한 날짜** Windows 탐색기에서 정보입니다.  
  
 **1과 10 사이의 숫자를 입력 하십시오.**  
**5 너무 높습니다.**   
**1과 10 사이의 숫자를 입력 하십시오.**   
**3 너무 높습니다.**   
**1과 10 사이의 숫자를 입력 하십시오.**   
**1 너무 낮습니다.**   
**1과 10 사이의 숫자를 입력 하십시오.**   
**2가 올바릅니다. 4 결과적으로 맞습니다.**      이 항목에서 추가된 `WriteLine`의 출력을 포함하여 업데이트된 `WriteLine` 출력이 추적 파일 내에 포함됩니다.  
  
4.  다시 숫자 추측 응용 프로그램으로 전환하고 업데이트를 수행하기 전에 시작된 워크플로 중 하나를 선택합니다. 상태 창 아래에 표시된 버전 정보를 확인하여 현재 선택된 워크플로의 버전을 식별할 수 있습니다. 몇 개의 추측 값을 입력한 후, 상태 업데이트가 이전 버전의 `WriteLine` 활동 출력과 일치하며 사용자의 추측 값을 포함하지 않음을 확인할 수 있습니다. 이는 이러한 워크플로가 `WriteLine` 업데이트가 없는 이전 워크플로 정의를 사용하기 때문입니다.  
  
     다음 단계에서 [하는 방법: 실행 중인 워크플로 인스턴스의 정의 업데이트](../../../docs/framework/windows-workflow-foundation/how-to-update-the-definition-of-a-running-workflow-instance.md), 실행 중인 `v1` 워크플로 인스턴스는 업데이트의 새로운 기능으로 포함 되므로 `v2` 인스턴스.
