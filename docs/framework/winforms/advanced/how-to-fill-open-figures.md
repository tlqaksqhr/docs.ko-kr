---
title: "방법: 열린 그림 채우기 | Microsoft Docs"
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
  - "그림, 채우기"
  - "열린 그림, 채우기"
ms.assetid: 5a36b0e4-f1f4-46c0-a85a-22ae98491950
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# 방법: 열린 그림 채우기
<xref:System.Drawing.Drawing2D.GraphicsPath> 개체를 <xref:System.Drawing.Graphics.FillPath%2A> 메서드에 전달하여 경로를 채울 수 있습니다.  <xref:System.Drawing.Graphics.FillPath%2A> 메서드에서는 경로에 현재 설정되어 있는 채우기 모드\(alternate 또는 winding\)에 따라 경로를 채웁니다.  경로에 열린 그림이 있으면 이 그림이 닫혀 있는 것처럼 경로가 채워집니다.  즉, [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]에서는 끝점과 시작점을 직선으로 연결하여 열린 그림을 닫습니다.  
  
## 예제  
 아래 예제에서는 열린 그림 하나\(원호\)와 닫힌 그림 하나\(타원\)로 이루어진 경로를 만듭니다.  <xref:System.Drawing.Graphics.FillPath%2A> 메서드는 기본 채우기 모드인 <xref:System.Drawing.Drawing2D.FillMode>에 따라 경로를 채웁니다.  
  
 다음 그림은 예제 코드의 실행 결과를 보여 줍니다.  여기에서는 열린 그림의 끝점과 시작점을 직선으로 연결하여 이 그림이 닫혀 있는 것처럼 경로를 채웁니다\(<xref:System.Drawing.Drawing2D.FillMode> 모드 사용\).  
  
 ![열린 경로 채우기](../../../../docs/framework/winforms/advanced/media/fillopenpath.png "FillOpenPath")  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#11)]  
  
## 코드 컴파일  
 앞의 예제는 Windows Forms에서 사용해야 하며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`를 필요로 합니다.  
  
## 참고 항목  
 <xref:System.Drawing.Drawing2D.GraphicsPath>   
 [GDI\+의 그래픽 경로](../../../../docs/framework/winforms/advanced/graphics-paths-in-gdi.md)