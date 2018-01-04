---
title: "방법: 그라데이션에 감마 보정 적용"
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
- gradient brushes [Windows Forms], gamma correction
- gradients [Windows Forms], gamma correction
ms.assetid: da4690e7-5fac-4fd2-b3f0-5cb35c165b92
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6321894c86f340154bd37f50e81ea8a58a2e0896
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-apply-gamma-correction-to-a-gradient"></a>방법: 그라데이션에 감마 보정 적용
브러시의 설정 하 여 선형 그라데이션 브러시에 대 한 감마 보정을 사용 하도록 설정할 수 있습니다 <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> 속성을 `true`합니다. 감마 보정을 사용 하지 않도록 설정 하 여 수는 <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> 속성을 `false`합니다. 감마 보정은 기본적으로 비활성화 되어 있습니다.  
  
## <a name="example"></a>예  
 선형 그라데이션 브러시를 만들고 해당 브러시를 사용 하 여 두 개의 사각형에 맞게는 예제입니다. 첫 번째 사각형 감마 보정 하지 않고 채워지고 두 번째 사각형 감마 보정 채워집니다.  
  
 다음 그림에서는 두 개의 채워진된 사각형을 보여 줍니다. 감마 보정 없는 위쪽 사각형 중간에 어두운 나타납니다. 감마 보정 있는 아래 사각형 농도가 좀 더 균일에 나타납니다.  
  
 ![그라데이션](../../../../docs/framework/winforms/advanced/media/gammagradient1.png "gammagradient1")  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingaGradientBrush#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`가 필요합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Drawing.Drawing2D.LinearGradientBrush>  
 [그라데이션 브러시를 사용하여 도형 채우기](../../../../docs/framework/winforms/advanced/using-a-gradient-brush-to-fill-shapes.md)
