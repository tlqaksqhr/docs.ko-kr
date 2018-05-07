---
title: DynamicActivity 만들기
ms.date: 03/30/2017
ms.assetid: d8ebe82f-98c8-4452-aed7-2c60a512b097
ms.openlocfilehash: 93435be69f90ca0b74dae6b934cb145fabb7afff
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="dynamicactivity-creation"></a>DynamicActivity 만들기
이 샘플에서는 <xref:System.Activities.DynamicActivity> 활동을 사용하여 런타임에 활동을 만드는 두 가지 방법을 보여 줍니다.  
  
 이 샘플에서는 <xref:System.Activities.Statements.Sequence> 및 <xref:System.Activities.Statements.ForEach%601> 활동이 포함된 <xref:System.Activities.Statements.Assign%601> 활동이 들어 있는 본문을 사용하여 런타임에 활동을 만듭니다. 여기에서는 정수의 입력 목록이 활동에 전달되고 속성으로 설정됩니다. 그런 다음 <xref:System.Activities.Statements.ForEach%601> 활동에서 값의 목록을 반복하며 누적 계산합니다. <xref:System.Activities.Statements.Assign%601> 활동에서는 목록의 요소 수로 누적기를 나눠 평균 값을 계산하고 그 결과를 평균에 할당합니다.  
  
 이 샘플에서는 변수를 입력 인수로 이동하고 값을 출력 인수로 반환하는 <xref:System.Activities.DynamicActivity> 활동의 사용 방법을 보여 줍니다. 이 활동에는 정수 목록인 `Numbers`라는 입력 인수 한 개가 있습니다. <xref:System.Activities.Statements.ForEach%601> 활동에서 값의 목록을 반복하며 누적 계산합니다. <xref:System.Activities.Statements.Assign%601> 활동에서는 목록의 요소 수로 누적기를 나눠 평균 값을 계산하고 그 결과를 평균에 할당합니다. 평균은 `Average`라는 출력 인수로 반환됩니다.  
  
 프로그래밍 방식으로 동적 활동을 만드는 경우 입력과 출력이 다음 코드 예제에서와 같이 선언됩니다.  
  
```csharp  
DynamicActivity act = new DynamicActivity()  
{  
    DisplayName = "Find average",  
    Properties =   
    {  
        // Input argument  
        new DynamicActivityProperty  
        {  
            Name = "Numbers",  
            Type = typeof(InArgument<List<int>>),  
            Value = numbers  
        },  
        // Output argument  
        new DynamicActivityProperty  
        {  
            Name = "Average",  
            Type = typeof(OutArgument<double>),  
            Value = average  
        }  
    },  
};  
```  
  
 다음 코드 예제에서는 목록의 값에 대한 평균을 계산하는 `DynamicActivity`의 완벽한 정의를 보여 줍니다.  
  
```  
DynamicActivity act = new DynamicActivity()  
{  
    DisplayName = "Find average",  
    Properties =   
    {  
        // Input argument  
        new DynamicActivityProperty  
        {  
            Name = "Numbers",  
            Type = typeof(InArgument<List<int>>),  
            Value = numbers  
        },  
        // Output argument  
        new DynamicActivityProperty  
        {  
            Name = "Average",  
            Type = typeof(OutArgument<double>),  
            Value = average  
        }  
    },  
    Implementation = () =>  
        new Sequence  
        {  
            Variables = { result, accumulator },  
            Activities =  
            {  
                new ForEach<int>  
                {  
                    Values =  new ArgumentValue<IEnumerable<int>> { ArgumentName = "Numbers" },                                  
                    Body = new ActivityAction<int>  
                    {  
                        Argument = iterationVariable,  
                        Handler = new Assign<int>  
                        {  
                            To = accumulator,  
                            Value = new InArgument<int>(env => iterationVariable.Get(env) +  accumulator.Get(env))  
                        }  
                    }  
                },  
  
                // Calculate the average and assign to the output argument.  
                new Assign<double>  
                {  
                    To = new ArgumentReference<double> { ArgumentName = "Average" },  
                    Value = new InArgument<double>(env => accumulator.Get(env) / numbers.Get(env).Count<int>())  
                },  
            }  
        }  
};  
```  
  
 XAML에서 이를 만드는 경우 입력과 출력이 다음 예제에서와 같이 선언됩니다.  
  
```xml  
<Activity x:Class="Microsoft.Samples.DynamicActivityCreation.FindAverage"  
          xmlns="http://schemas.microsoft.com/netfx/2009/xaml/activities"  
          xmlns:scg="clr-namespace:System.Collections.Generic;assembly=mscorlib"  
          xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">  
  <x:Members>  
    <x:Property Name="Numbers" Type="InArgument(scg:List(x:Int32))" />  
    <x:Property Name="Average" Type="OutArgument(x:Double)" />  
  </x:Members>  
    ...  
    ...  
</Activity>  
```  
  
 [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)]에서 XAML을 시각적으로 만들 수 있습니다. Visual Studio 프로젝트에 포함 되어 있는 경우에 "빌드 작업"을 "None" 컴파일할 하지 않도록 설정 해야 합니다. 그런 다음 아래와 같은 호출을 사용하여 동적으로 XAML을 로드할 수 있습니다.  
  
```  
Activity act2 = ActivityXamlServices.Load(@"FindAverage.xaml");  
```  
  
 프로그래밍 방식으로 만들거나 XAML 워크플로를 로드하여 만든 <xref:System.Activities.DynamicActivity> 인스턴스를 다음 코드 예제에서와 같이 사용할 수 있습니다. 에 전달 된 "작동"는 점에 유의 하십시오는 `WorkflowInvoker.Invoke` 된 "act" <xref:System.Activities.Activity> 첫 번째 코드 예제에 정의 합니다.  
  
```  
IDictionary<string, object> results = WorkflowInvoker.Invoke(act, new Dictionary<string, object> { { "Numbers", numbers } });  
  
Console.WriteLine("The average calculated using the code activity is = " + results["Average"]);  
```  
  
#### <a name="to-use-this-sample"></a>이 샘플을 사용하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 DynamicActivityCreation.sln 솔루션 파일을 엽니다.  
  
2.  Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.  
  
3.  Ctrl+F5를 눌러 솔루션을 실행합니다.  
  
## <a name="command-line-arguments"></a>명령줄 인수  
 이 샘플에는 명령줄 인수를 사용할 수 있습니다. 활동에서 평균을 계산하는 데 필요한 숫자 목록을 사용자가 입력할 수 있습니다. 사용할 숫자의 목록을 입력할 때는 목록의 각 숫자를 공백으로 구분해야 합니다. 예를 들어 5, 10, 32의 평균을 계산하려면 다음과 같은 명령줄을 사용하여 샘플을 호출합니다.  
  
 **DynamicActivityCreation 5 10 32**  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\DynamicActivity\DynamicActivityCreation`