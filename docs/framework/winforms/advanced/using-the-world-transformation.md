---
title: "전역 변환 사용 | Microsoft Docs"
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
  - "그래픽, 표준 변환"
  - "표준 변환, 예제"
ms.assetid: 1e717711-1361-448e-aa49-0f3ec43110c9
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# 전역 변환 사용
전역 변환은 <xref:System.Drawing.Graphics> 클래스의 속성입니다.  전역 변환을 지정하는 숫자는 3×3 매트릭스를 나타내는 <xref:System.Drawing.Drawing2D.Matrix> 개체에 저장됩니다.  <xref:System.Drawing.Drawing2D.Matrix> 클래스와 <xref:System.Drawing.Graphics> 클래스에는 전역 변환 매트릭스에 숫자를 설정하기 위한 메서드가 여러 개 있습니다.  
  
## 여러 종류의 변환  
 다음 예제의 코드에서는 먼저 50×50 사각형을 만들어 원점\(0, 0\)에 배치합니다.  원점은 클라이언트 영역의 왼쪽 위 모퉁이에 있습니다.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.MiscLegacyTopics#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#11)]  
  
 아래 코드에서는 사각형을 x 방향으로 1.75배 확장하고 y 방향으로 0.5배 축소하는 배율 조정 변환을 적용합니다.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#12)]
 [!code-vb[System.Drawing.MiscLegacyTopics#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#12)]  
  
 이 코드를 실행하면 원래의 사각형보다 x 방향은 더 길고 y 방향은 더 짧은 사각형이 만들어집니다.  
  
 배율을 조정하지 않고 사각형을 회전하려면 아래의 코드를 사용합니다.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#13](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#13)]
 [!code-vb[System.Drawing.MiscLegacyTopics#13](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#13)]  
  
 사각형을 이동하려면 아래의 코드를 사용합니다.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#14](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#14)]
 [!code-vb[System.Drawing.MiscLegacyTopics#14](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#14)]  
  
## 참고 항목  
 <xref:System.Drawing.Drawing2D.Matrix>   
 [좌표계 및 변환](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)   
 [관리 GDI\+에서 변환 사용](../../../../docs/framework/winforms/advanced/using-transformations-in-managed-gdi.md)