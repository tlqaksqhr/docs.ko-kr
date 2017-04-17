---
title: "명령 코드를 사용하여 워크플로, 활동 및 식 작성 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: cefc9cfc-2882-4eb9-8c94-7a6da957f2b2
caps.latest.revision: 16
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 16
---
# 명령 코드를 사용하여 워크플로, 활동 및 식 작성
워크플로 정의는 구성된 활동 개체의 트리입니다.XAML을 수동으로 편집하거나 Workflow Designer를 사용하여 XAML을 생성하는 등 여러 가지 방법으로 이 활동 트리를 정의할 수 있습니다.하지만 XAML 사용은 필수 사항이 아닙니다.프로그래밍 방식으로 워크플로 정의를 만들 수도 있습니다.이 항목에서는 코드를 사용하여 워크플로 정의, 활동 및 식을 만드는 방법을 간략히 설명합니다.코드를 사용한 XAML 워크플로 작업의 예제를 보려면 [워크플로 및 활동과 XAML 간 serialize](../../../docs/framework/windows-workflow-foundation//serializing-workflows-and-activities-to-and-from-xaml.md)를 참조하십시오.  
  
## 워크플로 정의 만들기  
 활동 형식의 인스턴스를 인스턴스화하고 활동 개체의 속성을 구성하여 워크플로 정의를 만들 수 있습니다.자식 활동을 포함하지 않는 활동의 경우 코드 몇 행으로 이 작업을 완료할 수 있습니다.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#47](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#47)]  
  
> [!NOTE]
>  이 항목의 예제에서는 <xref:System.Activities.WorkflowInvoker>를 사용하여 샘플 워크플로를 실행합니다.워크플로 호출, 인수 전달 및 사용 가능한 다양한 호스팅 옵션[!INCLUDE[crabout](../../../includes/crabout-md.md)][WorkflowInvoker 및 WorkflowApplication 사용](../../../docs/framework/windows-workflow-foundation//using-workflowinvoker-and-workflowapplication.md)을 참조하십시오.  
  
 이 예제에서는 <xref:System.Activities.Statements.WriteLine> 활동 하나로 구성된 워크플로를 만듭니다.<xref:System.Activities.Statements.WriteLine> 활동의 <xref:System.Activities.Statements.WriteLine.Text%2A> 인수를 설정하고 워크플로를 호출합니다.활동이 자식 활동을 포함하는 경우 생성 메서드는 유사합니다.다음 예에서는 <xref:System.Activities.Statements.WriteLine> 활동 두 개를 포함하는 <xref:System.Activities.Statements.Sequence> 활동을 사용합니다.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#48](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#48)]  
  
### 개체 이니셜라이저 사용  
 이 항목의 예에서는 개체 초기화 구문을 사용합니다.개체 초기화 구문은 워크플로에 있는 활동의 계층적 뷰를 제공하고 활동 간의 관계를 표시하기 때문에 코드에서 워크플로 정의를 만드는 유용한 방법일 수 있습니다.프로그래밍 방식으로 워크플로를 만들 때 개체 초기화 구문을 사용하기 위한 요구 사항은 없습니다.다음 예는 이전 예와 기능적으로 동일합니다.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#49](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#49)]  
  
 개체 이니셜라이저[!INCLUDE[crabout](../../../includes/crabout-md.md)][방법: 생성자를 호출하지 않고 개체 초기화\(C\# 프로그래밍 가이드\)](http://go.microsoft.com/fwlink/?LinkId=161015) 및 [방법: 개체 이니셜라이저를 사용하여 개체 선언](http://go.microsoft.com/fwlink/?LinkId=161016)을 참조하십시오.  
  
### 변수, 리터럴 값 및 식 작업  
 코드를 사용하여 워크플로 정의를 만들 때는 워크플로 정의 만들기 중 실행되는 코드와 해당 워크플로의 인스턴스 실행 중 실행되는 코드를 알아야 합니다.예를 들어, 다음은 난수를 생성하여 콘솔에 쓰기 위한 워크플로입니다.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#50](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#50)]  
  
 이 워크플로 정의 코드를 실행하면 `Random.Next`가 호출되고 결과가 워크플로 정의에 리터럴 값으로 저장됩니다.이 워크플로의 많은 인스턴스를 호출할 수 있으며 모두 동일한 수를 표시합니다.워크플로 실행 중 난수가 생성되도록 하려면 워크플로를 실행할 때마다 계산되는 식을 사용해야 합니다.다음 예제에서는 Visual Basic 식과 함께 <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601>가 사용됩니다.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#51](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#51)]  
  
 이전 예제의 식을 <xref:Microsoft.CSharp.Activities.CSharpValue%601> 및 C\# 식을 사용하여 구현할 수도 있습니다.  
  
```csharp  
new Assign<int>  
{  
    To = n,  
    Value = new CSharpValue<int>("new Random().Next(1, 101)")  
}  
  
```  
  
 C\# 식은 해당 식을 포함하는 워크플로를 호출하기 전에 컴파일해야 합니다.C\# 식을 컴파일하지 않으면 워크플로를 호출할 때 `Expression Activity type 'CSharpValue`1' requires compilation in order to run.  Please ensure that the workflow has been compiled.`라는 메시지와 함께 <xref:System.NotSupportedException>이 throw됩니다. Visual Studio에서 만들어진 워크플로를 사용하는 대부분의 시나리오에서 C\# 식은 자동으로 컴파일되지만 코드 워크플로와 같은 일부 시나리오에서는 C\# 식을 수동으로 컴파일해야 합니다.C\# 식을 컴파일하는 방법에 대한 예제는 [C\# 식](../../../docs/framework/windows-workflow-foundation//csharp-expressions.md) 항목의 [코드 워크플로에서 C\# 식 사용](../../../docs/framework/windows-workflow-foundation//csharp-expressions.md#CodeWorkflows) 단원을 참조하십시오.  
  
 <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601>는 식에서 r\-value로 사용할 수 있는 Visual Basic 구문의 식을 나타내며, <xref:Microsoft.CSharp.Activities.CSharpValue%601>는 식에서 r\-value로 사용할 수 있는 C\# 구문의 식을 나타냅니다.이러한 식은 포함 활동이 실행될 때마다 계산됩니다.  
  
> [!NOTE]
>  이러한 코드는 둘 다 C\#을 프로그래밍 언어로 사용하지만 하나는 <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601>를 사용하고 다른 하나는 <xref:Microsoft.CSharp.Activities.CSharpValue%601>를 사용합니다.<xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601> 및 <xref:Microsoft.CSharp.Activities.CSharpValue%601>는 Visual Basic 및 C\# 프로젝트 모두에서 사용할 수 있습니다.기본적으로 Workflow Designer에서 만든 식은 호스팅 프로젝트의 언어와 일치합니다.코드에서 워크플로를 작성할 때는 워크플로 작성자가 원하는 언어를 선택합니다.  
  
 이러한 예제에서 식의 결과는 워크플로 변수 `n`에 할당되고 이 결과는 워크플로의 다음 활동에서 사용됩니다.런타임에 워크플로 변수 `n`에 액세스하려면 <xref:System.Activities.ActivityContext>가 필요합니다.다음 람다 식을 사용하여 이 변수에 액세스할 수 있습니다.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#52](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#52)]  
  
 람다 식[!INCLUDE[crabout](../../../includes/crabout-md.md)][람다 식\(C\# 프로그래밍 가이드\)](http://go.microsoft.com/fwlink/?LinkID=152436) 또는 [람다 식\(Visual Basic\)](http://go.microsoft.com/fwlink/?LinkID=152437)을 참조하십시오.  
  
 람다 식은 XAML 형식으로 serialize할 수 없습니다.람다 식을 사용하여 워크플로를 serialize하려고 시도하면 <xref:System.Activities.Expressions.LambdaSerializationException>이 throw되고 "이 워크플로에는 코드에 지정된 람다 식이 포함됩니다.이러한 식은 직렬화할 수 있는 XAML 식이 아닙니다.워크플로를 직렬화할 수 있는 XAML로 만들려면 VisualBasicValue\/VisualBasicReference 또는 ExpressionServices.Convert\(lambda\)를 사용하십시오.그러면 람다 식이 식 작업으로 변환됩니다."라는 메시지가 표시됩니다. 이 식을 XAML과 호환 가능하게 만들려면 다음 예와 같이 <xref:System.Activities.Expressions.ExpressionServices>와 <xref:System.Activities.Expressions.ExpressionServices.Convert%2A>을 사용합니다.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#53](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#53)]  
  
 <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601>을 사용할 수도 있습니다.Visual Basic 식을 사용할 때는 람다 식이 필요하지 않습니다.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#54](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#54)]  
  
 런타임에 Visual Basic 식은 LINQ 식으로 컴파일됩니다.이전의 두 예제는 XAML로 serialize할 수 있지만 serialize한 XAML을 Workflow Designer에서 보고 편집하려는 경우에는 식에 <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601>를 사용하십시오.`ExpressionServices.Convert`를 사용하는 serialize된 워크플로는 디자이너에서 열 수 있지만 식의 값은 비게 됩니다.워크플로를 XAML로 serialize하는 방법[!INCLUDE[crabout](../../../includes/crabout-md.md)][워크플로 및 활동과 XAML 간 serialize](../../../docs/framework/windows-workflow-foundation//serializing-workflows-and-activities-to-and-from-xaml.md)를 참조하십시오.  
  
#### 리터럴 식 및 참조 형식  
 리터럴 식은 워크플로에서 <xref:System.Activities.Expressions.Literal%601> 활동으로 표시됩니다.다음 <xref:System.Activities.Statements.WriteLine> 활동은 기능이 동일합니다.  
  
```csharp  
new WriteLine  
{  
    Text = "Hello World."  
},  
new WriteLine  
{  
    Text = new Literal<string>("Hello World.")  
}  
  
```  
  
 리터럴 식은 <xref:System.String>을 제외한 참조 형식으로 초기화할 수 없습니다.다음 예제에서 <xref:System.Activities.Statements.Assign> 활동의 <xref:System.Activities.Statements.Assign.Value%2A> 속성은 `List<string>`을 사용한 리터럴 식으로 초기화됩니다.  
  
```csharp  
new Assign  
{  
    To = new OutArgument<List<string>>(items),  
    Value = new InArgument<List<string>>(new List<string>())  
},  
  
```  
  
 이 활동이 포함된 워크플로의 유효성을 검사하면 "리터럴은 값 형식과 불변 형식 System.String만 지원합니다.System.Collections.Generic.List\`1\[System.String\] 형식은 리터럴로 사용할 수 없습니다."라는 유효성 검사 오류가 반환됩니다. 워크플로가 호출되면 유효성 검사 오류 텍스트가 포함된 <xref:System.Activities.InvalidWorkflowException>이 throw됩니다.참조 형식을 사용하여 리터럴 식을 만들 경우 워크플로의 각 인스턴스에 대해 참조 형식의 새 인스턴스가 만들어지지 않으므로 이 오류는 유효성 검사 오류입니다.이 문제를 해결하려면 리터럴 식을 참조 형식의 새 인스턴스를 만들어 반환하는 식으로 바꾸십시오.  
  
```csharp  
new Assign  
{  
    To = new OutArgument<List<string>>(items),  
    Value = new InArgument<List<string>>(new VisualBasicValue<List<string>>("New List(Of String)"))  
},  
  
```  
  
 식[!INCLUDE[crabout](../../../includes/crabout-md.md)][식](../../../docs/framework/windows-workflow-foundation//expressions.md)를 참조하십시오.  
  
#### 식 및 InvokeMethod 활동을 사용하여 개체에 대한 메서드 호출  
 <xref:System.Activities.Expressions.InvokeMethod%601> 활동은 .NET Framework에서 클래스의 정적 및 인스턴스 메서드를 호출하는 데 사용할 수 있습니다.이 항목의 이전 예제에서는 <xref:System.Random> 클래스를 사용하여 난수를 생성했습니다.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#51](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#51)]  
  
 <xref:System.Activities.Expressions.InvokeMethod%601> 활동을 사용하여 <xref:System.Random> 클래스의 <xref:System.Random.Next%2A> 메서드를 이미 호출했을 수도 있습니다.  
  
```csharp  
new InvokeMethod<int>  
{  
    TargetObject = new InArgument<Random>(new VisualBasicValue<Random>("New Random()")),  
    MethodName = "Next",  
    Parameters =   
    {  
        new InArgument<int>(1),  
        new InArgument<int>(101)  
    },  
    Result = n  
}  
  
```  
  
 <xref:System.Random.Next%2A>는 정적 메서드가 아니기 때문에 <xref:System.Activities.Expressions.InvokeMethod%601.TargetObject%2A> 속성에 대해 <xref:System.Random> 클래스의 인스턴스가 제공됩니다.이 예제에서는 Visual Basic 식을 사용하여 새 인스턴스를 만들지만 새 인스턴스가 이미 만들어져 워크플로 변수에 저장되었을 수도 있습니다.이 예제에서는 <xref:System.Activities.Expressions.InvokeMethod%601> 활동 대신 <xref:System.Activities.Statements.Assign%601> 활동을 사용하는 것이 더욱 간단합니다.<xref:System.Activities.Statements.Assign%601> 또는 <xref:System.Activities.Expressions.InvokeMethod%601> 활동에 의해 최종적으로 호출된 메서드 호출이 오래 실행되는 경우 <xref:System.Activities.Expressions.InvokeMethod%601>는 <xref:System.Activities.Expressions.InvokeMethod%601.RunAsynchronously%2A> 속성이 있기 때문에 보다 편리합니다.이 속성이 `true`로 설정된 경우 호출된 메서드는 워크플로에 대해 비동기적으로 실행됩니다.다른 활동이 병렬로 실행되더라도 메서드가 비동기적으로 실행되는 동안에는 이러한 활동이 차단되지 않습니다.또한 호출되는 메서드에 반환 값이 없는 경우에는 <xref:System.Activities.Expressions.InvokeMethod%601>를 사용하여 메서드를 호출하는 것이 적절한 방법입니다.  
  
## 인수 및 동적 활동  
 워크플로 정의는 코드에서 활동을 활동 트리로 어셈블하고 속성과 인수를 구성하여 만들어집니다.기존 인수를 바인딩할 수 있지만, 새 인수를 활동에 추가할 수는 없습니다.여기에는 루트 활동에 전달된 워크플로 인수가 포함됩니다.명령적 코드에서는 워크플로 인수가 새 CLR 형식에 대한 속성으로 지정되고 XAML에서는 `x:Class` 및 `x:Member`를 사용하여 선언됩니다.메모리 내 개체 트리로 워크플로 정의를 만들 때 새 CLR 형식이 만들어지지 않았기 때문에 인수를 추가할 수 없습니다.하지만 <xref:System.Activities.DynamicActivity>에 인수를 추가할 수 있습니다.이 예제에서는 정수 인수 두 개를 취하여 이를 더한 다음 그 결과를 반환하는 <xref:System.Activities.DynamicActivity%601>을 만듭니다.각 인수에 대해 <xref:System.Activities.DynamicActivityProperty>를 만들고, 작업 결과를 <xref:System.Activities.DynamicActivity%601>의 <xref:System.Activities.Activity%601.Result%2A> 인수에 할당합니다.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#55](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#55)]  
  
 동적 활동[!INCLUDE[crabout](../../../includes/crabout-md.md)][런타임에 활동 만들기](../../../docs/framework/windows-workflow-foundation//creating-an-activity-at-runtime-with-dynamicactivity.md)를 참조하십시오.  
  
## 컴파일된 활동  
 동적 활동은 코드를 사용하여 인수가 포함된 활동을 정의하는 한 방법이지만 활동을 코드에서 만들어 형식으로 컴파일할 수도 있습니다.<xref:System.Activities.CodeActivity>에서 파생되는 간단한 활동과 <xref:System.Activities.AsyncCodeActivity>에서 파생되는 비동기 활동을 만들 수 있습니다.이러한 활동은 인수를 사용하고, 값을 반환하며, 명령적 코드를 사용하여 논리를 정의합니다.이러한 유형의 활동을 만드는 예제는 [CodeActivity 기본 클래스](../../../docs/framework/windows-workflow-foundation//workflow-activity-authoring-using-the-codeactivity-class.md) 및 [비동기 활동 만들기](../../../docs/framework/windows-workflow-foundation//creating-asynchronous-activities-in-wf.md)를 참조하십시오.  
  
 <xref:System.Activities.NativeActivity>에서 파생되는 활동은 명령적 코드를 사용하여 논리를 정의할 수 있으며 논리를 정의하는 자식 활동을 포함할 수도 있습니다.또한 책갈피 만들기 같은 런타임 기능에도 완벽하게 액세스할 수 있습니다.<xref:System.Activities.NativeActivity> 기반 활동을 만드는 예제는 [NativeActivity 기본 클래스](../../../docs/framework/windows-workflow-foundation//nativeactivity-base-class.md), [방법: 활동 만들기](../../../docs/framework/windows-workflow-foundation//how-to-create-an-activity.md) 및 [기본 활동을 사용하는 사용자 지정 복합](../../../docs/framework/windows-workflow-foundation/samples/custom-composite-using-native-activity.md) 샘플을 참조하십시오.  
  
 <xref:System.Activities.Activity>에서 파생되는 활동은 자식 활동을 통해서만 논리를 정의합니다.이러한 활동은 일반적으로 Workflow Designer를 사용하여 만들지만 코드를 사용하여 정의할 수도 있습니다.다음 예제에서는 `Activity<int>`에서 파생되는 `Square` 활동을 정의합니다.`Square` 활동은 `Value`라는 단일 <xref:System.Activities.InArgument%601>를 사용하며, <xref:System.Activities.Activity.Implementation%2A> 속성을 사용하여 <xref:System.Activities.Statements.Sequence> 활동을 지정함으로써 논리를 정의합니다.<xref:System.Activities.Statements.Sequence> 활동에는 <xref:System.Activities.Statements.WriteLine> 활동과 <xref:System.Activities.Statements.Assign%601> 활동이 포함됩니다.이러한 세 가지 활동이 함께 `Square` 활동의 논리를 구현합니다.  
  
```csharp  
class Square : Activity<int>  
{  
    [RequiredArgument]  
    public InArgument<int> Value { get; set; }  
  
    public Square()  
    {  
        this.Implementation = () => new Sequence  
        {  
            Activities =  
            {  
                new WriteLine  
                {  
                    Text = new InArgument<string>((env) => "Squaring the value: " + this.Value.Get(env))  
                },  
                new Assign<int>  
                {  
                    To = new OutArgument<int>((env) => this.Result.Get(env)),  
                    Value = new InArgument<int>((env) => this.Value.Get(env) * this.Value.Get(env))  
                }  
            }  
        };  
    }  
}  
  
```  
  
 다음 예제에서는 단일 `Square` 활동으로 구성된 워크플로 정의를 <xref:System.Activities.WorkflowInvoker>를 사용하여 호출합니다.  
  
```csharp  
Dictionary<string, object> inputs = new Dictionary<string, object> {{ "Value", 5}};  
int result = WorkflowInvoker.Invoke(new Square(), inputs);  
Console.WriteLine("Result: {0}", result);  
  
```  
  
 워크플로가 호출되면 다음 출력이 콘솔에 표시됩니다.  
  
 **Squaring the value: 5**   
**Result: 25**