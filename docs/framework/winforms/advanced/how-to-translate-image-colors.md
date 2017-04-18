---
title: "방법: 이미지 색 변환 | Microsoft Docs"
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
  - "비트맵[Windows Forms], 색 변경"
  - "이미지 색[Windows Forms]"
  - "이미지[Windows Forms], 색 변경"
ms.assetid: 2106fb9a-4d60-4dcf-9220-9f189a6c4d19
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# 방법: 이미지 색 변환
이동에서는 네 가지 색 구성 요소 중 하나 이상에 값을 더합니다.  이동을 나타내는 색 매트릭스 엔트리가 아래 표에 나와 있습니다.  
  
|변환할 구성 요소|매트릭스 엔트리|  
|---------------|--------------|  
|빨강|\[4\]\[0\]|  
|녹색|\[4\]\[1\]|  
|파랑|\[4\]\[2\]|  
|알파|\[4\]\[3\]|  
  
## 예제  
 다음 예제에서는 ColorBars.bmp 파일에서 <xref:System.Drawing.Image> 개체를 만듭니다.  이미지에 있는 각 픽셀의 빨강 구성 요소에 0.75를 더합니다.  변환된 이미지 옆에 원래 이미지가 그려집니다.  
  
 아래 그림에서 왼쪽은 원래 이미지이고 오른쪽은 변환된 이미지입니다.  
  
 ![색 변환](../../../../docs/framework/winforms/advanced/media/colortrans2.png "colortrans2")  
  
 아래 표에는 빨강 구성 요소를 이동하기 전과 이동 후의 막대 네 개에 대한 색 벡터가 나와 있습니다.  색 구성 요소에 대한 최대값이 1이기 때문에 두 번째 행에서 빨강 구성 요소에 대한 최대값은 변하지 않습니다.  마찬가지로, 색 구성 요소에 대한 최소값은 0입니다.  
  
|원래 설정|변환된 이미지|  
|-----------|-------------|  
|검정 \(0, 0, 0, 1\)|\(0.75, 0, 0, 1\)|  
|빨강 \(1, 0, 0, 1\)|\(1, 0, 0, 1\)|  
|녹색 \(0, 1, 0, 1\)|\(0.75, 1, 0, 1\)|  
|파랑 \(0, 0, 1, 1\)|\(0.75, 0, 1, 1\)|  
  
 [!code-csharp[System.Drawing.RecoloringImages#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.RecoloringImages#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#11)]  
  
## 코드 컴파일  
 앞의 예제는 Windows Forms에서 사용해야 하며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`를 필요로 합니다.  `ColorBars.bmp` 를 시스템에서 사용할 수 있는 이미지 파일 이름 및 경로로 바꾸십시오.  
  
## 참고 항목  
 <xref:System.Drawing.Imaging.ColorMatrix>   
 <xref:System.Drawing.Imaging.ImageAttributes>   
 [Windows Forms의 그래픽 및 그리기](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)   
 [이미지 다시 칠하기](../../../../docs/framework/winforms/advanced/recoloring-images.md)