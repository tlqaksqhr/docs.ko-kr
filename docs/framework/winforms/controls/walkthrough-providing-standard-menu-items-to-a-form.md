---
title: "연습: 폼에 표준 메뉴 항목 제공 | Microsoft Docs"
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
  - "메뉴 항목, 표준"
  - "StatusStrip 컨트롤[Windows Forms]"
  - "도구 모음[Windows Forms], 연습"
  - "ToolStrip 컨트롤[Windows Forms]"
ms.assetid: dac37d98-589e-4d6d-9673-6437e8943122
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# 연습: 폼에 표준 메뉴 항목 제공
<xref:System.Windows.Forms.MenuStrip> 컨트롤을 사용하여 폼에 표준 메뉴를 제공할 수 있습니다.  
  
 이 연습에서는 <xref:System.Windows.Forms.MenuStrip> 컨트롤을 사용하여 표준 메뉴를 만드는 방법을 보여 줍니다.  또한 이 폼은 사용자가 메뉴 항목을 선택할 때 반응합니다.  이 연습에서는 다음과 같은 작업을 설명합니다.  
  
-   Windows Forms 프로젝트 만들기  
  
-   표준 메뉴 만들기  
  
-   <xref:System.Windows.Forms.StatusStrip> 컨트롤 만들기  
  
-   메뉴 항목 선택 처리  
  
 이 연습을 마치면 <xref:System.Windows.Forms.StatusStrip> 컨트롤에 메뉴 항목 선택을 표시하는 표준 메뉴를 가진 폼이 완성됩니다.  
  
 이 항목의 코드를 단일 목록으로 복사하려면 [방법: 폼에 표준 메뉴 항목 제공](../../../../docs/framework/winforms/controls/how-to-provide-standard-menu-items-to-a-form.md)을 참조하십시오.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음과 같은 요건이 필요합니다.  
  
-   [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]가 설치되어 있는 컴퓨터에서 Windows Forms 응용 프로그램 프로젝트를 만들고 실행할 수 있는 충분한 권한이 있어야 합니다.  
  
## 프로젝트 만들기  
 첫 번째 단계는 프로젝트를 만들고 폼을 설정하는 것입니다.  
  
#### 프로젝트를 만들려면  
  
1.  StandardMenuForm이라는 Windows 응용 프로그램 프로젝트를 만듭니다.  
  
     자세한 내용은 [How to: Create a Windows Application Project](http://msdn.microsoft.com/ko-kr/b2f93fed-c635-4705-8d0e-cf079a264efa)를 참조하십시오.  
  
2.  Windows Forms 디자이너에서 폼을 선택합니다.  
  
## 표준 메뉴 만들기  
 Windows Forms 디자이너에서는 자동으로 <xref:System.Windows.Forms.MenuStrip> 컨트롤을 표준 메뉴 항목으로 채울 수 있습니다.  
  
#### 표준 메뉴를 만들려면  
  
1.  **도구 상자**에서 <xref:System.Windows.Forms.MenuStrip> 컨트롤을 폼으로 끌어 옵니다.  
  
2.  <xref:System.Windows.Forms.MenuStrip> 컨트롤의 스마트 태그 문자 모양\(![스마트 태그 문자 모양](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.png "VS\_WinFormSmtTagGlyph")\)을 클릭한 다음 **표준 항목 삽입**을 선택합니다.  
  
     <xref:System.Windows.Forms.MenuStrip> 컨트롤이 표준 메뉴 항목으로 채워집니다.  
  
3.  **파일** 메뉴 항목을 클릭하여 기본 메뉴 항목과 해당 아이콘을 확인합니다.  
  
## StatusStrip 컨트롤 만들기  
 <xref:System.Windows.Forms.StatusStrip> 컨트롤을 사용하여 Windows Forms 응용 프로그램의 상태를 표시합니다.  이 예제에서는 사용자가 선택한 메뉴 항목이 <xref:System.Windows.Forms.StatusStrip> 컨트롤에 표시됩니다.  
  
#### StatusStrip 컨트롤을 만들려면  
  
1.  **도구 상자**에서 <xref:System.Windows.Forms.StatusStrip> 컨트롤을 폼으로 끌어 옵니다.  
  
     <xref:System.Windows.Forms.StatusStrip> 컨트롤은 자동으로 폼 아래쪽에 도킹합니다.  
  
2.  <xref:System.Windows.Forms.StatusStrip> 컨트롤의 드롭다운 단추를 클릭하고 **StatusLabel**을 선택하여 <xref:System.Windows.Forms.ToolStripStatusLabel> 컨트롤을 <xref:System.Windows.Forms.StatusStrip> 컨트롤에 추가합니다.  
  
## 항목 선택 처리  
 사용자가 메뉴 항목을 선택할 때 반응할 <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> 이벤트를 처리합니다.  
  
#### 항목 선택을 처리하려면  
  
1.  표준 메뉴 만들기 단원에서 만든 **파일** 메뉴 항목을 클릭합니다.  
  
2.  **속성** 창에서 **이벤트**를 클릭합니다.  
  
3.  <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> 이벤트를 두 번 클릭합니다.  
  
     Windows Forms 디자이너가 <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> 이벤트의 이벤트 처리기를 생성합니다.  
  
4.  다음 코드를 이벤트 처리기에 삽입합니다.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#3)]  
  
5.  `UpdateStatus` 유틸리티 메서드 정의를 폼에 삽입합니다.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#2)]  
  
## 검사점  
  
#### 폼을 테스트하려면  
  
1.  F5 키를 눌러 폼을 컴파일하고 실행합니다.  
  
2.  **파일** 메뉴 항목을 클릭하여 메뉴를 엽니다.  
  
3.  **파일** 메뉴에서 한 항목을 클릭하여 선택합니다.  
  
     <xref:System.Windows.Forms.StatusStrip> 컨트롤에 선택한 항목이 표시됩니다.  
  
## 다음 단계  
 이 연습에서는 표준 메뉴를 가진 폼을 만들었습니다.  <xref:System.Windows.Forms.ToolStrip> 패밀리 컨트롤을 다음과 같은 여러 용도로 사용할 수 있습니다.  
  
-   <xref:System.Windows.Forms.ContextMenuStrip>을 사용하여 컨트롤의 바로 가기 메뉴를 만듭니다.  자세한 내용은 [ContextMenu 구성 요소 개요](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md)를 참조하십시오.  
  
-   <xref:System.Windows.Forms.ToolStrip> 컨트롤이 도킹된 MDI\(다중 문서 인터페이스\) 폼을 만듭니다.  자세한 내용은 [연습: 메뉴 병합 및 ToolStrip 컨트롤을 사용하여 MDI 폼 만들기](../../../../docs/framework/winforms/controls/walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md)를 참조하십시오.  
  
-   전문적인 모양을 갖춘 <xref:System.Windows.Forms.ToolStrip> 컨트롤을 만들 수 있습니다.  자세한 내용은 [방법: 응용 프로그램에 대한 ToolStrip 렌더러 설정](../../../../docs/framework/winforms/controls/how-to-set-the-toolstrip-renderer-for-an-application.md)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ToolStrip>   
 <xref:System.Windows.Forms.StatusStrip>   
 [MenuStrip 컨트롤](../../../../docs/framework/winforms/controls/menustrip-control-windows-forms.md)