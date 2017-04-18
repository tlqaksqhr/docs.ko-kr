---
title: "방법: 키 프레임을 사용하여 3차원 회전에 애니메이션 효과 주기 | Microsoft Docs"
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
  - "3차원 변환, 애니메이션 적용, 키 프레임으로(Rotation3DAnimation)"
  - "애니메이션, 3차원 변환, 키 프레임으로(Rotation3DAnimation)"
  - "키 프레임, Rotation3DAnimation"
ms.assetid: 6f671b95-7f30-4836-9a4f-aeb7dc30121f
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: 키 프레임을 사용하여 3차원 회전에 애니메이션 효과 주기
다음 예제에서 <xref:System.Windows.Media.Animation.Rotation3DAnimationUsingKeyFrames>는 3D 개체의 회전 축이 "비틀거리면서" 3D 개체가 회전하는 애니메이션 효과를 주는 데 사용됩니다.  이 애니메이션에서는 다음 키 프레임을 사용합니다.  
  
1.  <xref:System.Windows.Media.Animation.LinearRotation3DKeyFrame>은 값 사이에 부드러운 선형 보간을 만드는 데 사용됩니다.  
  
2.  <xref:System.Windows.Media.Animation.DiscreteRotation3DKeyFrame>은 값 간에 급격한 "이동"을 만드는 데 사용됩니다\(보간 없음\).  
  
3.  <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame>은 <xref:System.Windows.Media.Animation.SplineRotation3DKeyFrame.KeySpline%2A> 속성에 따라 값 간에 가변 전환을 만드는 데 사용됩니다.  아래 예제에서 이 애니메이션 부분은 처음에는 서서히 시작되다가 시간 세그먼트의 끝 부분으로 갈수록 빠르게 진행됩니다.  
  
## 예제  
 [!code-xml[Animation3DGallery_snip#Rotation3DAnimationUsingKeyFramesExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Rotation3DAnimationUsingKeyFramesExample.xaml#rotation3danimationusingkeyframesexamplewholepage)]  
  
## 참고 항목  
 [3차원 그래픽 개요](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)   
 [키 프레임 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [Storyboard를 사용하여 3차원 회전에 애니메이션 효과 주기](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-storyboards.md)   
 [Rotation3DAnimation을 사용하여 3차원 회전에 애니메이션 효과 주기](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-rotation3danimation.md)   
 [4원수를 사용하여 3차원 회전에 애니메이션 효과 주기](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-3-d-rotation-using-quaternions.md)   
 [키 프레임을 사용하여 3차원 회전에 애니메이션 효과 주기\(QuaternionAnimationUsingKeyFrames\)](../../../../docs/framework/wpf/graphics-multimedia/animate-a-3-d-rotation-quaternionanimationusingkeyframes.md)