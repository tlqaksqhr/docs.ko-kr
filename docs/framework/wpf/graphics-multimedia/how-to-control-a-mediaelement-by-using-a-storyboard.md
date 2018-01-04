---
title: "방법: Storyboard를 사용하여 MediaElement 제어"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- multimedia [WPF], controlling playback of media with Storyboards
- controlling playback of media [WPF], with Storyboards
- Storyboards [WPF], controlling playback of media with
- media [WPF], controlling playback with Storyboards
- playback of media [WPF], controlling with Storyboards
ms.assetid: 6128ca77-b826-4e36-b968-6f237157c543
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f52801ee3704c13ec5213cfc54b6392baa97e245
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-control-a-mediaelement-by-using-a-storyboard"></a>방법: Storyboard를 사용하여 MediaElement 제어
제어 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.MediaElement> 를 사용 하 여 한 <xref:System.Windows.Media.MediaTimeline> 에 <xref:System.Windows.Media.Animation.Storyboard>합니다.  
  
## <a name="example"></a>예  
 사용 하는 경우는 <xref:System.Windows.Media.MediaTimeline> 에 <xref:System.Windows.Media.Animation.Storyboard> 의 타이밍을 제어 하는 <xref:System.Windows.Controls.MediaElement>, 다른 기능과 동일 <xref:System.Windows.Media.Animation.Timeline> 애니메이션과 같은 개체입니다. 예를 들어는 <xref:System.Windows.Media.MediaTimeline> 사용 하 여 <xref:System.Windows.Media.Animation.Timeline> 같은 속성은 <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> 속성 시작 하는 시기를 지정 하는 <xref:System.Windows.Controls.MediaElement> (미디어 재생 시작)입니다. 또한 사용 하 여는 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 속성을 통해 지정 시간 <xref:System.Windows.Controls.MediaElement> 활성화 (미디어 재생 기간). 사용에 대 한 자세한 내용은 <xref:System.Windows.Media.Animation.Timeline> 개체와 <xref:System.Windows.Media.Animation.Storyboard>, 참조 [적기](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)합니다.  
  
 사용 하는 간단한 미디어 플레이어를 만드는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.MediaTimeline> 재생을 제어할 수 있습니다. 미디어 플레이어에는 재생, 일시 중지, 다시 시작 하 고 단추를 중지 합니다. 플레이어 역시는 <xref:System.Windows.Controls.Slider> 역할 진행률 표시줄을 컨트롤입니다.  
  
 다음 예제에서는 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 미디어 플레이어에 대 한 합니다.  
  
 [!code-xaml[MediaGallery_snip#MediaTimelineExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaTimelineExample.xaml#mediatimelineexamplewholepage)]  
  
 다음 예에서는 진행률 표시줄에 대 한 기능을 만듭니다.  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaTimelineExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaTimelineExample.xaml.cs#codebehindmediatimelineexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaTimelineExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaTimelineExample.xaml.vb#codebehindmediatimelineexamplewholepage)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Controls.MediaElement>  
 <xref:System.Windows.Media.MediaTimeline>  
 <xref:System.Windows.Media.Animation.Storyboard>  
 [MediaElement 제어(재생, 일시 중지, 정지, 볼륨 및 속도)](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-mediaelement-play-pause-stop-volume-and-speed.md)  
 [Storyboard 개요](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)  
 [키 프레임 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [방법 항목](../../../../docs/framework/wpf/graphics-multimedia/audio-and-video-how-to-topics.md)  
 [그래픽 및 멀티미디어](../../../../docs/framework/wpf/graphics-multimedia/index.md)
