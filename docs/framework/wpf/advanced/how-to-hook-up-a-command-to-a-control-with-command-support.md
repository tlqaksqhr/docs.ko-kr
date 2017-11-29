---
title: "방법: 명령을 지원하는 컨트롤에 명령 후크"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Control class [WPF], attaching a RoutedCommand
- classes [WPF], Control [WPF], attaching a RoutedCommand
- RoutedCommand class [WPF], attaching to a Control
- classes [WPF], RoutedCommand [WPF], attaching to a Control
ms.assetid: 8d8592ae-0c91-469e-a1cd-d179c4544548
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 61148e1249f7bfcf319c3be4a30c706c5c4dc344
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-hook-up-a-command-to-a-control-with-command-support"></a>방법: 명령을 지원하는 컨트롤에 명령 후크
후크 하는 방법을 보여 주는 다음 예제는 <xref:System.Windows.Input.RoutedCommand> 에 <xref:System.Windows.Controls.Control> 는 기본적으로 지 원하는 명령에 대 한 합니다.  여러 소스에 명령을 후크하는 전체 샘플은 [Create a Custom RoutedCommand Sample](http://go.microsoft.com/fwlink/?LinkID=159980)(사용자 지정 RoutedCommand 만들기 샘플)을 참조하세요.  
  
## <a name="example"></a>예제  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]는 응용 프로그램 프로그래머가 자주 접하게 되는 공용 명령의 라이브러리를 제공합니다.  클래스는 명령 라이브러리를 구성 하는: <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.ComponentCommands>, <xref:System.Windows.Input.NavigationCommands>, <xref:System.Windows.Input.MediaCommands>, 및 <xref:System.Windows.Documents.EditingCommands>합니다.  
  
 정적 <xref:System.Windows.Input.RoutedCommand> 이러한 클래스를 구성 하는 개체 명령 논리를 제공 하지 않습니다.  사용 하 여 명령과와 연결 된 명령에 대 한 논리는 <xref:System.Windows.Input.CommandBinding>합니다.  일부 컨트롤에는 일부 명령에 대한 CommandBindings가 기본 제공되어 있습니다.  이 메커니즘을 사용하면 명령의 의미 체계를 동일하게 유지하면서 실제 구현을 변경할 수 있습니다.  A <xref:System.Windows.Controls.TextBox>, 예를 들어 처리는 <xref:System.Windows.Input.ApplicationCommands.Paste%2A> 다르게 명령을 컨트롤 이미지를 지원 하도록 설계 되어 있지만 항목을 붙여 의미의 기본 개념은 동일 하 게 유지 합니다.  명령 논리는 명령에 의해 제공될 수 없으나 대신 컨트롤 또는 응용 프로그램에 의해 제공되어야 합니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 많은 컨트롤은 명령 라이브러리의 일부 명령에 대한 지원을 기본 제공합니다.  <xref:System.Windows.Controls.TextBox>예를 들어와 같은 다양 한 응용 프로그램 편집 명령을 지원 <xref:System.Windows.Input.ApplicationCommands.Paste%2A>, <xref:System.Windows.Input.ApplicationCommands.Copy%2A>, <xref:System.Windows.Input.ApplicationCommands.Cut%2A>, <xref:System.Windows.Input.ApplicationCommands.Redo%2A>, 및 <xref:System.Windows.Input.ApplicationCommands.Undo%2A>합니다.  응용 프로그램 개발자는 이러한 명령을 컨트롤과 함께 사용하기 위해 별도로 해야 하는 작업은 없습니다.  경우는 <xref:System.Windows.Controls.TextBox> 가 명령 대상 명령이 실행 될 때 사용 하 여 명령을 처리할 수 있으므로 <xref:System.Windows.Input.CommandBinding> 컨트롤에 내장 되어 있습니다.  
  
 다음을 사용 하는 방법을 보여 줍니다는 <xref:System.Windows.Controls.MenuItem> 명령 원본으로는 <xref:System.Windows.Input.ApplicationCommands.Paste%2A> 명령, 여기서는 <xref:System.Windows.Controls.TextBox> 명령의 대상입니다.  정의 하는 모든 논리 방법을 <xref:System.Windows.Controls.TextBox> 수행 붙여넣기에 기본 제공 되는 <xref:System.Windows.Controls.TextBox> 제어 합니다.  
  
 A <xref:System.Windows.Controls.MenuItem> 만들어집니다 있고 그것이 <xref:System.Windows.Controls.MenuItem.Command%2A> 속성이로 설정 되는 <xref:System.Windows.Input.ApplicationCommands.Paste%2A> 명령입니다.  <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> 로 명시적으로 설정 되지 않은 <xref:System.Windows.Controls.TextBox> 개체입니다.  경우는 <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> 을 설정 하지 않으면 대상에 명령에 키보드 포커스가 있는 요소입니다.  키보드 포커스가 있는 요소를 지원 하지 않는 경우는 <xref:System.Windows.Input.ApplicationCommands.Paste%2A> 명령을 선택 하거나 (클립보드 비어 있음, 예를 들어) 붙여넣기 명령을 실행할 현재 없습니다 하면 <xref:System.Windows.Controls.MenuItem> 이 회색입니다.  
  
 [!code-xaml[MenuItemCommandTask_XAML#MenuItemCommanding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandTask_XAML/CS/Window1.xaml#menuitemcommanding)]  
  
 [!code-csharp[MenuItemCommandTask#MenuItemCommandingCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandTask/CSharp/Window1.xaml.cs#menuitemcommandingcodebehind)]
 [!code-vb[MenuItemCommandTask#MenuItemCommandingCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MenuItemCommandTask/VisualBasic/Window1.xaml.vb#menuitemcommandingcodebehind)]  
  
## <a name="see-also"></a>참고 항목  
 [명령 개요](../../../../docs/framework/wpf/advanced/commanding-overview.md)  
 [명령을 지원하지 않는 컨트롤에 명령 후크](../../../../docs/framework/wpf/advanced/how-to-hook-up-a-command-to-a-control-with-no-command-support.md)
