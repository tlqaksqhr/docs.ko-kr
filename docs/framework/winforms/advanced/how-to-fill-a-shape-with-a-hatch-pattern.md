---
title: "방법: 빗살 무늬로 도형 채우기 | Microsoft Docs"
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
  - "브러시, 빗살 무늬 브러시 사용"
  - "패턴, 도형에 추가"
  - "도형, 패턴으로 채우기"
ms.assetid: 9c8300ff-187b-404f-af1f-ebd499f5b16f
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# 방법: 빗살 무늬로 도형 채우기
빗살 무늬는 두 가지 색, 즉 배경으로 사용할 색과 배경 위에 무늬를 만드는 선에 사용할 색으로 구성됩니다.  닫힌 도형을 빗살 무늬로 채우려면 <xref:System.Drawing.Drawing2D.HatchBrush> 개체를 사용합니다.  아래 예제에서는 타원을 빗살 무늬로 채우는 방법을 보여 줍니다.  
  
## 예제  
 <xref:System.Drawing.Drawing2D.HatchBrush.%23ctor%2A> 생성자에는 빗살 스타일, 빗살 선의 색, 배경색 등 세 개의 인수를 사용합니다.  <xref:System.Drawing.Drawing2D.HatchStyle> 열거형에 있는 요소 중 하나를 빗살 스타일 인수로 사용할 수 있습니다.  <xref:System.Drawing.Drawing2D.HatchStyle> 열거형에는 50개 이상의 요소가 있으며 그 중 일부가 다음 목록에 나와 있습니다.  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle>  
  
 아래 그림에 채워진 타원이 나와 있습니다.  
  
 ![빗살 무늬](../../../../docs/framework/winforms/advanced/media/hatch1.png "hatch1")  
  
 [!code-csharp[System.Drawing.UsingABrush#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.UsingABrush#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#41)]  
  
## 코드 컴파일  
 앞의 예제는 Windows Forms에서 사용해야 하며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`를 필요로 합니다.  
  
## 참고 항목  
 [브러시를 사용하여 도형 채우기](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)