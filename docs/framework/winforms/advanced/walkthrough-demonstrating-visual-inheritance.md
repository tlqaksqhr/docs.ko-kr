---
title: "연습: 시각적 상속 설명 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "폼 상속, 연습"
  - "상속, 연습"
  - "시각적 상속"
  - "연습[Windows Forms], 시각적 상속"
  - "Windows Forms, 상속"
ms.assetid: 01966086-3142-450e-8210-3fd4cb33f591
caps.latest.revision: 24
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 24
---
# 연습: 시각적 상속 설명
시각적 상속을 통해 기본 폼의 컨트롤을 보고 새 컨트롤을 추가할 수 있습니다.  이 연습에서는 기본 폼을 만들고 클래스 라이브러리로 컴파일합니다.  이 클래스 라이브러리를 다른 프로젝트로 가져와 기본 폼에서 상속하는 새 양식을 만듭니다.  이 연습에서는 다음 작업을 수행하는 방법을 배웁니다.  
  
-   기본 폼을 포함하는 클래스 라이브러리 프로젝트를 만듭니다.  
  
-   기본 폼의 파생 클래스가 수정할 수 있는 속성을 가진 단추를 추가합니다.  
  
-   기본 폼의 상속자가 수정할 수 없는 단추를 추가합니다.  
  
-   `BaseForm`에서 상속하는 폼을 포함하는 프로젝트를 만듭니다.  
  
 궁극적으로, 이 연습에서는 상속된 폼의 private 컨트롤과 protected 컨트롤 간의 차이점을 보여 줍니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
> [!CAUTION]
>  일부 컨트롤은 기본 폼에서의 시각적 상속을 지원하지 않습니다.  다음 컨트롤은 이 연습에 설명된 시나리오를 지원하지 않습니다.  
>   
>  <xref:System.Windows.Forms.WebBrowser>  
>   
>  <xref:System.Windows.Forms.ToolStrip>  
>   
>  <xref:System.Windows.Forms.ToolStripPanel>  
>   
>  <xref:System.Windows.Forms.TableLayoutPanel>  
>   
>  <xref:System.Windows.Forms.FlowLayoutPanel>  
>   
>  <xref:System.Windows.Forms.DataGridView>  
>   
>  상속된 폼의 이러한 컨트롤은 사용하는 한정자\(`private`, `protected` 또는 `public`\)에 관계없이 항상 읽기 전용입니다.  
  
## 시나리오 단계  
 첫 번째 단계는 기본 폼을 만드는 것입니다.  
  
#### 기본 폼을 포함하는 클래스 라이브러리 프로젝트를 만들려면  
  
1.  **파일** 메뉴에서 **새로 만들기**, **프로젝트**를 차례로 선택하여 **새 프로젝트** 대화 상자를 엽니다.  
  
2.  `BaseFormLibrary`라는 Windows Forms 응용 프로그램을 만듭니다.  
  
3.  표준 Windows Forms 응용 프로그램 대신 클래스 라이브러리를 만들려면 **솔루션 탐색기**에서 **BaseFormLibrary** 프로젝트 노드를 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.  
  
4.  프로젝트 속성에서 **출력 형식**을 **Windows 응용 프로그램**에서 **클래스 라이브러리**로 변경합니다.  
  
5.  **파일** 메뉴에서 **모두 저장**을 선택하여 프로젝트와 파일을 기본 위치에 저장합니다.  
  
 다음 두 절차에서는 기본 폼에 단추를 추가합니다.  시각적 상속을 보여 주기 위해 단추의 `Modifiers` 속성을 설정하여 단추에 다양한 액세스 수준을 제공합니다.  
  
#### 기본 폼의 상속자가 수정할 수 있는 단추를 추가하려면  
  
1.  디자이너에서 **Form1**을 엽니다.  
  
2.  **도구 상자**의 **모든 Windows Forms** 탭에서 **단추**를 두 번 클릭하여 폼에 단추를 추가합니다.  마우스를 사용하여 단추를 배치하고 크기를 조정합니다.  
  
3.  속성 창에서 단추의 다음 속성을 설정합니다.  
  
    -   **Text** 속성을 **Say Hello**로 설정합니다.  
  
    -   **\(Name\)** 속성을 **btnProtected**로 설정합니다.  
  
    -   **Modifiers** 속성을 **Protected**로 설정합니다.  이렇게 하면 **Form1**에서 상속하는 폼이 **btnProtected**의 속성을 수정할 수 있습니다.  
  
4.  **Say Hello** 단추를 두 번 클릭하여 **Click** 이벤트에 대한 이벤트 처리기를 추가합니다.  
  
5.  다음 코드 줄을 이벤트 처리기에 추가합니다.  
  
    ```vb  
    MessageBox.Show("Hello, World!")  
    ```  
  
    ```csharp  
    MessageBox.Show("Hello, World!");  
    ```  
  
#### 기본 폼의 상속자가 수정할 수 없는 단추를 추가하려면  
  
1.  코드 편집기 위의 **Form1.vb \[Design\], Form1.cs \[Design\] 또는 Form1.jsl \[Design\]** 탭을 클릭하거나 F7 키를 눌러 디자인 뷰로 전환합니다.  
  
