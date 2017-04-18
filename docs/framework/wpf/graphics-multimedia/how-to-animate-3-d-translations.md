---
title: "방법: 3차원 변환에 애니메이션 효과 주기 | Microsoft Docs"
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
  - "3차원 변환, 애니메이션 적용"
  - "애니메이션, 3차원 변환"
ms.assetid: d4eece1f-0cd2-4a2c-8370-293354c380e4
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: 3차원 변환에 애니메이션 효과 주기
이 항목에서는 [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] 모델에 설정된 변환 변형에 애니메이션 효과를 주는 방법을 보여 줍니다.  
  
 아래의 코드에서는 <xref:System.Windows.Media.Media3D.TranslateTransform3D> 개체를 <xref:System.Windows.Media.Media3D.GeometryModel3D>의 <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> 속성에 적용하는 방법을 보여 줍니다.  
  
 [!code-xml[Animation3DGallery_snip#Translation3DAnimationInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationinline1)]  
  
 아래의 코드를 사용하여 이 <xref:System.Windows.Media.Media3D.TranslateTransform3D> 개체의 <xref:System.Windows.Media.Media3D.TranslateTransform3D.OffsetX%2A> 속성에 애니메이션 효과를 줍니다.  
  
 [!code-xml[Animation3DGallery_snip#Translation3DAnimationInline2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationinline2)]  
  
## 예제  
 다음 코드에서는 전체 샘플을 보여 줍니다.  
  
 [!code-xml[Animation3DGallery_snip#Translation3DAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationexamplewholepage)]  
  
## 참고 항목  
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [3차원 장면 만들기](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)   
 [3차원 그래픽 개요](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)   
 [Transform 개요](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)