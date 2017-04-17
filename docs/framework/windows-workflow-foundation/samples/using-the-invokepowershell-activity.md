---
title: "InvokePowerShell 활동 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 956251a0-31ca-4183-bf76-d277c08585df
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# InvokePowerShell 활동 사용
InvokePowerShell 샘플에서는 `InvokePowerShell` 활동을 사용하여 Windows PowerShell 명령을 호출하는 방법을 보여 줍니다.  
  
## 세부 항목  
  
-   Windows PowerShell 명령을 단순화한 새로운 버전입니다.  
  
-   Windows PowerShell 출력 파이프라인에서 값을 검색한 다음 워크플로 변수에 저장합니다.  
  
-   데이터를 Windows PowerShell에 명령을 실행하기 위한 입력 파이프라인으로 전달합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.계속하기 전에 다음\(기본\) 디렉터리를 확인하십시오.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780)로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하십시오.이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\PowerShell`  
  
## 추가 설명  
 이 샘플에는 다음 세 개의 프로젝트가 포함되어 있습니다.  
  
|프로젝트 이름|설명|기본 파일|  
|-------------|--------|-----------|  
|CodedClient|PowerShell 활동을 사용하는 샘플 클라이언트 응용 프로그램입니다.|-   **Program.cs**: InvokePowerShell 활동을 호출하는 시퀀스 기반 워크플로를 프로그래밍 방식으로 만듭니다.|  
|DesignerClient|`InvokePowerShell` 사용자 지정 활동 및 기타 사용자 지정 활동이 포함된 사용자 지정 활동 집합과 이를 사용하는 워크플로입니다.|<ul><li>활동:<br /><br /> <ul><li>**PrintCollection.cs**: 컬렉션의 모든 항목을 콘솔에 출력하는 도우미 활동입니다.</li><li>**ReadLine.cs**: 콘솔에서 입력을 읽기 위한 도우미 활동입니다.</li></ul></li><li>파일 시스템:<br /><br /> <ul><li>**Copy.xaml**: 파일을 복사하는 활동입니다.</li><li>**CreateFile.xaml**: 파일을 만드는 활동입니다.</li><li>**DeleteFile.xaml**: 파일을 삭제하는 활동입니다.</li><li>**MakeDir.xaml**: 디렉터리를 만드는 활동입니다.</li><li>**Move.xaml**: 파일을 이동하는 활동입니다.</li><li>**ReadFile.xaml**: 파일을 읽은 후 파일 내용을 반환하는 활동입니다.</li><li>**TestPath.xaml**: 경로가 있는지 테스트하는 활동입니다.</li></ul></li><li>프로세스:<br /><br /> <ul><li>**GetProcess.xaml**: 실행 중인 프로세스 목록을 가져오는 활동입니다.</li><li>**StopProcess.xaml**: 특정 프로세스를 중지하는 활동입니다.</li></ul></li><li>**Program.cs**: Sequence1 워크플로를 호출합니다.</li><li>**Sequence1.xaml**: 시퀀스 기반 워크플로입니다.</li></ul>|  
|PowerShell|`InvokePowerShell` 활동 및 이 활동과 연결된 디자이너입니다.|활동 파일<br /><br /> -   **ExecutePowerShell.cs**: 활동의 기본 실행 논리입니다.<br />-   **InvokePowerShell.cs**: 기본 실행 논리에 대한 래퍼이며, 제네릭\(반환 값\) 버전과 비제네릭\(비반환 값\) 버전을 포함하고 있습니다.이는 활동의 공용 인터페이스입니다.<br />-   **NoPersistZone.cs**: 이 활동은 자식 활동이 지속되지 않게 합니다.이 클래스는 `InvokePowerShell` 활동 구현 내에서 실행 도중에 활동이 지속되지 않게 하는 데 사용됩니다.<br /><br /> 디자이너 파일:<br /><br /> 1.  **ArgumentDictionaryEditor.cs**: 사용자가 `InvokePowerShell` 활동의 인수를 편집할 수 있는 Windows 대화 상자입니다.<br />2.  **GenericInvokePowerShellDesigner.xaml** 및 **GenericInvokePowerShellDesigner.xaml.cs**: [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)]에서 제네릭 `InvokePowerShell` 활동의 모양을 정의합니다.<br />3.  **InvokePowerShellDesigner.xaml** 및 **InvokePowerShellDesigner.cs**: [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)]에서 비제네릭 `InvokePowerShell` 활동의 모양을 정의합니다.|  
  
 클라이언트 프로젝트의 사용 방법을 이해하면 PowerShell 활동의 내부 기능을 쉽게 이해할 수 있기 때문에 클라이언트 프로젝트에 대해 먼저 설명합니다.  
  
## 이 샘플의 사용법  
 다음 단원에서는 샘플에 있는 세 개의 프로젝트를 사용하는 방법에 대해 설명합니다.  
  
### 코딩된 클라이언트 프로젝트 사용법  
 샘플 클라이언트는 `InvokePowerShell` 활동의 여러 사용 방법 예제가 포함된 시퀀스 활동을 프로그래밍 방식으로 만듭니다.첫 번째 호출에서는 메모장을 시작합니다.  
  
```  
new InvokePowerShell()  
{  
    CommandText = "notepad"  
},  
  
