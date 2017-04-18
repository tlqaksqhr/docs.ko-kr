---
title: "기능별 Windows Forms 컨트롤 | Microsoft Docs"
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
  - "컨트롤[Windows Forms], 기능별"
  - "Windows Forms 컨트롤, 목록"
  - "Windows Forms, 기능별 컨트롤"
ms.assetid: 5e65a6c3-5d6f-480d-beb8-b28f865f07e3
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# 기능별 Windows Forms 컨트롤
Windows Forms에서는 여러 가지 기능을 수행하는 컨트롤과 구성 요소를 제공합니다.  다음 표에서는 일반적인 기능에 따라 Windows Forms 컨트롤 및 구성 요소를 나열합니다.  또한 같은 기능을 수행하는 컨트롤이 여러 개 있는 경우 대체된 컨트롤에 대한 설명과 함께 권장 컨트롤을 나열합니다.  이후에 나오는 별개의 표에서는 대체된 컨트롤이 권장되는 대체 컨트롤과 함께 나열됩니다.  
  
> [!NOTE]
>  다음 표에서는 Windows Forms에서 사용할 수 있는 컨트롤이나 구성 요소의 일부만 보여 줍니다. 전체 목록을 보려면 [Windows Forms에 사용할 수 있는 컨트롤](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)을 참조하십시오.  
  
## 기능별 권장 컨트롤 및 구성 요소  
  
