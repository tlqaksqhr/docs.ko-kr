---
title: ".NET Framework 4.5의 정책 활동 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8e375e0c-d7c1-4d69-88ab-36d52db0aa7e
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# .NET Framework 4.5의 정책 활동
Policy4 활동을 사용하면 WF 3.5에서 제공되는 규칙 엔진을 사용하여 [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]\(WF 4.5\)의 [!INCLUDE[wf2](../../../../includes/wf2-md.md)]에서 직접 [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)]\(WF 3.5\)의 [!INCLUDE[wf2](../../../../includes/wf2-md.md)]<xref:System.Workflow.Activities.Rules.RuleSet> 개체를 사용할 수 있습니다.이 활동을 사용하여 WF 3.5 <xref:System.Workflow.Activities.Rules.RuleSet>을 만들고 실행할 수 있습니다.Windows Workflow Foundation의 일부로 포함된 WF 3.5 규칙 엔진[!INCLUDE[crabout](../../../../includes/crabout-md.md)] Windows Workflow Foundation 규칙 엔진 소개를 참조하십시오.[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]에서 규칙을 WF로 마이그레이션하는 방법은 [마이그레이션 지침](../../../../docs/framework/windows-workflow-foundation//migration-guidance.md)을 참조하십시오.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.계속하기 전에 다음\(기본\) 디렉터리를 확인하십시오.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780)로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하십시오.이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\Rules-Policy4`  
  
## 이 샘플의 프로젝트  
  
|프로젝트 이름|설명|기본 파일|  
|-------------|--------|-----------|  
|Policy4|Policy4 활동과 이 활동의 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 디자이너가 들어 있습니다.|**Policy4.cs**: Policy4 활동 정의입니다.<br /><br /> **PolicyDesigner.xaml**: Policy4 활동의 사용자 지정 디자이너입니다.이 디자이너는 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 규칙 엔진의 규칙 편집기\([RuleSetDialog 클래스](http://go.microsoft.com/fwlink/?LinkId=150378)\)를 사용합니다.|  
|ImperativeCodeClientSample|명령적 C\# 코드를 사용하는 Policy4 응용 프로그램을 사용하여 워크플로를 구성하고 실행하는 샘플 클라이언트 응용 프로그램입니다\([!INCLUDE[wf1](../../../../includes/wf1-md.md)] 디자이너가 사용되지 않음\).|**ApplyDiscount.rules**: [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 규칙 정의가 있는 파일입니다.<br /><br /> **Order.cs**: 고객 주문을 나타내는 형식입니다.이 형식의 개체에 규칙이 적용됩니다.<br /><br /> **Program.cs**: Policy4 활동이 있는 워크플로를 구성하고 실행하여 ApplyDiscount.rules에 정의된 규칙을 Order 개체의 인스턴스에 적용합니다.<br /><br /> **App.config**: 규칙 파일의 경로가 있는 구성 파일입니다.|  
|DesignerClientSample|[!INCLUDE[wf1](../../../../includes/wf1-md.md)] 디자이너에서 Policy4 응용 프로그램을 사용하여 워크플로를 구성하고 실행하는 샘플 클라이언트 응용 프로그램입니다.|**Sequence1.xaml**: Policy4 활동을 사용하여 규칙을 평가하는 순차 워크플로입니다.<br /><br /> `Program.cs`: Sequence1.xaml에 정의된 워크플로의 인스턴스를 실행합니다.|  
  
## Policy4 활동  
 Policy4 활동은 워크플로가 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] RuleSet을 실행할 수 있도록 하는 <xref:System.Activities.NativeActivity%601>에서 파생되는 클래스입니다.다음 코드 예제는 활동의 공용 OM에 대한 간략한 정의입니다.  
  
```csharp  
  
public class Policy4Activity<TResult>: NativeActivity<TResult>  
{  
    public RuleSet RuleSet  
  
    [IsRequired]  
    public InArgument Input  
  
    public OutArgument<ValidationErrorCollection> ValidationErrors  
}  
```  
  
|속성|설명|  
|--------|--------|  
|RuleSet|활동을 실행할 때 평가할 .NET Framework 3.5용 WF [RuleSet Class](http://go.microsoft.com/fwlink/?LinkId=150379)입니다.|  
|TargetObject|[RuleSet Class](http://go.microsoft.com/fwlink/?LinkId=150379)의 규칙이 평가되는 대상 개체입니다.|  
|ValidationError|실행하기 전에 대상 개체에 대해 [RuleSet Class](http://go.microsoft.com/fwlink/?LinkId=150379)의 유효성을 검사할 때 .NET Framework 3.5용 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 규칙 엔진에서 반환하는 유효성 검사 오류 목록입니다.|  
  
## Policy4 활동 디자이너  
 Policy4 디자이너는 코드를 작성하지 않고 Policy4 활동을 구성할 수 있는 기능을 추가합니다.솔루션을 빌드한 후에는 도구 상자의 **Microsoft.Samples.Activities.Rules** 섹션에 있습니다.  
  
 WF 디자이너를 사용하면 대상 개체와 RuleSet을 구성할 수 있습니다.**RuleSet 편집** 단추를 클릭하면 [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)]용 WF [RuleSetDialog Class](http://go.microsoft.com/fwlink/?LinkId=150378)가 표시됩니다.이 대화 상자는 다시 호스팅된 [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] 규칙 편집기입니다.이 편집기를 사용하여 Policy4 활동이 실행하는 규칙을 만들고 편집할 수 있습니다.  
  
## 이 샘플의 사용법  
 이 샘플을 실행하기 위한 특별한 설정 작업은 필요하지 않습니다.Visual Studio에서 솔루션을 열고 F5 키를 누르기만 하면 응용 프로그램이 실행됩니다.  
  
 이 샘플에는 두 개의 클라이언트 응용 프로그램인 ImperativeCodeClientSample과 DesignerClientSample이 포함되어 있습니다.ImperativeCodeClientSample 클라이언트에서는 C\# 명령적 코드를 사용하여 Policy4 활동을 구성 및 실행하는 방법을 보여 주고,DesignerClientSample에서는 디자이너를 사용하여 Policy4 활동을 구성 및 실행하는 방법을 보여 줍니다.  
  
#### ImperativeCodeClientSample 클라이언트 응용 프로그램을 실행하려면  
  
1.  [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]을 사용하여 Policy4Sample.sln 솔루션 파일을 엽니다.  
  
2.  **솔루션 탐색기**에서 **ImperativeCodeClientSample** 프로젝트를 마우스 오른쪽 단추로 클릭한 다음 **시작 프로젝트로 설정**을 선택합니다.  
  
3.  Ctrl\+F5를 눌러 프로젝트를 실행합니다.  
  
#### ImperativeCodeClientSample 클라이언트 응용 프로그램을 실행하려면  
  
1.  [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]을 사용하여 Policy4Sample.sln 솔루션 파일을 엽니다.  
  
2.  **솔루션 탐색기**에서 **DesignerClientSample** 프로젝트를 마우스 오른쪽 단추로 클릭합니다.  
  
    -   **시작 프로젝트로 설정**을 선택합니다.  
  
3.  프로젝트를 컴파일하려면 Ctrl\+Shift\+B를 누릅니다.  
  
4.  Ctrl\+F5를 눌러 프로젝트를 실행합니다.  
  
## 참고 항목