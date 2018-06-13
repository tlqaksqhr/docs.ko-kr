---
title: '방법: ScrollChanged 이벤트 처리'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ScrollViewer control [WPF], raising ScrollChanged events
- ScrollChanged events [WPF]
ms.assetid: 42c695d8-ee28-49d4-80fd-fc71e9be7f29
ms.openlocfilehash: da7c1d1174e3264b21763177487ebcb75a4b3192
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33552703"
---
# <a name="how-to-handle-the-scrollchanged-event"></a><span data-ttu-id="4e456-102">방법: ScrollChanged 이벤트 처리</span><span class="sxs-lookup"><span data-stu-id="4e456-102">How to: Handle the ScrollChanged Event</span></span>
## <a name="example"></a><span data-ttu-id="4e456-103">예제</span><span class="sxs-lookup"><span data-stu-id="4e456-103">Example</span></span>  
 <span data-ttu-id="4e456-104">처리 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.ScrollViewer.ScrollChanged> 의 이벤트는 <xref:System.Windows.Controls.ScrollViewer>합니다.</span><span class="sxs-lookup"><span data-stu-id="4e456-104">This example shows how to handle the <xref:System.Windows.Controls.ScrollViewer.ScrollChanged> event of a <xref:System.Windows.Controls.ScrollViewer>.</span></span>  
  
 <span data-ttu-id="4e456-105">A <xref:System.Windows.Documents.FlowDocument> 요소 <xref:System.Windows.Documents.Paragraph> 파트에 정의 된 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="4e456-105">A <xref:System.Windows.Documents.FlowDocument> element with <xref:System.Windows.Documents.Paragraph> parts is defined in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span> <span data-ttu-id="4e456-106">경우는 <xref:System.Windows.Controls.ScrollViewer.ScrollChanged> 사용자 상호 작용으로 인해 이벤트가 발생할 처리기가 호출 되 고 텍스트에 기록 됩니다는 <xref:System.Windows.Controls.TextBlock> 이벤트가 발생 했음을 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="4e456-106">When the <xref:System.Windows.Controls.ScrollViewer.ScrollChanged> event occurs due to user interaction, a handler is invoked, and text is written to a <xref:System.Windows.Controls.TextBlock> indicating that the event has occurred.</span></span>  
  
 [!code-xaml[scrollchangedeventargsLayout#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/scrollchangedeventargsLayout/CSharp/Window1.xaml#1)]  
[!code-xaml[scrollchangedeventargsLayout#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/scrollchangedeventargsLayout/CSharp/Window1.xaml#2)]  
  
 [!code-csharp[scrollchangedeventargsLayout#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/scrollchangedeventargsLayout/CSharp/Window1.xaml.cs#3)]
 [!code-vb[scrollchangedeventargsLayout#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/scrollchangedeventargsLayout/VisualBasic/Window1.xaml.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="4e456-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4e456-107">See Also</span></span>  
 <xref:System.Windows.Controls.ScrollViewer>  
 <xref:System.Windows.Controls.ScrollViewer.ScrollChanged>  
 <xref:System.Windows.Controls.ScrollChangedEventHandler>  
 <xref:System.Windows.Controls.ScrollChangedEventArgs>
