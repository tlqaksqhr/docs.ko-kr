---
title: "연습: 전문적인 스타일의 ToolStrip 컨트롤 만들기 | Microsoft Docs"
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
  - "도구 모음[Windows Forms], 연습"
  - "ToolStrip 컨트롤[Windows Forms], 전문적인 스타일의 컨트롤 만들기"
  - "ToolStripProfessionalRenderer 클래스[Windows Forms]"
  - "ToolStripRenderer 클래스[Windows Forms]"
ms.assetid: b52339ae-f1d3-494e-996e-eb455614098a
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 연습: 전문적인 스타일의 ToolStrip 컨트롤 만들기
<xref:System.Windows.Forms.ToolStripProfessionalRenderer> 형식에서 파생되는 고유 클래스를 작성하여 응용 프로그램의 <xref:System.Windows.Forms.ToolStrip> 컨트롤에 전문적인 모양과 동작을 지정할 수 있습니다.  
  
 이 연습에서는 <xref:System.Windows.Forms.ToolStrip> 컨트롤을 사용하여 Microsoft® Outlook®의 **탐색 창**과 비슷한 복합 컨트롤을 만드는 방법을 보여 줍니다.  이 연습에서는 다음과 같은 작업을 설명합니다.  
  
-   Windows 컨트롤 라이브러리 프로젝트 만들기  
  
-   StackView 컨트롤 디자인  
  
-   사용자 지정 렌더러 구현  
  
 작업을 마치면 Microsoft Office® XP 컨트롤의 전문적인 모양을 갖춘 재사용 가능한 사용자 지정 클라이언트 컨트롤이 만들어집니다.  
  
 이 항목의 코드를 단일 목록으로 복사하려면 [방법: 전문적인 스타일의 ToolStrip 컨트롤 만들기](../../../../docs/framework/winforms/controls/how-to-create-a-professionally-styled-toolstrip-control.md)를 참조하십시오.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음과 같은 요건이 필요합니다.  
  
-   [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]가 설치되어 있는 컴퓨터에서 Windows Forms 응용 프로그램 프로젝트를 만들고 실행할 수 있는 충분한 권한이 있어야 합니다.  
  
## Windows 컨트롤 라이브러리 프로젝트 만들기  
 첫 번째 단계에서는 컨트롤 라이브러리 프로젝트를 만듭니다.  
  
#### 컨트롤 라이브러리 프로젝트를 만들려면  
  
1.  이름이 `StackViewLibrary`인 새 Windows 컨트롤 라이브러리 프로젝트를 만듭니다.  
  
