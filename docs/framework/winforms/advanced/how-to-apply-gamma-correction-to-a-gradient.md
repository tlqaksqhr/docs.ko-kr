---
title: "방법: 그라데이션에 감마 보정 적용 | Microsoft Docs"
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
  - "그라데이션 브러시, 감마 보정"
  - "그라데이션, 감마 보정"
ms.assetid: da4690e7-5fac-4fd2-b3f0-5cb35c165b92
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# 방법: 그라데이션에 감마 보정 적용
브러시의 <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> 속성을 `true`로 설정하여 선형 그라데이션 브러시에 감마 보정을 사용하도록 할 수 있습니다.  <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> 속성을 `false`로 설정하면 감마 보정 기능을 해제할 수 있습니다.  감마 보정은 기본적으로 사용되지 않습니다.  
  
## 예제  
 이 예제에서는 선형 그라데이션 브러시를 만들고 이 브러시를 사용하여 두 사각형을 채웁니다.  첫 번째 사각형을 채울 때는 감마 보정을 사용하지 않지만 두 번째 사각형을 채울 때는 감마 보정을 사용합니다.  
  
 아래 그림에서는 채워진 두 사각형을 보여 줍니다.  감마 보정을 적용하지 않은 위쪽 사각형은 중간 부분이 짙게 나타나는 반면  감마 보정을 적용한 아래쪽 사각형은 농도가 좀 더 균일하게 나타납니다.  
  
 ![그라데이션](../../../../docs/framework/winforms/advanced/media/gammagradient1.png "gammagradient1")  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingaGradientBrush#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#31)]  
  
## 코드 컴파일  
 앞의 예제는 Windows Forms에서 사용해야 하며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`를 필요로 합니다.  
  
## 참고 항목  
 <xref:System.Drawing.Drawing2D.LinearGradientBrush>   
 [그라데이션 브러시를 사용하여 도형 채우기](../../../../docs/framework/winforms/advanced/using-a-gradient-brush-to-fill-shapes.md)