---
title: "GDI+에서 이미지 자르기 및 배율 조정"
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
- GDI+, scaling images
- GDI+, cropping images
- images [Windows Forms], cropping
- compressing data [Windows Forms], images
- images [Windows Forms], expansion
- images [Windows Forms], scaling
- rectangles [Windows Forms], source
- rectangles [Windows Forms], destination
- images [Windows Forms], compression
ms.assetid: ad5daf26-005f-45bc-a2af-e0e97777a21a
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 63e1e55e57d586cbbca87361b95c18f0f53b8c75
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="cropping-and-scaling-images-in-gdi"></a>GDI+에서 이미지 자르기 및 배율 조정
사용할 수 있습니다는 <xref:System.Drawing.Graphics.DrawImage%2A> 의 메서드는 <xref:System.Drawing.Graphics> 클래스를 그리기 및 벡터 이미지 및 래스터 이미지 위치를 지정 합니다. <xref:System.Drawing.Graphics.DrawImage%2A>오버 로드 된 메서드를 이므로 여러 가지 인수를 제공할 수 있습니다.  
  
## <a name="drawimage-variations"></a>DrawImage 변형  
 한 변형 된 개체가 <xref:System.Drawing.Graphics.DrawImage%2A> 메서드 수신는 <xref:System.Drawing.Bitmap> 및 <xref:System.Drawing.Rectangle>합니다. 사각형 그리기 작업;에 대 한 대상 지정 즉, 이미지를 그릴 사각형을 지정 합니다. 대상 사각형의 크기는 원본 이미지의 크기와에서 다른 경우 대상 사각형에 맞게 이미지 배율을 조정 합니다. 다음 코드 예제에는 세 번 동일한 이미지를 그리는 방법을 보여 줍니다: 크기가와 한 번, 확장, 한 번 및를:  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#31)]  
  
 다음 그림에서는 세 그림을 보여 줍니다.  
  
 ![크기 조정](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art06.gif "AboutGdip03_Art06")  
  
 일부 변형이 <xref:System.Drawing.Graphics.DrawImage%2A> 메서드 대상 사각형 매개 변수 뿐 아니라 소스 사각형 매개 변수를 포함 합니다. 소스 사각형 매개 변수를 그릴 원본 이미지의 부분을 지정 합니다. 대상 사각형 이미지의 부분을 그릴 사각형을 지정 합니다. 대상 사각형의 크기가 소스 사각형의 크기와에서 다른 경우에 그림 대상 사각형에 맞게 크기가 조정 됩니다.  
  
 다음 코드 예제에서는 생성 하는 방법을 보여 줍니다.는 <xref:System.Drawing.Bitmap> Runner.jpg 파일에서 합니다. 전체 이미지 배율에으로 그려집니다 (0, 0). 다음 이미지의 작은 부분을 두 번 그려집니다:으로 압축 되 고 한 번 확장 되었습니다.  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#32)]  
  
 다음 그림에서는 실제 크기의 이미지 및 이미지 축소 및 확대 부분을 보여 줍니다.  
  
 ![자르기 및 배율 조정](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art07.gif "AboutGdip03_Art07")  
  
## <a name="see-also"></a>참고 항목  
 [이미지, 비트맵 및 메타파일](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [이미지, 비트맵, 아이콘 및 메타파일 사용](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
