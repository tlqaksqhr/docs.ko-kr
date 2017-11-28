---
title: "방법: 사용자 지정 파선 그리기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lines [Windows Forms], custom
- lines [Windows Forms], drawing
- lines [Windows Forms], dashed
ms.assetid: cd0ed96a-cce4-47b9-b58a-3bae2e3d1bee
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 90fcc99414e8d5c9542d643677c85d4ff670f50f
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-draw-a-custom-dashed-line"></a>방법: 사용자 지정 파선 그리기
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]에 나열 된 몇 가지 대시 스타일을 제공 된 <xref:System.Drawing.Drawing2D.DashStyle> 열거형입니다. 해당 표준 대시 스타일 사용자 요구에 적합 하지 않는 경우 사용자 지정 대시 패턴을 만들 수 있습니다.  
  
## <a name="example"></a>예제  
 사용자 지정 파선 그리기, 대시와 공백의 길이 배열에 배치할 및의 값으로 배열을 할당는 <xref:System.Drawing.Pen.DashPattern%2A> 속성은 <xref:System.Drawing.Pen> 개체입니다. 다음 예제에서는 배열을 기반으로 하는 사용자 지정 파선된 선을 그립니다 `{5, 2, 15, 4}`합니다. 배열 요소의 5의 펜 너비를 곱하면 경우 얻게 `{25, 10, 75, 20}`합니다. 표시 된 대시 25와 75, 사이의 길이가 대체 하 고 길이가 10과 20 사이의 공간을 교대로 할당 합니다.  
  
 다음은 결과 파선입니다. 마지막 대시 줄 끝 수 있도록 25 단위 미만 이어야 하는 참고 (405, 5).  
  
 ![펜](../../../../docs/framework/winforms/advanced/media/pens6.gif "pens6")  
  
 [!code-csharp[System.Drawing.UsingAPen#51](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.UsingAPen#51](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 Windows Form 만들기 및 폼의 처리 <xref:System.Windows.Forms.Control.Paint> 이벤트입니다. 앞의 코드에 붙여는 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기입니다.  
  
## <a name="see-also"></a>참고 항목  
 [펜을 사용하여 선과 도형 그리기](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
