---
title: "방법: 복잡한 모눈 만들기 | Microsoft Docs"
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
  - "일정, 만들기"
  - "Grid 컨트롤, 만들기, 복잡한 모눈"
  - "월별 달력, 만들기"
ms.assetid: 4ce3040a-a156-4364-9596-98ca1eca5550
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# 방법: 복잡한 모눈 만들기
이 예제에서는 <xref:System.Windows.Controls.Grid>를 사용하여 월별 달력과 같은 모습의 레이아웃을 만드는 방법을 보여 줍니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Controls.RowDefinition> 및 <xref:System.Windows.Controls.ColumnDefinition> 클래스를 사용하여 8개의 행과 8개의 열을 정의합니다.  이 예제에서는 <xref:System.Windows.Controls.Grid.ColumnSpan%2A?displayProperty=fullName> 및 <xref:System.Windows.Controls.Grid.RowSpan%2A?displayProperty=fullName> 연결된 속성을 <xref:System.Windows.Shapes.Rectangle> 요소와 함께 사용하여 다양한 열과 행의 배경을 채웁니다.  이 디자인은 <xref:System.Windows.Controls.Grid>의 각 셀에 두 개 이상의 요소가 존재할 수 있기 때문에 가능한데, 이러한 특징이 <xref:System.Windows.Controls.Grid>와 <xref:System.Windows.Documents.Table>의 가장 큰 차이점입니다.  
  
 다음 예제에서는 세로 그라데이션을 통해 열과 행에 <xref:System.Windows.Shapes.Shape.Fill%2A>을 적용하여 달력의 모양을 보기 좋게 하고 달력을 읽기 쉽게 합니다.  스타일이 지정된 <xref:System.Windows.Controls.TextBlock> 요소는 날짜와 요일을 나타냅니다.  <xref:System.Windows.Controls.TextBlock> 요소는 <xref:System.Windows.FrameworkElement.Margin%2A> 속성 및 해당 응용 프로그램의 스타일에 정의된 맞춤 속성을 사용하여 해당 셀 내의 절대 위치에 배치됩니다.  
  
 [!code-xml[GridComplex#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridComplex/CS/default.xaml#1)]  
  
## 참고 항목  
 <xref:System.Windows.Controls.Grid>   
 <xref:System.Windows.Documents.TableCell>   
 [단색 및 그라데이션을 사용한 그리기 개요](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)   
 [Panel 개요](../../../../docs/framework/wpf/controls/panels-overview.md)   
 [표 개요](../../../../docs/framework/wpf/advanced/table-overview.md)