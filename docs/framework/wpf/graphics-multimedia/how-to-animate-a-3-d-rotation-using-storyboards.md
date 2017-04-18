---
title: "방법: Storyboard를 사용하여 3차원 회전에 애니메이션 효과 주기 | Microsoft Docs"
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
  - "3차원 변환, 애니메이션 적용, Storyboard로"
  - "애니메이션, 3차원 변환, Storyboard로"
  - "스토리보드"
ms.assetid: 1020e44e-e21e-49a8-be53-53cbc1910e83
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 방법: Storyboard를 사용하여 3차원 회전에 애니메이션 효과 주기
다음 예제에서는 <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> 개체의 <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> 및 <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> 속성에 애니메이션 효과를 주어 3D 개체가 "비틀거리면서" 회전하도록 만드는 방법을 보여 줍니다.  이 <xref:System.Windows.Media.Media3D.AxisAngleRotation3D> 개체는 3D 개체의 회전 변환을 지정하므로 해당 속성에 애니메이션 효과를 주면 원하는 회전 효과가 만들어집니다.  Storyboard 내에서는 <xref:System.Windows.Media.Animation.DoubleAnimation>을 사용하여 <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Angle%2A> 속성에 애니메이션 효과를 주고 <xref:System.Windows.Media.Animation.Vector3DAnimation>을 사용하여 <xref:System.Windows.Media.Media3D.AxisAngleRotation3D.Axis%2A> 속성에 애니메이션 효과를 줍니다.  
  
## 예제  
 [!code-xml[Animation3DGallery_snip#Rotate3DUsingAxisAngleRotation3DExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotat3DUsingAxisAngleRotation3DExample.xaml#rotate3dusingaxisanglerotation3dexamplewholepage)]  
  
## 참고 항목  
 [Rotation3DAnimation을 사용하여 3차원 회전에 애니메이션 효과 주기](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-rotation3danimation.md)   
 [키 프레임을 사용하여 3차원 회전에 애니메이션 효과 주기\(Rotation3DAnimationUsingKeyFrames\)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-key-frames.md)   
 [3차원 그래픽 개요](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)   
 [Storyboard 개요](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)