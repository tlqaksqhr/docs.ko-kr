---
title: "방법: Grid 요소 만들기 | Microsoft Docs"
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
  - "Grid 컨트롤, 만들기, 모눈 인스턴스"
ms.assetid: b2f07626-9df8-43b8-8d36-492f3cb42837
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# 방법: Grid 요소 만들기
## 예제  
 다음 예제에서는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 또는 코드를 사용하여 <xref:System.Windows.Controls.Grid> 인스턴스를 만들고 사용하는 방법을 보여 줍니다.  이 예제에서는 세 개의 <xref:System.Windows.Controls.ColumnDefinition> 개체와 세 개의 <xref:System.Windows.Controls.RowDefinition> 개체를 사용하여 워크시트 등에서 9개의 셀이 있는 표를 만듭니다.  각 셀에는 데이터를 나타내는 <xref:System.Windows.Controls.TextBlock> 요소가 있으며 맨 위 행에는 <xref:System.Windows.Controls.Grid.ColumnSpan%2A> 속성이 적용된 <xref:System.Windows.Controls.TextBlock>이 있습니다.  각 셀의 경계를 표시하기 위해 <xref:System.Windows.Controls.Grid.ShowGridLines%2A> 속성을 사용합니다.  
  
 [!code-csharp[Grid#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Grid/CSharp/Grid_Code.cs#3)]
 [!code-vb[Grid#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Grid/VisualBasic/grid_vb.vb#3)]
 [!code-xml[Grid#3](../../../../samples/snippets/xaml/VS_Snippets_Wpf/Grid/XAML/default.xaml#3)]  
  
## 참고 항목  
 <xref:System.Windows.Controls.Grid>   
 [Panel 개요](../../../../docs/framework/wpf/controls/panels-overview.md)