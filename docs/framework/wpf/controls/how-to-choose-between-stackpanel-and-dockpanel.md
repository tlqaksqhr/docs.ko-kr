---
title: "방법: StackPanel과 DockPanel 중 선택 | Microsoft Docs"
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
  - "컨트롤[WPF], DockPanel"
  - "컨트롤[WPF], StackPanel"
  - "DockPanel 컨트롤, StackPanel 컨트롤 비교 대상"
  - "StackPanel 컨트롤, DockPanel 컨트롤 비교 대상"
ms.assetid: f9239086-451f-42e6-81f7-ef89ef349742
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: StackPanel과 DockPanel 중 선택
이 예제에서는 <xref:System.Windows.Controls.Panel>에 내용을 배치할 때 <xref:System.Windows.Controls.StackPanel>과 <xref:System.Windows.Controls.DockPanel> 중 어떤 것을 사용할지 선택하는 방법을 보여 줍니다.  
  
## 예제  
 <xref:System.Windows.Controls.DockPanel> 또는 <xref:System.Windows.Controls.StackPanel>을 사용하여 자식 요소를 배치할 수 있지만 경우에 따라 이 두 컨트롤의 결과가 다를 수 있습니다.  예를 들어 자식 요소를 배치하는 순서가 <xref:System.Windows.Controls.DockPanel>에서는 자식 요소의 크기에 영향을 주지만 <xref:System.Windows.Controls.StackPanel>에서는 그렇지 않을 수 있습니다.  <xref:System.Windows.Controls.StackPanel>은 <xref:System.Double>.<xref:System.Double.PositiveInfinity>에서 배치하는 방향으로 측정되지만, <xref:System.Windows.Controls.DockPanel>은 사용 가능한 크기만 측정하기 때문에 이러한 동작 차이가 발생합니다.  
  
 다음 예제에서는 <xref:System.Windows.Controls.DockPanel>과 <xref:System.Windows.Controls.StackPanel>의 이러한 주요 차이를 보여 줍니다.  
  
 [!code-cpp[StackPanelOvw4#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/StackPanelOvw4/CPP/StackPanel_Ovw_Sample4.cpp#1)]
 [!code-csharp[StackPanelOvw4#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StackPanelOvw4/CSharp/StackPanel_Ovw_Sample4.cs#1)]
 [!code-vb[StackPanelOvw4#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelOvw4/VisualBasic/StackPanelSamp.vb#1)]
 [!code-xml[StackPanelOvw4#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/StackPanelOvw4/XAML/default.xaml#1)]  
  
## 참고 항목  
 <xref:System.Windows.Controls.StackPanel>   
 <xref:System.Windows.Controls.DockPanel>   
 [Panel 개요](../../../../docs/framework/wpf/controls/panels-overview.md)