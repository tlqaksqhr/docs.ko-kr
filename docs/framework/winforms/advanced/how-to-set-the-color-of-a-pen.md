---
title: "방법: 펜 색 설정"
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
- cpp
helpviewer_keywords:
- pens [Windows Forms], setting color
- colored pens
ms.assetid: a9df06f9-a6d5-4d9b-a2d1-583943540775
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 452e88b4b41a22cc78f73e120e49468e4f4dad56
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-the-color-of-a-pen"></a>방법: 펜 색 설정
기존의 색을 변경 하는이 예제 <xref:System.Drawing.Pen> 개체  
  
## <a name="example"></a>예제  
 [!code-cpp[System.Drawing.ConceptualHowTos#9](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#9)]
 [!code-csharp[System.Drawing.ConceptualHowTos#9](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#9)]
 [!code-vb[System.Drawing.ConceptualHowTos#9](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#9)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   A <xref:System.Drawing.Pen> 라는 개체 `myPen`합니다.  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 호출 해야 <xref:System.Drawing.Pen.Dispose%2A> 시스템 리소스를 사용 하는 개체에 (같은 <xref:System.Drawing.Pen> 개체)을 사용 하 여 완료 한 후 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Drawing.Pen>  
 [그래픽 프로그래밍 시작](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [방법: 펜 만들기](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)  
 [펜을 사용하여 선과 도형 그리기](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)  
 [GDI+의 펜, 선 및 사각형](../../../../docs/framework/winforms/advanced/pens-lines-and-rectangles-in-gdi.md)
