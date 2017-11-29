---
title: "GDI+에서 이미지 그리기, 위치 지정 및 복제"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- raster images [Windows Forms]
- images [Windows Forms], positioning
- drawing [Windows Forms], images
- drawing [Windows Forms], raster images
- images [Windows Forms], cloning
- images [Windows Forms], drawing
- GDI+, drawing images
- GDI+, cloning images
- GDI+, positioning images
ms.assetid: 09f0c07a-19c0-43b4-90a2-862a10545ce8
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a3ba716a36280d2ac08dae907abbdbe05e563dfc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="drawing-positioning-and-cloning-images-in-gdi"></a>GDI+에서 이미지 그리기, 위치 지정 및 복제
사용할 수는 <xref:System.Drawing.Bitmap> 로드 및 래스터 이미지를 표시 하는 클래스를 사용할 수는 <xref:System.Drawing.Imaging.Metafile> 클래스를 로드 하 고 벡터 이미지를 표시 합니다. <xref:System.Drawing.Bitmap> 및 <xref:System.Drawing.Imaging.Metafile> 클래스에서 상속 된 <xref:System.Drawing.Image> 클래스입니다. 벡터 이미지를 표시 하려면의 인스턴스는 <xref:System.Drawing.Graphics> 클래스 및 <xref:System.Drawing.Imaging.Metafile>합니다. 래스터 이미지를 표시 하려면의 인스턴스는 <xref:System.Drawing.Graphics> 클래스 및 <xref:System.Drawing.Bitmap>합니다. 인스턴스는 <xref:System.Drawing.Graphics> 클래스를 제공는 <xref:System.Drawing.Graphics.DrawImage%2A> 를 받는 메서드에서 <xref:System.Drawing.Imaging.Metafile> 또는 <xref:System.Drawing.Bitmap> 인수로 서입니다.  
  
## <a name="file-types-and-cloning"></a>파일 형식 및 복제  
 다음 코드 예제에서는 생성 하는 방법을 보여 줍니다.는 <xref:System.Drawing.Bitmap> Climber.jpg 파일에서 비트맵을 표시 하 고 있습니다. 이미지의 왼쪽 위 모퉁이 대 한 대상 지점 (10, 10), 두 번째와 세 번째 매개 변수에 지정 합니다.  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#11)]  
  
 다음 그림에서는 이미지를 보여 줍니다.  
  
 ![샘플 이미지](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art04.gif "AboutGdip03_Art04")  
  
 생성할 수 있습니다 <xref:System.Drawing.Bitmap> 다양 한 그래픽 개체 파일 형식: BMP, GIF, JPEG, EXIF, PNG, TIFF 및 아이콘입니다.  
  
 다음 코드 예제에서는 생성 하는 방법을 보여 줍니다. <xref:System.Drawing.Bitmap> 다양 한 파일 형식에서에서 개체를 다음 비트맵을 표시 합니다.  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#12)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#12)]  
  
 <xref:System.Drawing.Bitmap> 클래스를 제공는 <xref:System.Drawing.Bitmap.Clone%2A> 기존 복사본을 만드는 데 사용할 수 있는 메서드 <xref:System.Drawing.Bitmap>합니다. <xref:System.Drawing.Bitmap.Clone%2A> 메서드에 복사 하려는 원본 비트맵의 일부를 지정 하는 데 사용할 수 있는 소스 사각형 매개 변수가 있습니다. 다음 코드 예제에서는 만드는 방법을 보여 줍니다.는 <xref:System.Drawing.Bitmap> 기존의 위쪽 절반을 복제 하 여 <xref:System.Drawing.Bitmap>합니다. 다음 두 이미지를 그립니다.  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#13](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#13)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#13](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#13)]  
  
 다음 그림은 두 가지 이미지를 보여 줍니다.  
  
 ![자르기](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art05.gif "AboutGdip03_Art05")  
  
## <a name="see-also"></a>참고 항목  
 [이미지, 비트맵 및 메타파일](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [방법: 그리는 데 필요한 그래픽 개체 만들기](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 [이미지, 비트맵, 아이콘 및 메타파일 사용](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
