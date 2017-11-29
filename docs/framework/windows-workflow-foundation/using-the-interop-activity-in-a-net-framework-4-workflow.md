---
title: ".NET Framework 4 워크플로에서 Interop 활동 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9bb747f0-eb33-4f70-84cd-317382372dcd
caps.latest.revision: "20"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c485a1c2c69169812e69c3bc1ea9969d12467d53
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="using-the-interop-activity-in-a-net-framework-4-workflow"></a>.NET Framework 4 워크플로에서 Interop 활동 사용
[!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] 또는 [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)]를 사용하여 만든 활동은 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] 활동을 통해 <xref:System.Activities.Statements.Interop> 워크플로에서 사용할 수 있습니다. 이 항목에서는 <xref:System.Activities.Statements.Interop> 활동 사용에 대해 간략하게 설명합니다.  
  
> [!NOTE]
>  <xref:System.Activities.Statements.Interop> 워크플로 프로젝트에 없는 경우 활동은 워크플로 디자이너 도구 상자에 나타나지 않습니다 해당 **대상 프레임 워크** 으로 설정 **.NET Framework 4** 이상.  
  
## <a name="using-the-interop-activity-in-net-framework-45-workflows"></a>.NET Framework 4.5 워크플로에서 Interop 활동 사용  
 이 항목에서는 [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] 활동을 포함하는 `DiscountCalculator` 활동 라이브러리를 만듭니다. `DiscountCalculator`는 구매량을 기준으로 할인을 계산하며 <xref:System.Workflow.Activities.SequenceActivity>를 포함하는 <xref:System.Workflow.Activities.PolicyActivity>로 구성됩니다.  
  
> [!NOTE]
>  이 항목에서 만드는 [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] 활동은 <xref:System.Workflow.Activities.PolicyActivity>를 사용하여 활동 논리를 구현합니다. [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] 워크플로에서 규칙을 사용하기 위해 사용자 지정 <xref:System.Activities.Statements.Interop> 활동이나 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] 활동을 사용할 필요는 없습니다. 규칙을 사용 하는 예제에 대 한 한 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] 워크플로 사용 하지 않고는 <xref:System.Activities.Statements.Interop> 활동 참조는 [.NET Framework 4.5에서 정책 작업](../../../docs/framework/windows-workflow-foundation/samples/policy-activity-in-net-framework-4-5.md) 샘플.  
  
#### <a name="to-create-the-net-framework-35-activity-library-project"></a>.NET Framework 3.5 활동 라이브러리 프로젝트를 만들려면  
  
1.  열기 [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] 선택 **새로** 차례로 **프로젝트...** **파일** 메뉴.  
  
2.  확장 된 **기타 프로젝트 형식** 에서 노드는 **설치 된 템플릿** 창과 선택 **Visual Studio 솔루션**합니다.  
  
3.  선택 **빈 솔루션** 에서 **Visual Studio 솔루션** 목록입니다. 형식 `PolicyInteropDemo` 에 **이름** 상자 한 클릭 **확인**합니다.  
  
4.  마우스 오른쪽 단추로 클릭 **PolicyInteropDemo** 에 **솔루션 탐색기** 선택 **추가** 차례로 **새 프로젝트...** .  
  
    > [!TIP]
    >  경우는 **솔루션 탐색기** 창이 표시, 선택 되지 않으면 **솔루션 탐색기** 에서 **보기** 메뉴.  
  
5.  에 **설치 된 템플릿** 목록에서 **Visual C#** 차례로 **워크플로**합니다. 선택 **.NET Framework 3.5** 선택 고.NET Framework 버전 드롭다운 목록에서 **워크플로 활동 라이브러리** 에서 **템플릿** 목록입니다.  
  
6.  형식 `PolicyActivityLibrary` 에 **이름** 상자 한 클릭 **확인**합니다.  
  
7.  마우스 오른쪽 단추로 클릭 **Activity1.cs** 에 **솔루션 탐색기** 선택 **삭제**합니다. **확인** 을 클릭하여 확인합니다.  
  
#### <a name="to-create-the-discountcalculator-activity"></a>DiscountCalculator 활동을 만들려면  
  
