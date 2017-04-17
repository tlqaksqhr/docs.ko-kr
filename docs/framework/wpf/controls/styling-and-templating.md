---
title: "스타일 지정 및 템플릿 | Microsoft Docs"
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
  - "트리거"
  - "스타일, 참조"
  - "이벤트 트리거"
  - "스타일, 필수 구성 요소"
  - "스타일, 선언"
  - "스타일, 개요"
  - "확장 스타일"
  - "스타일, 트리거"
  - "스타일, 이벤트 트리거"
ms.assetid: 481765e5-5467-4a75-9f7b-e10e2ac410d9
caps.latest.revision: 34
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 33
---
# 스타일 지정 및 템플릿
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]스타일 및 템플릿 집합 개발자와 디자이너가 멋진 시각 효과 만들고 해당 제품에 대 한 일관 된 모양을 만들 수 있는 기능 (스타일, 템플릿, 트리거 및 스토리 보드)을 참조 하십시오. 디자이너와 개발자는 응용 프로그램에서 응용 프로그램 기반 광범위 하 게 모양을 사용자 지정할 수 있습니다, 강력한 스타일 및 템플릿 모델은 유지 관리 및 응용 프로그램 간 및 계층 내 모양을 공유 하는 데 필요한. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]해당 모델을 제공 합니다.  
  
 또 다른 기능은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 스타일 모델은 프레젠테이션 및 논리의 분리 합니다. 즉, 디자이너만 사용 하 여 응용 프로그램의 모양을에서 작업할 수 있다는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 개발자가 C# 또는 Visual Basic을 사용 하 여 프로그래밍 논리에 작동 하는 동시에 합니다.  
  
 이 개요는 응용 프로그램의 스타일 및 템플릿 측면에 중점을 둡니다 하 고 모든 데이터 바인딩 개념을 설명 하지 않습니다. 데이터 바인딩에 대 한 정보를 참조 하십시오. [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)합니다.  
  
 또한은 스타일 및 템플릿을 재사용할 수 있게 하는 리소스를 이해 하는 것이 중요 합니다. 리소스에 대 한 자세한 내용은 참조 [XAML 리소스](../../../../docs/framework/wpf/advanced/xaml-resources.md)합니다.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="styling_and_templating_sample"></a>   
