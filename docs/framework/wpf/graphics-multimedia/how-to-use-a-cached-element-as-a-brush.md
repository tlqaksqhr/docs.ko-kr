---
title: '방법: 캐시된 요소를 브러시로 사용'
ms.date: 03/30/2017
helpviewer_keywords:
- BitmapCache [WPF], using
- cached element [WPF], use as a brush
- BitmapCacheBrush [WPF], using
- CacheMode [WPF], using
ms.assetid: d36e944a-866e-4baf-98c4-fd6a75f6fdd0
ms.openlocfilehash: c43c4ecbefe99d6e38766705378d85d92ecc5729
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561526"
---
# <a name="how-to-use-a-cached-element-as-a-brush"></a><span data-ttu-id="45487-102">방법: 캐시된 요소를 브러시로 사용</span><span class="sxs-lookup"><span data-stu-id="45487-102">How to: Use a Cached Element as a Brush</span></span>
<span data-ttu-id="45487-103">사용 하 여는 <xref:System.Windows.Media.BitmapCacheBrush> 클래스를 효율적으로 캐시 된 요소를 다시 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="45487-103">Use the <xref:System.Windows.Media.BitmapCacheBrush> class to reuse a cached element efficiently.</span></span> <span data-ttu-id="45487-104">새 인스턴스를 만들고 요소를 캐시 하려면는 <xref:System.Windows.Media.BitmapCache> 클래스 및 요소에 할당할 <xref:System.Windows.UIElement.CacheMode%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="45487-104">To cache an element, create a new instance of the <xref:System.Windows.Media.BitmapCache> class and assign it to the element's <xref:System.Windows.UIElement.CacheMode%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="45487-105">예제</span><span class="sxs-lookup"><span data-stu-id="45487-105">Example</span></span>  
 <span data-ttu-id="45487-106">다음 코드 예제에서는 캐시 된 요소를 다시 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="45487-106">The following code example shows how to reuse a cached element.</span></span> <span data-ttu-id="45487-107">캐시 된 요소는 한 <xref:System.Windows.Controls.Image> 큰 이미지를 표시 하는 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="45487-107">The cached element is an <xref:System.Windows.Controls.Image> control that displays a large image.</span></span> <span data-ttu-id="45487-108"><xref:System.Windows.Controls.Image> 컨트롤이 사용 하 여 비트맵으로 캐시 되는 <xref:System.Windows.Media.BitmapCache> 클래스 및 캐시에 할당 하 여 다시 사용 되는 <xref:System.Windows.Media.BitmapCacheBrush>합니다.</span><span class="sxs-lookup"><span data-stu-id="45487-108">The <xref:System.Windows.Controls.Image> control is cached as a bitmap by using the <xref:System.Windows.Media.BitmapCache> class, and the cache is reused by assigning it to a <xref:System.Windows.Media.BitmapCacheBrush>.</span></span> <span data-ttu-id="45487-109">효율적인 다시 사용할 수 있도록 표시 하려면 25 단추의 배경 브러시 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45487-109">The brush is assigned to the background of twenty-five buttons to show efficient reuse.</span></span>  
  
 [!code-xaml[System.Windows.Media.BitmapCacheBrush#_BitmapCacheBrushXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/system.windows.media.bitmapcachebrush/cs/window1.xaml#_bitmapcachebrushxaml)]  
  
## <a name="see-also"></a><span data-ttu-id="45487-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="45487-110">See Also</span></span>  
 <xref:System.Windows.Media.BitmapCache>  
 <xref:System.Windows.Media.BitmapCacheBrush>  
 <xref:System.Windows.UIElement.CacheMode%2A>  
 [<span data-ttu-id="45487-111">방법: 요소를 캐시하여 렌더링 성능 향상</span><span class="sxs-lookup"><span data-stu-id="45487-111">How to: Improve Rendering Performance by Caching an Element</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-improve-rendering-performance-by-caching-an-element.md)