1.  마우스 오른쪽 단추로 클릭 **PolicyActivityLibrary** 에 **솔루션 탐색기** 선택 **추가** 차례로 **활동 중...** .  
  
2.  선택 **활동 (코드 분리)** 에서 **Visual C# 항목** 목록입니다. 형식 `DiscountCalculator` 에 **이름** 상자 한 클릭 **확인**합니다.  
  
3.  마우스 오른쪽 단추로 클릭 **DiscountCalculator.xoml** 에 **솔루션 탐색기** 선택 **코드 보기**합니다.  
  
4.  `DiscountCalculator` 클래스에 다음 세 가지 속성을 추가합니다.  
  
    ```csharp  
    public partial class DiscountCalculator : SequenceActivity  
    {  
        public double Subtotal { get; set; }  
        public double DiscountPercent { get; set; }  
        public double Total { get; set; }  
    }  
    ```  
  
5.  마우스 오른쪽 단추로 클릭 **DiscountCalculator.xoml** 에 **솔루션 탐색기** 선택 **뷰 디자이너**합니다.  
  
6.  끌어서는 **정책** 활동을는 **Windows Workflow v3.0** 섹션은 **도구 상자** 놓습니다는 **DiscountCalculator** 활동 .  
  
    > [!TIP]
    >  경우는 **도구 상자** 창이 표시, 선택 되지 않으면 **도구 상자** 에서 **보기** 메뉴.  
  
#### <a name="to-configure-the-rules"></a>규칙을 구성하려면  
  
1.  새로 추가 된 클릭 **정책** 활동을 아직 선택 하지 않은 경우 선택 합니다.  
  
2.  클릭는 **RuleSetReference** 속성에는 **속성** 창을 선택한 속성의 오른쪽에 줄임표 단추를 클릭 합니다.  
  
    > [!TIP]
    >  경우는 **속성** 창이 표시 되지 않으면, 선택 **속성 창** 에서 **보기** 메뉴.  
  
3.  선택 **새로 만들기...** .  
  
4.  클릭 **규칙 추가**합니다.  
  
5.  에 다음 식을 입력는 **조건** 상자입니다.  
  
    ```  
    this.Subtotal >= 50 && this.Subtotal < 100  
    ```  
  
6.  에 다음 식을 입력는 **Thenactions** 상자입니다.  
  
    ```  
    this.DiscountPercent = 0.075  
    ```  
  
7.  클릭 **규칙 추가**합니다.  
  
8.  에 다음 식을 입력는 **조건** 상자입니다.  
  
    ```  
    this.Subtotal >= 100  
    ```  
  
9. 에 다음 식을 입력는 **Thenactions** 상자입니다.  
  
    ```  
    this.DiscountPercent = 0.15  
    ```  
  
10. 클릭 **규칙 추가**합니다.  
  
11. 에 다음 식을 입력는 **조건** 상자입니다.  
  
    ```  
    this.DiscountPercent > 0  
    ```  
  
12. 에 다음 식을 입력는 **Thenactions** 상자입니다.  
  
    ```  
    this.Total = this.Subtotal - this.Subtotal * this.DiscountPercent  
    ```  
  
13. 에 다음 식을 입력는 **Else 작업** 상자입니다.  
  
    ```  
    this.Total = this.Subtotal  
    ```  
  
14. 클릭 **확인** 를 닫으려면는 **규칙 집합 편집기** 대화 상자.  
  
15. 새로 작성 되어 있는지 확인 <xref:System.Workflow.Activities.Rules.RuleSet> 에서 선택한는 **이름** 목록으로 이동한 클릭 **확인**합니다.  
  
16. Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.  
  
 다음 코드 예제에서는 이 절차에서 `DiscountCalculator` 활동에 추가한 규칙을 보여 줍니다.  
  
```  
Rule1: IF this.Subtotal >= 50 && this.Subtotal < 100   
       THEN this.DiscountPercent = 0.075   
  
Rule2: IF this. Subtotal >= 100   
       THEN this.DiscountPercent = 0.15   
  
Rule3: IF this.DiscountPercent > 0   
       THEN this.Total = this.Subtotal - this.Subtotal * this.DiscountPercent   
       ELSE this.Total = this.Subtotal  
```  
  
 <xref:System.Workflow.Activities.PolicyActivity>가 실행되면 이 세 가지 규칙은 `Subtotal` 활동의 `DiscountPercent`, `Total` 및 `DiscountCalculator` 속성 값을 평가하고 수정하여 원하는 할인을 계산합니다.  
  
