---
title: "워크플로 및 활동과 XAML 간 serialize | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 37685b32-24e3-4d72-88d8-45d5fcc49ec2
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# 워크플로 및 활동과 XAML 간 serialize
어셈블리에 포함되어 있는 형식으로 컴파일하는 것 외에 워크플로 정의를 XAML로 serialize할 수도 있습니다.serialize된 이 정의를 다시 로드하여 편집 또는 검사하거나, 빌드 시스템에 전달하여 컴파일하거나, 로드 및 호출할 수 있습니다.이 항목에서는 워크플로 정의의 serialize와 XAML 워크플로 정의의 사용에 대해 간략하게 설명합니다.  
  
## XAML 워크플로 정의 사용  
 <xref:System.Activities.ActivityBuilder> 클래스를 사용하여 serialization에 대한 워크플로 정의를 만듭니다.<xref:System.Activities.ActivityBuilder>를 만드는 방법은 <xref:System.Activities.DynamicActivity>를 만드는 방법과 매우 비슷합니다.필요한 모든 인수를 지정하고 동작을 구성하는 활동을 구성합니다.다음 예제에서는 두 개의 인수를 가져와서 두 인수를 함께 추가하고 결과를 반환하는 `Add` 활동을 만듭니다.이 활동은 결과를 반환하므로 제네릭 <xref:System.Activities.ActivityBuilder%601> 클래스가 사용됩니다.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#41](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#41)]  
  
 각각의 <xref:System.Activities.DynamicActivityProperty> 인스턴스는 워크플로에 대한 입력 인수 중 하나를 나타내며 <xref:System.Activities.ActivityBuilder.Implementation%2A>에는 워크플로의 논리를 구성하는 활동이 포함되어 있습니다.이 예제의 r\-value 식은 Visual Basic 식입니다.람다 식은 <xref:System.Activities.Expressions.ExpressionServices.Convert%2A>를 사용하지 않으면 XAML로 serialize할 수 없습니다.serialize된 워크플로를 Workflow Designer에서 열거나 편집하려고 할 경우 Visual Basic 식을 사용해야 합니다.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)] [명령 코드를 사용하여 워크플로, 활동 및 식 작성](../../../docs/framework/windows-workflow-foundation//authoring-workflows-activities-and-expressions-using-imperative-code.md).  
  
 <xref:System.Activities.ActivityBuilder> 인스턴스가 나타내는 워크플로 정의를 XAML로 serialize하려면 <xref:System.Activities.XamlIntegration.ActivityXamlServices>를 사용하여 <xref:System.Xaml.XamlWriter>를 만든 다음, <xref:System.Xaml.XamlServices>를 사용하여 <xref:System.Xaml.XamlWriter>를 통해 워크플로 정의를 serialize합니다.<xref:System.Activities.XamlIntegration.ActivityXamlServices>에는 <xref:System.Activities.ActivityBuilder> 인스턴스와 XAML 간을 매핑하고, XAML 워크플로를 로드하고, 호출 가능한 <xref:System.Activities.DynamicActivity>를 반환하는 메서드가 있습니다.다음 예제에서는 이전 예제의 <xref:System.Activities.ActivityBuilder> 인스턴스를 문자열로 serialize하고 파일로 저장합니다.  
  
```csharp  
// Serialize the workflow to XAML and store it in a string.  
StringBuilder sb = new StringBuilder();  
StringWriter tw = new StringWriter(sb);  
XamlWriter xw = ActivityXamlServices.CreateBuilderWriter(new XamlXmlWriter(tw, new XamlSchemaContext()));  
XamlServices.Save(xw , ab);  
string serializedAB = sb.ToString();  
  
// Display the XAML to the console.  
Console.WriteLine(serializedAB);  
  
// Serialize the workflow to XAML and save it to a file.  
StreamWriter sw = File.CreateText(@"C:\Workflows\add.xaml");  
XamlWriter xw2 = ActivityXamlServices.CreateBuilderWriter(new XamlXmlWriter(sw, new XamlSchemaContext()));  
XamlServices.Save(xw2, ab);  
sw.Close();  
  
```  
  
 다음 예제에서는 serialize된 워크플로를 나타냅니다.  
  
```xaml  
<Activity   
  x:TypeArguments="x:Int32"   
  x:Class="Add"   
  xmlns="http://schemas.microsoft.com/netfx/2009/xaml/activities"   
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">  
  <x:Members>  
    <x:Property Name="Operand1" Type="InArgument(x:Int32)" />  
    <x:Property Name="Operand2" Type="InArgument(x:Int32)" />  
  </x:Members>  
  <Sequence>  
    <WriteLine Text="[Operand1.ToString() + " + " + Operand2.ToString()]" />  
    <Assign x:TypeArguments="x:Int32" Value="[Operand1 + Operand2]">  
      <Assign.To>  
        <OutArgument x:TypeArguments="x:Int32">  
          <ArgumentReference x:TypeArguments="x:Int32" ArgumentName="Result" />  
          </OutArgument>  
      </Assign.To>  
    </Assign>  
  </Sequence>  
</Activity>  
```  
  
 <xref:System.Activities.XamlIntegration.ActivityXamlServices> <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A> 메서드를 사용하여 serialize된 워크플로를 로드합니다.이 메서드는 serialize된 워크플로 정의를 사용하고 워크플로 정의를 나타내는 <xref:System.Activities.DynamicActivity>를 반환합니다.유효성 검사 프로세스가 진행되는 동안 <xref:System.Activities.DynamicActivity>의 본문에서 <xref:System.Activities.Activity.CacheMetadata%2A>를 호출할 때까지는 XAML이 deserialize되지 않습니다.유효성 검사를 명시적으로 호출하지 않으면 워크플로가 호출될 때 유효성 검사가 수행됩니다.XAML 워크플로 정의가 잘못된 경우 <xref:System.Argument> 예외가 throw됩니다.<xref:System.Activities.Activity.CacheMetadata%2A>에서 throw된 예외는 모두 <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>에 대한 호출에서 이스케이프되며 호출자가 처리해야 합니다.다음 예제에서는 이전 예제에서 serialize된 워크플로를 로드하고 <xref:System.Activities.WorkflowInvoker>를 사용하여 호출합니다.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#43](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#43)]  
  
 이 워크플로를 호출하면 다음 출력이 콘솔에 표시됩니다.  
  
 **25 \+ 15**   
**40**    
> [!NOTE]
>  입력 및 출력 인수를 사용한 워크플로 호출[!INCLUDE[crabout](../../../includes/crabout-md.md)][WorkflowInvoker 및 WorkflowApplication 사용](../../../docs/framework/windows-workflow-foundation//using-workflowinvoker-and-workflowapplication.md) 및 <xref:System.Activities.WorkflowInvoker.Invoke%2A>를 참조하십시오.  
  
 serialize된 워크플로에 C\# 식이 있을 경우 <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> 속성이 `true`로 설정된 <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings> 인스턴스가 <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A?displayProperty=fullName>에 매개 변수로 전달되어야 합니다. 그렇지 않으면 `Expression Activity type 'CSharpValue`1' requires compilation in order to run.  Please ensure that the workflow has been compiled.`와 유사한 메시지와 함께 <xref:System.NotSupportedException>이 throw됩니다.  
  
```csharp  
ActivityXamlServicesSettings settings = new ActivityXamlServicesSettings  
{  
    CompileExpressions = true  
};  
  
DynamicActivity<int> wf = ActivityXamlServices.Load(new StringReader(serializedAB), settings) as DynamicActivity<int>;  
  
```  
  
 [!INCLUDE[crdefault](../../../includes/crdefault-md.md)] [C\# 식](../../../docs/framework/windows-workflow-foundation//csharp-expressions.md).  
  
 <xref:System.Activities.XamlIntegration.ActivityXamlServices> <xref:System.Activities.XamlIntegration.ActivityXamlServices.CreateBuilderReader%2A> 메서드를 사용하여 serialize된 워크플로 정의를 <xref:System.Activities.ActivityBuilder> 인스턴스로 로드할 수도 있습니다.serialize된 워크플로를 <xref:System.Activities.ActivityBuilder> 인스턴스로 로드한 후 검사하고 수정할 수 있습니다.이 방법은 사용자 지정 Workflow Designer 작성자에게 유용하며, 디자인 프로세스가 진행되는 동안 워크플로 정의를 저장하고 다시 로드하기 위한 메커니즘을 제공합니다.다음 예제에서는 이전 예제에서 serialize된 워크플로 정의를 로드하고 해당 속성을 검사합니다.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#44](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#44)]