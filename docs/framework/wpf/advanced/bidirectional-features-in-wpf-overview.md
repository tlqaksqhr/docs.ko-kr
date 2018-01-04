---
title: "WPF의 양방향 기능 개요"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Span elements [WPF]
- bidirectional features [WPF]
ms.assetid: fd850e25-7dba-408c-b521-8873e51dc968
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b50d98d5f02a59a013d7577f0e312e6ffde35690
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="bidirectional-features-in-wpf-overview"></a>WPF의 양방향 기능 개요
다른 개발 플랫폼 달리 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 혼합된 왼쪽에서 오른쪽을 마우스 오른쪽 단추로 같은 문서에 데이터를 유지 하는 예를 들어, 양방향 콘텐츠의 신속 하 게 개발을 지 원하는 많은 기능이 있습니다. 같은 시간에 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 예: 아랍어 및 히브리어 사용자 양방향 기능이 필요한 사용자를 위한 뛰어난 경험을 만듭니다.  
  
 다음 섹션에서는 최상의 양방향 콘텐츠 표시를 수행하는 방법을 보여주는 예제와 함께 다양한 양방향 기능을 설명합니다. 대부분의 예제를 사용 하 여 [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)]개념을 쉽게 적용할 수 있지만, [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] 또는 [!INCLUDE[TLA#tla_visualb](../../../../includes/tlasharptla-visualb-md.md)] 코드입니다.  
  

  
<a name="FlowDirection"></a>   
## <a name="flowdirection"></a>FlowDirection  
 콘텐츠 흐름 방향을 정의 하는 기본 속성을 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램은 <xref:System.Windows.FrameworkElement.FlowDirection%2A>합니다. 이 속성은 두 개의 열거형 값 중 하나로 설정할 수 있습니다 <xref:System.Windows.FlowDirection.LeftToRight> 또는 <xref:System.Windows.FlowDirection.RightToLeft>합니다. 속성을 모두 사용할 수 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 에서 상속 되는 요소 <xref:System.Windows.FrameworkElement>합니다.  
  
 다음 예제에서는 설정 흐름의 방향을 <xref:System.Windows.Controls.TextBox> 요소입니다.  
  
 **왼쪽에서 오른쪽 흐름 방향**  
  
 [!code-xaml[LTRRTL#LTR](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LTRRTL/CS/Pane1.xaml#ltr)]  
  
 **오른쪽에서 왼쪽 흐름 방향**  
  
 [!code-xaml[LTRRTL#RTL](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LTRRTL/CS/Pane1.xaml#rtl)]  
  
 다음 그림에서는 이전 코드 렌더링 방법을 보여 줍니다.  
  
 **FlowDirection를 보여 주는 그래픽**  
  
 ![TextBlock 맞춤](../../../../docs/framework/wpf/advanced/media/lefttorightrighttoleft.PNG "LefttoRightRighttoLeft")  
  
 내에서 요소는 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 트리는 상속는 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 해당 컨테이너에서 합니다. 다음 예제에서는 <xref:System.Windows.Controls.TextBlock> 내는 <xref:System.Windows.Controls.Grid>에 상주 하는 <xref:System.Windows.Window>합니다. 설정의 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 에 대 한는 <xref:System.Windows.Window> 설정에 대 한 의미는 <xref:System.Windows.Controls.Grid> 및 <xref:System.Windows.Controls.TextBlock> 도 합니다.  
  
 다음 예제에서는 설정 <xref:System.Windows.FrameworkElement.FlowDirection%2A>합니다.  
  
 [!code-xaml[FlowDirection#FlowDirection](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDirection/CS/Window1.xaml#flowdirection)]  
  
 최상위 수준 <xref:System.Windows.Window> 에 <xref:System.Windows.FlowDirection.RightToLeft> <xref:System.Windows.FlowDirection>그 안에 포함 된 모든 요소는 또한 동일 상속 되므로 <xref:System.Windows.FrameworkElement.FlowDirection%2A>합니다. 지정 된 재정의 하는 요소에 대 한 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 명시적 방향 변경을 두 번째 등을 추가 해야 <xref:System.Windows.Controls.TextBlock> 로 변경 하는 이전 예제 <xref:System.Windows.FlowDirection.LeftToRight>합니다. No <xref:System.Windows.FrameworkElement.FlowDirection%2A> 정의 된 기본 <xref:System.Windows.FlowDirection.LeftToRight> 적용 됩니다.  
  
 다음 그래픽은 이전 예제의 출력을 보여 줍니다.  
  
 **지정된 FlowDirection을 명시적으로 보여 주는 그래픽**  
  
 ![흐름 방향 설명](../../../../docs/framework/wpf/advanced/media/flowdir.PNG "FlowDir")  
  
<a name="FlowDocument"></a>   
## <a name="flowdocument"></a>FlowDocument  
 와 같은 대부분의 개발 플랫폼 [!INCLUDE[TLA#tla_html](../../../../includes/tlasharptla-html-md.md)], [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] Java 양방향 콘텐츠 개발에 대 한 특별 한 지원을 제공 합니다. 과 같은 태그 언어 [!INCLUDE[TLA#tla_html](../../../../includes/tlasharptla-html-md.md)] 콘텐츠 작성자 예를 들어 필수 방향에 텍스트를 표시 하는 데 필요한 태그를 제공는 [!INCLUDE[TLA#tla_html](../../../../includes/tlasharptla-html-md.md)] 4.0 태그, "dir" 값으로 "rtl" 또는 "ltr"를 사용 합니다. 이 태그는 비슷합니다는 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 속성 이지만 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 속성 레이아웃 텍스트 콘텐츠에 더 많은 고급 방식으로 작동 하며 텍스트 이외의 다른 콘텐츠를 사용할 수 있습니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], <xref:System.Windows.Documents.FlowDocument> 는 용도가 넓은 함수로 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 텍스트, 테이블, 이미지 및 기타 요소를 조합한을 호스팅할 수 있는 요소입니다. 다음 섹션의 샘플은 이 요소를 사용합니다.  
  
 텍스트를 추가 <xref:System.Windows.Documents.FlowDocument> 을 여러 방법으로 더에서 수행할 수 있습니다. 작업을 수행 하는 간단한 방법을 통해는 <xref:System.Windows.Documents.Paragraph> 하는 블록 수준 요소 텍스트와 같은 그룹 콘텐츠 하는 데 사용 합니다. 샘플 사용 인라인 수준 요소에 텍스트를 추가 하려면 <xref:System.Windows.Documents.Span> 및 <xref:System.Windows.Documents.Run>합니다. <xref:System.Windows.Documents.Span>다른 인라인 요소를 그룹화 하는 데 사용 되는 인라인 수준의 유동 콘텐츠 요소는 동안는 <xref:System.Windows.Documents.Run> 인라인 수준의 유동 콘텐츠 요소는 서식 있는 텍스트 실행을 포함 하기 위한 것이 있습니다. A <xref:System.Windows.Documents.Span> 여러 개 포함할 수 <xref:System.Windows.Documents.Run> 요소입니다.  
  
 다양 한 네트워크 이름을; 공유에 있는 문서를 포함 하는 첫 번째 문서 예제 예를 들어 `\\server1\folder\file.ext`합니다. 이 네트워크 링크가 아랍어나 영어 문서에 있는지 여부에 따라 같은 방식으로 항상 표시될 수 있습니다. 다음 그림에서는 아랍어 <xref:System.Windows.FlowDirection.RightToLeft> 문서.  
  
 **Span 요소를 사용하여 설명하는 그래픽**  
  
 ![오른쪽에서 왼쪽으로 진행되는 문서](../../../../docs/framework/wpf/advanced/media/flowdocument.PNG "FlowDocument")  
  
 텍스트는 <xref:System.Windows.FlowDirection.RightToLeft>모든 특수와 같은 문자는 "\\"는 오른쪽에서 왼쪽된 맞춤에서 텍스트를 구분 합니다. 올바른 순서로 표시 되지 않으며 링크 인해, 따라서이 문제를 해결 하는 텍스트를 포함 해야 별도 유지 하기 위해 <xref:System.Windows.Documents.Run> 흐르는 <xref:System.Windows.FlowDirection.LeftToRight>합니다. 대신 별도 <xref:System.Windows.Documents.Run> 각 언어에 대 한 문제를 해결 하는 더 나은 방법은 높은 아랍어에 덜 사용 되는 영어 텍스트를 포함 하는 <xref:System.Windows.Documents.Span>합니다.  
  
 다음 그래픽은 이에 대한 예입니다.  
  
 **Span 요소에 포함된 Run 요소를 사용하여 설명하는 그래픽**  
  
 ![XamlPad 스크린 샷](../../../../docs/framework/wpf/advanced/media/runspan.PNG "RunSpan")  
  
 다음 예제를 사용 하 여 <xref:System.Windows.Documents.Run> 및 <xref:System.Windows.Documents.Span> 문서에 있는 요소입니다.  
  
 [!code-xaml[RunSpan#RunSpan](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RunSpan/CS/Window1.xaml#runspan)]  
  
<a name="SpanElements"></a>   
## <a name="span-elements"></a>Span 요소  
 <xref:System.Windows.Documents.Span> 여러 흐름 방향의 텍스트 사이의 경계 구분으로 작동 하는 요소입니다.  도 <xref:System.Windows.Documents.Span> 같은 흐름 방향으로 요소 한 범위를 다른 양방향으로 간주 됩니다는 <xref:System.Windows.Documents.Span> 요소를 정렬 하는 컨테이너에 <xref:System.Windows.FlowDirection>, 내의 내용만 <xref:System.Windows.Documents.Span> 요소 뒤에 오는 <xref:System.Windows.FlowDirection> 의 <xref:System.Windows.Documents.Span>합니다.  
  
 다음 그래픽에서는 일부의 흐름 방향 <xref:System.Windows.Controls.TextBlock> 요소입니다.  
  
 **여러 TextBlock 요소로 FlowDirection을 보여주는 그래픽**  
  
 ![흐름 방향이 다른 텍스트 블록](../../../../docs/framework/wpf/advanced/media/span.PNG "범위")  
  
 사용 하는 방법을 보여 주는 다음 예제는 <xref:System.Windows.Documents.Span> 및 <xref:System.Windows.Documents.Run> 요소 이전 그래픽에 표시 된 결과를 생성 합니다.  
  
 [!code-xaml[Span#Span](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Span/CS/Window1.xaml#span)]  
  
 에 <xref:System.Windows.Controls.TextBlock> 샘플에서 요소는 <xref:System.Windows.Documents.Span> 요소는 레이아웃에 따라는 <xref:System.Windows.FlowDirection> 부모 내의 각 텍스트의 <xref:System.Windows.Documents.Span> 자체에 따라 요소 흐름 <xref:System.Windows.FlowDirection>합니다. 라틴어와 아랍어 또는 다른 언어에 적용됩니다.  
  
### <a name="adding-xmllang"></a>Xml:lang 추가  
 다음 그래픽에서는 같은 숫자 및 산술 연산자를 사용 하는 또 다른 예로 `"200.0+21.4=221.4"`합니다. 공지만는 <xref:System.Windows.FlowDirection> 설정 됩니다.  
  
 **FlowDirection만을 사용하여 숫자를 표시하는 그래픽**  
  
 ![오른쪽에서 왼쪽으로 진행되는 숫자](../../../../docs/framework/wpf/advanced/media/langattribute.PNG "LangAttribute")  
  
 이 응용 프로그램의 사용자는 출력에 만족 하지 않을 <xref:System.Windows.FlowDirection> 숫자 모양이 아니기 때문 아랍어 숫자 올바릅니다.  
  
 XAML 요소를 포함할 수는 [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] 특성 (`xml:lang`) 언어의 각 요소를 정의 하는입니다. XAML에서는 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 언어 원칙 표현의 `xml:lang` 트리의 부모 요소에 적용 되는 값이 자식 요소에 의해 사용 됩니다. 이전 예제에서는 언어에 대해 정의 되지 않은 때문에 <xref:System.Windows.Documents.Run> 요소 또는 해당 최상위 수준 요소를 기본 `xml:lang` 사용 된 변수인 `en-US` XAML에 대 한 합니다. 내부 숫자의 셰이핑 알고리즘 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 이 경우는 영어-해당 언어의 숫자를 선택 합니다. 아랍어 렌더링을 올바르게 번호 `xml:lang` 설정 해야 합니다.  
  
 다음 그래픽에서는 사용 하 여 예제 `xml:lang` 추가 합니다.  
  
 **xml: lang 특성을 사용하여 설명하는 그래픽**  
  
 ![오른쪽에서 왼쪽으로 진행되는 아랍어 숫자](../../../../docs/framework/wpf/advanced/media/langattribute2.PNG "LangAttribute2")  
  
 다음 예제에서는 추가 `xml:lang` 응용 프로그램에 있습니다.  
  
 [!code-xaml[LangAttribute#LangAttribute](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LangAttribute/CS/Window1.xaml#langattribute)]  
  
 대부분의 언어는 서로 다른 제공 `xml:lang` 대상된 지역에 따라 값 `"ar-SA"` 및 `"ar-EG"` 아랍어의 합니다. 앞의 예제에서는 모두 정의 해야 하는 방법을 보여 줍니다는 `xml:lang` 및 <xref:System.Windows.FlowDirection> 값입니다.  
  
<a name="FlowDirectionNontext"></a>   
## <a name="flowdirection-with-non-text-elements"></a>텍스트가 아닌 요소가 있는 FlowDirection  
 <xref:System.Windows.FlowDirection>뿐만 아니라 텍스트 방향을 텍스트 요소 뿐만 아니라 거의 모든 다른 흐름 방향에서 정의 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 요소입니다. 다음 그래픽에 표시 된는 <xref:System.Windows.Controls.ToolBar> 가로 사용 하 여 <xref:System.Windows.Media.LinearGradientBrush> 의 배경을 그리는 데 합니다.  
  
 **그라데이션이 왼쪽에서 오른쪽인 도구 모음을 표시하는 그래픽**  
  
 ![그라데이션 스크린 샷](../../../../docs/framework/wpf/advanced/media/gradient.PNG "그라데이션")  
  
 설정한 후는 <xref:System.Windows.FlowDirection> 를 <xref:System.Windows.FlowDirection.RightToLeft>뿐 아니라,는 <xref:System.Windows.Controls.ToolBar> 단추 오른쪽에서 왼쪽도 있지만 정렬 <xref:System.Windows.Media.LinearGradientBrush> 해당 오프셋을 오른쪽에서 왼쪽으로 이동 합니다.  
  
 다음 그래픽에서는의 맞추는 <xref:System.Windows.Media.LinearGradientBrush>합니다.  
  
 **그라데이션이 오른쪽에서 왼쪽인 도구 모음을 표시하는 그래픽**  
  
 ![오른쪽에서 왼쪽으로 진행되는 그라데이션](../../../../docs/framework/wpf/advanced/media/gradient2-wpf.PNG "Gradient2_WPF")  
  
 다음 예제에서는 그립니다는 <xref:System.Windows.FlowDirection.RightToLeft> <xref:System.Windows.Controls.ToolBar>합니다. (제거를 그릴 왼쪽에서 오른쪽는 <xref:System.Windows.FlowDirection> 특성에 <xref:System.Windows.Controls.ToolBar>합니다.  
  
 [!code-xaml[Gradient#Gradient](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Gradient/CS/Window1.xaml#gradient)]  
  
<a name="FlowDirectionExceptions"></a>   
### <a name="flowdirection-exceptions"></a>FlowDirection 예외  
 몇 가지 경우도 있습니다. 여기서 <xref:System.Windows.FlowDirection> 예상 대로 작동 하지 않습니다. 이 섹션에서는 이러한 예외 중 두 가지를 설명합니다.  
  
 **Image**  
  
 <xref:System.Windows.Controls.Image> 이미지를 표시 하는 컨트롤을 나타냅니다. [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] 함께 사용할 수 있습니다는 <xref:System.Windows.Controls.Image.Source%2A> 속성을 정의 하는 [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] 의 <xref:System.Windows.Controls.Image> 표시 합니다.  
  
 다른 달리 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 요소는 <xref:System.Windows.Controls.Image> 상속 하지 않습니다는 <xref:System.Windows.FlowDirection> 컨테이너에서 합니다. 그러나 경우는 <xref:System.Windows.FlowDirection> 에 명시적으로 설정 되어 <xref:System.Windows.FlowDirection.RightToLeft>, <xref:System.Windows.Controls.Image> 가로로 대칭 되어 표시 됩니다. 양방향 콘텐츠의 개발자에게 편리한 기능으로 구현됩니다. 경우에 따라 이미지를 가로로 대칭 이동하면 원하는 효과가 나타나기 때문입니다.  
  
 다음 그래픽에서는 대칭 이동 된 <xref:System.Windows.Controls.Image>합니다.  
  
 **대칭 이동된 이미지를 보여주는 그래픽**  
  
 ![XamlPad 스크린 샷](../../../../docs/framework/wpf/advanced/media/image.PNG "이미지")  
  
 다음 예제에서는 <xref:System.Windows.Controls.Image> 상속 하도록 실패는 <xref:System.Windows.FlowDirection> 에서 <xref:System.Windows.Controls.StackPanel> 해당 항목을 포함 합니다. **참고** 라는 파일이 있어야 **ms_logo.jpg** 이 예를 실행 하려면 C:\ 드라이브에 있습니다.  
  
 [!code-xaml[Image#Image](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Image/CS/Window1.xaml#image)]  
  
 **참고** 다운로드 파일에 포함 되는 **ms_logo.jpg** 파일입니다. 코드는 .jpg 파일이 프로젝트 내에 있지 않지만 C:\ 드라이브 어딘가에 있다고 가정합니다. 프로젝트 파일에서 C:\ 드라이브로 .jpg를 복사하거나 프로젝트 내부에서 파일을 찾도록 코드를 변경해야 합니다. 이러한 변경 작업을 수행 하 `Source="file://c:/ms_logo.jpg"` 를 `Source="ms_logo.jpg"`합니다.  
  
 **경로**  
  
 이외에 <xref:System.Windows.Controls.Image>, 다른 흥미로운 요소는 <xref:System.Windows.Shapes.Path>합니다. 경로는 일련의 연결된 선 및 곡선을 그릴 수 있는 개체입니다. 에 비슷한 방식으로 동작 하는 <xref:System.Windows.Controls.Image> 에 대 한 해당 <xref:System.Windows.FlowDirection>; 예를 들면 해당 <xref:System.Windows.FlowDirection.RightToLeft> <xref:System.Windows.FlowDirection> 은 가로 반영 해당 <xref:System.Windows.FlowDirection.LeftToRight> 하나입니다. 그러나 달리는 <xref:System.Windows.Controls.Image>, <xref:System.Windows.Shapes.Path> 상속 해당 <xref:System.Windows.FlowDirection> 개와 컨테이너에서 하지 않아도 명시적으로 지정 합니다.  
  
 다음 예제에서는 3개의 선을 사용하여 간단한 화살표를 그립니다. 첫 번째 화살표는 <xref:System.Windows.FlowDirection.RightToLeft> 흐름 방향을 <xref:System.Windows.Controls.StackPanel> 하는 시작점과 끝점은 오른쪽에 루트에서 측정 됩니다. 명시적에 있는 두 번째 화살표 <xref:System.Windows.FlowDirection.RightToLeft> <xref:System.Windows.FlowDirection> 또한 오른쪽에서 시작 합니다. 그러나 세 번째 화살표는 왼쪽에 시작 루트가 있습니다. 참조를 그리기 대 한 자세한 내용은 <xref:System.Windows.Media.LineGeometry> 및 <xref:System.Windows.Media.GeometryGroup>합니다.  
  
 [!code-xaml[Paths#Paths](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Paths/CS/Window1.xaml#paths)]  
  
 다음 그래픽은 이전 예제의 출력을 보여 줍니다.  
  
 **Path 요소를 사용하여 그린 화살표를 보여 주는 그래픽**  
  
 ![Paths](../../../../docs/framework/wpf/advanced/media/paths.PNG "Paths")  
  
 <xref:System.Windows.Controls.Image> 및 <xref:System.Windows.Shapes.Path> 은 두 가지 예는 방법의 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 사용 하 여 <xref:System.Windows.FlowDirection>합니다. 배치 옆에 있는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 요소는 컨테이너 내에서 특정 방향으로 <xref:System.Windows.FlowDirection> 등 요소와 함께 사용할 수 있습니다 <xref:System.Windows.Controls.InkPresenter> 는 표면에 잉크를 렌더링 하 <xref:System.Windows.Media.LinearGradientBrush>, <xref:System.Windows.Media.RadialGradientBrush>합니다. 왼쪽에서 오른쪽의 동작을 모방 하는 콘텐츠에 대 한 왼쪽된 동작에 대 한 권한이 필요할 때마다 또는 반대로 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 해당 기능을 제공 합니다.  
  
<a name="NumberSubstitution"></a>   
## <a name="number-substitution"></a>숫자 대체  
 지금까지 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] 예에서는 숫자는 저장에 대 한 서로 다른 로캘에서 통합 된이 숫자의 내부 저장소를 유지 하면서 동일한 숫자에 대 한 다양 한 문화적 도형 표시 하 여 숫자 대체를 지원 했습니다 잘 알려진 16 진수 값, 0x40, 선택한 언어에 따라 표시 되었습니다.  
  
 에서는 응용 프로그램이 다른 언어에서 변환 하기 위해 필요 없이 숫자 값이 처리 되는이, 예를 들어 사용자를 열 수는 [!INCLUDE[TLA#tla_xl](../../../../includes/tlasharptla-xl-md.md)] 지역화 아랍어에서 스프레드시트 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] 아랍어, 모양 번호를 표시 하 고 있지만에서 열 유럽 버전의 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] 같은 번호는 및입니다. 보통 동일한 문서에서 숫자와 같이 표시되기 때문에 쉼표 구분 기호와 백분율 기호와 같은 다른 기호에도 필요합니다.  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]는 동일한 기능을 계속 유지하며 대체가 사용되는 시기와 방법을 사용자가 더 많이 제어할 수 있도록 이 기능에 대한 지원을 추가합니다. 이 기능은 모든 언어를 대상으로 하지만, 응용 프로그램을 실행하는 다양한 문화권 때문에 특정 언어에 대한 숫자 모양을 응용 프로그램 개발자가 지정하기 어려운 양방향 콘텐츠에서 더욱 유용합니다.  
  
 작동 하는 방법을 숫자 대체를 제어 하는 핵심 속성 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 는 <xref:System.Windows.Media.NumberSubstitution.Substitution%2A> 종속성 속성입니다. <xref:System.Windows.Media.NumberSubstitution> 클래스 텍스트의 숫자가 표시 되는 방법을 지정 합니다. 동작을 정의하는 세 가지 공용 속성이 있습니다. 다음은 각 속성에 대한 요약입니다.  
  
 **CultureSource:**  
  
 이 속성은 숫자에 대한 문화권을 결정하는 방법을 지정합니다. 3 가지 걸리는 <xref:System.Windows.Media.NumberCultureSource> 열거형 값입니다.  
  
-   재정의: 숫자 문화권이 <xref:System.Windows.Media.NumberSubstitution.CultureOverride%2A> 속성입니다.  
  
-   텍스트: 숫자 문화권이 텍스트 실행의 문화권입니다. 태그에서 것 `xml:lang`, 또는 해당 별칭인 `Language` 속성 (<xref:System.Windows.FrameworkElement.Language%2A> 또는 <xref:System.Windows.FrameworkContentElement.Language%2A>). 또한에서 파생 된 클래스에 대 한 기본값을은 <xref:System.Windows.FrameworkContentElement>합니다. 이러한 클래스에는 <xref:System.Windows.Documents.Paragraph?displayProperty=nameWithType>, <xref:System.Windows.Documents.Table?displayProperty=nameWithType>, <xref:System.Windows.Documents.TableCell?displayProperty=nameWithType> 등입니다.  
  
-   사용자: 숫자 문화권이 현재 스레드의 문화권입니다. 이 속성의 모든 하위 클래스에 대 한 기본값은 <xref:System.Windows.FrameworkElement> 같은 <xref:System.Windows.Controls.Page>, <xref:System.Windows.Window> 및 <xref:System.Windows.Controls.TextBlock>합니다.  
  
 **CultureOverride**:  
  
 <xref:System.Windows.Media.NumberSubstitution.CultureOverride%2A> 속성은 경우에 사용 된 <xref:System.Windows.Media.NumberSubstitution.CultureSource%2A> 속성이로 설정 되어 <xref:System.Windows.Media.NumberCultureSource.Override> 그렇지 않은 경우 무시 됩니다. 숫자 문화권을 지정합니다. 값이 `null`, 기본값은 EN-US로 해석 됩니다.  
  
 **대체**:  
  
 이 속성에는 수행할 숫자 대체의 형식을 지정합니다. 다음 중 하나를 사용 <xref:System.Windows.Media.NumberSubstitutionMethod> 열거형 값입니다.  
  
-   <xref:System.Windows.Media.NumberSubstitutionMethod.AsCulture>: 대체 메서드가 숫자 문화권에 따라 결정 됩니다 <xref:System.Globalization.NumberFormatInfo.DigitSubstitution%2A?displayProperty=nameWithType> 속성입니다. 이 값이 기본값입니다.  
  
-   <xref:System.Windows.Media.NumberSubstitutionMethod.Context>: 숫자 문화권은 아랍어 또는 페르시아어 문화권, 하는 경우 숫자는 컨텍스트에 따라 달라 집니다 지정 합니다.  
  
-   <xref:System.Windows.Media.NumberSubstitutionMethod.European>: 항상 숫자 유럽 자리 수로 렌더링 됩니다.  
  
-   <xref:System.Windows.Media.NumberSubstitutionMethod.NativeNational>: 숫자는 문화권에 의해 지정 된 대로 숫자 문화권에 대 한 국가별 숫자를 사용 하 여 렌더링 되는 <xref:System.Globalization.CultureInfo.NumberFormat%2A>합니다.  
  
-   <xref:System.Windows.Media.NumberSubstitutionMethod.Traditional>: 숫자는 숫자 문화권에 대 한 일반적인 숫자를 사용 하 여 렌더링 됩니다. 대부분의 문화권에 대 한 이것이 동일 <xref:System.Windows.Media.NumberSubstitutionMethod.NativeNational>합니다. 그러나 <xref:System.Windows.Media.NumberSubstitutionMethod.NativeNational> 되며이 값 아랍어 숫자가 모든 아랍어 문화권에 대 한 일부 아랍어 문화권에 대 한 라틴어 숫자에 발생 합니다.  
  
 이 값은 양방향 콘텐츠 개발자에게 무슨 의미입니까? 대부분의 경우에서 개발자만 정의 해야 할 수도 <xref:System.Windows.FlowDirection> 및 각 텍스트 언어 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 예를 들어 요소 `Language="ar-SA"` 및 <xref:System.Windows.Media.NumberSubstitution> 맞게 올바른 숫자를 표시 하는 논리를 담당 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]합니다. 다음 예제에서는 아랍어과 영어 번호를 사용 하는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 아랍어 버전의에서 실행 되는 응용 프로그램 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]합니다.  
  
 [!code-xaml[Numbers#Numbers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Numbers/CS/Window1.xaml#numbers)]  
  
 다음 그림의 아랍어 버전에서 실행 하는 경우 이전 샘플의 출력을 보여 줍니다 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]합니다.  
  
 **표시되는 아랍어 및 영어 숫자를 표시하는 그래픽**  
  
 ![숫자가 있는 XamlPad 스크린 샷](../../../../docs/framework/wpf/advanced/media/numbers.PNG "번호")  
  
 <xref:System.Windows.FlowDirection> 가 중요 한이 예에서 설정 때문에 <xref:System.Windows.FlowDirection> 를 <xref:System.Windows.FlowDirection.LeftToRight> 생성 유럽 숫자가 있습니다. 다음 섹션에서는 문서 전체에서 숫자를 단일하게 표시하는 방법을 설명합니다. 이 예제에서 아랍어 창을 실행하지 않는 경우 모든 숫자는 유럽 숫자로 표시됩니다.  
  
 **대체 규칙 정의**  
  
 실제 응용 프로그램에서, 언어를 프로그래밍 방식으로 설정해야 합니다. 설정 하려는 예를 들어는 `xml:lang` 특성은 시스템에서 사용 하는 것과 동일 하 게 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], 응용 프로그램 상태에 따라 언어를 변경할 또는 합니다.  
  
 확인 하려는 경우 응용 프로그램의 상태에 따라 변경, 확인에서 제공 하는 다른 기능을 사용 하 여 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]합니다.  
  
 먼저, 응용 프로그램 구성 요소의 설정 `NumberSubstitution.CultureSource="Text"`합니다. 이 설정을 사용 하면 설정을에서 제공 되지 않는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 텍스트 요소에 대해 "User" 기본적으로 같은 <xref:System.Windows.Controls.TextBlock>합니다.  
  
 예:  
  
||  
|-|  
|`<TextBlock`<br /><br /> `Name="text1" NumberSubstitution.CultureSource="Text">`<br /><br /> `1234+5679=6913`<br /><br /> `</TextBlock>`|  
  
 해당 [!INCLUDE[TLA2#tla_lhcshrp](../../../../includes/tla2sharptla-lhcshrp-md.md)] 코드, 설정 된 `Language` 속성 예를 들어 `"ar-SA"`합니다.  
  
||  
|-|  
|`text1.Language =`<br /><br /> `System.Windows.Markup.XmlLanguage.GetLanguage("ar-SA");`|  
  
 로 설정 해야 하는 경우는 `Language` 속성을 현재 사용자의 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 언어는 다음 코드를 사용 합니다.  
  
||  
|-|  
|`text1.Language =`<br /><br /> `System.Windows.Markup.XmlLanguage.GetLanguage(`<br /><br /> `System.Globalization.CultureInfo.CurrentUICulture.IetfLanguageTag);`|  
  
 <xref:System.Globalization.CultureInfo.CurrentCulture%2A>런타임 시 현재 스레드에서 사용 하는 현재 문화권을 나타냅니다.  
  
 최종 [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] 예제는 다음 예제와 유사 해야 합니다.  
  
 [!code-xaml[Numbers2#Numbers2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Numbers2/CS/Window1.xaml#numbers2)]  
  
 최종 [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] 예제는 다음과 비슷해야 합니다.  
  
 [!code-csharp[NumbersCSharp#NumbersCSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NumbersCSharp/CSharp/Window1.xaml.cs#numberscsharp)]  
  
 다음 그래픽은 프로그래밍 언어 중 하나와 같은 모양의 창을 보여 줍니다.  
  
 **아랍어 숫자를 표시하는 그래픽**  
  
 ![아랍어 숫자](../../../../docs/framework/wpf/advanced/media/numbers2.PNG "Numbers2")  
  
 **대체 속성 사용**  
  
 작동 하는 방식으로 숫자 대체 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 텍스트 요소의 언어에 따라 해당 <xref:System.Windows.FlowDirection>합니다. 경우는 <xref:System.Windows.FlowDirection> 는 왼쪽에서 오른쪽, 유럽 숫자가 렌더링 됩니다. 그러나 아랍어 텍스트 앞 또는 "ar"로 언어를 설정 하는 경우와 <xref:System.Windows.FlowDirection> 은 <xref:System.Windows.FlowDirection.RightToLeft>, 아랍어 숫자가 렌더링 됩니다.  
  
 그러나 경우에 따라 모든 사용자에 대해 유럽 숫자 같이 단일하게 적용할 수 있습니다. 또는 <xref:System.Windows.Documents.Table> 특정 셀 <xref:System.Windows.Style>합니다. 사용 하는 작업을 수행 하 한 가지 쉬운 방법은 <xref:System.Windows.Media.NumberSubstitution.Substitution%2A> 속성입니다.  
  
 다음 예에서 첫 번째 <xref:System.Windows.Controls.TextBlock> 없는 <xref:System.Windows.Media.NumberSubstitution.Substitution%2A> 알고리즘 예상 대로 아랍어 숫자를 표시 하도록 속성을 설정 합니다. 그러나 두 번째에서 <xref:System.Windows.Controls.TextBlock>, 대체 유럽으로 설정 된 기본 대체 아랍어 숫자에 대 한 재정의 및 유럽 숫자가 표시 됩니다.  
  
 [!code-xaml[Numbers3#Numbers3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Numbers3/CS/Window1.xaml#numbers3)]
