---
title: "GDI+에서 이미지 자르기 및 배율 조정 | Microsoft Docs"
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
  - "데이터 압축, 이미지"
  - "GDI+, 이미지 자르기"
  - "GDI+, 이미지 크기 조정"
  - "이미지[Windows Forms], 압축"
  - "이미지[Windows Forms], 자르기"
  - "이미지[Windows Forms], 확장"
  - "이미지[Windows Forms], 배율"
  - "사각형, 대상"
  - "사각형, 소스"
ms.assetid: ad5daf26-005f-45bc-a2af-e0e97777a21a
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# GDI+에서 이미지 자르기 및 배율 조정
<xref:System.Drawing.Graphics> 클래스의 <xref:System.Drawing.Graphics.DrawImage%2A> 메서드를 사용하여 벡터 이미지와 래스터 이미지를 그리고 위치를 지정할 수 있습니다.  <xref:System.Drawing.Graphics.DrawImage%2A>는 오버로드된 메서드이므로 여러 가지 방법으로 여기에 인수를 제공할 수 있습니다.  
  
## DrawImage의 변형 메서드  
 <xref:System.Drawing.Graphics.DrawImage%2A> 메서드에서 변형된 메서드는 <xref:System.Drawing.Bitmap> 개체와 <xref:System.Drawing.Rectangle> 개체를 받습니다.  사각형은 그리기 작업의 대상 위치를 지정합니다. 즉 이미지를 그릴 사각형 영역을 지정합니다.  대상 사각형이 원래의 이미지 크기와 다르면 이미지는 대상 사각형에 맞도록 크기가 조절됩니다.  다음 코드 예제에서는 같은 이미지를 세 번 그립니다. 이 때 배율 조정을 하지 않은 경우, 배율을 확대한 경우 및 배율을 축소한 경우와 같이 모두 세 가지 방법을 보여 줍니다.  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#31)]  
  
 다음 그림은 세 그림을 보여 줍니다.  
  
 ![배율 조정](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art06.png "AboutGdip03\_Art06")  
  
 <xref:System.Drawing.Graphics.DrawImage%2A> 메서드의 변형 메서드 중 일부는 대상 사각형 매개 변수와 원본 사각형 매개 변수를 사용합니다.  원본 사각형 매개 변수는 그리려는 원본 이미지 부분을 지정합니다.  대상 사각형은 이러한 이미지 부분을 그릴 사각형 영역을 지정합니다.  대상 사각형의 크기가 원본 사각형의 크기와 다르면 그림은 대상 사각형에 맞도록 크기가 조절됩니다.  
  
 다음 코드 예제에서는 Runner.jpg 파일에서 <xref:System.Drawing.Bitmap>을 만드는 방법을 보여 줍니다.  이때 배율을 조정하지 않은 상태로 \(0, 0\) 위치에 전체 이미지를 그립니다.  그런 다음 작은 이미지 부분을 두 번 그립니다. 한 번은 축소하여 그리고, 한 번은 확대하여 그립니다.  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#32)]  
  
 다음 그림은 크기 조절하지 않은 이미지와 축소 및 확대한 이미지 부분을 보여 줍니다.  
  
 ![자르기 및 배율 조정](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art07.png "AboutGdip03\_Art07")  
  
## 참고 항목  
 [이미지, 비트맵 및 메타파일](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)   
 [이미지, 비트맵, 아이콘 및 메타파일 사용](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)