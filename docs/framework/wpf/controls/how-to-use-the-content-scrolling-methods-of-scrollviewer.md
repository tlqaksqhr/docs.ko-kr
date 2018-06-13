---
title: '방법: ScrollViewer의 콘텐츠 스크롤 메서드 사용'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- IScrollInfo interface [WPF]
- scrolling methods [WPF]
- ScrollViewer control [WPF], scrolling methods
ms.assetid: 4708cc65-6510-45f8-82e6-30b0d3e30045
ms.openlocfilehash: b4da666934be7dd182838d870e54e496b2646901
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33552768"
---
# <a name="how-to-use-the-content-scrolling-methods-of-scrollviewer"></a><span data-ttu-id="939bd-102">방법: ScrollViewer의 콘텐츠 스크롤 메서드 사용</span><span class="sxs-lookup"><span data-stu-id="939bd-102">How to: Use the Content-Scrolling Methods of ScrollViewer</span></span>
<span data-ttu-id="939bd-103">스크롤 메서드를 사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.ScrollViewer> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="939bd-103">This example shows how to use the scrolling methods of the <xref:System.Windows.Controls.ScrollViewer> element.</span></span> <span data-ttu-id="939bd-104">이러한 메서드는 증분 스크롤 콘텐츠의 줄 또는 페이지에 제공 된 <xref:System.Windows.Controls.ScrollViewer>합니다.</span><span class="sxs-lookup"><span data-stu-id="939bd-104">These methods provide incremental scrolling of content, either by line or by page, in a <xref:System.Windows.Controls.ScrollViewer>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="939bd-105">예제</span><span class="sxs-lookup"><span data-stu-id="939bd-105">Example</span></span>  
 <span data-ttu-id="939bd-106">다음 예제에서는 한 <xref:System.Windows.Controls.ScrollViewer> 라는 `sv1`, 자식을 호스트 하는 <xref:System.Windows.Controls.TextBlock> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="939bd-106">The following example creates a <xref:System.Windows.Controls.ScrollViewer> named `sv1`, which hosts a child <xref:System.Windows.Controls.TextBlock> element.</span></span> <span data-ttu-id="939bd-107">때문에 <xref:System.Windows.Controls.TextBlock> 부모 보다 큰 <xref:System.Windows.Controls.ScrollViewer>을 스크롤할 수 있도록 스크롤 막대가 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="939bd-107">Because the <xref:System.Windows.Controls.TextBlock> is larger than the parent <xref:System.Windows.Controls.ScrollViewer>, scroll bars appear in order to enable scrolling.</span></span> <span data-ttu-id="939bd-108"><xref:System.Windows.Controls.Button> 다양 한 스크롤 메서드를 나타내는 요소는 별도의 왼쪽에 도킹 되어 <xref:System.Windows.Controls.StackPanel>합니다.</span><span class="sxs-lookup"><span data-stu-id="939bd-108"><xref:System.Windows.Controls.Button> elements that represent the various scrolling methods are docked on the left in a separate <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="939bd-109">각 <xref:System.Windows.Controls.Button> 에 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 의 스크롤 동작을 제어 하는 관련된 사용자 지정 메서드를 호출 하는 파일 <xref:System.Windows.Controls.ScrollViewer>합니다.</span><span class="sxs-lookup"><span data-stu-id="939bd-109">Each <xref:System.Windows.Controls.Button> in the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file calls a related custom method that controls scrolling behavior in <xref:System.Windows.Controls.ScrollViewer>.</span></span>  
  
 [!code-xaml[ScrollViewerMethods#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewerMethods/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="939bd-110">다음 예제에서는 <xref:System.Windows.Controls.ScrollViewer.LineUp%2A> 및 <xref:System.Windows.Controls.ScrollViewer.LineDown%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="939bd-110">The following example uses the <xref:System.Windows.Controls.ScrollViewer.LineUp%2A> and <xref:System.Windows.Controls.ScrollViewer.LineDown%2A> methods.</span></span>  
  
 [!code-csharp[ScrollViewerMethods#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewerMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[ScrollViewerMethods#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ScrollViewerMethods/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="939bd-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="939bd-111">See Also</span></span>  
 <xref:System.Windows.Controls.ScrollViewer>  
 <xref:System.Windows.Controls.StackPanel>
