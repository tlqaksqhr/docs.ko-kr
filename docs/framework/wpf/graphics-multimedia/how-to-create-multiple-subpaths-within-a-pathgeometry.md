---
title: '방법: PathGeometry 내에 다중 하위 경로 만들기'
ms.date: 03/30/2017
helpviewer_keywords:
- multiple subpaths [WPF]
- graphics [WPF], subpaths
- subpaths [WPF]
ms.assetid: 104a862c-dde2-4e62-ac87-80660dd1681c
ms.openlocfilehash: 5b129b1bacb5dc2cba87376e8df70e115a5ebd72
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33559333"
---
# <a name="how-to-create-multiple-subpaths-within-a-pathgeometry"></a><span data-ttu-id="aa6e5-102">방법: PathGeometry 내에 다중 하위 경로 만들기</span><span class="sxs-lookup"><span data-stu-id="aa6e5-102">How to: Create Multiple Subpaths Within a PathGeometry</span></span>
<span data-ttu-id="aa6e5-103">여러 하위 경로 만드는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.PathGeometry>합니다.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-103">This example shows how to create multiple subpaths in a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="aa6e5-104">여러 하위 경로 만들려면 만듭니다는 <xref:System.Windows.Media.PathFigure> 각 하위 경로 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-104">To create multiple subpaths, you create a <xref:System.Windows.Media.PathFigure> for each subpath.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aa6e5-105">예제</span><span class="sxs-lookup"><span data-stu-id="aa6e5-105">Example</span></span>  
 <span data-ttu-id="aa6e5-106">다음 예제에서는 두 개의 하위 경로 각 삼각형을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-106">The following example creates two subpaths, each one a triangle.</span></span>  
  
 [!code-xaml[GeometrySample#38](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#38)]  
  
 <span data-ttu-id="aa6e5-107">여러 하위 경로 사용 하 여 만드는 방법을 보여 주는 다음 예제는 <xref:System.Windows.Shapes.Path> 및 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 특성 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-107">The following example shows how to create multiple subpaths by using a <xref:System.Windows.Shapes.Path> and [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] attribute syntax.</span></span> <span data-ttu-id="aa6e5-108">각 `M` 새 하위 경로 만들어이 예에서는 각각 삼각형을 그리는 두 개의 하위 경로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-108">Each `M` creates a new subpath so that the example creates two subpaths that each draw a triangle.</span></span>  
  
 [!code-xaml[GeometrySample#58](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#58)]  
  
 <span data-ttu-id="aa6e5-109">(이 특성 구문 실제로 만드는 참고는 <xref:System.Windows.Media.StreamGeometry>, 간단한 버전의는 <xref:System.Windows.Media.PathGeometry>합니다.</span><span class="sxs-lookup"><span data-stu-id="aa6e5-109">(Note that this attribute syntax actually creates a <xref:System.Windows.Media.StreamGeometry>, a lighter-weight version of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="aa6e5-110">자세한 내용은 [경로 태그 구문](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) 페이지를 참조하세요.)</span><span class="sxs-lookup"><span data-stu-id="aa6e5-110">For more information, see the [Path Markup Syntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) page.)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa6e5-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="aa6e5-111">See Also</span></span>  
 [<span data-ttu-id="aa6e5-112">Geometry 개요</span><span class="sxs-lookup"><span data-stu-id="aa6e5-112">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)
