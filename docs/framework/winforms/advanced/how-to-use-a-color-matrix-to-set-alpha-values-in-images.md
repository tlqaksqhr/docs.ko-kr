---
title: "방법: 색 매트릭스를 사용하여 이미지에 알파 값 설정 | Microsoft Docs"
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
  - "비트맵[Windows Forms], 반투명에 색 매트릭스 사용"
  - "이미지[Windows Forms], 반투명에 색 매트릭스 사용"
  - "매트릭스, 알파 값"
  - "투명성, 색 매트릭스"
ms.assetid: a27121e6-f7e9-4c09-84e2-f05aa9d2a1bb
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# 방법: 색 매트릭스를 사용하여 이미지에 알파 값 설정
<xref:System.Drawing.Image> 클래스에서 상속되는 <xref:System.Drawing.Bitmap> 클래스와 <xref:System.Drawing.Imaging.ImageAttributes> 클래스에는 픽셀 값을 가져오고 설정하는 기능이 있습니다.  <xref:System.Drawing.Imaging.ImageAttributes> 클래스를 사용하여 전체 이미지의 알파 값을 수정하거나 <xref:System.Drawing.Bitmap> 클래스의 <xref:System.Drawing.Bitmap.SetPixel%2A> 메서드를 호출하여 개별 픽셀 값을 수정할 수 있습니다.  
  
## 예제  
 <xref:System.Drawing.Imaging.ImageAttributes> 클래스에는 렌더링하는 동안 이미지를 수정하는 데 사용할 수 있는 속성이 많이 있습니다.  다음 예제에서는 <xref:System.Drawing.Imaging.ImageAttributes> 개체를 사용하여 모든 알파 값을 원래 값의 80%로 설정합니다.  이를 위해 색 매트릭스를 초기화하고 매트릭스에서 알파 배율 조정 값을0.8로 설정합니다.  색 매트릭스의 주소는 <xref:System.Drawing.Imaging.ImageAttributes> 개체의 <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> 메서드에 전달되고 <xref:System.Drawing.Imaging.ImageAttributes> 개체는 <xref:System.Drawing.Graphics> 개체의 <xref:System.Drawing.Graphics.DrawString%2A> 메서드에 전달됩니다.  
  
 렌더링하는 동안 비트맵의 알파 값은 이전 값의 80%로 변환되며,  그에 따라 이미지가 배경과 혼합됩니다.  아래 그림에 나와 있는 것처럼 비트맵 이미지가 투명하므로 이미지를 투과하여 검정 선을 볼 수 있습니다.  
  
 ![매트릭스를 사용한 알파 혼합](../../../../docs/framework/winforms/advanced/media/image2.png "image2")  
  
 배경의 흰색 부분에 있는 이미지는 흰색과 혼합되고  검정 선과 교차하는 곳의 이미지는 검정과 혼합됩니다.  
  
 [!code-csharp[System.Drawing.AlphaBlending#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.AlphaBlending#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#21)]  
  
## 코드 컴파일  
 앞의 예제는 Windows Forms에서 사용해야 하며 <xref:System.Windows.Forms.PaintEventHandler>의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`를 필요로 합니다.  
  
## 참고 항목  
 [Windows Forms의 그래픽 및 그리기](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)   
 [선 및 채우기 알파 혼합](../../../../docs/framework/winforms/advanced/alpha-blending-lines-and-fills.md)