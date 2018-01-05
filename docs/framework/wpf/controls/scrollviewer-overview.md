---
title: "ScrollViewer 개요"
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
- cpp
helpviewer_keywords:
- controls [WPF], ScrollViewer
- ScrollViewer control [WPF], about ScrollViewer control
ms.assetid: 94a13b94-cfdf-4b12-a1aa-90cb50c6e9b9
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0d060e0b511f17a68edb013ae7241e1accbc7dcf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="scrollviewer-overview"></a>ScrollViewer 개요
사용자 인터페이스 내의 콘텐츠는 대개 컴퓨터 화면의 표시 영역보다 더 큽니다. <xref:System.Windows.Controls.ScrollViewer> 컨트롤의 콘텐츠를 스크롤할 수 있게 하는 편리한 방법을 제공 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 응용 프로그램입니다. 이 항목에서는 소개는 <xref:System.Windows.Controls.ScrollViewer> 요소 몇 가지 사용 예제를 제공 합니다.  
  
<a name="what_is_a_scrollviewer_element"></a>   
## <a name="the-scrollviewer-control"></a>ScrollViewer 컨트롤  
 스크롤할 수 있게 하는 두 개의 미리 정의 된 요소 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램: <xref:System.Windows.Controls.Primitives.ScrollBar> 및 <xref:System.Windows.Controls.ScrollViewer>합니다. <xref:System.Windows.Controls.ScrollViewer> 컨트롤 캡슐화 가로 및 세로 <xref:System.Windows.Controls.Primitives.ScrollBar> 요소 및 콘텐츠 컨테이너 (같은 <xref:System.Windows.Controls.Panel> 요소) 스크롤 가능한 영역에 표시 가능한 다른 요소를 표시 하기 위해. 사용 하려면 사용자 지정 개체를 작성 해야는 <xref:System.Windows.Controls.Primitives.ScrollBar> 콘텐츠 스크롤에 대 한 요소입니다. 사용할 수 있습니다는 <xref:System.Windows.Controls.ScrollViewer> 자체적으로 요소는 복합 컨트롤 이기 때문에 캡슐화 <xref:System.Windows.Controls.Primitives.ScrollBar> 기능입니다.  
  
 <xref:System.Windows.Controls.ScrollViewer> 컨트롤 마우스와 키보드 둘 다 명령에 응답 하 고 증분만큼 내용을 스크롤할 수 있는 다양 한 메서드를 정의 합니다. 사용할 수는 <xref:System.Windows.Controls.ScrollViewer.ScrollChanged> 에 변경 내용을 검색 하려면 이벤트는 <xref:System.Windows.Controls.ScrollViewer> 상태입니다.  
  
 A <xref:System.Windows.Controls.ScrollViewer> 일반적으로 하나의 자식만 포함할 수 있습니다는 <xref:System.Windows.Controls.Panel> 호스팅할 수 있는 요소는 <xref:System.Windows.Controls.Panel.Children%2A> 요소의 컬렉션입니다. <xref:System.Windows.Controls.ContentPresenter.Content%2A> 속성 정의의 유일한 자식은 <xref:System.Windows.Controls.ScrollViewer>합니다.  
  
<a name="scrollviewer_physical_vs_logical"></a>   
## <a name="physical-vs-logical-scrolling"></a>실제 및 논리적 스크롤  
 실제 스크롤은 미리 결정된 실제 증분만큼(일반적으로 픽셀 단위로 선언된 값만큼) 콘텐츠를 스크롤하는 데 사용됩니다. 논리적 스크롤은 논리 트리에서 다음 항목으로 스크롤하는 데 사용됩니다. 물리적 스크롤 하는 것은 대부분에 대 한 기본 스크롤 동작 <xref:System.Windows.Controls.Panel> 요소입니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 두 가지 스크롤 형식을 모두 지원합니다.  
  
