---
title: "방법: 개체에 다중 변환 적용 | Microsoft Docs"
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
  - "그래픽, Transform 개체 그룹화"
  - "Transform 개체 그룹화"
  - "Transform 개체, 그룹화"
  - "TransformGroup"
ms.assetid: 98cd1921-12bc-4bf5-8193-529228fb7402
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: 개체에 다중 변환 적용
이 예제에서는 <xref:System.Windows.Media.TransformGroup>을 사용하여 둘 이상의 <xref:System.Windows.Media.Transform> 개체를 단일 복합 <xref:System.Windows.Media.Transform>으로 그룹화하는 방법을 보여 줍니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Media.TransformGroup>을 사용하여 <xref:System.Windows.Media.ScaleTransform> 및 <xref:System.Windows.Media.RotateTransform>을 <xref:System.Windows.Controls.Button>에 적용합니다.  
  
 [!code-xml[Transforms_snip#MultipleTransformExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/MultipleTransformExample.xaml#multipletransformexamplewholepage)]  
  
 [!code-csharp[Transforms_Procedural_snip#MultipleTransformsCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/MultipleTransformsExample.cs#multipletransformscodeexamplewholepage)]
 [!code-vb[Transforms_Procedural_snip#MultipleTransformsCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/MultipleTransformsExample.vb#multipletransformscodeexamplewholepage)]  
  
## 참고 항목  
 <xref:System.Windows.UIElement.RenderTransform%2A>   
 <xref:System.Windows.Media.TransformGroup>   
 [Transform 개요](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)   
 [2\-D Transforms 샘플](http://go.microsoft.com/fwlink/?LinkID=158252)