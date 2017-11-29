---
title: "방법: MediaElement 제어(재생, 일시 중지, 정지, 볼륨 및 속도)"
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
- playback of media [WPF], controlling
- controlling playback of media [WPF]
- multimedia [WPF], controlling playback of media
- media [WPF], controlling playback of
ms.assetid: 6885a730-e054-4c16-8c1e-ffe17b1f7c32
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7362c57afa3d5615ffaa0616823a954a2d577cfe
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-control-a-mediaelement-play-pause-stop-volume-and-speed"></a>방법: MediaElement 제어(재생, 일시 중지, 정지, 볼륨 및 속도)
다음 예제에서는 미디어를 사용 하 여의 재생을 제어 하는 <xref:System.Windows.Controls.MediaElement>합니다. 이 예에서는 재생, 일시 중지, 중지 및 미디어에서 앞뒤로 건너뛰려면으로 볼륨 및 속도 비율을 조정할 수 있도록 간단한 미디어 플레이어를 만듭니다.  
  
## <a name="example"></a>예제  
 아래 코드는 UI를 만듭니다.  
  
> [!NOTE]
>  <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> 속성 <xref:System.Windows.Controls.MediaElement> 으로 설정 되어 있어야 `Manual` 하기 위해 대화형으로 중지, 일시 중지 및 미디어를 재생 합니다.  
  
 [!code-xaml[MediaGallery_snip#MediaElementExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml#mediaelementexamplewholepage)]  
  
## <a name="example"></a>예제  
 아래 코드 샘플 UI 컨트롤의 기능을 구현합니다. <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>, 및 <xref:System.Windows.Controls.MediaElement.Stop%2A> 메서드는 각각 재생 일시 중지 하 고 미디어를 중지 하는 데 사용 됩니다. 변경의 <xref:System.Windows.Controls.MediaElement.Position%2A> 의 속성은 <xref:System.Windows.Controls.MediaElement> 미디어에서 건너뛸 수 있습니다. 마지막으로 <xref:System.Windows.Controls.MediaElement.Volume%2A> 및 <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> 속성 미디어의 볼륨 및 재생 속도 조정 하는 데 사용 됩니다.  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaElementExample.xaml.cs#codebehindmediaelementexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml.vb#codebehindmediaelementexamplewholepage)]  
  
## <a name="see-also"></a>참고 항목  
 [Storyboard를 사용하여 MediaElement 제어](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-mediaelement-by-using-a-storyboard.md)
