---
title: "방법: GridSplitter 표시 | Microsoft Docs"
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
  - "GridSplitter 컨트롤, 표시 여부 확인"
ms.assetid: 0a62a964-89c8-48f0-9023-5df721a8cf47
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# 방법: GridSplitter 표시
이 예제에서는 <xref:System.Windows.Controls.GridSplitter> 컨트롤이 <xref:System.Windows.Controls.Grid>의 다른 컨트롤에 의해 숨겨지지 않도록 하는 방법을 보여 줍니다.  
  
## 예제  
 <xref:System.Windows.Controls.Grid> 컨트롤의 <xref:System.Windows.Controls.Panel.Children%2A>은 태그 또는 코드에 정의된 순서대로 렌더링됩니다.  <xref:System.Windows.Controls.GridSplitter> 컨트롤은 <xref:System.Windows.Controls.Panel.Children%2A> 컬렉션의 마지막 요소로 정의되지 않거나 다른 컨트롤에 더 높은 <xref:System.Windows.Controls.Panel.ZIndexProperty>가 지정된 경우에는 다른 컨트롤에 의해 숨겨질 수 있습니다.  
  
 <xref:System.Windows.Controls.GridSplitter> 컨트롤이 숨겨지지 않도록 하려면 다음 중 하나를 수행합니다.  
  
-   <xref:System.Windows.Controls.GridSplitter> 컨트롤이 <xref:System.Windows.Controls.Grid>에 추가된 마지막 <xref:System.Windows.Controls.Panel.Children%2A>이 되도록 합니다.  다음 예제에서 <xref:System.Windows.Controls.GridSplitter>는 <xref:System.Windows.Controls.Grid>의 <xref:System.Windows.Controls.Panel.Children%2A> 컬렉션에서 마지막 요소입니다.  
  
 [!code-xml[GridSplitterSnips#GridSplitterLastChild](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplitterlastchild)]  
  
-   <xref:System.Windows.Controls.GridSplitter>의 <xref:System.Windows.Controls.Panel.ZIndexProperty>가 이 컨트롤을 숨길 수 있는 컨트롤보다 높도록 설정합니다.  다음 예제에서는 <xref:System.Windows.Controls.GridSplitter> 컨트롤에 <xref:System.Windows.Controls.Button> 컨트롤보다 높은 <xref:System.Windows.Controls.Panel.ZIndexProperty>를 지정합니다.  
  
 [!code-xml[GridSplitterSnips#GridSplitterZIndex](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplitterzindex)]  
  
-   <xref:System.Windows.Controls.GridSplitter>를 숨길 수 있는 컨트롤의 여백을 <xref:System.Windows.Controls.GridSplitter>가 노출될 수 있는 크기로 설정합니다.  다음 예제에서는 <xref:System.Windows.Controls.GridSplitter>에 겹쳐져 이를 숨길 수 있는 컨트롤의 여백을 설정합니다.  
  
 [!code-xml[GridSplitterSnips#GridSplitterMargin](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplittermargin)]  
  
## 참고 항목  
 <xref:System.Windows.Controls.GridSplitter>   
 [방법 항목](../../../../docs/framework/wpf/controls/gridsplitter-how-to-topics.md)