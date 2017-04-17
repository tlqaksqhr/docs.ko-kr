---
title: "방법: 이미지 질감으로 도형 채우기 | Microsoft Docs"
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
  - "비트맵[Windows Forms], 질감 사용"
  - "이미지[Windows Forms], 브러시에 사용"
  - "도형, 이미지로 채우기"
ms.assetid: 508da5a6-2433-4d2b-9680-eaeae4e96e3b
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# 방법: 이미지 질감으로 도형 채우기
<xref:System.Drawing.Image> 클래스와 <xref:System.Drawing.TextureBrush> 클래스를 사용하면 닫힌 도형을 질감으로 채울 수 있습니다.  
  
## 예제  
 아래 예제에서는 타원에 이미지를 채웁니다.  이 코드에서는 <xref:System.Drawing.Image> 개체를 만들어 해당 <xref:System.Drawing.Image> 개체의 주소를 <xref:System.Drawing.TextureBrush.%23ctor%2A> 생성자에 인수로 전달합니다.  세 번째 문에서는 이미지의 배율을 조정하고 네 번째 문에서는 배율 조정된 이미지의 복사본을 반복적으로 사용하여 타원을 채웁니다.  
  
 다음 코드에서 <xref:System.Drawing.TextureBrush.Transform%2A> 속성에는 이미지를 그리기 전에 이미지에 적용되는 변환이 지정되어 있습니다.  원래 이미지의 너비는 640 픽셀이고 높이는 480 픽셀이라고 가정합니다.  변환에서는 가로 및 세로 배율 조정 값을 설정하여 이미지 크기를 75×75로 줄입니다.  
  
> [!NOTE]
>  다음 예제에서는 이미지 크기가 75×75이고 타원 크기는 150×250입니다.  채울 타원보다 이미지 크기가 작기 때문에 이미지가 타원에서 바둑판식으로 배열됩니다.  바둑판식으로 채울 때는 도형의 경계 부분에 이를 때까지 이미지가 가로 및 세로로 반복하여 배열됩니다.  바둑판식 배열에 대한 자세한 내용은 [방법: 도형에 이미지를 바둑판식으로 배열](../../../../docs/framework/winforms/advanced/how-to-tile-a-shape-with-an-image.md)을 참조하십시오.  
  
 [!code-csharp[System.Drawing.UsingABrush#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.UsingABrush#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#21)]  
  
## 코드 컴파일  
 앞의 예제는 Windows Forms에서 사용해야 하며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`를 필요로 합니다.  
  
## 참고 항목  
 [브러시를 사용하여 도형 채우기](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)