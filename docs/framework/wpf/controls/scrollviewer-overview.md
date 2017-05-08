---
title: "ScrollViewer 개요 | Microsoft Docs"
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
  - "컨트롤, ScrollViewer"
  - "ScrollViewer 컨트롤, ScrollViewer 컨트롤 정보"
ms.assetid: 94a13b94-cfdf-4b12-a1aa-90cb50c6e9b9
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# ScrollViewer 개요
사용자 인터페이스 내부의 콘텐츠가 컴퓨터 화면의 표시 영역보다 큰 경우가 종종 있습니다.  <xref:System.Windows.Controls.ScrollViewer> 컨트롤은 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 응용 프로그램에서 콘텐츠를 스크롤할 수 있는 편리한 방법을 제공합니다.  이 항목에서는 <xref:System.Windows.Controls.ScrollViewer> 요소를 소개하고 몇 가지 사용 예제를 제공합니다.  
  
 이 항목에는 다음과 같은 단원이 포함되어 있습니다.  
  
<a name="autoTopLevelSectionsOUTLINE0"></a>   
-   [ScrollViewer 컨트롤](#what_is_a_scrollviewer_element)  
  
-   [물리적 스크롤 및논리적 스크롤 비교](#scrollviewer_physical_vs_logical)  
  
-   [ScrollViewer 요소 정의 및 사용](#scrollviewer_markup_syntax_and_sample)  
  
-   [ScrollViewer 스타일 설정](#scrollviewer_styling_scrollviewer)  
  
-   [문서 페이지 매김](#scrollviewer_scroll_vs_paginate)  
  
-   [Related Topics](#seeAlsoToggle)  
  
<a name="what_is_a_scrollviewer_element"></a>   
## ScrollViewer 컨트롤  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램에서 스크롤을 활성화하는 미리 정의된 두 가지 요소는 <xref:System.Windows.Controls.Primitives.ScrollBar>와 <xref:System.Windows.Controls.ScrollViewer>입니다.  <xref:System.Windows.Controls.ScrollViewer> 컨트롤은 스크롤 가능한 영역에 다른 표시 가능한 요소를 표시하도록 가로 및 세로 <xref:System.Windows.Controls.Primitives.ScrollBar> 요소와 콘텐츠 컨테이너\(예: <xref:System.Windows.Controls.Panel> 요소\)를 캡슐화합니다.  콘텐츠 스크롤에 <xref:System.Windows.Controls.Primitives.ScrollBar> 요소를 사용하려면 사용자 지정 개체를 빌드해야 하지만,  <xref:System.Windows.Controls.ScrollViewer> 요소는 <xref:System.Windows.Controls.Primitives.ScrollBar> 기능을 캡슐화한 복합 컨트롤이기 때문에 그대로 사용할 수 있습니다.  
  
 <xref:System.Windows.Controls.ScrollViewer> 컨트롤은 마우스 명령과 키보드 명령에 모두 응답하며 미리 정의된 증분만큼 콘텐츠를 스크롤하는 다양한 메서드를 정의합니다.  <xref:System.Windows.Controls.ScrollViewer.ScrollChanged> 이벤트를 사용하면 <xref:System.Windows.Controls.ScrollViewer> 상태 변화를 확인할 수 있습니다.  
  
 <xref:System.Windows.Controls.ScrollViewer>는 하나의 자식 요소만 가질 수 있으며, 대개 이 자식 요소는 요소의 <xref:System.Windows.Controls.Panel.Children%2A> 컬렉션을 호스팅할 수 있는 <xref:System.Windows.Controls.Panel> 요소입니다.  <xref:System.Windows.Controls.ContentPresenter.Content%2A> 속성은 <xref:System.Windows.Controls.ScrollViewer>의 단독 자식 요소를 정의합니다.  
  
<a name="scrollviewer_physical_vs_logical"></a>   
## 물리적 스크롤 및논리적 스크롤 비교  
 물리적 스크롤은 미리 정의된 물리적 증분\(일반적으로 픽셀 단위로 선언된 값\)만큼 콘텐츠를 스크롤하는 데 사용됩니다.  논리적 스크롤은 논리 트리에서 다음 항목으로 스크롤하는 데 사용됩니다.  대부분의 <xref:System.Windows.Controls.Panel> 요소에서는 물리적 스크롤이 기본 스크롤 동작입니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 두 스크롤 형식을 모두 지원합니다.  
  
#### IScrollInfo 인터페이스  
 <xref:System.Windows.Controls.Primitives.IScrollInfo> 인터페이스는 <xref:System.Windows.Controls.ScrollViewer> 또는 파생 컨트롤 내에서 기본 스크롤 영역을 표현합니다.  이 인터페이스는 <xref:System.Windows.Controls.Panel> 요소로 구현할 수 있으며, 물리적 증분이 아니라 논리적 단위로 스크롤해야 하는 스크롤 속성과 메서드를 정의합니다.  <xref:System.Windows.Controls.Primitives.IScrollInfo>의 인스턴스를 파생된 <xref:System.Windows.Controls.Panel>로 캐스팅한 후 해당 스크롤 메서드를 사용하면 자식 컬렉션에서 픽셀 증분이 아닌 다음 논리 단위로 쉽게 스크롤할 수 있습니다.  기본적으로 <xref:System.Windows.Controls.ScrollViewer> 컨트롤은 물리적 단위의 스크롤을 지원합니다.  
  
 <xref:System.Windows.Controls.StackPanel> 및 <xref:System.Windows.Controls.VirtualizingStackPanel>은 모두 <xref:System.Windows.Controls.Primitives.IScrollInfo>를 구현하며 논리적 스크롤을 기본적으로 지원합니다.  논리적 스크롤을 기본적으로 지원하는 레이아웃 컨트롤의 경우에도 <xref:System.Windows.Controls.ScrollViewer>에 호스트 <xref:System.Windows.Controls.Panel> 요소를 래핑하고 <xref:System.Windows.Controls.ScrollViewer.CanContentScroll%2A> 속성을 `false`로 설정하면 물리적 스크롤을 사용할 수 있습니다.  
  
 다음 코드 예제에서는 <xref:System.Windows.Controls.Primitives.IScrollInfo> 인스턴스를 <xref:System.Windows.Controls.StackPanel>로 캐스팅한 후 인터페이스에 정의되어 있는 콘텐츠 스크롤 메서드\(<xref:System.Windows.Controls.Primitives.IScrollInfo.LineUp%2A> 및 <xref:System.Windows.Controls.Primitives.IScrollInfo.LineDown%2A>\)를 사용하는 방법을 보여 줍니다.  
  
 [!code-csharp[IScrollInfoMethods#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml.cs#3)]
 [!code-vb[IScrollInfoMethods#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/IScrollInfoMethods/VisualBasic/Window1.xaml.vb#3)]  
  
<a name="scrollviewer_markup_syntax_and_sample"></a>   
## ScrollViewer 요소 정의 및 사용  
 다음 예제에서는 텍스트와 사각형이 포함된 창에 <xref:System.Windows.Controls.ScrollViewer>를 만듭니다.  <xref:System.Windows.Controls.Primitives.ScrollBar> 요소는 필요한 경우에만 나타납니다.  창 크기를 조정하면 <xref:System.Windows.Controls.ScrollViewer.ComputedHorizontalScrollBarVisibility%2A> 및 <xref:System.Windows.Controls.ScrollViewer.ComputedVerticalScrollBarVisibility%2A> 속성 값이 업데이트되어 <xref:System.Windows.Controls.Primitives.ScrollBar> 요소가 나타나거나 사라집니다.  
  
 [!code-cpp[ScrollViewer#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/ScrollViewer/CPP/ScrollViewer_wcp.cpp#1)]
 [!code-csharp[ScrollViewer#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewer/CSharp/ScrollViewer_wcp.cs#1)]
 [!code-vb[ScrollViewer#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ScrollViewer/VisualBasic/ScrollViewer.vb#1)]
 [!code-xml[ScrollViewer#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/ScrollViewer/XAML/Pane1.xaml#1)]  
  
<a name="scrollviewer_styling_scrollviewer"></a>   
## ScrollViewer 스타일 설정  
 Windows Presentation Foundation의 다른 모든 컨트롤과 마찬가지로 <xref:System.Windows.Controls.ScrollViewer>에 스타일을 설정하여 컨트롤의 기본 렌더링 동작을 변경할 수 있습니다.  컨트롤 스타일 설정에 대한 자세한 내용은 [스타일 지정 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)을 참조하십시오.  
  
<a name="scrollviewer_scroll_vs_paginate"></a>   
## 문서 페이지 매김  
 문서 콘텐츠의 경우 스크롤 대신 페이지 매김을 지원하는 문서 컨테이너를 선택할 수 있습니다.  <xref:System.Windows.Documents.FlowDocument>는 <xref:System.Windows.Controls.FlowDocumentPageViewer>와 같이 스크롤이 필요 없도록 콘텐츠를 여러 페이지로 분할하는 기능을 지원하는 뷰 컨트롤 내부에서 호스팅되도록 디자인된 문서에 사용합니다.  <xref:System.Windows.Controls.DocumentViewer>는 일반적인 스크롤을 사용하여 표시 영역 외부에 있는 콘텐츠를 표시하는 <xref:System.Windows.Documents.FixedDocument> 콘텐츠 보기 방법을 제공합니다.  
  
 문서 형식 및 프레젠테이션 옵션에 대한 자세한 내용은 [WPF의 문서](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)를 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Controls.ScrollViewer>   
 <xref:System.Windows.Controls.Primitives.ScrollBar>   
 <xref:System.Windows.Controls.Primitives.IScrollInfo>   
 [Create a Scroll Viewer](http://msdn.microsoft.com/ko-kr/c8e46af7-b417-441b-aa30-791cbdbd43ef)   
 [WPF의 문서](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)   
 [ScrollBar 스타일 및 템플릿](../../../../docs/framework/wpf/controls/scrollbar-styles-and-templates.md)   
 [컨트롤](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)