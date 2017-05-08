---
title: ".NET Framework 4 워크플로에서 Interop 활동 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9bb747f0-eb33-4f70-84cd-317382372dcd
caps.latest.revision: 20
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 20
---
# .NET Framework 4 워크플로에서 Interop 활동 사용
사용 하 여 만든 활동 [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] 또는 [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] 에서 사용할 수는 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] 를 사용 하 여 워크플로 <xref:System.Activities.Statements.Interop> 활동입니다. 이 항목에서는 사용 하 여 간략하게는 <xref:System.Activities.Statements.Interop> 활동입니다.  
  
> [!NOTE]
>   <xref:System.Activities.Statements.Interop> 워크플로 프로젝트에 없는 경우 활동이 워크플로 디자이너 도구 상자에 나타나지 않습니다 해당 **대상 프레임 워크** 설정이로 **.NET Framework 4** 이상.  
  
## <a name="using-the-interop-activity-in-net-framework-45-workflows"></a>.NET Framework 4.5 워크플로에서 Interop 활동 사용  
 이 항목에서는 [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] 활동을 포함하는 `DiscountCalculator` 활동 라이브러리를 만듭니다.  `DiscountCalculator` 는 구매량을 기준으로 할인을 계산 하 고 이루어져는 <xref:System.Workflow.Activities.SequenceActivity> 를 포함 하는 <xref:System.Workflow.Activities.PolicyActivity>합니다.  
  
> [!NOTE]
>   [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] 사용 하 여이 항목에서 만든 활동은 <xref:System.Workflow.Activities.PolicyActivity> 활동의 논리를 구현 합니다. 사용자 지정을 사용 하 여 필요는 없습니다 [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] 활동 또는 <xref:System.Activities.Statements.Interop> 에 규칙을 사용 하려면 작업을 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] 워크플로. 규칙을 사용 하는 예제에 대 한 한 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] 워크플로 사용 하지 않고는 <xref:System.Activities.Statements.Interop> 활동 참조는 [.NET Framework 4.5의 정책 활동](../../../docs/framework/windows-workflow-foundation/samples/policy-activity-in-net-framework-4-5.md) 샘플입니다.  
  
#### <a name="to-create-the-net-framework-35-activity-library-project"></a>.NET Framework 3.5 활동 라이브러리 프로젝트를 만들려면  
  
1.  열기 [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] 선택한 **새로** 차례로 **프로젝트...**  **파일** 메뉴.  
  
2.  확장 된 **기타 프로젝트 형식** 에서 노드는 **설치 된 템플릿** 창과 선택 **Visual Studio 솔루션**합니다.  
  
3.  선택 **빈 솔루션** 에서 **Visual Studio 솔루션** 목록입니다. 형식 `PolicyInteropDemo` 에 **이름** 클릭 **확인**합니다.  
  
4.  마우스 오른쪽 단추로 클릭 **PolicyInteropDemo** 에서 **솔루션 탐색기** 선택한 **추가** 차례로 **새 프로젝트...**합니다.  
  
    > [!TIP]
    >  하는 경우는 **솔루션 탐색기** 창이 표시, 선택 되지 않으면 **솔루션 탐색기** 에서 **보기** 메뉴.  
  
5.  에 **설치 된 템플릿** 목록에서 **Visual C#** 차례로 **워크플로**합니다. 선택 **.NET Framework 3.5** 는.NET Framework 버전 드롭다운 목록에서 선택한 후 **워크플로 활동 라이브러리** 에서 **템플릿** 목록입니다.  
  
6.  형식 `PolicyActivityLibrary` 에 **이름** 클릭 **확인**합니다.  
  
7.  마우스 오른쪽 단추로 클릭 **Activity1.cs** 에서 **솔루션 탐색기** 선택한 **삭제**합니다. **확인** 을 클릭하여 확인합니다.  
  
#### <a name="to-create-the-discountcalculator-activity"></a>DiscountCalculator 활동을 만들려면  
  
