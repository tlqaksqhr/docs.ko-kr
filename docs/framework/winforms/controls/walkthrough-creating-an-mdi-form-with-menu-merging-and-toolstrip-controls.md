---
title: "연습: 메뉴 병합 및 ToolStrip 컨트롤을 사용하여 MDI 폼 만들기 | Microsoft Docs"
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
  - "MDI 폼"
  - "MDI 폼, 만들기"
  - "MDI 폼, 연습"
  - "MDI, 폼 만들기"
  - "다중 문서 인터페이스 폼"
  - "도구 모음[Windows Forms]"
  - "ToolStrip 컨트롤[Windows Forms]"
  - "ToolStripPanel 컨트롤[Windows Forms]"
ms.assetid: fbab4221-74af-42d0-bbf4-3c97f7b2e544
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# 연습: 메뉴 병합 및 ToolStrip 컨트롤을 사용하여 MDI 폼 만들기
<xref:System.Windows.Forms?displayProperty=fullName> 네임스페이스는 MDI\(다중 문서 인터페이스\) 응용 프로그램을 지원하고 <xref:System.Windows.Forms.MenuStrip> 컨트롤은 메뉴 병합을 지원합니다.  MDI 폼은 <xref:System.Windows.Forms.ToolStrip> 컨트롤일 수도 있습니다.  
  
 이 연습에서는 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤을 MDI 폼과 함께 사용하는 방법을 보여 줍니다.  또한 이 폼은 자식 메뉴와의 메뉴 병합을 지원합니다.  이 연습에서는 다음과 같은 작업을 설명합니다.  
  
-   Windows Forms 프로젝트 만들기  
  
-   폼의 주 메뉴 만들기.  실제 메뉴 이름은 달라집니다.  
  
-   <xref:System.Windows.Forms.ToolStripPanel> 컨트롤을 **도구 상자**에 추가  
  
-   자식 폼 만들기  
  
-   <xref:System.Windows.Forms.ToolStripPanel> 컨트롤을 Z 순서로 정렬  
  
 연습을 마치면 메뉴 병합과 이동할 수 있는 <xref:System.Windows.Forms.ToolStrip> 컨트롤을 지원하는 MDI 폼이 완성됩니다.  
  
 이 항목의 코드를 단일 목록으로 복사하려면 [방법: 메뉴 병합 및 ToolStrip 컨트롤을 사용하여 MDI 폼 만들기](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md)를 참조하십시오.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음과 같은 요건이 필요합니다.  
  
-   [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]가 설치되어 있는 컴퓨터에서 Windows Forms 응용 프로그램 프로젝트를 만들고 실행할 수 있는 충분한 권한이 있어야 합니다.  
  
## 프로젝트 만들기  
 첫 번째 단계는 프로젝트를 만들고 폼을 설정하는 것입니다.  
  
#### 프로젝트를 만들려면  
  
