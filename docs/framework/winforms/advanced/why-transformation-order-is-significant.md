---
title: "변환 순서의 중요성 | Microsoft Docs"
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
  - "변환, 순서 중요성"
ms.assetid: 37d5f9dc-a5cf-4475-aa5d-34d714e808a9
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# 변환 순서의 중요성
단일 <xref:System.Drawing.Drawing2D.Matrix> 개체에 단일 변환을 저장할 수도 있고 일련의 여러 변환을 저장할 수도 있습니다.  일련의 여러 변환을 복합 변환이라고 합니다.  복합 변환의 매트릭스는 개별 변환의 매트릭스를 곱한 결과입니다.  
  
## 복합 변환 예제  
 복합 변환에서 개별 변환의 순서는 매우 중요합니다.  예를 들어, 회전, 배율 조정, 이동 순으로 변환을 수행할 경우와 이동, 회전, 배율 조정 순으로 변환을 수행할 경우의 결과는 서로 다릅니다.  [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]에서 복합 변환은 왼쪽에서 오른쪽으로 수행됩니다.  S, R 및 T가 각각 배율 조정, 회전, 이동 매트릭스인 경우, SRT 곱은 배율 조정, 회전, 이동의 순서로 변환을 수행하는 복합 변환의 매트릭스입니다.  SRT 곱에서 생성되는 매트릭스와 TRS 곱에서 생성되는 매트릭스는 서로 다릅니다.  
  
 순서가 중요한 이유 중 하나는 회전이나 배율 조정 같은 변환이 좌표계의 원점을 기준으로 수행된다는 것입니다.  중심이 원점에 있는 개체의 배율을 조정한 결과와 원점에서 멀리 있는 개체의 배율을 조정한 결과는 서로 다르게 나타납니다.  마찬가지로, 중점이 원점에 있는 개체를 회전한 결과와 원점에서 멀리 있는 개체를 회전한 결과는 서로 다르게 나타납니다.  
  
 아래 예제에서는 배율 조정, 회전, 이동의 순서로 변환을 수행하는 복합 변환을 보여 줍니다.  <xref:System.Drawing.Graphics.RotateTransform%2A> 메서드에 전달되는 <xref:System.Drawing.Drawing2D.MatrixOrder> 인수는 배율을 조정한 다음에 회전 변환을 수행하도록 지정합니다.  마찬가지로 <xref:System.Drawing.Graphics.TranslateTransform%2A> 메서드에 전달되는 <xref:System.Drawing.Drawing2D.MatrixOrder> 인수는 회전 다음에 이동 변환을 수행하도록 지정합니다.  <xref:System.Drawing.Drawing2D.MatrixOrder> 및 <xref:System.Drawing.Drawing2D.MatrixOrder>는 <xref:System.Drawing.Drawing2D.MatrixOrder> 열거형의 멤버입니다.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.MiscLegacyTopics#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#21)]  
  
 아래 예제에서는 위 예제와 동일한 메서드를 호출하지만 호출 순서는 반대입니다.  따라서 이동, 회전, 배율 조정의 순으로 변환이 수행되므로 배율 조정, 회전, 이동 순으로 변환을 수행하는 앞의 예제와는 다른 결과가 나타납니다.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.MiscLegacyTopics#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#22)]  
  
 복합 변환에서 개별 변환의 순서를 반대로 바꾸는 방법 중 하나는 일련의 메서드 호출 순서를 반대로 바꾸는 것입니다.  두 번째 방법으로, 매트릭스 순서 인수를 변경하여 변환 작업의 순서를 제어할 수도 있습니다.  다음 예제는 <xref:System.Drawing.Drawing2D.MatrixOrder>가 <xref:System.Drawing.Drawing2D.MatrixOrder>로 변경된 것만 제외하면 앞의 예제와 같습니다.  매트릭스 곱은 SRT 순으로 수행됩니다. 이 경우 S, R, T는 각각 배율 조정, 회전, 이동을 나타내는 매트릭스입니다.  즉, 배율 조정, 회전, 이동의 순서로 복합 변환이 수행됩니다.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.MiscLegacyTopics#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#23)]  
  
 위 예제의 결과는 이 항목에 있는 첫 번째 예제의 결과와 동일합니다.  메서드 호출의 순서와 매트릭스 곱의 순서를 모두 반대로 바꾸었기 때문에 이러한 결과가 나타납니다.  
  
## 참고 항목  
 <xref:System.Drawing.Drawing2D.Matrix>   
 [좌표계 및 변환](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)   
 [관리 GDI\+에서 변환 사용](../../../../docs/framework/winforms/advanced/using-transformations-in-managed-gdi.md)