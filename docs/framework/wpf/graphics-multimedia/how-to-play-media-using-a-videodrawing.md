---
title: "방법: VideoDrawing을 사용하여 미디어 재생 | Microsoft Docs"
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
  - "클래스, MediaPlayer"
  - "클래스, VideoDrawing"
  - "MediaPlayer 클래스"
  - "미디어 재생"
  - "VideoDrawing 클래스"
ms.assetid: 165d47ed-22ce-4ded-aa6a-aa9b7467de87
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# 방법: VideoDrawing을 사용하여 미디어 재생
오디오 또는 비디오 파일을 재생하려면 <xref:System.Windows.Media.VideoDrawing> 및 <xref:System.Windows.Media.MediaPlayer>를 사용합니다.  두 가지 방법으로 미디어를 로드하고 재생할 수 있습니다.  첫 번째 방법은 <xref:System.Windows.Media.MediaPlayer> 및 <xref:System.Windows.Media.VideoDrawing>만 사용하는 것이고, 두 번째 방법은 자체적인 <xref:System.Windows.Media.MediaTimeline>을 만들어서 <xref:System.Windows.Media.MediaPlayer> 및 <xref:System.Windows.Media.VideoDrawing>과 함께 사용하는 것입니다.  
  
> [!NOTE]
>  응용 프로그램으로 미디어를 배포하는 경우 이미지와 달리 미디어 파일은 프로젝트 리소스로 사용할 수 없습니다.  대신 프로젝트 파일에서 미디어 형식을 `Content`로 설정하고 `CopyToOutputDirectory`를 `PreserveNewest` 또는 `Always`로 설정해야 합니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Media.VideoDrawing> 및 <xref:System.Windows.Media.MediaPlayer>를 사용하여 비디오 파일을 한 번 재생합니다.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 미디어에 대한 추가적인 타이밍 제어권을 얻으려면 <xref:System.Windows.Media.MediaTimeline>을 <xref:System.Windows.Media.MediaPlayer> 및 <xref:System.Windows.Media.VideoDrawing> 개체와 함께 사용하십시오.  <xref:System.Windows.Media.MediaTimeline>을 통해 비디오의 반복 여부를 지정할 수 있습니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Media.MediaPlayer> 및 <xref:System.Windows.Media.VideoDrawing> 개체에 <xref:System.Windows.Media.MediaTimeline>을 사용하여 비디오를 반복 재생합니다.  
  
 [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline)]  
  
 <xref:System.Windows.Media.MediaTimeline>을 사용할 때는 <xref:System.Windows.Media.MediaClock>의 <xref:System.Windows.Media.Animation.Clock.Controller%2A> 속성에서 반환된 대화형 <xref:System.Windows.Media.Animation.ClockController>를 사용하여 <xref:System.Windows.Media.MediaPlayer>의 대화형 메서드 대신 미디어 재생을 제어합니다.  
  
## 참고 항목  
 <xref:System.Windows.Media.VideoDrawing>   
 [Drawing 개체 개요](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)