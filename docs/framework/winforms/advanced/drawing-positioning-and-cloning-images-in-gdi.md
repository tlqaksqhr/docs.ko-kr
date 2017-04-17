---
title: "GDI+에서 이미지 그리기, 위치 지정 및 복제 | Microsoft Docs"
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
  - "그리기, 이미지"
  - "그리기, 래스터 이미지"
  - "GDI+, 이미지 복제"
  - "GDI+, 이미지 그리기"
  - "GDI+, 이미지 위치 지정"
  - "이미지[Windows Forms], 복제"
  - "이미지[Windows Forms], 그리기"
  - "이미지[Windows Forms], 위치 지정"
  - "래스터 이미지"
ms.assetid: 09f0c07a-19c0-43b4-90a2-862a10545ce8
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# GDI+에서 이미지 그리기, 위치 지정 및 복제
<xref:System.Drawing.Bitmap> 클래스를 사용하여 래스터 이미지를 로드하고 표시할 수 있으며 <xref:System.Drawing.Imaging.Metafile> 클래스를 사용하여 벡터 이미지를 로드하고 표시할 수 있습니다.  <xref:System.Drawing.Bitmap> 클래스와 <xref:System.Drawing.Imaging.Metafile> 클래스는 <xref:System.Drawing.Image> 클래스에서 상속됩니다.  벡터 이미지를 표시하려면 <xref:System.Drawing.Graphics> 클래스 인스턴스와 <xref:System.Drawing.Imaging.Metafile>이 필요하고  래스터 이미지를 표시하려면 <xref:System.Drawing.Graphics> 클래스 인스턴스와 <xref:System.Drawing.Bitmap>이 필요합니다.  <xref:System.Drawing.Graphics> 클래스 인스턴스는 <xref:System.Drawing.Imaging.Metafile> 또는 <xref:System.Drawing.Bitmap>을 인수로 받는 <xref:System.Drawing.Graphics.DrawImage%2A> 메서드를 제공합니다.  
  
## 파일 형식 및 복제  
 다음 코드 예제에서는 Climber.jpg 파일에서 <xref:System.Drawing.Bitmap> 개체를 만든 다음 비트맵을 표시하는 방법을 보여 줍니다.  두 번째 및 세 번째 매개 변수에 이미지의 왼쪽 위 모퉁이의 대상점인\(10, 10\)을 지정하였습니다.  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#11)]  
  
 다음 그림은 이미지를 보여 줍니다.  
  
 ![이미지 샘플](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art04.png "AboutGdip03\_Art04")  
  
 BMP, GIF, JPEG, EXIF, PNG, TIFF 및 ICON 같은 다양한 그래픽 파일 형식에서 <xref:System.Drawing.Bitmap> 개체를 만들 수 있습니다.  
  
 다음 코드 예제에서는 다양한 파일 형식에서 <xref:System.Drawing.Bitmap> 개체를 만든 다음 비트맵을 표시하는 방법을 보여 줍니다.  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#12)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#12)]  
  
 <xref:System.Drawing.Bitmap> 클래스는 기존 <xref:System.Drawing.Bitmap> 개체의 복사본을 만드는 데 사용할 수 있는 <xref:System.Drawing.Bitmap.Clone%2A> 메서드를 제공합니다.  <xref:System.Drawing.Bitmap.Clone%2A> 메서드에는 복사할 원본 비트맵의 일부를 지정하는 데 사용할 수 있는 원본 사각형 매개 변수가 있습니다.  다음 코드 예제에서는 기존 <xref:System.Drawing.Bitmap> 개체의 위쪽 절반을 복제하여 <xref:System.Drawing.Bitmap> 개체를 만드는 방법을 보여 줍니다.  그런 다음 두 이미지를 그립니다.  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#13](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#13)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#13](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#13)]  
  
 다음 그림은 두 이미지를 보여 줍니다.  
  
 ![자르기](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art05.png "AboutGdip03\_Art05")  
  
## 참고 항목  
 [이미지, 비트맵 및 메타파일](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)   
 [방법: 그리는 데 필요한 그래픽 개체 만들기](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)   
 [이미지, 비트맵, 아이콘 및 메타파일 사용](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)