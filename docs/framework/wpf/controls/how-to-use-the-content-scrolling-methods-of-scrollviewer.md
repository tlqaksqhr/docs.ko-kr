---
title: "방법: ScrollViewer의 콘텐츠 스크롤 메서드 사용 | Microsoft Docs"
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
  - "IScrollInfo 인터페이스"
  - "스크롤 메서드"
  - "ScrollViewer 컨트롤, 스크롤 메서드"
ms.assetid: 4708cc65-6510-45f8-82e6-30b0d3e30045
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 방법: ScrollViewer의 콘텐츠 스크롤 메서드 사용
이 예제에서는 <xref:System.Windows.Controls.ScrollViewer> 요소의 스크롤 메서드를 사용하는 방법을 보여 줍니다.  이러한 메서드는 <xref:System.Windows.Controls.ScrollViewer>에서 콘텐츠를 줄 또는 페이지 단위로 스크롤하는 방법을 제공합니다.  
  
## 예제  
 다음 예제에서는 자식 <xref:System.Windows.Controls.TextBlock> 요소를 호스팅하는 `sv1`이라는 <xref:System.Windows.Controls.ScrollViewer>를 만듭니다.  <xref:System.Windows.Controls.TextBlock>이 부모 <xref:System.Windows.Controls.ScrollViewer>보다 크므로 스크롤할 수 있도록 스크롤 막대가 나타납니다.  다양한 스크롤 메서드를 나타내는 <xref:System.Windows.Controls.Button> 요소가 왼쪽에 있는 별도의 <xref:System.Windows.Controls.StackPanel>에 도킹되어 있습니다.  [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일의 각 <xref:System.Windows.Controls.Button>은 <xref:System.Windows.Controls.ScrollViewer>의 스크롤 동작을 제어하는 관련 사용자 지정 메서드를 호출합니다.  
  
 [!code-xml[ScrollViewerMethods#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewerMethods/CSharp/Window1.xaml#1)]  
  
 다음 예제에서는 <xref:System.Windows.Controls.ScrollViewer.LineUp%2A> 및 <xref:System.Windows.Controls.ScrollViewer.LineDown%2A> 메서드를 사용합니다.  
  
 [!code-csharp[ScrollViewerMethods#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewerMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[ScrollViewerMethods#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ScrollViewerMethods/VisualBasic/Window1.xaml.vb#2)]  
  
## 참고 항목  
 <xref:System.Windows.Controls.ScrollViewer>   
 <xref:System.Windows.Controls.StackPanel>