---
title: "WPF의 트리 | Microsoft Docs"
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
  - "요소 트리"
  - "논리 트리(logical tree)"
  - "시각적 트리(visual tree)"
ms.assetid: e83f25e5-d66b-4fc7-92d2-50130c9a6649
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# WPF의 트리
많은 기술에서 요소와 구성 요소는 트리 구조로 구성되며, 개발자는 이 트리의 개체 노드를 직접 조작하여 응용 프로그램의 렌더링이나 동작에 영향을 줍니다.  또한 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서는 여러 가지 트리 구조 비유를 통해 프로그램 요소 간의 관계를 정의합니다.  대체로 WPF 개발자는 개체 트리 비유를 개념적으로 사용하여 코드에서 응용 프로그램을 만들거나 XAML에서 응용 프로그램의 일부를 정의할 수 있지만, 이 작업을 위해 XML DOM에서 사용할 수 있는 API 같은 일반적인 개체 트리 조작 API 대신 특정 API를 호출하거나 특정 태그를 사용합니다.  WPF는 트리 비유 뷰를 제공하는 두 개의 도우미 클래스 <xref:System.Windows.LogicalTreeHelper>와 <xref:System.Windows.Media.VisualTreeHelper>를 노출합니다.  시각적 트리 및 논리적 트리란 용어는 특정한 주요 WPF 기능의 동작을 이해하는 데 유용하므로 WPF 설명서에서도 사용됩니다.  이 항목에서는 시각적 트리 및 논리적 트리가 나타내는 대상을 정의하고, 이러한 트리가 전체 개체 트리 개념과 어떻게 관련되는지를 설명하며, <xref:System.Windows.LogicalTreeHelper> 및 <xref:System.Windows.Media.VisualTreeHelper>를 소개합니다.  
  
   
  
<a name="element_tree"></a>   
## WPF의 트리  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 가장 완전한 트리 구조는 개체 트리입니다.  [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서 응용 프로그램 페이지를 정의한 후 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]을 로드하면 태그 내 요소의 중첩 관계를 기반으로 트리 구조가 만들어집니다.  코드에서 응용 프로그램이나 응용 프로그램의 일부를 정의하면 지정된 개체에 대한 콘텐츠 모델을 구현하는 속성에 대해 속성 값을 할당하는 방법을 기반으로 트리 구조가 만들어집니다.  [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에는 전체 개체 트리가 개념화되고 해당 공용 API에 보고될 수 있는 두 가지 방법이 있으며, 각각 논리적 트리와 시각적 트리입니다.  논리적 트리와 시각적 트리의 차이가 항상 중요한 것은 아니지만 특정 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 하위 시스템에서는 종종 문제를 일으킬 수 있으며 사용자가 태그나 코드에서 선택하는 항목에 영향을 줄 수 있습니다.  
  
 논리적 트리나 시각적 트리를 항상 직접 조작하지는 않더라도 트리가 상호 작용하는 방법의 개념을 이해하면 WPF를 기술로 이해하는 데 도움이 됩니다.  또한 WPF를 일종의 트리 비유로 간주하는 것은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 속성 상속 및 이벤트 라우팅의 작동 방식을 이해하는 데 중요합니다.  
  
> [!NOTE]
>  개체 트리는 실제 API가 아니라 개념에 가깝기 때문에 개념을 개체 그래프로 간주할 수도 있습니다.  실제로, 트리 비유가 분석되는 런타임에는 개체 간에 관계가 있습니다.  하지만 특히 XAML로 정의된 UI의 경우 이 일반 개념을 참조할 때 대부분의 WPF 설명서에서 개체 트리 용어를 사용할 만큼 트리 비유가 관련이 있습니다.  
  