#### <a name="the-iscrollinfo-interface"></a>IScrollInfo 인터페이스  
 <xref:System.Windows.Controls.Primitives.IScrollInfo> 인터페이스 내에서 기본 스크롤 영역 나타냅니다는 <xref:System.Windows.Controls.ScrollViewer> 또는 파생 컨트롤입니다. 스크롤 속성 및에서 구현할 수 있는 메서드는 인터페이스 정의 <xref:System.Windows.Controls.Panel> 물리적 증가 하지 않고 논리 단위 여 스크롤해야 하는 요소입니다. 인스턴스로 캐스팅 <xref:System.Windows.Controls.Primitives.IScrollInfo> 파생에 <xref:System.Windows.Controls.Panel> 픽셀 증분이 아닌 자식 컬렉션의 다음 논리 단위에 스크롤 하는 유용한 방법은 제공 스크롤 해당 메서드를 사용 하 여 합니다. 기본적으로는 <xref:System.Windows.Controls.ScrollViewer> 컨트롤은 물리적 단위의 스크롤을 지원 합니다.  
  
 <xref:System.Windows.Controls.StackPanel>및 <xref:System.Windows.Controls.VirtualizingStackPanel> 둘 다 구현 <xref:System.Windows.Controls.Primitives.IScrollInfo> 및 고유 하 게 논리적 스크롤을 지원 합니다. 레이아웃 해당 고유 하 게 지원 논리적 스크롤 컨트롤을 얻을 수 있습니다 여전히 호스트를 배치 하 여 물리적 스크롤 <xref:System.Windows.Controls.Panel> 요소에는 <xref:System.Windows.Controls.ScrollViewer> 설정는 <xref:System.Windows.Controls.ScrollViewer.CanContentScroll%2A> 속성을 `false`합니다.  
  
 다음 코드 예제에서는의 인스턴스로 캐스팅 하는 방법을 보여 줍니다 <xref:System.Windows.Controls.Primitives.IScrollInfo> 에 <xref:System.Windows.Controls.StackPanel> 콘텐츠 스크롤 메서드를 사용 하 여 (<xref:System.Windows.Controls.Primitives.IScrollInfo.LineUp%2A> 및 <xref:System.Windows.Controls.Primitives.IScrollInfo.LineDown%2A>)는 인터페이스에서 정의 합니다.  
  
 [!code-csharp[IScrollInfoMethods#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml.cs#3)]
 [!code-vb[IScrollInfoMethods#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/IScrollInfoMethods/VisualBasic/Window1.xaml.vb#3)]  
  
<a name="scrollviewer_markup_syntax_and_sample"></a>   
## <a name="defining-and-using-a-scrollviewer-element"></a>ScrollViewer 요소 정의 및 사용  
 다음 예제에서는 한 <xref:System.Windows.Controls.ScrollViewer> 텍스트와 사각형을 포함 하는 창에 있습니다. <xref:System.Windows.Controls.Primitives.ScrollBar>요소에만 필요한 경우에 나타납니다. 창의 크기를 조정할 때의 <xref:System.Windows.Controls.Primitives.ScrollBar> 요소를 표시 하거나 숨길, 값이 업데이트 되어는 <xref:System.Windows.Controls.ScrollViewer.ComputedHorizontalScrollBarVisibility%2A> 및 <xref:System.Windows.Controls.ScrollViewer.ComputedVerticalScrollBarVisibility%2A> 속성입니다.  
  
 [!code-cpp[ScrollViewer#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/ScrollViewer/CPP/ScrollViewer_wcp.cpp#1)]
 [!code-csharp[ScrollViewer#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewer/CSharp/ScrollViewer_wcp.cs#1)]
 [!code-vb[ScrollViewer#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ScrollViewer/VisualBasic/ScrollViewer.vb#1)]
 [!code-xaml[ScrollViewer#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/ScrollViewer/XAML/Pane1.xaml#1)]  
  
<a name="scrollviewer_styling_scrollviewer"></a>   
## <a name="styling-a-scrollviewer"></a>ScrollViewer 스타일 지정  
 Windows Presentation Foundation의 모든 컨트롤과 같이 <xref:System.Windows.Controls.ScrollViewer> 컨트롤의 기본 렌더링 동작을 변경 하기 위해 스타일을 지정할 수 있습니다. 컨트롤 스타일 지정에 대한 자세한 내용은 [스타일 지정 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)을 참조하세요.  
  
<a name="scrollviewer_scroll_vs_paginate"></a>   
## <a name="paginating-documents"></a>문서 페이지 매김  
 문서 콘텐츠의 경우 스크롤 대신 페이지 매김을 지원하는 문서 컨테이너를 선택할 수 있습니다. <xref:System.Windows.Documents.FlowDocument>와 같은 보기 컨트롤 내에서 호스팅 되도록 디자인 된 문서에는 <xref:System.Windows.Controls.FlowDocumentPageViewer>, 스크롤할 필요성을 방지 하는 여러 페이지에 걸쳐 분할 콘텐츠를 지 원하는 합니다. <xref:System.Windows.Controls.DocumentViewer>보기에 대 한 솔루션을 제공 <xref:System.Windows.Documents.FixedDocument> 콘텐츠를 사용 하 여 일반적인 스크롤 표시 영역 외부에 콘텐츠를 표시 합니다.  
  
 문서 서식 및 프레젠테이션 옵션에 대한 자세한 내용은 [WPF의 문서](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Controls.ScrollViewer>  
 <xref:System.Windows.Controls.Primitives.ScrollBar>  
 <xref:System.Windows.Controls.Primitives.IScrollInfo>  
 [스크롤 뷰어 만들기](http://msdn.microsoft.com/en-us/c8e46af7-b417-441b-aa30-791cbdbd43ef)  
 [WPF의 문서](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [ScrollBar 스타일 및 템플릿](../../../../docs/framework/wpf/controls/scrollbar-styles-and-templates.md)  
 [컨트롤](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)