1.  마우스 오른쪽 단추로 클릭 **PolicyActivityLibrary** 에서 **솔루션 탐색기** 선택한 **추가** 차례로 **활동 …**합니다.  
  
2.  선택 **활동 (코드 분리)** 에서 **Visual C# 항목** 목록입니다. 형식 `DiscountCalculator` 에 **이름** 클릭 **확인**합니다.  
  
3.  마우스 오른쪽 단추로 클릭 **DiscountCalculator.xoml** 에서 **솔루션 탐색기** 선택한 **코드 보기**합니다.  
  
4.  `DiscountCalculator` 클래스에 다음 세 가지 속성을 추가합니다.  
  
    ```csharp  
    public partial class DiscountCalculator : SequenceActivity  
    {  
        public double Subtotal { get; set; }  
        public double DiscountPercent { get; set; }  
        public double Total { get; set; }  
    }  
    ```  
  
5.  마우스 오른쪽 단추로 클릭 **DiscountCalculator.xoml** 에서 **솔루션 탐색기** 선택한 **뷰 디자이너**합니다.  
  
6.  끌기는 **정책** 활동을는 **Windows Workflow v3.0** 섹션은 **도구 상자** 놓습니다는 **DiscountCalculator** 활동 합니다.  
  
    > [!TIP]
    >  하는 경우는 **도구 상자** 창이 표시, 선택 되지 않으면 **도구 상자** 에서 **보기** 메뉴.  
  
#### <a name="to-configure-the-rules"></a>규칙을 구성하려면  
  
1.  새로 추가 된 클릭 **정책** 활동을 아직 선택 하지 않은 경우에 선택 합니다.  
  
2.  클릭는 **RuleSetReference** 속성에는 **속성** 창, 선택한 속성의 오른쪽에 줄임표 (...) 단추를 클릭 합니다.  
  
    > [!TIP]
    >  하는 경우는 **속성** 창이 표시 되지 않으면, 선택 **속성 창** 에서 **보기** 메뉴.  
  
3.  선택 **새로 만들기 클릭...**합니다.  
  
4.  클릭 **규칙 추가**합니다.  
  
5.  에 다음 식을 입력은 **조건** 상자입니다.  
  
    ```  
    this.Subtotal >= 50 && this.Subtotal < 100  
    ```  
  
6.  에 다음 식을 입력은 **Thenactions** 상자입니다.  
  
    ```  
    this.DiscountPercent = 0.075  
    ```  
  
7.  클릭 **규칙 추가**합니다.  
  
8.  에 다음 식을 입력은 **조건** 상자입니다.  
  
    ```  
    this.Subtotal >= 100  
    ```  
  
9. 에 다음 식을 입력은 **Thenactions** 상자입니다.  
  
    ```  
    this.DiscountPercent = 0.15  
    ```  
  
10. 클릭 **규칙 추가**합니다.  
  
11. 에 다음 식을 입력은 **조건** 상자입니다.  
  
    ```  
    this.DiscountPercent > 0  
    ```  
  
12. 에 다음 식을 입력은 **Thenactions** 상자입니다.  
  
    ```  
    this.Total = this.Subtotal - this.Subtotal * this.DiscountPercent  
    ```  
  
13. 에 다음 식을 입력은 **Else 작업** 상자입니다.  
  
    ```  
    this.Total = this.Subtotal  
    ```  
  
14. 클릭 **확인** 를 닫으려면는 **규칙 집합 편집기** 대화 상자입니다.  
  
15. 새로 만든 되도록 <xref:System.Workflow.Activities.Rules.RuleSet> 에서 선택한는 **이름** 를 클릭 하 여 **확인**합니다.  
  
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
  
 때는 <xref:System.Workflow.Activities.PolicyActivity> 실행,이 세 가지 규칙 평가 하 고 수정는 `Subtotal`, `DiscountPercent`, 및 `Total` 속성 값이는 `DiscountCalculator` 활동 원하는 할인을 계산 합니다.  
  
