---
title: "방법: 대화형으로 Clock 제어 | Microsoft Docs"
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
  - "Clock, 대화형으로 제어"
  - "대화형으로 Clock 제어"
ms.assetid: d0b520e0-2f18-4cef-977f-2909e709548a
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# 방법: 대화형으로 Clock 제어
<xref:System.Windows.Media.Animation.Clock> 개체의 <xref:System.Windows.Media.Animation.ClockController> 속성을 사용하면 대화식으로 시계를 시작, 일시 중지, 다시 시작, 이동, 해당 전체 기간의 끝으로 진행 또는 중지할 수 있습니다.  시간 트리의 루트 시계만 대화식으로 제어할 수 있습니다.  
  
> [!NOTE]
>  시계에서 직접 작업하지 않고 애니메이션을 대화식으로 제어하는 방법에는 여러 가지가 있으며 Storyboard를 사용할 수도 있습니다.  Storyboard는 태그와 코드 모두에서 지원됩니다.  예제를 보려면 [Storyboard를 사용하여 속성에 애니메이션 효과 주기](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md) 또는 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)를 참조하십시오.  
  
 다음 예제에서는 몇 가지 단추를 사용하여 애니메이션 시계를 대화식으로 제어합니다.  
  
## 예제  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerExample.cs#graphicsmmclockcontrollerexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerexample.vb#graphicsmmclockcontrollerexample)]  
  
## 참고 항목  
 [Storyboard를 사용하여 속성에 애니메이션 효과 주기](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)   
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)