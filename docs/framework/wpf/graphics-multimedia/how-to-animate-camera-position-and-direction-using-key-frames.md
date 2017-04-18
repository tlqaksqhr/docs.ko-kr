---
title: "방법: 키 프레임을 사용하여 카메라 위치 및 방향에 애니메이션 효과 주기 | Microsoft Docs"
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
  - "애니메이션, 키 프레임으로 카메라 방향"
  - "애니메이션, 키 프레임으로 카메라 위치"
  - "카메라 방향, 키 프레임으로 애니메이션 적용"
  - "카메라 위치, 키 프레임으로 애니메이션 적용"
  - "키 프레임, 카메라 방향에 애니메이션 적용"
  - "키 프레임, 카메라 위치에 애니메이션 적용"
ms.assetid: 5753024e-0057-454d-947f-43ea686879c7
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# 방법: 키 프레임을 사용하여 카메라 위치 및 방향에 애니메이션 효과 주기
다음 예제에서는 3차원 장면에서 <xref:System.Windows.Media.Media3D.PerspectiveCamera>의 위치에 애니메이션 효과를 주기 위해 <xref:System.Windows.Media.Animation.Point3DAnimationUsingKeyFrames>가 사용됩니다.  또한 3차원 장면에서 카메라가 가리키는 방향에 애니메이션 효과를 주기 위해 <xref:System.Windows.Media.Animation.Vector3DAnimationUsingKeyFrames>가 사용됩니다.  이러한 애니메이션은 둘 다 일련의 애니메이션 효과를 만드는 여러 키 프레임을 사용합니다.  
  
1.  <xref:System.Windows.Media.Animation.LinearPoint3DKeyFrame> 및 <xref:System.Windows.Media.Animation.LinearVector3DKeyFrame>은 값 사이에 부드러운 선형 보간을 만드는 데 사용됩니다.  
  
2.  <xref:System.Windows.Media.Animation.DiscretePoint3DKeyFrame> 및 <xref:System.Windows.Media.Animation.DiscreteVector3DKeyFrame>은 값 간에 급격한 "점프"를 만드는 데 사용되며 보간은 없습니다.  
  
3.  <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame> 및 <xref:System.Windows.Media.Animation.SplineVector3DKeyFrame>은 <xref:System.Windows.Media.Animation.SplinePoint3DKeyFrame.KeySpline%2A> 속성에 따라 값 간에 가변 전환을 만드는 데 사용됩니다.  아래 예제의 경우 애니메이션이 처음에는 서서히 시작되다가 시간 세그먼트의 끝 부분으로 갈수록 빠르게 진행됩니다.  
  
## 예제  
 [!code-xml[Animation3DGallery_snip#PointVector3DAnimationUsingKeyFramesExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/PointVector3DAnimationUsingKeyFramesExample.xaml#pointvector3danimationusingkeyframesexamplewholepage)]  
  
## 참고 항목  
 [3차원 장면에서 카메라 위치 및 방향에 애니메이션 효과 주기](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-camera-position-and-direction-in-a-3d-scene.md)   
 [3차원 그래픽 개요](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)