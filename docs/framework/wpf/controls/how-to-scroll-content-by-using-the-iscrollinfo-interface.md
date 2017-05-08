---
title: "방법: IScrollInfo 인터페이스를 사용하여 콘텐츠 스크롤 | Microsoft Docs"
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
  - "콘텐츠 스크롤"
  - "ScrollViewer 컨트롤, 콘텐츠 스크롤"
ms.assetid: d8700bef-a3f8-4c12-9de2-fc3b79f32cd3
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# 방법: IScrollInfo 인터페이스를 사용하여 콘텐츠 스크롤
이 예제에서는 <xref:System.Windows.Controls.Primitives.IScrollInfo> 인터페이스를 사용하여 콘텐츠를 스크롤하는 방법을 보여 줍니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Controls.Primitives.IScrollInfo> 인터페이스의 기능을 보여 줍니다.  이 예제에서는 부모 <xref:System.Windows.Controls.ScrollViewer>에 중첩된 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]에 <xref:System.Windows.Controls.StackPanel> 요소를 생성합니다.  <xref:System.Windows.Controls.StackPanel>의 자식 요소는 <xref:System.Windows.Controls.Primitives.IScrollInfo> 인터페이스로 정의된 메서드를 사용하여 논리적으로 스크롤할 수 있으며 코드에서 <xref:System.Windows.Controls.StackPanel>\(`sp1`\)의 인스턴스로 캐스팅됩니다.  
  
 [!code-xml[IScrollInfoMethods#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml#2)]  
  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일의 각 <xref:System.Windows.Controls.Button>은 <xref:System.Windows.Controls.StackPanel>의 스크롤 동작을 제어하는 연결된 사용자 지정 메서드를 트리거합니다.  다음 예제에서는 <xref:System.Windows.Controls.Primitives.IScrollInfo.LineUp%2A> 및 <xref:System.Windows.Controls.Primitives.IScrollInfo.LineDown%2A> 메서드를 사용하는 방법을 보여 줍니다. 또한 일반적으로 <xref:System.Windows.Controls.Primitives.IScrollInfo> 클래스가 정의하는 모든 위치 지정 메서드를 사용하는 방법을 보여 줍니다.  
  
 [!code-csharp[IScrollInfoMethods#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml.cs#3)]
 [!code-vb[IScrollInfoMethods#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/IScrollInfoMethods/VisualBasic/Window1.xaml.vb#3)]  
  
## 참고 항목  
 <xref:System.Windows.Controls.ScrollViewer>   
 <xref:System.Windows.Controls.Primitives.IScrollInfo>   
 <xref:System.Windows.Controls.StackPanel>   
 [ScrollViewer 개요](../../../../docs/framework/wpf/controls/scrollviewer-overview.md)   
 [방법 항목](../../../../docs/framework/wpf/controls/scrollviewer-how-to-topics.md)   
 [Panel 개요](../../../../docs/framework/wpf/controls/panels-overview.md)