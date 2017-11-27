---
title: "포커스 개요"
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
- applications [WPF], focus
- focus in applications [WPF]
ms.assetid: 0230c4eb-0c8a-462b-ac4b-ae3e511659f4
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f4e10f7136b636829f99da34388db7676810cd06
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="focus-overview"></a>포커스 개요
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에는 포커스에 관한 두 가지 주요 개념이 있습니다. 즉, 키보드 포커스와 논리 포커스입니다.  키보드 포커스는 키보드 입력을 수신하는 요소를 나타내고 논리 포커스는 포커스가 있는 포커스 범위의 요소를 나타냅니다.  이러한 개념은 이 개요에서 자세히 설명합니다.  포커스를 얻을 수 있는 여러 영역이 있는 복잡한 응용 프로그램을 작성할 때 이 개념의 차이를 이해하는 것이 중요합니다.  
  
 포커스 관리에 참여 하는 주요 클래스는는 <xref:System.Windows.Input.Keyboard> 클래스는 <xref:System.Windows.Input.FocusManager> 클래스 및 기본 요소와 같은 클래스 <xref:System.Windows.UIElement> 및 <xref:System.Windows.ContentElement>합니다.  기본 요소에 대한 자세한 내용은 [기본 요소 개요](../../../../docs/framework/wpf/advanced/base-elements-overview.md)를 참조하세요.  
  
 <xref:System.Windows.Input.Keyboard> 클래스 키보드 포커스를 주로 우려 및 <xref:System.Windows.Input.FocusManager> 와 주로 논리적 포커스와 관련 있지만 절대 구분 하는 것은 아닙니다.  키보드 포커스가 있는 요소에는 논리 포커스도 있지만, 논리 포커스가 있는 요소에는 키보드 포커스가 없을 수도 있습니다.  사용 하는 경우이 명백한는 <xref:System.Windows.Input.Keyboard> 것에 대 한 키보드 포커스를 가진 요소를 설정 하는 클래스도 요소에 논리 포커스를 설정 합니다.  
  

  
