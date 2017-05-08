---
title: "방법: 화면에 기존 비트맵 그리기 | Microsoft Docs"
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
  - "비트맵[Windows Forms], Windows Forms에 표시"
  - "비트맵[Windows Forms], Windows Forms 응용 프로그램에서 로드"
  - "이미지[Windows Forms], Windows Forms에 표시"
ms.assetid: 5bc558d7-b326-4050-a834-b8600da0de95
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# 방법: 화면에 기존 비트맵 그리기
기존 이미지를 화면에 손쉽게 그릴 수 있습니다.  먼저 파일 이름을 받아들이는 비트맵 생성자 <xref:System.Drawing.Bitmap.%23ctor%28System.String%29>을 사용하여 <xref:System.Drawing.Bitmap> 개체를 만들어야 합니다.  이 생성자는 BMP, GIF, JPEG, PNG 및 TIFF 같은 다양한 파일 형식의 이미지를 사용할 수 있습니다.  <xref:System.Drawing.Bitmap> 개체를 만든 뒤에는 이 <xref:System.Drawing.Bitmap> 개체를 <xref:System.Drawing.Graphics> 개체의 <xref:System.Drawing.Graphics.DrawImage%2A> 메서드에 전달합니다.  
  
## 예제  
 이 예제에서는 JPEG 파일을 사용하여 <xref:System.Drawing.Bitmap> 개체를 만든 다음 왼쪽 위 모퉁이가 \(60, 10\)인 비트맵을 그립니다.  
  
 아래 그림에서는 지정한 위치에 그려진 비트맵을 보여 줍니다.  
  
 ![이미지 위치](../../../../docs/framework/winforms/advanced/media/csimageposition1.png "csimageposition1")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.WorkingWithImages#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#21)]  
  
## 코드 컴파일  
 앞의 예제는 Windows Forms에서 사용해야 하며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`를 필요로 합니다.  
  
## 참고 항목  
 [Windows Forms의 그래픽 및 그리기](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)   
 [이미지, 비트맵, 아이콘 및 메타파일 사용](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)