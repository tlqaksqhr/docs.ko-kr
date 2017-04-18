---
title: "방법: Point4D 구조체가 서로 같은지 및 다른지 여부 테스트 | Microsoft Docs"
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
  - "같음, Point4D 구조체 테스트"
  - "같지 않음, Point4D 구조체 테스트"
  - "Point4D 구조체, 같음 테스트"
  - "Point4D 구조체, 같지 않음 테스트"
  - "테스트, Point4D 구조체의 같음 여부"
  - "테스트, Point4D 구조체의 같지 않음 여부"
ms.assetid: e004a67e-db7f-4af8-a31f-e6b2a44ccf34
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: Point4D 구조체가 서로 같은지 및 다른지 여부 테스트
이 예제에서는 <xref:System.Windows.Media.Media3D.Point4D> 구조체가 서로 같은지 및 다른지 여부를 테스트하는 방법을 보여 줍니다.  
  
 다음 코드에서는 <xref:System.Windows.Media.Media3D.Point4D> 같음 메서드를 사용하여 <xref:System.Windows.Media.Media3D.Point4D> 구조체가 서로 같은지 및 다른지를 테스트하는 방법을 보여 줍니다.  먼저 오버로드된 같음\(`==`\) 연산자를 사용하여 <xref:System.Windows.Media.Media3D.Point4D> 구조체가 같은지 여부를 테스트하고 오버로드된 같지 않음\(`!=`\) 연산자를 사용하여 구조체가 서로 다른지 여부를 테스트한 후 정적 <xref:System.Windows.Media.Media3D.Point4D.Equals%2A> 메서드를 사용하여 <xref:System.Windows.Media.Media3D.Point3D> 구조체와 <xref:System.Windows.Media.Media3D.Point4D> 구조체가 같은지 여부를 확인합니다.  
  
## 예제  
 [!code-csharp[3DGallery_procedural_snip#Point4DEqualityExample_csharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Misc3DOperationsExample.cs#point4dequalityexample_csharp)]  
  
## 참고 항목  
 <xref:System.Windows.Media.Media3D.Point4D.op_Equality%2A>   
 <xref:System.Windows.Media.Media3D.Point4D.op_Inequality%2A>   
 <xref:System.Windows.Media.Media3D.Point4D.Equals%2A>