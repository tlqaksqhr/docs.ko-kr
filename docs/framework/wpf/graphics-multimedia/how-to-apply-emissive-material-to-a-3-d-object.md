---
title: "방법: 3차원 개체에 EmissiveMaterial 적용 | Microsoft Docs"
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
  - "3차원 개체, EmissiveMaterial 적용"
  - "EmissiveMaterial, 3차원 개체에 적용"
ms.assetid: fd442cc2-5adc-487a-ba70-e45ed54bb3b4
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# 방법: 3차원 개체에 EmissiveMaterial 적용
다음 예제에서는 <xref:System.Windows.Media.Media3D.EmissiveMaterial>을 사용하여 기존 Material에 EmissiveMaterial의 브러시와 같은 색을 추가하는 방법을 보여 줍니다.  아래 코드에서는 <xref:System.Windows.Media.Media3D.DiffuseMaterial>과 <xref:System.Windows.Media.Media3D.EmissiveMaterial>을 함께 적용하여 DiffuseMaterial의 모양에 파란색을 추가합니다.  
  
 [!code-xml[3DGallery_snip#EmmisiveMaterialAnimationExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/EmissiveMaterialExample.xaml#emmisivematerialanimationexampleinline1)]  
  
 프로시저 코드  
  
 [!code-csharp[3DGallery_procedural_snip#EmissiveMaterialCodeExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/EmissiveMaterialExample.cs#emissivematerialcodeexampleinline1)]
 [!code-vb[3DGallery_procedural_snip#EmissiveMaterialCodeExampleInline1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/emissivematerialexample.vb#emissivematerialcodeexampleinline1)]  
  
## 예제  
 다음은 XAML의 전체 샘플 코드입니다.  
  
 [!code-xml[3DGallery_snip#EmissiveMaterialExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/EmissiveMaterialExample.xaml#emissivematerialexamplewholepage)]  
  
## 예제  
 다음은 프로시저 코드의 전체 샘플입니다.  
  
 [!code-csharp[3DGallery_procedural_snip#EmissiveMaterialCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/EmissiveMaterialExample.cs#emissivematerialcodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#EmissiveMaterialCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/emissivematerialexample.vb#emissivematerialcodeexamplewholepage)]  
  
## 참고 항목  
 [3차원 장면 만들기](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)   
 [3차원 그래픽 개요](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)   
 [3차원 장면의 Material 속성에 애니메이션 효과 주기](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-material-properties-in-a-3-d-scene.md)   
 [3차원 개체의 앞과 뒤에 Material 적용](../../../../docs/framework/wpf/graphics-multimedia/how-to-apply-material-to-the-front-and-back-of-a-3-d-object.md)