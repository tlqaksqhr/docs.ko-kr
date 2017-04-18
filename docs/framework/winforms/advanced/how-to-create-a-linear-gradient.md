---
title: "방법: 선형 그라데이션 만들기 | Microsoft Docs"
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
  - "색, 선형 그라데이션 만들기"
  - "그라데이션"
  - "그라데이션, 선형 만들기"
  - "선형 그라데이션, 만들기"
ms.assetid: 6c88e1cc-1217-4399-ac12-cb37592b9f01
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# 방법: 선형 그라데이션 만들기
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]에서는 가로, 세로 및 대각선 방향의 선형 그라데이션을 제공합니다.  기본적으로 선형 그라데이션에서는 색이 균일하게 변합니다.  그러나 색이 균일하지 않은 방식으로 변하도록 선형 그라데이션을 사용자 지정할 수도 있습니다.  
  
 다음 예제에서는 선, 타원 및 사각형을 가로 방향의 선형 그라데이션 브러시로 채웁니다.  
  
 <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> 생성자는 네 개의 인수를 받습니다\(두 개의 점과 두 가지 색\).  첫 번째 점\(0, 10\)은 첫 번째 색\(빨강\)과 연결되고 두 번째 점\(200, 10\)은 두 번째 색\(파랑\)과 연결됩니다.  위의 코드에서 짐작할 수 있듯이 점 \(0, 10\)에서 점 \(200, 10\)로 연결된 선은 빨강에서 파랑으로 점진적으로 변합니다.  
  
 점 \(50, 10\)과 점 \(200, 10\)에서 10이라는 숫자는 중요하지 않습니다.  여기에서는 두 점이 수평으로 연결되도록 두 번째 좌표가 동일하다는 사실이 중요합니다.  타원과 사각형에서도 가로 좌표가 0에서 200으로 이동함에 따라 색이 빨강에서 파랑으로 점진적으로 변합니다.  
  
 아래 그림에서는 위 예제의 선, 타원 및 사각형을 보여 줍니다.  그림에서 보듯이 가로 좌표가 200을 초과하면 색 그라데이션이 다시 반복됩니다.  
  
 ![선형 그라데이션](../../../../docs/framework/winforms/advanced/media/cslineargradient1.png "cslineargradient1")  
  
### 가로 선형 그라데이션을 사용하려면  
  
-   불투명 빨강과 불투명 파랑을 각각 세 번째 인수와 네 번째 인수로 전달합니다.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#21)]
     [!code-vb[System.Drawing.UsingaGradientBrush#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#21)]  
  
 앞의 예제에서는 가로 좌표 0에서 가로 좌표 200으로 이동함에 따라 선형으로 색 구성 요소가 변합니다.  예를 들어 점의 첫 번째 좌표가 0과 200의 중간이면 해당 점의 파랑 구성 요소 값은 0과 255의 중간 값입니다.  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]를 사용하면 그라데이션의 한 쪽 가장자리에서 다른 쪽 가장자리로 이동하면서 색이 변하는 방식을 조정할 수 있습니다.  예를 들어, 다음 표에 나열된 값에 따라 검정에서 빨강으로 변해가는 그라데이션 브러시를 만들 수 있습니다.  
  
|가로 좌표|RGB 구성 요소|  
|-----------|---------------|  
|0|\(0, 0, 0\)|  
|40|\(128, 0, 0\)|  
|200|\(255, 0, 0\)|  
  
 이 예에서 가로 좌표가 0에서 200 사이의 20%되는 지점에 도달했을 때 빨강 구성 요소의 농도가 절반으로 줄어든 것을 알 수 있습니다.  
  
 다음 예제에서는 <xref:System.Drawing.Drawing2D.LinearGradientBrush> 개체의 <xref:System.Drawing.Drawing2D.LinearGradientBrush.Blend%2A> 속성을 설정하여 세 가지 상대 농도를 세 가지 상대 위치와 연결합니다.  위 표에 나와 있는 것처럼 상대 농도 0.5는 상대 위치 0.2와 연결됩니다.  아래 코드에서는 타원과 사각형을 그라데이션 브러시로 채웁니다.  
  
 아래 그림에서는 위 코드를 사용하여 만든 타원과 사각형을 보여 줍니다.  
  
 ![선형 그라데이션](../../../../docs/framework/winforms/advanced/media/cslineargradient2.png "cslineargradient2")  
  
### 선형 그라데이션을 사용자 지정하려면  
  
-   불투명 검정과 불투명 빨강을 각각 세 번째 인수와 네 번째 인수로 전달합니다.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#22)]
     [!code-vb[System.Drawing.UsingaGradientBrush#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#22)]  
  
 앞 예제에서는 그라데이션이 가로 방향으로 적용되었습니다.  세로 방향 그라데이션과 대각선 방향 그라데이션을 정의할 수도 있습니다.  
  
 다음 예제에서는 점 \(0, 0\)과 점 \(200, 100\)을 <xref:System.Drawing.Drawing2D.LinearGradientBrush.%23ctor%2A> 생성자에 전달합니다.  파랑은 점 \(0, 0\)에 연결되고 녹색은 점 \(200, 100\)에 연결됩니다.  펜 굵기가 10인 선과 타원을 선형 그라데이션 브러시로 채웁니다.  
  
 아래 그림에서는 위 코드를 사용하여 만든 선과 타원을 보여 줍니다.  이 그림에서 타원의 색은 점 \(0, 0\)과 점 \(200, 100\)을 잇는 선과 평행하는 선을 따라 가면서 점차 변합니다.  
  
 ![선형 그라데이션](../../../../docs/framework/winforms/advanced/media/cslineargradient3.png "cslineargradient3")  
  
### 대각선 선형 그라데이션을 만들려면  
  
-   불투명 파랑과 불투명 녹색을 각각 세 번째 인수와 네 번째 인수로 전달합니다.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#23)]
     [!code-vb[System.Drawing.UsingaGradientBrush#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#23)]  
  
## 참고 항목  
 [그라데이션 브러시를 사용하여 도형 채우기](../../../../docs/framework/winforms/advanced/using-a-gradient-brush-to-fill-shapes.md)   
 [Windows Forms의 그래픽 및 그리기](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)