|Function|컨트롤|설명|  
|--------------|---------|--------|  
|데이터 표시|<xref:System.Windows.Forms.DataGridView> 컨트롤|<xref:System.Windows.Forms.DataGridView> 컨트롤은 사용자 지정 가능한 테이블을 제공하여 데이터를 표시합니다.  <xref:System.Windows.Forms.DataGridView> 클래스는 셀, 행, 열 및 테두리의 사용자 지정 기능을 제공합니다. **Note:**  <xref:System.Windows.Forms.DataGridView> 컨트롤은 <xref:System.Windows.Forms.DataGrid> 컨트롤에는 없는 다양한 기본 기능 및 고급 기능을 제공합니다.  자세한 내용은 [Windows Forms DataGridView 컨트롤과 DataGrid 컨트롤의 차이점](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)를 참조하십시오.|  
|데이터 바인딩 및 탐색|<xref:System.Windows.Forms.BindingSource> 구성 요소|현재 위치 관리, 변경 알림 및 기타 서비스를 제공하여 폼의 컨트롤을 데이터에 바인딩하는 과정을 단순화합니다.|  
||<xref:System.Windows.Forms.BindingNavigator> 컨트롤|폼에서 데이터를 탐색하고 조작하는 데 필요한 기능을 제공하는 도구 모음 형식의 인터페이스를 제공합니다.|  
|텍스트 편집|<xref:System.Windows.Forms.TextBox> 컨트롤|디자인 타임에 입력된 텍스트로서, 사용자가 런타임에 편집하거나 프로그래밍 방식으로 변경할 수 있는 텍스트를 표시합니다.|  
||<xref:System.Windows.Forms.RichTextBox> 컨트롤|텍스트를 일반 텍스트에 서식이 지정된 형태 또는 RTF\(서식있는 텍스트\)로 표시합니다.|  
||<xref:System.Windows.Forms.MaskedTextBox> 컨트롤|사용자 입력의 형식을 제한합니다.|  
|정보 표시\(읽기 전용\)|<xref:System.Windows.Forms.Label> 컨트롤|사용자가 직접 편집할 수 없는 텍스트를 표시합니다.|  
||<xref:System.Windows.Forms.LinkLabel> 컨트롤|텍스트를 웹 스타일 링크로 표시하고 사용자가 이 특수 텍스트를 클릭하면 이벤트가 발생합니다.  텍스트는 보통 다른 창 또는 웹 사이트에 대한 링크입니다.|  
||<xref:System.Windows.Forms.StatusStrip> 컨트롤|보통 부모 폼의 맨 아래에 있으면서 프레임 영역을 사용하여 응용 프로그램의 현재 상태에 대한 정보를 표시합니다.|  
||<xref:System.Windows.Forms.ProgressBar> 컨트롤|작업의 현재 진행률을 사용자에게 표시합니다.|  
|웹 페이지 표시|<xref:System.Windows.Forms.WebBrowser> 컨트롤|사용자가 폼 내에서 웹 페이지를 탐색할 수 있도록 합니다.|  
|목록에서 선택|<xref:System.Windows.Forms.CheckedListBox> 컨트롤|각 항목에 확인란이 있는, 스크롤 가능한 목록을 표시합니다.|  
||<xref:System.Windows.Forms.ComboBox> 컨트롤|항목의 드롭다운 목록을 표시합니다.|  
||<xref:System.Windows.Forms.DomainUpDown> 컨트롤|사용자가 위로 이동 및 아래로 이동 단추를 사용하여 스크롤할 수 있는 텍스트 항목 목록을 표시합니다.|  
||<xref:System.Windows.Forms.ListBox> 컨트롤|텍스트 목록과 그래픽 항목\(아이콘\)을 표시합니다.|  
||<xref:System.Windows.Forms.ListView> 컨트롤|네 가지의 서로 다른 뷰 중 하나를 사용하여 항목을 표시합니다.  뷰에는 텍스트만 포함된 뷰, 작은 아이콘을 가진 텍스트 뷰, 큰 아이콘을 가진 텍스트 뷰 및 상세 뷰가 있습니다.|  
||<xref:System.Windows.Forms.NumericUpDown> 컨트롤|사용자가 위로 이동 및 아래로 이동 단추를 사용하여 스크롤할 수 있는 숫자 목록을 표시합니다.|  
||<xref:System.Windows.Forms.TreeView> 컨트롤|선택 확인란 또는 아이콘을 가진 텍스트로 구성된 노드 개체의 계층 구조 컬렉션을 표시합니다.|  
|그래픽 표시|<xref:System.Windows.Forms.PictureBox> 컨트롤|프레임에 비트맵 및 아이콘과 같은 그래픽 파일을 표시합니다.|  
|그래픽 저장소|<xref:System.Windows.Forms.ImageList> 컨트롤|이미지 저장소 역할을 합니다.  <xref:System.Windows.Forms.ImageList> 컨트롤과 이 컨트롤에 포함된 이미지는 다른 응용 프로그램에 다시 사용될 수 있습니다.|  
|값 설정|<xref:System.Windows.Forms.CheckBox> 컨트롤|텍스트에 확인란 및 레이블을 표시합니다.  보통 옵션을 설정할 때 사용합니다.|  
||<xref:System.Windows.Forms.CheckedListBox> 컨트롤|각 항목에 확인란이 있는, 스크롤 가능한 목록을 표시합니다.|  
||<xref:System.Windows.Forms.RadioButton> 컨트롤|켜거나 끌 수 있는 단추를 표시합니다.|  
||<xref:System.Windows.Forms.TrackBar> 컨트롤|눈금을 따라 "엄지 단추"를 이동하여 눈금의 값을 설정할 수 있습니다.|  
|날짜 설정|<xref:System.Windows.Forms.DateTimePicker> 컨트롤|사용자가 날짜 또는 시간을 선택할 수 있는 그래픽 달력을 표시합니다.|  
||<xref:System.Windows.Forms.MonthCalendar> 컨트롤|사용자가 날짜 범위를 선택할 수 있는 그래픽 달력을 표시합니다.|  
|대화 상자|<xref:System.Windows.Forms.ColorDialog> 컨트롤|사용자가 인터페이스 요소의 색을 설정할 수 있는 색 선택 대화 상자를 표시합니다.|  
||<xref:System.Windows.Forms.FontDialog> 컨트롤|사용자가 글꼴 및 해당 특성을 설정할 수 있는 대화 상자를 표시합니다.|  
||<xref:System.Windows.Forms.OpenFileDialog> 컨트롤|사용자가 파일을 탐색하고 선택할 수 있는 대화 상자를 표시합니다.|  
||<xref:System.Windows.Forms.PrintDialog> 컨트롤|사용자가 프린터를 선택하고 해당 특성을 설정할 수 있는 대화 상자를 표시합니다.|  
||<xref:System.Windows.Forms.PrintPreviewDialog> 컨트롤|컨트롤 <xref:System.Drawing.Printing.PrintDocument> 구성 요소의 인쇄 후 모양을 보여 주는 대화 상자를 표시합니다.|  
||<xref:System.Windows.Forms.FolderBrowserDialog> 컨트롤|사용자가 폴더를 찾아보고, 만들고, 선택할 수 있는 대화 상자를 표시합니다.|  
||<xref:System.Windows.Forms.SaveFileDialog> 컨트롤|사용자가 파일을 저장할 수 있는 대화 상자를 표시합니다.|  
|메뉴 컨트롤|<xref:System.Windows.Forms.MenuStrip> 컨트롤|사용자 지정 메뉴를 만듭니다. **Note:**  <xref:System.Windows.Forms.MenuStrip>은 <xref:System.Windows.Forms.MainMenu> 컨트롤을 바꾸는 데 사용합니다.|  
||<xref:System.Windows.Forms.ContextMenuStrip> 컨트롤|사용자 지정 상황에 맞는 메뉴를 만듭니다. **Note:**  <xref:System.Windows.Forms.ContextMenuStrip>은 <xref:System.Windows.Forms.ContextMenu> 컨트롤을 바꾸는 데 사용합니다.|  
|명령|<xref:System.Windows.Forms.Button> 컨트롤|프로세스를 시작, 중지 또는 중단합니다.|  
||<xref:System.Windows.Forms.LinkLabel> 컨트롤|텍스트를 웹 스타일 링크로 표시하고 사용자가 이 특수 텍스트를 클릭하면 이벤트가 발생합니다.  텍스트는 보통 다른 창 또는 웹 사이트에 대한 링크입니다.|  
||<xref:System.Windows.Forms.NotifyIcon> 컨트롤|작업 표시줄에 있는 상태 알림 영역에 백그라운드로 실행되는 응용 프로그램을 나타내는 아이콘을 표시합니다.|  
||<xref:System.Windows.Forms.ToolStrip> 컨트롤|테마를 포함하거나 포함하지 않고 오버플로 및 런타임 항목 다시 정렬을 지원하는 Microsoft Windows XP, Microsoft Office, Microsoft Internet Explorer 또는 사용자 지정 모양과 느낌을 가진 도구 모음을 만듭니다. **Note:**  <xref:System.Windows.Forms.ToolStrip> 컨트롤은 <xref:System.Windows.Forms.ToolBar> 컨트롤을 바꾸는 데 사용합니다.|  
|사용자 도움말|<xref:System.Windows.Forms.HelpProvider> 구성 요소|컨트롤에 대한 팝업 또는 온라인을 제공합니다.|  
||<xref:System.Windows.Forms.ToolTip> 구성 요소|사용자가 컨트롤 위에 포인터를 놓았을 때 컨트롤의 용도에 대한 간략한 설명을 표시하는 팝업 창을 제공합니다.|  
|기타 컨트롤의 그룹화|<xref:System.Windows.Forms.Panel> 컨트롤|레이블이 없으면서 스크롤이 가능한 프레임에 있는 컨트롤 집합을 그룹화합니다.|  
||<xref:System.Windows.Forms.GroupBox> 컨트롤|레이블이 있으면서 스크롤이 불가능한 프레임에 있는 컨트롤\(예: 라디오 단추\) 집합을 그룹화합니다.|  
||<xref:System.Windows.Forms.TabControl> 컨트롤|그룹화된 개체를 효율적으로 구성 및 액세스할 수 있도록 탭으로 구성된 페이지를 제공합니다.|  
||<xref:System.Windows.Forms.SplitContainer> 컨트롤|이동 가능한 막대로 구분된 두 개의 패널을 제공합니다. **Note:**  <xref:System.Windows.Forms.SplitContainer> 컨트롤은 <xref:System.Windows.Forms.Splitter> 컨트롤을 바꾸는 데 사용합니다.|  
||<xref:System.Windows.Forms.TableLayoutPanel> 컨트롤|행과 열로 구성된 표로 내용을 동적으로 레이아웃하는 패널을 나타냅니다.|  
||<xref:System.Windows.Forms.FlowLayoutPanel> 컨트롤|내용을 동적으로 가로 또는 세로로 레이아웃하는 패널을 나타냅니다.|  
|오디오|<xref:System.Media.SoundPlayer> 컨트롤|.wav 형식의 사운드 파일을 재생합니다.  소리는 비동기적으로 로드되거나 재생될 수 있습니다.|  
  
