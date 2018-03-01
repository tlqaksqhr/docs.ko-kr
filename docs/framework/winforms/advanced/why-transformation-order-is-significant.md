---
title: "변형 순서의 중요성"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- transformations [Windows Forms], order signficance
ms.assetid: 37d5f9dc-a5cf-4475-aa5d-34d714e808a9
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: cd3363a1afb8658ed3bb27359259cb752464507d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="why-transformation-order-is-significant"></a>변형 순서의 중요성
단일 <xref:System.Drawing.Drawing2D.Matrix> 개체는 단일 변환 또는 일련의 변환 저장할 수 있습니다. 후자 보다 복합 변환을 이라고 합니다. 복합 변환 매트릭스 개별 변환 행렬을 곱하여 구합니다.  
  
## <a name="composite-transform-examples"></a>복합 변환 예제  
 복합 변환에서 개별 변환의 순서가 중요 합니다. 예를 들어 하면 먼저 회전, 크기 조정을 차례로 변환, 메시지가 다른 결과 보다 먼저 변환 하는 경우 다음 회전 다음 크기를 조정 합니다. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], 합성 변형 왼쪽에서 오른쪽에 빌드됩니다. S, R, 및 T 크기 조정, 회전 및 변환 행렬을 각각은, 한 다음 제품 SRT 순서에 따라 해당 복합 변환 매트릭스 해당 첫 번째 눈금, 다음 회전 경우 변환 합니다. 제품에 의해 생성 되는 매트릭스 SRT는 TR 제품에 의해 생성 되는 매트릭스와에서 다릅니다.  
  
 순서는 중요 한 가지 이유는 회전 및 배율 조정 같은 변환 좌표계의 원점을 기준으로 수행 됩니다. 원본에서 멀리 이동 된 개체를 확장 합니다. 결과 서로 다르게 생성 중심이 원점 하는 개체 크기를 조정 합니다. 마찬가지로, 중심이 원점 있는 개체를 회전 원본에서 멀리 이동 된 개체를 회전 다른 결과 생성 합니다.  
  
 다음 예제에서는 크기 조정, 회전, 순서 대로) (에서 이동 하는 복합 변환을 결합 합니다. 인수 <xref:System.Drawing.Drawing2D.MatrixOrder.Append> 에 전달 되는 <xref:System.Drawing.Graphics.RotateTransform%2A> 메서드 크기 조정을 회전을 따를 것을 나타냅니다. 마찬가지로, 인수 <xref:System.Drawing.Drawing2D.MatrixOrder.Append> 에 전달 되는 <xref:System.Drawing.Graphics.TranslateTransform%2A> 메서드 변환 회전을 따를 것을 나타냅니다. <xref:System.Drawing.Drawing2D.MatrixOrder.Append>및 <xref:System.Drawing.Drawing2D.MatrixOrder.Prepend> 의 구성원은 <xref:System.Drawing.Drawing2D.MatrixOrder> 열거형입니다.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.MiscLegacyTopics#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#21)]  
  
 다음 예에서는 앞의 예제와 동일한 메서드를 호출 하지만 호출 하 여 순서가 반대로 바뀌었습니다. 작업의 결과 순서 회전, 첫 번째 눈금 보다에서 매우 다른 결과 생성 하 눈금 회전, 차례로 번역 먼저 변환 됩니다.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.MiscLegacyTopics#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#22)]  
  
 복합 변환에서 개별 변환의 순서를 반대로 바꾸려면 가지 방법은 메서드 호출의 시퀀스의 순서를 반대로 하는 것입니다. 작업의 순서를 제어 하는 두 번째 방법은 행렬 order 인수를 변경 하는 것입니다. 다음 예제는 점을 제외 하 고 앞의 예제와 동일 <xref:System.Drawing.Drawing2D.MatrixOrder.Append> 로 변경 되었습니다 <xref:System.Drawing.Drawing2D.MatrixOrder.Prepend>합니다. 행렬 곱 SRT, 여기서 S, R, T는 회전, 크기 조정에 대 한 행렬 이며 곱은 순서로 수행 됩니다. 복합 변환의 순서는 첫 번째 눈금 회전 차례로 변환 합니다.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#23)]
 [!code-vb[System.Drawing.MiscLegacyTopics#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#23)]  
  
 바로 위 예의 결과이 항목의 첫 번째 예의 결과로는 동일 합니다. 메서드 호출의 순서와 행렬 곱하기의 순서를 둘 다 바꾸었기 때문입니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Drawing.Drawing2D.Matrix>  
 [좌표계 및 변형](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)  
 [관리 GDI+에서 변형 사용](../../../../docs/framework/winforms/advanced/using-transformations-in-managed-gdi.md)