2.  **솔루션 탐색기**에서 선택한 언어에 따라 이름이 "UserControl1.cs" 또는 "UserControl1.vb"인 소스 파일을 삭제하여 프로젝트의 기본 컨트롤을 삭제합니다.  
  
     자세한 내용은 [NIB:How to: Remove, Delete, and Exclude Items](http://msdn.microsoft.com/ko-kr/6dffdc86-29c8-4eff-bcd8-e3a0dd9e9a73)를 참조하십시오.  
  
3.  **StackViewLibrary** 프로젝트에 새 <xref:System.Windows.Forms.UserControl> 항목을 추가합니다.  새 소스 파일에 `StackView`라는 기본 이름을 지정합니다.  
  
## StackView 컨트롤 디자인  
 `StackView` 컨트롤은 자식 <xref:System.Windows.Forms.ToolStrip> 컨트롤 하나를 갖는 복합 컨트롤입니다.  복합 컨트롤에 대한 자세한 내용은 [사용자 지정 컨트롤의 종류](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)를 참조하십시오.  
  
#### StackView 컨트롤을 디자인하려면  
  
1.  **도구 상자**에서 <xref:System.Windows.Forms.ToolStrip> 컨트롤을 디자인 화면으로 끌어 옵니다.  
  
2.  **속성** 창에서 다음 표에 따라 <xref:System.Windows.Forms.ToolStrip> 컨트롤의 속성을 설정합니다.  
  
    |Property|값|  
    |--------------|-------|  
    |Name|`stackStrip`|  
    |CanOverflow|`false`|  
    |Dock|<xref:System.Windows.Forms.DockStyle>|  
    |글꼴|`Tahoma, 10pt, style=Bold`|  
    |GripStyle|<xref:System.Windows.Forms.ToolStripGripStyle>|  
    |LayoutStyle|<xref:System.Windows.Forms.ToolStripLayoutStyle>|  
    |안쪽 여백|`0, 7, 0, 0`|  
    |RenderMode|<xref:System.Windows.Forms.ToolStripRenderMode>|  
  
3.  Windows Forms 디자이너에서 <xref:System.Windows.Forms.ToolStrip> 컨트롤의 **추가** 단추를 클릭하고 `stackStrip` 컨트롤에 <xref:System.Windows.Forms.ToolStripButton>을 추가합니다.  
  
4.  **속성** 창에서 다음 표에 따라 <xref:System.Windows.Forms.ToolStripButton> 컨트롤의 속성을 설정합니다.  
  
    |Property|값|  
    |--------------|-------|  
    |Name|`mailStackButton`|  
    |CheckOnClick|true|  
    |CheckState|<xref:System.Windows.Forms.CheckState>|  
    |DisplayStyle|<xref:System.Windows.Forms.ToolStripItemDisplayStyle>|  
    |ImageAlign|<xref:System.Drawing.ContentAlignment>|  
    |ImageScaling|<xref:System.Windows.Forms.ToolStripItemImageScaling>|  
    |ImageTransparentColor|`238, 238, 238`|  
    |Margin|`0, 0, 0, 0`|  
    |안쪽 여백|`3, 3, 3, 3`|  
    |Text|Mail|  
    |TextAlign|<xref:System.Drawing.ContentAlignment>|  
  
5.  3개의 추가 <xref:System.Windows.Forms.ToolStripButton> 컨트롤에 대해 7단계를 반복합니다.  
  
     `calendarStackButton`, `contactsStackButton` 및 `tasksStackButton` 컨트롤의 이름을 지정합니다.  <xref:System.Windows.Forms.Control.Text%2A> 속성 값을 각각 Calendar, Contacts 및 Tasks로 설정합니다.  
  
## 이벤트 처리  
 `StackView` 컨트롤이 제대로 동작하도록 만들려면 두 가지 이벤트가 중요합니다.  <xref:System.Windows.Forms.UserControl.Load> 이벤트를 처리하여 컨트롤이 올바로 배치되도록 합니다.  각 <xref:System.Windows.Forms.ToolStripButton>의 <xref:System.Windows.Forms.ToolStripItem.Click> 이벤트를 처리하여 `StackView` 컨트롤 상태 동작을 <xref:System.Windows.Forms.RadioButton> 컨트롤과 유사하게 만듭니다.  
  
#### 이벤트를 처리하려면  
  
1.  Windows Forms 디자이너에서 `StackView` 컨트롤을 선택합니다.  
  
2.  **속성** 창에서 **이벤트**를 클릭합니다.  
  
3.  Load 이벤트를 두 번 클릭하여 `StackView_Load` 이벤트 처리기를 생성합니다.  
  
4.  `StackView_Load` 이벤트 처리기에서 다음 코드를 복사하여 붙여넣습니다.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#3)]  
  
5.  Windows Forms 디자이너에서 `mailStackButton` 컨트롤을 선택합니다.  
  
6.  **속성** 창에서 **이벤트**를 클릭합니다.  
  
7.  Click 이벤트를 두 번 클릭합니다.  
  
     Windows Forms 디자이너에서 `mailStackButton_Click` 이벤트 처리기가 생성됩니다.  
  
8.  `mailStackButton_Click` 이벤트 처리기 이름을 `stackButton_Click`으로 바꿉니다.  
  
     자세한 내용은 [How to: Rename an Identifier \(Visual Basic\)](http://msdn.microsoft.com/ko-kr/e5a5edf8-3dba-4119-81f4-fc2aba180e0c)를 참조하십시오.  
  
9. `stackButton_Click` 이벤트 처리기에 다음 코드를 삽입합니다.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#4)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#4)]  
  
10. Windows Forms 디자이너에서 `calendarStackButton` 컨트롤을 선택합니다.  
  
11. **속성** 창에서 `stackButton_Click` 이벤트 처리기에 대해 Click 이벤트를 설정합니다.  
  
12. `contactsStackButton` 및 `tasksStackButton` 컨트롤에 대해 10단계와 11단계를 반복합니다.  
  
## 아이콘 정의  
 각 `StackView` 단추에는 연결된 아이콘이 있습니다.  편의를 위해 각 아이콘은 Base64로 인코딩된 문자열로 표시되며 이 문자열에서 <xref:System.Drawing.Bitmap>이 만들어지기 전에 문자열이 deserialize됩니다.  프로덕션 환경에서 비트맵 데이터를 리소스로 저장하면 해당 아이콘이 Windows Forms 디자이너에 표시됩니다.  자세한 내용은 [How to: Add Background Images to Windows Forms](http://msdn.microsoft.com/ko-kr/7a509ba2-055c-4ae6-b88a-54625c6d9aff)를 참조하십시오.  
  
#### 아이콘을 정의하려면  
  
1.  코드 편집기에서 `StackView` 클래스 정의에 다음 코드를 삽입합니다.  이 코드에서는 <xref:System.Windows.Forms.ToolStripButton> 아이콘에 대한 비트맵을 초기화합니다.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#2)]  
  
2.  `InitializeImages` 메서드에 대한 호출을 `StackView` 클래스 생성자에 추가합니다.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#5)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#5)]  
  
## 사용자 지정 렌더러 구현  
 <xref:System.Windows.Forms.ToolStripRenderer> 클래스에서 파생되는 클래스를 구현하여 `StackView` 컨트롤의 요소를 대부분 사용자 지정할 수 있습니다.  이 절차에서는 그립을 사용자 지정하고 <xref:System.Windows.Forms.ToolStripButton> 컨트롤의 그라데이션 배경을 그리는 <xref:System.Windows.Forms.ToolStripProfessionalRenderer> 클래스를 구현합니다.  
  
#### 사용자 지정 렌더러를 구현하려면  
  
1.  `StackView` 컨트롤 정의에 다음 코드를 삽입합니다.  
  
     이 코드는 <xref:System.Windows.Forms.ToolStripRenderer.RenderGrip>, <xref:System.Windows.Forms.ToolStripRenderer.RenderToolStripBorder> 및 <xref:System.Windows.Forms.ToolStripRenderer.RenderButtonBackground> 메서드를 재정의하여 사용자 지정 모양을 만드는 `StackRenderer` 클래스에 대한 정의입니다.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#10)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#10)]  
  
2.  `StackView` 컨트롤의 생성자에서 `StackRenderer` 클래스의 새 인스턴스를 만들고 이 인스턴스를 `stackStrip` 컨트롤의 <xref:System.Windows.Forms.ToolStrip.Renderer%2A> 속성에 할당합니다.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#5)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#5)]  
  
## StackView 컨트롤 테스트  
 `StackView` 컨트롤은 <xref:System.Windows.Forms.UserControl> 클래스에서 파생됩니다.  따라서 **UserControl Test Container**를 사용하여 컨트롤을 테스트할 수 있습니다.  자세한 내용은 [방법: UserControl의 런타임 동작 테스트](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md)를 참조하십시오.  
  
#### StackView 컨트롤을 테스트하려면  
  
1.  F5 키를 눌러 프로젝트를 빌드하고 **UserControl Test Container**를 시작합니다.  
  
2.  포인터를 `StackView` 컨트롤의 단추로 이동한 다음 단추를 클릭하여 선택한 상태의 모양을 확인합니다.  
  
## 다음 단계  
 이 연습에서는 Office XP 컨트롤의 전문적인 모양을 갖춘 재사용 가능한 사용자 지정 클라이언트 컨트롤을 만들었습니다.  <xref:System.Windows.Forms.ToolStrip> 패밀리 컨트롤을 다음과 같은 여러 용도로 사용할 수 있습니다.  
  
-   <xref:System.Windows.Forms.ContextMenuStrip>을 사용하여 컨트롤의 바로 가기 메뉴를 만듭니다.  자세한 내용은 [ContextMenu 구성 요소 개요](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md)를 참조하십시오.  
  
-   자동으로 채워지는 표준 메뉴를 가진 폼을 만듭니다.  자세한 내용은 [연습: 폼에 표준 메뉴 항목 제공](../../../../docs/framework/winforms/controls/walkthrough-providing-standard-menu-items-to-a-form.md)을 참조하십시오.  
  
-   <xref:System.Windows.Forms.ToolStrip> 컨트롤이 도킹된 MDI\(다중 문서 인터페이스\) 폼을 만듭니다.  자세한 내용은 [방법: 메뉴 병합 및 ToolStrip 컨트롤을 사용하여 MDI 폼 만들기](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md)를 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ToolStrip>   
 <xref:System.Windows.Forms.StatusStrip>   
 [ToolStrip 컨트롤](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)   
 [방법: 폼에 표준 메뉴 항목 제공](../../../../docs/framework/winforms/controls/how-to-provide-standard-menu-items-to-a-form.md)