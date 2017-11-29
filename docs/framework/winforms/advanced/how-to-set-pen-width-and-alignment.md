---
title: "방법: 펜 굵기 및 맞춤 설정"
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
- pens [Windows Forms], setting width
- pens [Windows Forms], setting alignment
ms.assetid: a202af36-4d31-4401-a126-b232f51db581
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6ed2a28c49554c686abb5e2635ab35b746b83465
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-pen-width-and-alignment"></a>방법: 펜 굵기 및 맞춤 설정
만들 때 한 <xref:System.Drawing.Pen>, 생성자의 인수 중 하나로 펜 너비를 제공할 수 있습니다. 펜 너비를 변경할 수도 있습니다는 <xref:System.Drawing.Pen.Width%2A> 의 속성은 <xref:System.Drawing.Pen> 클래스입니다.  
  
 이론적인 선의 너비는 0에 있습니다. 1 픽셀 너비에 있는 줄을 그릴 때 이론적인 줄에 있는 픽셀 가운데 맞춤 됩니다. 둘 이상의 픽셀 너비에 있는 줄을 그릴 경우 픽셀은 하거나 선 가운데에 이론적인 또는 이론적인 선의 한쪽으로 나타납니다. 펜 맞춤 속성을 설정할 수 있습니다는 <xref:System.Drawing.Pen> 이론적인 선을 기준으로 해당 펜을 사용 하 여 그린 픽셀 배치 되는 방식을 결정 하 합니다.  
  
 값 <xref:System.Drawing.Drawing2D.PenAlignment.Center>, <xref:System.Drawing.Drawing2D.PenAlignment.Outset>, 및 <xref:System.Drawing.Drawing2D.PenAlignment.Inset> 다음에 나타나는 컴퓨터의 멤버인 코드 예제는 <xref:System.Drawing.Drawing2D.PenAlignment> 열거형입니다.  
  
 다음 코드 예제에서는 한 줄을 두 번 그립니다: 고 한 번의 너비가 10 녹색 펜 너비 1의 검은색 펜으로 한 번입니다.  
  
### <a name="to-vary-the-width-of-a-pen"></a>펜의 너비를 변경 하려면  
  
-   값을 설정할는 <xref:System.Drawing.Pen.Alignment%2A> 속성을 <xref:System.Drawing.Drawing2D.PenAlignment.Center> (기본값) 녹색 펜을 사용 하 여 그린 픽셀 이론적인 줄에 가운데 맞춤 될 됩니다 지정할 수 있습니다. 다음 그림에서는 결과 선을 보여 줍니다.  
  
     ![펜](../../../../docs/framework/winforms/advanced/media/pens1a.gif "pens1A")  
  
     다음 코드 예제에서는 두 번 사각형을 그립니다: 고 한 번의 너비가 10 녹색 펜 너비 1의 검은색 펜으로 한 번입니다.  
  
     [!code-csharp[System.Drawing.UsingAPen#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#41)]
     [!code-vb[System.Drawing.UsingAPen#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#41)]  
  
### <a name="to-change-the-alignment-of-a-pen"></a>펜의 맞춤을 변경 하려면  
  
-   값을 설정할는 <xref:System.Drawing.Pen.Alignment%2A> 속성을 <xref:System.Drawing.Drawing2D.PenAlignment.Center> 픽셀 녹색 펜을 사용 하 여 그린 사각형의 경계에서 가운데 맞춤 될 됩니다 지정할 수 있습니다.  
  
     다음 그림에서는 결과 사각형을 보여 줍니다.  
  
     ![펜](../../../../docs/framework/winforms/advanced/media/pens2.gif "pens2")  
  
     [!code-csharp[System.Drawing.UsingAPen#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#42)]
     [!code-vb[System.Drawing.UsingAPen#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#42)]  
  
### <a name="to-create-an-inset-pen"></a>삽입 펜을 만들려면  
  
-   이전 코드 예제에서 세 번째 문을 다음과 같이 수정 하 여 녹색 펜의 맞춤을 변경 합니다.  
  
     [!code-csharp[System.Drawing.UsingAPen#43](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#43)]
     [!code-vb[System.Drawing.UsingAPen#43](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#43)]  
  
     이제 다음 그림에 나와 있는 것 처럼 굵은 녹색 줄의 픽셀 사각형의 내부에 나타납니다.  
  
     ![펜](../../../../docs/framework/winforms/advanced/media/pens3.gif "pens3")  
  
## <a name="see-also"></a>참고 항목  
 [펜을 사용하여 선과 도형 그리기](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)  
 [Windows Forms의 그래픽 및 그리기](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
