---
title: "기능별 Windows Forms 컨트롤"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [Windows Forms], by function
- Windows Forms, controls by function
- Windows Forms controls, list of
ms.assetid: 5e65a6c3-5d6f-480d-beb8-b28f865f07e3
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a48e1e728e3ded58b0045554a81588933027074c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="windows-forms-controls-by-function"></a>기능별 Windows Forms 컨트롤
Windows Forms 컨트롤 및 다양 한 기능을 수행 하는 구성 요소를 제공 합니다. 다음 표에서 Windows Forms 컨트롤 및 일반 함수에 따라 구성 요소를 나열합니다. 또한 컨트롤이 여러 개 동일한 기능을 제공 하는 있는 권장된 컨트롤 대체 된 컨트롤에 대 한 메모 함께 나열 됩니다. 별도 후속 테이블에서 대체 컨트롤과 권장된 대신 사용할 함께 나열 됩니다.  
  
> [!NOTE]
>  다음 표에서 모든 컨트롤 또는 Windows Forms;에서 사용할 수는 구성 요소를 나열 하지 않습니다. 보다 포괄적인 목록에 대 한 참조 [Windows Forms에서 사용할 컨트롤](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
  
## <a name="recommended-controls-and-components-by-function"></a>권장된 된 제어 및 함수에 의해 구성 요소  
  
|함수|Control|설명|  
|--------------|-------------|-----------------|  
|데이터 표시|<xref:System.Windows.Forms.DataGridView> 컨트롤|<xref:System.Windows.Forms.DataGridView> 컨트롤은 데이터를 표시 하기 위한 사용자 지정 가능한 테이블을 제공 합니다. <xref:System.Windows.Forms.DataGridView> 클래스에는 셀, 행, 열 및 테두리는 사용자 지정할 수 있습니다. **참고:** 는 <xref:System.Windows.Forms.DataGridView> 에 누락 된 다양 한 기본 및 고급 기능을 제공 하는 컨트롤의 <xref:System.Windows.Forms.DataGrid> 제어 합니다. 자세한 내용은 참조 [차이점 Windows Forms DataGridView 컨트롤과 DataGrid 컨트롤](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)|  
|데이터 바인딩 및 탐색|<xref:System.Windows.Forms.BindingSource>구성 요소|현재 항목 관리, 변경 알림 및 기타 서비스를 제공 하 여 데이터를 폼에 컨트롤 바인딩을 간소화 합니다.|  
||<xref:System.Windows.Forms.BindingNavigator> 컨트롤|탐색 하 고 폼에서 데이터를 조작 하기 위한 도구 모음 유형 인터페이스를 제공 합니다.|  
|텍스트 편집|<xref:System.Windows.Forms.TextBox> 컨트롤|런타임 시 사용자가 편집 하거나 프로그래밍 방식으로 변경할 수 있는 디자인 타임에 입력 한 텍스트를 표시 합니다.|  
||<xref:System.Windows.Forms.RichTextBox> 컨트롤|일반 텍스트 또는 서식 있는 텍스트 형식 (RTF)에 서식이 지정 된 표시 될 텍스트를를 수 있습니다.|  
||<xref:System.Windows.Forms.MaskedTextBox> 컨트롤|사용자 입력의 형식을 제한합니다.|  
|정보 표시 (읽기 전용)|<xref:System.Windows.Forms.Label> 컨트롤|사용자가 직접 편집할 수 없는 텍스트를 표시합니다.|  
||<xref:System.Windows.Forms.LinkLabel> 컨트롤|웹 스타일 링크 텍스트를 표시 하 고 사용자가 특수 한 텍스트를 클릭 하면 이벤트가 발생 합니다. 일반적으로 텍스트 다른 창이 나 웹 사이트에 대 한 링크입니다.|  
||<xref:System.Windows.Forms.StatusStrip> 컨트롤|일반적으로 부모 폼의 맨 아래에 프레임된 영역을 사용 하 여 응용 프로그램의 현재 상태에 대 한 정보를 표시 합니다.|  
||<xref:System.Windows.Forms.ProgressBar> 컨트롤|사용자에 게 작업의 현재 진행률을 표시합니다.|  
|웹 페이지 표시|<xref:System.Windows.Forms.WebBrowser> 컨트롤|사용자가 해당 양식 내에서 웹 페이지를 탐색할 수 있도록 합니다.|  
|목록에서 선택|<xref:System.Windows.Forms.CheckedListBox> 컨트롤|스크롤할 수 있는 목록이 각 항목의 확인란으로 표시 됩니다.|  
||<xref:System.Windows.Forms.ComboBox> 컨트롤|항목의 드롭다운 목록을 표시합니다.|  
||<xref:System.Windows.Forms.DomainUpDown> 컨트롤|사용자가 위쪽 및 아래쪽 단추를 사용 하 여 스크롤할 수 있는 텍스트 항목 목록을 표시 합니다.|  
||<xref:System.Windows.Forms.ListBox> 컨트롤|텍스트와 그래픽 항목 (아이콘)의 목록을 표시합니다.|  
||<xref:System.Windows.Forms.ListView> 컨트롤|네 가지 뷰 중 하나에서 항목을 표시합니다. 보기에는 텍스트만, 작은 아이콘, 큰 아이콘으로 텍스트 및 자세히 보기가 포함 됩니다.|  
||<xref:System.Windows.Forms.NumericUpDown> 컨트롤|사용자가 위쪽 및 아래쪽 단추를 사용 하 여 스크롤할 수 있는 숫자의 목록을 표시 합니다.|  
||<xref:System.Windows.Forms.TreeView> 컨트롤|텍스트 선택 확인란 또는 아이콘을 가진 구성 될 수 있는 노드 개체의 계층적 컬렉션을 표시 합니다.|  
|그래픽 표시|<xref:System.Windows.Forms.PictureBox> 컨트롤|예: 비트맵 및 아이콘 그래픽 파일 프레임에 표시 됩니다.|  
|그래픽 저장소|<xref:System.Windows.Forms.ImageList> 컨트롤|이미지에 대 한 리포지토리 역할을 합니다. <xref:System.Windows.Forms.ImageList>한 응용 프로그램에서 다음 컨트롤 및 포함 된 이미지를 재사용할 수 있습니다.|  
|값 설정|<xref:System.Windows.Forms.CheckBox> 컨트롤|확인란 및 텍스트에 대 한 레이블을 표시합니다. 일반적으로 옵션을 설정 하는 데 사용 합니다.|  
||<xref:System.Windows.Forms.CheckedListBox> 컨트롤|스크롤할 수 있는 목록이 각 항목의 확인란으로 표시 됩니다.|  
||<xref:System.Windows.Forms.RadioButton> 컨트롤|설정 하거나 해제할 수 있는 단추를 표시 합니다.|  
||<xref:System.Windows.Forms.TrackBar> 컨트롤|"Thumb" 눈금을 따라 이동 하 여 눈금 값을 설정할 수 있습니다.|  
|날짜 설정|<xref:System.Windows.Forms.DateTimePicker> 컨트롤|사용자가 날짜 또는 시간을 선택할 수 있도록 그래픽 달력을 표시 합니다.|  
||<xref:System.Windows.Forms.MonthCalendar> 컨트롤|사용자가 날짜 범위를 선택할 수 있도록 그래픽 달력을 표시 합니다.|  
|대화 상자|<xref:System.Windows.Forms.ColorDialog> 컨트롤|사용자가 인터페이스 요소 색상을 설정할 수 있는 색 선택 대화 상자를 표시 합니다.|  
||<xref:System.Windows.Forms.FontDialog> 컨트롤|사용자가 글꼴 및 해당 특성을 설정할 수 있는 대화 상자를 표시 합니다.|  
||<xref:System.Windows.Forms.OpenFileDialog> 컨트롤|사용자가 탐색 하 고 파일을 선택할 수 있는 대화 상자가 표시 됩니다.|  
||<xref:System.Windows.Forms.PrintDialog> 컨트롤|사용자가 프린터를 선택 하 고 해당 특성을 설정할 수 있는 대화 상자를 표시 합니다.|  
||<xref:System.Windows.Forms.PrintPreviewDialog> 컨트롤|방법 컨트롤 표시 하는 대화 상자가 표시 됩니다. <xref:System.Drawing.Printing.PrintDocument> 구성 요소는 인쇄할 때 표시 됩니다.|  
||<xref:System.Windows.Forms.FolderBrowserDialog> 컨트롤|사용자가 찾아보기 만들고 결국 폴더를 선택할 수 있는 대화 상자 표시|  
||<xref:System.Windows.Forms.SaveFileDialog> 컨트롤|사용자가 파일을 저장할 수 있는 대화 상자가 표시 됩니다.|  
|메뉴 컨트롤|<xref:System.Windows.Forms.MenuStrip> 컨트롤|사용자 지정 메뉴를 만듭니다. **참고:** 는 <xref:System.Windows.Forms.MenuStrip> 바꾸는 데는 <xref:System.Windows.Forms.MainMenu> 제어 합니다.|  
||<xref:System.Windows.Forms.ContextMenuStrip> 컨트롤|사용자 지정 상황에 맞는 메뉴를 만듭니다. **참고:** 는 <xref:System.Windows.Forms.ContextMenuStrip> 바꾸는 데는 <xref:System.Windows.Forms.ContextMenu> 제어 합니다.|  
|명령|<xref:System.Windows.Forms.Button> 컨트롤|시작, 중지 또는 중단 하는 프로세스입니다.|  
||<xref:System.Windows.Forms.LinkLabel> 컨트롤|웹 스타일 링크 텍스트를 표시 하 고 사용자가 특수 한 텍스트를 클릭 하면 이벤트가 발생 합니다. 일반적으로 텍스트 다른 창이 나 웹 사이트에 대 한 링크입니다.|  
||<xref:System.Windows.Forms.NotifyIcon> 컨트롤|백그라운드에서 실행 중인 응용 프로그램을 나타내는 작업 표시줄의 상태 알림 영역에 아이콘을 표시 합니다.|  
||<xref:System.Windows.Forms.ToolStrip> 컨트롤|Microsoft Windows XP, Microsoft Office, Microsoft Internet Explorer 또는 사용자 지정 디자인으로 또는 테마, 없이 및 오버플로 및 런타임 항목 다시 정렬을 지 원하는 가질 수 있는 도구 모음을 만듭니다. **참고:** 는 <xref:System.Windows.Forms.ToolStrip> 대체 하도록 디자인 된는 <xref:System.Windows.Forms.ToolBar> 제어 합니다.|  
|사용자 도움말|<xref:System.Windows.Forms.HelpProvider>구성 요소|컨트롤에 대한 팝업 또는 온라인 도움말을 제공합니다.|  
||<xref:System.Windows.Forms.ToolTip>구성 요소|사용자 컨트롤에 포인터를 놓을 때 컨트롤의 용도에 대 한 간략 한 설명을 표시 하는 팝업 창을 제공 합니다.|  
|다른 컨트롤 그룹화|<xref:System.Windows.Forms.Panel> 컨트롤|스크롤 가능, 레이블이 지정 되지 않은 프레임에 대 한 컨트롤 집합을 그룹화합니다.|  
||<xref:System.Windows.Forms.GroupBox> 컨트롤|레이블이 지정 된, 비스크롤형 프레임에 컨트롤 (예: 라디오 단추)의 집합을 그룹화합니다.|  
||<xref:System.Windows.Forms.TabControl> 컨트롤|효율적으로 그룹화 된 개체를 구성 하 고 액세스 하는 탭된 페이지를 제공 합니다.|  
||<xref:System.Windows.Forms.SplitContainer> 컨트롤|이동 가능한 막대로 구분 된 두 개의 패널을 제공 합니다. **참고:** 는 <xref:System.Windows.Forms.SplitContainer> 대체 하도록 디자인 된는 <xref:System.Windows.Forms.Splitter> 제어 합니다.|  
||<xref:System.Windows.Forms.TableLayoutPanel> 컨트롤|행과 열로 구성된 표로 내용을 동적으로 레이아웃하는 패널을 나타냅니다.|  
||<xref:System.Windows.Forms.FlowLayoutPanel> 컨트롤|가로 또는 세로로 해당 내용을 동적으로 펼쳐지는 패널을 나타냅니다.|  
|오디오|<xref:System.Media.SoundPlayer> 컨트롤|소리.wav 형식의 파일을 재생 합니다. 소리를 로드 또는 비동기적으로 재생할 수 있습니다.|  
  
## <a name="superseded-controls-and-components-by-function"></a>대체 컨트롤 및 함수에 의해 구성 요소  
  
|함수|대체 된 컨트롤|권장된 교체|  
|--------------|------------------------|-----------------------------|  
|데이터 표시|<xref:System.Windows.Forms.DataGrid>|<xref:System.Windows.Forms.DataGridView>|  
|정보 표시 (읽기 전용 컨트롤)|<xref:System.Windows.Forms.StatusBar>|<xref:System.Windows.Forms.StatusStrip>|  
|메뉴 컨트롤|<xref:System.Windows.Forms.ContextMenu>|<xref:System.Windows.Forms.ContextMenuStrip>|  
||<xref:System.Windows.Forms.MainMenu>|<xref:System.Windows.Forms.MenuStrip>|  
|명령|<xref:System.Windows.Forms.ToolBar>|<xref:System.Windows.Forms.ToolStrip>|  
||<xref:System.Windows.Forms.StatusBar>|<xref:System.Windows.Forms.StatusStrip>|  
|폼 레이아웃|<xref:System.Windows.Forms.Splitter>|<xref:System.Windows.Forms.SplitContainer>|  
  
## <a name="see-also"></a>참고 항목  
 [Windows Forms에 사용할 수 있는 컨트롤](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [.NET Framework에서 사용자 지정 Windows Forms 컨트롤 개발](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)
