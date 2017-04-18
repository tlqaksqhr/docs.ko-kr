---
title: "연습: Visual Basic을 사용하여 Windows Forms 컨트롤에서 상속 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "사용자 지정 컨트롤[Windows Forms], 상속"
  - "상속, 컨트롤"
  - "상속, 사용자 지정 컨트롤"
  - "상속, 연습"
  - "Windows Forms 컨트롤, 상속"
ms.assetid: fb58d7c8-b702-4478-ad31-b00cae118882
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# 연습: Visual Basic을 사용하여 Windows Forms 컨트롤에서 상속
[!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)]를 사용하면 *상속*을 통해 강력한 사용자 지정 컨트롤을 만들 수 있습니다.  상속을 통하면 표준 Windows Form 컨트롤의 모든 기본 기능을 보유하는 컨트롤을 만들 수 있을 뿐 아니라 사용자 지정 기능도 결합시킬 수 있습니다.  이 연습에서는 `ValueButton`이라는 간단한 상속된 컨트롤을 만듭니다.  이 단추는 표준 Windows Form <xref:System.Windows.Forms.Button> 컨트롤에서 기능이 상속되고 `ButtonValue`라는 사용자 지정 속성을 노출합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
## 프로젝트 만들기  
 새 프로젝트를 만들 때는 루트 네임스페이스, 어셈블리 이름 및 프로젝트 이름을 설정하고 기본 구성 요소가 올바른 네임스페이스에 놓이도록 하기 위해 이름을 지정해야 합니다.  
  
#### ValueButtonLib 컨트롤 라이브러리 및 ValueButton 컨트롤을 만들려면  
  
1.  **파일**메뉴에서 **새로 만들기**를 가리킨 다음 **프로젝트**를 클릭하여 **새 프로젝트** 대화 상자를 엽니다.  
  
2.  [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] 프로젝트 목록에서 **Windows Forms 컨트롤 라이브러리** 프로젝트 템플릿을 선택한 다음 **이름** 상자에 `ValueButtonLib`를 입력합니다.  
  
     기본적으로 프로젝트 이름인 `ValueButtonLib`도 루트 네임스페이스에 할당됩니다.  루트 네임스페이스는 어셈블리에서 구성 요소의 이름을 한정하는 데 사용됩니다.  예를 들어, 두 어셈블리에서 `ValueButton`이라는 이름의 구성 요소가 제공되는 경우 `ValueButtonLib.ValueButton`을 사용하여 `ValueButton` 구성 요소를 지정할 수 있습니다.  자세한 내용은 [Visual Basic의 네임스페이스](../Topic/Namespaces%20in%20Visual%20Basic.md)를 참조하십시오.  
  
3.  **솔루션 탐색기**에서 **UserControl1.vb**를 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **이름 바꾸기**를 선택합니다.  파일 이름을 `ValueButton.vb`로 변경합니다.  모든 참조를 코드 요소 'UserControl1'로 이름을 바꿀지 묻는 메시지가 나타나면 **예** 단추를 클릭합니다.  
  
4.  **솔루션 탐색기**에서 **모든 파일 표시** 단추를 클릭합니다.  
  
5.  **ValueButton.vb** 노드를 열어 디자이너에서 생성한 코드 파일인 **ValueButton.Designer.vb**를 표시합니다.  **코드 편집기**에서 이 파일을 엽니다.  
  
6.  `Class` 문에서 `Partial Public Class ValueButton`을 찾아 이 컨트롤이 상속되는 형식을 <xref:System.Windows.Forms.UserControl>에서 <xref:System.Windows.Forms.Button>으로 변경합니다.  이렇게 하면 상속된 컨트롤이 <xref:System.Windows.Forms.Button> 컨트롤의 모든 기능을 상속합니다.  
  
7.  `InitializeComponent` 메서드를 찾아 <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A> 속성을 할당하는 줄을 제거합니다.  이 속성은 <xref:System.Windows.Forms.Button> 컨트롤에 없습니다.  
  
8.  **파일** 메뉴에서 **모두 저장**을 선택하여 프로젝트를 저장합니다.  
  
     더 이상 비주얼 디자이너를 사용할 수 없습니다.  <xref:System.Windows.Forms.Button> 컨트롤은 자체적으로 그려지므로 디자이너에서 모양을 수정할 수 없습니다.  이 컨트롤의 시각적 표시는 코드에서 수정하지 않을 경우 이를 상속해 준 클래스\(즉, <xref:System.Windows.Forms.Button>\)와 같습니다.  
  
> [!NOTE]
>  UI 요소가 없는 구성 요소를 디자인 화면에 여전히 추가할 수 있습니다.  
  
## 상속된 컨트롤에 속성 추가  
 상속된 Windows Form 컨트롤의 가능한 용도 중 하나는 표준 Windows Form 컨트롤과 같은 모양과 동작\(모양과 느낌\)을 제공하지만 사용자 지정 속성을 노출하는 컨트롤을 만드는 것입니다.  이 단원에서는 사용자 정의 컨트롤에 `ButtonValue`라는 속성을 추가합니다.  
  
#### Value 속성을 추가하려면  
  
1.  **솔루션 탐색기**에서 **ValueButton.vb**를 마우스 오른쪽 단추로 클릭한 다음 바로 가기 메뉴에서 **코드 보기**를 클릭합니다.  
  
