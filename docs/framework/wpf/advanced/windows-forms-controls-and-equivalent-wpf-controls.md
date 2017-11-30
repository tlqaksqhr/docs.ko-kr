---
title: "Windows Forms 컨트롤 및 해당 WPF 컨트롤"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms [WPF], interoperability with
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
ms.assetid: 8a157e6b-8054-46db-a5cf-a78966acc7a1
caps.latest.revision: "27"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0fae33ee8744936f3152ef991715853028063066
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="windows-forms-controls-and-equivalent-wpf-controls"></a><span data-ttu-id="59e51-102">Windows Forms 컨트롤 및 해당 WPF 컨트롤</span><span class="sxs-lookup"><span data-stu-id="59e51-102">Windows Forms Controls and Equivalent WPF Controls</span></span>
<span data-ttu-id="59e51-103">많은 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤 해당 하는 요소가 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤 이지만 일부 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 해당 컨트롤에는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="59e51-103">Many [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls have equivalent [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controls, but some [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls have no equivalents in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span> <span data-ttu-id="59e51-104">이 항목에서는 두 가지 기술에서 제공 하는 컨트롤 형식을 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="59e51-104">This topic compares control types provided by the two technologies.</span></span>  
  
 <span data-ttu-id="59e51-105">호스트의 상호 운용을 항상 사용할 수 있습니다 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 의 해당 항목을 포함 하지 않는 컨트롤 프로그램 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-기반 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="59e51-105">You can always use interoperation to host [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls that do not have equivalents in your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based applications.</span></span>  
  
 <span data-ttu-id="59e51-106">다음 표에 나와 있는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤 및 구성 요소가 해당 하는 요소가 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 기능을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="59e51-106">The following table shows which [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls and components have equivalent [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] control functionality.</span></span>  
  
|<span data-ttu-id="59e51-107">Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="59e51-107">Windows Forms control</span></span>|<span data-ttu-id="59e51-108">해당 WPF 컨트롤</span><span class="sxs-lookup"><span data-stu-id="59e51-108">WPF equivalent control</span></span>|<span data-ttu-id="59e51-109">설명</span><span class="sxs-lookup"><span data-stu-id="59e51-109">Remarks</span></span>|  
|---------------------------|----------------------------|-------------|  
|<xref:System.Windows.Forms.BindingNavigator>|<span data-ttu-id="59e51-110">해당 하는 제어 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="59e51-110">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.BindingSource>|<xref:System.Windows.Data.CollectionViewSource>||  
|<xref:System.Windows.Forms.Button>|<xref:System.Windows.Controls.Button>||  
|<xref:System.Windows.Forms.CheckBox>|<xref:System.Windows.Controls.CheckBox>||  
|<xref:System.Windows.Forms.CheckedListBox>|<span data-ttu-id="59e51-111"><xref:System.Windows.Controls.ListBox>composition과.</span><span class="sxs-lookup"><span data-stu-id="59e51-111"><xref:System.Windows.Controls.ListBox> with composition.</span></span>||  
|<xref:System.Windows.Forms.ColorDialog>|<span data-ttu-id="59e51-112">해당 하는 제어 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="59e51-112">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.ComboBox>|<xref:System.Windows.Controls.ComboBox>|<span data-ttu-id="59e51-113"><xref:System.Windows.Controls.ComboBox>자동 완성을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="59e51-113"><xref:System.Windows.Controls.ComboBox> does not support auto-complete.</span></span>|  
|<xref:System.Windows.Forms.ContextMenuStrip>|<xref:System.Windows.Controls.ContextMenu>||  
|<xref:System.Windows.Forms.DataGridView>|<xref:System.Windows.Controls.DataGrid>||  
|<xref:System.Windows.Forms.DateTimePicker>|<xref:System.Windows.Controls.DatePicker>||  
|<xref:System.Windows.Forms.DomainUpDown>|<span data-ttu-id="59e51-114"><xref:System.Windows.Controls.TextBox>와 그 두 <xref:System.Windows.Controls.Primitives.RepeatButton> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="59e51-114"><xref:System.Windows.Controls.TextBox> and two <xref:System.Windows.Controls.Primitives.RepeatButton> controls.</span></span>||  
|<xref:System.Windows.Forms.ErrorProvider>|<span data-ttu-id="59e51-115">해당 하는 제어 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="59e51-115">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.FlowLayoutPanel>|<span data-ttu-id="59e51-116"><xref:System.Windows.Controls.WrapPanel> 또는 <xref:System.Windows.Controls.StackPanel></span><span class="sxs-lookup"><span data-stu-id="59e51-116"><xref:System.Windows.Controls.WrapPanel> or <xref:System.Windows.Controls.StackPanel></span></span>||  
|<xref:System.Windows.Forms.FolderBrowserDialog>|<span data-ttu-id="59e51-117">해당 하는 제어 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="59e51-117">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.FontDialog>|<span data-ttu-id="59e51-118">해당 하는 제어 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="59e51-118">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.Form>|<xref:System.Windows.Window>|<span data-ttu-id="59e51-119"><xref:System.Windows.Window>자식 창 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="59e51-119"><xref:System.Windows.Window> does not support child windows.</span></span>|  
|<xref:System.Windows.Forms.GroupBox>|<xref:System.Windows.Controls.GroupBox>||  
|<xref:System.Windows.Forms.HelpProvider>|<span data-ttu-id="59e51-120">해당 하는 제어 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="59e51-120">No equivalent control.</span></span>|<span data-ttu-id="59e51-121">F1 도움말이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="59e51-121">No F1 Help.</span></span> <span data-ttu-id="59e51-122">"기능"을이 도움말은 도구 설명으로 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="59e51-122">"What's This" Help is replaced by ToolTips.</span></span>|  
|<xref:System.Windows.Forms.HScrollBar>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="59e51-123">컨테이너 컨트롤에 스크롤가 빌드됩니다.</span><span class="sxs-lookup"><span data-stu-id="59e51-123">Scrolling is built into container controls.</span></span>|  
|<xref:System.Windows.Forms.ImageList>|<span data-ttu-id="59e51-124">해당 하는 제어 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="59e51-124">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.Label>|<xref:System.Windows.Controls.Label>||  
|<xref:System.Windows.Forms.LinkLabel>|<span data-ttu-id="59e51-125">해당 하는 제어 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="59e51-125">No equivalent control.</span></span>|<span data-ttu-id="59e51-126">사용할 수는 <xref:System.Windows.Documents.Hyperlink> 클래스 유동 콘텐츠 내에서 하이퍼링크를 호스팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59e51-126">You can use the <xref:System.Windows.Documents.Hyperlink> class to host hyperlinks within flow content.</span></span>|  
|<xref:System.Windows.Forms.ListBox>|<xref:System.Windows.Controls.ListBox>||  
|<xref:System.Windows.Forms.ListView>|<xref:System.Windows.Controls.ListView>|<span data-ttu-id="59e51-127"><xref:System.Windows.Controls.ListView> 컨트롤은 읽기 전용 세부 정보 보기를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="59e51-127">The <xref:System.Windows.Controls.ListView> control provides a read-only details view.</span></span>|  
|<xref:System.Windows.Forms.MaskedTextBox>|<span data-ttu-id="59e51-128">해당 하는 제어 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="59e51-128">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.MenuStrip>|<xref:System.Windows.Controls.Menu>|<span data-ttu-id="59e51-129"><xref:System.Windows.Controls.Menu>동작 및 모양 컨트롤 스타일 지정 대략적인 수는 <xref:System.Windows.Forms.ToolStripProfessionalRenderer?displayProperty=nameWithType> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="59e51-129"><xref:System.Windows.Controls.Menu> control styling can approximate the behavior and appearance of the <xref:System.Windows.Forms.ToolStripProfessionalRenderer?displayProperty=nameWithType> class.</span></span>|  
|<xref:System.Windows.Forms.MonthCalendar>|<xref:System.Windows.Controls.Calendar>||  
|<xref:System.Windows.Forms.NotifyIcon>|<span data-ttu-id="59e51-130">해당 하는 제어 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="59e51-130">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.NumericUpDown>|<span data-ttu-id="59e51-131"><xref:System.Windows.Controls.TextBox>와 그 두 <xref:System.Windows.Controls.Primitives.RepeatButton> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="59e51-131"><xref:System.Windows.Controls.TextBox> and two <xref:System.Windows.Controls.Primitives.RepeatButton> controls.</span></span>||  
|<xref:System.Windows.Forms.OpenFileDialog>|<xref:Microsoft.Win32.OpenFileDialog>|<span data-ttu-id="59e51-132"><xref:Microsoft.Win32.OpenFileDialog> 클래스는는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 래퍼는 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="59e51-132">The <xref:Microsoft.Win32.OpenFileDialog> class is a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wrapper around the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] control.</span></span>|  
|<xref:System.Windows.Forms.PageSetupDialog>|<span data-ttu-id="59e51-133">해당 하는 제어 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="59e51-133">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.Panel>|<xref:System.Windows.Controls.Canvas>||  
|<xref:System.Windows.Forms.PictureBox>|<xref:System.Windows.Controls.Image>||  
|<xref:System.Windows.Forms.PrintDialog>|<xref:System.Windows.Controls.PrintDialog>||  
|<xref:System.Drawing.Printing.PrintDocument>|<span data-ttu-id="59e51-134">해당 하는 제어 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="59e51-134">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.PrintPreviewControl>|<xref:System.Windows.Controls.DocumentViewer>||  
|<xref:System.Windows.Forms.PrintPreviewDialog>|<span data-ttu-id="59e51-135">해당 하는 제어 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="59e51-135">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.ProgressBar>|<xref:System.Windows.Controls.ProgressBar>||  
|<xref:System.Windows.Forms.PropertyGrid>|<span data-ttu-id="59e51-136">해당 하는 제어 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="59e51-136">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.RadioButton>|<xref:System.Windows.Controls.RadioButton>||  
|<xref:System.Windows.Forms.RichTextBox>|<xref:System.Windows.Controls.RichTextBox>||  
|<xref:System.Windows.Forms.SaveFileDialog>|<xref:Microsoft.Win32.SaveFileDialog>|<span data-ttu-id="59e51-137"><xref:Microsoft.Win32.SaveFileDialog> 클래스는는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 래퍼는 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="59e51-137">The <xref:Microsoft.Win32.SaveFileDialog> class is a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wrapper around the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] control.</span></span>|  
|<xref:System.Windows.Forms.ScrollableControl>|<xref:System.Windows.Controls.ScrollViewer>||  
|<xref:System.Media.SoundPlayer>|<xref:System.Windows.Media.MediaPlayer>||  
|<xref:System.Windows.Forms.SplitContainer>|<xref:System.Windows.Controls.GridSplitter>||  
|<xref:System.Windows.Forms.StatusStrip>|<xref:System.Windows.Controls.Primitives.StatusBar>||  
|<xref:System.Windows.Forms.TabControl>|<xref:System.Windows.Controls.TabControl>||  
|<xref:System.Windows.Forms.TableLayoutPanel>|<xref:System.Windows.Controls.Grid>||  
|<xref:System.Windows.Forms.TextBox>|<xref:System.Windows.Controls.TextBox>||  
|<xref:System.Windows.Forms.Timer>|<xref:System.Windows.Threading.DispatcherTimer>||  
|<xref:System.Windows.Forms.ToolStrip>|<xref:System.Windows.Controls.ToolBar>||  
|<xref:System.Windows.Forms.ToolStripContainer>|<span data-ttu-id="59e51-138"><xref:System.Windows.Controls.ToolBar>composition과.</span><span class="sxs-lookup"><span data-stu-id="59e51-138"><xref:System.Windows.Controls.ToolBar> with composition.</span></span>||  
|<xref:System.Windows.Forms.ToolStripDropDown>|<span data-ttu-id="59e51-139"><xref:System.Windows.Controls.ToolBar>composition과.</span><span class="sxs-lookup"><span data-stu-id="59e51-139"><xref:System.Windows.Controls.ToolBar> with composition.</span></span>||  
|<xref:System.Windows.Forms.ToolStripDropDownMenu>|<span data-ttu-id="59e51-140"><xref:System.Windows.Controls.ToolBar>composition과.</span><span class="sxs-lookup"><span data-stu-id="59e51-140"><xref:System.Windows.Controls.ToolBar> with composition.</span></span>||  
|<xref:System.Windows.Forms.ToolStripPanel>|<span data-ttu-id="59e51-141"><xref:System.Windows.Controls.ToolBar>composition과.</span><span class="sxs-lookup"><span data-stu-id="59e51-141"><xref:System.Windows.Controls.ToolBar> with composition.</span></span>||  
|<xref:System.Windows.Forms.ToolTip>|<xref:System.Windows.Controls.ToolTip>||  
|<xref:System.Windows.Forms.TrackBar>|<xref:System.Windows.Controls.Slider>||  
|<xref:System.Windows.Forms.TreeView>|<xref:System.Windows.Controls.TreeView>||  
|<xref:System.Windows.Forms.UserControl>|<xref:System.Windows.Controls.UserControl>||  
|<xref:System.Windows.Forms.VScrollBar>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="59e51-142">컨테이너 컨트롤에 스크롤가 빌드됩니다.</span><span class="sxs-lookup"><span data-stu-id="59e51-142">Scrolling is built into container controls.</span></span>|  
|<xref:System.Windows.Forms.WebBrowser>|<span data-ttu-id="59e51-143"><xref:System.Windows.Controls.Frame>, <xref:System.Windows.Controls.WebBrowser?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="59e51-143"><xref:System.Windows.Controls.Frame>, <xref:System.Windows.Controls.WebBrowser?displayProperty=nameWithType></span></span>|<span data-ttu-id="59e51-144"><xref:System.Windows.Controls.Frame> 컨트롤이 HTML 페이지를 호스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59e51-144">The <xref:System.Windows.Controls.Frame> control can host HTML pages.</span></span><br /><br /> <span data-ttu-id="59e51-145">부터는 [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)], <xref:System.Windows.Controls.WebBrowser?displayProperty=nameWithType> 컨트롤이 HTML 페이지 및 회의 호스트할 수는 <xref:System.Windows.Controls.Frame> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="59e51-145">Starting in the [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)], the <xref:System.Windows.Controls.WebBrowser?displayProperty=nameWithType> control can host HTML pages and also backs the <xref:System.Windows.Controls.Frame> control.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="59e51-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="59e51-146">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="59e51-147">Windows 용 WPF 디자이너 Forms 개발자가</span><span class="sxs-lookup"><span data-stu-id="59e51-147">WPF Designer for Windows Forms Developers</span></span>](http://msdn.microsoft.com/en-us/47ad0909-e89b-4996-b4ac-874d929f94ca)  
 [<span data-ttu-id="59e51-148">연습: WPF에서 Windows Forms 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="59e51-148">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)  
 [<span data-ttu-id="59e51-149">연습: Windows Forms에서 WPF 복합 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="59e51-149">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)  
 [<span data-ttu-id="59e51-150">마이그레이션 및 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="59e51-150">Migration and Interoperability</span></span>](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)
