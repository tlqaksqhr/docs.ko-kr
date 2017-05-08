---
title: "방법: 애니메이션의 지속 시간 설정 | Microsoft Docs"
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
  - "애니메이션, 기간"
  - "애니메이션 지속 시간"
  - "Timeline, description"
ms.assetid: 155034ef-7d00-4416-a73c-b1713992d2eb
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: 애니메이션의 지속 시간 설정
<xref:System.Windows.Media.Animation.Timeline>은 Timeline의 <xref:System.Windows.Duration>으로 결정되는 시간 세그먼트 및 해당 세그먼트의 길이를 나타냅니다.  <xref:System.Windows.Media.Animation.Timeline>이 해당 지속 시간의 끝에 도달하면 재생이 중지됩니다.  <xref:System.Windows.Media.Animation.Timeline>에 자식 Timeline이 있는 경우 자식 Timeline의 재생도 중지됩니다.  애니메이션의 경우 <xref:System.Windows.Duration>은 애니메이션이 해당 시작 값에서 끝 값까지 전환하는 데 걸리는 시간을 지정합니다.  
  
 제한된 특정 시간 값 또는 특수 값인 <xref:System.Windows.Duration.Automatic%2A> 또는 <xref:System.Windows.Duration.Forever%2A>를 사용하여 <xref:System.Windows.Duration>을 지정할 수 있습니다.  애니메이션의 지속 시간은 항상 시간 값이어야 합니다. 이는 애니메이션에 항상 유한한 길이가 정의되어 있어야 하기 때문이며 그렇지 않은 경우에는 애니메이션이 해당 대상 값 간에 어떻게 전환되는지 알 수 없습니다.  <xref:System.Windows.Media.Animation.Storyboard> 및 <xref:System.Windows.Media.Animation.ParallelTimeline>과 같은 컨테이너 Timeline\(<xref:System.Windows.Media.Animation.TimelineGroup> 개체\)의 지속 시간 기본값은 <xref:System.Windows.Duration.Automatic%2A>이므로, 마지막 자식의 재생이 중지되면 자동으로 종료됩니다.  
  
 다음 예제에서는 <xref:System.Windows.Shapes.Rectangle>의 너비, 높이 및 채우기 색에 애니메이션 효과를 줍니다.  애니메이션 Timeline 및 컨테이너 Timeline에 지속 시간을 설정하여 애니메이션 인식 속도를 제어하고 자식 Timeline의 지속 시간을 컨테이너 Timeline의 지속 시간으로 재정의하는 등의 애니메이션 효과를 적용합니다.  
  
## 예제  
 [!code-xml[timingbehaviors_snip#DurationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/DurationExample.xaml#durationexamplewholepage)]  
  
## 참고 항목  
 <xref:System.Windows.Duration>   
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)