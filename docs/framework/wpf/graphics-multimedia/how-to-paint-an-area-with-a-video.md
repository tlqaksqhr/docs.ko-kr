---
title: "방법: 비디오로 영역 그리기"
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
- painting with a video [WPF]
- video [WPF], painting with
- brushes [WPF], painting with a video
ms.assetid: 04dd6600-4a6e-4b43-a93e-21cce7dfbcb8
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 362231bbd1f4e95c260370a99233b7e8c2617ca1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-paint-an-area-with-a-video"></a><span data-ttu-id="b9541-102">방법: 비디오로 영역 그리기</span><span class="sxs-lookup"><span data-stu-id="b9541-102">How to: Paint an Area with a Video</span></span>
<span data-ttu-id="b9541-103">이 예제에는 미디어와 영역을 그리는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b9541-103">This example shows how to paint an area with media.</span></span> <span data-ttu-id="b9541-104">한 가지 방법은 미디어를 사용 하 여 영역을 그리는 데 사용 하는 것을 <xref:System.Windows.Controls.MediaElement> 와 함께 한 <xref:System.Windows.Media.VisualBrush>합니다.</span><span class="sxs-lookup"><span data-stu-id="b9541-104">One way to paint an area with media is to use a <xref:System.Windows.Controls.MediaElement> together with a <xref:System.Windows.Media.VisualBrush>.</span></span> <span data-ttu-id="b9541-105">사용 하 여는 <xref:System.Windows.Controls.MediaElement> 로드는 미디어 재생 및를 사용 하 여 설정 하는 <xref:System.Windows.Media.VisualBrush.Visual%2A> 의 속성은 <xref:System.Windows.Media.VisualBrush>합니다.</span><span class="sxs-lookup"><span data-stu-id="b9541-105">Use the <xref:System.Windows.Controls.MediaElement> to load and play the media, and then use it to set the <xref:System.Windows.Media.VisualBrush.Visual%2A> property of the <xref:System.Windows.Media.VisualBrush>.</span></span> <span data-ttu-id="b9541-106">그런 다음 사용할 수는 <xref:System.Windows.Media.VisualBrush> 로드 된 미디어를 사용 하 여 영역을 그리는 데 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9541-106">You can then use the <xref:System.Windows.Media.VisualBrush> to paint an area with the loaded media.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9541-107">예제</span><span class="sxs-lookup"><span data-stu-id="b9541-107">Example</span></span>  
 <span data-ttu-id="b9541-108">다음 예제에서는 <xref:System.Windows.Controls.MediaElement> 및 <xref:System.Windows.Media.VisualBrush> 을 그리는 <xref:System.Windows.Controls.TextBlock.Foreground%2A> 의 <xref:System.Windows.Controls.TextBlock> 컨트롤 비디오를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9541-108">The following example uses a <xref:System.Windows.Controls.MediaElement> and a <xref:System.Windows.Media.VisualBrush> to paint the <xref:System.Windows.Controls.TextBlock.Foreground%2A> of a <xref:System.Windows.Controls.TextBlock> control with video.</span></span> <span data-ttu-id="b9541-109">설정 하는이 예제는 <xref:System.Windows.Controls.MediaElement.IsMuted%2A> 의 속성은 <xref:System.Windows.Controls.MediaElement> 를 `true` 소리가 생성 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9541-109">This example sets the <xref:System.Windows.Controls.MediaElement.IsMuted%2A> property of the <xref:System.Windows.Controls.MediaElement> to `true` so that it produces no sound.</span></span>  
  
 [!code-csharp[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/PaintWithVideoExample.cs#graphicsmmvideoastextbackgroundinline)]
 [!code-vb[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/paintwithvideoexample.vb#graphicsmmvideoastextbackgroundinline)]
 [!code-xaml[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/PaintWithVideoExample.xaml#graphicsmmvideoastextbackgroundinline)]  
  
## <a name="example"></a><span data-ttu-id="b9541-110">예제</span><span class="sxs-lookup"><span data-stu-id="b9541-110">Example</span></span>  
 <span data-ttu-id="b9541-111">때문에 <xref:System.Windows.Media.VisualBrush> 에서 상속 되는 <xref:System.Windows.Media.TileBrush> 클래스인 바둑판식 배열은 모드가 몇 가지 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9541-111">Because <xref:System.Windows.Media.VisualBrush> inherits from the <xref:System.Windows.Media.TileBrush> class, it provides several tiling modes.</span></span> <span data-ttu-id="b9541-112">설정 하 여는 <xref:System.Windows.Media.TileBrush.TileMode%2A> 속성은 <xref:System.Windows.Media.VisualBrush> 를 <xref:System.Windows.Media.TileMode.Tile> 설정 하 여 해당 <xref:System.Windows.Media.TileBrush.Viewport%2A> 사용자 칠하고 있는 영역 보다 작은 값으로 속성을 바둑판식 배열된 패턴을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9541-112">By setting the <xref:System.Windows.Media.TileBrush.TileMode%2A> property of a <xref:System.Windows.Media.VisualBrush> to <xref:System.Windows.Media.TileMode.Tile> and by setting its <xref:System.Windows.Media.TileBrush.Viewport%2A> property to a value smaller than the area that you are painting, you can create a tiled pattern.</span></span>  
  
 <span data-ttu-id="b9541-113">다음 예제는 점을 제외 하 고 이전 예제와 동일한는 <xref:System.Windows.Media.VisualBrush> 비디오에서 패턴을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9541-113">The following example is identical to the previous example, except that the <xref:System.Windows.Media.VisualBrush> generates a pattern from the video.</span></span>  
  
 [!code-csharp[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/PaintWithVideoExample.cs#graphicsmmvideoastextbackgroundtiledinline)]
 [!code-vb[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/paintwithvideoexample.vb#graphicsmmvideoastextbackgroundtiledinline)]
 [!code-xaml[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/PaintWithVideoExample.xaml#graphicsmmvideoastextbackgroundtiledinline)]  
  
 <span data-ttu-id="b9541-114">응용 프로그램에 미디어 파일 등의 콘텐츠 파일을 추가 하는 방법에 대 한 정보를 참조 하십시오. [WPF 응용 프로그램 리소스, 내용 및 데이터 파일](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b9541-114">For information about how to add a content file, such as a media file, to your application, see [WPF Application Resource, Content, and Data Files](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md).</span></span> <span data-ttu-id="b9541-115">미디어 파일을 추가, 리소스 파일이 아닌, 콘텐츠 파일로 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9541-115">When you add a media file, you must add it as a content file, not as a resource file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9541-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b9541-116">See Also</span></span>  
 <xref:System.Windows.Media.VisualBrush>  
 [<span data-ttu-id="b9541-117">이미지, 그림 및 시각적 표시로 그리기</span><span class="sxs-lookup"><span data-stu-id="b9541-117">Painting with Images, Drawings, and Visuals</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)  
 [<span data-ttu-id="b9541-118">TileBrush 개요</span><span class="sxs-lookup"><span data-stu-id="b9541-118">TileBrush Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/tilebrush-overview.md)  
 [<span data-ttu-id="b9541-119">멀티미디어 개요</span><span class="sxs-lookup"><span data-stu-id="b9541-119">Multimedia Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/multimedia-overview.md)
