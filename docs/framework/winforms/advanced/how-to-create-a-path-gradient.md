---
title: "방법: 경로 그라데이션 만들기 | Microsoft Docs"
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
  - "그라데이션, 경로 만들기"
  - "그래픽 경로, 그라데이션 만들기"
  - "경로 그라데이션, 만들기"
ms.assetid: 1948e834-e104-481c-b71d-d8aa9e4d106e
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# 방법: 경로 그라데이션 만들기
<xref:System.Drawing.Drawing2D.PathGradientBrush> 클래스를 사용하면 점진적으로 변하는 색으로 도형을 채우는 방식을 사용자 지정할 수 있습니다.  예를 들어, 경로의 중앙과 경로 경계에 대해 각각 다른 색을 지정할 수 있습니다.  경로의 경계를 따라 여러 지점에 각각 별도의 색을 지정할 수도 있습니다.  
  
> [!NOTE]
>  [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]에서 경로란 <xref:System.Drawing.Drawing2D.GraphicsPath> 개체에서 유지하는 일련의 선과 곡선을 의미합니다.  [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 경로에 대한 자세한 내용은 [GDI\+의 그래픽 경로](../../../../docs/framework/winforms/advanced/graphics-paths-in-gdi.md) 및 [경로 구성 및 그리기](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)를 참조하십시오.  
  
### 경로 그라데이션으로 타원을 채우려면  
  
-   아래 예제에서는 경로 그라데이션 브러시로 타원을 채웁니다.  중앙의 색은 파랑으로 설정하고 경계의 색은 바다색으로 설정합니다.  아래 그림에 채워진 타원이 나와 있습니다.  
  
     ![그라데이션 경로](../../../../docs/framework/winforms/advanced/media/pathgradient1.png "pathgradient1")  
  
     기본적으로 경로 그라데이션 브러시는 경로의 경계를 벗어나지 않습니다.  경로 그라데이션 브러시를 사용하여 경로의 경계를 넘는 그림을 채울 경우 경로를 벗어나는 화면 영역은 채워지지 않습니다.  
  
     다음 그림은 다음 코드의 <xref:System.Drawing.Graphics.FillEllipse%2A> 호출을 `e.Graphics.FillRectangle(pthGrBrush, 0, 10, 200, 40)`로 변경할 경우 일어나는 상황을 보여 줍니다.  
  
     ![그라데이션 경로](../../../../docs/framework/winforms/advanced/media/pathgradient2.png "pathgradient2")  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#11)]
     [!code-vb[System.Drawing.UsingaGradientBrush#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#11)]  
  
     앞의 코드 예제는 Windows Forms에서 사용해야 하며 <xref:System.Windows.Forms.PaintEventHandler>의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> e를 필요로 합니다.  
  
### 경계에 점을 지정하려면  
  
-   아래 예제에서는 별 모양의 경로에서 경로 그라데이션 브러시를 만듭니다.  코드에서는 <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterColor%2A> 속성을 설정하여 별의 중앙 부분 색을 빨강으로 지정합니다.  그런 다음 `colors` 배열에 저장된 다양한 색을 `points` 배열에 있는 각 점에 적용하도록 <xref:System.Drawing.Drawing2D.PathGradientBrush.SurroundColors%2A> 속성을 설정합니다.  이 코드의 마지막 문에서는 별 모양의 경로를 경로 그라데이션 브러시로 채웁니다.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#12)]
     [!code-vb[System.Drawing.UsingaGradientBrush#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#12)]  
  
-   다음 예제에서는 코드에서 <xref:System.Drawing.Drawing2D.GraphicsPath> 개체 없이 경로 그라데이션을 그립니다.  이 예제에서는 특정 <xref:System.Drawing.Drawing2D.PathGradientBrush.%23ctor%2A> 생성자에 점의 배열을 전달하지만 <xref:System.Drawing.Drawing2D.GraphicsPath> 개체는 필요 없습니다.  또한 <xref:System.Drawing.Drawing2D.PathGradientBrush>는 경로가 아니라 사각형을 채우는 데 사용됩니다.  브러시를 정의하는 데 사용된 닫힌 경로보다 사각형이 크므로 사각형의 일부가 브러시로 칠해지지 않습니다.  아래 그림에서는 사각형 전체 및 사각형에서 경로 그라데이션 브러시로 칠해지는 부분을 보여 줍니다. 사각형 전체는 점선으로 표시되어 있습니다.  
  
     ![그라데이션](../../../../docs/framework/winforms/advanced/media/gradient4.png "gradient4")  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#13](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#13)]
     [!code-vb[System.Drawing.UsingaGradientBrush#13](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#13)]  
  
### 경로 그라데이션을 사용자 지정하려면  
  
-   경로 그라데이션 브러시를 사용자 지정하는 방법 중 하나는 <xref:System.Drawing.Drawing2D.PathGradientBrush.FocusScales%2A> 속성을 설정하는 것입니다.  이 속성에서는 주 경로 안에 있는 내부 경로를 지정합니다.  중점 뿐만 아니라 내부 경로의 모든 부분이 중앙 색으로 채워집니다.  
  
     아래 예제에서는 타원형 경로를 기반으로 경로 그라데이션 브러시를 만듭니다.  코드에서는 경계의 색을 파랑으로, 중앙의 색을 바다색으로 설정한 다음 경로 그라데이션 브러시를 사용하여 타원형 경로를 채웁니다.  
  
     그런 다음, 경로 그라데이션 브러시의 포커스 배율을 설정합니다.  x 포커스 배율을 0.3으로, y 포커스 배율을 0.8로 설정합니다.  코드에서는 <xref:System.Drawing.Graphics.FillPath%2A> 이후의 호출에서 첫 번째 타원의 오른쪽에 있는 타원을 채울 수 있도록 먼저 <xref:System.Drawing.Graphics> 개체의 <xref:System.Drawing.Graphics.TranslateTransform%2A> 메서드를 호출합니다.  
  
     주 타원과 중점이 동일한 작은 타원을 생각해 보면 포커스 배율의 효과를 쉽게 이해할 수 있습니다.  작은 타원\(안쪽 타원\)은 주 타원의 중점을 기준으로 가로로 0.3, 세로로 0.8배 축소된 타원입니다.  바깥쪽 타원의 경계에서 안쪽 타원의 경계로 가면서 색이 파랑에서 바다색으로 점차 변합니다.  안쪽 타원의 경계에서 공유 중점까지는 변하지 않고 바다색이 유지됩니다.  
  
     다음 그림에서는 아래 코드를 실행한 결과를 보여 줍니다.  왼쪽 타원에서는 중점만 바다색이고  오른쪽 타원에서는 내부 경로 안쪽의 모든 곳이 바다색입니다.  
  
 ![그라데이션](../../../../docs/framework/winforms/advanced/media/focusscales1nogamma.png "focusscales1NoGamma")  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#14](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#14)]
 [!code-vb[System.Drawing.UsingaGradientBrush#14](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#14)]  
  
### 보간을 사용하여 사용자 지정하려면  
  
-   삽입할 색의 배열과 삽입할 위치의 배열을 지정하여 경로 그라데이션 브러시를 사용자 지정할 수도 있습니다.  
  
     아래 예제에서는 삼각형을 기반으로 경로 그라데이션 브러시를 만듭니다.  이 코드에서는 경로 그라데이션 브러시의 <xref:System.Drawing.Drawing2D.PathGradientBrush.InterpolationColors%2A> 속성을 설정하여 보간 색의 배열\(진한 녹색, 바다색, 파랑\)과 보간 위치의 배열\(0, 0.25, 1\)을 지정합니다.  삼각형의 경계에서 중점으로 가면서 진한 녹색에서 바다색으로 점차 변한 다음 바다색에서 파랑으로 변합니다.  진한 녹색에서 바다색으로 변해가는 거리는 진한 녹색에서 파랑으로 변해가는 전체 거리의 25%입니다.  
  
     아래 그림에서는 사용자 지정 경로 그라데이션 브러시로 채운 삼각형을 보여 줍니다.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#15](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#15)]
     [!code-vb[System.Drawing.UsingaGradientBrush#15](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#15)]  
  
### 중점을 설정하려면  
  
-   기본적으로 경로 그라데이션 브러시의 중점은 브러시를 만드는 데 사용되는 경로의 중앙입니다.  <xref:System.Drawing.Drawing2D.PathGradientBrush> 클래스의 <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A> 속성을 설정하여 중점의 위치를 변경할 수 있습니다.  
  
     아래 예제에서는 타원을 기반으로 경로 그라데이션 브러시를 만듭니다.  이 예제에서는 타원의 중점이 \(70, 35\)이지만 경로 그라데이션 브러시의 중점을 \(120, 40\)으로 설정합니다.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#16](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#16)]
     [!code-vb[System.Drawing.UsingaGradientBrush#16](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#16)]  
  
     아래 그림에서는 채워진 타원과 경로 그라데이션 브러시의 중점을 보여 줍니다.  
  
     ![그라데이션 경로](../../../../docs/framework/winforms/advanced/media/pathgradient5.png "pathgradient5")  
  
-   경로 그라데이션 브러시의 중점을 브러시를 만드는 데 사용한 경로 밖에 있는 위치로 설정할 수도 있습니다.  다음 예제에서는 위 코드의 <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A> 속성을 설정하도록 호출을 바꿉니다.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#17](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#17)]
     [!code-vb[System.Drawing.UsingaGradientBrush#17](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#17)]  
  
     이렇게 변경한 결과가 아래 그림에 나와 있습니다.  
  
     ![그라데이션 경로](../../../../docs/framework/winforms/advanced/media/pathgradient6.png "pathgradient6")  
  
     위 그림의 타원에서 가장 오른쪽에 있는 점들은 순수한 파랑과 매우 가깝긴 해도 순수한 파랑이 아닙니다.  순수한 파랑\(0, 0, 255\)이 되는 점\(145, 35\)까지 그라데이션에서 색을 채운 것처럼 보이지만,  경로 그라데이션 브러시에서는 경로 안쪽만 칠하기 때문에 \(145, 35\)까지 색이 칠해지지는 않습니다.  
  
## 코드 컴파일  
 앞의 예제는 Windows Forms에서 사용해야 하며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`를 필요로 합니다.  
  
## 참고 항목  
 [그라데이션 브러시를 사용하여 도형 채우기](../../../../docs/framework/winforms/advanced/using-a-gradient-brush-to-fill-shapes.md)