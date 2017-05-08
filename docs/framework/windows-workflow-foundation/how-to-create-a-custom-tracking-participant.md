---
title: "방법: 사용자 지정 추적 참가자 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1b612c7e-2381-4a7c-b07a-77030415f2a3
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# 방법: 사용자 지정 추적 참가자 만들기
워크플로 추적을 통해 워크플로 실행 상태를 볼 수 있습니다.워크플로 런타임은 워크플로 수명 주기 이벤트, 활동 수명 주기 이벤트, 책갈피 다시 시작 및 오류를 설명하는 추적 레코드를 내보냅니다.이러한 추적 레코드는 추적 참가자에서 사용됩니다.[!INCLUDE[wf](../../../includes/wf-md.md)]에는 추적 레코드를 ETW\(Windows용 이벤트 추적\) 이벤트로 기록하는 표준 추적 참가자가 포함되어 있습니다.표준 참가자가 요구 사항에 맞지 않는 경우 사용자 지정 추적 참가자를 작성할 수도 있습니다.이 자습서 단계에서는 `WriteLine` 활동의 출력을 캡처하여 사용자에게 표시될 수 있도록 하는 추적 프로필 및 사용자 지정 추적 참가자를 만드는 방법에 대해 설명합니다.  
  
> [!NOTE]
>  초보자를 위한 자습서의 각 항목은 이전 항목을 바탕으로 합니다.이 항목을 진행하려면 먼저 이전 항목을 완료해야 합니다.자습서의 전체 버전을 다운로드하거나 비디오 연습을 보려면 [Windows Workflow Foundation\(WF45\) \- 초보자를 위한 자습서](http://go.microsoft.com/fwlink/?LinkID=248976)를 참조하십시오.  
  
## 항목 내용  
  
-   [사용자 지정 추적 참가자를 만들려면](../../../docs/framework/windows-workflow-foundation//how-to-create-a-custom-tracking-participant.md#BKMK_CustomTrackingParticipant)  
  
-   [추적 프로필을 만들고 추적 참가자를 등록하려면](../../../docs/framework/windows-workflow-foundation//how-to-create-a-custom-tracking-participant.md#BKMK_TrackingProfile)  
  
-   [추적 정보를 표시하려면](../../../docs/framework/windows-workflow-foundation//how-to-create-a-custom-tracking-participant.md#BKMK_DisplayTracking)  
  
-   [응용 프로그램을 빌드하고 실행하려면](../../../docs/framework/windows-workflow-foundation//how-to-create-a-custom-tracking-participant.md#BKMK_BuildAndRun)  
  
###  <a name="BKMK_CustomTrackingParticipant"></a> 사용자 지정 추적 참가자를 만들려면  
  
1.  **솔루션 탐색기**에서 **NumberGuessWorkflowHost**를 마우스 오른쪽 단추로 클릭하고 **추가**, **클래스**를 차례로 선택합니다.**이름** 상자에 `StatusTrackingParticipant`를 입력하고 **추가**를 클릭합니다.  
  
2.  다음 `using`\(또는 `Imports`\) 문을 파일의 맨 위에 다른 `using`\(또는 `Imports`\) 문과 함께 추가합니다.  
  
    ```vb  
    Imports System.Activities.Tracking  
    Imports System.IO  
    ```  
  
    ```csharp  
    using System.Activities.Tracking;  
    using System.IO;  
    ```  
  
3.  `TrackingParticipant`에서 상속하도록 `StatusTrackingParticipant` 클래스를 수정합니다.  
  
    ```vb  
    Public Class StatusTrackingParticipant  
        Inherits TrackingParticipant  
  
    End Class  
    ```  
  
    ```csharp  
    class StatusTrackingParticipant : TrackingParticipant  
    {  
    }  
    ```  
  
4.  다음 `Track` 메서드 재정의를 추가합니다.추적 레코드에는 여러 가지 유형이 있습니다.여기서는 활동 추적 레코드에 포함된 `WriteLine` 활동의 출력에 초점을 둡니다.`TrackingRecord`가 `WriteLine` 활동에 대한 `ActivityTrackingRecord`인 경우 `WriteLine`의 `Text`는 워크플로의 `InstanceId`에 따라 이름이 지정된 파일에 추가됩니다.이 자습서에서는 파일이 호스트 응용 프로그램의 현재 폴더에 저장됩니다.  
  
    ```vb  
    Protected Overrides Sub Track(record As TrackingRecord, timeout As TimeSpan)  
        Dim asr As ActivityStateRecord = TryCast(record, ActivityStateRecord)  
  
        If Not asr Is Nothing Then  
            If asr.State = ActivityStates.Executing And _  
            asr.Activity.TypeName = "System.Activities.Statements.WriteLine" Then  
  
                'Append the WriteLine output to the tracking  
                'file for this instance.  
                Using writer As StreamWriter = File.AppendText(record.InstanceId.ToString())  
                    writer.WriteLine(asr.Arguments("Text"))  
                    writer.Close()  
                End Using  
            End If  
        End If  
    End Sub  
    ```  
  
    ```csharp  
    protected override void Track(TrackingRecord record, TimeSpan timeout)  
    {  
        ActivityStateRecord asr = record as ActivityStateRecord;  
  
        if (asr != null)  
        {  
            if (asr.State == ActivityStates.Executing &&  
                asr.Activity.TypeName == "System.Activities.Statements.WriteLine")  
            {  
                // Append the WriteLine output to the tracking  
                // file for this instance  
                using (StreamWriter writer = File.AppendText(record.InstanceId.ToString()))  
                {  
                    writer.WriteLine(asr.Arguments["Text"]);  
                    writer.Close();  
                }  
            }  
        }  
    }  
    ```  
  
     추적 프로필이 지정되어 있지 않은 경우 기본 추적 프로필이 사용됩니다.기본 추적 프로필이 사용될 경우 모든 `ActivityStates`에 대해 추적 레코드가 내보내집니다.여기서는 `WriteLine` 활동의 수명 주기 동안 텍스트를 한 번만 캡처하면 되므로 `ActivityStates.Executing` 상태의 텍스트만 추출합니다.[추적 프로필을 만들고 추적 참가자를 등록하려면](../../../docs/framework/windows-workflow-foundation//how-to-create-a-custom-tracking-participant.md#BKMK_TrackingProfile)에서는 `WriteLine` `ActivityStates.Executing` 추적 레코드만 내보내도록 지정하는 추적 프로필을 만듭니다.  
  
###  <a name="BKMK_TrackingProfile"></a> 추적 프로필을 만들고 추적 참가자를 등록하려면  
  
1.  **솔루션 탐색기**에서 **WorkflowHostForm**을 마우스 오른쪽 단추로 클릭하고 **코드 보기**를 선택합니다.  
  
2.  다음 `using`\(또는 `Imports`\) 문을 파일의 맨 위에 다른 `using`\(또는 `Imports`\) 문과 함께 추가합니다.  
  
    ```vb  
    Imports System.Activities.Tracking  
    ```  
  
    ```csharp  
    using System.Activities.Tracking;  
    ```  
  
3.  워크플로 확장에 `StringWriter`를 추가하는 코드 바로 뒤와 워크플로 수명 주기 처리기 앞의 `ConfigureWorkflowApplication`에 다음 코드를 추가합니다.  
  
    ```vb  
    'Add the custom tracking participant with a tracking profile  
    'that only emits tracking records for WriteLine activities.  
    Dim query As New ActivityStateQuery()  
    query.ActivityName = "WriteLine"  
    query.States.Add(ActivityStates.Executing)  
    query.Arguments.Add("Text")  
  
    Dim profile As New TrackingProfile()  
    profile.Queries.Add(query)  
  
    Dim stp As New StatusTrackingParticipant()  
    stp.TrackingProfile = profile  
  
    wfApp.Extensions.Add(stp)  
    ```  
  
    ```csharp  
    // Add the custom tracking participant with a tracking profile  
    // that only emits tracking records for WriteLine activities.  
    StatusTrackingParticipant stp = new StatusTrackingParticipant  
    {  
        TrackingProfile = new TrackingProfile  
        {  
            Queries =   
            {  
                new ActivityStateQuery  
                {  
                    ActivityName = "WriteLine",  
                    States = { ActivityStates.Executing },  
                    Arguments = { "Text" }  
                }  
            }  
        }  
    };  
  
    wfApp.Extensions.Add(stp);  
    ```  
  
     이 추적 프로필은 `Executing` 상태의 `WriteLine` 활동에 대한 활동 상태 레코드만 사용자 지정 추적 참가자로 내보내도록 지정합니다.  
  
     코드를 추가한 후 `ConfigureWorkflowApplication`의 시작 부분은 다음 예제와 같게 됩니다.  
  
    ```vb  
    Private Sub ConfigureWorkflowApplication(wfApp As WorkflowApplication)  
        'Configure the persistence store.  
        wfApp.InstanceStore = store  
  
        'Add a StringWriter to the extensions. This captures the output  
        'from the WriteLine activities so we can display it in the form.  
        Dim sw As New StringWriter()  
        wfApp.Extensions.Add(sw)  
  
        'Add the custom tracking participant with a tracking profile  
        'that only emits tracking records for WriteLine activities.  
        Dim query As New ActivityStateQuery()  
        query.ActivityName = "WriteLine"  
        query.States.Add(ActivityStates.Executing)  
        query.Arguments.Add("Text")  
  
        Dim profile As New TrackingProfile()  
        profile.Queries.Add(query)  
  
        Dim stp As New StatusTrackingParticipant()  
        stp.TrackingProfile = profile  
  
        wfApp.Extensions.Add(stp)  
  
        'Workflow lifecycle handlers...  
    ```  
  
    ```csharp  
    private void ConfigureWorkflowApplication(WorkflowApplication wfApp)  
    {  
        // Configure the persistence store.  
        wfApp.InstanceStore = store;  
  
        // Add a StringWriter to the extensions. This captures the output  
        // from the WriteLine activities so we can display it in the form.  
        StringWriter sw = new StringWriter();  
        wfApp.Extensions.Add(sw);  
  
        // Add the custom tracking participant with a tracking profile  
        // that only emits tracking records for WriteLine activities.  
        StatusTrackingParticipant stp = new StatusTrackingParticipant  
        {  
            TrackingProfile = new TrackingProfile  
            {  
                Queries =   
                {  
                    new ActivityStateQuery  
                    {  
                        ActivityName = "WriteLine",  
                        States = { ActivityStates.Executing },  
                        Arguments = { "Text" }  
                    }  
                }  
            }  
        };  
  
        wfApp.Extensions.Add(stp);  
  
        // Workflow lifecycle handlers...  
    ```  
  
###  <a name="BKMK_DisplayTracking"></a> 추적 정보를 표시하려면  
  
1.  **솔루션 탐색기**에서 **WorkflowHostForm**을 마우스 오른쪽 단추로 클릭하고 **코드 보기**를 선택합니다.  
  
2.  `InstanceId_SelectedIndexChanged` 처리기에서 상태 창을 지우는 코드 바로 뒤에 다음 코드를 추가합니다.  
  
    ```vb  
    'If there is tracking data for this workflow, display it  
    'in the status window.  
    If File.Exists(WorkflowInstanceId.ToString()) Then  
        Dim status As String = File.ReadAllText(WorkflowInstanceId.ToString())  
        UpdateStatus(status)  
    End If  
    ```  
  
    ```csharp  
    // If there is tracking data for this workflow, display it  
    // in the status window.  
    if (File.Exists(WorkflowInstanceId.ToString()))  
    {  
        string status = File.ReadAllText(WorkflowInstanceId.ToString());  
        UpdateStatus(status);  
    }  
    ```  
  
     워크플로 목록에 새 워크플로가 선택된 경우 해당 워크플로에 대한 추적 레코드가 로드되어 상태 창에 표시됩니다.다음 예제는 전체 `InstanceId_SelectedIndexChanged` 처리기입니다.  
  
    ```vb  
    Private Sub InstanceId_SelectedIndexChanged(sender As Object, e As EventArgs) Handles InstanceId.SelectedIndexChanged  
        If InstanceId.SelectedIndex = -1 Then  
            Return  
        End If  
  
        'Clear the status window.  
        WorkflowStatus.Clear()  
  
        'If there is tracking data for this workflow, display it  
        'in the status window.  
        If File.Exists(WorkflowInstanceId.ToString()) Then  
            Dim status As String = File.ReadAllText(WorkflowInstanceId.ToString())  
            UpdateStatus(status)  
        End If  
  
        'Get the workflow version and display it.  
        'If the workflow is just starting then this info will not  
        'be available in the persistence store so do not try and retrieve it.  
        If Not WorkflowStarting Then  
            Dim instance As WorkflowApplicationInstance = _  
                WorkflowApplication.GetInstance(WorkflowInstanceId, store)  
  
            WorkflowVersion.Text = _  
                WorkflowVersionMap.GetIdentityDescription(instance.DefinitionIdentity)  
  
            'Unload the instance.  
            instance.Abandon()  
        End If  
    End Sub  
    ```  
  
    ```csharp  
    private void InstanceId_SelectedIndexChanged(object sender, EventArgs e)  
    {  
        if (InstanceId.SelectedIndex == -1)  
        {  
            return;  
        }  
  
        // Clear the status window.  
        WorkflowStatus.Clear();  
  
        // If there is tracking data for this workflow, display it  
        // in the status window.  
        if (File.Exists(WorkflowInstanceId.ToString()))  
        {  
            string status = File.ReadAllText(WorkflowInstanceId.ToString());  
            UpdateStatus(status);  
        }  
  
        // Get the workflow version and display it.  
        // If the workflow is just starting then this info will not  
        // be available in the persistence store so do not try and retrieve it.  
        if (!WorkflowStarting)  
        {  
            WorkflowApplicationInstance instance =  
                WorkflowApplication.GetInstance(this.WorkflowInstanceId, store);  
  
            WorkflowVersion.Text =  
                WorkflowVersionMap.GetIdentityDescription(instance.DefinitionIdentity);  
  
            // Unload the instance.  
            instance.Abandon();  
        }  
    }  
  
    ```  
  
###  <a name="BKMK_BuildAndRun"></a> 응용 프로그램을 빌드하고 실행하려면  
  
1.  Ctrl\+Shift\+B를 눌러 응용 프로그램을 빌드합니다.  
  
2.  Ctrl\+F5를 눌러 응용 프로그램을 시작합니다.  
  
3.  추측 게임의 범위와 시작할 워크플로 유형을 선택하고 **New Game**을 클릭합니다.**Guess** 상자에 추측 값을 입력하고 **Go**를 클릭하여 추측 값을 제출합니다.워크플로의 상태가 상태 창에 표시됩니다.이 출력은 `WriteLine` 활동에서 캡처됩니다.**Workflow Instance Id** 콤보 상자에서 다른 워크플로를 선택하여 해당 워크플로로 전환하고 현재 워크플로의 상태가 제거되었는지 확인합니다.다시 이전 워크플로로 전환하고 상태가 다음 예제와 같이 복원되었는지 확인합니다.  
  
    > [!NOTE]
    >  추적을 사용하도록 설정하기 전에 시작된 워크플로로 전환할 경우에는 상태가 표시되지 않습니다.그러나 추가로 숫자를 추측한 경우에는 이제 추적을 사용하도록 설정되었으므로 해당 상태가 저장됩니다.  
  
 **Please enter a number between 1 and 10**   
**Your guess is too high.**   
**Please enter a number between 1 and 10**    
    > [!NOTE]
    >  이 정보는 난수의 범위를 결정하는 데 유용하지만 이전에 추측한 값에 대한 정보는 포함되지 않습니다.이 정보는 다음 단계인 [방법: 여러 버전의 워크플로를 함께 호스팅](../../../docs/framework/windows-workflow-foundation//how-to-host-multiple-versions-of-a-workflow-side-by-side.md)에 있습니다.  
  
     워크플로 인스턴스 ID를 적어 두고 게임을 완료될 때까지 실행합니다.  
  
4.  Windows 탐색기를 열고 **NumberGuessWorkflowHost\\bin\\debug** 폴더\(또는 프로젝트 설정에 따라 **bin\\release**\)로 이동합니다.이 폴더에는 프로젝트 실행 파일 뿐만 아니라 GUID 파일 이름을 가진 파일도 있습니다.이전 단계에서 완료된 워크플로에서 워크플로 인스턴스 ID에 해당하는 파일을 확인하고 이 파일을 메모장에서 엽니다.추적 정보에는 다음과 유사한 정보가 포함됩니다.  
  
 **Please enter a number between 1 and 10**   
**Your guess is too high.**   
**Please enter a number between 1 and 10**   
**Your guess is too high.**   
**Please enter a number between 1 and 10**      이 추적 데이터에는 사용자의 추측 값이 포함되지 않을 뿐 아니라 워크플로의 최종 추측에 대한 정보도 포함되지 않습니다.추적 정보는 워크플로의 `WriteLine` 출력과 워크플로가 완료된 후 `Completed` 처리기에 의해 표시되는 최종 메시지로만 구성되기 때문입니다.자습서의 다음 단계인 [방법: 여러 버전의 워크플로를 함께 호스팅](../../../docs/framework/windows-workflow-foundation//how-to-host-multiple-versions-of-a-workflow-side-by-side.md)에서는 사용자의 추측 값을 표시하도록 기존 `WriteLine` 활동을 수정하고 최종 결과를 표시하는 추가 `WriteLine` 활동을 추가합니다.이러한 변경 내용이 통합된 후 [방법: 여러 버전의 워크플로를 함께 호스팅](../../../docs/framework/windows-workflow-foundation//how-to-host-multiple-versions-of-a-workflow-side-by-side.md)에서는 여러 버전의 워크플로를 동시에 호스팅하는 방법을 보여 줍니다.