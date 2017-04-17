---
title: "방법: Dock 값 가져오기 또는 설정 | Microsoft Docs"
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
  - "Dock 값, 가져오기"
  - "Dock 값, 설정"
ms.assetid: fcf4ab8a-c7cd-4835-8d04-de1c999ab4a8
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# 방법: Dock 값 가져오기 또는 설정
다음 예제에서는 개체에 대한 <xref:System.Windows.Controls.Dock> 값을 할당하는 방법을 보여 줍니다.  예제에서는 <xref:System.Windows.Controls.DockPanel>의 <xref:System.Windows.Controls.DockPanel.GetDock%2A> 및 <xref:System.Windows.Controls.DockPanel.SetDock%2A> 메서드를 사용합니다.  
  
## 예제  
 예제에서는 <xref:System.Windows.Controls.TextBlock> 요소의 인스턴스 `txt1`을 만들고 <xref:System.Windows.Controls.DockPanel>의 <xref:System.Windows.Controls.DockPanel.SetDock%2A> 메서드를 사용하여 <xref:System.Windows.Controls.Dock> 값으로 `Top`을 할당합니다.  그런 다음 <xref:System.Windows.Controls.DockPanel.GetDock%2A> 메서드를 사용하여 <xref:System.Windows.Controls.TextBlock> 요소의 <xref:System.Windows.Controls.TextBlock.Text%2A>에 <xref:System.Windows.Controls.Dock> 속성의 값을 추가합니다.  마지막으로 부모 <xref:System.Windows.Controls.DockPanel>인 `dp1`에 <xref:System.Windows.Controls.TextBlock> 요소를 추가합니다.  
  
 [!code-csharp[DockPanelSetDock#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DockPanelSetDock/CSharp/DockPanel_SetDock.cs#1)]
 [!code-vb[DockPanelSetDock#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelSetDock/VisualBasic/DockPanel_SetDock.vb#1)]  
  
## 참고 항목  
 <xref:System.Windows.Controls.DockPanel>   
 <xref:System.Windows.Controls.DockPanel.GetDock%2A>   
 <xref:System.Windows.Controls.DockPanel.SetDock%2A>   
 [Panel 개요](../../../../docs/framework/wpf/controls/panels-overview.md)