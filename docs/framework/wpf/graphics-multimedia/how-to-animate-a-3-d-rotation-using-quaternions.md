---
title: "방법: 4원수를 사용하여 3차원 회전에 애니메이션 효과 주기 | Microsoft Docs"
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
  - "3차원 변환, 애니메이션 적용, 4원수로"
  - "애니메이션, 3차원 변환, 4원수로"
  - "4원수"
ms.assetid: adca9cb1-066b-4de8-abbb-6b4007579ee7
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# 방법: 4원수를 사용하여 3차원 회전에 애니메이션 효과 주기
이 예제에서는 4원수를 사용하여 3차원 개체 회전에 애니메이션 효과를 주는 방법을 보여 줍니다.  
  
 아래 코드에서는 <xref:System.Windows.Media.Media3D.RotateTransform3D>의 <xref:System.Windows.Media.Media3D.RotateTransform3D.Rotation%2A> 속성에 대한 값으로 사용되는 <xref:System.Windows.Media.Media3D.QuaternionRotation3D>를 보여 줍니다.  
  
 [!code-xml[Animation3DGallery_snip#QuaternionAnimationExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline1)]  
  
 아래의 코드를 사용하여 <xref:System.Windows.Media.Animation.Storyboard> 내의 <xref:System.Windows.Media.Animation.QuaternionAnimation>으로 이 <xref:System.Windows.Media.Media3D.QuaternionRotation3D>에 애니메이션 효과를 줍니다.  
  
 [!code-xml[Animation3DGallery_snip#QuaternionAnimationExampleInline2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexampleinline2)]  
  
## 예제  
 다음 코드에서는 전체 샘플을 보여 줍니다.  
  
 [!code-xml[Animation3DGallery_snip#QuaternionAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/QuaternionAnimationExample.xaml#quaternionanimationexamplewholepage)]  
  
## 참고 항목  
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [3차원 장면 만들기](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)   
 [3차원 그래픽 개요](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)   
 [Transform 개요](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)   
 [Storyboard를 사용하여 3차원 회전에 애니메이션 효과 주기](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-storyboards.md)   
 [Rotation3DAnimation을 사용하여 3차원 회전에 애니메이션 효과 주기](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-rotation3danimation.md)