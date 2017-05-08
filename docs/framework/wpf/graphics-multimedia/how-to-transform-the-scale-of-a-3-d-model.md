---
title: "방법: 3차원 모델의 배율 변환 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "3차원 개체, 배율"
  - "배율, 3차원 개체"
ms.assetid: f3fdfe33-f7dc-44b0-84a5-e43b89947f35
caps.latest.revision: 3
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 3
---
# 방법: 3차원 모델의 배율 변환
이 예제에서는 3차원 개체의 배율을 조정하는 방법을 보여 줍니다.  3차원 개체의 배율을 조정하려면 <xref:System.Windows.Media.Media3D.ScaleTransform3D>를 사용합니다.  <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A>, <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A> 및 <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleZ%2A> 속성은 사용자가 지정한 인수에 따라 요소의 크기를 조정합니다.  예를 들어 <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A> 값 1.5는 개체를 원래 너비의 150%로 늘립니다.  <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A> 값 0.5는 개체의 높이를 50%까지 줄입니다.  아래의 코드에서는 <xref:System.Windows.Media.Media3D.GeometryModel3D>에 대한 변환으로 <xref:System.Windows.Media.Media3D.ScaleTransform3D>를 사용하는 방법을 보여 줍니다.  
  
 [!code-xml[3DGallery_snip#ScaleTransform3DExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexampleinline1)]  
  
## 예제  
 다음 코드에서는 전체 샘플을 보여 줍니다.  
  
 [!code-xml[3DGallery_snip#ScaleTransform3DExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexamplewholepage)]  
  
## 참고 항목  
 [3차원 변환에 애니메이션 효과 주기](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-3-d-translations.md)   
 [3차원 장면 만들기](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)   
 [3차원 그래픽 개요](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)