## <a name="using-the-discountcalculator-activity-with-the-interop-activity"></a>Interop 활동과 함께 DiscountCalculator 활동 사용  
 사용 하는 `DiscountCalculator` 내 활동은 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] 워크플로 <xref:System.Activities.Statements.Interop> 활동을 사용 합니다. 이 섹션에서는 두 워크플로 생성을 하나 사용 하는 방법을 보여 주는 코드 및 workflow designer를 사용 하 여 하나를 사용 하는 <xref:System.Activities.Statements.Interop> 와 관련 된 활동의 `DiscountCalculator` 활동입니다. 두 워크플로에 동일한 호스트 응용 프로그램을 사용합니다.  
  
#### <a name="to-create-the-host-application"></a>호스트 응용 프로그램을 만들려면  
  
1.  마우스 오른쪽 단추로 클릭 **PolicyInteropDemo** 에서 **솔루션 탐색기** 선택한 **추가**, 차례로 **새 프로젝트...**합니다.  
  
2.  확인 **.NET Framework 4.5** 을.NET Framework 버전 드롭다운 목록에서 선택 하 고 선택  **워크플로 콘솔 응용 프로그램** 에서 **Visual C# 항목** 목록입니다.  
  
3.  형식 `PolicyInteropHost` 에 **이름** 클릭 **확인**합니다.  
  
4.  마우스 오른쪽 단추로 클릭 **PolicyInteropHost** 에서 **솔루션 탐색기** 선택한 **속성**합니다.  
  
5.  에 **대상 프레임 워크** 드롭 다운 목록에서 선택 항목을 변경 **.NET Framework 4 Client Profile** 에 **.NET Framework 4.5**합니다. 클릭 **예** 확인 합니다.  
  
6.  마우스 오른쪽 단추로 클릭 **PolicyInteropHost** 에서 **솔루션 탐색기** 선택한 **참조 추가...**합니다.  
  
7.  선택 **PolicyActivityLibrary** 에서 **프로젝트** 탭을 클릭 **확인**합니다.  
  
8.  마우스 오른쪽 단추로 클릭 **PolicyInteropHost** 에서 **솔루션 탐색기** 선택한 **참조 추가...**합니다.  
  
9. 선택 **System.Workflow.Activities**, **System.Workflow.ComponentModel**, 차례로 **System.Workflow.Runtime** 에서 **.NET** 탭을 클릭 **확인**합니다.  
  
10. 마우스 오른쪽 단추로 클릭 **PolicyInteropHost** 에서 **솔루션 탐색기** 선택한 **시작 프로젝트로 설정**합니다.  
  
11. Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.  
  
### <a name="using-the-interop-activity-in-code"></a>코드에서 Interop 활동 사용  
 이 예제에서는 워크플로 정의 사용 하 여 만들어집니다 포함 하는 코드는 <xref:System.Activities.Statements.Interop> 활동 및 `DiscountCalculator` 활동입니다. 이 워크플로 사용 하 여 호출 <xref:System.Activities.WorkflowInvoker> 규칙 평가 결과 사용 하 여 콘솔에 기록 됩니다는 <xref:System.Activities.Statements.WriteLine> 활동입니다.  
  
##### <a name="to-use-the-interop-activity-in-code"></a>코드에서 Interop 활동을 사용하려면  
  
1.  마우스 오른쪽 단추로 클릭 **Program.cs** 에서 **솔루션 탐색기** 선택한 **코드 보기**합니다.  
  
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
    >   `Subtotal`, `DiscountPercent`, 및 `Total` 의 속성은 `DiscountCalculator` 활동의 인수로 표시 되는 <xref:System.Activities.Statements.Interop> 활동과 로컬 워크플로 변수에 바인딩됩니다에 <xref:System.Activities.Statements.Interop> 활동의 <xref:System.Activities.Statements.Interop.ActivityProperties%2A> 컬렉션. `Subtotal` 으로 추가 됩니다는 <xref:System.Activities.ArgumentDirection> 인수 때문에 `Subtotal` 데이터 흐름에 <xref:System.Activities.Statements.Interop> 활동 및 `DiscountPercent` 및 `Total` 으로 추가 됩니다 <xref:System.Activities.ArgumentDirection> 인수 데이터 밖으로 흐르기 때문에 <xref:System.Activities.Statements.Interop> 활동입니다. 두 <xref:System.Activities.ArgumentDirection> 인수는 이름으로 추가 됩니다 `DiscountPercentOut` 및 `TotalOut` 나타내는 나타내려면 <xref:System.Activities.ArgumentDirection> 인수입니다.  `DiscountCalculator` 형식으로 지정 되는 <xref:System.Activities.Statements.Interop> 활동의 <xref:System.Activities.Statements.Interop.ActivityType%2A>합니다.  
  
