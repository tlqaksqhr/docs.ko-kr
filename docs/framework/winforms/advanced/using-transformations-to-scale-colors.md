---
title: "변환을 사용하여 색의 비율 조정 | Microsoft Docs"
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
  - "색, 배율"
  - "변환, 색 비율 조정"
ms.assetid: df23c887-7fd6-4b15-ad94-e30b5bd4b849
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# 변환을 사용하여 색의 비율 조정
배율 조정 변환에서는 네 가지 구성 요소 중 하나 이상에 숫자를 곱합니다.  배율 조정을 나타내는 색 매트릭스 엔트리가 아래 표에 나와 있습니다.  
  
|배율을 조정할 구성 요소|매트릭스 엔트리|  
|-------------------|--------------|  
|빨강|\[0\]\[0\]|  
|녹색|\[1\]\[1\]|  
|파랑|\[2\]\[2\]|  
|알파|\[3\]\[3\]|  
  
## 한 색 배율 조정  
 다음 예제에서는 ColorBars2.bmp 파일에서 <xref:System.Drawing.Image> 개체를 만듭니다.  그런 다음 코드에서는 이미지에 있는 각 픽셀의 파랑 구성 요소에 2를 곱하여 배율을 조정합니다.  변환된 이미지 옆에 원래 이미지가 그려집니다.  
  
 [!code-csharp[System.Drawing.RecoloringImages#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.RecoloringImages#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#41)]  
  
 아래 그림에서 왼쪽은 원래 이미지이고 오른쪽은 배율을 조정한 이미지입니다.  
  
 ![색의 비율 조정](../../../../docs/framework/winforms/advanced/media/colortrans3.png "colortrans3")  
  
 아래 표에는 파랑 구성 요소의 배율을 조정하기 전과 배율 조정 후의 막대 네 개에 대한 색 벡터가 나와 있습니다.  네 번째 색 막대에서 파랑 구성 요소가 0.8에서 0.6으로 변한 것을 알 수 있습니다.  이는 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]에서 결과의 소수 부분만을 유지하기 때문입니다.  예를 들어, \(2\)\(0.8\) \= 1.6이고 1.6의 소수 부분은 0.6입니다.  소수 부분만을 보존하므로 결과는 항상 \[0, 1\] 사이에 있습니다.  
  
|원래 설정|배율 조정 후 이미지|  
|-----------|-----------------|  
|\(0.4, 0.4, 0.4, 1\)|\(0.4, 0.4, 0.8, 1\)|  
|\(0.4, 0.2, 0.2, 1\)|\(0.4, 0.2, 0.4, 1\)|  
|\(0.2, 0.4, 0.2, 1\)|\(0.2, 0.4, 0.4, 1\)|  
|\(0.4, 0.4, 0.8, 1\)|\(0.4, 0.4, 0.6, 1\)|  
  
## 여러 색 배율 조정  
 다음 예제에서는 ColorBars2.bmp 파일에서 <xref:System.Drawing.Image> 개체를 만듭니다.  그런 다음 코드에서는 이미지에 있는 각 픽셀의 빨강, 녹색 및 파랑 구성 요소의 배율을 조정합니다.  빨강 구성 요소는 25%, 녹색 구성 요소는 35%, 파랑 구성 요소는 50%가 줄어듭니다.  
  
 [!code-csharp[System.Drawing.RecoloringImages#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#42)]
 [!code-vb[System.Drawing.RecoloringImages#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#42)]  
  
 아래 그림에서 왼쪽은 원래 이미지이고 오른쪽은 배율을 조정한 이미지입니다.  
  
 ![색의 비율 조정](../../../../docs/framework/winforms/advanced/media/colortrans4.png "colortrans4")  
  
 아래 표에는 빨강, 녹색 및 파랑 구성 요소의 배율을 조정하기 전과 배율 조정 후의 막대 네 개에 대한 색 벡터가 나와 있습니다.  
  
|원래 설정|배율 조정 후 이미지|  
|-----------|-----------------|  
|\(0.6, 0.6, 0.6, 1\)|\(0.45, 0.39, 0.3, 1\)|  
|\(0, 1, 1, 1\)|\(0, 0.65, 0.5, 1\)|  
|\(1, 1, 0, 1\)|\(0.75, 0.65, 0, 1\)|  
|\(1, 0, 1, 1\)|\(0.75, 0, 0.5, 1\)|  
  
## 참고 항목  
 <xref:System.Drawing.Imaging.ColorMatrix>   
 <xref:System.Drawing.Imaging.ImageAttributes>   
 [Windows Forms의 그래픽 및 그리기](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)   
 [이미지 다시 칠하기](../../../../docs/framework/winforms/advanced/recoloring-images.md)