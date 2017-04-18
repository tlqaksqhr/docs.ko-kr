---
title: "입력 개요 | Microsoft Docs"
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
  - "명령[WPF]"
  - "개요, 입력 [WPF]"
  - "키보드 포커스[WPF]"
  - "키보드 입력[WPF]"
  - "터치 이벤트[WPF]"
  - "이벤트 라우팅[WPF]"
  - "터치식 입력[WPF]"
  - "조작[WPF]"
  - "논리 포커스[WPF]"
  - "스타일러스 입력[WPF]"
  - "텍스트 입력[WPF]"
  - "처리 입력된 이벤트 [WPF]"
  - "WPF에서 입력된 개요"
  - "조작 이벤트[WPF]"
  - "마우스 입력[WPF]"
  - "마우스 캡처[WPF]"
  - "포커스[WPF]"
  - "마우스 위치[WPF]"
ms.assetid: ee5258b7-6567-415a-9b1c-c0cbe46e79ef
caps.latest.revision: 50
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 50
---
# 입력 개요
<a name="introduction"></a>[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 하위 시스템은 강력한 제공 [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] 다양 한 장치에서에서 입력을 가져오는, 마우스, 키보드, 터치 및 스타일러스를 포함 합니다. 이 항목에서 제공 하는 서비스에 설명 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 입력된 시스템의 아키텍처에 설명 합니다.  
  
  
<a name="input_api"></a>   
## <a name="input-api"></a>입력 API  
 기본 입력 [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] 기본 요소 클래스에 노출 됩니다: <xref:System.Windows.UIElement>, <xref:System.Windows.ContentElement>, <xref:System.Windows.FrameworkElement>, 및 <xref:System.Windows.FrameworkContentElement>합니다.  기본 요소에 대 한 자세한 내용은 참조 [기본 요소 개요](../../../../docs/framework/wpf/advanced/base-elements-overview.md)합니다.  이러한 클래스는 키 누름, 마우스 단추, 마우스 휠, 마우스 이동, 포커스 관리 및 마우스 캡처 등과 관련 된 입력된 이벤트에 대 한 기능을 제공 합니다. 입력을 배치 하 여 [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] 기본 요소에 처리 하는 대신 모든 입력 이벤트는 서비스, 입력된 아키텍처는 UI에서 특정 개체에 의해 제공 하 고 둘 이상의 요소가 입력된 이벤트를 처리 하는 이벤트 라우팅 체계를 지원 하기 위해 입력된 이벤트를 사용 합니다. 대부분의 입력된 이벤트 관련 된 이벤트는 포함 합니다.  예를 들어 키 이벤트과 연관 된 <xref:System.Windows.Input.Keyboard.KeyDown> 및 <xref:System.Windows.Input.Keyboard.PreviewKeyDown> 이벤트입니다.  어떻게 라우팅될 때 대상 요소에 이러한 이벤트에 차이가 있습니다.  미리 보기는 요소 트리의 루트 요소에서 대상 요소 이벤트 터널 합니다.  이벤트 버블링 대상 요소에서 루트 요소에 전달 합니다.  이벤트 라우팅에 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 및이 개요의 뒷부분에 자세히 설명 되어는 [라우트된 이벤트 개요](../../../../docs/framework/wpf/advanced/routed-events-overview.md)합니다.  
  
### <a name="keyboard-and-mouse-classes"></a>키보드 및 마우스 클래스  
 입력 외에도 [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] 기본 요소 클래스에는 <xref:System.Windows.Input.Keyboard> 클래스 및 <xref:System.Windows.Input.Mouse> 클래스는 추가 제공 [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] 키보드 및 마우스 입력을 사용 합니다.  
  
 입력의 예 [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] 에 <xref:System.Windows.Input.Keyboard> 클래스는 <xref:System.Windows.Input.Keyboard.Modifiers%2A> 반환 하는 속성을는 <xref:System.Windows.Input.ModifierKeys> 현재 누른 및 <xref:System.Windows.Input.Keyboard.IsKeyDown%2A> 지정된 된 키를 눌렀는지 여부를 결정 하는 방법입니다.  
  
 다음 예제에서는 <xref:System.Windows.Input.Keyboard.GetKeyStates%2A> 여부를 확인 하는 메서드는 <xref:System.Windows.Input.Key> 아래쪽 상태입니다.  
  
 [!code-csharp[keyargssnippetsample#KeyEventArgsKeyBoardGetKeyStates](../../../../samples/snippets/csharp/VS_Snippets_Wpf/KeyArgsSnippetSample/CSharp/Window1.xaml.cs#keyeventargskeyboardgetkeystates)]
 [!code-vb[keyargssnippetsample#KeyEventArgsKeyBoardGetKeyStates](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/KeyArgsSnippetSample/visualbasic/window1.xaml.vb#keyeventargskeyboardgetkeystates)]  
  
 입력의 예 [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] 에 <xref:System.Windows.Input.Mouse> 클래스는 <xref:System.Windows.Input.Mouse.MiddleButton%2A>, 마우스 가운데 단추의 상태를 가져오는 및 <xref:System.Windows.Input.Mouse.DirectlyOver%2A>를 통해 현재는 마우스 포인터의 요소를 가져옵니다.  
  
 다음 예제에서는 확인 여부는 <xref:System.Windows.Input.Mouse.LeftButton%2A> 마우스가는 <xref:System.Windows.Input.MouseButtonState> 상태입니다.  
  
 [!code-csharp[mouserelatedsnippets#MouseRelatedSnippetsGetLeftButtonMouse](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MouseRelatedSnippets/CSharp/Window1.xaml.cs#mouserelatedsnippetsgetleftbuttonmouse)]
 [!code-vb[mouserelatedsnippets#MouseRelatedSnippetsGetLeftButtonMouse](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MouseRelatedSnippets/visualbasic/window1.xaml.vb#mouserelatedsnippetsgetleftbuttonmouse)]  
  
 <xref:System.Windows.Input.Mouse> 및 <xref:System.Windows.Input.Keyboard> 클래스가이 개요 항목에서 자세히 설명 되어 있습니다.  
  
### <a name="stylus-input"></a>스타일러스 입력  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에 대 한 지원이 통합 되어는 <xref:System.Windows.Input.Stylus>합니다.  <xref:System.Windows.Input.Stylus> 에 널리 사용 되는 펜 입력는 [!INCLUDE[TLA#tla_tpc](../../../../includes/tlasharptla-tpc-md.md)]합니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]응용 프로그램으로 처리할 수 스타일러스 마우스 마우스를 사용 하 여 [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)], 하지만 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 키보드 및 마우스와 비슷한 모델을 사용 하는 스타일러스 장치 추상화를 제공 합니다.  스타일러스를 모든 관련 [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] "스타일러스" 라는 단어를 포함 합니다.  
  
 스타일러스 수 마우스 역할을 하기 때문에 마우스 입력을 지 원하는 응용 프로그램 여전히 얻을 수 일정 수준의 스타일러스 지원 자동으로. 스타일러스를 이러한 방식으로 사용 하는 경우 응용 프로그램 기회가 적절 한 스타일러스 이벤트를 처리 하는 하 고 해당 마우스 이벤트를 처리 합니다. 또한 잉크 입력 등의 더 높은 수준의 서비스 스타일러스 장치 추상화를 통해 사용할 수 있습니다.  입력으로 잉크에 대 한 자세한 내용은 참조 [잉크 시작](../../../../docs/framework/wpf/advanced/getting-started-with-ink.md)합니다.  
  
<a name="event_routing"></a>   
## <a name="event-routing"></a>이벤트 라우팅  
 A <xref:System.Windows.FrameworkElement> 요소 트리를 형성 하는 콘텐츠 모델에 대 한 자식 요소로 다른 요소를 포함할 수 있습니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], 부모 요소는 입력 이벤트를 처리 하 여 해당 자식 요소 또는 다른 하위 요소를 대상에 참여할 수 있습니다. 이 프로세스를 "컨트롤 컴퍼지션" 또는 "합성 합니다." 라고 더 작은 컨트롤에서 컨트롤을 빌드하는 데 특히 유용 요소 트리 및 이벤트 경로가 요소 트리 간의 관계에 대 한 자세한 내용은 참조 [WPF의 트리](../../../../docs/framework/wpf/advanced/trees-in-wpf.md)합니다.  
  
 이벤트 라우팅의 목적은 여러 요소에 이벤트를 전달할 특정 개체 또는 경로 상의 한 요소가 다른 요소에 의해 발생 시킨 이벤트에 처리를 통해 의미 있는 응답을 제공 하도록 선택할 수 있도록 합니다.  라우트된 이벤트 세 가지 라우팅 메커니즘 중 하나를 사용 합니다: 직접, 버블링 및 터널링 합니다.  직접 라우팅에서 소스 요소 알림을 받지 못하고, 단일 요소가 고 다른 요소에 이벤트 라우팅되지 않습니다. 그러나 직접 라우트된 이벤트 몇 가지 추가 기능을 제공 표준와는 달리 라우트된 이벤트에 대 한 존재 하는 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 이벤트입니다. 버블링 알림으로써 첫 번째 요소에 다음 이벤트를 알린 부모 요소와 등의 요소 트리를 작동 합니다.  터널링 요소 트리의 루트에서 시작 하며 원래 소스 요소까지 아래쪽으로 작동 합니다.  라우트된 이벤트에 대 한 자세한 내용은 참조 [라우트된 이벤트 개요](../../../../docs/framework/wpf/advanced/routed-events-overview.md)합니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]일반적으로 입력된 이벤트 버블링 이벤트 및 터널링 이벤트로 구성 된 쌍으로 제공 합니다.  터널링 이벤트에서 "Preview" 접두사가 포함 된 이벤트 버블링 구별 됩니다.  예를 들어, <xref:System.Windows.Input.Mouse.PreviewMouseMove> 은 마우스 이동 이벤트의 터널링 버전 및 <xref:System.Windows.Input.Mouse.MouseMove> 이 이벤트의 버블링 버전입니다. 이 이벤트 쌍은 요소 수준에서 구현 되 고는 내재 된 기능을 포함 하는 규칙은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 이벤트 시스템입니다. 자세한 내용은의 WPF 입력 이벤트 섹션을 참조 [라우트된 이벤트 개요](../../../../docs/framework/wpf/advanced/routed-events-overview.md)합니다.  
  
<a name="handling_input_events"></a>   
## <a name="handling-input-events"></a>입력된 이벤트 처리  
 요소에서 입력을 받으려면 이벤트 처리기는 특정 이벤트와 연결 되어야 합니다.  [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 이 작업은 간단 합니다:이 이벤트를 수신 하는 요소의 특성으로 이벤트의 이름을 참조 합니다.  그런 다음 대리자 기반을 정의 하는 이벤트 처리기의 이름으로 특성의 값을 설정할 수 있습니다.  코드에서와 같은 이벤트 처리기를 작성 해야 [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] 코드 숨김 파일에 포함 될 수 있습니다.  
  
 키보드 이벤트에는 운영 체제 보고서 요소에 키보드 포커스가 있을 때 발생 하는 주요 작업 하는 경우 발생 합니다. 마우스 및 스타일러스 이벤트는 각각 두 가지 범주로 나뉩니다: 요소를 기준으로 포인터 위치에 변경 내용을 보고 하는 이벤트 및 보고서에서 장치 단추의 상태를 변경 하는 이벤트입니다.  
  
### <a name="keyboard-input-event-example"></a>키보드 입력된 이벤트 예제  
 다음 예제에서는 왼쪽된 화살표 키 누름에 대 한 수신 대기합니다.  A <xref:System.Windows.Controls.StackPanel> 만들어집니다에 <xref:System.Windows.Controls.Button>합니다.  왼쪽된 화살표 키 누름에 연결 된 수신 하는 이벤트 처리기는 <xref:System.Windows.Controls.Button> 인스턴스.  
  
 예의 첫 번째 섹션에서는 만들고는 <xref:System.Windows.Controls.StackPanel> 및 <xref:System.Windows.Controls.Button> 에 대 한 이벤트 처리기를 연결 하 고는 <xref:System.Windows.UIElement.KeyDown>합니다.  
  
 [!code-xml[InputOvw#Input_OvwKeyboardExampleXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml#input_ovwkeyboardexamplexaml)]  
  
 [!code-csharp[InputOvw#Input_OvwKeyboardExampleUICodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml.cs#input_ovwkeyboardexampleuicodebehind)]
 [!code-vb[InputOvw#Input_OvwKeyboardExampleUICodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InputOvw/VisualBasic/Page1.xaml.vb#input_ovwkeyboardexampleuicodebehind)]  
  
 두 번째 섹션은 코드로 작성 하 고 이벤트 처리기를 정의 합니다.  왼쪽된 화살표 키를 누를 때 및 <xref:System.Windows.Controls.Button> 키보드 포커스가 처리기가 실행 및 <xref:System.Windows.Controls.Control.Background%2A> 의 색은 <xref:System.Windows.Controls.Button> 변경 됩니다.  키를 누르면 있지만 왼쪽된 화살표 키, 없는 경우는 <xref:System.Windows.Controls.Control.Background%2A> 의 색은 <xref:System.Windows.Controls.Button> 다시 시작 색으로 변경 됩니다.  
  
 [!code-csharp[InputOvw#Input_OvwKeyboardExampleHandlerCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml.cs#input_ovwkeyboardexamplehandlercodebehind)]
 [!code-vb[InputOvw#Input_OvwKeyboardExampleHandlerCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InputOvw/VisualBasic/Page1.xaml.vb#input_ovwkeyboardexamplehandlercodebehind)]  
  
### <a name="mouse-input-event-example"></a>마우스 입력된 이벤트 예제  
 다음 예제에서는 <xref:System.Windows.Controls.Control.Background%2A> 의 색을 <xref:System.Windows.Controls.Button> 마우스 포인터가 들어올 때 변경 되는 <xref:System.Windows.Controls.Button>합니다.  <xref:System.Windows.Controls.Control.Background%2A> 외부로 색 복원 되는 <xref:System.Windows.Controls.Button>합니다.  
  
 예제의 첫 번째 부분을 만듭니다는 <xref:System.Windows.Controls.StackPanel> 및 <xref:System.Windows.Controls.Button> 에 대 한 이벤트 처리기를 연결 및 제어는 <xref:System.Windows.UIElement.MouseEnter> 및 <xref:System.Windows.UIElement.MouseLeave> 이벤트는 <xref:System.Windows.Controls.Button>.  
  
 [!code-xml[InputOvw#Input_OvwMouseExampleXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml#input_ovwmouseexamplexaml)]  
  
 [!code-csharp[InputOvw#Input_OvwMouseExampleUICodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml.cs#input_ovwmouseexampleuicodebehind)]
 [!code-vb[InputOvw#Input_OvwMouseExampleUICodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InputOvw/VisualBasic/Page1.xaml.vb#input_ovwmouseexampleuicodebehind)]  
  
 예제의 두 번째 부분 코드로 작성 하 고 이벤트 처리기를 정의 합니다.  마우스를 가져가면는 <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Control.Background%2A> 의 색은 <xref:System.Windows.Controls.Button> 로 변경 <xref:System.Windows.Media.Brushes.SlateGray%2A>합니다.  마우스가 벗어날 때는 <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Control.Background%2A> 의 색은 <xref:System.Windows.Controls.Button> 다시 변경 됩니다 <xref:System.Windows.Media.Brushes.AliceBlue%2A>합니다.  
  
 [!code-csharp[InputOvw#Input_OvwMouseExampleEneterHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml.cs#input_ovwmouseexampleeneterhandler)]
 [!code-vb[InputOvw#Input_OvwMouseExampleEneterHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InputOvw/VisualBasic/Page1.xaml.vb#input_ovwmouseexampleeneterhandler)]  
  
 [!code-csharp[InputOvw#Input_OvwMouseExampleLeaveHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml.cs#input_ovwmouseexampleleavehandler)]
 [!code-vb[InputOvw#Input_OvwMouseExampleLeaveHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InputOvw/VisualBasic/Page1.xaml.vb#input_ovwmouseexampleleavehandler)]  
  
<a name="text_input"></a>   
## <a name="text-input"></a>텍스트 입력  
 <xref:System.Windows.ContentElement.TextInput> 이벤트를 사용 하면 장치에 관계 없이 텍스트 입력을 수신 대기할 수 있습니다. 키보드는 텍스트 입력을 하지만 음성, 필기의 기본 수단 및 기타 입력된 장치에 텍스트 입력도 생성할 수 있습니다.  
  
 키보드 입력에 대 한 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 먼저 적절 한 보냅니다 <xref:System.Windows.ContentElement.KeyDown>/<xref:System.Windows.ContentElement.KeyUp> 이벤트입니다. 이러한 이벤트는 처리 되지 않은 고 키 (방향 화살표와 같은 제어 키) 또는 기능 키 대신 텍스트는 <xref:System.Windows.ContentElement.TextInput> 이벤트가 발생 합니다.  없는 항상 간의 단순 일대일 매핑을 <xref:System.Windows.ContentElement.KeyDown>/<xref:System.Windows.ContentElement.KeyUp> 및 <xref:System.Windows.ContentElement.TextInput> 이벤트 여러 키 입력 텍스트 입력의 단일 문자를 생성할 수 있으므로 단일 키 입력 복수 문자 문자열을 생성할 수 있습니다.  사용 하는 언어 중국어, 일본어, 한국어 등의 경우가 특히 그렇습니다 [!INCLUDE[TLA#tla_ime#plural](../../../../includes/tlasharptla-imesharpplural-md.md)] 를 알파벳에 수천 개의 가능한 문자를 생성 합니다.  
  
 때 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 보냅니다는 <xref:System.Windows.ContentElement.KeyUp>/<xref:System.Windows.ContentElement.KeyDown> 이벤트 <xref:System.Windows.Input.KeyEventArgs.Key%2A> 로 설정 된 <xref:System.Windows.Input.Key?displayProperty=fullName> 키 입력의 일부가 될 수 있는 경우는 <xref:System.Windows.ContentElement.TextInput> 이벤트 (예를 들어 ALT + S를 누르면,) 하는 경우. 이렇게 하면 코드에는 <xref:System.Windows.ContentElement.KeyDown> 이벤트 처리기를 확인 하려면 <xref:System.Windows.Input.Key?displayProperty=fullName> 하며, 발견 되 면 이후에 발생의 처리기에 대 한 처리 <xref:System.Windows.ContentElement.TextInput> 이벤트. 이러한 경우의 다양 한 속성에는 <xref:System.Windows.Input.TextCompositionEventArgs> 원래 키 입력을 확인 하려면 인수를 사용할 수 있습니다. 마찬가지로, 경우는 [!INCLUDE[TLA2#tla_ime](../../../../includes/tla2sharptla-ime-md.md)] 활성 상태인 <xref:System.Windows.Input.Key> 의 값은 <xref:System.Windows.Input.Key?displayProperty=fullName>, 및 <xref:System.Windows.Input.KeyEventArgs.ImeProcessedKey%2A> 원래 키 또는 키 입력을 제공 합니다.  
  
 다음 예제에 대 한 처리기를 정의 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트 및에 대 한 처리기는 <xref:System.Windows.UIElement.KeyDown> 이벤트입니다.  
  
 코드 또는 태그의 첫 번째 세그먼트는 사용자 인터페이스를 만듭니다.  
  
 [!code-xml[InputOvw#Input_OvwTextInputXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml#input_ovwtextinputxaml)]  
  
 [!code-csharp[InputOvw#Input_OvwTextInputUICodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml.cs#input_ovwtextinputuicodebehind)]
 [!code-vb[InputOvw#Input_OvwTextInputUICodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InputOvw/VisualBasic/Page1.xaml.vb#input_ovwtextinputuicodebehind)]  
  
 코드의 두 번째 세그먼트는 이벤트 처리기를 포함합니다.  
  
 [!code-csharp[InputOvw#Input_OvwTextInputHandlersCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml.cs#input_ovwtextinputhandlerscodebehind)]
 [!code-vb[InputOvw#Input_OvwTextInputHandlersCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InputOvw/VisualBasic/Page1.xaml.vb#input_ovwtextinputhandlerscodebehind)]  
  
 입력된 이벤트는 이벤트 경로 버블링 때문에 <xref:System.Windows.Controls.StackPanel> 에 키보드 포커스가 있는 요소에 관계 없이 입력을 받습니다. <xref:System.Windows.Controls.TextBox> 컨트롤은 먼저 알림 및 `OnTextInputKeyDown` 경우에 처리기가 호출는 <xref:System.Windows.Controls.TextBox> 입력을 처리 하지 못했습니다. 하는 경우는 <xref:System.Windows.UIElement.PreviewKeyDown> 이벤트 대신 사용 되는 <xref:System.Windows.UIElement.KeyDown> 이벤트를는 `OnTextInputKeyDown` 처리기가 먼저 호출 됩니다.  
  
 이 예제에서는 처리 논리를 작성 두 번-한 번 CTRL + O, 다시에 대 한 단추의 click 이벤트입니다. 입력된 이벤트를 직접 처리 하는 대신 명령을 사용 하 여이 단순화할 수 있습니다.  명령이 개요 및 [명령 개요](../../../../docs/framework/wpf/advanced/commanding-overview.md)합니다.  
  
<a name="touch_and_manipulation"></a>   
## <a name="touch-and-manipulation"></a>터치 및 조작  
 새 하드웨어와 Windows 7 운영 체제에서 API 응용 프로그램을 동시에 여러 터치의 입력을 받는 기능을 제공 합니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]응용 프로그램을을 검색 하 고 터치가 일어날 때 이벤트를 발생 시켜 마우스 또는 키보드 등의 다른 입력에 응답 하는 유사한 방식으로 터치에 응답할 수 있습니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]두 가지 유형의 터치 발생할 때 이벤트를 노출 합니다: 터치 이벤트와 조작 이벤트입니다. 터치 이벤트는 터치 스크린의 이동에 각 손가락에 대 한 원시 데이터를 제공합니다. 조작 이벤트는 특정 작업으로 입력을 해석합니다. 두 가지 유형의 이벤트는이 섹션에서 설명 합니다.  
  
### <a name="prerequisites"></a>필수 조건  
 터치에 반응 하는 응용 프로그램을 개발 하려면 다음 구성 해야 합니다.  
  
-   [!INCLUDE[vs_dev10_ext](../../../../includes/vs-dev10-ext-md.md)].  
  
-   Windows 7입니다.  
  
-   장치를 지 원하는 Windows Touch 터치 스크린 등입니다.  
  
### <a name="terminology"></a>용어  
 터치 설명 하는 경우는 다음과 같은 용어가 사용 됩니다.  
  
-   **터치** Windows 7에서 인식 되는 사용자 입력의 형식입니다. 일반적으로 터치 손가락 터치 감지 화면에 배치 하 여 시작 됩니다. Note 랩톱 컴퓨터에 공통 된 터치 패드와 같은 장치 장치는 단순히 손가락의 위치 및 움직임 마우스 입력을 변환 하는 경우 터치 지원 하지 않습니다.  
  
-   **다중 터치** 동시에 둘 이상의 지점에서 발생 하는 터치 합니다. Windows 7 및 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 다중 터치를 지원 합니다. 터치에 대 한 설명서에 대해서는 설명 때마다 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], 개념은 다중 터치에 적용 합니다.  
  
-   A **조작** 터치 개체에 적용 되는 실제 작업으로 해석 되는 경우에 발생 합니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], 조작 이벤트 입력을 번역, 확장 또는 회전 조작으로 해석 합니다.  
  
-   A `touch device` 터치를 한 손가락 터치 스크린에서 같은 입력을 생성 하는 장치를 나타냅니다.  
  
### <a name="controls-that-respond-to-touch"></a>터치에 응답 하는 컨트롤  
 스크롤되어 보이지는 콘텐츠가 있으면 컨트롤에서 손가락을 끄는 하 여 다음과 같은 컨트롤을 스크롤할 수 있습니다.  
  
-   <xref:System.Windows.Controls.ComboBox>  
  
-   <xref:System.Windows.Controls.ContextMenu>  
  
-   <xref:System.Windows.Controls.DataGrid>  
  
-   <xref:System.Windows.Controls.ListBox>  
  
-   <xref:System.Windows.Controls.ListView>  
  
-   <xref:System.Windows.Controls.MenuItem>  
  
-   <xref:System.Windows.Controls.TextBox>  
  
-   <xref:System.Windows.Controls.ToolBar>  
  
-   <xref:System.Windows.Controls.TreeView>  
  
 <xref:System.Windows.Controls.ScrollViewer> 정의 <xref:System.Windows.Controls.ScrollViewer.PanningMode%2A?displayProperty=fullName> 터치 팬은 사용할 수 있는지 여부 가로, 세로, 가로 및 세로 또는 둘 다 지정할 수 있는 연결 된 속성입니다. <xref:System.Windows.Controls.ScrollViewer.PanningDeceleration%2A?displayProperty=fullName> 얼마나 빨리 스크롤 속도가 느려집니다 치우면 손가락 터치 스크린에서 속성을 지정 합니다. <xref:System.Windows.Controls.ScrollViewer.PanningRatio%2A?displayProperty=fullName> 조작 오프셋 변환할 스크롤 오프셋의 비율을 지정 하는 연결 된 속성입니다.  
  
### <a name="touch-events"></a>터치 이벤트  
 기본 클래스 <xref:System.Windows.UIElement>, <xref:System.Windows.UIElement3D>, 및 <xref:System.Windows.ContentElement>, 응용 프로그램은 터치에 반응 하도록 구독할 수 있는 이벤트를 정의 합니다. 터치 이벤트는 응용 프로그램 개체를 조작 되지 않았을 터치를 해석 하는 경우에 유용 합니다. 예를 들어 사용자가 하나 이상의 손가락으로 그릴 수 있도록 하는 응용 프로그램은 터치 이벤트를 구독 합니다.  
  
 세 클래스 모두 클래스 정의 관계 없이 이와 비슷하게 동작 하는 다음 이벤트를 정의 합니다.  
  
-   <xref:System.Windows.UIElement.TouchDown>  
  
-   <xref:System.Windows.UIElement.TouchMove>  
  
-   <xref:System.Windows.UIElement.TouchUp>  
  
-   <xref:System.Windows.UIElement.TouchEnter>  
  
-   <xref:System.Windows.UIElement.TouchLeave>  
  
-   <xref:System.Windows.UIElement.PreviewTouchDown>  
  
-   <xref:System.Windows.UIElement.PreviewTouchMove>  
  
-   <xref:System.Windows.UIElement.PreviewTouchUp>  
  
-   <xref:System.Windows.UIElement.GotTouchCapture>  
  
-   <xref:System.Windows.UIElement.LostTouchCapture>  
  
 키보드 및 마우스 이벤트와 마찬가지로 터치 이벤트는 라우트된 이벤트를 사용 합니다. 로 시작 하는 이벤트 `Preview` 이벤트 및 이벤트로 시작 하는 터널링 `Touch` 는 버블링 이벤트입니다. 라우트된 이벤트에 대 한 자세한 내용은 참조 [라우트된 이벤트 개요](../../../../docs/framework/wpf/advanced/routed-events-overview.md)합니다. 이러한 이벤트를 처리할 때 호출 하 여 모든 요소를 기준으로 입력의 위치를 가져올 수 있습니다는 <xref:System.Windows.Input.TouchEventArgs.GetTouchPoint%2A> 또는 <xref:System.Windows.Input.TouchEventArgs.GetIntermediateTouchPoints%2A> 메서드.  
  
 터치 이벤트 간의 상호 작용을 이해 하려면 여기서 사용자가 손가락을 요소에, 손가락 요소에서 이동한 다음 요소에서 손가락이 들어 올리기 시나리오를 살펴보겠습니다. 다음 그림 (터널링 이벤트는 편의상 생략 됨)는 버블링 이벤트의 실행을 보여 줍니다.  
  
 ![터치 이벤트 순서를 지정 합니다.](../../../../docs/framework/wpf/advanced/media/ndp-touchevents.png "NDP_TouchEvents")  
터치 이벤트  
  
 다음 목록에서는 앞의 그림에서 이벤트의 순서를 설명합니다.  
  
1.  <xref:System.Windows.UIElement.TouchEnter> 이벤트는 사용자가 요소에 손가락을 놓고 하는 경우 한 번 발생 합니다.  
  
2.  <xref:System.Windows.UIElement.TouchDown> 이벤트 한 번 발생 합니다.  
  
3.  <xref:System.Windows.UIElement.TouchMove> 손가락 요소 내에서 이동할 때 이벤트에 여러 번 발생 합니다.  
  
4.  <xref:System.Windows.UIElement.TouchUp> 이벤트는 사용자가 요소에서 손가락을 들어 올리기 때 한 번 발생 합니다.  
  
5.  <xref:System.Windows.UIElement.TouchLeave> 이벤트 한 번 발생 합니다.  
  
 두 개 이상의 손가락으로 사용 되는 경우 각 손가락에는 이벤트가 발생 합니다.  
  
### <a name="manipulation-events"></a>조작 이벤트  
 응용 프로그램을 통해 사용자가 개체를 조작할 수 있는 경우에는 <xref:System.Windows.UIElement> 조작 이벤트 클래스를 정의 합니다. 터치 위치를 보고 하는 터치 이벤트와는 달리 조작 이벤트는 입력 수 해석 하는 방법을 보고 합니다. 조작, 번역, 확장 및 회전의 세 가지 종류가 있습니다. 다음은 세 가지 유형의 조작을 호출 하는 방법을 설명 합니다.  
  
-   개체에 손가락을 놓고 및 번역 조작을 호출 하려면 터치 스크린에서 손가락을 이동 합니다. 이 개체는 일반적으로 이동합니다.  
  
-   개체에 두 손가락을 배치 하 고 더 가깝게 함께 또는 별도로 확장 조작을 호출 서로 멀리 손가락을 이동 합니다. 일반적으로 개체 크기 조정합니다.  
  
-   개체에 두 손가락을 놓고 회전 조작을 호출 서로 손가락의 회전 합니다. 이 일반적으로 개체를 회전합니다.  
  
 둘 이상의 조작 유형의 동시에 발생할 수 있습니다.  
  
 조작에 반응 하는 개체를 일으킬 때 관성을 개체가 있을 수 있습니다. 실제 세상을 시뮬레이션 하 여 개체 크기 수 있습니다. 예를 들어 하드 푸시할 경우 테이블을 통해 책을 푸시할 때 콘텐츠가 충분히 책 릴리스하기 후 이동를 계속 됩니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]개체는 사용자의 손가락을 뗀 후 조작 이벤트를 발생 하 여이 동작을 시뮬레이션할 수 있습니다.  
  
 이동, 크기 조정 및 개체를 회전 하는 데 사용할 수 있는 응용 프로그램을 만드는 방법에 대 한 정보를 참조 하십시오. [연습: 만들기 첫 Touch 응용 프로그램](../../../../docs/framework/wpf/advanced/walkthrough-creating-your-first-touch-application.md)합니다.  
  
 <xref:System.Windows.UIElement> 다음 조작 이벤트를 정의 합니다.  
  
-   <xref:System.Windows.UIElement.ManipulationStarting>  
  
-   <xref:System.Windows.UIElement.ManipulationStarted>  
  
-   <xref:System.Windows.UIElement.ManipulationDelta>  
  
-   <xref:System.Windows.UIElement.ManipulationInertiaStarting>  
  
-   <xref:System.Windows.UIElement.ManipulationCompleted>  
  
-   <xref:System.Windows.UIElement.ManipulationBoundaryFeedback>  
  
 기본적으로는 <xref:System.Windows.UIElement> 이러한 조작 이벤트를 수신 하지 않습니다. 조작 이벤트에 받을 <xref:System.Windows.UIElement>설정, <xref:System.Windows.UIElement.IsManipulationEnabled%2A?displayProperty=fullName> 를 `true`합니다.  
  
#### <a name="the-execution-path-of-manipulation-events"></a>조작 이벤트의 실행 경로  
 여기서는 사용자 "" 개체가 throw 하는 시나리오를 고려해 보십시오. 개체에서 손가락을 놓고 손가락 짧은 거리에 대 한 터치 스크린에서 이동한 이동 하는 동안 다음 손가락이 들어 올리기입니다. 이 개체에서 사용자의 손가락 이동 되며 사용자가 손가락을 들어 올리기 후 이동를 계속 됩니다.  
  
 다음은 각 이벤트에 대 한 중요 한 정보 및 조작 이벤트의 실행 경로입니다.  
  
 ![조작 이벤트의 시퀀스입니다.](../../../../docs/framework/wpf/advanced/media/ndp-manipulationevents.png "NDP_ManipulationEvents")  
조작 이벤트  
  
 다음 목록에서는 앞의 그림에서 이벤트의 순서를 설명합니다.  
  
1.  <xref:System.Windows.UIElement.ManipulationStarting> 이벤트 개체에 대 한 손가락을 놓을 때 발생 합니다. 무엇 보다도이 이벤트를 통해 설정할 수는 <xref:System.Windows.Input.ManipulationStartingEventArgs.ManipulationContainer%2A> 속성입니다. 후속 이벤트에서 조작의 위치에 상대적인 됩니다는 <xref:System.Windows.Input.ManipulationStartingEventArgs.ManipulationContainer%2A>합니다. 이외의 이벤트에서 <xref:System.Windows.UIElement.ManipulationStarting>,이 속성은 읽기 전용 이므로 <xref:System.Windows.UIElement.ManipulationStarting> 이벤트는이 속성을 설정할 수 있는 유일한 경우입니다.  
  
2.  <xref:System.Windows.UIElement.ManipulationStarted> 이벤트 다음 발생 합니다. 이 이벤트는 조작 원점이 보고합니다.  
  
3.  <xref:System.Windows.UIElement.ManipulationDelta> 이벤트 터치 스크린에서 사용자의 손가락 이동으로 여러 번 발생 합니다. <xref:System.Windows.Input.ManipulationDeltaEventArgs.DeltaManipulation%2A> 의 속성은 <xref:System.Windows.Input.ManipulationDeltaEventArgs> 클래스 조작 이동, 확장 또는 변환으로 해석 됩니다 있는지 여부를 보고 합니다. 대부분의 개체를 조작 하는 작업을 수행 하는 위치입니다.  
  
4.  <xref:System.Windows.UIElement.ManipulationInertiaStarting> 이 이벤트는 사용자의 손가락의 개체와 연결이 끊어질 때 발생 합니다. 이 이벤트는 조작의 관성 도중 감속을 지정할 수 있습니다. 이므로 선택 하는 경우 개체는 서로 다른 물리적 공간 또는 특성에 에뮬레이트할 수 있습니다. 예를 들어, 응용 프로그램에 실제 세상에서 항목을 나타내는 두 개의 개체가 있고 하나는 다른 것 보다 더 많은 것입니다. 가벼운 개체 보다 더 빠르게 감속 더 많은 개체를 만들 수 있습니다.  
  
5.  <xref:System.Windows.UIElement.ManipulationDelta> 관성 발생 이벤트에 여러 번 발생 합니다. 이 이벤트는 터치 스크린에서 사용자의 손가락을 이동 하는 경우 발생할 참고 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 관성을 시뮬레이션 합니다. 즉, <xref:System.Windows.UIElement.ManipulationDelta> 전과 후에 발생 된 <xref:System.Windows.UIElement.ManipulationInertiaStarting> 이벤트입니다. <xref:System.Windows.Input.ManipulationDeltaEventArgs.IsInertial%2A?displayProperty=fullName> 속성 보고서 여부는 <xref:System.Windows.UIElement.ManipulationDelta> 관성을 하는 동안 이벤트 발생 하지 않으므로 해당 속성을 확인 하 고 해당 값에 따라 다른 작업을 수행할 수 있습니다.  
  
6.  <xref:System.Windows.UIElement.ManipulationCompleted> 이벤트 발생 조작 및 관성의 종료 시점입니다. 즉, 이후 모든은 <xref:System.Windows.UIElement.ManipulationDelta> 이벤트가 발생할는 <xref:System.Windows.UIElement.ManipulationCompleted> 를 조작이 완료 되었음을 알리는 이벤트가 발생 합니다.  
  
 <xref:System.Windows.UIElement> 정의 <xref:System.Windows.UIElement.ManipulationBoundaryFeedback> 이벤트입니다. 이 이벤트가 발생할 때의 <xref:System.Windows.Input.ManipulationDeltaEventArgs.ReportBoundaryFeedback%2A> 메서드는 <xref:System.Windows.UIElement.ManipulationDelta> 이벤트입니다. <xref:System.Windows.UIElement.ManipulationBoundaryFeedback> 이벤트 개체는 경계에 도달 하면 시각적 피드백을 제공 하는 응용 프로그램 또는 구성 요소를 사용 합니다. 예를 들어는 <xref:System.Windows.Window> 핸들 클래스는 <xref:System.Windows.UIElement.ManipulationBoundaryFeedback> 창이 약간 발생의 가장자리를 이동 하는 이벤트입니다.  
  
 호출 하 여 조작을 취소할 수는 <xref:System.Windows.Input.ManipulationStartingEventArgs.Cancel%2A> 제외 하 고 조작 이벤트의 이벤트 인수에서 메서드 <xref:System.Windows.UIElement.ManipulationBoundaryFeedback> 이벤트입니다. 호출 하는 경우 <xref:System.Windows.Input.ManipulationStartingEventArgs.Cancel%2A>조작 이벤트는 더 이상 발생 하 고 터치에 대 한 마우스 이벤트를 발생 합니다. 다음 표에서 조작이 취소 되는 시간과 발생 하는 마우스 이벤트 간의 관계를 설명 합니다.  
  
|취소 하는 이벤트 라고 합니다.|이미 발생 한 입력에 대해 발생 하는 마우스 이벤트|  
|----------------------------------------|-----------------------------------------------------------------|  
|<xref:System.Windows.UIElement.ManipulationStarting> 및 <xref:System.Windows.UIElement.ManipulationStarted>|마우스 이벤트를 제공 합니다.|  
|<xref:System.Windows.UIElement.ManipulationDelta>|마우스 누름 및 마우스 이동 이벤트입니다.|  
|<xref:System.Windows.UIElement.ManipulationInertiaStarting> 및 <xref:System.Windows.UIElement.ManipulationCompleted>|마우스 아래로 마우스 이동 및 마우스 위로 이벤트입니다.|  
  
 호출 하는 경우 사용자에 게 유의 <xref:System.Windows.Input.ManipulationStartingEventArgs.Cancel%2A> 메서드 조작 관성 이면 `false` 하며 입력 마우스 이벤트를 발생 하지 않습니다.  
  
### <a name="the-relationship-between-touch-and-manipulation-events"></a>터치와 조작 이벤트의 관계  
 A <xref:System.Windows.UIElement> 항상 터치 이벤트를 받을 수 있습니다. 경우는 <xref:System.Windows.UIElement.IsManipulationEnabled%2A> 속성이 `true`, <xref:System.Windows.UIElement> 모두 터치 이벤트와 조작 이벤트를 받을 수 있습니다.  하는 경우는 <xref:System.Windows.UIElement.TouchDown> 이벤트가 처리 되지 않은 (즉,는 <xref:System.Windows.RoutedEventArgs.Handled%2A> 속성은 `false`), 조작 논리 요소에 터치를 캡처하고 조작 이벤트를 생성 합니다. 하는 경우는 <xref:System.Windows.RoutedEventArgs.Handled%2A> 속성이 `true` 에 <xref:System.Windows.UIElement.TouchDown> 이벤트를 조작 논리 조작 이벤트를 생성 하지 않습니다. 다음 그림 터치 이벤트와 조작 이벤트의 관계를 보여 줍니다.  
  
 ![터치 이벤트와 조작 이벤트 간의 관계](../../../../docs/framework/wpf/advanced/media/ndp-touchmanipulateevents.png "NDP_TouchManipulateEvents")  
터치 이벤트와 조작 이벤트  
  
 다음은 앞의 그림에 표시 되는 터치 및 조작 이벤트 간의 관계를 설명 합니다.  
  
-   첫 번째 터치 장치 생성 하는 경우는 <xref:System.Windows.UIElement.TouchDown> 이벤트에는 <xref:System.Windows.UIElement>, 조작 논리 호출은 <xref:System.Windows.UIElement.CaptureTouch%2A> 메서드를 생성 하는 <xref:System.Windows.UIElement.GotTouchCapture> 이벤트입니다.  
  
-   때는 <xref:System.Windows.UIElement.GotTouchCapture> 발생 조작 논리 호출의 <xref:System.Windows.Input.Manipulation.AddManipulator%2A?displayProperty=fullName> 생성 하는 메서드는 <xref:System.Windows.UIElement.ManipulationStarting> 이벤트입니다.  
  
-   때는 <xref:System.Windows.UIElement.TouchMove> 조작 논리를 생성, 이벤트가 발생 된 <xref:System.Windows.UIElement.ManipulationDelta> 이벤트 전에 발생 하는 <xref:System.Windows.UIElement.ManipulationInertiaStarting> 이벤트입니다.  
  
-   마지막 장치를 터치 요소를 발생 시킵니다는 <xref:System.Windows.UIElement.TouchUp> 조작 논리를 생성 이벤트에는 <xref:System.Windows.UIElement.ManipulationInertiaStarting> 이벤트입니다.  
  
<a name="focus"></a>   
## <a name="focus"></a>포커스  
 두 가지 주요 개념인에 포커스와 관련 된 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: 키보드 포커스와 논리적 포커스입니다.  
  
### <a name="keyboard-focus"></a>키보드 포커스  
 키보드 포커스는 키보드 입력을 받고 있는 요소를 참조 합니다.  키보드 포커스가 있는 바탕 화면에서 하나의 요소만 있을 수 있습니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], 키보드 포커스가 있는 요소에 포함 될 <xref:System.Windows.IInputElement.IsKeyboardFocused%2A> 로 설정 `true`합니다.  정적 <xref:System.Windows.Input.Keyboard> 메서드 <xref:System.Windows.Input.Keyboard.FocusedElement%2A> 현재 키보드 포커스가 있는 요소를 반환 합니다.  
  
 요소에 탭 이동 하거나와 같은 특정 요소에 마우스를 클릭 하 여 키보드 포커스를 얻을 수 있습니다는 <xref:System.Windows.Controls.TextBox>합니다.  키보드 포커스를 사용 하 여 프로그래밍 방식으로 가져올 수도 있습니다는 <xref:System.Windows.Input.Keyboard.Focus%2A> 메서드는 <xref:System.Windows.Input.Keyboard> 클래스입니다.  <xref:System.Windows.Input.Keyboard.Focus%2A> 키보드 포커스를 지정된 된 요소를 제공 하려고 합니다.  반환한 요소 <xref:System.Windows.Input.Keyboard.Focus%2A> 현재 키보드 포커스가 있는 요소입니다.  
  
 키보드 포커스를 얻을 수 있는 요소에 대 한 순서는 <xref:System.Windows.UIElement.Focusable%2A> 속성 및 <xref:System.Windows.UIElement.IsVisible%2A> 속성으로 설정 되어 있어야 **true**합니다.  와 같은 일부 클래스 <xref:System.Windows.Controls.Panel>, 한 <xref:System.Windows.UIElement.Focusable%2A> 로 설정 `false` 기본적으로 따라서 해야이 속성을 설정 `true` 포커스를 받고 수 있으려면 해당 요소에 들어 있습니다.  
  
 다음 예제에서는 <xref:System.Windows.Input.Keyboard.Focus%2A> 에 키보드 포커스를 설정 하는 <xref:System.Windows.Controls.Button>합니다.  응용 프로그램에서 초기 포커스를 설정 하는 가장 좋은 위치는 <xref:System.Windows.FrameworkElement.Loaded> 이벤트 처리기입니다.  
  
 [!code-csharp[focussample#FocusSampleSetFocus](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FocusSample/CSharp/Window1.xaml.cs#focussamplesetfocus)]
 [!code-vb[focussample#FocusSampleSetFocus](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSample/visualbasic/window1.xaml.vb#focussamplesetfocus)]  
  
 키보드 포커스에 대 한 자세한 내용은 참조 [포커스 개요](../../../../docs/framework/wpf/advanced/focus-overview.md)합니다.  
  
### <a name="logical-focus"></a>논리적 포커스  
 논리적 포커스 참조 하는 <xref:System.Windows.Input.FocusManager.FocusedElement%2A?displayProperty=fullName> 포커스 범위 내에서.  응용 프로그램에서 논리적 포커스를 가진 여러 요소가 있을 수 있지만 특정 포커스 범위 내에서 논리적 포커스 된 요소 수입니다.  
  
 포커스 범위는 추적 하는 컨테이너 요소는 <xref:System.Windows.Input.FocusManager.FocusedElement%2A> 해당 범위 내에서.  포커스 포커스 범위를 벗어날 때 포커스가 있는 요소에 키보드 포커스를 잃게 됩니다 있지만 논리적 포커스를 유지 합니다.  포커스에 포커스 범위를 반환 하는 경우 포커스가 있는 요소는 키보드 포커스를 가져옵니다.  이 키보드 포커스 여러 포커스 범위 사이 변경 될 수 있습니다 되더라도 포커스를 반환 하는 경우 포커스 범위 내에서 포커스가 있는 요소 포커스가 있는 요소는 유지 됩니다.  
  
 요소에서 포커스 범위로 전환할 수 있습니다 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 설정 하 여는 <xref:System.Windows.Input.FocusManager> 연결 된 속성 <xref:System.Windows.Input.FocusManager.IsFocusScope%2A> 를 `true`, 또는 사용 하 여 연결된 된 속성을 설정 하 여 코드에서의 <xref:System.Windows.Input.FocusManager.SetIsFocusScope%2A> 메서드.  
  
 다음 예제에서는 한 <xref:System.Windows.Controls.StackPanel> 설정 하 여 포커스 범위로 <xref:System.Windows.Input.FocusManager.IsFocusScope%2A> 연결 된 속성입니다.  
  
 [!code-xml[MarkupSnippets#MarkupIsFocusScopeXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml#markupisfocusscopexaml)]  
  
 [!code-csharp[FocusSnippets#FocusSetIsFocusScope](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FocusSnippets/CSharp/Window1.xaml.cs#focussetisfocusscope)]
 [!code-vb[FocusSnippets#FocusSetIsFocusScope](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSnippets/visualbasic/window1.xaml.vb#focussetisfocusscope)]  
  
 클래스의 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 는 기본적으로 포커스 범위인 <xref:System.Windows.Window>, <xref:System.Windows.Controls.Menu>, <xref:System.Windows.Controls.ToolBar>, 및 <xref:System.Windows.Controls.ContextMenu>합니다.  
  
 키보드 포커스가 있는 요소에는;에 속한 포커스 범위에 대 한 논리적 포커스 따라서 요소에 포커스를 설정는 <xref:System.Windows.Input.Keyboard.Focus%2A> 메서드는 <xref:System.Windows.Input.Keyboard> 클래스 또는 기본 요소 클래스 요소에 키보드 포커스, 논리적 포커스를 지정 하려고 합니다.  
  
 포커스 범위 내에서 포커스가 있는 요소를 확인 하려면 사용 <xref:System.Windows.Input.FocusManager.GetFocusedElement%2A>합니다. 포커스 범위에 대 한 포커스가 있는 요소를 변경 하려면 사용 <xref:System.Windows.Input.FocusManager.SetFocusedElement%2A>합니다.  
  
 논리 포커스에 대 한 자세한 내용은 참조 [포커스 개요](../../../../docs/framework/wpf/advanced/focus-overview.md)합니다.  
  
<a name="mouse_position"></a>   
## <a name="mouse-position"></a>마우스 위치  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 입력 [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] 좌표 공간과 관련 된 유용한 정보를 제공 합니다.  예를 들어 좌표 `(0,0)` 왼쪽 위 좌표 건 트리에 있는 요소의 왼쪽 위? 입력된 대상에 있는 요소? 이벤트 처리기를 연결 하는 요소? 또는 무엇 인가? 혼동을 피하기 위해는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 입력 [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] 에서 마우스로 좌표를 사용 하 여 작업할 때 참조 프레임을 지정 해야 합니다. <xref:System.Windows.Input.Mouse.GetPosition%2A> 메서드는 지정된 된 요소를 기준으로 마우스 포인터의 좌표를 반환 합니다.  
  
<a name="mouse_capture"></a>   
## <a name="mouse-capture"></a>마우스 캡처  
 마우스 장치는 특히 마우스 캡처 라고 하는 모달 특성을 보유 합니다. 마우스 캡처 정격을 화면에 나타나는 관련 된 다른 작업에서 마우스 포인터의 위치 발생할 필요가 있도록 끌어서 놓기 작업이 시작 될 때 전환 입력된 상태를 유지 하는 데 사용 됩니다. 끄는 동안 사용자는 끌어서 놓기, 그러면 대부분의 마우스 이동 동작이 부적절 한 끌기 원점에서 마우스 캡처를 보관 하는 동안 중단 하지 않고 클릭할 수 없습니다. 입력된 시스템을 노출 [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] 마우스 캡처 상태를 확인할 수 있는로 [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] 마우스 캡처 특정 요소를 적용 하거나 마우스 캡처 상태를 선택 취소 하 합니다. 끌어서 놓기 작업에 대 한 자세한 내용은 참조 하십시오. [놓기](../../../../docs/framework/wpf/advanced/drag-and-drop-overview.md)합니다.  
  
<a name="commands"></a>   
## <a name="commands"></a>명령  
 명령을 장치 입력에 비해 근본적으로 의미론 수준에서 입력된을 처리할을 수 있습니다.  간단한 지시문과 같은 주석은 `Cut`, `Copy`, `Paste`, 또는 `Open`합니다.  명령은 명령 논리를 중앙 집중화 하는 데 유용 합니다.  동일한 명령에서 액세스 될 수는 <xref:System.Windows.Controls.Menu>의 <xref:System.Windows.Controls.ToolBar>, 또는 바로 가기 키입니다. 또한 명령은 명령을 사용할 수 없을 때 컨트롤을 사용 하지 않도록 설정 하는 메커니즘을 제공 합니다.  
  
 <xref:System.Windows.Input.RoutedCommand> 는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 구현의 <xref:System.Windows.Input.ICommand>합니다.  때는 <xref:System.Windows.Input.RoutedCommand> 실행 되는 <xref:System.Windows.Input.CommandManager.PreviewExecuted> 및 <xref:System.Windows.Input.CommandManager.Executed> 이벤트는 터널와 거품형 요소 트리를 통해 다른 입력 등의 명령 대상에서 발생 합니다.  명령 대상 설정 되어 있지 않으면 키보드 포커스가 있는 요소 명령 대상이 됩니다.  에 연결 명령을 수행 하는 논리는 <xref:System.Windows.Input.CommandBinding>합니다.  때는 <xref:System.Windows.Input.CommandManager.Executed> 에 도달 하면 이벤트는 <xref:System.Windows.Input.CommandBinding> 특정 명령에 대 한는 <xref:System.Windows.Input.ExecutedRoutedEventHandler> 에 <xref:System.Windows.Input.CommandBinding> 호출 됩니다.  이 처리기는 명령의 동작을 수행합니다.  
  
 명령에 대 한 자세한 내용은 참조 하십시오. [명령 개요](../../../../docs/framework/wpf/advanced/commanding-overview.md)합니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]구성 된 공통 명령의 라이브러리 제공 <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.MediaCommands>, <xref:System.Windows.Input.ComponentCommands>, <xref:System.Windows.Input.NavigationCommands>, 및 <xref:System.Windows.Documents.EditingCommands>, 하거나 직접 정의할 수 있습니다.  
  
 다음 예제를 설정 하는 방법을 보여 줍니다는 <xref:System.Windows.Controls.MenuItem> 하므로 클릭할 때 호출는 <xref:System.Windows.Input.ApplicationCommands.Paste%2A> 명령을 <xref:System.Windows.Controls.TextBox>는 <xref:System.Windows.Controls.TextBox> 키보드 포커스가 합니다.  
  
 [!code-xml[CommandingOverviewSnippets#CommandingOverviewSimpleCommand](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewsimplecommand)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcommandtargetcodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcommandtargetcodebehind)]  
  
 명령에 대 한 자세한 내용은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], 참조 [명령 개요](../../../../docs/framework/wpf/advanced/commanding-overview.md)합니다.  
  
<a name="the_input_system_and_base_elements"></a>   
## <a name="the-input-system-and-base-elements"></a>입력된 시스템 및 기본 요소  
 입력 하 여 정의 하는 연결 된 이벤트와 같은 이벤트는 <xref:System.Windows.Input.Mouse>, <xref:System.Windows.Input.Keyboard>, 및 <xref:System.Windows.Input.Stylus> 클래스는 입력된 시스템에 의해 발생 되며 적중 시각적 트리 실행 시 테스트를 기반으로 개체 모델의 특정 위치에 삽입 합니다.  
  
 각 이벤트는 <xref:System.Windows.Input.Mouse>, <xref:System.Windows.Input.Keyboard>, 및 <xref:System.Windows.Input.Stylus> 정의 연결된 된 이벤트의 클래스에 의해 다시 노출 됩니다 <xref:System.Windows.UIElement> 및 <xref:System.Windows.ContentElement> 새 라우트된 이벤트로 합니다. 기본 요소의 라우트된 이벤트는 원래 연결 된 이벤트를 처리 하 고 다시 사용 하는 이벤트 데이터 클래스를 통해 생성 됩니다.  
  
 입력된 이벤트의 입력된 이벤트 구현을 통해 특정 소스 요소와 연결 되 면 논리적 트리와 시각적 트리 개체의 조합을 기반으로 하며 응용 프로그램 코드에서 처리 되어야 하는 이벤트 경로의 나머지 부분을 통해 라우팅할 수 있습니다.  라우트된 이벤트에서 사용 하 여 이러한 장치 관련 입력된 이벤트를 처리 하는 편리한 방법을 일반적으로 <xref:System.Windows.UIElement> 및 <xref:System.Windows.ContentElement>보다 직관적인 이벤트 처리기 구문을 모두에서 사용할 수 있으므로, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 및 코드입니다. 대신 프로세스를 시작한 연결 된 이벤트를 처리 하도록 선택할 수 있지만 몇 가지 문제에 직면할: 연결 된 이벤트에 대 한 처리기를 연결 하기 위해 true 이벤트 구문 보다는 접근자 메서드를 사용 해야 하 고 연결 된 이벤트의 클래스 처리를 통해 처리 된 표시 될 수도 있습니다.  
  
<a name="whats_next"></a>   
## <a name="whats-next"></a>새로운 기능  
 입력을 처리 하는 몇 가지 기법을 이제 있습니다 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]합니다.  다양 한 유형의 입력된 이벤트 및 라우트된 이벤트 메커니즘에서 사용 하는 향상 된 이해 해야 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]합니다.  
  
 추가 리소스는 사용할 수 있는 설명 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 프레임 워크 요소 및 이벤트 자세히 라우팅. 자세한 내용은 다음 개요를 참조 [명령 개요](../../../../docs/framework/wpf/advanced/commanding-overview.md), [포커스 개요](../../../../docs/framework/wpf/advanced/focus-overview.md), [기본 요소 개요](../../../../docs/framework/wpf/advanced/base-elements-overview.md), [WPF의 트리](../../../../docs/framework/wpf/advanced/trees-in-wpf.md), 및 [라우트된 이벤트 개요](../../../../docs/framework/wpf/advanced/routed-events-overview.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [포커스 개요](../../../../docs/framework/wpf/advanced/focus-overview.md)   
 [명령 개요](../../../../docs/framework/wpf/advanced/commanding-overview.md)   
 [라우트된 이벤트 개요](../../../../docs/framework/wpf/advanced/routed-events-overview.md)   
 [기본 요소 개요](../../../../docs/framework/wpf/advanced/base-elements-overview.md)   
 [속성](../../../../docs/framework/wpf/advanced/properties-wpf.md)