5.  Ctrl+F5를 눌러 응용 프로그램을 빌드하고 실행합니다. `Subtotal` 값에 다양한 값을 대체하여 `DiscountCalculator` 활동에서 제공하는 다양한 할인 수준을 테스트합니다.  
  
    ```csharp  
    Variable<double> Subtotal = new Variable<double>  
    {  
        Default = 75.99, // Change this value.  
        Name = "Subtotal"  
    };  
    ```  
  
### <a name="using-the-interop-activity-in-the-workflow-designer"></a>Workflow Designer에서 Interop 활동 사용  
 이 예제에서는 워크플로 디자이너를 사용하여 워크플로를 만듭니다. 이 워크플로 이전 예제에서와 동일한 기능을 제외한 보다 사용 하는 대신 한 <xref:System.Activities.Statements.WriteLine> 할인을 표시 하는 활동 호스트 응용 프로그램 검색 하 고 워크플로가 완료 되는 할인 정보를 표시 합니다. 또한 로컬 워크플로 변수를 사용하여 데이터를 포함하는 대신에 워크플로 디자이너에서 인수가 만들어지고 워크플로가 호출될 때 호스트에서 값이 전달됩니다.  
  
##### <a name="to-host-the-policyactivity-using-a-workflow-designer-created-workflow"></a>워크플로 디자이너에서 만든 워크플로를 사용하여 PolicyActivity를 호스트하려면  
  
1.  마우스 오른쪽 단추로 클릭 **Workflow1.xaml** 에서 **솔루션 탐색기** 선택한 **삭제**합니다. **확인** 을 클릭하여 확인합니다.  
  
2.  마우스 오른쪽 단추로 클릭 **PolicyInteropHost** 에서 **솔루션 탐색기** 선택한 **추가**, **새 항목...**합니다.  
  
3.  확장 된 **Visual C# 항목** 노드 선택한 **워크플로**합니다. 선택 **활동** 에서 **Visual C# 항목** 목록입니다.  
  
4.  형식 `DiscountWorkflow` 에 **이름** 클릭 **추가**합니다.  
  
5.  클릭 된 **인수** 표시 하는 워크플로 디자이너의 왼쪽 아래에서 단추는 **인수** 창.  
  
6.  클릭 **인수 만들기**합니다.  
  
7.  형식 `Subtotal` 에 **이름** 상자에서 **에** 에서 **방향** 드롭다운 목록에서 선택 **Double** 에서 **인수 형식** 드롭 다운 고 enter 키를 눌러 인수를 저장 합니다.  
  
    > [!NOTE]
    >  경우 **Double** 에 없는 **인수 형식** 드롭 다운 목록에서 **형식 찾아보기...**, 형식 `System.Double` 에 **형식 이름** 상자를 클릭 **확인**합니다.  
  
8.  클릭 **인수 만들기**합니다.  
  
9. 형식 `DiscountPercent` 에 **이름** 상자에서 **아웃** 에서 **방향** 드롭다운 목록에서 선택 **Double** 에서 **인수 형식** 드롭 다운 고 enter 키를 눌러 인수를 저장 합니다.  
  
10. 클릭 **인수 만들기**합니다.  
  
11. 형식 `Total` 에 **이름** 상자에서 **아웃** 에서 **방향** 드롭다운 목록에서 선택 **Double** 에서 **인수 형식** 드롭 다운 고 enter 키를 눌러 인수를 저장 합니다.  
  
