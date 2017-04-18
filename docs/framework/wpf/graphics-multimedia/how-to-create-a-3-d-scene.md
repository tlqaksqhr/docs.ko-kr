---
title: "방법: 3차원 장면 만들기 | Microsoft Docs"
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
  - "3차원 장면"
  - "만들기, 3차원 장면"
  - "장면, 3차원"
ms.assetid: adb4a598-71a2-4dd5-b677-ea3fc11b78b2
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# 방법: 3차원 장면 만들기
이 예제에서는 회전된 평면 용지처럼 보이는 3차원 개체를 만드는 방법을 보여 줍니다.  이러한 간단한 3차원 장면을 만드는 데 다음 구성 요소와 함께 <xref:System.Windows.Controls.Viewport3D>가 사용됩니다.  
  
-   카메라는 <xref:System.Windows.Media.Media3D.PerspectiveCamera>를 사용하여 만듭니다.  카메라는 3차원 장면에서 볼 수 있는 부분을 지정합니다.  
  
-   망상 조직은 <xref:System.Windows.Media.Media3D.GeometryModel3D>의 <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> 속성을 사용하여 3차원 개체의 도형\(용지\)을 지정하기 위해 만듭니다.  
  
-   재질은 <xref:System.Windows.Media.Media3D.GeometryModel3D>의 <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> 속성을 사용하여 개체의 표면\(이 샘플에서는 선형 그라데이션\)에 표시되도록 지정합니다.  
  
-   조명은 <xref:System.Windows.Media.Media3D.DirectionalLight>를 사용하여 개체에서 빛나도록 만듭니다.  
  
## 예제  
 아래 코드에서는 XAML로 3차원 장면을 만드는 방법을 보여 줍니다.  
  
 [!code-xml[3DGallery_snip#Basic3DShapeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/Basic3DShapeExample.xaml#basic3dshapeexamplewholepage)]  
  
## 예제  
 아래 코드에서는 프로시저 코드로 같은 3차원 장면을 만드는 방법을 보여 줍니다.  
  
 [!code-csharp[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Basic3DShapeExample.cs#basic3dshapecodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/basic3dshapeexample.vb#basic3dshapecodeexamplewholepage)]  
  
## 참고 항목  
 [3차원 그래픽 개요](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)