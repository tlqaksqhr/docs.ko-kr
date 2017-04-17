---
title: "방법: 사용자 이벤트를 사용하여 미디어 재생 트리거 | Microsoft Docs"
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
  - "미디어 재생을 이벤트에 동기화"
  - "이벤트와 함께 동기화 미디어 재생"
  - "미디어 재생을 이벤트에 동기화 합니다."
  - "이벤트를 사용 하 여 멀티미디어, 동기화 미디어 재생"
ms.assetid: c4dbe632-6e7f-4d7f-9df5-98737a758bc3
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# 방법: 사용자 이벤트를 사용하여 미디어 재생 트리거
이 예제에서는 미디어 재생을 이벤트와 동기화 하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 <xref:System.Windows.Controls.MediaElement> 컨트롤 및 <xref:System.Windows.Media.MediaTimeline> 를 클릭할 때 발생 하는 소리를 재생 하는 클래스는 <xref:System.Windows.Controls.Button>합니다.  
  
 [!code-xml[MediaGallery_snippet#SoundFromUserEventExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snippet/CSharp/SoundFromUserEventExample.xaml#soundfromusereventexamplewholepage)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Controls.MediaElement>   
 <xref:System.Windows.Media.MediaTimeline>   
 <xref:System.Windows.EventTrigger.RoutedEvent%2A>   
 <xref:System.Windows.Media.Animation.Storyboard>   
 [방법 도움말 항목](../../../../docs/framework/wpf/graphics-multimedia/audio-and-video-how-to-topics.md)   
 [그래픽 및 멀티미디어](../../../../docs/framework/wpf/graphics-multimedia/index.md)