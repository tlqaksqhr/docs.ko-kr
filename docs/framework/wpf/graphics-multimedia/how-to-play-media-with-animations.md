---
title: '방법: 애니메이션이 있는 미디어 재생'
ms.date: 03/30/2017
helpviewer_keywords:
- multimedia [WPF], playback with animations
- playback of media [WPF], with animations
- animation [WPF], media playback with
- media [WPF], playback with animations
ms.assetid: 8982b7b7-1c6c-4b24-8801-b328862975f5
ms.openlocfilehash: 21c9b35828dca03c05def11cff22f1f1e33d45cc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33560277"
---
# <a name="how-to-play-media-with-animations"></a><span data-ttu-id="5ec61-102">방법: 애니메이션이 있는 미디어 재생</span><span class="sxs-lookup"><span data-stu-id="5ec61-102">How to: Play Media with Animations</span></span>
<span data-ttu-id="5ec61-103">사용 하 여 동시에 미디어 및 애니메이션을 재생 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.MediaTimeline> 및 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> 클래스를 같은 <xref:System.Windows.Media.Animation.Storyboard>합니다.</span><span class="sxs-lookup"><span data-stu-id="5ec61-103">This example shows how to play media and animations at the same time by using the <xref:System.Windows.Media.MediaTimeline> and <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> classes in the same <xref:System.Windows.Media.Animation.Storyboard>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5ec61-104">예제</span><span class="sxs-lookup"><span data-stu-id="5ec61-104">Example</span></span>  
 <span data-ttu-id="5ec61-105">하나 이상 사용할 수 <xref:System.Windows.Media.MediaTimeline> 개체에 <xref:System.Windows.Media.Animation.Storyboard> 다른 함께 <xref:System.Windows.Media.Animation.Timeline> 애니메이션과 같은 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="5ec61-105">You can use one or more <xref:System.Windows.Media.MediaTimeline> objects in a <xref:System.Windows.Media.Animation.Storyboard> together with other <xref:System.Windows.Media.Animation.Timeline> objects, such as animations.</span></span>  
  
 <span data-ttu-id="5ec61-106">다음 예에서는 <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A> 속성의는 <xref:System.Windows.Media.Animation.Storyboard> 의 값에 `Slip`, 애니메이션, (이 예의 비디오) 미디어 진행 될 때까지 진행 되지 않는 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ec61-106">The following example sets the <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A> property of the <xref:System.Windows.Media.Animation.Storyboard> to a value of `Slip`, which specifies that the animation does not progress until the media (video in this example) progresses.</span></span> <span data-ttu-id="5ec61-107">이 기능은 로드 시간 때문에 미디어 재생을 지연해야 할 경우에 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ec61-107">This functionality might be needed if media playback is delayed because of loading time.</span></span>  
  
 [!code-xaml[MediaGallery_snippet#MediaTimelinePlusAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snippet/CSharp/MediaTimelinePlusAnimationExample.xaml#mediatimelineplusanimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="5ec61-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5ec61-108">See Also</span></span>  
 <xref:System.Windows.Media.MediaTimeline>  
 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>  
 <xref:System.Windows.Media.Animation.Storyboard>  
 <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A>  
 [<span data-ttu-id="5ec61-109">방법 항목</span><span class="sxs-lookup"><span data-stu-id="5ec61-109">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/audio-and-video-how-to-topics.md)  
 [<span data-ttu-id="5ec61-110">Storyboard 개요</span><span class="sxs-lookup"><span data-stu-id="5ec61-110">Storyboards Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)  
 [<span data-ttu-id="5ec61-111">키 프레임 애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="5ec61-111">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="5ec61-112">애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="5ec61-112">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="5ec61-113">그래픽 및 멀티미디어</span><span class="sxs-lookup"><span data-stu-id="5ec61-113">Graphics and Multimedia</span></span>](../../../../docs/framework/wpf/graphics-multimedia/index.md)
