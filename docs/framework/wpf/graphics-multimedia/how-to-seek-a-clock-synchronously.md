---
title: "방법: 동기적으로 시계 검색 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Clock, 동기적으로 검색"
  - "동기적으로 Clock 검색"
ms.assetid: e5b7529b-b7d0-40d2-9e1d-fa4b5e736e96
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# 방법: 동기적으로 시계 검색
<xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A> 메서드를 사용하면 특정 지점에 대해 동기적으로 시계를 검색할 수 있습니다.  다음 예제에서는 <xref:System.Windows.Media.Animation.ClockController>의 <xref:System.Windows.Media.Animation.ClockController.Seek%2A> 및 <xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A> 메서드를 보여 줍니다.  
  
 이 예제에서는 <xref:System.Windows.Media.Animation.Clock>을 검색하는 방법을 보여 줍니다. Storyboard 검색 방법을 보여 주는 예제는 [동기적으로 Storyboard 검색](../../../../docs/framework/wpf/graphics-multimedia/how-to-seek-a-storyboard-synchronously.md)을 참조하십시오.  
  
## 예제  
 [!code-csharp[ClockController_procedural_snip#ClockControllerSeekExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ClockController_procedural_snip/CSharp/SeekAlignedToLastTickExample.cs#clockcontrollerseekexample)]
 [!code-vb[ClockController_procedural_snip#ClockControllerSeekExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ClockController_procedural_snip/visualbasic/seekalignedtolasttickexample.vb#clockcontrollerseekexample)]