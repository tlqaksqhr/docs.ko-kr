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
ms.openlocfilehash: 2341d2814e5bd42c652865c76d115defcc5b15b2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-control-a-mediaelement-by-using-a-storyboard"></a><span data-ttu-id="ef312-102">방법: Storyboard를 사용하여 MediaElement 제어</span><span class="sxs-lookup"><span data-stu-id="ef312-102">How to: Control a MediaElement by Using a Storyboard</span></span>
<span data-ttu-id="ef312-103">제어 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.MediaElement> 를 사용 하 여 한 <xref:System.Windows.Media.MediaTimeline> 에 <xref:System.Windows.Media.Animation.Storyboard>합니다.</span><span class="sxs-lookup"><span data-stu-id="ef312-103">This example shows how to control a <xref:System.Windows.Controls.MediaElement> by using a <xref:System.Windows.Media.MediaTimeline> in a <xref:System.Windows.Media.Animation.Storyboard>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ef312-104">예제</span><span class="sxs-lookup"><span data-stu-id="ef312-104">Example</span></span>  
 <span data-ttu-id="ef312-105">사용 하는 경우는 <xref:System.Windows.Media.MediaTimeline> 에 <xref:System.Windows.Media.Animation.Storyboard> 의 타이밍을 제어 하는 <xref:System.Windows.Controls.MediaElement>, 다른 기능과 동일 <xref:System.Windows.Media.Animation.Timeline> 애니메이션과 같은 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="ef312-105">When you use a <xref:System.Windows.Media.MediaTimeline> in a <xref:System.Windows.Media.Animation.Storyboard> to control the timing of a <xref:System.Windows.Controls.MediaElement>, the functionality is identical to the functionality of other <xref:System.Windows.Media.Animation.Timeline> objects, such as animations.</span></span> <span data-ttu-id="ef312-106">예를 들어는 <xref:System.Windows.Media.MediaTimeline> 사용 하 여 <xref:System.Windows.Media.Animation.Timeline> 같은 속성은 <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> 속성 시작 하는 시기를 지정 하는 <xref:System.Windows.Controls.MediaElement> (미디어 재생 시작)입니다.</span><span class="sxs-lookup"><span data-stu-id="ef312-106">For example, a <xref:System.Windows.Media.MediaTimeline> uses <xref:System.Windows.Media.Animation.Timeline> properties like the <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> property to specify when to start a <xref:System.Windows.Controls.MediaElement> (start media playback).</span></span> <span data-ttu-id="ef312-107">또한 사용 하 여는 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 속성을 통해 지정 시간 <xref:System.Windows.Controls.MediaElement> 활성화 (미디어 재생 기간).</span><span class="sxs-lookup"><span data-stu-id="ef312-107">It also uses the <xref:System.Windows.Media.Animation.Timeline.Duration%2A> property to specify how long the <xref:System.Windows.Controls.MediaElement> is active (duration of media playback).</span></span> <span data-ttu-id="ef312-108">사용에 대 한 자세한 내용은 <xref:System.Windows.Media.Animation.Timeline> 개체와 <xref:System.Windows.Media.Animation.Storyboard>, 참조 [적기](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ef312-108">For more information about using <xref:System.Windows.Media.Animation.Timeline> objects with a <xref:System.Windows.Media.Animation.Storyboard>, see [Storyboards Overview](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).</span></span>  
  
 <span data-ttu-id="ef312-109">사용 하는 간단한 미디어 플레이어를 만드는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.MediaTimeline> 재생을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef312-109">This example shows how to create a simple media player that uses a <xref:System.Windows.Media.MediaTimeline> to control playback.</span></span> <span data-ttu-id="ef312-110">미디어 플레이어에는 재생, 일시 중지, 다시 시작 하 고 단추를 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef312-110">The media player includes play, pause, resume, and stop buttons.</span></span> <span data-ttu-id="ef312-111">플레이어 역시는 <xref:System.Windows.Controls.Slider> 역할 진행률 표시줄을 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="ef312-111">The player also has a <xref:System.Windows.Controls.Slider> control that acts as a progress bar.</span></span>  
  
 <span data-ttu-id="ef312-112">다음 예제에서는 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 미디어 플레이어에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef312-112">The following example creates the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] for the media player.</span></span>  
  
 [!code-xaml[MediaGallery_snip#MediaTimelineExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaTimelineExample.xaml#mediatimelineexamplewholepage)]  
  
 <span data-ttu-id="ef312-113">다음 예에서는 진행률 표시줄에 대 한 기능을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ef312-113">The following example creates the functionality for the progress bar.</span></span>  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaTimelineExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaTimelineExample.xaml.cs#codebehindmediatimelineexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaTimelineExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaTimelineExample.xaml.vb#codebehindmediatimelineexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="ef312-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ef312-114">See Also</span></span>  
 <xref:System.Windows.Controls.MediaElement>  
 <xref:System.Windows.Media.MediaTimeline>  
 <xref:System.Windows.Media.Animation.Storyboard>  
 [<span data-ttu-id="ef312-115">MediaElement 제어(재생, 일시 중지, 정지, 볼륨 및 속도)</span><span class="sxs-lookup"><span data-stu-id="ef312-115">Control a MediaElement (Play, Pause, Stop, Volume, and Speed)</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-mediaelement-play-pause-stop-volume-and-speed.md)  
 [<span data-ttu-id="ef312-116">Storyboard 개요</span><span class="sxs-lookup"><span data-stu-id="ef312-116">Storyboards Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)  
 [<span data-ttu-id="ef312-117">키 프레임 애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="ef312-117">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="ef312-118">애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="ef312-118">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="ef312-119">방법 항목</span><span class="sxs-lookup"><span data-stu-id="ef312-119">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/audio-and-video-how-to-topics.md)  
 [<span data-ttu-id="ef312-120">그래픽 및 멀티미디어</span><span class="sxs-lookup"><span data-stu-id="ef312-120">Graphics and Multimedia</span></span>](../../../../docs/framework/wpf/graphics-multimedia/index.md)
