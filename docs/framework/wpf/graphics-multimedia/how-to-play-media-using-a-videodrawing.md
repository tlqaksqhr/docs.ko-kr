---
title: '방법: VideoDrawing을 사용하여 미디어 재생'
ms.date: 03/30/2017
helpviewer_keywords:
- playback of media [WPF]
- classes [WPF], MediaPlayer
ms.assetid: 165d47ed-22ce-4ded-aa6a-aa9b7467de87
ms.openlocfilehash: 27959cc967eac0a0f642da079f8758b0f756800e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-play-media-using-a-videodrawing"></a>방법: VideoDrawing을 사용하여 미디어 재생
오디오 또는 비디오 파일을 재생 하려면 사용 하는 <xref:System.Windows.Media.VideoDrawing> 및 <xref:System.Windows.Media.MediaPlayer>합니다. 미디어를 로드하고 재생하는 방법에는 다음 두 가지가 있습니다. 첫 번째 사용 하는 한 <xref:System.Windows.Media.MediaPlayer> 및 <xref:System.Windows.Media.VideoDrawing> 고 두 번째 방법은 직접 만들 <xref:System.Windows.Media.MediaTimeline> 를 사용 하는 <xref:System.Windows.Media.MediaPlayer> 및 <xref:System.Windows.Media.VideoDrawing>합니다.  
  
> [!NOTE]
>  응용 프로그램을 사용하여 미디어를 배포하는 경우 이미지의 경우처럼 미디어 파일을 프로젝트 리소스로 사용할 수 없습니다. 대신 프로젝트 파일에서 미디어 형식을 `Content`로 설정하고 `CopyToOutputDirectory`를 `PreserveNewest` 또는 `Always`로 설정해야 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 한 <xref:System.Windows.Media.VideoDrawing> 및 <xref:System.Windows.Media.MediaPlayer> 비디오 파일을 한 번 재생 합니다.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 제어할 추가 타이밍 미디어를 사용 하 여 한 <xref:System.Windows.Media.MediaTimeline> 와 <xref:System.Windows.Media.MediaPlayer> 및 <xref:System.Windows.Media.VideoDrawing> 개체입니다. <xref:System.Windows.Media.MediaTimeline> 비디오를 반복 해야 하는지 여부를 지정할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 한 <xref:System.Windows.Media.MediaTimeline> 와 <xref:System.Windows.Media.MediaPlayer> 및 <xref:System.Windows.Media.VideoDrawing> 비디오를 반복 해 서 재생 하는 개체입니다.  
  
 [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline)]  
  
 유의 사용 하는 경우는 <xref:System.Windows.Media.MediaTimeline>, 대화형 사용 하 여 <xref:System.Windows.Media.Animation.ClockController> 에서 반환 된는 <xref:System.Windows.Media.Animation.Clock.Controller%2A> 속성의는 <xref:System.Windows.Media.MediaClock> 재생을 제어 하려면 미디어의 대화형 메서드 대신 <xref:System.Windows.Media.MediaPlayer>합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Media.VideoDrawing>  
 [Drawing 개체 개요](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)