2.  `Public Class ValueButton` 문을 찾아  이 문 바로 아래에 다음 코드를 입력합니다.  
  
     \[Visual Basic\]  
  
    ```  
    ' Creates the private variable that will store the value of your   
    ' property.  
    Private varValue as integer  
    ' Declares the property.  
    Property ButtonValue() as Integer  
    ' Sets the method for retrieving the value of your property.  
       Get  
          Return varValue  
       End Get  
    ' Sets the method for setting the value of your property.  
       Set(ByVal Value as Integer)  
          varValue = Value  
       End Set  
    End Property  
    ```  
  
     이 코드는 `ButtonValue` 속성의 저장 및 검색에 사용할 수 있는 메서드를 설정합니다.  `Get` 문은 반환되는 값을 private 변수인 `varValue`에 저장된 값으로 설정하고 `Set` 문은 `Value` 키워드를 사용하여 private 변수의 값을 설정합니다.  
  
3.  **파일** 메뉴에서 **모두 저장**을 선택하여 프로젝트를 저장합니다.  
  
## 컨트롤 테스트  
 컨트롤은 독립 실행형 프로젝트가 아니며 컨테이너에서 호스팅되어야 합니다.  컨트롤을 테스트하려면 해당 컨트롤이 실행될 테스트 프로젝트가 있어야 합니다.   또한 테스트 프로젝트를 빌드\(컴파일\)하여 해당 프로젝트에서 컨트롤에 액세스할 수 있도록 해야 합니다.  이 단원에서는 사용자 정의 컨트롤을 빌드하고 이를 Windows Form에서 테스트합니다.  
  
#### 컨트롤을 빌드하려면  
  
1.  **빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.  
  
     컴파일러 오류 또는 경고 없이 빌드가 성공적이어야 합니다.  
  
#### 테스트 프로젝트를 만들려면  
  
1.  **파일** 메뉴에서 **추가**를 가리킨 다음 **새 프로젝트**를 클릭하여 **새 프로젝트 추가** 대화 상자를 엽니다.  
  
2.  [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] 프로젝트 노드를 선택하고 **Windows Forms 응용 프로그램**을 클릭합니다.  
  
3.  **이름** 상자에 `Test`를 입력합니다.  
  
4.  **솔루션 탐색기**에서 **모든 파일 표시** 단추를 클릭합니다.  
  
5.  **솔루션 탐색기**에서 테스트 프로젝트에 대한 **참조** 노드를 마우스 오른쪽 단추로 클릭한 다음 바로 가기 메뉴에서 **참조 추가**를 선택하여 **참조 추가** 대화 상자를 표시합니다.  
  
6.  **프로젝트** 탭을 클릭합니다.  
  
7.  **프로젝트**라는 레이블이 붙은 탭을 클릭합니다.  `ValueButtonLib` 프로젝트가 **프로젝트 이름** 아래에 나열됩니다.  프로젝트를 두 번 클릭하여 해당 참조를 테스트 프로젝트에 추가합니다.  
  
8.  **솔루션 탐색기**에서 **Test**를 마우스 오른쪽 단추로 클릭한 다음 **빌드**를 선택합니다.  
  
#### 폼에 컨트롤을 추가하려면  
  
1.  **솔루션 탐색기**에서 **Form1.vb**를 마우스 오른쪽 단추로 클릭한 다음 바로 가기 메뉴에서 **디자이너 보기**를 선택합니다.  
  
2.  **도구 상자**에서 **ValueButtonLib 구성 요소**를 클릭합니다.  **ValueButton**을 두 번 클릭합니다.  
  
     폼에 **ValueButton**이 나타납니다.  
  
3.  **ValueButton**을 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **속성**을 선택합니다.  
  
4.  **속성** 창에서 이 컨트롤의 속성을 검사합니다.  이들 속성은 `ButtonValue`라는 추가 속성을 제외하면 표준 단추에서 노출한 속성과 동일합니다.  
  
5.  `ButtonValue` 속성을 `5`로 설정합니다.  
  
6.  **도구 상자**의 **모든 Windows Forms** 탭에서 **Label**을 두 번 클릭하여 <xref:System.Windows.Forms.Label> 컨트롤을 폼에 추가합니다.  
  
7.  Label을 폼의 가운데로 재배치합니다.  
  
8.  `ValueButton1`을 두 번 클릭합니다.  
  
     `ValueButton1_Click` 이벤트에 대해 **코드 편집기**가 열립니다.  
  
9. 다음 코드 줄을 입력합니다.  
  
     \[Visual Basic\]  
  
    ```  
    Label1.Text = CStr(ValueButton1.ButtonValue)  
    ```  
  
10. **솔루션 탐색기**에서 **Test**를 마우스 오른쪽 단추로 클릭한 다음 바로 가기 메뉴에서 **시작 프로젝트로 설정**을 선택합니다.  
  
11. **디버그** 메뉴에서 **디버깅 시작**을 선택합니다.  
  
     `Form1`이 나타납니다.  
  
12. `Valuebutton1`를 클릭합니다.  
  
     상속된 컨트롤의 `ButtonValue` 속성이 `ValueButton1_Click` 메서드를 통해 `Label1`로 전달되었음을 보여 주는 숫자 '5'가 `Label1`에 표시됩니다.  따라서 `ValueButton` 컨트롤은 표준 Windows Form 단추의 모든 기능을 상속하지만 추가적인 사용자 지정 속성은 노출합니다.  
  
## 참고 항목  
 [연습: Visual Basic에서 합성 컨트롤 제작](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-basic.md)   
 [방법: 도구 상자 항목 선택 대화 상자에 컨트롤 표시](../../../../docs/framework/winforms/controls/how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)   
 [.NET Framework에서 사용자 지정 Windows Forms 컨트롤 개발](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)   
 [NOT IN BUILD: Inheritance in Visual Basic](http://msdn.microsoft.com/ko-kr/e5e6e240-ed31-4657-820c-079b7c79313c)   
 [Component Authoring Walkthroughs](../Topic/Component%20Authoring%20Walkthroughs.md)