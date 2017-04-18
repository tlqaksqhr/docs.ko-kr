---
title: "방법: GridSplitter로 열 크기 조정 | Microsoft Docs"
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
  - "모눈 열, 크기 조정"
  - "GridSplitter 컨트롤, 모눈 열 크기 조정"
  - "모눈 열 크기 조정"
ms.assetid: 47b20fe6-7adc-4aa6-9693-b4e184eef74b
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: GridSplitter로 열 크기 조정
이 예제에서는 세로 <xref:System.Windows.Controls.GridSplitter>를 만들어 <xref:System.Windows.Controls.Grid>의 크기는 변경하지 않고 <xref:System.Windows.Controls.Grid>에 있는 두 열 사이의 공간을 다시 배분하는 방법을 보여 줍니다.  
  
## 예제  
 **열 가장자리를 겹쳐 표시하는 GridSplitter를 만드는 방법**  
  
 <xref:System.Windows.Controls.Grid>에서 인접 열의 크기를 조정하는 <xref:System.Windows.Controls.GridSplitter>를 지정하려면 크기를 조정할 열 중 하나로 <xref:System.Windows.Controls.Grid.Column%2A> [연결된 속성](GTMT)을 설정합니다.  <xref:System.Windows.Controls.Grid>에 행이 두 개 이상 있는 경우 <xref:System.Windows.Controls.Grid.RowSpan%2A> 연결된 속성을 해당 행 수로 설정합니다.  그런 다음 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 속성을 <xref:System.Windows.HorizontalAlignment> 또는 <xref:System.Windows.HorizontalAlignment>으로 설정합니다. 이 값은 크기를 조정할 두 개의 열에 따라 설정할 맞춤입니다.  마지막으로 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> 속성을 <xref:System.Windows.VerticalAlignment>로 설정합니다.  
  
 [!code-xml[GridSplitterRowColumn#GridSplitterColumnOverlay](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplittercolumnoverlay)]  
  
 자체 열이 없는 <xref:System.Windows.Controls.GridSplitter>의 경우 <xref:System.Windows.Controls.Grid>의 다른 컨트롤에 가려질 수도 있습니다.  이 문제를 방지하는 방법에 대한 자세한 내용은 [GridSplitter 표시](../../../../docs/framework/wpf/controls/how-to-make-sure-that-a-gridsplitter-is-visible.md)를 참조하십시오.  
  
 **열을 점유하는 GridSplitter를 만드는 방법**  
  
 <xref:System.Windows.Controls.Grid>의 열을 점유하는 <xref:System.Windows.Controls.GridSplitter>를 지정하려면 크기를 조정할 열 중 하나로 <xref:System.Windows.Controls.Grid.Column%2A> [연결된 속성](GTMT)을 설정합니다.  Grid에 행이 두 개 이상 있는 경우 <xref:System.Windows.Controls.Grid.RowSpan%2A> 연결된 속성을 해당 행 수로 설정합니다.  그런 다음 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>를 <xref:System.Windows.HorizontalAlignment>로 설정하고, <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> 속성을 <xref:System.Windows.VerticalAlignment>로 설정하고, <xref:System.Windows.Controls.GridSplitter>가 포함된 열의 <xref:System.Windows.Controls.ColumnDefinition.Width%2A>를 <xref:System.Windows.GridLength.Auto%2A>로 설정합니다.  
  
 다음 예제에서는 한 개의 열을 점유하고 양쪽에 있는 열의 크기를 조정하는 세로 <xref:System.Windows.Controls.GridSplitter>를 정의하는 방법을 보여 줍니다.  
  
 [!code-xml[GridSplitterRowColumn#GridSplitterEntireColumnPart1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirecolumnpart1)]  
[!code-xml[GridSplitterRowColumn#GridSplitterEntireColumnPart2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirecolumnpart2)]  
  
## 참고 항목  
 <xref:System.Windows.Controls.GridSplitter>   
 [방법 항목](../../../../docs/framework/wpf/controls/gridsplitter-how-to-topics.md)