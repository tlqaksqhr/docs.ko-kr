---
title: "방법: 3차원 장면에서 카메라 위치 및 방향에 애니메이션 효과 주기 | Microsoft Docs"
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
  - "3차원 장면, 카메라 방향에 애니메이션 적용"
  - "3차원 장면, 카메라 위치에 애니메이션 적용"
  - "애니메이션, 3차원 장면의 카메라 방향"
  - "애니메이션, 3차원 장면의 카메라 위치"
  - "카메라 방향, 3차원 장면에 애니메이션 적용"
  - "카메라 위치, 3차원 장면에 애니메이션 적용"
ms.assetid: 480224b7-a5e5-4165-ba7f-ef760ddff94a
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# 방법: 3차원 장면에서 카메라 위치 및 방향에 애니메이션 효과 주기
다음 예제에서는 3차원 장면에서 카메라의 위치 및 카메라가 가리키고 있는 방향에 애니메이션 효과를 주는 방법을 보여 줍니다.  이 작업은 <xref:System.Windows.Media.Animation.Point3DAnimation> 및 <xref:System.Windows.Media.Animation.Vector3DAnimation>을 사용하여 <xref:System.Windows.Media.Media3D.PerspectiveCamera> 각각에 대한 <xref:System.Windows.Media.Media3D.ProjectionCamera.Position%2A> 및 <xref:System.Windows.Media.Media3D.ProjectionCamera.LookDirection%2A> 속성에 애니메이션 효과를 주면 가능합니다.  이와 같은 애니메이션을 사용하면 이벤트에 응답하여 보는 이의 장면 보기를 변경할 수 있습니다.  
  
## 예제  
 [!code-xml[Animation3DGallery_snip#PointVector3DAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/PointVector3DAnimationExample.xaml#pointvector3danimationexamplewholepage)]  
  
## 참고 항목  
 <xref:System.Windows.Media.Animation.Vector3DAnimation>   
 <xref:System.Windows.Media.Animation.Point3DAnimation>   
 [키 프레임을 사용하여 카메라 위치 및 방향에 애니메이션 효과 주기](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-camera-position-and-direction-using-key-frames.md)   
 [3차원 그래픽 개요](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)