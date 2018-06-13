---
title: 값 범위에서 전환할 사용자 지정 활동
ms.date: 03/30/2017
ms.assetid: 441e0a17-421f-430c-ba97-59e4cc6c88e3
ms.openlocfilehash: 785db08ffaf4ca6fe27d6418878c0bbf4ada44fd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33517071"
---
# <a name="custom-activity-to-switch-on-a-range-of-values"></a>값 범위에서 전환할 사용자 지정 활동
이 샘플에서는 <xref:System.Activities.Statements.Switch%601>의 사용을 확장하는 사용자 지정 활동을 만드는 방법을 보여 줍니다. 일반적인 <xref:System.Activities.Statements.Switch%601> 문을 사용하면 단일 값에 따라 전환할 수 있습니다. 그러나 값 범위에 따라 활동을 전환해야 하는 비즈니스 시나리오도 있습니다. 예를 들어 활동이 전환되는 기준 값이 1과 5 사이인 경우 하나의 동작을 실행하고 값이 6에서 10 사이인 경우 다른 동작을 실행하고 다른 모든 값의 경우 기본 동작을 실행할 수 있습니다. 이 사용자 지정 활동을 사용하면 해당 시나리오를 정확하게 수행할 수 있습니다.  
  
## <a name="the-switchrange-activity"></a>SwitchRange 활동  
 `SwitchRange` 활동은 식의 결과 값이 `Cases` 중 하나의 범위 내에 포함되는 경우 자식 활동을 예약합니다.  
  
 다음 코드 예제는 값 범위에 따라 전환되는 사용자 지정 활동입니다.  
  
```csharp  
public sealed class SwitchRange<T> : NativeActivity where T : IComparable  
{  
   [RequiredArgument]  
   [DefaultValue(null)]  
   public InArgument<T> Expression { get; set; }  
  
   public IList<CaseRange<T>> Cases  
  
   [DefaultValue(null)]  
   public Activity Default { get; set; }}  
}  
```  
  
|속성|설명|  
|-|-|  
|식|Cases 목록의 범위를 기준으로 계산 및 비교될 식입니다. 식의 결과 형식은 T 형식입니다.|  
|Cases|각 케이스는 범위(시작과 끝)와 활동(본문)으로 구성됩니다. 식은 범위를 기준으로 계산 및 비교됩니다. 식의 결과가 케이스 중 하나의 범위 내에 있는 경우 해당 활동이 실행됩니다.|  
|기본|일치하는 케이스가 없는 경우 실행되는 활동입니다. `null`로 설정되어 있으면 아무 동작도 수행되지 않습니다.|  
  
## <a name="caserange-class"></a>CaseRange 클래스  
 `CaseRange` 클래스는 `SwitchRange` 활동 내의 범위를 나타냅니다. `CaseRange`의 모든 인스턴스에는 범위(`From` 과 `To`로 구성)와 `Body`의 식이 범위 내에서 계산되는 경우 예약되는 `SwitchRange` 활동이 포함됩니다.  
  
 다음 코드 예제는 `CaseRange` 클래스에 대한 정의입니다.  
  
```  
public class CaseRange<T> where T : IComparable  
{  
    public T From { get; set; }  
  
    public T To { get; set; }  
  
    public Activity Action { get; set; }  
}  
```  
  
> [!NOTE]
>  샘플에 정의된 `SwitchRange` 및 `CaseRange` 클래스는 `IComparable`을 구현하는 모든 형식을 사용할 수 있는 제네릭 클래스입니다(예: <xref:System.Activities.Statements.Switch%601> 클래스).  
  
## <a name="sample-usage"></a>샘플 사용  
 다음 코드 예제에서는 `SwitchRange` 활동을 사용하는 방법을 보여 줍니다.  
  
```csharp  
Activity SwitchRange = new SwitchRange<int>  
{  
    Expression = new InArgument<int>(value),  
    Cases =   
    {  
        new CaseRange<int>                      
        {  
            From = 1,  
            To = 5,  
            Action = new WriteLine  
            {  
                Text = "Case 1-5 selected",  
            }  
        },  
        new CaseRange<int>  
        {  
            From = 6,  
            To = 10,  
            Action = new WriteLine  
            {  
                Text = "Case 6-10 selected",  
            }  
        }  
    },  
    Default = new WriteLine { Text = "Default Case selected" }  
};  
```  
  
#### <a name="to-use-this-sample"></a>이 샘플을 사용하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]을 사용하여 SwitchRange.sln 솔루션 파일을 엽니다.  
  
2.  Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.  
  
3.  Ctrl+F5를 눌러 솔루션을 실행합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\SwitchRange`