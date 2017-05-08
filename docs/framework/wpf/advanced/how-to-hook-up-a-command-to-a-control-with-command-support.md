---
title: "방법: 명령을 지원하는 컨트롤에 명령 후크 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "RoutedCommand 연결 되는 컨트롤 클래스"
  - "클래스, 제어, RoutedCommand 연결"
  - "컨트롤에 연결 하는 RoutedCommand 클래스"
  - "클래스, RoutedCommand, 컨트롤에 연결"
ms.assetid: 8d8592ae-0c91-469e-a1cd-d179c4544548
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: 명령을 지원하는 컨트롤에 명령 후크
다음 예제에 후크 하는 방법을 보여 줍니다는 <xref:System.Windows.Input.RoutedCommand> 에 <xref:System.Windows.Controls.Control> 는 명령에 대 한 지원 하도록 설계 되었습니다.  여러 원본에 명령을를 연결 하는 전체 샘플을 참조 하십시오.는 [만들기 사용자 지정 RoutedCommand 샘플](http://go.microsoft.com/fwlink/?LinkID=159980) 샘플입니다.  
  
## <a name="example"></a>예제  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]응용 프로그램 프로그래머는 정기적으로 발생 하는 일반적인 명령의 라이브러리를 제공 합니다.  명령 라이브러리를 구성 하는 클래스는: <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.ComponentCommands>, <xref:System.Windows.Input.NavigationCommands>, <xref:System.Windows.Input.MediaCommands>, 및 <xref:System.Windows.Documents.EditingCommands>합니다.  
  
 정적 <xref:System.Windows.Input.RoutedCommand> 이러한 클래스를 구성 하는 개체 명령 논리를 제공 하지 않습니다.  명령에 대 한 논리를 사용 하는 명령은와 연결 된 한 <xref:System.Windows.Input.CommandBinding>합니다.  일부 컨트롤 몇 가지 명령에 대 한 CommandBindings 구축한 합니다.  이 메커니즘의 실제 구현 되는 동안 동일 하 게 유지 하는 명령 의미 체계를 변경할 수 있습니다.  A <xref:System.Windows.Controls.TextBox>, 예를 들어 처리는 <xref:System.Windows.Input.ApplicationCommands.Paste%2A> 다르게 명령을 컨트롤 이미지를 지원 하도록 설계 되었지만 의미 하는 항목을 붙여의 기본 개념은 동일 하 게 유지 합니다.  명령 논리 명령에서 지정할 수 없습니다. 하지만 컨트롤이 나 응용 프로그램에서 제공 해야 합니다.  
  
 많은 컨트롤 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 명령 라이브러리의 명령 중 일부에 대 한 지원 기능이 내장 되어 수행 합니다.  <xref:System.Windows.Controls.TextBox>, 예를 들어과 같은 다양 한 응용 프로그램 편집 명령을 지원 <xref:System.Windows.Input.ApplicationCommands.Paste%2A>, <xref:System.Windows.Input.ApplicationCommands.Copy%2A>, <xref:System.Windows.Input.ApplicationCommands.Cut%2A>, <xref:System.Windows.Input.ApplicationCommands.Redo%2A>, 및 <xref:System.Windows.Input.ApplicationCommands.Undo%2A>합니다.  응용 프로그램 개발자는 이러한 명령에는 이러한 컨트롤을 사용 하기 위해 특별 한 모든 작업을 수행할 필요가 없습니다.  하는 경우는 <xref:System.Windows.Controls.TextBox> 가 명령 대상 명령이 실행 될 때 사용 하 여 명령을 처리할 수 있으므로 <xref:System.Windows.Input.CommandBinding> 컨트롤에 내장 되어 있습니다.  
  
 다음을 사용 하는 방법을 보여 줍니다는 <xref:System.Windows.Controls.MenuItem> 명령 원본으로는 <xref:System.Windows.Input.ApplicationCommands.Paste%2A> 명령, 여기서는 <xref:System.Windows.Controls.TextBox> 명령의 대상입니다.  정의 하는 모든 논리 방법을 <xref:System.Windows.Controls.TextBox> 수행 붙여넣기에 기본 제공 되는 <xref:System.Windows.Controls.TextBox> 제어 합니다.  
  
 A <xref:System.Windows.Controls.MenuItem> 만들어집니다 이며 <xref:System.Windows.Controls.MenuItem.Command%2A> 속성이로 설정 되는 <xref:System.Windows.Input.ApplicationCommands.Paste%2A> 명령입니다.  <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> 로 명시적으로 설정 되지 않은 <xref:System.Windows.Controls.TextBox> 개체입니다.  때는 <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> 을 설정 하지 않으면 대상 명령에 키보드 포커스가 있는 요소입니다.  키보드 포커스가 있는 요소를 지원 하지 않는 경우는 <xref:System.Windows.Input.ApplicationCommands.Paste%2A> 명령 또는 현재는 붙여넣기 명령 (클립보드 비어 있음, 예를 들어)를 실행할 수 없습니다 면 <xref:System.Windows.Controls.MenuItem> 이 회색입니다.  
  
 [!code-xml[MenuItemCommandTask_XAML#MenuItemCommanding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandTask_XAML/CS/Window1.xaml#menuitemcommanding)]  
  
 [!code-csharp[MenuItemCommandTask#MenuItemCommandingCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandTask/CSharp/Window1.xaml.cs#menuitemcommandingcodebehind)]
 [!code-vb[MenuItemCommandTask#MenuItemCommandingCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MenuItemCommandTask/VisualBasic/Window1.xaml.vb#menuitemcommandingcodebehind)]  
  
## <a name="see-also"></a>참고 항목  
 [명령 개요](../../../../docs/framework/wpf/advanced/commanding-overview.md)   
 [명령 지원 하지 않는 컨트롤에 명령 후크](../../../../docs/framework/wpf/advanced/how-to-hook-up-a-command-to-a-control-with-no-command-support.md)