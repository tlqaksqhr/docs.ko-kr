---
title: '방법: StackPanel에서 콘텐츠 가로 또는 세로 맞춤'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- StackPanel control [WPF], content alignment [WPF]
- content alignment [WPF]
- aligning [WPF], content
ms.assetid: c1e8f962-72c8-4e7a-8670-7a2d7e021791
ms.openlocfilehash: a03cb1ed9b3e5bd42b28e37f5bbb3e1d0446a4ef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33550757"
---
# <a name="how-to-horizontally-or-vertically-align-content-in-a-stackpanel"></a><span data-ttu-id="ee53b-102">방법: StackPanel에서 콘텐츠 가로 또는 세로 맞춤</span><span class="sxs-lookup"><span data-stu-id="ee53b-102">How to: Horizontally or Vertically Align Content in a StackPanel</span></span>
<span data-ttu-id="ee53b-103">조정 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.StackPanel.Orientation%2A> 내의 콘텐츠는 <xref:System.Windows.Controls.StackPanel> 요소 및 조정 하는 방법의 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 및 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> 자식 콘텐츠입니다.</span><span class="sxs-lookup"><span data-stu-id="ee53b-103">This example shows how to adjust the <xref:System.Windows.Controls.StackPanel.Orientation%2A> of content within a <xref:System.Windows.Controls.StackPanel> element, and also how to adjust the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> and <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> of child content.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ee53b-104">예제</span><span class="sxs-lookup"><span data-stu-id="ee53b-104">Example</span></span>  
 <span data-ttu-id="ee53b-105">다음 예제에서는 세 개의 <xref:System.Windows.Controls.ListBox> 요소 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="ee53b-105">The following example creates three <xref:System.Windows.Controls.ListBox> elements in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> <span data-ttu-id="ee53b-106">각 <xref:System.Windows.Controls.ListBox> 의 가능한 값을 나타냅니다는 <xref:System.Windows.Controls.StackPanel.Orientation%2A>, <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, 및 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> 의 속성을 <xref:System.Windows.Controls.StackPanel>합니다.</span><span class="sxs-lookup"><span data-stu-id="ee53b-106">Each <xref:System.Windows.Controls.ListBox> represents the possible values of the <xref:System.Windows.Controls.StackPanel.Orientation%2A>, <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, and <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> properties of a <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="ee53b-107">사용자 중 하나에 값을 선택 하는 경우는 <xref:System.Windows.Controls.ListBox> 요소, 연결 된 속성의는 <xref:System.Windows.Controls.StackPanel> 와 해당 자식 <xref:System.Windows.Controls.Button> 요소를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee53b-107">When a user selects a value in any of the <xref:System.Windows.Controls.ListBox> elements, the associated property of the <xref:System.Windows.Controls.StackPanel> and its child <xref:System.Windows.Controls.Button> elements change.</span></span>  
  
 [!code-xaml[StackPanelIntroSamp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StackPanelIntroSamp/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="ee53b-108">다음 코드 숨김 파일 연관 된 이벤트에 변경 내용을 정의 <xref:System.Windows.Controls.ListBox> 선택 항목이 변경 됨.</span><span class="sxs-lookup"><span data-stu-id="ee53b-108">The following code-behind file defines the changes to the events that are associated with the <xref:System.Windows.Controls.ListBox> selection changes.</span></span> <span data-ttu-id="ee53b-109"><xref:System.Windows.Controls.StackPanel> 로 식별 되는 <xref:System.Windows.FrameworkElement.Name%2A> `sp1`합니다.</span><span class="sxs-lookup"><span data-stu-id="ee53b-109"><xref:System.Windows.Controls.StackPanel> is identified by the <xref:System.Windows.FrameworkElement.Name%2A> `sp1`.</span></span>  
  
 [!code-csharp[StackPanelIntroSamp#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StackPanelIntroSamp/CSharp/Window1.xaml.cs#2)]
 [!code-vb[StackPanelIntroSamp#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelIntroSamp/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="ee53b-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ee53b-110">See Also</span></span>  
 <xref:System.Windows.Controls.StackPanel>  
 <xref:System.Windows.Controls.ListBox>  
 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>  
 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>  
 [<span data-ttu-id="ee53b-111">패널 개요</span><span class="sxs-lookup"><span data-stu-id="ee53b-111">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)
