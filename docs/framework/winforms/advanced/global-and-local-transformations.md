---
title: "전역 및 지역 변환 | Microsoft Docs"
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
  - "매트릭스, 변환 사용"
  - "변환, global"
  - "변환, 로컬"
ms.assetid: b601d66d-d572-4f11-9d2e-92f0dc8893f3
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# 전역 및 지역 변환
전역 변환은 지정된 <xref:System.Drawing.Graphics> 개체에서 그리는 모든 항목에 적용되는 변환을 말하고  지역 변환은 그리려는 특정 항목에만 적용되는 변환을 말합니다.  
  
## 전역 변환  
 전역 변환을 만들려면 <xref:System.Drawing.Graphics> 개체를 만든 다음 이 개체의 <xref:System.Drawing.Graphics.Transform%2A> 속성을 조작합니다.  <xref:System.Drawing.Graphics.Transform%2A> 속성은 <xref:System.Drawing.Drawing2D.Matrix> 개체이므로 일련의 상관 변환을 포함할 수 있습니다.  <xref:System.Drawing.Graphics.Transform%2A> 속성에 저장된 변환을 전역 변환이라고 합니다.  <xref:System.Drawing.Graphics> 클래스는 복합 전역 변환을 작성할 수 있도록 <xref:System.Drawing.Graphics.MultiplyTransform%2A>, <xref:System.Drawing.Graphics.RotateTransform%2A>, <xref:System.Drawing.Graphics.ScaleTransform%2A> 및 <xref:System.Drawing.Graphics.TranslateTransform%2A> 메서드를 제공합니다.  다음 예제는 전역 변환을 만들기 전과 만든 후에 각각 한 번씩 타원을 그립니다.  이 변환에서는 y축 방향으로 0.5의 비율로 크기를 조정하고, x축 방향으로 50단위를 이동한 다음, 30도를 회전합니다.  
  
 [!code-csharp[System.Drawing.CoordinateSystems#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.CoordinateSystems#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#21)]  
  
 다음 그림은 변환과 관련된 매트릭스를 나타냅니다.  
  
 ![변환](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art14.gif "AboutGdip05\_art14")  
  
> [!NOTE]
>  위의 예제에서는 클라이언트 영역의 왼쪽 위에 있는 좌표계 원점을 중심으로 타원이 회전합니다.  이 경우 타원이 자체의 축을 중심으로 회전할 때와 다른 결과가 발생합니다.  
  
## 지역 변환  
 지역 변환은 그리려는 특정 항목에만 적용됩니다.  예를 들어 <xref:System.Drawing.Drawing2D.GraphicsPath> 개체에는 해당 경로의 데이터 요소를 변환할 수 있는 <xref:System.Drawing.Drawing2D.GraphicsPath.Transform%2A> 메서드가 있습니다.  다음 예제는 변환이 사용되지 않은 사각형과 회전 변환이 사용된 경로를 그립니다.  전역 변환은 사용되지 않는다고 가정합니다.  
  
 [!code-csharp[System.Drawing.CoordinateSystems#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.CoordinateSystems#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#22)]  
  
 전역 변환과 지역 변환을 함께 사용하면 다양한 효과를 낼 수 있습니다.  예를 들어, 전역 변환을 사용하여 좌표계를 새로 수정할 수 있으며, 지역 변환을 사용하여 새 좌표에 그려진 개체를 회전시키고 개체의 크기를 조정할 수 있습니다.  
  
 예를 들어, 클라이언트 공간의 왼쪽 가장자리에서 200픽셀, 클라이언트 공간의 위에서 150픽셀 떨어진 위치에 원점이 존재하는 좌표계를 만들려고 합니다.  또한, 측정 단위를 픽셀로 설정하고, x축이 오른쪽을 향하고 y축이 위쪽을 향하도록 설정하려고 합니다.  기본 좌표계에서는 y축이 아래쪽을 향하고 있으므로 가로축을 기준으로 반사를 수행해야 합니다.  다음 그림은 이러한 반사 매트릭스를 나타냅니다.  
  
 ![변환](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art15.png "AboutGdip05\_art15")  
  
 이번에는 오른쪽으로 200단위를 이동하고 아래로 150단위를 이동하려고 합니다.  
  
 다음 예제에서는 <xref:System.Drawing.Graphics> 개체의 전역 변환을 설정하여 방금 설명한 좌표계를 구성합니다.  
  
 [!code-csharp[System.Drawing.CoordinateSystems#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.CoordinateSystems#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#23)]  
  
 위 예제의 끝에 나오는 다음 코드는 단일 사각형으로 구성된 경로를 만드는데, 이 사각형의 왼쪽 아래 모퉁이는 새 좌표계의 원점에 존재합니다.  이 사각형은 한 번은 지역 변환을 사용하여 채워지고 다른 한 번은 지역 변환을 사용하지 않고 채워집니다.  이 지역 변환은 2의 비율로 가로 크기를 조정한 다음 30도를 회전시키는 변환으로 구성됩니다.  
  
 [!code-csharp[System.Drawing.CoordinateSystems#24](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#24)]
 [!code-vb[System.Drawing.CoordinateSystems#24](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#24)]  
  
 다음 그림은 새 좌표계와 두 개의 사각형을 나타냅니다.  
  
 ![변환](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art16.png "AboutGdip05\_art16")  
  
## 참고 항목  
 [좌표계 및 변환](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)   
 [관리 GDI\+에서 변환 사용](../../../../docs/framework/winforms/advanced/using-transformations-in-managed-gdi.md)