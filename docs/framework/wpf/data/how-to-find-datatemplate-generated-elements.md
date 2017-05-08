---
title: "방법: DataTemplate에서 생성된 요소 찾기 | Microsoft Docs"
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
  - "DataTemplate"
  - "DataTemplate 요소 찾기"
ms.assetid: bfcd564e-5e9e-451e-8641-a9b5c3cfac90
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# 방법: DataTemplate에서 생성된 요소 찾기
이 예제에서는 <xref:System.Windows.DataTemplate>에 의해 생성된 요소를 찾는 방법을 보여 줍니다.  
  
## 예제  
 이 예제에는 일부 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 데이터에 바인딩된 <xref:System.Windows.Controls.ListBox>가 있습니다.  
  
 [!code-xml[FindGeneratedItems#LB](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#lb)]  
  
 <xref:System.Windows.Controls.ListBox>는 다음 <xref:System.Windows.DataTemplate>을 사용합니다.  
  
 [!code-xml[FindGeneratedItems#DT](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#dt)]  
  
 특정 <xref:System.Windows.Controls.ListBoxItem>의 <xref:System.Windows.DataTemplate>에 의해 생성된 <xref:System.Windows.Controls.TextBlock> 요소를 검색하려는 경우 <xref:System.Windows.Controls.ListBoxItem>을 가져오고, 해당 <xref:System.Windows.Controls.ListBoxItem> 내에서 <xref:System.Windows.Controls.ContentPresenter>를 찾은 다음 해당 <xref:System.Windows.Controls.ContentPresenter>에 설정되어 있는 <xref:System.Windows.DataTemplate>에서 <xref:System.Windows.FrameworkTemplate.FindName%2A>을 호출해야 합니다.  다음 예제에서는 이러한 단계를 수행하는 방법을 보여 줍니다.  데모용으로 이 예제에서는 <xref:System.Windows.DataTemplate> 생성 텍스트 블록의 텍스트 콘텐츠를 보여 주는 메시지 상자를 만듭니다.  
  
 [!code-csharp[FindGeneratedItems#DTFindElement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#dtfindelement)]
 [!code-vb[FindGeneratedItems#DTFindElement](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#dtfindelement)]  
  
 다음은 <xref:System.Windows.Media.VisualTreeHelper> 메서드를 사용하는 `FindVisualChild`를 구현한 것입니다.  
  
 [!code-csharp[FindGeneratedItems#FVC](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#fvc)]
 [!code-vb[FindGeneratedItems#FVC](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#fvc)]  
  
## 참고 항목  
 [방법: ControlTemplate에서 생성된 요소 찾기](../../../../docs/framework/wpf/controls/how-to-find-controltemplate-generated-elements.md)   
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [방법 항목](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)   
 [스타일 지정 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [WPF XAML 이름 범위](../../../../docs/framework/wpf/advanced/wpf-xaml-namescopes.md)   
 [WPF의 트리](../../../../docs/framework/wpf/advanced/trees-in-wpf.md)