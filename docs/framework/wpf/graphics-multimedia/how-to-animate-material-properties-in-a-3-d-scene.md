---
title: "방법: 3차원 장면의 Material 속성에 애니메이션 효과 주기 | Microsoft Docs"
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
  - "3차원 장면, Material 속성에 애니메이션 적용"
  - "애니메이션, 3차원 장면의 Material 속성"
  - "Material 속성, 3차원 장면에 애니메이션 적용"
ms.assetid: 229fd6eb-7401-4992-b0c9-8b28de230c0f
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: 3차원 장면의 Material 속성에 애니메이션 효과 주기
이 예제에서는 [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] 모델에 적용된 <xref:System.Windows.Media.Media3D.Material>의 <xref:System.Windows.Media.Brush.Opacity%2A> 속성에 애니메이션 효과를 주는 방법을 보여 줍니다.  
  
 다음 코드 예제에서는 3D 개체에 적용된 <xref:System.Windows.Media.Media3D.Material>로 사용되는 <xref:System.Windows.Media.LinearGradientBrush>를 정의합니다.  
  
 [!code-xml[Animation3DGallery_snip#AnimateMaterialExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexampleinline1)]  
  
 아래의 코드 예제를 사용하여 이 <xref:System.Windows.Media.LinearGradientBrush>의 <xref:System.Windows.Media.Brush.Opacity%2A> 속성에 애니메이션 효과를 줍니다.  
  
 [!code-xml[Animation3DGallery_snip#AnimateMaterialExampleInline2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexampleinline2)]  
  
## 예제  
 다음 코드에서는 전체 샘플을 보여 줍니다.  
  
 [!code-xml[Animation3DGallery_snip#AnimateMaterialExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexamplewholepage)]  
  
## 참고 항목  
 [3차원 장면 만들기](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)   
 [3차원 그래픽 개요](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)