---
title: "방법: Thumb을 사용하여 캔버스 크기 조정 | Microsoft Docs"
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
  - "Canvas 컨트롤"
  - "컨트롤, Canvas"
  - "컨트롤, Thumb"
  - "Canvas 컨트롤 크기 조정"
  - "Thumb 컨트롤"
ms.assetid: 7dc9f435-726c-4d4d-be41-eb24cfe17bef
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# 방법: Thumb을 사용하여 캔버스 크기 조정
이 예제에서는 <xref:System.Windows.Controls.Primitives.Thumb> 컨트롤을 사용하여 <xref:System.Windows.Controls.Canvas> 컨트롤의 크기를 조정하는 방법을 보여 줍니다.  
  
## 예제  
 <xref:System.Windows.Controls.Primitives.Thumb> 컨트롤은 <xref:System.Windows.Controls.Primitives.Thumb>의 <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>, <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> 및 <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> 이벤트를 모니터링하여 컨트롤을 이동하거나 크기를 조정하는 데 사용할 수 있는 끌기 기능을 제공합니다.  
  
 끌기 작업은 먼저 <xref:System.Windows.Controls.Primitives.Thumb> 컨트롤에 마우스 포인터를 두고 마우스 왼쪽 단추를 눌러 시작합니다.  마우스 왼쪽 단추를 누르고 있는 동안에는 끌기 작업이 계속됩니다.  끌기 작업 중 <xref:System.Windows.Controls.Primitives.Thumb.DragDelta>가 두 번 이상 발생할 수 있습니다.  발생할 때마다 <xref:System.Windows.Controls.Primitives.DragDeltaEventArgs> 클래스가 마우스 위치 변경에 해당하는 위치 변경을 제공합니다.  마우스 왼쪽 단추를 놓으면 끌기 작업이 끝납니다.  끌기 작업은 새 좌표를 제공하기만 하고 자동으로 <xref:System.Windows.Controls.Primitives.Thumb>의 위치를 바꾸지는 않습니다.  
  
 다음 예제에서는 <xref:System.Windows.Controls.Canvas> 컨트롤의 자식 요소인 <xref:System.Windows.Controls.Primitives.Thumb> 컨트롤을 보여 줍니다.  해당 <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> 이벤트에 대한 이벤트 처리기가 <xref:System.Windows.Controls.Primitives.Thumb>을 이동하고 <xref:System.Windows.Controls.Canvas>의 크기를 조정하는 논리를 제공합니다.  <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> 및 <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> 이벤트의 이벤트 처리기가 끌기 작업 중 <xref:System.Windows.Controls.Primitives.Thumb>의 색을 변경합니다.  다음 예제에서는 <xref:System.Windows.Controls.Primitives.Thumb>을 정의합니다.  
  
 [!code-xml[Thumb#thumb](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml#thumb)]  
  
 다음 예제에서는 마우스 이동에 응답하여 <xref:System.Windows.Controls.Primitives.Thumb>을 이동하고 <xref:System.Windows.Controls.Canvas>의 크기를 조정하는 <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> 이벤트 처리기를 보여 줍니다.  
  
 [!code-csharp[Thumb#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#2)]  
  
 다음 예제에서는 <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> 이벤트 처리기를 보여 줍니다.  
  
 [!code-csharp[Thumb#DragStartedHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragstartedhandler)]
 [!code-vb[Thumb#DragStartedHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragstartedhandler)]  
  
 다음 예제에서는 <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> 이벤트 처리기를 보여 줍니다.  
  
 [!code-csharp[Thumb#DragCompletedHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragcompletedhandler)]
 [!code-vb[Thumb#DragCompletedHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragcompletedhandler)]  
  
 전체 샘플을 보려면 [Thumb Drag Functionality 샘플](http://go.microsoft.com/fwlink/?LinkID=160042)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Controls.Primitives.Thumb>   
 <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>   
 <xref:System.Windows.Controls.Primitives.Thumb.DragDelta>   
 <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted>