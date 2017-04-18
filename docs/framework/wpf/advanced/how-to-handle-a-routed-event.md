---
title: "방법: 라우트된 이벤트 처리 | Microsoft Docs"
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
  - "이벤트 버블링"
  - "라우트된 이벤트, 처리"
ms.assetid: 157787b4-f469-4047-8777-5b034145f32e
caps.latest.revision: 23
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 22
---
# 방법: 라우트된 이벤트 처리
이 예제에서는 [버블링](GTMT) 이벤트의 작동 방법 및 [라우트된 이벤트](GTMT) 데이터를 처리할 수 있는 처리기를 작성하는 방법을 보여 줍니다.  
  
## 예제  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서 요소는 [이벤트 트리](GTMT) 구조 내에 정렬됩니다.  부모 요소는 요소 트리의 자식 요소에 의해 처음 발생한 이벤트의 처리에 참가할 수 있습니다.  이것이 가능한 것은 [이벤트 라우팅](GTMT) 덕분입니다.  
  
 라우트된 이벤트는 일반적으로 [버블링](GTMT) 또는 [터널링](GTMT)이라는 두 라우팅 전략 중 하나를 따릅니다.  이 예제에서는 [버블링](GTMT) 이벤트를 중점적으로 다루며 <xref:System.Windows.Controls.Primitives.ButtonBase.Click?displayProperty=fullName> 이벤트를 사용하여 라우팅의 작동 원리를 보여 줍니다.  
  
 다음 예제에서는 두 개의 <xref:System.Windows.Controls.Button> 컨트롤을 만들고 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 특성 구문을 사용하여 공통 부모 요소인 <xref:System.Windows.Controls.StackPanel>에 이벤트 처리기를 연결합니다.  이 예제에서는 각 <xref:System.Windows.Controls.Button> 자식 요소에 대해 개별적으로 이벤트 처리기를 연결하는 대신 특성 구문을 사용하여 <xref:System.Windows.Controls.StackPanel> 부모 요소에 이벤트 처리기를 연결합니다.  이 이벤트 처리 패턴은 이벤트 라우팅을 통해 처리기가 연결되는 요소의 수를 줄이는 방법을 보여 줍니다.  각 <xref:System.Windows.Controls.Button>에 대한 모든 [버블링](GTMT) 이벤트는 부모 요소를 통해 라우팅합니다.  
  
 부모 <xref:System.Windows.Controls.StackPanel> 요소에서 특성으로 지정된 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트 이름은 <xref:System.Windows.Controls.Button> 클래스 이름을 지정하는 방식으로 부분적으로 정규화되어 있습니다.  <xref:System.Windows.Controls.Button> 클래스는 해당 멤버 목록에 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트가 포함된 <xref:System.Windows.Controls.Primitives.ButtonBase> 파생 클래스입니다.  이벤트 처리기 연결을 위한 이와 같은 부분 정규화 기법은 라우트된 이벤트 처리기가 연결된 요소의 멤버 목록에 처리할 이벤트가 없는 경우 필요합니다.  
  
 [!code-xml[RoutedEventHandle#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventHandle/CSharp/default.xaml#xaml)]  
  
 다음 예제에서는 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트를 처리합니다.  이 예제에서는 이벤트를 처리하는 요소와 이벤트를 발생시키는 요소를 보고합니다.  사용자가 단추를 클릭하면 이벤트 처리기가 실행됩니다.  
  
 [!code-csharp[RoutedEventHandle#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventHandle/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventHandle#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventHandle/VisualBasic/MainWindow.xaml.vb#handler)]  
  
## 참고 항목  
 <xref:System.Windows.RoutedEvent>   
 [입력 개요](../../../../docs/framework/wpf/advanced/input-overview.md)   
 [라우트된 이벤트 개요](../../../../docs/framework/wpf/advanced/routed-events-overview.md)   
 [방법 항목](../../../../docs/framework/wpf/advanced/events-how-to-topics.md)   
 [XAML 구문 정보](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md)