```  
  
 두 번째 호출에서는 로컬 컴퓨터에서 실행 중인 프로세스 목록을 가져옵니다.  
  
```  
new InvokePowerShell<Process>()  
{  
    CommandText = "Get-Process",  
    Output = processes1,  
},  
  
```  
  
 `Output`은 명령의 출력을 저장하는 데 사용되는 변수입니다.  
  
 다음 호출에서는 PowerShell 호출의 각 출력에 대해 후처리 단계를 실행하는 방법을 보여 줍니다.`InitializationAction`은 각 프로세스에 대한 문자열 표현을 출력하는 함수로 설정됩니다.이 문자열의 컬렉션은 `InvokePowerShell<string>` 활동에 의해 `Output` 변수에 반환됩니다.  
  
 그 다음 `InvokePowerShell` 호출에서는 데이터를 활동에 전달하고 출력과 오류를 가져오는 방법을 보여 줍니다.  
  
### 디자이너 클라이언트 프로젝트 사용법  
 디자이너 클라이언트 프로젝트는 사용자 지정 활동 집합으로 구성되며, 그 중 대부분의 활동이 `InvokePowerShell` 활동을 포함하여 빌드됩니다.대부분의 활동은 비제네릭 버전의 `InvokePowerShell` 활동을 호출하며 반환 값을 기다리지 않습니다.그 외 활동은 제네릭 버전의 `InvokePowerShell` 활동을 사용하고 `InitializationAction` 인수를 사용하여 결과에 대한 후처리 작업을 수행합니다.  
  
## PowerShell 프로젝트 사용법  
 활동의 기본 동작은 `ExecutePowerShell` 클래스에서 수행됩니다.PowerShell 명령을 실행할 때 기본 워크플로 스레드가 차단되지 않아야 하기 때문에 <xref:System.Activities.AsyncCodeActivity> 클래스에서 상속하여 비동기 활동이 되도록 활동을 만듭니다.  
  
 워크플로 런타임에서 <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> 메서드를 호출하여 활동을 실행하기 시작합니다.PowerShell API를 호출하여 PowerShell 파이프라인을 만드는 작업으로 시작합니다.  
  
```  
runspace = RunspaceFactory.CreateRunspace();  
runspace.Open();  
pipeline = runspace.CreatePipeline();  
  
```  
  
 그런 다음 PowerShell 명령을 만들고 매개 변수 및 변수로 채웁니다.  
  
```  
Command cmd = new Command(this.CommandText, this.IsScript);   
// loop over parameters and run: cmd.Parameters.Add(...)  
// loop over variables and run: runspace.SessionStateProxy.SetVariable(...)  
pipeline.Commands.Add(cmd);  
  
