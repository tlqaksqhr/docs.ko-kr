---
title: "방법: 빗살 무늬로 도형 채우기"
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
- patterns [Windows Forms], adding to shapes
- shapes [Windows Forms], filling with patterns
- brushes [Windows Forms], using hatch brushes
ms.assetid: 9c8300ff-187b-404f-af1f-ebd499f5b16f
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 36ee5b7152dabc7dcd1e0c844e8549eb03aa0045
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-fill-a-shape-with-a-hatch-pattern"></a>방법: 빗살 무늬로 도형 채우기
빗살 무늬 두 가지 색에서 만들어진: 배경색과 배경 위에 패턴을 형성 하는 줄 하나에 대 한 합니다. 빗살 무늬로 닫힌된 셰이프를 채울를 사용 하 여 한 <xref:System.Drawing.Drawing2D.HatchBrush> 개체입니다. 다음 예제에는 빗살 무늬로 타원을 채우는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 <xref:System.Drawing.Drawing2D.HatchBrush.%23ctor%2A> 생성자에는 세 가지 인수: 해치 스타일, 해치 줄의 색 및 배경의 색입니다. 해치 스타일 인수로 사용할 수 있는 모든 값의 <xref:System.Drawing.Drawing2D.HatchStyle> 열거형입니다. 에 50 개 이상의 요소가 <xref:System.Drawing.Drawing2D.HatchStyle> 열거형; 몇 가지 요소는 다음 목록에 표시 됩니다.  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.Vertical>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.BackwardDiagonal>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.Cross>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.DiagonalCross>  
  
 다음 그림에서는 채워진된 타원을 보여 줍니다.  
  
 ![패턴 해치](../../../../docs/framework/winforms/advanced/media/hatch1.png "hatch1")  
  
 [!code-csharp[System.Drawing.UsingABrush#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.UsingABrush#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.PaintEventArgs> 이벤트 처리기의 매개 변수인 `e`<xref:System.Windows.Forms.Control.Paint>가 필요합니다.  
  
## <a name="see-also"></a>참고 항목  
 [브러시를 사용하여 도형 채우기](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)
