---
title: "방법: 3차원 개체의 앞과 뒤에 Material 적용 | Microsoft Docs"
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
  - "3차원 개체, Material 클래스 적용"
  - "클래스, 재질"
  - "Material 클래스, 3차원 개체의 양쪽에 모두 적용"
ms.assetid: d93c8ad6-4939-4d29-9544-4d16d98093c1
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# 방법: 3차원 개체의 앞과 뒤에 Material 적용
다음 예제에서는 3차원 개체의 앞과 뒤에 <xref:System.Windows.Media.Media3D.Material>을 적용하고 개체에 애니메이션 효과를 주어 개체의 양쪽 측면을 표시하는 방법을 보여 줍니다.  <xref:System.Windows.Media.Media3D.GeometryModel3D>의 <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> 속성은 빨간색 <xref:System.Windows.Media.Brush>를 개체의 앞면에 적용하는 데 사용되고 <xref:System.Windows.Media.Media3D.GeometryModel3D>의 <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> 속성은 파란색 <xref:System.Windows.Media.Brush>를 개체의 뒷면에 적용하는 데 사용됩니다.  아래의 코드에서는 재질을 개체에 적용하는 방법을 보여 줍니다.  
  
 [!code-xml[Animation3DGallery_snip#BackMaterialAnimationExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexampleinline1)]  
  
## 예제  
 다음 코드에서는 전체 샘플을 보여 줍니다.  
  
 [!code-xml[Animation3DGallery_snip#BackMaterialAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexamplewholepage)]  
  
## 참고 항목  
 [3차원 장면 만들기](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)   
 [3차원 그래픽 개요](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)   
 [3차원 장면의 Material 속성에 애니메이션 효과 주기](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-material-properties-in-a-3-d-scene.md)   
 [3차원 개체에 EmissiveMaterial 적용](../../../../docs/framework/wpf/graphics-multimedia/how-to-apply-emissive-material-to-a-3-d-object.md)