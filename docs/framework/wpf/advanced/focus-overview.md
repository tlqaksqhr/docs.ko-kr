---
title: "포커스 개요 | Microsoft Docs"
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
  - "응용 프로그램, 포커스"
  - "응용 프로그램의 포커스"
ms.assetid: 0230c4eb-0c8a-462b-ac4b-ae3e511659f4
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# 포커스 개요
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에는 포커스와 관련된 두 가지 주요 개념인 키보드 포커스와 논리적 포커스가 있습니다.  키보드 포커스는 키보드 입력을 받는 요소를 가리키고 논리적 포커스는 포커스 범위 내에서 포커스가 있는 요소를 가리킵니다.  이 개요 부분에서는 이러한 개념에 대해 자세하게 설명합니다.  포커스를 가질 수 있는 영역이 여러 개 포함된 복잡한 응용 프로그램을 만들 경우에는 이 두 개념의 차이를 이해하는 것이 중요합니다.  
  
 포커스 관리와 관련된 주요 클래스로는 <xref:System.Windows.Input.Keyboard> 클래스, <xref:System.Windows.Input.FocusManager> 클래스 및 <xref:System.Windows.UIElement>와 <xref:System.Windows.ContentElement> 같은 기본 요소 클래스가 있습니다.  기본 요소에 대한 자세한 내용은 [기본 요소 개요](../../../../docs/framework/wpf/advanced/base-elements-overview.md)를 참조하십시오.  
  
 <xref:System.Windows.Input.Keyboard> 클래스는 주로 키보드 포커스와 관련되고 <xref:System.Windows.Input.FocusManager>는 주로 논리적 포커스와 관련되지만 그 사용 영역이 명확하게 구분되는 것은 아닙니다.  키보드 포커스가 있는 요소에는 논리적 포커스도 있지만 논리적 포커스가 있는 요소에는 키보드 포커스가 없을 수 있습니다.  <xref:System.Windows.Input.Keyboard> 클래스를 사용하여 키보드 포커스가 있는 요소를 설정하면 해당 요소에 논리적 포커스도 설정되기 때문에 이 차이를 확실하게 알 수 있습니다.  
  
   
  