1.  MdiForm이라는 Windows 응용 프로그램 프로젝트를 만듭니다.  
  
     자세한 내용은 [How to: Create a Windows Application Project](http://msdn.microsoft.com/ko-kr/b2f93fed-c635-4705-8d0e-cf079a264efa)를 참조하십시오.  
  
2.  Windows Forms 디자이너에서 폼을 선택합니다.  
  
3.  속성 창에서 <xref:System.Windows.Forms.Form.IsMdiContainer%2A> 값을 `true`로 설정합니다.  
  
## 주 메뉴 만들기  
 부모 MDI 폼에는 주 메뉴가 들어 있습니다.  주 메뉴에는 이름이 **창**인 메뉴 항목이 하나 있습니다.  **창** 메뉴 항목을 사용하여 자식 폼을 만들 수 있습니다.  자식 폼의 메뉴 항목은 주 메뉴에 병합됩니다.  
  
#### 주 메뉴를 만들려면  
  
1.  **도구 상자**에서 <xref:System.Windows.Forms.MenuStrip> 컨트롤을 폼으로 끌어 옵니다.  
  
2.  <xref:System.Windows.Forms.ToolStripMenuItem>을 <xref:System.Windows.Forms.MenuStrip> 컨트롤에 추가하고 이름을 창으로 지정합니다.  
  
3.  <xref:System.Windows.Forms.MenuStrip> 컨트롤을 선택합니다.  
  
4.  속성 창에서 <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> 속성 값을 `ToolStripMenuItem1`로 설정합니다.  
  
5.  하위 항목을 **창** 메뉴 항목에 추가하고 이 하위 항목 이름을 새로 만들기로 지정합니다.  
  
6.  속성 창에서 **이벤트**를 클릭합니다.  
  
7.  <xref:System.Windows.Forms.ToolStripItem.Click> 이벤트를 두 번 클릭합니다.  
  
     Windows Forms 디자이너가 <xref:System.Windows.Forms.ToolStripItem.Click> 이벤트의 이벤트 처리기를 생성합니다.  
  
8.  다음 코드를 이벤트 처리기에 삽입합니다.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#2)]  
  
## 도구 상자에 ToolStripPanel 컨트롤 추가  
 MDI 폼이 있는 <xref:System.Windows.Forms.MenuStrip> 컨트롤을 사용할 때는 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤이 있어야 합니다.  <xref:System.Windows.Forms.ToolStripPanel> 컨트롤을 **도구 상자**에 추가하여 Windows Forms 디자이너에서 MDI 폼을 만들어야 합니다.  
  
#### ToolStripPanel 컨트롤을 도구 상자에 추가하려면  
  
1.  **도구 상자**를 연 다음 **모든 Windows Forms** 탭을 클릭하여 사용할 수 있는 Windows Forms 컨트롤을 표시합니다.  
  
2.  마우스 오른쪽 단추를 클릭하여 바로 가기 메뉴를 열고 **항목 선택**을 선택합니다.  
  
3.  **도구 상자 항목 선택** 대화 상자에서 **Name** 열을 아래로 스크롤하여 **ToolStripPanel**을 찾습니다.  
  
4.  **ToolStripPanel** 옆의 확인란을 선택한 다음 **확인**을 클릭합니다.  
  
     <xref:System.Windows.Forms.ToolStripPanel> 컨트롤이 **도구 상자**에 나타납니다.  
  
## 자식 폼 만들기  
 이 절차에서는 고유한 <xref:System.Windows.Forms.MenuStrip> 컨트롤을 가진 별도의 자식 폼 클래스를 정의합니다.  이 폼의 메뉴 항목은 부모 폼의 메뉴 항목과 병합됩니다.  
  
#### 자식 폼을 정의하려면  
  
1.  프로젝트에 `ChildForm`이라는 새 폼을 추가합니다.  
  
     자세한 내용은 [How to: Add Windows Forms to a Project](http://msdn.microsoft.com/ko-kr/3d7bb25f-fd90-47cf-9378-fa0d764686c1)를 참조하십시오.  
  
2.  **도구 상자**에서 <xref:System.Windows.Forms.MenuStrip> 컨트롤을 자식 폼으로 끌어 옵니다.  
  
3.  <xref:System.Windows.Forms.MenuStrip> 컨트롤의 스마트 태그 문자 모양\(![스마트 태그 문자 모양](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.png "VS\_WinFormSmtTagGlyph")\)을 클릭한 다음 **항목 편집**을 선택합니다.  
  
4.  **항목 컬렉션 편집기** 대화 상자에서 이름이 ChildMenuItem인 새 <xref:System.Windows.Forms.ToolStripMenuItem>을 자식 메뉴에 추가합니다.  
  
     자세한 내용은 [ToolStrip Items Collection Editor](http://msdn.microsoft.com/ko-kr/e681f3ab-94ba-4b2b-ac64-1dfad46caa25)를 참조하십시오.  
  
## 폼 테스트  
  
#### 폼을 테스트하려면  
  
1.  F5 키를 눌러 폼을 컴파일하고 실행합니다.  
  
2.  **창** 메뉴 항목을 클릭하여 메뉴를 연 다음 **새로 만들기**를 클릭합니다.  
  
     새 자식 폼이 폼의 MDI 클라이언트 영역에 만들어집니다.  자식 폼의 메뉴가 주 메뉴와 병합됩니다.  
  
3.  자식 폼을 닫습니다.  
  
     자식 폼의 메뉴가 주 메뉴에서 제거됩니다.  
  
4.  **새로 만들기**를 몇 차례 클릭합니다.  
  
     <xref:System.Windows.Forms.MenuStrip> 컨트롤의 <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> 속성이 할당되었기 때문에 **창** 메뉴 항목 아래에 자식 폼이 자동으로 나열됩니다.  
  
## ToolStrip 지원 추가  
 이 절차에서는 네 개의 <xref:System.Windows.Forms.ToolStrip> 컨트롤을 MDI 부모 폼에 추가합니다.  각 <xref:System.Windows.Forms.ToolStrip> 컨트롤은 폼의 가장자리에 도킹되는 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤의 내부에 추가됩니다.  
  
#### ToolStrip 컨트롤을 MDI 부모 폼에 추가하려면  
  
1.  **도구 상자**에서 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤을 폼으로 끌어 옵니다.  
  
2.  <xref:System.Windows.Forms.ToolStripPanel> 컨트롤이 선택된 상태에서 **도구 상자**에 있는 <xref:System.Windows.Forms.ToolStrip> 컨트롤을 두 번 클릭합니다.  
  
     <xref:System.Windows.Forms.ToolStrip> 컨트롤이 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤 내에 만들어집니다.  
  
3.  <xref:System.Windows.Forms.ToolStripPanel> 컨트롤을 선택합니다.  
  
4.  속성 창에서 컨트롤의 <xref:System.Windows.Forms.Control.Dock%2A> 속성 값을 <xref:System.Windows.Forms.DockStyle>로 변경합니다.  
  
     <xref:System.Windows.Forms.ToolStripPanel> 컨트롤이 폼의 왼쪽, 주 메뉴 아래에 도킹됩니다.  MDI 클라이언트 영역의 크기가 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤에 맞게 조정됩니다.  
  
5.  1단계부터 4단계까지 반복합니다.  
  
     새 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤을 폼의 맨 위에 도킹합니다.  
  
     <xref:System.Windows.Forms.ToolStripPanel> 컨트롤이 주 메뉴 아래, 첫 번째 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤의 오른쪽에 도킹됩니다.  이 단계에서는 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤의 올바른 배치에 Z 순서가 중요함을 보여 줍니다.  
  
6.  두 개 이상의 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤에 대해 1\-4단계를 반복합니다.  
  
     새 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤을 폼의 오른쪽 아래에 도킹합니다.  
  
## ToolStripPanel 컨트롤을 Z 순서로 정렬  
 MDI 폼에 도킹된 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤의 위치는 Z 순서에서의 컨트롤 위치에 따라 결정됩니다.  컨트롤의 Z 순서는 문서 개요 창에서 쉽게 정렬할 수 있습니다.  
  
#### ToolStripPanel 컨트롤을 Z 순서로 정렬하려면  
  
1.  **보기** 메뉴에서 **다른 창**을 클릭한 다음 **문서 개요**를 클릭합니다.  
  
     이전 절차에서 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤을 정렬한 방법은 일반적인 방법이 아닙니다.  그 이유는 Z 순서가 올바르지 않기 때문입니다.  컨트롤의 Z 순서를 변경하려면 문서 개요 창을 사용합니다.  
  
2.  문서 개요 창에서 **ToolStripPanel4**를 선택합니다.  
  
3.  **ToolStripPanel4**가 목록의 아래쪽에 나타날 때까지 아래쪽 화살표 단추를 반복해서 클릭합니다.  
  
     **ToolStripPanel4** 컨트롤이 폼의 아래쪽, 다른 컨트롤의 아래에 도킹됩니다.  
  
4.  **ToolStripPanel2**를 선택합니다.  
  
5.  아래쪽 화살표 단추를 한 번 클릭하여 컨트롤을 목록의 세 번째에 배치합니다.  
  
     **ToolStripPanel2** 컨트롤이 폼의 위쪽, 주 메뉴 아래, 다른 컨트롤의 위에 도킹됩니다.  
  
6.  **문서 개요** 창에서 다양한 컨트롤을 선택한 다음 Z 순서의 다른 위치로 이동합니다.  Z 순서에 따른 도킹된 컨트롤의 배치 결과를 확인합니다.  Ctrl\+Z 또는 **편집** 메뉴의 **실행 취소**를 사용하여 변경 내용을 취소합니다.  
  
## 검사점  
  
#### 폼을 테스트하려면  
  
1.  F5 키를 눌러 폼을 컴파일하고 실행합니다.  
  
2.  <xref:System.Windows.Forms.ToolStrip> 컨트롤의 그립을 클릭한 다음 컨트롤을 폼의 다른 위치로 끌어 놓습니다.  
  
     <xref:System.Windows.Forms.ToolStripPanel> 컨트롤 간에 <xref:System.Windows.Forms.ToolStrip> 컨트롤을 끌어 놓을 수 있습니다.  
  
## 다음 단계  
 이 연습에서는 <xref:System.Windows.Forms.ToolStrip> 컨트롤과 메뉴 병합을 사용하여 MDI 부모 폼을 만들었습니다.  <xref:System.Windows.Forms.ToolStrip> 패밀리 컨트롤을 다음과 같은 여러 용도로 사용할 수 있습니다.  
  
-   <xref:System.Windows.Forms.ContextMenuStrip>을 사용하여 컨트롤의 바로 가기 메뉴를 만듭니다.  자세한 내용은 [ContextMenu 구성 요소 개요](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md)를 참조하십시오.  
  
-   자동으로 채워지는 표준 메뉴를 가진 폼을 만듭니다.  자세한 내용은 [연습: 폼에 표준 메뉴 항목 제공](../../../../docs/framework/winforms/controls/walkthrough-providing-standard-menu-items-to-a-form.md)을 참조하십시오.  
  
-   전문적인 모양을 갖춘 <xref:System.Windows.Forms.ToolStrip> 컨트롤을 만들 수 있습니다.  자세한 내용은 [방법: 응용 프로그램에 대한 ToolStrip 렌더러 설정](../../../../docs/framework/winforms/controls/how-to-set-the-toolstrip-renderer-for-an-application.md)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ToolStrip>   
 <xref:System.Windows.Forms.StatusStrip>   
 [방법: MDI 상위 폼 만들기](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)   
 [방법: MDI 자식 폼 만들기](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)   
 [방법: MDI 드롭다운 메뉴에 MenuStrip 삽입](../../../../docs/framework/winforms/controls/how-to-insert-a-menustrip-into-an-mdi-drop-down-menu-windows-forms.md)   
 [ToolStrip 컨트롤](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)