```  
  
 이때 전송된 입력도 파이프라인으로 보내집니다.마지막으로 파이프라인이 `PipelineInvokerAsyncResult` 개체에 래핑되고 반환됩니다.`PipelineInvokerAsyncResult` 개체는 수신기를 등록하고 파이프라인을 호출합니다.  
  
```  
pipeline.InvokeAsync();  
  
```  
  
 실행이 완료되면 출력과 오류가 동일한 `PipelineInvokerAsyncResult` 개체 내에 저장되고 원래 <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A>에 전달된 콜백 메서드를 호출하여 컨트롤이 워크플로 런타임에 다시 전달됩니다.  
  
 메서드 실행이 끝나면 워크플로 런타임이 활동의 <xref:System.Activities.AsyncCodeActivity.EndExecute%2A> 메서드를 호출합니다.  
  
 `InvokePowerShell` 클래스는 `ExecutePowerShellCommand` 클래스를 래핑하고 두 버전의 활동, 즉 제네릭 버전과 비제네릭 버전을 만듭니다.제네릭 버전은 개별 결과를 제네릭 형식으로 변환하는 반면 비제네릭 버전은 PowerShell 실행 출력을 직접 반환합니다.  
  
 제네릭 버전의 활동은 `ExecutePowerShellCommand`를 호출하고 결과에 대한 후처리 작업을 수행하는 순차 워크플로로 구현됩니다.결과 컬렉션의 각 요소에 대한 후처리 단계가 설정되어 있으면 `InitializationAction`을 호출하고,그렇지 않으면 간단한 캐스팅을 수행합니다.  
  
```  
new ForEach<PSObject>  
{  
    Values = psObjects,  
    Body = new ActivityAction<PSObject>  
    {  
        Argument = psObject,  
        Handler = new Sequence  
        {  
            Activities =  
            {  
                new If  
                {  
                    Condition = // Is InitializationAction set?  
                    Then = new InvokeFunc<PSObject, TResult>  
                    {  
                        Argument = psObject,  
                        Result = outputObject,  
                        Func = this.InitializationAction  
                    },  
                    Else = new Assign<TResult>  
                    {  
                        To = outputObject,  
                        Value = new InArgument<TResult>(ctx => (TResult) psObject.Get(ctx).BaseObject),  
                    }  
                },  
                new AddToCollection<TResult>  
                {  
                    Collection = outputObjects,  
                    Item = outputObject  
                },  
            }  
        }  
    }  
},  
  
```  
  
 두 `InvokePowerShell` 활동\(제네릭 및 비제네릭 버전\) 각각에 대해 디자이너를 만들었습니다.InvokePowerShellDesigner.xaml 및 이 파일과 연결된 .cs 파일은 [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)]에서 비제네릭 버전의 `InvokePowerShell` 활동에 대한 모양을 정의합니다.InvokePowerShellDesigner.xaml 내부에서 <xref:System.Windows.Controls.DockPanel>은 그래픽 인터페이스를 나타내는 데 사용됩니다.  
  
```  
<DockPanel x:Uid="DockPanel_1" LastChildFill="True">  
        <TextBlock x:Uid="TextBlock_1" Text="CommandText" />  
        <TextBox x:Uid="TextBox_1" Text="{Binding Path=ModelItem.CommandText, Mode=TwoWay}"  
                 TextWrapping="WrapWithOverflow"  AcceptsReturn="True" MinLines="4" MaxLines="4"  
                 Background="{x:Null}" Margin="3" />  
    </DockPanel>  
  
```  
  
 텍스트 상자의 `Text` 속성은 활동의 `CommandText` 속성을 디자이너에 대한 입력 값과 동일하게 만드는 양방향 바인딩입니다.  
  
 GenericInvokePowerShellDesigner.xaml 및 이 파일과 연결된 .cs 파일은 제네릭 `InvokePowerShell` 활동의 그래픽 인터페이스를 정의합니다.디자이너는 사용자가 `InitializationAction`을 설정할 수 있게 하므로 조금 더 복잡합니다.<xref:System.Activities.Presentation.WorkflowItemPresenter>를 사용하여 자식 활동을 `InvokePowerShell` 디자이너 화면으로 끌어서 놓을 수 있게 한다는 점이 주요 요소입니다.  
  
```  
<sap:WorkflowItemPresenter x:Uid="sap:WorkflowItemPresenter_1" Margin="0,10,0,10"  
    HintText="Drop Activities Here"  
    AllowedItemType="{x:Type sa:Activity}"  
    Item="{Binding Path=ModelItem.InitializationAction.Handler, Mode=TwoWay}"  
    Grid.Row="1" Grid.Column="1" />  
  