12. 클릭 된 **인수** 를 닫으려면 워크플로 디자이너의 왼쪽 아래에서 단추는 **인수** 창.  
  
13. 끌기는 **시퀀스** 활동을는 **제어 흐름** 의 섹션은 **도구 상자** workflow designer 화면에 놓습니다.  
  
14. 끌기는 **Interop** 활동을는 **마이그레이션** 섹션은 **도구 상자** 놓습니다는 **시퀀스** 활동 합니다.  
  
15. 클릭 하 고 **Interop** 활동에는 **찾아보려면 클릭...** 레이블, 입력 **DiscountCalculator** 에 **형식 이름** 상자를 클릭 **확인**합니다.  
  
    > [!NOTE]
    >  때는 <xref:System.Activities.Statements.Interop> 활동을 워크플로에 추가 및 `DiscountCalculator` 으로 형식이 지정 되어 해당 <xref:System.Activities.Statements.Interop.ActivityType%2A>,  <xref:System.Activities.Statements.Interop> 활동 세 개를 노출 합니다. <xref:System.Activities.ArgumentDirection> 인수 및 3 <xref:System.Activities.ArgumentDirection> 의 세 가지 공용 속성을 나타내는 인수가 `DiscountCalculator` 활동 합니다.  <xref:System.Activities.ArgumentDirection> 인수 이름이 같은 세 가지 공용 속성 및 세 가지 <xref:System.Activities.ArgumentDirection> 인수와 같은 이름을 가진 **아웃** 속성 이름에 추가 합니다. 다음 단계에서는 이전 단계에서 만든 워크플로 인수가에 바인딩된는 <xref:System.Activities.Statements.Interop> 활동의 인수입니다.  
  
16. 형식 `DiscountPercent` 에 **VB 식 입력** 의 오른쪽 상자에는 **DiscountPercentOut** 속성과 TAB 키를 누릅니다.  
  
17. 형식 `Subtotal` 에 **VB 식 입력** 의 오른쪽 상자에는 **Subtotal** 속성과 TAB 키를 누릅니다.  
  
18. 형식 `Total` 에 **VB 식 입력** 의 오른쪽 상자에는 **TotalOut** 속성과 TAB 키를 누릅니다.  
  
19. 마우스 오른쪽 단추로 클릭 **Program.cs** 에서 **솔루션 탐색기** 선택한 **코드 보기**합니다.  
  
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
|RuleSet|[워크플로에서 Ruleset 사용](http://go.microsoft.com/fwlink/?LinkId=178516) 및 <xref:System.Workflow.Activities.Rules.RuleSet>|  
|규칙 확인|[Ruleset의 규칙 확인](http://go.microsoft.com/fwlink/?LinkId=178517)|  
|규칙 연결|[전방 연결 제어](http://go.microsoft.com/fwlink/?LinkId=178518) 및 [규칙의 전방 연결](http://go.microsoft.com/fwlink/?LinkId=178519)|  
|규칙에서 컬렉션 처리|[규칙에서 컬렉션 처리](http://go.microsoft.com/fwlink/?LinkId=178520)|  
|PolicyActivity 사용|[PolicyActivity 활동을 사용 하 여](http://go.microsoft.com/fwlink/?LinkId=178521) 및 <xref:System.Workflow.Activities.PolicyActivity>|  
  
 만든 워크플로 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] 모두 제공 하는 규칙 기능을 사용 하지 않는 [!INCLUDE[wf1](../../../includes/wf1-md.md)], 선언적 활동 조건 및 조건부 활동과 같은 <xref:System.Workflow.Activities.ConditionedActivityGroup> 및 <xref:System.Workflow.Activities.ReplicatorActivity>합니다. 필요할 경우 [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] 및 [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)]를 사용하여 만든 워크플로에 이 기능을 사용할 수 있습니다. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][마이그레이션 지침](../../../docs/framework/windows-workflow-foundation//migration-guidance.md)합니다.