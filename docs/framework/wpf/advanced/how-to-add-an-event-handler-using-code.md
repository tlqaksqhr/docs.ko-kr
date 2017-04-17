---
title: "방법: 코드를 사용하여 이벤트 처리기 추가 | Microsoft Docs"
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
  - "이벤트 처리기, 추가"
  - "XAML, 이벤트 처리기 추가"
ms.assetid: 269c61e0-6bd9-4291-9bed-1c5ee66da486
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# 방법: 코드를 사용하여 이벤트 처리기 추가
이 예제에서는 코드를 사용하여 요소에 이벤트 처리기를 추가하는 방법을 보여 줍니다.  
  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 요소에 이벤트 처리기를 추가하려면 요소를 포함하는 태그 페이지를 먼저 로드한 후 코드를 사용하여 처리기를 추가해야 합니다.  또는, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]을 사용하여 요소를 선언하는 않고 코드만 사용하여 전체 응용 프로그램의 요소 트리를 작성하는 경우에는 특정 메서드를 호출하여 구성된 요소 트리에 이벤트 처리기를 추가할 수 있습니다.  
  
## 예제  
 다음 예제에서는 새 <xref:System.Windows.Controls.Button>을 원래 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에 정의되어 있는 기존 페이지에 추가합니다.  코드 숨김 파일은 이벤트 처리기 메서드를 구현한 후 해당 메서드를 <xref:System.Windows.Controls.Button>에 대한 새 이벤트 처리기로 추가합니다.  
  
 [!INCLUDE[TLA2#tla_cshrp](../../../../includes/tla2sharptla-cshrp-md.md)] 예제에서는 `+=` 연산자를 사용하여 이벤트에 처리기를 할당합니다.  이 연산자는 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 이벤트 처리 모델에서 처리기를 할당하는 데 사용되는 것과 동일한 연산자입니다.  [!INCLUDE[TLA#tla_visualb](../../../../includes/tlasharptla-visualb-md.md)]에서는 이벤트 처리기를 추가하는 방법으로 이 연산자를 사용할 수 없습니다.  대신 다음 방법 중 하나를 사용해야 합니다.  
  
-   <xref:System.Windows.UIElement.AddHandler%2A> 메서드를 `AddressOf` 연산자와 함께 사용하여 이벤트 처리기 구현을 참조합니다.  
  
-   이벤트 처리기 정의의 일부로 `Handles` 키워드를 사용합니다.  이 방법은 여기에서 보여 주지 않습니다. 대신 [Visual Basic 및 WPF 이벤트 처리](../../../../docs/framework/wpf/advanced/visual-basic-and-wpf-event-handling.md)를 참조하십시오.  
  
 [!code-xml[RoutedEventAddRemoveHandler#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[RoutedEventAddRemoveHandler#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventAddRemoveHandler#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventAddRemoveHandler/VisualBasic/default.xaml.vb#handler)]  
  
> [!NOTE]
>  처음에 구문 분석된 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 페이지에 이벤트 처리기를 추가하는 것이 훨씬 간단합니다.  이벤트 처리기를 추가하려는 개체 요소 내에 처리할 이벤트 이름과 일치하는 특성을 추가합니다.  그런 다음 해당 특성 값을 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 페이지의 코드 숨김 파일에 정의되어 있는 이벤트 처리기 메서드 이름으로 지정합니다.  자세한 내용은 [XAML 개요\(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md) 또는 [라우트된 이벤트 개요](../../../../docs/framework/wpf/advanced/routed-events-overview.md)를 참조하십시오.  
  
## 참고 항목  
 [라우트된 이벤트 개요](../../../../docs/framework/wpf/advanced/routed-events-overview.md)   
 [방법 항목](../../../../docs/framework/wpf/advanced/events-how-to-topics.md)