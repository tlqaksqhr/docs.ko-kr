---
title: '방법: 요소를 캐시하여 렌더링 성능 향상'
ms.date: 03/30/2017
helpviewer_keywords:
- rendering performance [WPF], caching an element
- BitmapCache [WPF], improving rendering performance
- CacheMode [WPF], improving rendering performance
- performance [WPF], caching an element
- UIElement [WPF], caching
ms.assetid: 4739c1fc-60ba-4c46-aba6-f6c1a2688f19
ms.openlocfilehash: a92909c623db0c10e3434677b4275fa82b787fa7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33559300"
---
# <a name="how-to-improve-rendering-performance-by-caching-an-element"></a><span data-ttu-id="fa7dc-102">방법: 요소를 캐시하여 렌더링 성능 향상</span><span class="sxs-lookup"><span data-stu-id="fa7dc-102">How to: Improve Rendering Performance by Caching an Element</span></span>
<span data-ttu-id="fa7dc-103">사용 하 여는 <xref:System.Windows.Media.BitmapCache> 복잡 한의 렌더링 성능을 개선 하기 위해 클래스 <xref:System.Windows.UIElement>합니다.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-103">Use the <xref:System.Windows.Media.BitmapCache> class to improve rendering performance of a complex <xref:System.Windows.UIElement>.</span></span> <span data-ttu-id="fa7dc-104">새 인스턴스를 만들고 요소를 캐시 하려면는 <xref:System.Windows.Media.BitmapCache> 클래스 및 요소에 할당할 <xref:System.Windows.UIElement.CacheMode%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-104">To cache an element, create a new instance of the <xref:System.Windows.Media.BitmapCache> class and assign it to the element's <xref:System.Windows.UIElement.CacheMode%2A> property.</span></span> <span data-ttu-id="fa7dc-105">다시 사용할 수는 <xref:System.Windows.Media.BitmapCache> 에 효율적으로 한 <xref:System.Windows.Media.BitmapCacheBrush>합니다.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-105">You can reuse a <xref:System.Windows.Media.BitmapCache> efficiently in a <xref:System.Windows.Media.BitmapCacheBrush>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa7dc-106">예제</span><span class="sxs-lookup"><span data-stu-id="fa7dc-106">Example</span></span>  
 <span data-ttu-id="fa7dc-107">다음 코드 예제에서는 요소 애니메이션 될 때 성능을 향상 시키는 비트맵으로 캐시 하는 복잡 한 요소를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-107">The following code example shows how to create a complex element and cache it as a bitmap, which improves performance when the element is animated.</span></span> <span data-ttu-id="fa7dc-108">많은 꼭 짓 점 기 하 도형을 포함 하는 캔버스입니다.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-108">The element is a canvas that holds shape geometries with many vertices.</span></span> <span data-ttu-id="fa7dc-109">A <xref:System.Windows.Media.BitmapCache> 에 할당 된 값 이며 기본값은는 <xref:System.Windows.UIElement.CacheMode%2A> 를 캔버스의 애니메이션 캐시 된 비트맵의 부드러운 크기 조정을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fa7dc-109">A <xref:System.Windows.Media.BitmapCache> with default values is assigned to the <xref:System.Windows.UIElement.CacheMode%2A> of the canvas, and an animation shows the smooth scaling of the cached bitmap.</span></span>  
  
 [!code-xaml[System.Windows.Media.BitmapCache#_BitmapCacheXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/system.windows.media.bitmapcache/cs/window1.xaml#_bitmapcachexaml)]  
  
## <a name="see-also"></a><span data-ttu-id="fa7dc-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fa7dc-110">See Also</span></span>  
 <xref:System.Windows.Media.BitmapCache>  
 <xref:System.Windows.Media.BitmapCacheBrush>  
 <xref:System.Windows.UIElement.CacheMode%2A>  
 [<span data-ttu-id="fa7dc-111">방법: 캐시된 요소를 브러시로 사용</span><span class="sxs-lookup"><span data-stu-id="fa7dc-111">How to: Use a Cached Element as a Brush</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-a-cached-element-as-a-brush.md)