2.  두 번째 단추를 추가하고 해당 속성을 다음과 같이 설정합니다.  
  
    -   **Text** 속성을 **Say Goodbye**로 설정합니다.  
  
    -   **\(Name\)** 속성을 **btnPrivate**로 설정합니다.  
  
    -   **Modifiers** 속성을 **Private**로 설정합니다.  이렇게 하면 **Form1**에서 상속하는 폼이 **btnPrivate**의 속성을 수정할 수 없습니다.  
  
3.  **Say Goodbye** 단추를 두 번 클릭하여 **Click** 이벤트에 대한 이벤트 처리기를 추가합니다.  다음 코드 줄을 이벤트 프로시저에 배치합니다.  
  
    ```vb  
    MessageBox.Show("Goodbye!")  
    ```  
  
    ```csharp  
    MessageBox.Show("Goodbye!");  
    ```  
  
4.  **빌드** 메뉴에서 **BaseForm 라이브러리 빌드**를 선택하여 클래스 라이브러리를 빌드합니다.  
  
     라이브러리가 빌드되고 나면 방금 만든 폼에서 상속하는 새 프로젝트를 만들 수 있습니다.  
  
#### 기본 폼에서 상속하는 폼을 포함하는 프로젝트를 만들려면  
  
1.  **파일** 메뉴에서 **추가**, **새 프로젝트**를 차례로 선택하여 **새 프로젝트 추가** 대화 상자를 엽니다.  
  
2.  `InheritanceTest`라는 Windows Forms 응용 프로그램을 만듭니다.  
  
#### 상속된 폼을 추가하려면  
  
1.  **솔루션 탐색기**에서 **InheritanceTest** 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가**를 선택한 다음 **새 항목**을 선택합니다.  
  
2.  **새 항목 추가** 대화 상자에서 **Windows Forms** 범주\(범주 목록이 있는 경우\)를 선택한 다음 **상속된 폼** 템플릿을 선택합니다.  
  
3.  기본 이름인 `Form2`를 그대로 두고 **추가**를 클릭합니다.  
  
4.  **상속 선택** 대화 상자에서 **BaseFormLibrary** 프로젝트의 **Form1**을 상속할 폼으로 선택하고 **확인**을 클릭합니다.  
  
     이렇게 하면 **InheritanceTest** 프로젝트에 **BaseFormLibrary**의 폼에서 파생되는 폼이 만들어집니다.  
  
5.  디자이너에서 상속된 폼\(**Form2**\)을 두 번 클릭하여 엽니다\(아직 열지 않은 경우\).  
  
     디자이너에서 상속된 단추의 위쪽 모퉁이에는 상속되었음을 나타내는 기호\(![VisualBasicInheritanceSymbol 스크린 샷](../../../../docs/framework/winforms/advanced/media/vbinheritanceglyph.png "vbInheritanceGlyph")\)가 있습니다.  
  
6.  **Say Hello** 단추를 선택하고 크기 조정 핸들을 관찰합니다.  이 단추는 protected이므로 상속자가 이동하고, 크기를 조정하고, 캡션을 변경하고, 기타 수정 작업을 할 수 있습니다.  
  
7.  private **Say Goodbye** 단추를 선택하고 크기 조정 핸들이 없는 것을 확인합니다.  또한 **속성** 창에서 이 단추의 속성은 회색으로 표시되어 수정할 수 없음을 나타냅니다.  
  
8.  [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]을 사용하는 경우  
  
    1.  **솔루션 탐색기**에서 **InheritanceTest** 프로젝트의 **Form1**을 마우스 오른쪽 단추로 클릭하고 **삭제**를 선택합니다.  표시되는 메시지 상자에서 **확인**을 클릭하여 삭제를 확인합니다.  
  
    2.  Program.cs 파일을 열고 `Application.Run(new Form1());` 줄을 `Application.Run(new Form2());`으로 변경합니다.  
  
9. **솔루션 탐색기**에서 **InheritanceTest** 프로젝트를 마우스 오른쪽 단추로 클릭하고 **시작 프로젝트로 설정**을 선택합니다.  
  
10. **솔루션 탐색기**에서 **InheritanceTest** 프로젝트를 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.  
  
11. **InheritanceTest** 속성 페이지에서 **시작 개체**를 상속된 폼\(**Form2**\)으로 설정합니다.  
  
12. F5 키를 눌러 응용 프로그램을 실행하고 상속된 폼의 동작을 관찰합니다.  
  
## 다음 단계  
 사용자 정의 컨트롤의 상속도 거의 동일한 방식으로 작동합니다.  새 클래스 라이브러리 프로젝트를 열고 사용자 정의 컨트롤을 추가합니다.  구성 요소 컨트롤을 배치하고 프로젝트를 컴파일합니다.  다른 새 클래스 라이브러리 프로젝트를 열고 컴파일된 클래스 라이브러리에 대한 참조를 추가합니다.  또한 **새 항목 추가** 대화 상자를 통해 상속된 컨트롤을 프로젝트에 추가하고 **상속 선택**을 사용해 봅니다.  사용자 정의 컨트롤을 추가하고 `Inherits`\([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]에서는 `:`\) 문을 변경합니다.  자세한 내용은 [방법: Windows Forms 상속](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md)을 참조하세요.  
  
## 참고 항목  
 [방법: Windows Forms 상속](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md)   
 [Windows Forms 시각적 상속](../../../../docs/framework/winforms/advanced/windows-forms-visual-inheritance.md)   
 [Windows Forms](../../../../docs/framework/winforms/index.md)