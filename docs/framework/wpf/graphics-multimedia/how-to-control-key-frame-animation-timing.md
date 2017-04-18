---
title: "방법: 키 프레임 애니메이션 타이밍 제어 | Microsoft Docs"
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
  - "키 프레임[WPF], 타이밍"
  - "키 프레임 애니메이션 타이밍"
ms.assetid: b059216f-7d4b-4ca8-a019-bc287ee7bf16
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: 키 프레임 애니메이션 타이밍 제어
이 예제에서는 키 프레임 애니메이션 내에서 키 프레임의 타이밍을 제어하는 방법을 보여 줍니다.  다른 애니메이션과 마찬가지로 키 프레임 애니메이션에는 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 속성이 있습니다.  애니메이션의 기간을 지정하는 동시에 애니메이션의 각 키 프레임에 해당 기간의 얼마를 할당할 것인지 지정해야 합니다.  시간을 할당하려면 애니메이션의 각 키 프레임에 대해 <xref:System.Windows.Media.Animation.KeyTime>을 지정합니다.  
  
 각 키 프레임에 대한 <xref:System.Windows.Media.Animation.KeyTime>은 키 프레임이 재생되는 기간을 지정하는 것이 아니라 키 프레임이 끝나는 시간을 지정합니다.  <xref:System.Windows.Media.Animation.KeyTime>을 <xref:System.TimeSpan> 값, 백분율 또는 <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A>으로 지정하거나 특수한 <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> 값으로 지정할 수 있습니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>를 사용하여 화면에 표시되는 사각형에 애니메이션 효과를 줍니다.  키 프레임의 키 시간은 <xref:System.TimeSpan> 값으로 설정됩니다.  
  
 [!code-csharp[keyframes_snip#KeyTimesTimeSpanExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimestimespanexample)]
 [!code-vb[keyframes_snip#KeyTimesTimeSpanExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimestimespanexample)]
 [!code-xml[keyframes_snip#KeyTimesTimeSpanExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimestimespanexample)]  
  
 다음 그림에서는 각 키 프레임 값이 도달한 경우를 보여 줍니다.  
  
 ![3, 4, 10초에 키 값에 도달](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime1-timespan.png "graphicsmm\_keyframe\_keytime1\_timespan")  
  
 다음 예제에서는 키 프레임의 키 시간이 백분율 값으로 설정되는 점을 제외하고는 이전 예제와 동일한 애니메이션을 보여 줍니다.  
  
 [!code-csharp[keyframes_snip#KeyTimesPercentageExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespercentageexample)]
 [!code-vb[keyframes_snip#KeyTimesPercentageExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespercentageexample)]
 [!code-xml[keyframes_snip#KeyTimesPercentageExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespercentageexample)]  
  
 다음 그림에서는 각 키 프레임 값이 도달한 경우를 보여 줍니다.  
  
 ![3, 4, 10초에 키 값에 도달](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime2-percentage.png "graphicsmm\_keyframe\_keytime2\_percentage")  
  
 다음 예제에서는 <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> 키 시간 값을 사용합니다.  
  
 [!code-csharp[keyframes_snip#KeyTimesUniformExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimesuniformexample)]
 [!code-vb[keyframes_snip#KeyTimesUniformExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimesuniformexample)]
 [!code-xml[keyframes_snip#KeyTimesUniformExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimesuniformexample)]  
  
 다음 그림에서는 각 키 프레임 값이 도달한 경우를 보여 줍니다.  
  
 ![키 값은 3.3, 6.6 및 9.9초에 도달](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime3-uniform.png "graphicsmm\_keyframe\_keytime3\_uniform")  
  
 마지막 예제에서는 <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> 키 시간 값을 사용합니다.  
  
 [!code-csharp[keyframes_snip#KeyTimesPacedExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespacedexample)]
 [!code-vb[keyframes_snip#KeyTimesPacedExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespacedexample)]
 [!code-xml[keyframes_snip#KeyTimesPacedExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespacedexample)]  
  
 다음 그림에서는 각 키 프레임 값이 도달한 경우를 보여 줍니다.  
  
 ![0, 5, 10초에 키 값에 도달](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyframe-keytime4-paced.png "graphicsmm\_keyframe\_keytime4\_paced")  
  
 단일 속성에 단일 애니메이션만 적용되므로 편의상 이 예제의 코드 버전에서는 Storyboard를 사용하지 않고 로컬 애니메이션을 사용하지만 대신 Storyboard를 사용하도록 예제를 수정할 수 있습니다.  코드에서 Storyboard를 선언하는 방법을 보여 주는 예제를 보려면 [Storyboard를 사용하여 속성에 애니메이션 효과 주기](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)를 참조하십시오.  
  
 전체 샘플을 보려면 [KeyFrame Animation 샘플](http://go.microsoft.com/fwlink/?LinkID=160012)을 참조하십시오.  키 프레임 애니메이션에 대한 자세한 내용은 [키 프레임 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)를 참조하십시오.  
  
## 참고 항목  
 [키 프레임 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [방법 항목](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)