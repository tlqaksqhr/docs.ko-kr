---
title: "GDI+에서 그리기 화면 제한 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "클리핑, GDI+ 사용"
  - "GDI+, 클리핑"
  - "GDI+, 그리기 화면 제한"
ms.assetid: 8b5f71d9-d2f0-4540-9c41-740f90fd4c26
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# GDI+에서 그리기 화면 제한
클리핑은 그리기를 특정 사각형 또는 영역으로 제한합니다.  다음 그림은 문자열 "Hello"가 하트 모양의 영역에 클리핑된 것을 보여 줍니다.  
  
 ![제한된 그리기 화면](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art30.png "AboutGdip02\_Art30")  
  
## 영역을 사용하여 클리핑  
 영역은 경로에서 생성될 수 있고 경로는 문자열의 윤곽을 포함할 수 있기 때문에 윤곽이 있는 텍스트를 클리핑에 사용할 수 있습니다.  다음 그림은 텍스트 문자열의 내부에 클리핑된 동심 타원 집합을 보여 줍니다.  
  
 ![제한된 그리기 화면](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art31.png "AboutGdip02\_Art31")  
  
 클리핑을 사용하여 그림을 그리려면 <xref:System.Drawing.Graphics> 개체를 만들고 <xref:System.Drawing.Graphics.Clip%2A> 속성을 설정한 다음 같은 <xref:System.Drawing.Graphics> 개체의 그리기 메서드를 호출합니다.  
  
 [!code-csharp[LinesCurvesAndShapes#91](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#91)]
 [!code-vb[LinesCurvesAndShapes#91](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#91)]  
  
## 참고 항목  
 <xref:System.Drawing.Graphics?displayProperty=fullName>   
 <xref:System.Drawing.Region?displayProperty=fullName>   
 [선, 곡선 및 도형](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)   
 [영역 사용](../../../../docs/framework/winforms/advanced/using-regions.md)