## <a name="using-the-discountcalculator-activity-with-the-interop-activity"></a>Interop 활동과 함께 DiscountCalculator 활동 사용  
 `DiscountCalculator` 워크플로 내에서 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] 활동을 사용하려면 <xref:System.Activities.Statements.Interop> 활동을 사용합니다. 이 단원에서는 <xref:System.Activities.Statements.Interop> 활동과 함께 `DiscountCalculator` 활동을 사용하는 방법을 보여 주는 두 개의 워크플로를 코드 및 Workflow Designer를 사용하여 각각 만듭니다. 두 워크플로에 동일한 호스트 응용 프로그램을 사용합니다.  
  
#### <a name="to-create-the-host-application"></a>호스트 응용 프로그램을 만들려면  
  
1.  마우스 오른쪽 단추로 클릭 **PolicyInteropDemo** 에 **솔루션 탐색기** 선택 **추가**, 차례로 **새 프로젝트...** .  
  
2.  되도록 **.NET Framework 4.5** 을.NET Framework 버전 드롭다운 목록에서 선택 하 고 선택 **워크플로 콘솔 응용 프로그램** 에서 **Visual C# 항목** 목록입니다.  
  
3.  형식 `PolicyInteropHost` 에 **이름** 상자 한 클릭 **확인**합니다.  
  
4.  마우스 오른쪽 단추로 클릭 **PolicyInteropHost** 에 **솔루션 탐색기** 선택 **속성**합니다.  
  
5.  에 **대상 프레임 워크** 드롭 다운 목록에서에서 선택을 변경 **.NET Framework 4 Client Profile** 를 **.NET Framework 4.5**합니다. 클릭 **예** 를 확인 합니다.  
  
6.  마우스 오른쪽 단추로 클릭 **PolicyInteropHost** 에 **솔루션 탐색기** 선택 **참조 추가...** .  
  
7.  선택 **PolicyActivityLibrary** 에서 **프로젝트** 탭을 클릭 **확인**합니다.  
  
8.  마우스 오른쪽 단추로 클릭 **PolicyInteropHost** 에 **솔루션 탐색기** 선택 **참조 추가...** .  
  
9. 선택 **System.Workflow.Activities**, **System.Workflow.ComponentModel**, 차례로 **System.Workflow.Runtime** 에서 **.NET**탭을 클릭 **확인**합니다.  
  
10. 마우스 오른쪽 단추로 클릭 **PolicyInteropHost** 에 **솔루션 탐색기** 선택 **시작 프로젝트로 설정**합니다.  
  
11. Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.  
  
### <a name="using-the-interop-activity-in-code"></a>코드에서 Interop 활동 사용  
 이 예제에서는 코드를 사용하여 <xref:System.Activities.Statements.Interop> 활동과 `DiscountCalculator` 활동을 포함하는 워크플로 정의를 만듭니다. 이 워크플로는 <xref:System.Activities.WorkflowInvoker>를 사용하여 호출하고 <xref:System.Activities.Statements.WriteLine> 활동을 사용하여 규칙 평가 결과를 콘솔에 씁니다.  
  
##### <a name="to-use-the-interop-activity-in-code"></a>코드에서 Interop 활동을 사용하려면  
  
1.  마우스 오른쪽 단추로 클릭 **Program.cs** 에 **솔루션 탐색기** 선택 **코드 보기**합니다.  
  
2.  파일 맨 위에 다음 `using` 문을 추가합니다.  
  
    ```csharp  
    using PolicyActivityLibrary;  
    ```  
  
3.  `Main` 메서드의 내용을 제거하고 다음 코드로 대체합니다.  
  
    ```csharp  
    static void Main(string[] args)  
    {  
        CalculateDiscountUsingCodeWorkflow();  
    }  
    ```  
  