<a name="logical_tree"></a>   
## 논리적 트리  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 이러한 요소를 지원하는 개체의 속성을 설정하여 UI 요소에 콘텐츠를 추가합니다.  예를 들어, <xref:System.Windows.Controls.ListBox> 컨트롤에 항목을 추가할 때는 해당 <xref:System.Windows.Controls.ItemsControl.Items%2A> 속성을 조작합니다.  이렇게 하면 <xref:System.Windows.Controls.ItemsControl.Items%2A> 속성 값인 <xref:System.Windows.Controls.ItemCollection>에 항목이 배치됩니다.  마찬가지로, <xref:System.Windows.Controls.DockPanel>에 개체를 추가하려면 해당 <xref:System.Windows.Controls.Panel.Children%2A> 속성 값을 조작합니다.  이때는 <xref:System.Windows.Controls.UIElementCollection>에 개체를 추가하게 됩니다.  코드 예제를 보려면 [Add an Element Dynamically](http://msdn.microsoft.com/ko-kr/d00f258a-7973-4de7-bc54-a3fc1f638419)를 참조하십시오.  
  
 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]에서 <xref:System.Windows.Controls.ListBox>의 목록 항목, 컨트롤 또는 다른 UI 요소를 <xref:System.Windows.Controls.DockPanel>에 배치할 때는 다음 예제와 같이 명시적 또는 암시적으로 <xref:System.Windows.Controls.ItemsControl.Items%2A> 및 <xref:System.Windows.Controls.Panel.Children%2A> 속성도 사용합니다.  
  
 [!code-xml[TreeOvwsSupport#AllCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeOvwsSupport/CS/page1.xaml#allcode)]  
  
 문서 개체 모델에서 이 XAML을 XML로 처리하려고 했으며, 적합했을 동작이지만 암시적으로 주석 처리된 태그를 포함했다면 결과로 생성된 XML DOM 트리에 `<ListBox.Items>` 및 다른 암시적 항목에 대한 요소가 포함되었을 것입니다.  그러나 XAML에서는 태그를 읽고 개체에 쓸 때 이런 방식으로 처리되지 않으며, 결과로 생성된 개체 그래프에 `ListBox.Items`가 포함되지 않습니다.  그러나 <xref:System.Windows.Controls.ItemCollection>이 포함된 `Items`라는 <xref:System.Windows.Controls.ListBox> 속성이 있으며, <xref:System.Windows.Controls.ListBox> XAML을 처리할 때는 이 <xref:System.Windows.Controls.ItemCollection>이 초기화되었지만 비어 있습니다.  그런 후에 <xref:System.Windows.Controls.ListBox>의 콘텐츠로 존재하는 각 자식 개체 요소가 `ItemCollection.Add`에 대한 파서 호출을 통해 <xref:System.Windows.Controls.ItemCollection>에 추가됩니다.  지금까지는 XAML을 개체 트리로 처리하는 이 예제가 기본적으로 논리적 트리인 개체 트리를 만드는 예제처럼 보입니다.  
  
 그러나 XAML 암시적 구문 항목을 제외하더라도 논리적 트리는 런타임에 응용 프로그램 UI에 대해 존재하는 전체 개체 그래프가 아닙니다.  이것은 주로 시각 효과와 템플릿 때문입니다.  예를 들어, <xref:System.Windows.Controls.Button>을 고려해 보겠습니다.  논리적 트리는 <xref:System.Windows.Controls.Button> 개체 및 이 개체의 문자열 `Content`를 보고합니다.  그러나 런타임 개체 트리에서는 이 단추에 그 밖의 특성이 있습니다.  특히, 특정 <xref:System.Windows.Controls.Button> 컨트롤 템플릿이 적용되었기 때문에 이 단추는 기본 모양으로만 화면에 나타납니다.  적용된 템플릿\(예: 시각적 단추 주위에 있는 진한 회색의 템플릿 정의 <xref:System.Windows.Controls.Border>\)에서 제공된 시각 효과는 표시되는 UI의 입력 이벤트를 처리한 후 논리적 트리를 읽는 경우처럼 런타임에 논리적 트리를 보는 경우에도 논리적 트리에 보고되지 않습니다.  템플릿 시각 효과를 찾으려면 대신 시각적 트리를 검사해야 합니다.  
  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 구문이 만들어진 개체 그래프에 매핑되는 방법 및 XAML의 암시적 구문에 대한 자세한 내용은 [XAML 구문 정보](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md) 또는 [XAML 개요\(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)를 참조하십시오.  
  
<a name="tree_property_inheritance_event_routing"></a>   
### 논리적 트리의 용도  
 논리적 트리는 콘텐츠 모델이 해당 자식 개체에서 쉽게 반복될 수 있도록 하고 콘텐츠 모델을 확장할 수 있도록 하는 역할을 합니다.  또한 논리적 트리는 논리적 트리의 모든 개체가 로드되었을 때와 같은 특정 알림을 위한 프레임워크를 제공합니다.  기본적으로 논리적 트리는 런타임 개체 그래프의 프레임워크 수준 근사값으로, 시각 효과를 제외하지만 고유한 런타임 응용 프로그램의 컴퍼지션에 대한 대부분의 쿼리 작업에 적합합니다.  
  
 또한 초기 요청 개체의 <xref:System.Windows.FrameworkElement.Resources%2A> 컬렉션에 대한 논리적 트리에서 위쪽을 살펴본 후 논리적 트리를 올라가면서 해당 키를 포함할 수 있는 <xref:System.Windows.ResourceDictionary>가 포함된 다른 `Resources` 값에 대해 각 <xref:System.Windows.FrameworkElement>\(또는 <xref:System.Windows.FrameworkContentElement>\)를 검사하여 정적 및 동적 리소스 참조를 모두 확인합니다.  논리적 트리와 시각적 트리가 모두 있는 경우 리소스 조회 시 논리적 트리가 사용됩니다.  리소스 사전 및 조회에 대한 자세한 내용은 [XAML 리소스](../../../../docs/framework/wpf/advanced/xaml-resources.md)를 참조하십시오.  
  
<a name="composition"></a>   
### 논리적 트리의 컴퍼지션  
 논리적 트리는 [WPF 프레임워크 수준](GTMT)에서 정의되므로 논리적 트리 작업에 가장 적합한 WPF 기본 요소는 <xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.FrameworkContentElement>입니다.  그러나 실제로 <xref:System.Windows.LogicalTreeHelper> API를 사용하는 경우 <xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.FrameworkContentElement>가 아닌 노드가 논리적 트리에 포함될 수도 있습니다.  예를 들어, 논리적 트리는 <xref:System.Windows.Controls.TextBlock>의 <xref:System.Windows.Controls.TextBlock.Text%2A> 값을 보고하며 이 값은 문자열입니다.  
  
<a name="override_logical_tree"></a>   
### 논리적 트리 재정의  
 고급 컨트롤 작성자는 일반 개체 또는 콘텐츠 모델이 논리적 트리 내에서 개체를 추가하거나 제거하는 방법을 정의하는 몇 가지 [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]를 재정의하여 논리적 트리를 재정의할 수 있습니다.  논리적 트리를 재정의하는 방법을 보여 주는 예제는 [논리 트리 재정의](../../../../docs/framework/wpf/advanced/how-to-override-the-logical-tree.md)를 참조하십시오.  
  
<a name="pvi"></a>   
### 속성 값 상속  
 속성 값 상속은 혼합 트리를 통해 작동합니다.  속성 상속을 가능하게 하는 <xref:System.Windows.FrameworkPropertyMetadata.Inherits%2A> 속성을 포함하는 실제 메타데이터는 [WPF 프레임워크 수준](GTMT) <xref:System.Windows.FrameworkPropertyMetadata> 클래스입니다.  따라서 원래 값을 보유하는 부모와 해당 값을 상속하는 자식 개체는 모두 <xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.FrameworkContentElement>여야 하고 논리적 트리의 일부여야 합니다.  하지만 속성 상속을 지원하는 기존 WPF 속성의 경우 속성 값 상속이 논리적 트리에 없는 중간 개체에도 적용될 수 있습니다.  이 기능은 주로 템플릿 요소가 템플릿을 기반으로 하는 인스턴스에 설정되었거나 페이지 수준 컴퍼지션의 상위 수준에 있어 논리적 트리에서도 상위 수준에 있는 상속된 속성 값을 사용하도록 하는 데 적합합니다.  이러한 경계에서 속성 값이 일관되게 상속되려면 상속 속성이 연결된 속성으로 등록되어 있어야 하며, 속성 상속 동작이 있는 사용자 지정 종속성 속성을 정의하려는 경우 이 패턴을 따라야 합니다.  속성 상속에 사용되는 트리가 어떤 것인지는 도우미 클래스 유틸리티 메서드가 정확하게 예상할 수 없으며 이는 런타임에도 마찬가지입니다.  자세한 내용은 [속성 값 상속](../../../../docs/framework/wpf/advanced/property-value-inheritance.md)을 참조하십시오.  
  
<a name="two_trees"></a>   
## 시각적 트리  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에는 논리적 트리라는 개념과 함께 [시각적 트리](GTMT)라는 개념도 사용됩니다.  시각적 트리는 <xref:System.Windows.Media.Visual> 기본 클래스가 나타내는 시각적 개체의 구조에 대해 설명합니다.  컨트롤의 템플릿을 작성할 때 컨트롤에 적용되는 시각적 트리를 정의하거나 다시 정의합니다.  시각적 트리는 성능 및 최적화를 위해 그리기에 하위 수준의 컨트롤을 사용하려는 개발자에게도 유용합니다.  시각적 트리가 기본 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램 프로그래밍의 일부로 노출되는 한 가지 예로 [라우트된 이벤트](GTMT)의 이벤트 경로가 대부분 논리적 트리가 아니라 시각적 트리를 따라 이동하는 것을 들 수 있습니다.  라우트된 이벤트의 이와 같은 미묘한 동작은 컨트롤 작성자가 아니면 쉽게 알지 못할 수 있습니다.  시각적 트리에서 이벤트를 라우팅하면 시각적 수준에서 컴퍼지션을 구현하는 컨트롤이 이벤트를 처리하거나 이벤트 setter를 만들 수 있습니다.  
  
<a name="trees_content"></a>   
## 트리, 콘텐츠 요소 및 콘텐츠 호스트  
 콘텐츠 요소\(<xref:System.Windows.ContentElement>에서 파생되는 클래스\)는 시각적 트리의 일부가 아닙니다. 콘텐츠 요소는 <xref:System.Windows.Media.Visual>에서 상속되지 않으므로 시각적 표현이 없습니다.  <xref:System.Windows.ContentElement>가 UI에 나타나려면 <xref:System.Windows.Media.Visual>이면서 동시에 논리적 트리 참가자인 콘텐츠 호스트에서 호스팅되어야 합니다.  대체로 이러한 개체는 <xref:System.Windows.FrameworkElement>입니다.  콘텐츠 호스트는 호스트가 제어하는 화면 영역 내에서 콘텐츠 표시 방법을 선택하는 콘텐츠용 "브라우저"라고 볼 수 있습니다.  콘텐츠가 호스팅되면 일반적으로 시각적 트리와 연결된 특정 트리 프로세스에 참가하도록 콘텐츠를 설정할 수 있습니다.  일반적으로 <xref:System.Windows.FrameworkElement> 호스트 클래스에는 호스팅된 콘텐츠가 실제 시각적 트리의 일부가 아닌 경우를 비롯하여 호스팅된 <xref:System.Windows.ContentElement>를 콘텐츠 논리적 트리의 하위 노드를 통해 이벤트 경로에 추가하는 구현 코드가 포함되어 있습니다.  이렇게 해야만 <xref:System.Windows.ContentElement>가 자신이 아닌 다른 요소로 이동하는 라우트된 이벤트를 발생시킬 수 있습니다.  
  
<a name="tree_traversal"></a>   
## 트리 이동  
 <xref:System.Windows.LogicalTreeHelper> 클래스는 논리적 트리 이동을 위해 <xref:System.Windows.LogicalTreeHelper.GetChildren%2A>, <xref:System.Windows.LogicalTreeHelper.GetParent%2A> 및 <xref:System.Windows.LogicalTreeHelper.FindLogicalNode%2A> 메서드를 제공합니다.  기존 컨트롤은 자신의 논리적 자식 요소를 항상 `Add`, 인덱서 등과 같이 컬렉션 액세스를 지원하는 전용 컬렉션 속성으로 노출하므로 대체로 기존 컨트롤의 논리적 트리를 이동할 필요는 없습니다.  트리 이동은 <xref:System.Windows.Controls.ItemsControl> 또는 <xref:System.Windows.Controls.Panel>과 같이 컬렉션 속성이 이미 정의된 컨트롤 패턴에서 파생하지 않고 자체적인 컬렉션 속성 지원을 제공하려는 컨트롤 작성자가 주로 사용하는 시나리오입니다.  
  
 시각적 트리도 시각적 트리 이동을 위해 <xref:System.Windows.Media.VisualTreeHelper>라는 도우미 클래스를 지원합니다.  시각적 트리는 컨트롤별 속성을 통해 노출되지 않습니다. 따라서 프로그래밍 시나리오에 필요하여 시각적 트리를 이동해야 하는 경우에는 <xref:System.Windows.Media.VisualTreeHelper> 클래스를 사용하는 것이 좋습니다.  자세한 내용은 [WPF 그래픽 렌더링 개요](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)를 참조하십시오.  
  
> [!NOTE]
>  적용된 템플릿의 시각적 트리를 검사해야 하는 경우도 있습니다.  이 방법을 사용할 때는 주의해야 합니다.  템플릿이 정의되는 컨트롤의 시각적 트리를 이동하는 경우에도 컨트롤 소비자는 언제든지 인스턴스의 <xref:System.Windows.Controls.Control.Template%2A> 속성을 설정하여 템플릿을 변경할 수 있으며, 최종 사용자도 시스템 테마를 변경하여 적용된 템플릿에 영향을 줄 수 있습니다.  
  
<a name="routes"></a>   
## 라우트된 이벤트의 경로\("트리"\)  
 앞에서 설명한 것처럼, 주어진 라우트된 이벤트의 경로는 시각 효과와 논리적 트리 표현이 혼합된 미리 결정된 단일 트리 경로를 따라 이동합니다.  이벤트 경로는 터널링 라우트된 이벤트인지 또는 버블링 라우트된 이벤트인지에 따라 트리에서 위쪽 또는 아래쪽 방향으로 이동할 수 있습니다.  이벤트 경로라는 개념에는 실제로 경로를 이동하는 이벤트의 발생과는 독립적으로 이벤트 경로를 "단계별로 이동"하는 데 사용할 수 있는 직접적인 지원 도우미 클래스가 없습니다.  경로를 나타내는 <xref:System.Windows.EventRoute>라는 클래스는 있지만 이 클래스의 메서드는 일반적으로 내부 전용입니다.  
  
<a name="resourcesandtrees"></a>   
## 리소스 사전 및 트리  
 페이지에 정의된 모든 `Resources`에 대한 리소스 사전 조회는 기본적으로 논리적 트리를 이동합니다.  논리적 트리에 없는 개체도 키 리소스를 참조할 수 있지만 해당 개체가 논리적 트리에 연결될 때 리소스 조회 시퀀스가 조회가 시작됩니다.  WPF에서는 논리적 트리 노드만 <xref:System.Windows.ResourceDictionary>가 포함된 `Resources` 속성을 가질 수 있으므로 <xref:System.Windows.ResourceDictionary>에서 키 리소스를 찾기 위해 시각적 트리를 이동하는 것은 아무런 의미가 없습니다.  
  
 하지만 리소스 조회의 범위를 직접적 논리적 트리를 넘어 확장할 수 있습니다.  응용 프로그램 태그의 경우 리소스 조회가 응용 프로그램 수준 리소스 사전 및 정적 속성이나 키로 참조된 시스템 값 및 테마 지원까지 위쪽으로 계속 진행할 수 있습니다.  리소스 참조가 동적인 경우 테마도 테마의 논리적 트리 외부에 있는 시스템 값을 참조할 수 있습니다.  리소스 사전 및 조회 논리에 대한 자세한 내용은 [XAML 리소스](../../../../docs/framework/wpf/advanced/xaml-resources.md)를 참조하십시오.  
  
## 참고 항목  
 [입력 개요](../../../../docs/framework/wpf/advanced/input-overview.md)   
 [WPF 그래픽 렌더링 개요](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)   
 [라우트된 이벤트 개요](../../../../docs/framework/wpf/advanced/routed-events-overview.md)   
 [개체 트리에 없는 개체 요소 초기화](../../../../docs/framework/wpf/advanced/initialization-for-object-elements-not-in-an-object-tree.md)   
 [WPF 아키텍처](../../../../docs/framework/wpf/advanced/wpf-architecture.md)