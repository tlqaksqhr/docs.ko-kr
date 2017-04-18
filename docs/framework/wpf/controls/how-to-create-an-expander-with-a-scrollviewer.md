---
title: "방법: ScrollViewer가 있는 Expander 만들기 | Microsoft Docs"
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
  - "컨트롤[WPF], Expander"
  - "컨트롤[WPF], ScrollViewer"
  - "Expander 컨트롤, 만들기"
  - "ScrollViewer 컨트롤, Expander 컨트롤"
ms.assetid: 2ad124d2-2406-4157-aaf2-64e067298f01
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# 방법: ScrollViewer가 있는 Expander 만들기
이 예제에서는 이미지 및 텍스트와 같은 복합 콘텐츠를 포함하는 <xref:System.Windows.Controls.Expander> 컨트롤을 만드는 방법을 보여 줍니다.  이 예제에서는 <xref:System.Windows.Controls.ScrollViewer> 컨트롤에 <xref:System.Windows.Controls.Expander>의 콘텐츠도 포함합니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Controls.Expander>를 만드는 방법을 보여 줍니다.  이 예제에서는 이미지 및 텍스트가 포함된 <xref:System.Windows.Controls.Primitives.BulletDecorator> 컨트롤을 사용하여 <xref:System.Windows.Controls.HeaderedContentControl.Header%2A>를 정의합니다.  <xref:System.Windows.Controls.ScrollViewer> 컨트롤은 확장된 콘텐츠를 스크롤하기 위한 메서드를 제공합니다.  
  
 이 예제에서는 콘텐츠가 아닌 <xref:System.Windows.Controls.ScrollViewer>에서 <xref:System.Windows.FrameworkElement.Height%2A> 속성을 설정합니다.  <xref:System.Windows.FrameworkElement.Height%2A>가 콘텐츠에 설정되어 있는 경우에는 사용자가 <xref:System.Windows.Controls.ScrollViewer>에서 콘텐츠를 스크롤할 수 없습니다.  <xref:System.Windows.FrameworkElement.Width%2A> 속성은 <xref:System.Windows.Controls.Expander> 컨트롤에 설정되며 이 설정은 <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> 및 확장된 콘텐츠에 적용됩니다.  
  
 [!code-xml[ExpanderRichContent#CreateExpander](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml#createexpander)]  
  
 [!code-csharp[ExpanderRichContent#CreateExpanderCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml.cs#createexpandercode)]  
  
## 참고 항목  
 <xref:System.Windows.Controls.Expander>   
 [Expander 개요](../../../../docs/framework/wpf/controls/expander-overview.md)   
 [방법 항목](../../../../docs/framework/wpf/controls/expander-how-to-topics.md)