---
title: "방법: 3차원 모델에 그리기 적용 | Microsoft Docs"
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
  - "3차원 모델, 그리기 적용"
  - "그리기, 3차원 모델에 적용"
ms.assetid: 68357577-b7fc-446e-8be9-a8cc7df3a350
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# 방법: 3차원 모델에 그리기 적용
이 예제에서는 <xref:System.Windows.Media.DrawingBrush>를 [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] 모델에 적용된 <xref:System.Windows.Media.Media3D.Material>로 사용하는 방법을 보여 줍니다.  
  
 다음 코드에서는 <xref:System.Windows.Media.DrawingGroup>을 <xref:System.Windows.Media.DrawingBrush>의 콘텐츠로 정의합니다.  <xref:System.Windows.Media.DrawingBrush>는 [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] 평면에 적용된 <xref:System.Windows.Media.Media3D.DiffuseMaterial>의 <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> 속성으로 설정됩니다.  
  
 **참고:** 아래의 그림과 같은 복잡한 개체와 값을 다시 사용할 수 있고 코드를 단순화할 수 있는 리소스로 정의하는 것이 좋습니다.  자세한 내용은 [XAML 리소스](../../../../docs/framework/wpf/advanced/xaml-resources.md)를 참조하십시오.  
  
 [!code-xml[3DGallery_snip#ApplyDrawingToMaterialInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialinline1)]  
  
## 예제  
 다음 코드에서는 전체 샘플을 보여 줍니다.  
  
 [!code-xml[3DGallery_snip#ApplyDrawingToMaterialExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialexamplewholepage)]  
  
## 참고 항목  
 [XAML 리소스](../../../../docs/framework/wpf/advanced/xaml-resources.md)   
 [3차원 장면 만들기](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)   
 [Drawing 개체 개요](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)   
 [3차원 그래픽 개요](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)