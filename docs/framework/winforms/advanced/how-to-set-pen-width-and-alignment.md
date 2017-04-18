---
title: "방법: 펜 굵기 및 맞춤 설정 | Microsoft Docs"
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
  - "펜, 맞춤 설정"
  - "펜, 굵기 설정"
ms.assetid: a202af36-4d31-4401-a126-b232f51db581
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# 방법: 펜 굵기 및 맞춤 설정
<xref:System.Drawing.Pen> 개체를 만들 때 펜 굵기를 생성자에 대한 인수 중 하나로 지정할 수 있습니다.  또한 <xref:System.Drawing.Pen> 클래스의 <xref:System.Drawing.Pen.Width%2A> 속성을 사용하여 펜 굵기를 변경할 수도 있습니다.  
  
 이론적인 선의 굵기는 0입니다.  굵기가 1픽셀인 선을 그릴 경우 픽셀은 이론적인 선의 가운데에 위치하게 됩니다.  굵기가 2 픽셀 이상인 선을 그리는 경우에는 픽셀이 이론적인 선의 가운데에 위치하거나 한쪽 옆에 나타납니다.  <xref:System.Drawing.Pen> 개체의 펜 맞춤 속성을 설정하면 해당 펜으로 그리는 픽셀의 상대적인 위치를 이론적인 선을 기준으로 결정할 수 있습니다.  
  
 다음 코드 예제에 나타나는 <xref:System.Drawing.Drawing2D.PenAlignment>, <xref:System.Drawing.Drawing2D.PenAlignment> 및 <xref:System.Drawing.Drawing2D.PenAlignment> 값은 <xref:System.Drawing.Drawing2D.PenAlignment> 열거형의 멤버입니다.  
  
 다음 코드 예제에서는 선을 두 번 그리는데 한 번은 굵기가 1인 검정 펜을 사용하고 또 한 번은 굵기가 10인 녹색 펜을 사용합니다.  
  
### 펜 굵기를 변경하려면  
  
-   <xref:System.Drawing.Pen.Alignment%2A> 속성의 값을 기본값인 <xref:System.Drawing.Drawing2D.PenAlignment>로 설정하여 녹색 펜으로 그리는 픽셀이 이론적인 선의 가운데에 위치하도록 지정합니다.  아래 그림에 이 예제에서 그린 선이 나와 있습니다.  
  
     ![펜](../../../../docs/framework/winforms/advanced/media/pens1a.png "pens1A")  
  
     다음 코드 예제에서는 사각형을 두 번 그리는데 한 번은 굵기가 1인 검정 펜을 사용하고 또 한 번은 굵기가 10인 녹색 펜을 사용합니다.  
  
     [!code-csharp[System.Drawing.UsingAPen#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#41)]
     [!code-vb[System.Drawing.UsingAPen#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#41)]  
  
### 펜 맞춤을 변경하려면  
  
-   <xref:System.Drawing.Pen.Alignment%2A> 속성의 값을 <xref:System.Drawing.Drawing2D.PenAlignment>로 설정하여 녹색 펜으로 그리는 픽셀이 사각형의 경계선 가운데에 위치하도록 지정합니다.  
  
     아래 그림에 이 코드에서 그린 사각형이 나와 있습니다.  
  
     ![펜](../../../../docs/framework/winforms/advanced/media/pens2.png "pens2")  
  
     [!code-csharp[System.Drawing.UsingAPen#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#42)]
     [!code-vb[System.Drawing.UsingAPen#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#42)]  
  
### 안쪽 맞춤 펜을 만들려면  
  
-   위의 코드 예제에서 세 번째 문을 다음과 같이 수정하여 녹색 펜의 맞춤을 변경합니다.  
  
     [!code-csharp[System.Drawing.UsingAPen#43](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#43)]
     [!code-vb[System.Drawing.UsingAPen#43](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#43)]  
  
     아래 그림과 같이 굵은 녹색 선의 픽셀이 사각형의 안쪽에 나타납니다.  
  
     ![펜](../../../../docs/framework/winforms/advanced/media/pens3.png "pens3")  
  
## 참고 항목  
 [펜을 사용하여 선과 도형 그리기](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)   
 [Windows Forms의 그래픽 및 그리기](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)