4.  `Program` 클래스에 다음 코드를 포함하는 `CalculateDiscountUsingCodeWorkflow`라는 새 메서드를 만듭니다.  
  
    ```csharp  
    static void CalculateDiscountUsingCodeWorkflow()  
    {  
        Variable<double> Subtotal = new Variable<double>  
        {  
            Default = 75.99,  
            Name = "Subtotal"  
        };  
  
        Variable<double> DiscountPercent = new Variable<double>  
        {  
            Name = "DiscountPercent"  
        };  
  
        Variable<double> Total = new Variable<double>  
        {  
            Name = "Total"  
        };  
  
        Activity wf = new Sequence  
        {  
            Variables = { Subtotal, DiscountPercent, Total },  
            Activities =   
            {  
                new Interop  
                {  
                    ActivityType = typeof(DiscountCalculator),  
                    ActivityProperties =   
                    {  
                        { "Subtotal", new InArgument<double>(Subtotal) },  
                        { "DiscountPercentOut", new OutArgument<double>(DiscountPercent) },  
                        { "TotalOut", new OutArgument<double>(Total) }  
                    }  
                },  
                new WriteLine  
                {  
                    Text =  new InArgument<string>(env =>   
                        string.Format("Subtotal: {0:C}, Discount {1}%, Total {2:C}",   
                        Subtotal.Get(env), DiscountPercent.Get(env) * 100, Total.Get(env)))  
                }  
            }  
        };  
  
        WorkflowInvoker.Invoke(wf);  
    }  
    ```  
  
    > [!NOTE]
    >  `Subtotal` 활동의 `DiscountPercent`, `Total` 및 `DiscountCalculator` 속성은 <xref:System.Activities.Statements.Interop> 활동의 인수로 표시되고 <xref:System.Activities.Statements.Interop> 활동의 <xref:System.Activities.Statements.Interop.ActivityProperties%2A> 컬렉션에서 로컬 워크플로 변수에 바인딩됩니다. `Subtotal`은 <xref:System.Activities.ArgumentDirection.In> 데이터가 `Subtotal` 활동 안으로 흐르기 때문에 <xref:System.Activities.Statements.Interop> 인수로 추가되고, `DiscountPercent` 및 `Total`은 해당 데이터가 <xref:System.Activities.ArgumentDirection.Out> 활동 밖으로 흐르기 때문에 <xref:System.Activities.Statements.Interop> 인수로 추가됩니다. 두 <xref:System.Activities.ArgumentDirection.Out> 인수는 `DiscountPercentOut` 인수임을 나타내기 위해 `TotalOut` 및 <xref:System.Activities.ArgumentDirection.Out>이라는 이름으로 추가됩니다. `DiscountCalculator` 형식은 <xref:System.Activities.Statements.Interop> 활동의 <xref:System.Activities.Statements.Interop.ActivityType%2A>으로 지정됩니다.  
  
5.  Ctrl+F5를 눌러 응용 프로그램을 빌드하고 실행합니다. `Subtotal` 값에 다양한 값을 대체하여 `DiscountCalculator` 활동에서 제공하는 다양한 할인 수준을 테스트합니다.  
  
    ```csharp  
    Variable<double> Subtotal = new Variable<double>  
    {  
        Default = 75.99, // Change this value.  
        Name = "Subtotal"  
    };  
    ```  
  
### <a name="using-the-interop-activity-in-the-workflow-designer"></a>Workflow Designer에서 Interop 활동 사용  
 이 예제에서는 Workflow Designer를 사용하여 워크플로를 만듭니다. 이 워크플로는 <xref:System.Activities.Statements.WriteLine> 활동을 사용하여 할인을 표시하는 대신에 워크플로가 완료될 때 호스트 응용 프로그램이 할인 정보를 검색하여 표시한다는 점을 제외하고 이전 예제와 동일한 기능을 가집니다. 또한 로컬 워크플로 변수를 사용하여 데이터를 포함하는 대신에 Workflow Designer에서 인수가 만들어지고 워크플로가 호출될 때 호스트에서 값이 전달됩니다.  
  
##### <a name="to-host-the-policyactivity-using-a-workflow-designer-created-workflow"></a>워크플로 디자이너에서 만든 워크플로를 사용하여 PolicyActivity를 호스트하려면  
  
1.  마우스 오른쪽 단추로 클릭 **Workflow1.xaml** 에 **솔루션 탐색기** 선택 **삭제**합니다. **확인** 을 클릭하여 확인합니다.  
  
