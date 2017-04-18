---
title: "방법: MediaElement 제어(재생, 일시 중지, 정지, 볼륨 및 속도) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "미디어 재생 제어"
  - "미디어, 재생 제어"
  - "멀티미디어, 미디어 재생 제어"
  - "미디어 재생, 제어"
ms.assetid: 6885a730-e054-4c16-8c1e-ffe17b1f7c32
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: MediaElement 제어(재생, 일시 중지, 정지, 볼륨 및 속도)
다음 예제에서는 <xref:System.Windows.Controls.MediaElement>를 사용하여 미디어의 재생을 제어하는 방법을 보여 줍니다.  이 예제에서는 미디어 재생, 일시 중지, 정지 및 앞\/뒤로 건너뛰기 기능을 갖추고 있고 볼륨과 속도도 조정할 수 있는 간단한 미디어 플레이어를 만들어 봅니다.  
  
## 예제  
 다음은 UI를 만드는 코드입니다.  
  
> [!NOTE]
>  미디어를 대화형으로 중지, 일시 중지 및 재생할 수 있으려면 <xref:System.Windows.Controls.MediaElement>의 <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> 속성을 `Manual`로 설정해야 합니다.  
  
 [!code-xml[MediaGallery_snip#MediaElementExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml#mediaelementexamplewholepage)]  
  
## 예제  
 다음은 샘플 UI 컨트롤의 기능을 구현하는 코드입니다.  <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A> 및 <xref:System.Windows.Controls.MediaElement.Stop%2A> 메서드는 각각 미디어를 재생, 일시 중지 및 정지하는 데 사용됩니다.  <xref:System.Windows.Controls.MediaElement>의 <xref:System.Windows.Controls.MediaElement.Position%2A> 속성을 변경하면 미디어 내에서 건너뛸 수 있습니다.  마지막으로 <xref:System.Windows.Controls.MediaElement.Volume%2A> 및 <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> 속성은 미디어의 볼륨과 재생 속도를 조정하는 데 사용됩니다.  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaElementExample.xaml.cs#codebehindmediaelementexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml.vb#codebehindmediaelementexamplewholepage)]  
  
## 참고 항목  
 [Storyboard를 사용하여 MediaElement 제어](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-mediaelement-by-using-a-storyboard.md)