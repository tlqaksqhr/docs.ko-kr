---
title: "방법: 사용자 이벤트를 사용하여 미디어 재생 트리거"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- synchronizing media playback with events [WPF]
- playback of media [WPF], synchronizing with events
- media [WPF], synchronizing playback with events
- multimedia [WPF], synchronizing media playback with events
ms.assetid: c4dbe632-6e7f-4d7f-9df5-98737a758bc3
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 39d50fc23be4a5cdf4df90cd6fa96466acc738aa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-trigger-media-playback-with-a-user-event"></a><span data-ttu-id="1c2c7-102">방법: 사용자 이벤트를 사용하여 미디어 재생 트리거</span><span class="sxs-lookup"><span data-stu-id="1c2c7-102">How to: Trigger Media Playback with a User Event</span></span>
<span data-ttu-id="1c2c7-103">이 예제에서는 미디어 재생을 이벤트와 동기화하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1c2c7-103">This example shows how to synchronize media playback with an event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1c2c7-104">예제</span><span class="sxs-lookup"><span data-stu-id="1c2c7-104">Example</span></span>  
 <span data-ttu-id="1c2c7-105">다음 예제에서는 <xref:System.Windows.Controls.MediaElement> 제어 및 <xref:System.Windows.Media.MediaTimeline> 소리 재생 하는 사용자가 클릭할 때 발생 하는 클래스는 <xref:System.Windows.Controls.Button>합니다.</span><span class="sxs-lookup"><span data-stu-id="1c2c7-105">The following example uses the <xref:System.Windows.Controls.MediaElement> control and the <xref:System.Windows.Media.MediaTimeline> class to play a sound that occurs when the user clicks a <xref:System.Windows.Controls.Button>.</span></span>  
  
 [!code-xaml[MediaGallery_snippet#SoundFromUserEventExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snippet/CSharp/SoundFromUserEventExample.xaml#soundfromusereventexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="1c2c7-106">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1c2c7-106">See Also</span></span>  
 <xref:System.Windows.Controls.MediaElement>  
 <xref:System.Windows.Media.MediaTimeline>  
 <xref:System.Windows.EventTrigger.RoutedEvent%2A>  
 <xref:System.Windows.Media.Animation.Storyboard>  
 [<span data-ttu-id="1c2c7-107">방법 항목</span><span class="sxs-lookup"><span data-stu-id="1c2c7-107">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/audio-and-video-how-to-topics.md)  
 [<span data-ttu-id="1c2c7-108">그래픽 및 멀티미디어</span><span class="sxs-lookup"><span data-stu-id="1c2c7-108">Graphics and Multimedia</span></span>](../../../../docs/framework/wpf/graphics-multimedia/index.md)
