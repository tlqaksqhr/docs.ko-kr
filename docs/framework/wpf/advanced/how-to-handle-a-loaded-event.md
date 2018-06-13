---
title: '방법: Loaded 이벤트 처리'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- XAML [WPF], Loaded events
- events [WPF], Loaded
- Loaded events [WPF]
ms.assetid: 0cf8d003-8441-4df4-807a-6db09347e829
ms.openlocfilehash: 6f3520fc3bc2a64d76083af415588ff819890eb9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33544198"
---
# <a name="how-to-handle-a-loaded-event"></a>방법: Loaded 이벤트 처리
처리 하는 방법을 보여 주는이 예제는 <xref:System.Windows.FrameworkElement.Loaded?displayProperty=nameWithType> 이벤트 및 해당 이벤트를 처리 하기 위한 적합 한 시나리오가 있습니다. 처리기 만듭니다는 <xref:System.Windows.Controls.Button> 페이지를 로드 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 코드 숨김 파일과 함께 합니다.  
  
 [!code-xaml[FELoaded#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FELoaded/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[FELoaded#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FELoaded/CSharp/default.xaml.cs#handler)]
 [!code-vb[FELoaded#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FELoaded/VisualBasic/default.xaml.vb#handler)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.FrameworkElement>  
 [개체 수명 이벤트](../../../../docs/framework/wpf/advanced/object-lifetime-events.md)  
 [라우트된 이벤트 개요](../../../../docs/framework/wpf/advanced/routed-events-overview.md)  
 [방법 항목](../../../../docs/framework/wpf/advanced/base-elements-how-to-topics.md)
