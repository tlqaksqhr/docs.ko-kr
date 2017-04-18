---
title: "방법: 사용자 지정 파선 그리기 | Microsoft Docs"
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
  - "선, 사용자 지정"
  - "선, 파선"
  - "선, 그리기"
ms.assetid: cd0ed96a-cce4-47b9-b58a-3bae2e3d1bee
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# 방법: 사용자 지정 파선 그리기
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]에서는 <xref:System.Drawing.Drawing2D.DashStyle> 열거형에 나열된 몇 가지 대시 스타일을 제공합니다.  이러한 표준 대시 스타일이 적합하지 않은 경우에는 사용자 지정 대시 패턴을 만들 수 있습니다.  
  
## 예제  
 사용자 지정 파선을 그리려면 대시 및 공백의 길이를 배열에 넣은 다음 이 배열을 <xref:System.Drawing.Pen> 개체의 <xref:System.Drawing.Pen.DashPattern%2A> 속성 값으로 지정합니다.  다음 예제에서는  `{5, 2, 15, 4}` 배열을 기반으로 사용자 지정 파선을 그립니다.  배열의 각 요소에 펜 굵기 5를 곱하면 `{25, 10, 75, 20}`이 됩니다.  길이 25인 대시와 75인 대시가 번갈아 표시되고 길이 10인 공백과 20인 공백이 번갈아 사용됩니다.  
  
 아래 그림에 이 예제에서 그린 파선이 나와 있습니다.  마지막 대시는 25단위보다 작아야 선이 \(405, 5\)에서 끝날 수 있습니다.  
  
 ![펜](../../../../docs/framework/winforms/advanced/media/pens6.png "pens6")  
  
 [!code-csharp[System.Drawing.UsingAPen#51](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.UsingAPen#51](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#51)]  
  
## 코드 컴파일  
 Windows Form을 만들고 이 폼의 <xref:System.Windows.Forms.Control.Paint> 이벤트를 처리한 다음  위의 코드를 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기에 붙여넣고  
  
## 참고 항목  
 [펜을 사용하여 선과 도형 그리기](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)