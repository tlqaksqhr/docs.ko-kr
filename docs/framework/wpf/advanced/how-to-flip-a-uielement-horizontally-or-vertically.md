---
title: "방법: UIElement를 좌우 또는 상하 대칭 이동 | Microsoft Docs"
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
  - "UIElement 대칭 이동"
  - "UIElements, 대칭 이동"
ms.assetid: 02c6730f-65c0-40d5-a553-4cb663721882
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# 방법: UIElement를 좌우 또는 상하 대칭 이동
이 예제에서는 <xref:System.Windows.Media.ScaleTransform>을 사용하여 <xref:System.Windows.UIElement>를 상하 또는 좌우로 대칭 이동하는 방법을 보여 줍니다.  이 예제에서는 <xref:System.Windows.UIElement> 형식인 <xref:System.Windows.Controls.Button> 컨트롤의 <xref:System.Windows.UIElement.RenderTransform%2A> 속성에 <xref:System.Windows.Media.ScaleTransform>을 적용하여 이 컨트롤을 대칭 이동합니다.  
  
## 예제  
 다음 그림에서는 대칭 이동할 단추를 보여 줍니다.  
  
 ![변환이 없는 단추](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonflipbeforeflip.png "graphicsmm\_buttonflipbeforeflip")  
대칭 이동할 UIElement  
  
 다음은 단추를 만드는 코드를 보여 줍니다.  
  
 [!code-xml[Transforms_snip#GraphicsMMButtonWithoutFlip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmbuttonwithoutflip)]  
  
## 예제  
 단추를 좌우 대칭 이동하려면 <xref:System.Windows.Media.ScaleTransform>을 만들고 해당 <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> 속성을 \-1로 설정합니다.  단추의 <xref:System.Windows.UIElement.RenderTransform%2A> 속성에 <xref:System.Windows.Media.ScaleTransform>을 적용합니다.  
  
 [!code-xml[Transforms_snip#GraphicsMMFlipButtonExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmflipbuttonexample1)]  
  
 ![&#40;0,0&#41;을 중심으로 가로 대칭 이동된 단추](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonfliphorizontalflip-displaced.png "graphicsmm\_buttonfliphorizontalflip\_displaced")  
ScaleTransform을 적용한 후의 단추  
  
## 예제  
 이전 그림에서 볼 수 있듯이 단추가 좌우로 대칭되는 동시에 이동되었습니다.  이는 단추를 왼쪽 모퉁이를 기준으로 대칭 이동했기 때문입니다.  단추를 제자리에서 대칭 이동하려면 <xref:System.Windows.Media.ScaleTransform>을 모퉁이가 아니라 가운데에 적용해야 합니다.  단추의 <xref:System.Windows.UIElement.RenderTransformOrigin%2A> 속성을 0.5, 0.5로 설정하면 손쉽게 단추 가운데에 <xref:System.Windows.Media.ScaleTransform>을 적용할 수 있습니다.  
  
 [!code-xml[Transforms_snip#GraphicsMMFlipButtonExample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmflipbuttonexample2)]  
  
 ![가운데를 중심으로 가로 대칭 이동된 단추](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonfliphorizontalflip-inplace.png "graphicsmm\_buttonfliphorizontalflip\_inplace")  
RenderTransformOrigin이 0.5, 0.5인 단추  
  
## 예제  
 단추를 상하 대칭 이동하려면 <xref:System.Windows.Media.ScaleTransform> 개체의 <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> 속성 대신 <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> 속성을 설정합니다.  
  
 [!code-xml[Transforms_snip#GraphicsMMVerticalFlipButtonExample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmverticalflipbuttonexample2)]  
  
 ![가운데를 중심으로 세로 대칭 이동된 단추](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonflipverticalflip-inplace.png "graphicsmm\_buttonflipverticalflip\_inplace")  
상하 대칭 이동한 단추  
  
## 참고 항목  
 [Transform 개요](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)