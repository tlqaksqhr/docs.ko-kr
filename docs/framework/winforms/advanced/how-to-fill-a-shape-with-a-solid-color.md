---
title: "방법: 단색으로 도형 채우기 | Microsoft Docs"
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
  - "색, 도형에 추가"
  - "도형, 채우기"
ms.assetid: 06088b31-bac9-4ef3-9ebe-06c2c764d6df
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# 방법: 단색으로 도형 채우기
단색으로 도형을 채우려면 <xref:System.Drawing.SolidBrush> 개체를 만든 다음 이 <xref:System.Drawing.SolidBrush> 개체를 <xref:System.Drawing.Graphics> 클래스의 채우기 메서드 중 하나에 인수로 전달합니다.  아래 예제에서는 빨간색으로 타원을 채우는 방법을 보여 줍니다.  
  
## 예제  
 다음 코드에서 <xref:System.Drawing.SolidBrush.%23ctor%2A> 생성자는 <xref:System.Drawing.Color> 개체만 인수로 사용합니다.  <xref:System.Drawing.Color.FromArgb%2A> 메서드에 사용되는 값은 색의 알파, 빨강, 녹색 및 파랑 구성 요소를 나타냅니다.  이러한 각 값은 0\-255 사이에 있어야 합니다.  첫 번째 255는 색이 완전한 불투명이라는 것을 나타내며 두 번째 255는 빨강 구성 요소의 농도가 100%라는 것을 나타냅니다.  나머지 두 개의 0은 각각 녹색 및 파랑 구성 요소의 농도가 0%임을 나타냅니다.  
  
 <xref:System.Drawing.Graphics.FillEllipse%2A> 메서드에 전달된 네 개의 숫자 \(0, 0, 100, 60\)은 타원을 둘러싸는 사각형의 위치와 크기를 나타냅니다.  이 사각형의 왼쪽 위 모퉁이는 \(0, 0\)이고 너비는 100, 높이는 60입니다.  
  
 [!code-csharp[System.Drawing.UsingABrush#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingABrush#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#11)]  
  
## 코드 컴파일  
 앞의 예제는 Windows Forms에서 사용해야 하며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`를 필요로 합니다.  
  
## 참고 항목  
 [브러시를 사용하여 도형 채우기](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)