2.  마우스 오른쪽 단추로 클릭 **PolicyInteropHost** 에 **솔루션 탐색기** 선택 **추가**, **새 항목...** .  
  
3.  확장 된 **Visual C# 항목** 노드 선택한 **워크플로**합니다. 선택 **활동** 에서 **Visual C# 항목** 목록입니다.  
  
4.  형식 `DiscountWorkflow` 에 **이름** 상자 한 클릭 **추가**합니다.  
  
5.  클릭는 **인수** 표시 하려면 워크플로 디자이너 왼쪽 아래에서 단추는 **인수** 창.  
  
6.  클릭 **인수 만들기**합니다.  
  
7.  형식 `Subtotal` 에 **이름** 상자 **에** 에서 **방향** 드롭다운 목록에서 선택 **Double** 는 에서**인수 형식이** 드롭 다운 고 enter 키를 눌러 인수를 저장 합니다.  
  
    > [!NOTE]
    >  경우 **Double** 에 속하지 않는 **인수 형식이** 드롭 다운 목록 **형식 찾아보기...** , 형식 `System.Double` 에 **유형 이름** 고 클릭 **확인**합니다.  
  
8.  클릭 **인수 만들기**합니다.  
  
9. 형식 `DiscountPercent` 에 **이름** 상자 **아웃** 에서 **방향** 드롭다운 목록에서 선택 **Double** 는 에서**인수 형식이** 드롭 다운 고 enter 키를 눌러 인수를 저장 합니다.  
  
10. 클릭 **인수 만들기**합니다.  
  
11. 형식 `Total` 에 **이름** 상자 **아웃** 에서 **방향** 드롭다운 목록에서 선택 **Double** 는 에서**인수 형식이** 드롭 다운 고 enter 키를 눌러 인수를 저장 합니다.  
  
12. 클릭는 **인수** 를 닫으려면 워크플로 디자이너 왼쪽 아래에서 단추는 **인수** 창.  
  
13. 끌어서는 **시퀀스** 활동을는 **제어 흐름** 의 섹션은 **도구 상자** 워크플로 디자이너 화면에 놓습니다.  
  
14. 끌어서는 **Interop** 활동을는 **마이그레이션** 의 섹션에서 **도구 상자** 에 놓습니다는 **시퀀스** 활동입니다.  
  
15. 클릭는 **Interop** 활동에는 **찾아보려면 클릭...** 레이블을 입력 합니다. **DiscountCalculator** 에 **유형 이름** 고 클릭 **확인**합니다.  
  
    > [!NOTE]
    >  <xref:System.Activities.Statements.Interop> 활동이 워크플로에 추가되고 `DiscountCalculator` 형식이 해당 <xref:System.Activities.Statements.Interop.ActivityType%2A>으로 지정되면 <xref:System.Activities.Statements.Interop> 활동은 <xref:System.Activities.ArgumentDirection.In> 활동의 세 가지 공용 속성을 나타내는 <xref:System.Activities.ArgumentDirection.Out> 인수 세 개와 `DiscountCalculator` 인수 세 개를 노출합니다. <xref:System.Activities.ArgumentDirection.In> 인수 세 가지 공용 속성 및 3으로 동일한 이름을 사용할 <xref:System.Activities.ArgumentDirection.Out> 인수와 동일한 이름을 가진 **아웃** 속성 이름에 추가 합니다. 다음 단계에서는 이전 단계에서 만든 워크플로 인수가 <xref:System.Activities.Statements.Interop> 활동의 인수에 바인딩됩니다.  
  
16. 형식 `DiscountPercent` 에 **VB 식 입력** 의 오른쪽에 상자는 **DiscountPercentOut** 속성과 TAB 키를 누릅니다.  
  
17. 형식 `Subtotal` 에 **VB 식 입력** 의 오른쪽에 상자는 **Subtotal** 속성과 TAB 키를 누릅니다.  
  
18. 형식 `Total` 에 **VB 식 입력** 의 오른쪽에 상자는 **TotalOut** 속성과 TAB 키를 누릅니다.  
  
19. 마우스 오른쪽 단추로 클릭 **Program.cs** 에 **솔루션 탐색기** 선택 **코드 보기**합니다.  
  
