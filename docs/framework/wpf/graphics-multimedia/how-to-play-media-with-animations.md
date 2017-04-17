---
title: "방법: 애니메이션이 있는 미디어 재생 | Microsoft Docs"
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
  - "애니메이션을 사용 하 여 멀티미디어, 재생"
  - "애니메이션이 있는 미디어 재생"
  - "애니메이션을 사용 하 여 미디어 재생"
  - "미디어, 애니메이션을 사용 하 여 재생"
ms.assetid: 8982b7b7-1c6c-4b24-8801-b328862975f5
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# 방법: 애니메이션이 있는 미디어 재생
사용 하 여 동시에 미디어 및 애니메이션을 재생 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.MediaTimeline> 및 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> 클래스를 같은 <xref:System.Windows.Media.Animation.Storyboard>합니다.  
  
## <a name="example"></a>예제  
 하나 이상 사용할 수 <xref:System.Windows.Media.MediaTimeline> 개체에 <xref:System.Windows.Media.Animation.Storyboard> 다른 함께 <xref:System.Windows.Media.Animation.Timeline> 애니메이션 등의 개체입니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A> 의 속성은 <xref:System.Windows.Media.Animation.Storyboard> 의 값을 `Slip`, (이 예제에서는 비디오) 미디어 진행 될 때까지 애니메이션을 진행을 지정 하는 합니다. 이 기능은 미디어 재생 로드 시간으로 인해 지연 되는 경우 필요할 수 있습니다.  
  
 [!code-xml[MediaGallery_snippet#MediaTimelinePlusAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snippet/CSharp/MediaTimelinePlusAnimationExample.xaml#mediatimelineplusanimationexamplewholepage)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Media.MediaTimeline>   
 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>   
 <xref:System.Windows.Media.Animation.Storyboard>   
 <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A>   
 [방법 도움말 항목](../../../../docs/framework/wpf/graphics-multimedia/audio-and-video-how-to-topics.md)   
 [Storyboard 개요](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)   
 [키 프레임 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [그래픽 및 멀티미디어](../../../../docs/framework/wpf/graphics-multimedia/index.md)