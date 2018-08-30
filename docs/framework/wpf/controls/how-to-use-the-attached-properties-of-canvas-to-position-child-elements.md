---
title: '방법: Canvas의 연결된 속성을 사용하여 자식 요소 배치'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- attached properties [WPF Designer]
- Canvas control [WPF], attached properties
ms.assetid: 48f1d25d-3820-4107-a4cc-d6c1e5664a44
ms.openlocfilehash: 886440304dc1bebdcfae66676254bef7ac35457d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33552376"
---
# <a name="how-to-use-the-attached-properties-of-canvas-to-position-child-elements"></a>방법: Canvas의 연결된 속성을 사용하여 자식 요소 배치
이 예제는, 자식 요소들을 위치시키기 위해, <xref:System.Windows.Controls.Canvas>의 연결속성을 사용하는 법을 알려주는 예제입니다.  
  
## <a name="example"></a>예제  
아래의 예제는, 4개의 <xref:System.Windows.Controls.Button>을 부모 <xref:System.Windows.Controls.Canvas>의 자식 요소로 추가하는 예제입니다.
각 요소들은 <xref:System.Windows.Controls.Canvas.Bottom%2A>, <xref:System.Windows.Controls.Canvas.Left%2A>, <xref:System.Windows.Controls.Canvas.Right%2A>, <xref:System.Windows.Controls.Canvas.Top%2A> 과 같이 구별되는 캔버스의 연결속성으로 나타 낼 수있습니다.
각 <xref:System.Windows.Controls.Button>은 부모 <xref:System.Windows.Controls.Canvas>를 기준으로 하는 상대 위치 좌표를, 연결 요소 값으로 할당하는 방식으로 배치합니다. 
  
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
