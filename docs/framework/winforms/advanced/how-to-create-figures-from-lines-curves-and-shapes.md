---
title: "방법: 선, 곡선 및 도형으로 그림 만들기 | Microsoft Docs"
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
  - "그림, 선으로 만들기"
  - "그림, 도형으로 만들기"
ms.assetid: 82fd56c7-b443-4765-9b7c-62ce030656ec
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# 방법: 선, 곡선 및 도형으로 그림 만들기
그림을 만들려면 <xref:System.Drawing.Drawing2D.GraphicsPath>를 만든 다음 <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> 및 <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A>와 같은 메서드를 호출하여 기본 요소를 경로에 추가합니다.  
  
## 예제  
 다음 코드 예제에서는 다음과 같이 그림이 포함된 경로를 만듭니다.  
  
-   첫 번째 예제에서는 그림이 한 개 포함된 경로를 만듭니다.  이 그림은 원호 한 개로 이루어집니다.  원호의 전진 각도는 기본 좌표계에서 시계 반대 방향으로 180도입니다.  
  
-   두 번째 예제에서는 그림이 두 개 포함된 경로를 만듭니다.  첫 번째 그림은 원호와 선이 연결되어 구성되고,  두 번째 그림은 선, 곡선, 선이 차례로 연결되어 구성됩니다.  첫 번째 그림은 왼쪽이 열려 있고 두 번째 그림은 닫혀 있습니다.  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#21)]  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#22)]  
  
## 코드 컴파일  
 앞의 예제는 Windows Forms에서 사용해야 하며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`를 필요로 합니다.  
  
## 참고 항목  
 <xref:System.Drawing.Drawing2D.GraphicsPath>   
 [경로 구성 및 그리기](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)   
 [펜을 사용하여 선과 도형 그리기](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)