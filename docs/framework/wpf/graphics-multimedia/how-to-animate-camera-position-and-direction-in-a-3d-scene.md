---
title: "방법: 3차원 장면에서 카메라 위치 및 방향에 애니메이션 효과 주기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], camera position in 3-D scenes
- camera direction [WPF], animating in 3-D scenes
- 3-D scenes [WPF], animating camera position
- 3-D scenes [WPF], animating camera direction
- camera position [WPF], animating in 3-D scenes
- animation [WPF], camera direction in 3-D scenes
ms.assetid: 480224b7-a5e5-4165-ba7f-ef760ddff94a
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 790260f974dcb0be398af202cc7156fc91efed91
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-camera-position-and-direction-in-a-3d-scene"></a>방법: 3차원 장면에서 카메라 위치 및 방향에 애니메이션 효과 주기
다음 예제에서는 카메라의 위치 및 3D 장면에 가리키는지 방향에 애니메이션을 적용 하는 방법을 보여 줍니다. 사용 하 여 이렇게 <xref:System.Windows.Media.Animation.Point3DAnimation> 및 <xref:System.Windows.Media.Animation.Vector3DAnimation> 애니메이션 효과를 주는 <xref:System.Windows.Media.Media3D.ProjectionCamera.Position%2A> 및 <xref:System.Windows.Media.Media3D.ProjectionCamera.LookDirection%2A> 각각의 속성은 <xref:System.Windows.Media.Media3D.PerspectiveCamera>합니다. 이벤트에 대 한 응답으로 장면의 보는 보기를 변경 하려면 다음과 같이 애니메이션을 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 [!code-xaml[Animation3DGallery_snip#PointVector3DAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/PointVector3DAnimationExample.xaml#pointvector3danimationexamplewholepage)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Media.Animation.Vector3DAnimation>  
 <xref:System.Windows.Media.Animation.Point3DAnimation>  
 [키 프레임을 사용하여 카메라 위치 및 방향에 애니메이션 효과 주기](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-camera-position-and-direction-using-key-frames.md)  
 [3차원 그래픽 개요](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
