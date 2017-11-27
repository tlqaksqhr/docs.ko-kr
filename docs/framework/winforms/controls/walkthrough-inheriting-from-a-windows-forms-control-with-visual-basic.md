---
title: "연습: Visual Basic을 사용하여 Windows Forms 컨트롤에서 상속"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: vb
helpviewer_keywords:
- inheritance [Windows Forms], custom controls
- inheritance [Windows Forms], control
- Windows Forms controls, inheritance
- inheritance [Windows Forms], walkthroughs
- custom controls [Windows Forms], inheritance
ms.assetid: fb58d7c8-b702-4478-ad31-b00cae118882
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0625695933b776b8cdbe5488adc116723b930dd0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic"></a>연습: Visual Basic을 사용하여 Windows Forms 컨트롤에서 상속
[!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)]에서는 *상속*을 통해 강력한 사용자 지정 컨트롤을 만들 수 있습니다. 상속을 통해 표준 Windows Forms 컨트롤의 모든 고유 기능을 유지하면서 사용자 지정 기능을 통합하는 컨트롤을 만들 수 있습니다. 이 연습에서는 `ValueButton`이라는 간단한 상속된 컨트롤을 만듭니다. 이 단추는 표준 Windows Forms에서 기능을 상속 <xref:System.Windows.Forms.Button> 컨트롤을 호출 하는 사용자 지정 속성을 노출 합니다 `ButtonValue`합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
## <a name="creating-the-project"></a>프로젝트 만들기  
 새 프로젝트를 만들 때는 루트 네임스페이스, 어셈블리 이름 및 프로젝트 이름을 설정하기 위해 이름을 지정하고 기본 구성 요소가 올바른 네임스페이스에 있는지 확인합니다.  
  
#### <a name="to-create-the-valuebuttonlib-control-library-and-the-valuebutton-control"></a>ValueButtonLib 컨트롤 라이브러리 및 ValueButton 컨트롤을 만들려면  
  
1.  **파일** 메뉴에서 **새로 만들기**를 가리키고 **프로젝트**를 선택하여 **새 프로젝트** 대화 상자를 엽니다.  
  
2.  [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] 프로젝트 목록에서 **Windows Forms 컨트롤 라이브러리** 프로젝트 템플릿을 선택하고 **이름** 상자에 `ValueButtonLib`를 입력합니다.  
  
     프로젝트 이름, `ValueButtonLib`는 기본적으로 루트 네임스페이스에도 할당됩니다. 루트 네임스페이스는 어셈블리에서 구성 요소의 이름을 정규화하는 데 사용됩니다. 예를 들어 두 어셈블리에서 `ValueButton`이라는 구성 요소를 제공하면 `ValueButtonLib.ValueButton`을 사용하여 `ValueButton` 구성 요소를 지정할 수 있습니다. 자세한 내용은 [Visual Basic의 네임스페이스](~/docs/visual-basic/programming-guide/program-structure/namespaces.md)를 참조하세요.  
  
3.  **솔루션 탐색기**에서 **UserControl1.vb**를 마우스 오른쪽 단추로 클릭한 다음 바로 가기 메뉴에서 **이름 바꾸기**를 선택합니다. 파일 이름을 `ValueButton.vb`로 변경합니다. 코드 요소 'UserControl1'에 대한 모든 참조 이름을 변경할지 묻는 메시지가 표시되면 **예** 단추를 클릭합니다.  
  
4.  **솔루션 탐색기**에서 **모든 파일 표시** 단추를 클릭합니다.  
  
5.  **ValueButton.vb** 노드를 열어 디자이너에서 생성한 코드 파일인 **ValueButton.Designer.vb**를 표시합니다. **코드 편집기**에서 이 파일을 엽니다.  
  
6.  찾을 `Class` 문, `Partial Public Class ValueButton`,이 컨트롤에서 상속 된 형식을 변경 하 고 <xref:System.Windows.Forms.UserControl> 를 <xref:System.Windows.Forms.Button>합니다. 이렇게 하면 상속 된 컨트롤의 모든 기능을 상속는 <xref:System.Windows.Forms.Button> 제어 합니다.  
  
7.  찾습니다는 `InitializeComponent` 메서드 및 remove 할당 하는 줄은 <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A> 속성입니다. 이 속성에 존재 하지 않습니다는 <xref:System.Windows.Forms.Button> 제어 합니다.  
  
8.  **파일** 메뉴에서 **모두 저장**을 선택하여 프로젝트를 저장합니다.  
  
     비주얼 디자이너는 더 이상 사용할 수 없습니다. 때문에 <xref:System.Windows.Forms.Button> 디자이너에서 모양을 수정할 수 없는, 컨트롤은 자체 그리기를 수행 합니다. 시각적 표시는 정확히 같을 수에서 상속 된 클래스의 (즉, <xref:System.Windows.Forms.Button>)는 코드에서 수정 하지 않는 한 합니다.  
  
> [!NOTE]
>  UI 요소가 없는 구성 요소를 디자인 화면에 계속 추가할 수 있습니다.  
  
## <a name="adding-a-property-to-your-inherited-control"></a>상속된 컨트롤에 속성 추가  
 상속된 Windows Forms 컨트롤의 한 가지 가능한 용도는 표준 Windows Forms 컨트롤과 모양 및 동작(모양 및 느낌)이 동일하지만 사용자 지정 속성을 노출하는 컨트롤을 만드는 것입니다. 이 섹션에서는 `ButtonValue`라는 속성을 컨트롤에 추가합니다.  
  
#### <a name="to-add-the-value-property"></a>Value 속성을 추가하려면  
  
