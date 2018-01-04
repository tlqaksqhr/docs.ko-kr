---
title: "방법: 캔버스 만들기 및 사용"
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
helpviewer_keywords:
- controls [WPF], Canvas
- Canvas control [WPF], creating
- Canvas control [WPF], using
ms.assetid: 420b9487-9a15-477c-9489-a22a4dec7779
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 562531f75d6a800ff93a02709a053b790de52ea2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-and-use-a-canvas"></a>방법: 캔버스 만들기 및 사용
만들고의 인스턴스를 사용 하는 방법을 보여 주는이 예제 <xref:System.Windows.Controls.Canvas>합니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 명시적으로 두 개의 배치 <xref:System.Windows.Controls.TextBlock> 요소를 사용 하 여는 <xref:System.Windows.Controls.Canvas.SetTop%2A> 및 <xref:System.Windows.Controls.Canvas.SetLeft%2A> 방식의 <xref:System.Windows.Controls.Canvas>합니다. 이 예에서는 또한 할당 한 <xref:System.Windows.Controls.Control.Background%2A> 의 색 `LightSteelBlue` 에 <xref:System.Windows.Controls.Canvas>합니다.  
  
> [!NOTE]
>  사용 하는 경우 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 위치로 <xref:System.Windows.Controls.TextBlock> 요소를 사용 하 여는 <xref:System.Windows.Controls.Canvas.Top%2A> 및 <xref:System.Windows.Controls.Canvas.Left%2A> 속성입니다.  
  
 [!code-csharp[CanvasCode#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CanvasCode/CSharp/Canvas_Code.cs#1)]
 [!code-vb[CanvasCode#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasCode/VisualBasic/canvas_vb.vb#1)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Controls.Canvas>  
 <xref:System.Windows.Controls.TextBlock>  
 <xref:System.Windows.Controls.Canvas.SetTop%2A>  
 <xref:System.Windows.Controls.Canvas.SetLeft%2A>  
 <xref:System.Windows.Controls.Canvas.Top%2A>  
 <xref:System.Windows.Controls.Canvas.Left%2A>  
 [패널 개요](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [방법 항목](../../../../docs/framework/wpf/controls/canvas-how-to-topics.md)
