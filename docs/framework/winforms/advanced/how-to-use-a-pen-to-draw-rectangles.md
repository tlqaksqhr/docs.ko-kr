---
title: "방법: 펜을 사용하여 사각형 그리기 | Microsoft Docs"
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
  - "펜, 사각형 그리기"
  - "사각형, 그리기"
ms.assetid: 54a7fa14-3ad8-4d64-b424-2a12005b250c
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# 방법: 펜을 사용하여 사각형 그리기
사각형을 그리려면 <xref:System.Drawing.Graphics> 개체와 <xref:System.Drawing.Pen> 개체가 필요합니다.  <xref:System.Drawing.Graphics> 개체는 <xref:System.Drawing.Graphics.DrawRectangle%2A> 메서드를 제공하고 <xref:System.Drawing.Pen> 개체에는 선의 색과 두께 같은 특징이 저장됩니다.  
  
## 예제  
 아래 예제에서는 왼쪽 위 모퉁이가 \(10, 10\)인 사각형을 그립니다.  사각형의 너비는 100이고 높이는 50입니다.  <xref:System.Drawing.Pen.%23ctor%2A> 생성자에 전달되는 두 번째 인수는 펜 너비를 5픽셀로 지정합니다.  
  
 사각형을 그릴 때 펜은 사각형 경계의 가운데에 위치합니다.  펜의 굵기가 5이므로 사각형의 변은 5 픽셀 너비로 그려집니다. 1 픽셀은 경계에, 2 픽셀은 안쪽에, 나머지 2 픽셀은 바깥쪽에 그려집니다.  펜 맞춤에 대한 자세한 내용은 [방법: 펜 굵기 및 맞춤 설정](../../../../docs/framework/winforms/advanced/how-to-set-pen-width-and-alignment.md)을 참조하십시오.  
  
 아래 그림에 이 코드에서 그린 사각형이 나와 있습니다.  점선은 펜 굵기가 1 픽셀인 경우 사각형이 그려지는 위치를 나타냅니다.  사각형의 왼쪽 위 모퉁이를 확대해서 보면 굵은 검정선이 이 점선의 가운데에 있는 것을 알 수 있습니다.  
  
 ![펜](../../../../docs/framework/winforms/advanced/media/pens1.png "pens1")  
  
 [!code-csharp[System.Drawing.UsingAPen#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.UsingAPen#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#21)]  
  
## 코드 컴파일  
 앞의 예제는 Windows Forms에서 사용해야 하며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`를 필요로 합니다.  
  
## 참고 항목  
 [펜을 사용하여 선과 도형 그리기](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)