1.  **솔루션 탐색기**에서 **ValueButton.vb**를 마우스 오른쪽 단추로 클릭한 다음 바로 가기 메뉴에서 **코드 보기**를 클릭합니다.  
  
2.  `Public Class ValueButton` 문을 찾습니다. 이 문 바로 아래에 다음 코드를 입력합니다.  
  
    ```vb  
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
  
     이 코드는 `ButtonValue` 속성을 저장 및 검색할 메서드를 설정합니다. `Get` 문은 반환된 값을 private 변수 `varValue`에 저장된 값으로 설정하고 `Set` 문은 `Value` 키워드를 사용하여 private 변수의 값을 설정합니다.  
  
3.  **파일** 메뉴에서 **모두 저장**을 선택하여 프로젝트를 저장합니다.  
  
## <a name="testing-your-control"></a>컨트롤 테스트  
 컨트롤은 독립 실행형 프로젝트가 아니며 컨테이너에서 호스팅해야 합니다. 컨트롤을 테스트하려면 컨트롤을 실행할 테스트 프로젝트를 제공해야 합니다. 또한 컨트롤을 빌드(컴파일)하여 컨트롤에서 테스트 프로젝트에 액세스할 수 있도록 해야 합니다. 이 섹션에서는 컨트롤을 테스트하고 Windows Form에서 테스트합니다.  
  
#### <a name="to-build-your-control"></a>컨트롤을 빌드하려면  
  
1.  **빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.  
  
     컴파일러 오류 또는 경고 없이 빌드에 성공해야 합니다.  
  
#### <a name="to-create-a-test-project"></a>테스트 프로젝트를 만들려면  
  
1.  **파일** 메뉴에서 **추가**를 가리킨 후 **새 프로젝트**를 클릭하여 **새 프로젝트 추가** 대화 상자를 엽니다.  
  
2.  [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] 프로젝트 노드를 선택하고 **Windows Forms 응용 프로그램**을 클릭합니다.  
  
3.  **이름** 상자에 `Test`을 입력합니다.  
  
4.  **솔루션 탐색기**에서 **모든 파일 표시** 단추를 클릭합니다.  
  
5.  **솔루션 탐색기**에서 테스트 프로젝트에 대한 **참조** 노드를 마우스 오른쪽 단추로 클릭한 다음 바로 가기 메뉴에서 **참조 추가**를 선택하면 **참조 추가** 대화 상자가 표시됩니다.  
  
6.  **프로젝트** 탭을 클릭합니다.  
  
7.  **프로젝트**로 레이블이 지정된 탭을 클릭합니다. `ValueButtonLib` 프로젝트가 **프로젝트 이름** 아래에 나열됩니다. 프로젝트를 두 번 클릭하여 테스트 프로젝트에 참조를 추가합니다.  
  
8.  **솔루션 탐색기**에서 **Test**를 마우스 오른쪽 단추로 클릭한 후 **빌드**를 선택합니다.  
  
#### <a name="to-add-your-control-to-the-form"></a>폼에 컨트롤을 추가하려면  
  
1.  **솔루션 탐색기**에서 **Form1.vb**를 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **뷰 디자이너**를 선택합니다.  
  
2.  **도구 상자**에서 **ValueButtonLib 구성 요소**를 클릭합니다. **ValueButton**을 두 번 클릭합니다.  
  
     **ValueButton**이 폼에 나타납니다.  
  
3.  **ValueButton**을 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **속성**을 선택합니다.  
  
4.  **속성** 창에서 이 컨트롤의 속성을 점검합니다. `ButtonValue`라는 추가 속성이 있는 것을 제외하고, 표준 단추에 노출된 속성과 동일한 것을 확인할 수 있습니다.  
  
5.  `ButtonValue` 속성을 `5`으로 설정합니다.  
  
6.  에 **모든 Windows Forms** 탭은 **도구 상자**, 두 번 클릭 **레이블** 추가 하는 <xref:System.Windows.Forms.Label> 컨트롤을 폼입니다.  
  
7.  폼 가운데에 레이블을 다시 배치합니다.  
  
8.  `ValueButton1`을 두 번 클릭합니다.  
  
     **코드 편집기**에 `ValueButton1_Click` 이벤트가 열립니다.  
  
9. 다음 코드 행을 입력합니다.  
  
    ```vb  
    Label1.Text = CStr(ValueButton1.ButtonValue)  
    ```  
  
10. **솔루션 탐색기**에서 **Test**를 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **시작 프로젝트로 설정**을 선택합니다.  
  
11. **디버그** 메뉴에서 **디버깅 시작**을 선택합니다.  
  
     `Form1`이 나타납니다.  
  
12. `Valuebutton1`을 클릭합니다.  
  
     숫자 '5'가 `Label1`에 표시되며 상속된 컨트롤의 `ButtonValue` 속성이 `ValueButton1_Click` 메서드를 통해 `Label1`에 전달되었음을 보여 줍니다. 따라서 `ValueButton` 컨트롤은 표준 Windows Forms 단추의 모든 기능을 상속하지만 추가 사용자 지정 속성을 노출합니다.  
  
## <a name="see-also"></a>참고 항목  
 [연습: Visual Basic에서 합성 컨트롤 작성](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-basic.md)  
 [방법: 도구 상자 항목 선택 대화 상자에 컨트롤 표시](../../../../docs/framework/winforms/controls/how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)  
 [.NET Framework에서 사용자 지정 Windows Forms 컨트롤 개발](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)  
 [상속 기본 사항 (Visual Basic)](~/docs/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)  
 [구성 요소 제작 연습](http://msdn.microsoft.com/library/c414cca9-2489-4208-8b38-954586d91c13)
