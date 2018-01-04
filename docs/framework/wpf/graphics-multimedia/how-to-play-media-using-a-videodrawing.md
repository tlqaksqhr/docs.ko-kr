---
title: "방법: VideoDrawing을 사용하여 미디어 재생"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- playback of media [WPF]
- classes [WPF], MediaPlayer
ms.assetid: 165d47ed-22ce-4ded-aa6a-aa9b7467de87
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 773a0a1e2252b3f7154ef218f887be6f56e9995f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-play-media-using-a-videodrawing"></a><span data-ttu-id="6c3d2-102">방법: VideoDrawing을 사용하여 미디어 재생</span><span class="sxs-lookup"><span data-stu-id="6c3d2-102">How to: Play Media using a VideoDrawing</span></span>
<span data-ttu-id="6c3d2-103">오디오 또는 비디오 파일을 재생 하려면 사용 하는 <xref:System.Windows.Media.VideoDrawing> 및 <xref:System.Windows.Media.MediaPlayer>합니다.</span><span class="sxs-lookup"><span data-stu-id="6c3d2-103">To play an audio or video file, you use a <xref:System.Windows.Media.VideoDrawing> and a <xref:System.Windows.Media.MediaPlayer>.</span></span> <span data-ttu-id="6c3d2-104">미디어를 로드하고 재생하는 방법에는 다음 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c3d2-104">There are two ways to load and play media.</span></span> <span data-ttu-id="6c3d2-105">첫 번째 사용 하는 한 <xref:System.Windows.Media.MediaPlayer> 및 <xref:System.Windows.Media.VideoDrawing> 고 두 번째 방법은 직접 만들 <xref:System.Windows.Media.MediaTimeline> 를 사용 하는 <xref:System.Windows.Media.MediaPlayer> 및 <xref:System.Windows.Media.VideoDrawing>합니다.</span><span class="sxs-lookup"><span data-stu-id="6c3d2-105">The first is to use a <xref:System.Windows.Media.MediaPlayer> and a <xref:System.Windows.Media.VideoDrawing> by themselves, and the second way is to create your own <xref:System.Windows.Media.MediaTimeline> to use with the <xref:System.Windows.Media.MediaPlayer> and <xref:System.Windows.Media.VideoDrawing>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6c3d2-106">응용 프로그램을 사용하여 미디어를 배포하는 경우 이미지의 경우처럼 미디어 파일을 프로젝트 리소스로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6c3d2-106">When distributing media with your application, you cannot use a media file as a project resource, like you would an image.</span></span> <span data-ttu-id="6c3d2-107">대신 프로젝트 파일에서 미디어 형식을 `Content`로 설정하고 `CopyToOutputDirectory`를 `PreserveNewest` 또는 `Always`로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c3d2-107">In your project file, you must instead set the media type to `Content` and set `CopyToOutputDirectory` to `PreserveNewest` or `Always`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6c3d2-108">예</span><span class="sxs-lookup"><span data-stu-id="6c3d2-108">Example</span></span>  
 <span data-ttu-id="6c3d2-109">다음 예제에서는 한 <xref:System.Windows.Media.VideoDrawing> 및 <xref:System.Windows.Media.MediaPlayer> 비디오 파일을 한 번 재생 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c3d2-109">The following example uses a <xref:System.Windows.Media.VideoDrawing> and a <xref:System.Windows.Media.MediaPlayer> to play a video file once.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 <span data-ttu-id="6c3d2-110">제어할 추가 타이밍 미디어를 사용 하 여 한 <xref:System.Windows.Media.MediaTimeline> 와 <xref:System.Windows.Media.MediaPlayer> 및 <xref:System.Windows.Media.VideoDrawing> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="6c3d2-110">To gain additional timing control over the media, use a <xref:System.Windows.Media.MediaTimeline> with the <xref:System.Windows.Media.MediaPlayer> and <xref:System.Windows.Media.VideoDrawing> objects.</span></span> <span data-ttu-id="6c3d2-111"><xref:System.Windows.Media.MediaTimeline> 비디오를 반복 해야 하는지 여부를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c3d2-111">The <xref:System.Windows.Media.MediaTimeline> enables you to specify whether the video should repeat.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6c3d2-112">예</span><span class="sxs-lookup"><span data-stu-id="6c3d2-112">Example</span></span>  
 <span data-ttu-id="6c3d2-113">다음 예제에서는 한 <xref:System.Windows.Media.MediaTimeline> 와 <xref:System.Windows.Media.MediaPlayer> 및 <xref:System.Windows.Media.VideoDrawing> 비디오를 반복 해 서 재생 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="6c3d2-113">The following example uses a <xref:System.Windows.Media.MediaTimeline> with the <xref:System.Windows.Media.MediaPlayer> and <xref:System.Windows.Media.VideoDrawing> objects to play a video repeatedly.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline)]  
  
 <span data-ttu-id="6c3d2-114">유의 사용 하는 경우는 <xref:System.Windows.Media.MediaTimeline>, 대화형 사용 하 여 <xref:System.Windows.Media.Animation.ClockController> 에서 반환 된는 <xref:System.Windows.Media.Animation.Clock.Controller%2A> 속성의는 <xref:System.Windows.Media.MediaClock> 재생을 제어 하려면 미디어의 대화형 메서드 대신 <xref:System.Windows.Media.MediaPlayer>합니다.</span><span class="sxs-lookup"><span data-stu-id="6c3d2-114">Note that, when you use a <xref:System.Windows.Media.MediaTimeline>, you use the interactive <xref:System.Windows.Media.Animation.ClockController> returned from the <xref:System.Windows.Media.Animation.Clock.Controller%2A> property of the <xref:System.Windows.Media.MediaClock> to control media playback instead of the interactive methods of <xref:System.Windows.Media.MediaPlayer>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c3d2-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6c3d2-115">See Also</span></span>  
 <xref:System.Windows.Media.VideoDrawing>  
 [<span data-ttu-id="6c3d2-116">Drawing 개체 개요</span><span class="sxs-lookup"><span data-stu-id="6c3d2-116">Drawing Objects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)