<a name="Keyboard_Focus"></a>   
## <a name="keyboard-focus"></a>키보드 포커스  
 키보드 포커스는 현재 키보드 입력을 수신 중인 요소를 나타냅니다.  키보드 포커스가 있는 전체 데스크탑에는 요소가 하나뿐이어야 합니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], 키보드 포커스가 있는 요소에 포함 될 <xref:System.Windows.IInputElement.IsKeyboardFocused%2A> 로 설정 `true`합니다.  정적 속성 <xref:System.Windows.Input.Keyboard.FocusedElement%2A> 에 <xref:System.Windows.Input.Keyboard> 클래스 현재 키보드 포커스가 있는 요소를 가져옵니다.  
  
 키보드 포커스를 가져오려면 요소에 대 한 순서 대로 <xref:System.Windows.UIElement.Focusable%2A> 및 <xref:System.Windows.UIElement.IsVisible%2A> 기본 요소에 속성으로 설정 되어 있어야 `true`합니다.  와 같은 일부 클래스는 <xref:System.Windows.Controls.Panel> 기본 클래스, <xref:System.Windows.UIElement.Focusable%2A> 로 설정 `false` 기본적으로 따라서 설정 해야 <xref:System.Windows.UIElement.Focusable%2A> 를 `true` 이러한 요소에 키보드 포커스가 수 있게 되기를 원하는 경우.  
  
 키보드 포커스는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]와의 상호 작용을 통해 얻을 수 있습니다(예: 요소로 탭 이동 또는 특정 요소에서 마우스 클릭).  키보드 포커스를 사용 하 여 프로그래밍 방식으로 얻을 수도 있습니다는 <xref:System.Windows.Input.Keyboard.Focus%2A> 에서 메서드는 <xref:System.Windows.Input.Keyboard> 클래스입니다.  <xref:System.Windows.Input.Keyboard.Focus%2A> 메서드는 지정 된 요소가 키보드 포커스를 시도 합니다.  반환된 요소는 키보드 포커스가 있는 요소입니다. 이 요소는 이전 또는 새 포커스 개체가 요청을 차단하는 경우 요청된 요소와 다를 수 있습니다.  
  
 다음 예제에서는 <xref:System.Windows.Input.Keyboard.Focus%2A> 에 키보드 포커스를 설정 하는 메서드는 <xref:System.Windows.Controls.Button>합니다.  
  
 [!code-csharp[focussample#FocusSampleSetFocus](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FocusSample/CSharp/Window1.xaml.cs#focussamplesetfocus)]
 [!code-vb[focussample#FocusSampleSetFocus](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSample/visualbasic/window1.xaml.vb#focussamplesetfocus)]  
  
 <xref:System.Windows.UIElement.IsKeyboardFocused%2A> 기본 요소 클래스에 속성 요소에 키보드 포커스가 있는지 여부를 나타내는 값을 가져옵니다.  <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A> 기본 요소 클래스에 속성 요소 또는 시각적 자식 요소 중 하나에 키보드 포커스가 있는지 여부를 나타내는 값을 가져옵니다.  
  
 요소가 있어야 하 고 포커스를 받을 요소는 응용 프로그램에서 로드 하는 초기 창의 시각적 트리에 있어야 응용 프로그램 시작 시 초기 포커스를 설정할 때는 <xref:System.Windows.UIElement.Focusable%2A> 및 <xref:System.Windows.UIElement.IsVisible%2A> 로 설정 `true`합니다.  초기 포커스를 설정 하는 가장 좋은 위치는 <xref:System.Windows.FrameworkElement.Loaded> 이벤트 처리기입니다.  A <xref:System.Windows.Threading.Dispatcher> 콜백 호출 하 여 사용할 수도 있습니다 <xref:System.Windows.Threading.Dispatcher.Invoke%2A> 또는 <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A>합니다.  
  
<a name="Logical_Focus"></a>   
## <a name="logical-focus"></a>논리 포커스  
 논리 포커스를 참조 하는 <xref:System.Windows.Input.FocusManager.FocusedElement%2A?displayProperty=nameWithType> 포커스 범위 내에서.  포커스 범위는 추적 하는 요소는 <xref:System.Windows.Input.FocusManager.FocusedElement%2A> 해당 범위 내에서.  키보드 포커스가 포커스 범위를 벗어나면 포커스된 요소에서 키보드 포커스를 잃지만 논리 포커스는 유지합니다.  키보드 포커스가 포커스 범위로 돌아오면 포커스된 요소가 키보드 포커스를 얻습니다.  그러면 키보드 포커스가 여러 포커스 범위 간에 변경될 수 있지만, 포커스가 포커스 범위로 돌아가면 포커스 범위에 있는 포커스된 요소가 키보드 포커스를 다시 얻습니다.  
  
 응용 프로그램에 논리 포커스가 있는 요소는 여러 개일 수 있지만, 특정 포커스 범위에 논리 포커스가 있는 요소는 하나뿐일 수 있습니다.  
  
 키보드 포커스가 있는 요소에는 요소가 속해 있는 포커스 범위에 대한 논리 포커스가 있습니다.  
  
 요소에서 포커스 범위로 변환할 수 있습니다 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 설정 하 여는 <xref:System.Windows.Input.FocusManager> 연결 된 속성 <xref:System.Windows.Input.FocusManager.IsFocusScope%2A> 를 `true`합니다.  코드에서 요소로 변환할 수 있습니다 포커스 범위를 호출 하 여 <xref:System.Windows.Input.FocusManager.SetIsFocusScope%2A>합니다.  
  
 다음 예에서는 한 <xref:System.Windows.Controls.StackPanel> 설정 하 여 포커스 범위로 <xref:System.Windows.Input.FocusManager.IsFocusScope%2A> 연결 된 속성입니다.  
  
 [!code-xaml[MarkupSnippets#MarkupIsFocusScopeXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml#markupisfocusscopexaml)]  
  
 [!code-csharp[FocusSnippets#FocusSetIsFocusScope](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FocusSnippets/CSharp/Window1.xaml.cs#focussetisfocusscope)]
 [!code-vb[FocusSnippets#FocusSetIsFocusScope](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSnippets/visualbasic/window1.xaml.vb#focussetisfocusscope)]  
  
 <xref:System.Windows.Input.FocusManager.GetFocusScope%2A>지정된 된 요소에 대 한 포커스 범위를 반환합니다.  
  
 에 있는 클래스 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 는 기본적으로 포커스 범위인 <xref:System.Windows.Window>, <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.ToolBar>, 및 <xref:System.Windows.Controls.ContextMenu>합니다.  
  
 <xref:System.Windows.Input.FocusManager.GetFocusedElement%2A>지정한 포커스 범위에 대 한 포커스가 있는 요소를 가져옵니다.  <xref:System.Windows.Input.FocusManager.SetFocusedElement%2A>지정한 포커스 범위 내에서 포커스가 있는 요소를 설정합니다.  <xref:System.Windows.Input.FocusManager.SetFocusedElement%2A>초기 포커스가 있는 요소를 설정 하려면 일반적으로 사용 됩니다.  
  
 다음 예에서는 포커스 범위에서 포커스된 요소를 설정하고 포커스 범위의 포커스된 요소를 가져옵니다.  
  
 [!code-csharp[FocusSnippets#FocusGetSetFocusedElement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FocusSnippets/CSharp/Window1.xaml.cs#focusgetsetfocusedelement)]
 [!code-vb[FocusSnippets#FocusGetSetFocusedElement](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSnippets/visualbasic/window1.xaml.vb#focusgetsetfocusedelement)]  
  
<a name="Keyboard_Navigation"></a>   
## <a name="keyboard-navigation"></a>키보드 탐색  
 <xref:System.Windows.Input.KeyboardNavigation> 클래스는 탐색 키 중 하나를 누를 때 기본 키보드 포커스 탐색을 구현 해야 합니다.  탐색 키는 TAB, SHIFT+TAB, CTRL+TAB, CTRL+SHIFT+TAB, UPARROW, DOWNARROW, LEFTARROW 및 RIGHTARROW 키입니다.  
  
 연결 된 설정 하 여 탐색 컨테이너의 탐색 동작을 변경할 수 있습니다 <xref:System.Windows.Input.KeyboardNavigation> 속성 <xref:System.Windows.Input.KeyboardNavigation.TabNavigation%2A>, <xref:System.Windows.Input.KeyboardNavigation.ControlTabNavigation%2A>, 및 <xref:System.Windows.Input.KeyboardNavigation.DirectionalNavigation%2A>합니다.  이러한 속성은 형식의 <xref:System.Windows.Input.KeyboardNavigationMode> 가능한 값은 및 <xref:System.Windows.Input.KeyboardNavigationMode.Continue>, <xref:System.Windows.Input.KeyboardNavigationMode.Local>, <xref:System.Windows.Input.KeyboardNavigationMode.Contained>, <xref:System.Windows.Input.KeyboardNavigationMode.Cycle>, <xref:System.Windows.Input.KeyboardNavigationMode.Once>, 및 <xref:System.Windows.Input.KeyboardNavigationMode.None>합니다.  기본값은 <xref:System.Windows.Input.KeyboardNavigationMode.Continue>, 요소를 의미 하는 컨테이너가 아닌 탐색 합니다.  
  
 다음 예제에서는 한 <xref:System.Windows.Controls.Menu> 의 번호로 <xref:System.Windows.Controls.MenuItem> 개체입니다.  <xref:System.Windows.Input.KeyboardNavigation.TabNavigation%2A> 연결된 속성이로 설정 되어 <xref:System.Windows.Input.KeyboardNavigationMode.Cycle> 에 <xref:System.Windows.Controls.Menu>합니다.  내에서 tab 키를 사용 하 여 포커스를 변경 하는 경우는 <xref:System.Windows.Controls.Menu>, 포커스 각 요소에서 이동 하 고 마지막 요소에 도달할 때 되돌아갑니다 첫 번째 요소입니다.  
  
 [!code-xaml[MarkupSnippets#MarkupKeyboardNavigationTabNavigationXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml#markupkeyboardnavigationtabnavigationxaml)]  
  
 [!code-csharp[MarkupSnippets#MarkupKeyboardNavigationTabNavigationCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml.cs#markupkeyboardnavigationtabnavigationcode)]
 [!code-vb[MarkupSnippets#MarkupKeyboardNavigationTabNavigationCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MarkupSnippets/visualbasic/window1.xaml.vb#markupkeyboardnavigationtabnavigationcode)]  
  
<a name="Manipulating_Focus_Programmatically"></a>   
## <a name="navigating-focus-programmatically"></a>포커스를 프로그래밍 방식으로 탐색  
 추가 [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] 는 포커스 작업할 <xref:System.Windows.UIElement.MoveFocus%2A> 및 <xref:System.Windows.UIElement.PredictFocus%2A>합니다.  
  
 <xref:System.Windows.FrameworkElement.MoveFocus%2A>응용 프로그램의 다음 요소에 포커스를 변경 합니다.  A <xref:System.Windows.Input.TraversalRequest> 방향을 지정 하는 데 사용 됩니다.   <xref:System.Windows.Input.FocusNavigationDirection> 에 전달 된 <xref:System.Windows.UIElement.MoveFocus%2A> 방향을 포커스를 이동할 수 있는 같은 지정 <xref:System.Windows.Input.FocusNavigationDirection.First>, <xref:System.Windows.Input.FocusNavigationDirection.Last>, <xref:System.Windows.Input.FocusNavigationDirection.Up> 및 <xref:System.Windows.Input.FocusNavigationDirection.Down>합니다.  
  
 다음 예제에서는 <xref:System.Windows.FrameworkElement.MoveFocus%2A> 포커스가 있는 요소를 변경할 수 있습니다.  
  
 [!code-csharp[focussample#FocusSampleMoveFocus](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FocusSample/CSharp/Window1.xaml.cs#focussamplemovefocus)]
 [!code-vb[focussample#FocusSampleMoveFocus](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSample/visualbasic/window1.xaml.vb#focussamplemovefocus)]  
  
 <xref:System.Windows.FrameworkElement.PredictFocus%2A>포커스가 변경 될 경우 포커스를 받을 개체를 반환 합니다.  현재만 <xref:System.Windows.Input.FocusNavigationDirection.Up>, <xref:System.Windows.Input.FocusNavigationDirection.Down>, <xref:System.Windows.Input.FocusNavigationDirection.Left>, 및 <xref:System.Windows.Input.FocusNavigationDirection.Right> 에서 지 원하는 <xref:System.Windows.FrameworkElement.PredictFocus%2A>합니다.  
  
<a name="Focus_Events"></a>   
## <a name="focus-events"></a>포커스 이벤트  
 키보드 포커스와 관련 된 이벤트는 <xref:System.Windows.Input.Keyboard.PreviewGotKeyboardFocus>, <xref:System.Windows.Input.Keyboard.GotKeyboardFocus> 및 <xref:System.Windows.Input.Keyboard.PreviewLostKeyboardFocus>, <xref:System.Windows.Input.Keyboard.LostKeyboardFocus>합니다.  이벤트에 연결 된 이벤트로 정의 된는 <xref:System.Windows.Input.Keyboard> 클래스 같지만 기본 요소 클래스에 해당 하는 라우트된 이벤트로 보다 쉽게 액세스할 수 있습니다.  이벤트에 대한 자세한 내용은 [라우트된 이벤트 개요](../../../../docs/framework/wpf/advanced/routed-events-overview.md)를 참조하세요.  
  
 <xref:System.Windows.Input.Keyboard.GotKeyboardFocus>요소가 키보드 포커스를 받을 때 발생 합니다.  <xref:System.Windows.Input.Keyboard.LostKeyboardFocus>요소가 키보드 포커스를 잃을 때 발생 합니다.  경우는 <xref:System.Windows.Input.Keyboard.PreviewGotKeyboardFocus> 이벤트 또는 <xref:System.Windows.Input.Keyboard.PreviewLostKeyboardFocusEvent> 이벤트를 처리 하 고 <xref:System.Windows.RoutedEventArgs.Handled%2A> 로 설정 된 `true`, 다음 포커스 변경 되지 것입니다.  
  
 다음 예제에서는 연결 <xref:System.Windows.UIElement.GotKeyboardFocus> 및 <xref:System.Windows.UIElement.LostKeyboardFocus> 에 이벤트 처리기는 <xref:System.Windows.Controls.TextBox>합니다.  
  
 [!code-xaml[keyboardsample#KeyboardSampleXAMLHandlerHookup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml#keyboardsamplexamlhandlerhookup)]  
  
 때는 <xref:System.Windows.Controls.TextBox> 키보드 포커스를 받을 <xref:System.Windows.Controls.Control.Background%2A> 의 속성은 <xref:System.Windows.Controls.TextBox> 로 변경 <xref:System.Windows.Media.Brushes.LightBlue%2A>합니다.  
  
 [!code-csharp[keyboardsample#KeyboardSampleGotFocus](../../../../samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml.cs#keyboardsamplegotfocus)]
 [!code-vb[keyboardsample#KeyboardSampleGotFocus](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/KeyboardSample/visualbasic/window1.xaml.vb#keyboardsamplegotfocus)]  
  
 경우는 <xref:System.Windows.Controls.TextBox> 키보드 포커스를 잃을 <xref:System.Windows.Controls.Control.Background%2A> 의 속성은 <xref:System.Windows.Controls.TextBox> 다시 흰색으로 변경 합니다.  
  
 [!code-csharp[keyboardsample#KeyboardSampleLostFocus](../../../../samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml.cs#keyboardsamplelostfocus)]
 [!code-vb[keyboardsample#KeyboardSampleLostFocus](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/KeyboardSample/visualbasic/window1.xaml.vb#keyboardsamplelostfocus)]  
  
 논리 포커스와 관련 된 이벤트는 <xref:System.Windows.UIElement.GotFocus> 및 <xref:System.Windows.UIElement.LostFocus>합니다.  이러한 이벤트에 정의 된는 <xref:System.Windows.Input.FocusManager> 연결 된 이벤트로만 <xref:System.Windows.Input.FocusManager> CLR 이벤트 래퍼를 노출 하지 않습니다.  <xref:System.Windows.UIElement>및 <xref:System.Windows.ContentElement> 더 편리 하 게 이러한 이벤트를 노출 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Input.FocusManager>  
 <xref:System.Windows.UIElement>  
 <xref:System.Windows.ContentElement>  
 [입력 개요](../../../../docs/framework/wpf/advanced/input-overview.md)  
 [기본 요소 개요](../../../../docs/framework/wpf/advanced/base-elements-overview.md)
