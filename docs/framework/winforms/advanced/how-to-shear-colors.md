---
title: "방법: 색 전단 | Microsoft Docs"
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
  - "색, 전단"
  - "색, 색 매트릭스를 사용하여 변환"
ms.assetid: 0a424171-5b8b-45c4-afef-e9720a6c3e22
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# 방법: 색 전단
전단 변환에서는 다른 색 구성 요소의 일정 비율로 색 구성 요소를 늘리거나 줄입니다.  예를 들어, 빨강 구성 요소를 파랑 구성 요소 값의 50%만큼 늘리는 변환에서는  색 \(0.2, 0.5, 1\)이 \(0.7, 0.5, 1\)로 변환됩니다.  여기서 변환된 빨강 구성 요소의 값은 0.2 \+ \(1\/2\)\(1\)의 결과로 0.7이 되었습니다.  
  
## 예제  
 다음 예제에서는 ColorBars4.bmp 파일에서 <xref:System.Drawing.Image> 개체를 만듭니다.  그런 다음 코드에서는 위 단락에서 설명한 전단 변환을 이미지의 각 픽셀에 적용합니다.  
  
 아래 그림에서 왼쪽은 원래 이미지이고 오른쪽은 기울이기 변환이 적용된 이미지입니다.  
  
 ![색 전단](../../../../docs/framework/winforms/advanced/media/colortrans6.png "colortrans6")  
  
 아래 표에는 전단 변환을 수행하기 전과 변환 후의 막대 네 개에 대한 색 벡터가 나와 있습니다.  
  
|원래 설정|기울이기 적용 후 이미지|  
|-----------|-------------------|  
|\(0, 0, 1, 1\)|\(0.5, 0, 1, 1\)|  
|\(0.5, 1, 0.5, 1\)|\(0.75, 1, 0.5, 1\)|  
|\(1, 1, 0, 1\)|\(1, 1, 0, 1\)|  
|\(0.4, 0.4, 0.4, 1\)|\(0.6, 0.4, 0.4, 1\)|  
  
 [!code-csharp[System.Drawing.Misc3#9](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Misc3/CS/Form1.cs#9)]
 [!code-vb[System.Drawing.Misc3#9](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Misc3/VB/Form1.vb#9)]  
  
## 코드 컴파일  
 앞의 예제는 Windows Forms에서 사용해야 하며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`를 필요로 합니다.  `ColorBars.bmp`를 시스템에서 사용할 수 있는 이미지 이름 및 경로로 바꾸십시오.  
  
## 참고 항목  
 <xref:System.Drawing.Imaging.ColorMatrix>   
 <xref:System.Drawing.Imaging.ImageAttributes>   
 [Windows Forms의 그래픽 및 그리기](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)   
 [이미지 다시 칠하기](../../../../docs/framework/winforms/advanced/recoloring-images.md)