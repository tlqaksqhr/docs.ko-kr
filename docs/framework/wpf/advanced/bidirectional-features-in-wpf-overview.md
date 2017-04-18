---
title: "WPF의 양방향 기능 개요 | Microsoft Docs"
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
  - "양방향 기능"
  - "FlowDirection 속성"
  - "FlowDocument 속성"
  - "Span 요소"
ms.assetid: fd850e25-7dba-408c-b521-8873e51dc968
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# WPF의 양방향 기능 개요
다른 개발 플랫폼과 달리 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에는 양방향 콘텐츠의 신속한 개발을 지원하는 많은 기능\(예: 동일한 문서에 왼쪽에서 오른쪽 데이터 및 오른쪽에서 왼쪽 데이터를 혼합하는 기능\)이 있습니다.  이와 동시에 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 아랍어 및 히브리어 사용자와 같은 양방향 기능이 필요한 사용자를 위한 뛰어난 경험을 제공합니다.  
  
 다음 단원에서는 양방향 콘텐츠를 가장 잘 표시하는 방법에 대한 예제와 함께 다양한 양방향 기능에 대해 설명합니다.  대부분의 샘플에서는 [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)]이 사용되지만 이러한 개념을 [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] 또는 [!INCLUDE[TLA#tla_visualb](../../../../includes/tlasharptla-visualb-md.md)] 코드에 쉽게 적용할 수 있습니다.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="FlowDirection"></a>   
## FlowDirection  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램에서 콘텐츠 흐름 방향을 정의하는 기본 속성은 <xref:System.Windows.FrameworkElement.FlowDirection%2A>입니다.  이 속성은 두 개의 열거형 값인 <xref:System.Windows.FlowDirection>와 <xref:System.Windows.FlowDirection> 중 하나로 설정할 수 있습니다.  이 속성은 <xref:System.Windows.FrameworkElement>에서 상속되는 모든 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 요소에 사용할 수 있습니다.  
  
 다음 예제에서는 <xref:System.Windows.Controls.TextBox> 요소의 흐름 방향을 설정합니다.  
  
 **왼쪽에서 오른쪽으로 흐름 방향**  
  
 [!code-xml[LTRRTL#LTR](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LTRRTL/CS/Pane1.xaml#ltr)]  
  
 **오른쪽에서 왼쪽으로 흐름 방향**  
  
 [!code-xml[LTRRTL#RTL](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LTRRTL/CS/Pane1.xaml#rtl)]  
  
 다음 그래픽에서는 위 코드가 렌더링되는 방법을 보여 줍니다.  
  
 **FlowDirection을 보여 주는 그래픽**  
  
 ![TextBlock 맞춤](../../../../docs/framework/wpf/advanced/media/lefttorightrighttoleft.png "LefttoRightRighttoLeft")  
  
 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 트리 내의 요소는 컨테이너에서 <xref:System.Windows.FrameworkElement.FlowDirection%2A>을 상속합니다.  다음 예제에서 <xref:System.Windows.Controls.TextBlock>은 <xref:System.Windows.Window>에 상주하는 <xref:System.Windows.Controls.Grid> 안에 있습니다.  <xref:System.Windows.FrameworkElement.FlowDirection%2A>을 <xref:System.Windows.Window>에 대해 설정하는 것은 <xref:System.Windows.Controls.Grid> 및 <xref:System.Windows.Controls.TextBlock>에 대해서도 설정하는 것을 의미합니다.  
  
 다음 예제에서는 <xref:System.Windows.FrameworkElement.FlowDirection%2A>을 설정하는 방법을 보여 줍니다.  
  
 [!code-xml[FlowDirection#FlowDirection](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDirection/CS/Window1.xaml#flowdirection)]  
  
 최상위 수준 <xref:System.Windows.Window>에는 <xref:System.Windows.FlowDirection> <xref:System.Windows.FlowDirection>이 있으므로 포함된 모든 요소도 동일한 <xref:System.Windows.FrameworkElement.FlowDirection%2A>을 상속합니다.  지정된 <xref:System.Windows.FrameworkElement.FlowDirection%2A>을 요소에서 재정의하려면 <xref:System.Windows.FlowDirection>으로 변경되는 이전 예제의 두 번째 <xref:System.Windows.Controls.TextBlock>과 같은 명시적 방향 변경을 추가해야 합니다.  <xref:System.Windows.FrameworkElement.FlowDirection%2A>이 정의되지 않은 경우 기본 <xref:System.Windows.FlowDirection>가 적용됩니다.  
  
 다음 그래픽에서는 위 예제의 출력을 보여 줍니다.  
  
 **명시적으로 할당된 FlowDirection을 보여 주는 그래픽**  
  
 ![흐름 방향 설명](../../../../docs/framework/wpf/advanced/media/flowdir.png "FlowDir")  
  
<a name="FlowDocument"></a>   
## FlowDocument  
 [!INCLUDE[TLA#tla_html](../../../../includes/tlasharptla-html-md.md)], [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] 및 Java와 같은 대부분의 개발 플랫폼은 양방향 콘텐츠 개발을 위한 특수한 지원을 제공합니다.  [!INCLUDE[TLA#tla_html](../../../../includes/tlasharptla-html-md.md)]과 같은 태그 언어는 텍스트를 필수 방향으로 표시하는 데 필요한 태그\(예: “rtl” 또는 “ltr”을 값으로 사용하는 [!INCLUDE[TLA#tla_html](../../../../includes/tlasharptla-html-md.md)] 4.0 태그 “dir”\)를 콘텐츠 작성자에게 제공합니다.  이 태그는 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 속성과 비슷하지만 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 속성은 텍스트 콘텐츠에 대한 고급 레이아웃 방법을 제공하며 텍스트가 아닌 콘텐츠에 사용할 수 있습니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 <xref:System.Windows.Documents.FlowDocument>는 텍스트, 표, 이미지 및 기타 요소의 조합을 호스팅할 수 있는 다양성을 가진 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 요소입니다.  다음 단원의 샘플에서는 이 요소를 사용합니다.  
  
 <xref:System.Windows.Documents.FlowDocument>에 텍스트를 추가하는 작업을 여러 방법으로 수행할 수 있습니다.  간단한 방법은 텍스트와 같은 콘텐츠를 그룹화하는 데 사용되는 블록 수준 요소인 <xref:System.Windows.Documents.Paragraph>를 사용하는 것입니다.  인라인 수준 요소에 텍스트를 추가하기 위해 샘플에서는 <xref:System.Windows.Documents.Span> 및 <xref:System.Windows.Documents.Run>을 사용합니다.  <xref:System.Windows.Documents.Span>은 다른 인라인 요소를 그룹화하는 데 사용되는 인라인 수준 유동 콘텐츠 요소이고 <xref:System.Windows.Documents.Run>은 서식 없는 텍스트의 실행을 포함하기 위한 인라인 수준 유동 콘텐츠 요소입니다.  <xref:System.Windows.Documents.Span>은 여러 <xref:System.Windows.Documents.Run> 요소를 포함할 수 있습니다.  
  
 첫 번째 문서 예제에 나와 있는 문서의 네트워크 공유 이름은 여러 개입니다\(예: `\\server1\folder\file.ext`\).  아랍어 또는 영어 문서에서 이러한 네트워크 링크가 있는 경우 항상 동일한 방법으로 표시되기를 원할 것입니다.  다음 그래픽에서는 아랍어 <xref:System.Windows.FlowDirection> 문서의 링크를 보여 줍니다.  
  
 **Span 요소 사용을 보여 주는 그래픽**  
  
 ![오른쪽에서 왼쪽으로 진행되는 문서](../../../../docs/framework/wpf/advanced/media/flowdocument.png "FlowDocument")  
  
 텍스트가 <xref:System.Windows.FlowDirection>이므로 “\\”와 같은 모든 특수 문자는 오른쪽에서 왼쪽 순서로 텍스트를 구분합니다.  이로 인해 링크가 올바르게 순서로 표시되지 않으며 이 문제를 해결하려면 <xref:System.Windows.FlowDirection>로 흐르는 별개의 <xref:System.Windows.Documents.Run>을 유지하도록 텍스트를 포함해야 합니다.  언어별로 개별 <xref:System.Windows.Documents.Run>을 가지는 대신에 사용 빈도가 낮은 영어 텍스트를 사용 빈도가 높은 아랍어 <xref:System.Windows.Documents.Span>에 포함하면 이 문제를 보다 쉽게 해결할 수 있습니다.  
  
 다음은 이를 보여 주는 그래픽입니다.  
  
 **Span 요소에 포함된 Run 요소 사용을 보여 주는 그래픽**  
  
 ![XamlPad 스크린 샷](../../../../docs/framework/wpf/advanced/media/runspan.png "RunSpan")  
  
 다음 예제에서는 문서에서 <xref:System.Windows.Documents.Run> 및 <xref:System.Windows.Documents.Span> 요소를 사용하는 방법을 보여 줍니다.  
  
 [!code-xml[RunSpan#RunSpan](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RunSpan/CS/Window1.xaml#runspan)]  
  
<a name="SpanElements"></a>   
## Span 요소  
 <xref:System.Windows.Documents.Span> 요소는 흐름 방향이 서로 다른 텍스트 간을 구분하는 경계로 사용됩니다.  흐름 방향이 동일한 <xref:System.Windows.Documents.Span> 요소도 다른 양방향 범위를 가진 것으로 간주되며 이는 컨테이너의 <xref:System.Windows.FlowDirection>에 따라 <xref:System.Windows.Documents.Span> 요소의 순서가 지정되고 <xref:System.Windows.Documents.Span> 내의 콘텐츠만 <xref:System.Windows.Documents.Span>의 <xref:System.Windows.FlowDirection>을 따르는 것을 의미합니다.  
  
 다음 그래픽에서는 여러 <xref:System.Windows.Controls.TextBlock> 요소의 흐름 방향을 보여 줍니다.  
  
 **여러 TextBlock 요소의 FlowDirection을 보여 주는 그래픽**  
  
 ![여러 흐름 방향의 텍스트 블록](../../../../docs/framework/wpf/advanced/media/span.png "Span")  
  
 다음 예제에서는 <xref:System.Windows.Documents.Span> 및 <xref:System.Windows.Documents.Run> 요소를 사용하여 이전 그래픽에 표시된 결과를 생성하는 방법을 보여 줍니다.  
  
 [!code-xml[Span#Span](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Span/CS/Window1.xaml#span)]  
  
 샘플의 <xref:System.Windows.Controls.TextBlock> 요소에서 <xref:System.Windows.Documents.Span> 요소는 해당 부모의 <xref:System.Windows.FlowDirection>에 따라 레이아웃되지만 각 <xref:System.Windows.Documents.Span> 요소 내의 텍스트는 고유한 <xref:System.Windows.FlowDirection>에 따라 흐릅니다.  이는 라틴어와 아랍어 또는 다른 모든 언어에 적용할 수 있습니다.  
  
### xml:lang 추가  
 다음 그래픽에서는 `"200.0+21.4=221.4"`와 같은 숫자 및 산술 연산자를 사용하는 다른 예제를 보여 줍니다.  <xref:System.Windows.FlowDirection>만 설정된다는 것에 주의합니다.  
  
 **FlowDirection만 사용하여 숫자를 표시하는 그래픽**  
  
 ![오른쪽에서 왼쪽으로 진행되는 숫자](../../../../docs/framework/wpf/advanced/media/langattribute.png "LangAttribute")  
  
 <xref:System.Windows.FlowDirection>이 올바르지만 숫자가 아랍어 숫자 모양이 아니기 때문에 이 응용 프로그램의 사용자는 출력에 만족하지 않을 것입니다.  
  
 XAML 요소는 각 요소의 언어를 정의하는 [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] 특성\(`xml:lang`\)을 포함할 수 있습니다.  XAML은 트리의 부모 요소에 적용된 `xml:lang` 값이 자식 요소에서 사용되는 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 언어 원칙도 지원합니다.  이전 예제에서는 <xref:System.Windows.Documents.Run> 요소 또는 해당 최상위 요소에 언어가 정의되지 않았으므로 기본 `xml:lang`\(XAML의 경우 `en-US`\)가 사용되었습니다.  [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]의 내부 숫자 셰이핑 알고리즘은 해당 언어\(이 경우는 영어\)의 숫자를 선택합니다.  아랍어 숫자를 올바르게 렌더링하려면 `xml:lang`를 설정해야 합니다.  
  
 다음 그래픽에서는 `xml:lang`가 추가된 예제를 보여 줍니다.  
  
 **xml:lang 특성 사용을 보여 주는 그래픽**  
  
 ![오른쪽에서 왼쪽으로 진행되는 아랍어 숫자](../../../../docs/framework/wpf/advanced/media/langattribute2.png "LangAttribute2")  
  
 다음 예제에서는 응용 프로그램에 `xml:lang`를 추가합니다.  
  
 [!code-xml[LangAttribute#LangAttribute](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LangAttribute/CS/Window1.xaml#langattribute)]  
  
 대부분의 언어의 경우 `xml:lang` 값이 대상으로 지정된 지역에 따라 서로 다릅니다. 예를 들어 `"ar-SA"` 및 `"ar-EG"`는 두 개의 아랍어 변형을 나타냅니다.  위 예제에서는 `xml:lang` 및 <xref:System.Windows.FlowDirection> 값을 모두 정의해야 한다는 것을 보여 줍니다.  
  
<a name="FlowDirectionNontext"></a>   
## 텍스트가 아닌 요소가 있는 FlowDirection  
 <xref:System.Windows.FlowDirection>은 텍스트 요소에서 텍스트가 흐르는 방법뿐만 아니라 거의 모든 다른 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 요소의 흐름 방향을 정의합니다.  다음 그래픽에서는 가로 <xref:System.Windows.Media.LinearGradientBrush>를 사용하여 해당 배경을 그리는 <xref:System.Windows.Controls.ToolBar>를 보여 줍니다.  
  
 **왼쪽에서 오른쪽으로의 그라데이션이 있는 도구 모음을 표시하는 그래픽**  
  
 ![그라데이션 스크린 샷](../../../../docs/framework/wpf/advanced/media/gradient.png "Gradient")  
  
 <xref:System.Windows.FlowDirection>을 <xref:System.Windows.FlowDirection>로 설정한 후 <xref:System.Windows.Controls.ToolBar> 단추가 오른쪽에서 왼쪽으로 정렬될 뿐만 아니라 <xref:System.Windows.Media.LinearGradientBrush>는 오른쪽에서 왼쪽으로 흐르도록 해당 오프셋을 다시 맞춥니다.  
  
 다음 그래픽에서는 <xref:System.Windows.Media.LinearGradientBrush>의 다시 맞춤을 보여 줍니다.  
  
 **오른쪽에서 왼쪽으로의 그라데이션이 있는 도구 모음을 표시하는 그래픽**  
  
 ![오른쪽에서 왼쪽으로 진행되는 그라데이션](../../../../docs/framework/wpf/advanced/media/gradient2-wpf.png "Gradient2\_WPF")  
  
 다음 예제에서는 <xref:System.Windows.FlowDirection> <xref:System.Windows.Controls.ToolBar>를 그립니다.  왼쪽에서 오른쪽으로 그리려면 <xref:System.Windows.Controls.ToolBar>에서 <xref:System.Windows.FlowDirection> 특성을 제거합니다.  
  
 [!code-xml[Gradient#Gradient](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Gradient/CS/Window1.xaml#gradient)]  
  
<a name="FlowDirectionExceptions"></a>   
### FlowDirection 예외  
 <xref:System.Windows.FlowDirection>가 예상대로 작동하지 않는 몇 가지 경우가 있습니다.  이 단원에서는 이러한 예외 중 두 가지를 설명합니다.  
  
 **Image**  
  
 <xref:System.Windows.Controls.Image>는 이미지를 표시하는 컨트롤을 나타냅니다.  [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)]에서는 표시할 <xref:System.Windows.Controls.Image>의 [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)]를 정의하는 <xref:System.Windows.Controls.Image.Source%2A> 속성과 함께 사용할 수 있습니다.  
  
 다른 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 요소와 달리 <xref:System.Windows.Controls.Image>는 컨테이너에서 <xref:System.Windows.FlowDirection>을 상속하지 않습니다.  그러나 <xref:System.Windows.FlowDirection>이 명시적으로 <xref:System.Windows.FlowDirection>로 설정된 경우 <xref:System.Windows.Controls.Image>는 가로로 대칭되어 표시됩니다.  이미지를 가로로 대칭하면 원하는 효과가 발생하는 경우가 있기 때문에 이는 양방향 콘텐츠 개발자를 위한 편리한 기능으로 구현됩니다.  
  
 다음 그래픽에서는 대칭 이동한 <xref:System.Windows.Controls.Image>를 보여 줍니다.  
  
 **대칭 이동한 이미지를 보여 주는 그래픽**  
  
 ![XamlPad 스크린 샷](../../../../docs/framework/wpf/advanced/media/image.png "Image")  
  
 다음 예제에서는 <xref:System.Windows.FlowDirection>이 포함된 <xref:System.Windows.Controls.StackPanel>에서 <xref:System.Windows.Controls.Image>가 이 속성을 상속하는 데 실패하는 경우를 보여 줍니다.  **참고** 이 예제를 실행하려면 C:\\ 드라이브에 **ms\_logo.jpg**라는 파일이 있어야 합니다.  
  
 [!code-xml[Image#Image](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Image/CS/Window1.xaml#image)]  
  
 **참고** 다운로드 파일에는 **ms\_logo.jpg** 파일이 포함되어 있습니다.  코드에서는 .jpg 파일이 프로젝트에 없지만 C:\\ 드라이브의 어딘가에 있다고 가정합니다.  .jpg를 프로젝트 파일에서 C:\\ 드라이브로 복사하거나 코드를 변경하여 프로젝트 안에서 파일을 찾도록 해야 합니다.  이렇게 하려면 `Source="file://c:/ms_logo.jpg"`를 `Source="ms_logo.jpg"`로 변경합니다.  
  
 **Paths**  
  
 <xref:System.Windows.Controls.Image> 외에도 또 다른 흥미로운 요소는 <xref:System.Windows.Shapes.Path>입니다.  Path는 일련의 연결된 선과 곡선을 그릴 수 있는 개체로,  해당 <xref:System.Windows.FlowDirection>과 관련해서는 <xref:System.Windows.Controls.Image>와 비슷하게 작동합니다. 예를 들어 해당 <xref:System.Windows.FlowDirection> <xref:System.Windows.FlowDirection>은 해당 <xref:System.Windows.FlowDirection>의 수평 미러입니다.  그러나 <xref:System.Windows.Controls.Image>와 달리 <xref:System.Windows.Shapes.Path>는 컨테이너에서 <xref:System.Windows.FlowDirection>을 상속하며 이를 명시적으로 지정할 필요가 없습니다.  
  
 다음 예제에서는 세 개의 선을 사용하여 간단한 화살표를 그립니다.  첫 번째 화살표는 <xref:System.Windows.Controls.StackPanel>에서 <xref:System.Windows.FlowDirection> 흐름 방향을 상속하므로 해당 시작점과 끝점이 오른쪽의 루트로부터 측정됩니다.  명시적 <xref:System.Windows.FlowDirection> <xref:System.Windows.FlowDirection>이 있는 두 번째 화살표도 오른쪽에서 시작됩니다.  그러나 세 번째 화살표의 경우 왼쪽에 시작 루트가 있습니다.  그리기에 대한 자세한 내용은 <xref:System.Windows.Media.LineGeometry> 및 <xref:System.Windows.Media.GeometryGroup>을 참조하십시오.  
  
 [!code-xml[Paths#Paths](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Paths/CS/Window1.xaml#paths)]  
  
 다음 그래픽에서는 위 예제의 출력을 보여 줍니다.  
  
 **Path 요소를 사용하여 그린 화살표를 보여 주는 그래픽**  
  
 ![경로](../../../../docs/framework/wpf/advanced/media/paths.png "Paths")  
  
 <xref:System.Windows.Controls.Image> 및 <xref:System.Windows.Shapes.Path>는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서 <xref:System.Windows.FlowDirection>을 사용하는 방법을 보여 주는 두 가지 예입니다.  컨테이너 내에서 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 요소를 특정 방향으로 레이아웃하는 것 외에도 <xref:System.Windows.FlowDirection>은 화면에서 잉크를 렌더링하는 <xref:System.Windows.Controls.InkPresenter>, <xref:System.Windows.Media.LinearGradientBrush>, <xref:System.Windows.Media.RadialGradientBrush> 등과 같은 요소와 함께 사용할 수 있습니다.  왼쪽에서 오른쪽으로의 동작을 모방하는 오른쪽에서 왼쪽으로의 동작 또는 그 반대의 동작이 콘텐츠에 필요한 경우 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]는 항상 해당 기능을 제공합니다.  
  
<a name="NumberSubstitution"></a>   
## 숫자 대체  
 지금까지 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]는 동일한 숫자에 대한 다양한 문화권 도형 표시를 허용하여 숫자 대체를 지원했으며 이러한 숫자의 내부 저장소는 다양한 로캘에서 통합된 상태로 유지되었습니다. 예를 들어 숫자는 잘 알려진 16진수 값인 0x40, 0x41 등으로 저장되지만 선택한 언어에 따라 표시됩니다.  
  
 이에 따라 응용 프로그램은 숫자 값을 한 언어에서 다른 언어로 변환할 필요 없이 처리할 수 있었습니다. 예를 들어 사용자는 지역화된 아랍어 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]에서 [!INCLUDE[TLA#tla_xl](../../../../includes/tlasharptla-xl-md.md)] 스프레드시트를 열고 아랍어 모양의 숫자를 볼 수 있지만 해당 스프레드시트를 유럽 버전의 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]에서 열 경우 유럽 버전으로 표시된 동일한 숫자를 볼 수 있습니다.  쉼표 구분 기호 및 백분율 기호와 같은 다른 기호는 일반적으로 동일한 문서에서 숫자를 수반하므로 이러한 기호에도 이 작업이 필요합니다.  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]는 동일한 기능을 계속 지원할 뿐만 아니라 이 기능에 대한 추가 지원을 제공하여 대체가 사용되는 시기와 방법을 사용자가 더 많이 제어할 수 있게 합니다.  이 기능은 모든 언어에 사용하도록 디자인되었지만 응용 프로그램이 실행되는 다양한 문화권으로 인해 응용 프로그램 개발자가 특정 언어의 숫자 셰이핑을 수행하기 어려운 양방향 콘텐츠에서 특히 유용합니다.  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서 숫자 대체가 작동하는 방법을 제어하는 핵심 속성은 <xref:System.Windows.Media.NumberSubstitution.Substitution%2A> 종속성 속성입니다.  <xref:System.Windows.Media.NumberSubstitution> 클래스는 텍스트의 숫자를 표시하는 방법을 지정합니다.  이 클래스에는 해당 동작을 정의하는 세 개의 공용 속성이 있습니다.  각 속성을 요약하면 다음과 같습니다.  
  
 **CultureSource:**  
  
 이 속성은 숫자에 대한 문화권을 결정하는 방법을 지정하며  다음과 같은 세 개의 <xref:System.Windows.Media.NumberCultureSource> 열거형 값 중 하나를 사용합니다.  
  
-   Override: 숫자 문화권이 <xref:System.Windows.Media.NumberSubstitution.CultureOverride%2A> 속성의 문화권입니다.  
  
-   Text: 숫자 문화권이 텍스트 런\(Text Run\)의 문화권입니다.  태그에서 이것은 `xml:lang` 또는 해당 별칭인 `Language` 속성\(<xref:System.Windows.FrameworkElement.Language%2A> 또는 <xref:System.Windows.FrameworkContentElement.Language%2A>\)입니다.  또한 <xref:System.Windows.FrameworkContentElement>에서 파생되는 클래스의 기본값입니다.  이러한 클래스에는 <xref:System.Windows.Documents.Paragraph?displayProperty=fullName>, <xref:System.Windows.Documents.Table?displayProperty=fullName>, <xref:System.Windows.Documents.TableCell?displayProperty=fullName> 등이 포함됩니다.  
  
-   User: 숫자 문화권이 현재 스레드의 문화권입니다.  이 속성은 <xref:System.Windows.Controls.Page>, <xref:System.Windows.Window> 및 <xref:System.Windows.Controls.TextBlock>와 같은 <xref:System.Windows.FrameworkElement>의 모든 서브클래스에 대한 기본값입니다.  
  
 **CultureOverride**:  
  
 <xref:System.Windows.Media.NumberSubstitution.CultureOverride%2A> 속성은 <xref:System.Windows.Media.NumberSubstitution.CultureSource%2A> 속성이 <xref:System.Windows.Media.NumberCultureSource>로 설정된 경우에만 사용되고 그렇지 않은 경우 무시됩니다.  이 속성은 숫자 문화권을 지정합니다.  기본값인 `null` 값은 en\-US로 해석됩니다.  
  
 **Substitution**:  
  
 이 속성은 수행할 숫자 대체의 형식을 지정하며  다음 <xref:System.Windows.Media.NumberSubstitutionMethod> 열거형 값 중 하나를 사용합니다.  
  
-   <xref:System.Windows.Media.NumberSubstitutionMethod>: 대체 메서드가 숫자 문화권의 <xref:System.Globalization.NumberFormatInfo.DigitSubstitution%2A?displayProperty=fullName> 속성에 따라 결정됩니다.  이 값이 기본값입니다.  
  
-   <xref:System.Windows.Media.NumberSubstitutionMethod>: 숫자 문화권이 아랍어 또는 페르시아어 문화권이면 컨텍스트에 따라 숫자가 결정되도록 지정합니다.  
  
-   <xref:System.Windows.Media.NumberSubstitutionMethod>: 숫자가 항상 유럽 숫자로 렌더링됩니다.  
  
-   <xref:System.Windows.Media.NumberSubstitutionMethod>: 문화권의 <xref:System.Globalization.CultureInfo.NumberFormat%2A>에 의해 지정된 대로 숫자 문화권에 대한 해당 국가의 숫자를 사용하여 숫자가 렌더링됩니다.  
  
-   <xref:System.Windows.Media.NumberSubstitutionMethod>: 숫자 문화권에 대한 전통 숫자를 사용하여 숫자가 렌더링됩니다.  대부분의 문화권에서 <xref:System.Windows.Media.NumberSubstitutionMethod>과 동일합니다.  그러나 <xref:System.Windows.Media.NumberSubstitutionMethod>을 사용하면 일부 아랍어 문화권에 대해 라틴 숫자가 사용되며 이 값을 사용하면 모든 아랍어 문화권에 대해 아랍어 숫자가 사용됩니다.  
  
 양방향 콘텐츠 개발자에게 이러한 값은 어떤 의미가 있습니까?  대부분의 경우 개발자는 각 텍스트 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 요소의 <xref:System.Windows.FlowDirection> 및 언어\(예: `Language="ar-SA"`\)만 정의하면 되고 올바른 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]에 따라 숫자를 표시하는 작업은 <xref:System.Windows.Media.NumberSubstitution> 논리에 의해 수행됩니다.  다음 예제에서는 아랍어 버전의 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]에서 실행 중인 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 응용 프로그램에서 아랍어 및 영어 숫자를 사용하는 경우를 보여 줍니다.  
  
 [!code-xml[Numbers#Numbers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Numbers/CS/Window1.xaml#numbers)]  
  
 다음 그래픽에서는 아랍어 버전의 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]에서 실행 중인 경우 이전 샘플의 출력을 보여 줍니다.  
  
 **표시된 아랍어 및 영어 숫자를 보여 주는 그래픽**  
  
 ![숫자가 있는 XamlPad 스크린 샷](../../../../docs/framework/wpf/advanced/media/numbers.png "Numbers")  
  
 <xref:System.Windows.FlowDirection>을 <xref:System.Windows.FlowDirection>로 설정하면 유럽 숫자가 생성되므로 이 경우 <xref:System.Windows.FlowDirection>이 중요했습니다.  다음 단원에서는 문서 전체에서 통일되게 숫자를 표시하는 방법에 대해 설명합니다.  이 예제가 아랍어 Windows에서 실행 중이 아닌 경우 모든 숫자는 유럽 숫자로 표시됩니다.  
  
 **대체 규칙 정의**  
  
 실제 응용 프로그램에서는 Language를 프로그래밍 방식으로 설정해야 할 수 있습니다.  예를 들어 `xml:lang` 특성을 시스템의 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]에 사용되는 것과 동일하게 설정하거나 응용 프로그램 상태에 따라 언어를 변경할 수 있습니다.  
  
 응용 프로그램의 상태에 따라 변경을 수행하려면 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에 의해 제공되는 다른 기능을 사용합니다.  
  
 먼저 응용 프로그램 구성 요소의 `NumberSubstitution.CultureSource="Text"`를 설정합니다.  이 설정을 사용하면 <xref:System.Windows.Controls.TextBlock>과 같은 “User”를 기본값으로 사용하는 텍스트 요소의 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]에서 설정이 제공되지 않습니다.  
  
 예를 들면 다음과 같습니다.  
  
||  
|-|  
|`<TextBlock`<br /><br /> `Name="text1" NumberSubstitution.CultureSource="Text">`<br /><br /> `1234+5679=6913`<br /><br /> `</TextBlock>`|  
  
 해당 [!INCLUDE[TLA2#tla_lhcshrp](../../../../includes/tla2sharptla-lhcshrp-md.md)] 코드에서 `Language` 속성을 예를 들어 `"ar-SA"`로 설정합니다.  
  
||  
|-|  
|`text1.Language =`<br /><br /> `System.Windows.Markup.XmlLanguage.GetLanguage("ar-SA");`|  
  
 `Language` 속성을 현재 사용자의 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 언어로 설정해야 할 경우 다음 코드를 사용합니다.  
  
||  
|-|  
|`text1.Language =`<br /><br /> `System.Windows.Markup.XmlLanguage.GetLanguage(`<br /><br /> `System.Globalization.CultureInfo.CurrentUICulture.IetfLanguageTag);`|  
  
 <xref:System.Globalization.CultureInfo.CurrentCulture%2A>는 런타임에 현재 스레드에 사용되는 현재 문화권을 나타냅니다.  
  
 최종 [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] 예제는 다음 예제와 비슷해야 합니다.  
  
 [!code-xml[Numbers2#Numbers2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Numbers2/CS/Window1.xaml#numbers2)]  
  
 최종 [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] 예제는 다음과 비슷해야 합니다.  
  
 [!code-csharp[NumbersCSharp#NumbersCSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/NumbersCSharp/CSharp/Window1.xaml.cs#numberscsharp)]  
  
 다음 그래픽에서는 둘 중 하나의 프로그래밍 언어에 대해 창이 어떻게 표시되는지 보여 줍니다.  
  
 **아랍어 숫자를 표시하는 그래픽**  
  
 ![아랍어 숫자](../../../../docs/framework/wpf/advanced/media/numbers2.png "Numbers2")  
  
 **대체 속성 사용**  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서 숫자 대체가 작동하는 방법은 텍스트 요소의 Language 및 해당 <xref:System.Windows.FlowDirection>에 따라 달라집니다.  <xref:System.Windows.FlowDirection>이 왼쪽에서 오른쪽인 경우 유럽 숫자가 렌더링됩니다.  그러나 아랍어 텍스트가 앞에 오거나 언어가 “ar”로 설정되고 <xref:System.Windows.FlowDirection>이 <xref:System.Windows.FlowDirection>인 경우 아랍어 숫자가 렌더링됩니다.  
  
 그러나 모든 사용자를 위한 유럽 숫자와 같이 통일된 응용 프로그램을 만들어야 할 경우가 있습니다.  또는 특정 <xref:System.Windows.Style>의 <xref:System.Windows.Documents.Table> 셀에 아랍어 숫자가 필요할 수 있습니다.  이 작업을 수행하기 위한 쉬운 방법은 <xref:System.Windows.Media.NumberSubstitution.Substitution%2A> 속성을 사용하는 것입니다.  
  
 다음 예제에서 첫 번째 <xref:System.Windows.Controls.TextBlock>에는 <xref:System.Windows.Media.NumberSubstitution.Substitution%2A> 속성이 설정되어 있지 않으므로 알고리즘은 아랍어 숫자를 예상대로 표시합니다.  그러나 두 번째 <xref:System.Windows.Controls.TextBlock>에서는 대체가 유럽으로 설정되어 아랍어 숫자에 대한 기본 대체를 재정의하므로 유럽 숫자가 표시됩니다.  
  
 [!code-xml[Numbers3#Numbers3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Numbers3/CS/Window1.xaml#numbers3)]