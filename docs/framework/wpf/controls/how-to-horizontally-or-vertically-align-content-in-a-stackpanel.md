---
title: "방법: StackPanel에서 콘텐츠 가로 또는 세로 맞춤 | Microsoft Docs"
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
  - "맞추기, 내용"
  - "콘텐츠 맞춤"
  - "StackPanel 컨트롤, 콘텐츠 맞춤"
ms.assetid: c1e8f962-72c8-4e7a-8670-7a2d7e021791
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: StackPanel에서 콘텐츠 가로 또는 세로 맞춤
이 예제에서는 <xref:System.Windows.Controls.StackPanel> 요소 내 콘텐츠의 <xref:System.Windows.Controls.StackPanel.Orientation%2A>을 조정하는 방법과 자식 콘텐츠의 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 및 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>를 조정하는 방법을 보여 줍니다.  
  
## 예제  
 다음 예제에서는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]에 세 개의 <xref:System.Windows.Controls.ListBox> 요소를 만듭니다.  각 <xref:System.Windows.Controls.ListBox>는 <xref:System.Windows.Controls.StackPanel>의 <xref:System.Windows.Controls.StackPanel.Orientation%2A>, <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 및 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> 속성에 사용 가능한 값을 나타냅니다.  사용자가 <xref:System.Windows.Controls.ListBox> 요소의 값을 선택하면 <xref:System.Windows.Controls.StackPanel> 및 자식 <xref:System.Windows.Controls.Button> 요소의 연결된 속성이 변경됩니다.  
  
 [!code-xml[StackPanelIntroSamp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StackPanelIntroSamp/CSharp/Window1.xaml#1)]  
  
 다음 코드 숨김 파일은 <xref:System.Windows.Controls.ListBox> 선택 변경 사항과 연결된 이벤트에 대한 변경 사항을 정의합니다.  <xref:System.Windows.Controls.StackPanel>은 <xref:System.Windows.FrameworkElement.Name%2A> `sp1`로 식별됩니다.  
  
 [!code-csharp[StackPanelIntroSamp#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StackPanelIntroSamp/CSharp/Window1.xaml.cs#2)]
 [!code-vb[StackPanelIntroSamp#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelIntroSamp/VisualBasic/Window1.xaml.vb#2)]  
  
## 참고 항목  
 <xref:System.Windows.Controls.StackPanel>   
 <xref:System.Windows.Controls.ListBox>   
 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>   
 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>   
 [Panel 개요](../../../../docs/framework/wpf/controls/panels-overview.md)