<a name="Keyboard_Focus"></a>   
## 키보드 포커스  
 키보드 포커스는 현재 키보드 입력을 받고 있는 요소를 가리킵니다.  바탕 화면에서 하나의 요소만 키보드 포커스를 가질 수 있습니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 키보드 포커스를 갖는 요소에는 <xref:System.Windows.IInputElement.IsKeyboardFocused%2A>가 `true`로 설정됩니다.  <xref:System.Windows.Input.Keyboard> 클래스의 정적 속성 <xref:System.Windows.Input.Keyboard.FocusedElement%2A>는 현재 키보드 포커스가 있는 요소를 가져옵니다.  
  
 요소가 키보드 포커스를 가지려면 기본 요소의 <xref:System.Windows.UIElement.Focusable%2A> 속성과 <xref:System.Windows.UIElement.IsVisible%2A> 속성이 `true`로 설정되어야 합니다.  <xref:System.Windows.Controls.Panel> 기본 클래스와 같은 일부 클래스는 <xref:System.Windows.UIElement.Focusable%2A>이 기본적으로 `false`로 설정되기 때문에 이러한 요소가 키보드 포커스를 받을 수 있으려면 <xref:System.Windows.UIElement.Focusable%2A>을 `true`로 직접 설정해야 합니다.  
  
 키보드 포커스는 탭을 사용하여 요소로 이동하거나 특정 요소를 마우스로 클릭하는 등의 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]의 사용자 상호 작용을 통해 설정할 수 있습니다.  또는 <xref:System.Windows.Input.Keyboard> 클래스에서 <xref:System.Windows.Input.Keyboard.Focus%2A> 메서드를 사용하여 프로그래밍 방식으로 키보드 포커스를 설정할 수도 있습니다.  <xref:System.Windows.Input.Keyboard.Focus%2A> 메서드는 지정한 요소에 키보드 포커스를 설정하려고 시도합니다.  이 메서드는 키보드 포커스가 있는 요소를 반환하지만, 이전 포커스 개체나 새 포커스 개체가 요청을 차단한 경우에는 원래 요청한 요소가 아닌 다른 요소가 반환될 수도 있습니다.  
  
 다음 예제에서는 <xref:System.Windows.Input.Keyboard.Focus%2A> 메서드를 사용하여 <xref:System.Windows.Controls.Button>에 키보드 포커스를 설정합니다.  
  
 [!code-csharp[focussample#FocusSampleSetFocus](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FocusSample/CSharp/Window1.xaml.cs#focussamplesetfocus)]
 [!code-vb[focussample#FocusSampleSetFocus](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSample/visualbasic/window1.xaml.vb#focussamplesetfocus)]  
  
 기본 요소 클래스의 <xref:System.Windows.UIElement.IsKeyboardFocused%2A> 속성은 요소에 키보드 포커스가 있는지 여부를 나타내는 값을 가져옵니다.  기본 요소 클래스의 <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A> 속성은 요소 또는 해당 요소의 시각적 자식 요소 중 하나에 키보드 포커스가 있는지 여부를 나타내는 값을 가져옵니다.  
  
 응용 프로그램 시작 시 초기 포커스를 설정하는 경우 포커스를 받을 요소는 응용 프로그램이 로드하는 초기 창의 시각적 트리에 있어야 하고 요소의 <xref:System.Windows.UIElement.Focusable%2A> 및 <xref:System.Windows.UIElement.IsVisible%2A>은 `true`로 설정되어 있어야 합니다.  초기 포커스를 설정하기 가장 좋은 위치는 <xref:System.Windows.FrameworkElement.Loaded> 이벤트 처리기입니다.  <xref:System.Windows.Threading.Dispatcher.Invoke%2A> 또는 <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A>를 호출하여 <xref:System.Windows.Threading.Dispatcher> 콜백을 사용할 수도 있습니다.  
  
<a name="Logical_Focus"></a>   
## 논리적인 포커스  
 논리적인 포커스는 포커스 범위 내의 <xref:System.Windows.Input.FocusManager.FocusedElement%2A?displayProperty=fullName>를 말합니다.  포커스 범위는 범위 내에서 <xref:System.Windows.Input.FocusManager.FocusedElement%2A>를 추적하는 요소입니다.  키보드 포커스가 포커스 범위를 벗어나면 포커스가 있는 요소는 키보드 포커스를 잃지만 논리적 포커스는 그대로 유지합니다.  키보드 포커스가 포커스 범위로 다시 돌아가면 포커스가 있는 요소에 키보드 포커스가 설정됩니다.  이렇게 하면 여러 포커스 범위 사이에서 키보드 포커스가 변경되더라도 포커스 범위에 포커스가 다시 돌아왔을 때 포커스 범위 내에서 포커스가 있는 요소가 키보드 포커스를 다시 받을 수 있습니다.  
  
 응용 프로그램에서 여러 요소가 논리적인 포커스를 가질 수 있지만 특정 포커스 범위 내에서 하나의 요소만 논리적인 포커스를 가질 수 있습니다.  
  
 키보드 포커스가 있는 요소는 해당 요소가 속한 포커스 범위에서 논리적 포커스도 가집니다.  
  
 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]에서 <xref:System.Windows.Input.FocusManager> 연결 속성 <xref:System.Windows.Input.FocusManager.IsFocusScope%2A>를 `true`로 설정하면 요소를 포커스 범위로 만들 수 있습니다.  코드에서는 <xref:System.Windows.Input.FocusManager.SetIsFocusScope%2A>를 호출하여 요소를 포커스 범위로 만들 수 있습니다.  
  
 다음 예제에서는 연결된 속성 <xref:System.Windows.Input.FocusManager.IsFocusScope%2A>를 설정하여 <xref:System.Windows.Controls.StackPanel>을 포커스 범위로 만듭니다.  
  
 [!code-xml[MarkupSnippets#MarkupIsFocusScopeXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml#markupisfocusscopexaml)]  
  
 [!code-csharp[FocusSnippets#FocusSetIsFocusScope](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FocusSnippets/CSharp/Window1.xaml.cs#focussetisfocusscope)]
 [!code-vb[FocusSnippets#FocusSetIsFocusScope](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSnippets/visualbasic/window1.xaml.vb#focussetisfocusscope)]  
  
 <xref:System.Windows.Input.FocusManager.GetFocusScope%2A>는 지정한 요소의 포커스 범위를 반환합니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 <xref:System.Windows.Window>, <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.ToolBar> 및 <xref:System.Windows.Controls.ContextMenu> 클래스는 기본적으로 포커스 범위입니다.  
  
 <xref:System.Windows.Input.FocusManager.GetFocusedElement%2A>는 지정된 포커스 범위에서 포커스가 있는 요소를 가져오고,  <xref:System.Windows.Input.FocusManager.SetFocusedElement%2A>는 지정된 포커스 범위에서 포커스가 있는 요소를 설정합니다.  <xref:System.Windows.Input.FocusManager.SetFocusedElement%2A>는 일반적으로 처음 포커스가 있는 요소를 설정하는 데 사용됩니다.  
  
 다음 예제에서는 포커스 범위에서 포커스가 있는 요소를 설정하고, 포커스 범위에서 포커스가 있는 요소를 가져옵니다.  
  
 [!code-csharp[FocusSnippets#FocusGetSetFocusedElement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FocusSnippets/CSharp/Window1.xaml.cs#focusgetsetfocusedelement)]
 [!code-vb[FocusSnippets#FocusGetSetFocusedElement](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSnippets/visualbasic/window1.xaml.vb#focusgetsetfocusedelement)]  
  
<a name="Keyboard_Navigation"></a>   
## 키보드 탐색  
 <xref:System.Windows.Input.KeyboardNavigation> 클래스는 탐색 키 중 하나를 누른 경우 기본 키보드 포커스 탐색을 구현합니다.  탐색 키로는 Tab, Shift\+Tab, Ctrl\+Tab, Ctrl\+Shift\+Tab, UpArrow, DownArrow, LeftArrow 및 RightArrow 키가 있습니다.  
  
 탐색 컨테이너의 탐색 동작은 연결된 <xref:System.Windows.Input.KeyboardNavigation> 속성인 <xref:System.Windows.Input.KeyboardNavigation.TabNavigation%2A>, <xref:System.Windows.Input.KeyboardNavigation.ControlTabNavigation%2A> 및 <xref:System.Windows.Input.KeyboardNavigation.DirectionalNavigation%2A>을 설정하여 변경할 수 있습니다.  이러한 속성의 형식은 <xref:System.Windows.Input.KeyboardNavigationMode>이며 가능한 값은 <xref:System.Windows.Input.KeyboardNavigationMode>, <xref:System.Windows.Input.KeyboardNavigationMode>, <xref:System.Windows.Input.KeyboardNavigationMode>, <xref:System.Windows.Input.KeyboardNavigationMode>, <xref:System.Windows.Input.KeyboardNavigationMode> 및 <xref:System.Windows.Input.KeyboardNavigationMode>입니다.  기본값은 <xref:System.Windows.Input.KeyboardNavigationMode>이며, 이는 요소가 탐색 컨테이너가 아님을 의미합니다.  
  
 다음 예제에서는 <xref:System.Windows.Controls.MenuItem> 개체가 여러 개 있는 <xref:System.Windows.Controls.Menu>를 만듭니다.  <xref:System.Windows.Controls.Menu>에서 <xref:System.Windows.Input.KeyboardNavigation.TabNavigation%2A> 연결된 속성은 <xref:System.Windows.Input.KeyboardNavigationMode>로 설정되어 있습니다.  <xref:System.Windows.Controls.Menu> 내에서 탭 키를 사용하여 포커스를 변경하면 포커스가 각 요소에서 차례로 이동하고 마지막 요소에 도달하면 첫 번째 요소로 되돌아갑니다.  
  
 [!code-xml[MarkupSnippets#MarkupKeyboardNavigationTabNavigationXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml#markupkeyboardnavigationtabnavigationxaml)]  
  
 [!code-csharp[MarkupSnippets#MarkupKeyboardNavigationTabNavigationCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml.cs#markupkeyboardnavigationtabnavigationcode)]
 [!code-vb[MarkupSnippets#MarkupKeyboardNavigationTabNavigationCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MarkupSnippets/visualbasic/window1.xaml.vb#markupkeyboardnavigationtabnavigationcode)]  
  
<a name="Manipulating_Focus_Programmatically"></a>   
## 프로그래밍 방식으로 포커스 탐색  
 <xref:System.Windows.UIElement.MoveFocus%2A>와 <xref:System.Windows.UIElement.PredictFocus%2A>는 포커스로 작업하는 데 사용할 수 있는 추가적인 [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)]입니다.  
  
 <xref:System.Windows.FrameworkElement.MoveFocus%2A>는 응용 프로그램의 다음 요소로 포커스를 변경합니다.  이때 <xref:System.Windows.Input.TraversalRequest>는 방향을 지정하는 데 사용됩니다.  <xref:System.Windows.UIElement.MoveFocus%2A>에 전달되는 <xref:System.Windows.Input.FocusNavigationDirection>은 <xref:System.Windows.Input.FocusNavigationDirection>, <xref:System.Windows.Input.FocusNavigationDirection>, <xref:System.Windows.Input.FocusNavigationDirection>, <xref:System.Windows.Input.FocusNavigationDirection> 등 포커스를 이동할 수 있는 여러 방향을 지정합니다.  
  
 다음 예제에서는 <xref:System.Windows.FrameworkElement.MoveFocus%2A>를 사용하여 포커스가 있는 요소를 변경합니다.  
  
 [!code-csharp[focussample#FocusSampleMoveFocus](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FocusSample/CSharp/Window1.xaml.cs#focussamplemovefocus)]
 [!code-vb[focussample#FocusSampleMoveFocus](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSample/visualbasic/window1.xaml.vb#focussamplemovefocus)]  
  
 <xref:System.Windows.FrameworkElement.PredictFocus%2A>는 포커스를 변경할 경우 포커스를 받게 될 개체를 반환합니다.  현재 <xref:System.Windows.FrameworkElement.PredictFocus%2A>에는 <xref:System.Windows.Input.FocusNavigationDirection>, <xref:System.Windows.Input.FocusNavigationDirection>, <xref:System.Windows.Input.FocusNavigationDirection> 및 <xref:System.Windows.Input.FocusNavigationDirection>만 지원됩니다.  
  
<a name="Focus_Events"></a>   
## 포커스 이벤트  
 키보드 포커스와 관련된 이벤트로는 <xref:System.Windows.Input.Keyboard.PreviewGotKeyboardFocus>, <xref:System.Windows.Input.Keyboard.GotKeyboardFocus>, <xref:System.Windows.Input.Keyboard.PreviewLostKeyboardFocus> 및 <xref:System.Windows.Input.Keyboard.LostKeyboardFocus>가 있습니다.  이벤트는 <xref:System.Windows.Input.Keyboard> 클래스에 연결된 이벤트로 정의되지만 기본 요소 클래스에서 이에 해당되는 라우트된 이벤트로 더 쉽게 액세스할 수 있습니다.  이벤트에 대한 자세한 내용은 [라우트된 이벤트 개요](../../../../docs/framework/wpf/advanced/routed-events-overview.md)를 참조하십시오.  
  
 <xref:System.Windows.Input.Keyboard.GotKeyboardFocus>는 요소가 키보드 포커스를 받을 때 발생하고,  <xref:System.Windows.Input.Keyboard.LostKeyboardFocus>는 요소가 키보드 포커스를 잃을 때 발생합니다.  <xref:System.Windows.Input.Keyboard.PreviewGotKeyboardFocus> 이벤트 또는 <xref:System.Windows.Input.Keyboard.PreviewLostKeyboardFocusEvent> 이벤트가 처리될 때 <xref:System.Windows.RoutedEventArgs.Handled%2A>가 `true`로 설정되어 있으면 포커스가 변경되지 않습니다.  
  
 다음 예제에서는 <xref:System.Windows.Controls.TextBox>에 <xref:System.Windows.UIElement.GotKeyboardFocus> 및 <xref:System.Windows.UIElement.LostKeyboardFocus> 이벤트 처리기를 연결합니다.  
  
 [!code-xml[keyboardsample#KeyboardSampleXAMLHandlerHookup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml#keyboardsamplexamlhandlerhookup)]  
  
 <xref:System.Windows.Controls.TextBox>가 키보드 포커스를 받으면 <xref:System.Windows.Controls.TextBox>의 <xref:System.Windows.Controls.Control.Background%2A> 속성이 <xref:System.Windows.Media.Brushes.LightBlue%2A>로 변경됩니다.  
  
 [!code-csharp[keyboardsample#KeyboardSampleGotFocus](../../../../samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml.cs#keyboardsamplegotfocus)]
 [!code-vb[keyboardsample#KeyboardSampleGotFocus](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/KeyboardSample/visualbasic/window1.xaml.vb#keyboardsamplegotfocus)]  
  
 <xref:System.Windows.Controls.TextBox>가 키보드 포커스를 잃으면 <xref:System.Windows.Controls.TextBox>의 <xref:System.Windows.Controls.Control.Background%2A> 속성이 다시 흰색으로 변경됩니다.  
  
 [!code-csharp[keyboardsample#KeyboardSampleLostFocus](../../../../samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml.cs#keyboardsamplelostfocus)]
 [!code-vb[keyboardsample#KeyboardSampleLostFocus](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/KeyboardSample/visualbasic/window1.xaml.vb#keyboardsamplelostfocus)]  
  
 논리적 포커스와 관련된 이벤트로는 <xref:System.Windows.UIElement.GotFocus>와 <xref:System.Windows.UIElement.LostFocus>가 있습니다.  이 두 이벤트는 <xref:System.Windows.Input.FocusManager>에 연결된 이벤트로 정의되지만 <xref:System.Windows.Input.FocusManager>는 CLR 이벤트 래퍼를 노출하지 않습니다.  대신 <xref:System.Windows.UIElement> 및 <xref:System.Windows.ContentElement>에서 이러한 이벤트를 노출하므로 더욱 편리합니다.  
  
## 참고 항목  
 <xref:System.Windows.Input.FocusManager>   
 <xref:System.Windows.UIElement>   
 <xref:System.Windows.ContentElement>   
 [입력 개요](../../../../docs/framework/wpf/advanced/input-overview.md)   
 [기본 요소 개요](../../../../docs/framework/wpf/advanced/base-elements-overview.md)