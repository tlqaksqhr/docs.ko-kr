---
title: "방법: Canvas의 연결된 속성을 사용하여 자식 요소 배치"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- attached properties [WPF Designer]
- Canvas control [WPF], attached properties
ms.assetid: 48f1d25d-3820-4107-a4cc-d6c1e5664a44
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5314f39c3012826f25fa6c64baf7eb8e42329f58
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-the-attached-properties-of-canvas-to-position-child-elements"></a>방법: Canvas의 연결된 속성을 사용하여 자식 요소 배치
연결된 된 속성을 사용 하는 방법을 보여 주는이 예제 <xref:System.Windows.Controls.Canvas> 자식 요소의 위치입니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 4 개의 <xref:System.Windows.Controls.Button> 부모의 자식 요소로 요소 <xref:System.Windows.Controls.Canvas>합니다. 이 고유한 연결 된 속성을 각 자식 요소 <xref:System.Windows.Controls.Canvas>: <xref:System.Windows.Controls.Canvas.Bottom%2A>, <xref:System.Windows.Controls.Canvas.Left%2A>, <xref:System.Windows.Controls.Canvas.Right%2A>, 및 <xref:System.Windows.Controls.Canvas.Top%2A>합니다. 각 <xref:System.Windows.Controls.Button> 에서 부모에 상대적인 배치 <xref:System.Windows.Controls.Canvas> 할당된 된 속성 값에 따라 합니다.  
  
 [!code-cpp[CanvasAttachedProperties#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/CanvasAttachedProperties/CPP/CanvasAttachedProps.cpp#1)]
 [!code-csharp[CanvasAttachedProperties#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CanvasAttachedProperties/CSharp/CanvasAttachedProps.cs#1)]
 [!code-vb[CanvasAttachedProperties#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasAttachedProperties/VisualBasic/CanvasAttachedProps.vb#1)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Controls.Canvas>  
 <xref:System.Windows.Controls.Canvas.Bottom%2A>  
 <xref:System.Windows.Controls.Canvas.Left%2A>  
 <xref:System.Windows.Controls.Canvas.Right%2A>  
 <xref:System.Windows.Controls.Canvas.Top%2A>  
 <xref:System.Windows.Controls.Button>  
 [패널 개요](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [방법 항목](../../../../docs/framework/wpf/controls/canvas-how-to-topics.md)  
 [연결된 속성 개요](../../../../docs/framework/wpf/advanced/attached-properties-overview.md)
