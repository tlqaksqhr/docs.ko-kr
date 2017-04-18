---
title: "방법: 캔버스 위치 지정 속성 가져오기 또는 설정 | Microsoft Docs"
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
  - "Canvas 컨트롤, 위치 지정 속성 설정"
ms.assetid: 1636b950-2b5a-4507-8a10-c5034cc58b1c
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# 방법: 캔버스 위치 지정 속성 가져오기 또는 설정
이 예제에서는 <xref:System.Windows.Controls.Canvas> 요소의 위치 지정 메서드를 사용하여 자식 콘텐츠의 위치를 지정하는 방법을 보여 줍니다.  이 예제에서는 <xref:System.Windows.Controls.ListBoxItem>의 콘텐츠를 사용하여 위치 지정 값을 나타내고 값을 위치 지정을 위한 필수 인수인 <xref:System.Double>의 인스턴스로 변환합니다.  그런 다음 값은 다시 문자열로 변환되고 <xref:System.Windows.Controls.Canvas.GetLeft%2A> 메서드를 통해 <xref:System.Windows.Controls.TextBlock> 요소에 텍스트로 표시됩니다.  
  
## 예제  
 다음 예제에서는 11개의 선택 가능한 <xref:System.Windows.Controls.ListBoxItem> 요소가 있는 <xref:System.Windows.Controls.ListBox> 요소를 만듭니다.  <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> 이벤트는 이후 코드 블록에서 정의되는 `ChangeLeft` 사용자 지정 메서드를 트리거합니다.  
  
 각 <xref:System.Windows.Controls.ListBoxItem>은 <xref:System.Windows.Controls.Canvas>의 <xref:System.Windows.Controls.Canvas.SetLeft%2A> 메서드가 사용하는 인수 중 하나인 <xref:System.Double> 값을 나타냅니다.  <xref:System.Windows.Controls.ListBoxItem>을 사용하여 <xref:System.Double>의 인스턴스를 나타내려면 먼저 <xref:System.Windows.Controls.ListBoxItem>을 올바른 데이터 형식으로 변환해야 합니다.  
  
 [!code-xml[CanvasPositioningProperties#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CanvasPositioningProperties/CSharp/Window1.xaml#1)]  
  
 사용자가 <xref:System.Windows.Controls.ListBox> 선택 항목을 변경하면 `ChangeLeft` 사용자 지정 메서드가 호출됩니다.  이 메서드는 <xref:System.Windows.Controls.ListBoxItem>을 <xref:System.Windows.LengthConverter> 개체에 전달하며 이 개체는 <xref:System.Windows.Controls.ListBoxItem>의 <xref:System.Windows.Controls.ContentControl.Content%2A>를 <xref:System.Double>의 인스턴스로 변환합니다. 이 값은 <xref:System.Windows.Controls.Control.ToString%2A> 메서드를 통해 이미 <xref:System.String>으로 변환되었다는 점을 유의하십시오.  그런 다음 이 값은 `text1` 개체의 위치를 변경하기 위해 다시 <xref:System.Windows.Controls.Canvas>의 <xref:System.Windows.Controls.Canvas.SetLeft%2A> 및 <xref:System.Windows.Controls.Canvas.GetLeft%2A> 메서드에 전달됩니다.  
  
 [!code-csharp[CanvasPositioningProperties#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CanvasPositioningProperties/CSharp/Window1.xaml.cs#2)]
 [!code-vb[CanvasPositioningProperties#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasPositioningProperties/VisualBasic/Window1.xaml.vb#2)]  
  
## 참고 항목  
 <xref:System.Windows.Controls.Canvas>   
 <xref:System.Windows.Controls.ListBoxItem>   
 <xref:System.Windows.LengthConverter>   
 [Panel 개요](../../../../docs/framework/wpf/controls/panels-overview.md)