---
title: "방법: 사용자 지정 패널 요소 만들기 | Microsoft Docs"
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
  - "사용자 지정 Panel 요소"
  - "Panel 컨트롤"
ms.assetid: e0df4f1e-8c07-4e86-89a3-e22acfffdc2a
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: 사용자 지정 패널 요소 만들기
## 예제  
 이 예제에서는 <xref:System.Windows.Controls.Panel> 요소의 기본 레이아웃 동작을 재정의하고 <xref:System.Windows.Controls.Panel>에서 파생된 사용자 지정 레이아웃 요소를 만드는 방법을 보여 줍니다.  
  
 예제에서는 두 개의 하드 코드된 x 및 y 좌표에 따라 자식 요소를 배치하는 `PlotPanel`이라는 간단한 사용자 지정 <xref:System.Windows.Controls.Panel> 요소를 정의합니다.  이 예제에서 `x` 및 `y`는 모두 `50`으로 설정되므로 모든 자식 요소는 x 및 y 축에서 해당 위치에 배치됩니다.  
  
 사용자 지정 <xref:System.Windows.Controls.Panel> 동작을 구현하기 위해 예제에서는 <xref:System.Windows.FrameworkElement.MeasureOverride%2A> 및 <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> 메서드를 사용합니다.  각 메서드는 자식 요소를 배치하고 렌더링하는 데 필요한 <xref:System.Windows.Size> 데이터를 반환합니다.  
  
 [!code-cpp[PlotPanel#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PlotPanel/CPP/PlotPanel.cpp#1)]
 [!code-csharp[PlotPanel#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PlotPanel/CSharp/PlotPanel.cs#1)]
 [!code-vb[PlotPanel#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PlotPanel/VisualBasic/PlotPanel.vb#1)]  
  
## 참고 항목  
 <xref:System.Windows.Controls.Panel>   
 [Panel 개요](../../../../docs/framework/wpf/controls/panels-overview.md)   
 [Create a Custom Content\-Wrapping Panel 샘플](http://go.microsoft.com/fwlink/?LinkID=159979)