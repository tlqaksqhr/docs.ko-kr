---
title: "방법: Storyboard를 사용하여 MediaElement 제어 | Microsoft Docs"
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
  - "미디어 재생 제어, Storyboard로"
  - "미디어, Storyboard로 재생 제어"
  - "멀티미디어, Storyboard로 미디어 재생 제어"
  - "미디어 재생, Storyboard로 제어"
  - "스토리보드, 미디어 재생 제어"
ms.assetid: 6128ca77-b826-4e36-b968-6f237157c543
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: Storyboard를 사용하여 MediaElement 제어
이 예제에서는 <xref:System.Windows.Media.Animation.Storyboard>의 <xref:System.Windows.Media.MediaTimeline>을 사용하여 <xref:System.Windows.Controls.MediaElement>를 제어하는 방법을 보여 줍니다.  
  
## 예제  
 <xref:System.Windows.Media.Animation.Storyboard>의 <xref:System.Windows.Media.MediaTimeline>을 사용하여 <xref:System.Windows.Controls.MediaElement>의 타이밍을 제어하는 이 기능은 애니메이션과 같은 다른 <xref:System.Windows.Media.Animation.Timeline> 개체의 기능과 동일합니다.  예를 들어 <xref:System.Windows.Media.MediaTimeline>은 <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> 속성과 같은 <xref:System.Windows.Media.Animation.Timeline> 속성을 사용하여 <xref:System.Windows.Controls.MediaElement>를 시작할 시기, 즉 미디어 재생을 시작할 시기를 지정합니다.  또한 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 속성을 사용하여 <xref:System.Windows.Controls.MediaElement>가 활성 상태인 기간, 즉 미디어 재생 기간을 지정합니다.  <xref:System.Windows.Media.Animation.Storyboard>와 함께 <xref:System.Windows.Media.Animation.Timeline> 개체를 사용하는 방법에 대한 자세한 내용은 [Storyboard 개요](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)를 참조하십시오.  
  
 이 예제에서는 <xref:System.Windows.Media.MediaTimeline>을 사용하여 재생을 제어하는 간단한 미디어 플레이어를 만드는 방법을 보여 줍니다.  이 미디어 플레이어에는 재생, 일시 중지, 다시 시작 및 중지 단추가 있습니다.  이 미디어 플레이어에는 진행률 표시줄의 기능을 하는 <xref:System.Windows.Controls.Slider> 컨트롤도 있습니다.  
  
 다음 예제에서는 미디어 플레이어의 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]를 만듭니다.  
  
 [!code-xml[MediaGallery_snip#MediaTimelineExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaTimelineExample.xaml#mediatimelineexamplewholepage)]  
  
 다음 예제에서는 진행률 표시줄 기능을 만듭니다.  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaTimelineExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaTimelineExample.xaml.cs#codebehindmediatimelineexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaTimelineExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaTimelineExample.xaml.vb#codebehindmediatimelineexamplewholepage)]  
  
## 참고 항목  
 <xref:System.Windows.Controls.MediaElement>   
 <xref:System.Windows.Media.MediaTimeline>   
 <xref:System.Windows.Media.Animation.Storyboard>   
 [MediaElement 제어\(재생, 일시 중지, 정지, 볼륨 및 속도\)](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-mediaelement-play-pause-stop-volume-and-speed.md)   
 [Storyboard 개요](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)   
 [키 프레임 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [방법 항목](../../../../docs/framework/wpf/graphics-multimedia/audio-and-video-how-to-topics.md)   
 [그래픽 및 멀티미디어](../../../../docs/framework/wpf/graphics-multimedia/index.md)