```  
  
 디자이너 사용자 지정은 디자인 캔버스에서 활동의 모양을 정의하는 .xaml 파일로 끝나지 않습니다.활동의 매개 변수를 표시하는 데 사용되는 대화 상자도 사용자 지정할 수 있습니다.이 매개 변수와 PowerShell 변수는 PowerShell 명령의 동작에 영향을 줍니다.활동은 이 매개 변수와 변수를 <xref:System.Collections.Generic.Dictionary%601> 형식으로 노출합니다.ArgumentDictionaryEditor.cs, PropertyEditorResources.xaml 및 PropertyEditorResources.cs는 이러한 형식을 편집할 수 있는 대화 상자를 정의합니다.  
  
## 샘플을 설치, 빌드 및 실행하려면  
 이 샘플을 실행하려면 Windows PowerShell을 설치해야 합니다.[Windows PowerShell](http://go.microsoft.com/fwlink/?LinkId=150383) 위치에서 Windows PowerShell을 설치할 수 있습니다.  
  
#### 코딩된 클라이언트를 실행하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]을 사용하여 PowerShell.sln을 엽니다.  
  
2.  솔루션을 마우스 오른쪽 단추로 클릭하고 빌드합니다.  
  
3.  **CodedClient** 프로젝트를 마우스 오른쪽 단추로 클릭하고 **시작 프로젝트로 설정**을 선택합니다.  
  
4.  Ctrl\+F5를 눌러 응용 프로그램을 실행합니다.  
  
#### 디자이너 클라이언트를 실행하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]을 사용하여 PowerShell.sln을 엽니다.  
  
2.  솔루션을 마우스 오른쪽 단추로 클릭하고 빌드합니다.  
  
3.  **DesignerClient** 프로젝트를 마우스 오른쪽 단추로 클릭하고 **시작 프로젝트로 설정**을 선택합니다.  
  
4.  Ctrl\+F5를 눌러 응용 프로그램을 실행합니다.  
  
## 알려진 문제  
  
1.  다른 프로젝트의 `InvokePowerShell` 활동 어셈블리 또는 프로젝트를 참조할 때 빌드 오류가 발생하는 경우 새 프로젝트의 .csproj 파일에서 `InvokePowerShell`을 참조하는 줄 아래에 `<SpecificVersion>True</SpecificVersion>` 요소를 수동으로 추가해야 할 수 있습니다.  
  
2.  Windows PowerShell이 설치되어 있지 않으면 `InvokePowerShell` 활동을 워크플로에 추가하는 즉시 Visual Studio에 다음과 같은 오류 메시지가 표시됩니다. `Workflow Designer에서 문서에 문제가 발생했습니다. ‘System.Management.Automation’ ... 또는 여기에 종속되어 있는 파일이나 어셈블리 중 하나를 로드할 수 없습니다. 지정한 파일을 찾을 수 없습니다.`  
  
3.  Windows PowerShell 2.0에서 `$input.MoveNext()`를 프로그래밍 방식으로 호출하면 실패하며 `$input.MoveNext()`를 사용하는 스크립트에서 의도하지 않은 오류 및 결과가 발생합니다.이 문제를 해결하려면 배열을 반복할 때 `MoveNext()`를 호출하는 대신 PowerShell 동사 `foreach`를 사용해 보십시오.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.계속하기 전에 다음\(기본\) 디렉터리를 확인하십시오.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780)로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하십시오.이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\PowerShell`  
  
## 참고 항목