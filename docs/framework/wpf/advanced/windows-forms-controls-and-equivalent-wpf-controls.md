---
title: "Windows Forms 컨트롤 및 해당 WPF 컨트롤 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "상호 운용성[WPF], Windows Forms"
  - "Windows Forms[WPF], 상호 운용성"
  - "Windows Forms, WPF 상호 운용"
ms.assetid: 8a157e6b-8054-46db-a5cf-a78966acc7a1
caps.latest.revision: 27
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 27
---
# Windows Forms 컨트롤 및 해당 WPF 컨트롤
여러 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤에는 대응되는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤이 있지만 일부 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤의 경우에는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에 대응되는 컨트롤이 없습니다.  이 항목에서는 이 두 기술에서 제공하는 컨트롤 형식을 비교합니다.  
  
 항상 상호 운용을 사용하여 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 기반 응용 프로그램에 대응되는 컨트롤이 없는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤을 호스팅할 수 있습니다.  
  
 다음 표에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에 대응되는 컨트롤 기능이 있는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤 및 구성 요소를 보여 줍니다.  
  
|Windows Forms 컨트롤|해당 WPF 컨트롤|설명|  
|-----------------------|----------------|--------|  
|<xref:System.Windows.Forms.BindingNavigator>|해당 컨트롤 없음||  
|<xref:System.Windows.Forms.BindingSource>|<xref:System.Windows.Data.CollectionViewSource>||  
|<xref:System.Windows.Forms.Button>|<xref:System.Windows.Controls.Button>||  
|<xref:System.Windows.Forms.CheckBox>|<xref:System.Windows.Controls.CheckBox>||  
|<xref:System.Windows.Forms.CheckedListBox>|컴퍼지션을 사용한 <xref:System.Windows.Controls.ListBox>||  
|<xref:System.Windows.Forms.ColorDialog>|해당 컨트롤 없음||  
|<xref:System.Windows.Forms.ComboBox>|<xref:System.Windows.Controls.ComboBox>|<xref:System.Windows.Controls.ComboBox>는 자동 완료를 지원하지 않습니다.|  
|<xref:System.Windows.Forms.ContextMenuStrip>|<xref:System.Windows.Controls.ContextMenu>||  
|<xref:System.Windows.Forms.DataGridView>|<xref:System.Windows.Controls.DataGrid>||  
|<xref:System.Windows.Forms.DateTimePicker>|<xref:System.Windows.Controls.DatePicker>||  
|<xref:System.Windows.Forms.DomainUpDown>|<xref:System.Windows.Controls.TextBox> 및 두 개의 <xref:System.Windows.Controls.Primitives.RepeatButton> 컨트롤||  
|<xref:System.Windows.Forms.ErrorProvider>|해당 컨트롤 없음||  
|<xref:System.Windows.Forms.FlowLayoutPanel>|<xref:System.Windows.Controls.WrapPanel> 또는 <xref:System.Windows.Controls.StackPanel>||  
|<xref:System.Windows.Forms.FolderBrowserDialog>|해당 컨트롤 없음||  
|<xref:System.Windows.Forms.FontDialog>|해당 컨트롤 없음||  
|<xref:System.Windows.Forms.Form>|<xref:System.Windows.Window>|<xref:System.Windows.Window>는 자식 창을 지원하지 않습니다.|  
|<xref:System.Windows.Forms.GroupBox>|<xref:System.Windows.Controls.GroupBox>||  
|<xref:System.Windows.Forms.HelpProvider>|해당 컨트롤 없음|F1 도움말이 없습니다. 이때   설명" 도움말이 도구 설명으로 대체되었습니다.|  
|<xref:System.Windows.Forms.HScrollBar>|<xref:System.Windows.Controls.Primitives.ScrollBar>|스크롤이 컨테이너 컨트롤에 기본 제공됩니다.|  
|<xref:System.Windows.Forms.ImageList>|해당 컨트롤 없음||  
|<xref:System.Windows.Forms.Label>|<xref:System.Windows.Controls.Label>||  
|<xref:System.Windows.Forms.LinkLabel>|해당 컨트롤 없음|<xref:System.Windows.Documents.Hyperlink> 클래스를 사용하여 유동 콘텐츠 안에 하이퍼링크를 호스팅할 수 있습니다.|  
|<xref:System.Windows.Forms.ListBox>|<xref:System.Windows.Controls.ListBox>||  
|<xref:System.Windows.Forms.ListView>|<xref:System.Windows.Controls.ListView>|<xref:System.Windows.Controls.ListView> 컨트롤은 읽기 전용 자세히 보기를 지원합니다.|  
|<xref:System.Windows.Forms.MaskedTextBox>|해당 컨트롤 없음||  
|<xref:System.Windows.Forms.MenuStrip>|<xref:System.Windows.Controls.Menu>|<xref:System.Windows.Controls.Menu> 컨트롤 스타일 설정은 <xref:System.Windows.Forms.ToolStripProfessionalRenderer?displayProperty=fullName> 클래스의 동작 및 모양과 비슷합니다.|  
|<xref:System.Windows.Forms.MonthCalendar>|<xref:System.Windows.Controls.Calendar>||  
|<xref:System.Windows.Forms.NotifyIcon>|해당 컨트롤 없음||  
|<xref:System.Windows.Forms.NumericUpDown>|<xref:System.Windows.Controls.TextBox> 및 두 개의 <xref:System.Windows.Controls.Primitives.RepeatButton> 컨트롤||  
|<xref:System.Windows.Forms.OpenFileDialog>|<xref:Microsoft.Win32.OpenFileDialog>|<xref:Microsoft.Win32.OpenFileDialog> 클래스는 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 컨트롤 주위의 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 래퍼입니다.|  
|<xref:System.Windows.Forms.PageSetupDialog>|해당 컨트롤 없음||  
|<xref:System.Windows.Forms.Panel>|<xref:System.Windows.Controls.Canvas>||  
|<xref:System.Windows.Forms.PictureBox>|<xref:System.Windows.Controls.Image>||  
|<xref:System.Windows.Forms.PrintDialog>|<xref:System.Windows.Controls.PrintDialog>||  
|<xref:System.Drawing.Printing.PrintDocument>|해당 컨트롤 없음||  
|<xref:System.Windows.Forms.PrintPreviewControl>|<xref:System.Windows.Controls.DocumentViewer>||  
|<xref:System.Windows.Forms.PrintPreviewDialog>|해당 컨트롤 없음||  
|<xref:System.Windows.Forms.ProgressBar>|<xref:System.Windows.Controls.ProgressBar>||  
|<xref:System.Windows.Forms.PropertyGrid>|해당 컨트롤 없음||  
|<xref:System.Windows.Forms.RadioButton>|<xref:System.Windows.Controls.RadioButton>||  
|<xref:System.Windows.Forms.RichTextBox>|<xref:System.Windows.Controls.RichTextBox>||  
|<xref:System.Windows.Forms.SaveFileDialog>|<xref:Microsoft.Win32.SaveFileDialog>|<xref:Microsoft.Win32.SaveFileDialog> 클래스는 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 컨트롤 주위의 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 래퍼입니다.|  
|<xref:System.Windows.Forms.ScrollableControl>|<xref:System.Windows.Controls.ScrollViewer>||  
|<xref:System.Media.SoundPlayer>|<xref:System.Windows.Media.MediaPlayer>||  
|<xref:System.Windows.Forms.SplitContainer>|<xref:System.Windows.Controls.GridSplitter>||  
|<xref:System.Windows.Forms.StatusStrip>|<xref:System.Windows.Controls.Primitives.StatusBar>||  
|<xref:System.Windows.Forms.TabControl>|<xref:System.Windows.Controls.TabControl>||  
|<xref:System.Windows.Forms.TableLayoutPanel>|<xref:System.Windows.Controls.Grid>||  
|<xref:System.Windows.Forms.TextBox>|<xref:System.Windows.Controls.TextBox>||  
|<xref:System.Windows.Forms.Timer>|<xref:System.Windows.Threading.DispatcherTimer>||  
|<xref:System.Windows.Forms.ToolStrip>|<xref:System.Windows.Controls.ToolBar>||  
|<xref:System.Windows.Forms.ToolStripContainer>|컴퍼지션을 사용한 <xref:System.Windows.Controls.ToolBar>||  
|<xref:System.Windows.Forms.ToolStripDropDown>|컴퍼지션을 사용한 <xref:System.Windows.Controls.ToolBar>||  
|<xref:System.Windows.Forms.ToolStripDropDownMenu>|컴퍼지션을 사용한 <xref:System.Windows.Controls.ToolBar>||  
|<xref:System.Windows.Forms.ToolStripPanel>|컴퍼지션을 사용한 <xref:System.Windows.Controls.ToolBar>||  
|<xref:System.Windows.Forms.ToolTip>|<xref:System.Windows.Controls.ToolTip>||  
|<xref:System.Windows.Forms.TrackBar>|<xref:System.Windows.Controls.Slider>||  
|<xref:System.Windows.Forms.TreeView>|<xref:System.Windows.Controls.TreeView>||  
|<xref:System.Windows.Forms.UserControl>|<xref:System.Windows.Controls.UserControl>||  
|<xref:System.Windows.Forms.VScrollBar>|<xref:System.Windows.Controls.Primitives.ScrollBar>|스크롤이 컨테이너 컨트롤에 기본 제공됩니다.|  
|<xref:System.Windows.Forms.WebBrowser>|<xref:System.Windows.Controls.Frame>, <xref:System.Windows.Controls.WebBrowser?displayProperty=fullName>|<xref:System.Windows.Controls.Frame> 컨트롤은 HTML 페이지를 호스팅할 수 있습니다.<br /><br /> [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)]부터는 <xref:System.Windows.Controls.WebBrowser?displayProperty=fullName> 컨트롤에서 HTML 페이지를 호스팅할 수 있으며 <xref:System.Windows.Controls.Frame> 컨트롤도 지원합니다.|  
  
## 참고 항목  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [Windows Forms 개발자를 위한 WPF Designer](http://msdn.microsoft.com/ko-kr/47ad0909-e89b-4996-b4ac-874d929f94ca)   
 [연습: WPF에서 Windows Forms 컨트롤 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)   
 [연습: Windows Forms에서 WPF 복합 컨트롤 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)   
 [마이그레이션 및 상호 운용성](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)