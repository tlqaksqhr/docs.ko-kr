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
ms.workload: dotnet
ms.openlocfilehash: a72843547d934aeaeec062eec1241e402baf56bf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-paint-an-area-with-a-video"></a>방법: 비디오로 영역 그리기
이 예제에는 미디어와 영역을 그리는 방법을 보여 줍니다. 한 가지 방법은 미디어를 사용 하 여 영역을 그리는 데 사용 하는 것을 <xref:System.Windows.Controls.MediaElement> 와 함께 한 <xref:System.Windows.Media.VisualBrush>합니다. 사용 하 여는 <xref:System.Windows.Controls.MediaElement> 로드는 미디어 재생 및를 사용 하 여 설정 하는 <xref:System.Windows.Media.VisualBrush.Visual%2A> 의 속성은 <xref:System.Windows.Media.VisualBrush>합니다. 그런 다음 사용할 수는 <xref:System.Windows.Media.VisualBrush> 로드 된 미디어를 사용 하 여 영역을 그리는 데 합니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 <xref:System.Windows.Controls.MediaElement> 및 <xref:System.Windows.Media.VisualBrush> 을 그리는 <xref:System.Windows.Controls.TextBlock.Foreground%2A> 의 <xref:System.Windows.Controls.TextBlock> 컨트롤 비디오를 포함 합니다. 설정 하는이 예제는 <xref:System.Windows.Controls.MediaElement.IsMuted%2A> 의 속성은 <xref:System.Windows.Controls.MediaElement> 를 `true` 소리가 생성 되도록 합니다.  
  
 [!code-csharp[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/PaintWithVideoExample.cs#graphicsmmvideoastextbackgroundinline)]
 [!code-vb[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/paintwithvideoexample.vb#graphicsmmvideoastextbackgroundinline)]
 [!code-xaml[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/PaintWithVideoExample.xaml#graphicsmmvideoastextbackgroundinline)]  
  
## <a name="example"></a>예  
 때문에 <xref:System.Windows.Media.VisualBrush> 에서 상속 되는 <xref:System.Windows.Media.TileBrush> 클래스인 바둑판식 배열은 모드가 몇 가지 제공 합니다. 설정 하 여는 <xref:System.Windows.Media.TileBrush.TileMode%2A> 속성은 <xref:System.Windows.Media.VisualBrush> 를 <xref:System.Windows.Media.TileMode.Tile> 설정 하 여 해당 <xref:System.Windows.Media.TileBrush.Viewport%2A> 사용자 칠하고 있는 영역 보다 작은 값으로 속성을 바둑판식 배열된 패턴을 만들 수 있습니다.  
  
 다음 예제는 점을 제외 하 고 이전 예제와 동일한는 <xref:System.Windows.Media.VisualBrush> 비디오에서 패턴을 생성 합니다.  
  
 [!code-csharp[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/PaintWithVideoExample.cs#graphicsmmvideoastextbackgroundtiledinline)]
 [!code-vb[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/paintwithvideoexample.vb#graphicsmmvideoastextbackgroundtiledinline)]
 [!code-xaml[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/PaintWithVideoExample.xaml#graphicsmmvideoastextbackgroundtiledinline)]  
  
 응용 프로그램에 미디어 파일 등의 콘텐츠 파일을 추가 하는 방법에 대 한 정보를 참조 하십시오. [WPF 응용 프로그램 리소스, 내용 및 데이터 파일](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md)합니다. 미디어 파일을 추가, 리소스 파일이 아닌, 콘텐츠 파일로 추가 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Media.VisualBrush>  
 [이미지, 그림 및 시각적 표시로 그리기](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)  
 [TileBrush 개요](../../../../docs/framework/wpf/graphics-multimedia/tilebrush-overview.md)  
 [멀티미디어 개요](../../../../docs/framework/wpf/graphics-multimedia/multimedia-overview.md)
