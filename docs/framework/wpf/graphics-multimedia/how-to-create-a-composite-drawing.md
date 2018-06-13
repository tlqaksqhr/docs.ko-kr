---
title: '방법: 합성 그리기 만들기'
ms.date: 03/30/2017
helpviewer_keywords:
- drawings [WPF], composite
- composite drawings [WPF]
- graphics [WPF], composite drawings
ms.assetid: 066eb0ab-5f0e-439d-85c6-dca60af269fc
ms.openlocfilehash: bb222fff11c81b491c0413f174539ff0005d11b8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561595"
---
# <a name="how-to-create-a-composite-drawing"></a><span data-ttu-id="2bae8-102">방법: 합성 그리기 만들기</span><span class="sxs-lookup"><span data-stu-id="2bae8-102">How to: Create a Composite Drawing</span></span>
<span data-ttu-id="2bae8-103">사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.DrawingGroup> 다중 결합 하 여 복잡 한 드로잉을 만드는 데 <xref:System.Windows.Media.Drawing> 단일 복합 그리기 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="2bae8-103">This example shows how to use a <xref:System.Windows.Media.DrawingGroup> to create complex drawings by combining multiple <xref:System.Windows.Media.Drawing> objects into a single composite drawing.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2bae8-104">예제</span><span class="sxs-lookup"><span data-stu-id="2bae8-104">Example</span></span>  
 <span data-ttu-id="2bae8-105">다음 예제에서는 한 <xref:System.Windows.Media.DrawingGroup> 합성 그리기를 만들려는 <xref:System.Windows.Media.GeometryDrawing> 및 <xref:System.Windows.Media.ImageDrawing> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="2bae8-105">The following example uses a <xref:System.Windows.Media.DrawingGroup> to create a composite drawing from the <xref:System.Windows.Media.GeometryDrawing> and <xref:System.Windows.Media.ImageDrawing> objects.</span></span> <span data-ttu-id="2bae8-106">다음 그림에서는 이 예제가 생성하는 출력을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2bae8-106">The following illustration shows the output that this example produces.</span></span>  
  
 <span data-ttu-id="2bae8-107">![여러 개의 그리기가 있는 DrawingGroup](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-simple.jpg "graphicsmm_simple")</span><span class="sxs-lookup"><span data-stu-id="2bae8-107">![A DrawingGroup with multiple drawings](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-simple.jpg "graphicsmm_simple")</span></span>  
<span data-ttu-id="2bae8-108">DrawingGroup를 사용 하 여 만든 복합 그리기</span><span class="sxs-lookup"><span data-stu-id="2bae8-108">A composite drawing that is created by using DrawingGroup</span></span>  
  
 <span data-ttu-id="2bae8-109">Note 회색 테두리 드로잉의 경계를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2bae8-109">Note the gray border, which shows the bounds of the drawing.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmsimpledrawinggroupexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmsimpledrawinggroupexample)]  
  
 <span data-ttu-id="2bae8-110">사용할 수는 <xref:System.Windows.Media.DrawingGroup> 적용 하는 <xref:System.Windows.Media.DrawingGroup.Transform%2A>, <xref:System.Windows.Media.DrawingGroup.Opacity%2A> 설정을 <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>, <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>, <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>, 또는 <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> 포함 된 그리기를 합니다.</span><span class="sxs-lookup"><span data-stu-id="2bae8-110">You can use a <xref:System.Windows.Media.DrawingGroup> to apply a <xref:System.Windows.Media.DrawingGroup.Transform%2A>, <xref:System.Windows.Media.DrawingGroup.Opacity%2A> setting, <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>, <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>, <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>, or <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> to the drawings it contains.</span></span> <span data-ttu-id="2bae8-111">때문에 <xref:System.Windows.Media.DrawingGroup> 이기도 한 <xref:System.Windows.Media.Drawing>, 다른 포함 될 수 있습니다 <xref:System.Windows.Media.DrawingGroup> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="2bae8-111">Because a <xref:System.Windows.Media.DrawingGroup> is also a <xref:System.Windows.Media.Drawing>, it can contain other <xref:System.Windows.Media.DrawingGroup> objects.</span></span>  
  
 <span data-ttu-id="2bae8-112">추가 사용 하 여 다음 예제는 앞의 예제와 유사 <xref:System.Windows.Media.DrawingGroup> 일부 그리기에 불투명 마스크 및 비트맵 효과 적용할 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="2bae8-112">The following example is similar to the preceding example, except that it uses additional <xref:System.Windows.Media.DrawingGroup> objects to apply bitmap effects and an opacity mask to some of its drawings.</span></span> <span data-ttu-id="2bae8-113">다음 그림에서는 이 예제가 생성하는 출력을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2bae8-113">The following illustration shows the output that this example produces.</span></span>  
  
 <span data-ttu-id="2bae8-114">![여러 개의 그리기가 있는 DrawingGroup](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-multiple.jpg "graphicsmm_multiple")</span><span class="sxs-lookup"><span data-stu-id="2bae8-114">![A DrawingGroup with multiple drawings](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-multiple.jpg "graphicsmm_multiple")</span></span>  
<span data-ttu-id="2bae8-115">합성 있는 그리기에 여러 DrawingGroup 개체</span><span class="sxs-lookup"><span data-stu-id="2bae8-115">Composite drawing that has multiple DrawingGroup objects</span></span>  
  
 <span data-ttu-id="2bae8-116">Note 회색 테두리 드로잉의 경계를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2bae8-116">Note the gray border, which shows the bounds of the drawing.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMMultipleDrawingGroupsExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmmultipledrawinggroupsexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMMultipleDrawingGroupsExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmmultipledrawinggroupsexample)]  
  
 <span data-ttu-id="2bae8-117">에 대 한 자세한 내용은 <xref:System.Windows.Media.Drawing> 개체 참조 [그리기 개체 개요](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2bae8-117">For more information about <xref:System.Windows.Media.Drawing> objects, see [Drawing Objects Overview](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bae8-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2bae8-118">See Also</span></span>  
 <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>  
 <xref:System.Windows.Media.DrawingGroup.Transform%2A>  
 <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>  
 <xref:System.Windows.Media.DrawingGroup.Opacity%2A>  
 <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>  
 <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>  
 [<span data-ttu-id="2bae8-119">Drawing 개체 개요</span><span class="sxs-lookup"><span data-stu-id="2bae8-119">Drawing Objects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)