## 기능별 대체 컨트롤 및 구성 요소  
  
|Function|대체된 컨트롤|권장 컨트롤|  
|--------------|-------------|------------|  
|데이터 표시|<xref:System.Windows.Forms.DataGrid>|<xref:System.Windows.Forms.DataGridView>|  
|정보 표시\(읽기 전용 컨트롤\)|<xref:System.Windows.Forms.StatusBar>|<xref:System.Windows.Forms.StatusStrip>|  
|메뉴 컨트롤|<xref:System.Windows.Forms.ContextMenu>|<xref:System.Windows.Forms.ContextMenuStrip>|  
||<xref:System.Windows.Forms.MainMenu>|<xref:System.Windows.Forms.MenuStrip>|  
|명령|<xref:System.Windows.Forms.ToolBar>|<xref:System.Windows.Forms.ToolStrip>|  
||<xref:System.Windows.Forms.StatusBar>|<xref:System.Windows.Forms.StatusStrip>|  
|폼 레이아웃|<xref:System.Windows.Forms.Splitter>|<xref:System.Windows.Forms.SplitContainer>|  
  
## 참고 항목  
 [Windows Forms에 사용할 수 있는 컨트롤](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)   
 [.NET Framework에서 사용자 지정 Windows Forms 컨트롤 개발](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)