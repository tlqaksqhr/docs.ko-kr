---
title: "방법: DockPanel 만들기 | Microsoft Docs"
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
  - "컨트롤, DockPanel"
  - "DockPanel 컨트롤, 만들기"
ms.assetid: 9194f663-e279-4f1a-86d7-125a57d05c6f
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: DockPanel 만들기
## 예제  
 다음 예제에서는 코드를 사용하여 <xref:System.Windows.Controls.DockPanel>의 인스턴스를 만들고 사용합니다.  이 예제에서는 다섯 개의 <xref:System.Windows.Shapes.Rectangle> 요소를 만든 다음 부모 <xref:System.Windows.Controls.DockPanel> 안에 배치\(도킹\)하여 공간을 분할하는 방법을 보여 줍니다.  기본 설정을 유지하면 마지막 사각형이 할당되지 않은 나머지 공간을 모두 채웁니다.  
  
 [!code-csharp[DockPanelCode#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DockPanelCode/CSharp/DockPanel_Code.cs#1)]
 [!code-vb[DockPanelCode#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelCode/VisualBasic/dockpanel_vb.vb#1)]  
  
## 참고 항목  
 <xref:System.Windows.Controls.DockPanel>   
 <xref:System.Windows.Controls.Dock>   
 [Panel 개요](../../../../docs/framework/wpf/controls/panels-overview.md)