## <a name="styling-and-templating-sample"></a>스타일 및 템플릿 샘플  
 이 개요에 사용 되는 코드 예제에서는 다음 그림에 표시 된 간단한 사진 샘플을 기반으로 합니다.  
  
 ![ListView 스타일](../../../../docs/framework/wpf/controls/media/stylingintro-triggers.png "StylingIntro_triggers")  
  
 이 간단한 사진 샘플 스타일 및 템플릿을 사용 하 여 시각적으로 멋진 사용자 환경을 제공 합니다. 이 샘플에는 두 개의 <xref:System.Windows.Controls.TextBlock> 요소와 <xref:System.Windows.Controls.ListBox> 이미지 목록에 바인딩된 컨트롤입니다. 전체 샘플을 참조 하십시오. [스타일 및 템플릿 샘플 소개](http://go.microsoft.com/fwlink/?LinkID=160010)합니다.  
  
<a name="styling_basics"></a>   
## <a name="style-basics"></a>스타일 기본 사항  
 상상할 수 있는 한 <xref:System.Windows.Style> 둘 이상의 요소에 속성 값의 집합을 적용 하는 편리한 방법으로 합니다. 예를 들어 다음은 <xref:System.Windows.Controls.TextBlock> 요소와 해당 기본 모양:  
  
 [!code-xml[StylingIntroSample_snippet#TextBlocks](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSample_snippet/CSharp/Window1.xaml#textblocks)]  
  
 ![스타일 샘플 스크린 샷](../../../../docs/framework/wpf/controls/media/stylingintro-textblocksbefore.png "StylingIntro_TextBlocksBefore")  
  
 와 같은 속성을 설정 하 여 기본 모양을 변경할 수 있습니다 <xref:System.Windows.Controls.Control.FontSize%2A> 및 <xref:System.Windows.Controls.Control.FontFamily%2A>, 각 <xref:System.Windows.Controls.TextBlock> 요소를 직접. 그러나 원하는 경우 프로그램 <xref:System.Windows.Controls.TextBlock> 일부 속성을 공유 하는 요소 만들 수 있습니다는 <xref:System.Windows.Style> 에 `Resources` 의 섹션 프로그램 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일을 다음과 같이:  
  
 [!code-xml[StylingIntroSnippet#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#resources)]  
[!code-xml[StylingIntroSnippet#tb1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#tb1)]  
[!code-xml[StylingIntroSnippet#Resources2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#resources2)]  
  
 설정 하는 경우는 <xref:System.Windows.Style.TargetType%2A> 의 스타일을는 <xref:System.Windows.Controls.TextBlock> 형식이, 스타일 모두에 적용 되는 <xref:System.Windows.Controls.TextBlock> 창에서 구성 요소입니다.  
  
 이제는 <xref:System.Windows.Controls.TextBlock> 요소가 다음과 같이 나타납니다.  
  
 ![스타일 샘플 스크린 샷](../../../../docs/framework/wpf/controls/media/stylingintro-textblocksbasestyle.png "StylingIntro_TextBlocksBaseStyle")  
  
### <a name="extending-styles"></a>확장 스타일  
 두 하 려 한다고 가정해 <xref:System.Windows.Controls.TextBlock> 같은 몇 가지 속성 값을 공유 하는 요소는 <xref:System.Windows.Controls.Control.FontFamily%2A> 및 가운데에 맞춰진 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, 텍스트 "내 그림" 몇 가지 추가 속성을 갖도록 할 수 있습니다. 다음과 같이 첫 번째 스타일을 기반으로 하는 새 스타일을 만들어 수행할 수 있습니다.  
  
 [!code-xml[StylingIntroSnippet#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#resources)]  
[!code-xml[StylingIntroSnippet#tb2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#tb2)]  
[!code-xml[StylingIntroSnippet#Resources2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#resources2)]  
  
 이전 스타일은 지정 하는 `x:Key`합니다. 설정한 스타일을 적용 하려면는 <xref:System.Windows.FrameworkElement.Style%2A> 속성을 사용자 <xref:System.Windows.Controls.TextBlock> 에 `x:Key` 값을 다음과 같이 합니다.  
  
 [!code-xml[StylingIntroSnippet#UIText](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#uitext)]  
  
 이 <xref:System.Windows.Controls.TextBlock> 스타일 설정 되었습니다는 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 의 값 <xref:System.Windows.HorizontalAlignment>, <xref:System.Windows.Controls.TextBlock.FontFamily%2A> 값 `Comic Sans MS`, <xref:System.Windows.Controls.TextBlock.FontSize%2A> 26의 값 및 <xref:System.Windows.Controls.TextBlock.Foreground%2A> 값으로 설정는 <xref:System.Windows.Media.LinearGradientBrush> 예제에 나와 있습니다. 재정의 하는 <xref:System.Windows.Controls.Control.FontSize%2A> 기본 스타일의 값입니다. 여러 개 있으면 <xref:System.Windows.Setter> 에서 동일한 속성을 설정는 <xref:System.Windows.Style>, <xref:System.Windows.Setter> 즉 선언 된 마지막 우선 합니다.  
  
 다음 예를 보여 줍니다는 <xref:System.Windows.Controls.TextBlock> 요소의 모양을:  
  
 ![Textblock 스타일](../../../../docs/framework/wpf/controls/media/stylingintro-textblocks.png "StylingIntro_TextBlocks")  
  
 이 `TitleText` 스타일에 대해 작성 된 스타일을 확장의 <xref:System.Windows.Controls.TextBlock> 유형입니다. 포함 된 스타일을 확장할 수도 있습니다는 `x:Key` 를 사용 하 여는 `x:Key` 값입니다. 예를 들어, 참조에 대 한 제공 된 예제는 <xref:System.Windows.Style.BasedOn%2A> 속성입니다.  
  
### <a name="relationship-of-the-targettype-property-and-the-xkey-attribute"></a>TargetType 속성 및 X:key 특성의 관계  
 첫 번째 예제에서와 같이 설정 된 <xref:System.Windows.Style.TargetType%2A> 속성을 `TextBlock` 스타일을 할당 하지 않고는 `x:Key` 스타일을 모두에 적용 하면 <xref:System.Windows.Controls.TextBlock> 요소입니다. 이 경우에 `x:Key` 로 암시적으로 설정 된 `{x:Type TextBlock}`합니다. 즉, 명시적으로 설정 하는 경우는 `x:Key` 이외의 값으로 값 `{x:Type TextBlock}`, <xref:System.Windows.Style> 모두에 적용 되지 않습니다 <xref:System.Windows.Controls.TextBlock> 요소 자동으로 합니다. 스타일을 적용 해야 하는 대신 (사용 하 여는 `x:Key` 값)에 <xref:System.Windows.Controls.TextBlock> 요소 명시적으로 합니다. 스타일 리소스 섹션에 있고 설정 하지 않은 경우는 <xref:System.Windows.Style.TargetType%2A> 스타일에 다음 속성을 제공 해야는 `x:Key`합니다.  
  
 에 대 한 기본값을 제공 하는 것 외에도 `x:Key`, <xref:System.Windows.Style.TargetType%2A> 속성 setter 속성이 적용 되는 형식을 지정 합니다. 지정 하지 않은 경우는 <xref:System.Windows.Style.TargetType%2A>의 속성을 정규화 해야 프로그램 <xref:System.Windows.Setter> 구문을 사용 하 여 클래스 이름 사용 하 여 개체 `Property="ClassName.Property"`합니다. 예를 들어 설정 하는 대신 `Property="FontSize"`를 설정 해야 <xref:System.Windows.Setter.Property%2A> 를 `"TextBlock.FontSize"` 또는 `"Control.FontSize"`합니다.  
  
 또한 많은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤의 다른 조합으로 구성 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤입니다. 형식의 모든 컨트롤에 적용 되는 스타일을 만드는 경우 예기치 않은 결과가 발생할 수 있습니다. 예를 들어, 대상으로 하는 스타일을 만드는 경우는 <xref:System.Windows.Controls.TextBlock> 에 입력 한 <xref:System.Windows.Window>, 모든 스타일 적용 됩니다 <xref:System.Windows.Controls.TextBlock> 컨트롤 창에서 경우에는 <xref:System.Windows.Controls.TextBlock> 같은 다른 컨트롤의 일부입니다는 <xref:System.Windows.Controls.ListBox>.  
  
### <a name="styles-and-resources"></a>스타일 및 리소스  
 파생 된 모든 요소에 스타일을 사용할 수 <xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.FrameworkContentElement>합니다. 리소스에 사용 하는 스타일을 선언 하는 가장 일반적인 방법은 `Resources` 섹션는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 앞의 예제에 나와 있는 것 처럼 파일입니다. 모든 리소스에 적용 되는 동일한 범위 지정 규칙을 따르며 스타일은 리소스 때문에 스타일을 선언 하는 위치는 스타일을 적용할 수 있는 위치에 영향을 줍니다. 예를 들어, 응용 프로그램 정의의 루트 요소에 스타일을 선언 하는 경우 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일을 응용 프로그램에서 아무 곳 이나 사용할 수 있습니다. 탐색 응용 프로그램을 만들고 응용 프로그램의 중 하나에 선언 된 스타일 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일, 스타일에만 사용할 수 있습니다 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일입니다. 리소스에 대 한 규칙의 범위를 지정 하는 방법에 대 한 자세한 내용은 참조 [XAML 리소스](../../../../docs/framework/wpf/advanced/xaml-resources.md)합니다.  
  
 또한 스타일과의 리소스에 대 한 자세한 정보를 찾을 수 있습니다 [공유 리소스 및 테마](#styling_themes) 이 개요의 뒷부분에 나오는 합니다.  
  
### <a name="setting-styles-programmatically"></a>스타일을 프로그래밍 방식으로 설정  
 요소에 명명 된 스타일을 프로그래밍 방식으로 할당 하려면 스타일 리소스 컬렉션에서 가져오고 요소에 할당할 <xref:System.Windows.FrameworkElement.Style%2A> 속성입니다. 리소스 컬렉션의에서 항목에는 형식의 <xref:System.Object>합니다. 따라서, 검색 된 스타일을 캐스팅 해야는 <xref:System.Windows.Style> 에 할당 하기 전에 <xref:System.Windows.FrameworkElement.Style%2A> 속성입니다. 예를 들어, 정의 된 설정 하려면 `TitleText` 에 스타일는 <xref:System.Windows.Controls.TextBlock> 라는 `textblock1`, 다음을 수행 합니다.  
  
 [!code-csharp[StylingIntroSample_snippet#Code](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSample_snippet/CSharp/Window1.xaml.cs#code)]
 [!code-vb[StylingIntroSample_snippet#Code](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StylingIntroSample_snippet/visualbasic/window1.xaml.vb#code)]  
  
 Note 스타일을 적용 한 후는 봉인 클래스를 변경할 수 없습니다. 이미 적용 된 스타일을 동적으로 변경 하려는 경우 기존 엔터티를 바꾸려면 새 스타일을 만들어야 합니다. 자세한 내용은 참조는 <xref:System.Windows.Style.IsSealed%2A> 속성입니다.  
  
 사용자 지정 논리에 따라 적용할 스타일을 선택 하는 개체를 만들 수 있습니다. 예를 들어, 참조에 대 한 제공 된 예제는 <xref:System.Windows.Controls.StyleSelector> 클래스입니다.  
  
<a name="styling_binding_dynamicresource"></a>   
### <a name="bindings-dynamic-resources-and-event-handlers"></a>바인딩, 동적 리소스 및 이벤트 처리기  
 사용할 수는 `Setter.Value` 속성을 지정 된 [바인딩 태그 확장](../../../../docs/framework/wpf/advanced/binding-markup-extension.md) 또는 [DynamicResource 태그 확장](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md)합니다. 자세한 내용은 참조에 대해 제공 되는 예제는 <xref:System.Windows.Setter.Value%2A?displayProperty=fullName> 속성입니다.  
  
 지금까지이 개요만 setter 속성 값을 설정 하려면 사용을 설명 합니다. 또한 스타일의 이벤트 처리기를 지정할 수 있습니다. 자세한 내용은 참조 <xref:System.Windows.EventSetter>합니다.  
  
<a name="styling_datatemplates"></a>   
## <a name="data-templates"></a>데이터 템플릿  
 이 샘플 응용 프로그램에는 한 <xref:System.Windows.Controls.ListBox> 사진 목록에 바인딩된 컨트롤에:  
  
 [!code-xml[StylingIntroSnippet#UIListBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#uilistbox)]  
  
 이 <xref:System.Windows.Controls.ListBox> 다음과 같이 현재:  
  
 ![템플릿 적용 전의 ListBox](../../../../docs/framework/wpf/controls/media/stylingintro-listboxbefore.png "StylingIntro_ListBoxBefore")  
  
 대부분의 컨트롤은 특정 유형의 콘텐츠를 있고 해당 콘텐츠를 바인딩하는 데이터에서 가져오는 경우가 많습니다. 이 샘플에서는 데이터에는 사진의 목록입니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 사용 하면는 <xref:System.Windows.DataTemplate> 데이터의 시각적 표현을 정의 합니다. 기본적으로, 무엇에 추가한는 <xref:System.Windows.DataTemplate> 렌더링 된 응용 프로그램에서 데이터 모양을 결정 합니다.  
  
 각 사용자 지정 샘플 응용 프로그램에서 `Photo` 개체에는 `Source` 이미지의 파일 경로 지정 하는 문자열 형식의 속성입니다. 현재는 사진 개체가 파일 경로로 나타납니다.  
  
 만들 이미지로 표시 하는 사진에 대 한 한 <xref:System.Windows.DataTemplate> 리소스:  
  
 [!code-xml[StylingIntroSnippet#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#resources)]  
[!code-xml[StylingIntroSnippet#DataTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#datatemplate)]  
[!code-xml[StylingIntroSnippet#Resources2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSnippet/CS/window1.xaml#resources2)]  
  
 다음에 유의 <xref:System.Windows.DataTemplate.DataType%2A> 속성은 매우 비슷합니다는 <xref:System.Windows.Style.TargetType%2A> 속성은 <xref:System.Windows.Style>합니다. 경우에 <xref:System.Windows.DataTemplate> 지정 하는 경우 리소스 섹션에는 <xref:System.Windows.DataTemplate.DataType%2A> 속성 형식에 할당 하지 않은 채로 `x:Key`, <xref:System.Windows.DataTemplate> 해당 형식이 나타날 때마다 적용 됩니다. 항상을 할당할 수 있는 <xref:System.Windows.DataTemplate> 와 `x:Key` 로 설정한 다음는 `StaticResource` 사용 하는 속성에 대 한 <xref:System.Windows.DataTemplate> 등의 형식과 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> 속성 또는 <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> 속성.  
  
 기본적으로,는 <xref:System.Windows.DataTemplate> 위의 예제에서 정의 하는 있을 때마다는 `Photo` 로 표시 되어야 개체는 <xref:System.Windows.Controls.Image> 내는 <xref:System.Windows.Controls.Border>. 이 <xref:System.Windows.DataTemplate>, 이제 응용 프로그램은 다음과 같습니다.  
  
 ![사진 이미지](../../../../docs/framework/wpf/controls/media/stylingintro-photosasimages.png "StylingIntro_PhotosAsImages")  
  
 데이터 템플릿 모델 다른 기능을 제공합니다. 예를 들어를 사용 하 여 다른 컬렉션을 포함 하는 컬렉션 데이터를 표시 하는 경우는 <xref:System.Windows.Controls.HeaderedItemsControl> 등의 입력을 <xref:System.Windows.Controls.Menu> 또는 <xref:System.Windows.Controls.TreeView>는 <xref:System.Windows.HierarchicalDataTemplate>합니다. 다른 데이터 템플릿 기능은 <xref:System.Windows.Controls.DataTemplateSelector>를 선택할 수 있습니다는 <xref:System.Windows.DataTemplate> 에 따라 사용자 지정 논리를 사용 하 여 합니다. 자세한 내용은 참조 [데이터 템플릿 개요](../../../../docs/framework/wpf/data/data-templating-overview.md), 자세한 설명은 다른 데이터 템플릿 기능을 제공 하는 합니다.  
  
<a name="styling_controltemplates"></a>   
## <a name="control-templates"></a>컨트롤 템플릿  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], <xref:System.Windows.Controls.ControlTemplate> 컨트롤의 컨트롤의 모양을 정의 합니다. 새 정의 하 여 컨트롤의 모양과 구조를 변경할 수 있습니다 <xref:System.Windows.Controls.ControlTemplate> 컨트롤입니다. 대부분의 경우가 방법을 사용 하면 충분 한 유연성을 사용자 지정 컨트롤을 직접 작성할 필요가 없습니다. 자세한 내용은 참조 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)합니다.  
  
<a name="styling_triggers"></a>   
## <a name="triggers"></a>트리거  
 트리거 속성을 설정 하거나 속성 값이 변경 하거나 이벤트가 발생할 때 애니메이션 등의 작업을 시작 합니다. <xref:System.Windows.Style>, <xref:System.Windows.Controls.ControlTemplate>, 및 <xref:System.Windows.DataTemplate> 모두는 `Triggers` 트리거 집합을 포함할 수 있는 속성입니다. 다양 한 유형의 트리거가 있습니다.  
  
### <a name="property-triggers"></a>속성 트리거  
 A <xref:System.Windows.Trigger> 집합 속성 값 또는 속성의 값을 기반으로 하는 작업을 시작 속성 트리거 호출 됩니다.  
  
 를 속성 트리거를 사용 하는 방법을 보여 주기 위해 각 변경할 수 있습니다 <xref:System.Windows.Controls.ListBoxItem> 선택 되어 있지 않으면 부분적으로 투명 합니다. 다음 스타일 설정은 <xref:System.Windows.UIElement.Opacity%2A> 의 값을 <xref:System.Windows.Controls.ListBoxItem> 를 `0.5`합니다. 경우는 <xref:System.Windows.Controls.ListBoxItem.IsSelected%2A> 속성은 `true`그러나는 <xref:System.Windows.UIElement.Opacity%2A> 로 설정 되어 `1.0`:  
  
 [!code-xml[StylingIntroSample_snippet#Triggers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSample_snippet/CSharp/Window1.xaml#triggers)]  
[!code-xml[StylingIntroSample_snippet#EndTriggers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSample_snippet/CSharp/Window1.xaml#endtriggers)]  
  
 사용 하 여이 예제는 <xref:System.Windows.Trigger> 속성 값을 설정 하는 <xref:System.Windows.Trigger> 클래스에는 <xref:System.Windows.TriggerBase.EnterActions%2A> 및 <xref:System.Windows.TriggerBase.ExitActions%2A> 작업을 수행 하는 트리거를 사용할 수 있는 속성입니다.  
  
 다음에 유의 <xref:System.Windows.FrameworkElement.MaxHeight%2A> 의 속성은 <xref:System.Windows.Controls.ListBoxItem> 로 설정 되어 `75`합니다. 다음 그림에서는 세 번째 항목에는 선택한 항목이입니다.  
  
 ![ListView 스타일](../../../../docs/framework/wpf/controls/media/stylingintro-triggers.png "StylingIntro_triggers")  
  
### <a name="eventtriggers-and-storyboards"></a>Eventtrigger 및 스토리 보드  
 다른 유형의 트리거는 <xref:System.Windows.EventTrigger>, 일련의 이벤트 발생에 따라 작업을 시작 하는 합니다. 예를 들어, 다음 <xref:System.Windows.EventTrigger> 개체를 지정 하는 마우스 포인터가 들어올 때는 <xref:System.Windows.Controls.ListBoxItem>, <xref:System.Windows.FrameworkElement.MaxHeight%2A> 속성의 값에 애니메이션을 적용 `90` 통해는 `0.2` 두 번째 기간입니다. 속성은 기간 동안 원래 값으로 반환 항목에서 마우스를 움직이면 `1` 두 번째입니다. 방법을 지정 하는 필요 하지 않습니다는 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 에 대 한 값은 <xref:System.Windows.ContentElement.MouseLeave> 애니메이션 합니다. 이 애니메이션에서 원래 값을 추적할 수 있습니다.  
  
 [!code-xml[StylingIntroSample_snippet#EventTriggers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StylingIntroSample_snippet/CSharp/Window1.xaml#eventtriggers)]  
  
 자세한 내용은 참조는 [Storyboard 개요](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)합니다.  
  
 다음 그림에서는 세 번째 항목을 마우스로 가리키고 있습니다.  
  
 ![스타일 샘플 스크린 샷](../../../../docs/framework/wpf/controls/media/stylingintro-eventtriggers.png "StylingIntro_EventTriggers")  
  
### <a name="multitriggers-datatriggers-and-multidatatriggers"></a>MultiTriggers, Datatrigger, 및 MultiDataTriggers  
 외에 <xref:System.Windows.Trigger> 및 <xref:System.Windows.EventTrigger>, 다른 유형의 트리거가 있습니다. <xref:System.Windows.MultiTrigger> 여러 조건에 따라 속성 값을 설정할 수 있습니다. 사용 하면 <xref:System.Windows.DataTrigger> 및 <xref:System.Windows.MultiDataTrigger> 조건의 속성 데이터 바인딩된 경우입니다.  
  
<a name="styling_themes"></a>   
## <a name="shared-resources-and-themes"></a>공유 리소스 및 테마  
 일반적인 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] 응용 프로그램에는 응용 프로그램에 걸쳐 적용 되는 여러 사용자 인터페이스 (UI) 리소스 있을 수 있습니다. 종합적으로 리소스의이 집합에는 응용 프로그램에 대 한 테마를 간주할 수 있습니다. [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]지원 패키지 사용자에 대 한 인터페이스 (UI) 리소스 테마를 사용 하 여 제공 캡슐화 된 리소스 사전에서 <xref:System.Windows.ResourceDictionary> 클래스입니다.  
  
 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]테마는 스타일 및 템플릿 메커니즘을 사용 하 여 정의 됩니다는 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] 요소의 시각화를 사용자 지정을 노출 합니다.  
  
 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]테마 리소스는 포함 된 리소스 사전에 저장 됩니다. 이러한 리소스 사전이 서명된 된 어셈블리 내에 포함 되어야 있고 하나 포함할 수 또는 side-by-side-어셈블리 코드 자체와 동일한 어셈블리에 있습니다. PresentationFramework.dll, 포함 된 어셈블리의 경우 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] 컨트롤, 테마 리소스가 일련의 side by side 어셈블리에 배치 됩니다.  
  
 테마는 요소의 스타일을 검색할 때 검색 하는 마지막 좋습니다 됩니다. 일반적으로 검색을는 적절 한 리소스를 검색 하는 요소 트리를 탐색 하 여 시작 응용 프로그램 리소스 컬렉션을 확인 하 고 마지막으로 시스템을 쿼리 합니다. 이 통해 응용 프로그램 개발자는 테마에 도달 하기 전에 트리 또는 응용 프로그램 수준에서 개체에 대 한 스타일을 다시 정의할 수 있습니다.  
  
 리소스 사전을 여러 응용 프로그램에서 테마를 다시 사용할 수 있도록 하는 개별 파일로 정의할 수 있습니다. 또한 동일한 종류의 리소스 하지만 서로 다른 값으로 제공 하는 여러 개의 리소스 사전을 정의 하 여 스왑 가능한 테마를 만들 수 있습니다. 이러한 스타일 또는 응용 프로그램 수준에서 다른 리소스를 다시 정의 하는 것이 좋습니다 응용 프로그램에 스킨을 제공 합니다.  
  
 스타일 및 템플릿, 응용 프로그램을 비롯 한 리소스 집합을 공유를 만들 수는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일을 정의 <xref:System.Windows.ResourceDictionary>합니다. 예를 들어 살펴보겠습니다의 일부를 보여 주는 다음 그림은 [보려면](http://go.microsoft.com/fwlink/?LinkID=160041):  
  
 ![컨트롤 템플릿 예제](../../../../docs/framework/wpf/controls/media/stylingintro-controltemplateexamples.png "StylingIntro_ControlTemplateExamples")  
  
 보면는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 샘플에서 파일을 알 수 있습니다는 모든 파일에서 다음:  
  
 [!code-xml[ControlTemplateExamples#MergedDictionaries](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/button.xaml#mergeddictionaries)]  
  
 공유 하는 것 `shared.xaml`를 정의 하는 <xref:System.Windows.ResourceDictionary> 동일 하 게 표시 하는 샘플의 컨트롤을 활성화 하는 스타일 및 브러시 리소스 집합이 포함 된.  
  
 자세한 내용은 참조 [병합 된 리소스 사전](../../../../docs/framework/wpf/advanced/merged-resource-dictionaries.md)합니다.  
  
 테마를 사용자 지정 컨트롤을 만드는 경우의 외부 컨트롤 라이브러리 섹션을 참조는 [컨트롤 제작 개요](../../../../docs/framework/wpf/controls/control-authoring-overview.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [WPF의 pack Uri](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md)   
 [방법: ControlTemplate에서 생성 된 요소 찾기](../../../../docs/framework/wpf/controls/how-to-find-controltemplate-generated-elements.md)   
 [DataTemplate에서 생성 된 요소 찾기](../../../../docs/framework/wpf/data/how-to-find-datatemplate-generated-elements.md)