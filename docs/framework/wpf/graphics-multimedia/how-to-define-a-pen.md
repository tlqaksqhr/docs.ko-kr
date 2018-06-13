---
title: '방법: 펜 정의'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pens [WPF], defining
- creating [WPF], pens
ms.assetid: 7a4f2900-cdf9-49de-84e0-ba5d0ded4d33
ms.openlocfilehash: 7c5be5eff06df55e465f3e34646ba1c34e8b7e07
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33559866"
---
# <a name="how-to-define-a-pen"></a>방법: 펜 정의
이 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Pen> 셰이프를 간략하게 설명 합니다. 간단한 만들려면 <xref:System.Windows.Media.Pen>를 지정 하면 해당 <xref:System.Windows.Media.Pen.Thickness%2A> 및 <xref:System.Windows.Media.Pen.Brush%2A>합니다. 지정 하 여 보다 복잡 한 펜을 만들 수 있습니다는 <xref:System.Windows.Media.Pen.DashStyle%2A>, <xref:System.Windows.Media.Pen.DashCap%2A>, <xref:System.Windows.Media.Pen.LineJoin%2A>, <xref:System.Windows.Media.Pen.StartLineCap%2A>, 및 <xref:System.Windows.Media.Pen.EndLineCap%2A>합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 한 <xref:System.Windows.Media.Pen> 에 의해 정의 되는 도형을 설명는 <xref:System.Windows.Media.GeometryDrawing>합니다.  
  
 [!code-csharp[PenExamples_snip#PenExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PenExamples_snip/CSharp/PenExample.cs#penexamplewholepage)]
 [!code-vb[PenExamples_snip#PenExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PenExamples_snip/VisualBasic/PenExample.vb#penexamplewholepage)]  
  
 ![펜으로 만들어진 윤곽선](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-simple-pen.jpg "graphicsmm_simple_pen")  
GeometryDrawing