20. 파일 맨 위에 다음 `using` 문을 추가합니다.  
  
    ```csharp  
    using System.Collections.Generic;  
    ```  
  
21. `CalculateDiscountInCode` 메서드에서 `Main` 메서드에 대한 호출을 주석으로 처리하고 다음 코드를 추가합니다.  
  
    > [!NOTE]
    >  이전 절차를 따르지 않은 경우 기본 `Main` 코드가 있으면 `Main`의 내용을 다음 코드로 대체합니다.  
  
    ```csharp  
    static void Main(string[] args)  
    {  
        CalculateDiscountUsingDesignerWorkflow();  
        //CalculateDiscountUsingCodeWorkflow();  
    }  
    ```  
  
22. `Program` 클래스에 다음 코드를 포함하는 `CalculateDiscountUsingDesignerWorkflow`라는 새 메서드를 만듭니다.  
  
    ```csharp  
    static void CalculateDiscountUsingDesignerWorkflow()  
    {  
        double SubtotalValue = 125.99;  
        Dictionary<string, object> wfargs = new Dictionary<string, object>  
        {  
            {"Subtotal", SubtotalValue}  
        };  
  
        Activity wf = new DiscountWorkflow();  
  
        IDictionary<string, object> outputs =  
            WorkflowInvoker.Invoke(wf, wfargs);  
  
        Console.WriteLine("Subtotal: {0:C}, Discount {1}%, Total {2:C}",  
            SubtotalValue, (double)outputs["DiscountPercent"] * 100,  
            outputs["Total"]);  
    }  
    ```  
  
23. Ctrl+F5를 눌러 응용 프로그램을 빌드하고 실행합니다. 다른 `Subtotal` 금액을 지정하려면 다음 코드에서 `SubtotalValue`의 값을 변경합니다.  
  
    ```csharp  
    double SubtotalValue = 125.99; // Change this value.  
    ```  
  
## <a name="rules-features-overview"></a>규칙 기능 개요  
 [!INCLUDE[wf1](../../../includes/wf1-md.md)] 규칙 엔진은 전방 연결을 지원하면서 우선 순위 기반 방식의 규칙 처리를 지원합니다. 단일 항목 또는 컬렉션의 항목에 대해 규칙을 평가할 수 있습니다. 규칙에 대한 간략한 설명과 특정 규칙의 기능에 대한 자세한 내용은 다음 표를 참조하세요.  
  
|규칙 기능|설명서|  
|-------------------|-------------------|  
|규칙 개요|[Windows Workflow Foundation 규칙 엔진 소개](http://go.microsoft.com/fwlink/?LinkID=152836)|  
|RuleSet|[워크플로에서 Ruleset 사용](http://go.microsoft.com/fwlink/?LinkId=178516) 및<xref:System.Workflow.Activities.Rules.RuleSet>|  
|규칙 확인|[Ruleset의 규칙 평가](http://go.microsoft.com/fwlink/?LinkId=178517)|  
|규칙 연결|[전방 연결 제어](http://go.microsoft.com/fwlink/?LinkId=178518) 및 [규칙의 전방 연결](http://go.microsoft.com/fwlink/?LinkId=178519)|  
|규칙에서 컬렉션 처리|[규칙에서 컬렉션 처리](http://go.microsoft.com/fwlink/?LinkId=178520)|  
|PolicyActivity 사용|[PolicyActivity 활동 사용](http://go.microsoft.com/fwlink/?LinkId=178521) 및<xref:System.Workflow.Activities.PolicyActivity>|  
  
 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]에서 만든 워크플로는 선언적 활동 조건 및 [!INCLUDE[wf1](../../../includes/wf1-md.md)], <xref:System.Workflow.Activities.ConditionedActivityGroup> 등의 조건부 활동과 같은 <xref:System.Workflow.Activities.ReplicatorActivity>에서 제공하는 모든 규칙 기능을 사용하는 것은 아닙니다. 필요할 경우 [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] 및 [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)]를 사용하여 만든 워크플로에 이 기능을 사용할 수 있습니다. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][마이그레이션 지침](../../../docs/framework/windows-workflow-foundation/migration-guidance.md)합니다.
