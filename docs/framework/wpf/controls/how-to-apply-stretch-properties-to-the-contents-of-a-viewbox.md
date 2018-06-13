---
title: '방법: Viewbox의 콘텐츠에 Stretch 속성 적용'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- StretchDirection properties [WPF]
- Stretch properties [WPF]
- controls [WPF], Viewbox
- Viewbox control [WPF]
ms.assetid: b9c22ef4-bce4-4300-9e0c-8260b7db83cc
ms.openlocfilehash: 3e81ec9fd045bb3fcf359943e455d2cce94aec55
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33552807"
---
# <a name="how-to-apply-stretch-properties-to-the-contents-of-a-viewbox"></a><span data-ttu-id="4a75a-102">방법: Viewbox의 콘텐츠에 Stretch 속성 적용</span><span class="sxs-lookup"><span data-stu-id="4a75a-102">How to: Apply Stretch Properties to the Contents of a Viewbox</span></span>
## <a name="example"></a><span data-ttu-id="4a75a-103">예제</span><span class="sxs-lookup"><span data-stu-id="4a75a-103">Example</span></span>  
 <span data-ttu-id="4a75a-104">값을 변경 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.Viewbox.StretchDirection%2A> 및 <xref:System.Windows.Controls.Viewbox.Stretch%2A> 의 속성을 <xref:System.Windows.Controls.Viewbox>합니다.</span><span class="sxs-lookup"><span data-stu-id="4a75a-104">This example shows how to change the value of the <xref:System.Windows.Controls.Viewbox.StretchDirection%2A> and <xref:System.Windows.Controls.Viewbox.Stretch%2A> properties of a <xref:System.Windows.Controls.Viewbox>.</span></span>  
  
 <span data-ttu-id="4a75a-105">사용 하 여 첫 번째 예제 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 정의 하는 <xref:System.Windows.Controls.Viewbox> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="4a75a-105">The first example uses [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to define a <xref:System.Windows.Controls.Viewbox> element.</span></span> <span data-ttu-id="4a75a-106">자동으로 할당 한 <xref:System.Windows.FrameworkElement.MaxWidth%2A> 및 <xref:System.Windows.FrameworkElement.MaxHeight%2A> 400입니다.</span><span class="sxs-lookup"><span data-stu-id="4a75a-106">It assigns a <xref:System.Windows.FrameworkElement.MaxWidth%2A> and <xref:System.Windows.FrameworkElement.MaxHeight%2A> of 400.</span></span> <span data-ttu-id="4a75a-107">예에서는 중첩 된 <xref:System.Windows.Controls.Image> 내의 요소는 <xref:System.Windows.Controls.Viewbox>합니다.</span><span class="sxs-lookup"><span data-stu-id="4a75a-107">The example nests an <xref:System.Windows.Controls.Image> element within the <xref:System.Windows.Controls.Viewbox>.</span></span> <span data-ttu-id="4a75a-108"><xref:System.Windows.Controls.Button> 에 대 한 속성 값에 해당 하는 요소는 <xref:System.Windows.Controls.Viewbox.Stretch%2A> 및 <xref:System.Windows.Controls.StretchDirection> 는 중첩 된 늘이기 동작을 조작 하는 열거형 <xref:System.Windows.Controls.Image>합니다.</span><span class="sxs-lookup"><span data-stu-id="4a75a-108"><xref:System.Windows.Controls.Button> elements that correspond to the property values for the <xref:System.Windows.Controls.Viewbox.Stretch%2A> and <xref:System.Windows.Controls.StretchDirection> enumerations manipulate the stretching behavior of the nested <xref:System.Windows.Controls.Image>.</span></span>  
  
 [!code-xaml[viewboxStretchLayoutSamp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/viewboxStretchLayoutSamp/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="4a75a-109">다음 코드 숨김 파일 핸들은 <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트는 이전 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 정의 하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="4a75a-109">The following code-behind file handles the <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.Primitives.ButtonBase.Click> events that the previous [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] example defines.</span></span>  
  
 [!code-csharp[viewboxStretchLayoutSamp#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/viewboxStretchLayoutSamp/CSharp/Window1.xaml.cs#2)]
 [!code-vb[viewboxStretchLayoutSamp#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/viewboxStretchLayoutSamp/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="4a75a-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4a75a-110">See Also</span></span>  
 <xref:System.Windows.Controls.Viewbox>  
 <xref:System.Windows.Media.Stretch>  
 <xref:System.Windows.Controls.StretchDirection>
