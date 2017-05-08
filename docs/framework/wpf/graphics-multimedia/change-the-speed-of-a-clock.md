---
title: "방법: 해당 Timeline의 속도를 변경하지 않고 시계의 속도 변경 | Microsoft Docs"
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
  - "Clock, 속도 변경"
  - "Clock 속도, 변경"
ms.assetid: 72f36dd0-f085-445d-8589-19a83fe74f5e
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# 방법: 해당 Timeline의 속도를 변경하지 않고 시계의 속도 변경
<xref:System.Windows.Media.Animation.ClockController> 개체의 <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> 속성을 사용하면 시계 <xref:System.Windows.Media.Animation.Timeline>의 <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A>를 변경하지 않고 <xref:System.Windows.Media.Animation.Clock>의 속도를 변경할 수 있습니다.  다음 예제에서는 <xref:System.Windows.Media.Animation.ClockController>를 사용하여 시계의 <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A>를 대화식으로 수정합니다.  <xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeedInvalidated> 이벤트 및 시계의 <xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeed%2A> 속성은 대화식 <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A>가 변경될 때마다 시계의 현재 전역 속도를 표시하는 데 사용됩니다.  
  
## 예제  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerSpeedRatioExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerSpeedRatioExample.cs#graphicsmmclockcontrollerspeedratioexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerSpeedRatioExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerspeedratioexample.vb#graphicsmmclockcontrollerspeedratioexample)]