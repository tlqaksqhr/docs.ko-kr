---
title: "방법: StreamGeometry를 사용하여 도형 만들기"
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
- graphics [WPF], shapes
- shapes [WPF], creating with StreamGeometry class
ms.assetid: 08f7c8ce-074b-49cd-9aba-cc9592d4ee51
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a333fd6c1906eaea2c8eaf2c3b07502b5a9c4d40
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-shape-using-a-streamgeometry"></a><span data-ttu-id="82b96-102">방법: StreamGeometry를 사용하여 도형 만들기</span><span class="sxs-lookup"><span data-stu-id="82b96-102">How to: Create a Shape Using a StreamGeometry</span></span>
<span data-ttu-id="82b96-103"><xref:System.Windows.Media.StreamGeometry>간단한 안으로 <xref:System.Windows.Media.PathGeometry> 기 하 도형 만들기에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="82b96-103"><xref:System.Windows.Media.StreamGeometry> is light-weight alternative to <xref:System.Windows.Media.PathGeometry> for creating geometric shapes.</span></span> <span data-ttu-id="82b96-104">사용 하 여 한 <xref:System.Windows.Media.StreamGeometry> 복잡 기 하 도형을 설명 해야 하지만 데이터 바인딩, 애니메이션 또는 수정을 지원의 오버 헤드를 원하지 않는 합니다.</span><span class="sxs-lookup"><span data-stu-id="82b96-104">Use a <xref:System.Windows.Media.StreamGeometry> when you need to describe a complex geometry but do not want the overhead of supporting data binding, animation, or modification.</span></span> <span data-ttu-id="82b96-105">예를 들어는 효율성으로 인해는 <xref:System.Windows.Media.StreamGeometry> 클래스는 표시기를 설명 하기에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="82b96-105">For example, because of its efficiency, the <xref:System.Windows.Media.StreamGeometry> class is a good choice for describing adorners.</span></span>  
  
## <a name="example"></a><span data-ttu-id="82b96-106">예</span><span class="sxs-lookup"><span data-stu-id="82b96-106">Example</span></span>  
 <span data-ttu-id="82b96-107">다음 예제에서는 특성 구문을 사용 하 여 삼각형을 만들려는 <xref:System.Windows.Media.StreamGeometry> 에서 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="82b96-107">The following example uses attribute syntax to create a triangular <xref:System.Windows.Media.StreamGeometry> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 [!code-xaml[GeometriesMiscSnippets_snip#StreamGeometryTriangleExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/StreamGeometryExample.xaml#streamgeometrytriangleexamplewholepage)]  
  
 <span data-ttu-id="82b96-108">에 대 한 자세한 내용은 <xref:System.Windows.Media.StreamGeometry> 특성 구문, 참조는 [경로 태그 구문](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) 페이지.</span><span class="sxs-lookup"><span data-stu-id="82b96-108">For more information about <xref:System.Windows.Media.StreamGeometry> attribute syntax, see the [Path Markup Syntax](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) page.</span></span>  
  
## <a name="example"></a><span data-ttu-id="82b96-109">예</span><span class="sxs-lookup"><span data-stu-id="82b96-109">Example</span></span>  
 <span data-ttu-id="82b96-110">사용 하 여 다음 예제는 <xref:System.Windows.Media.StreamGeometry> 코드에서 삼각형을 정의 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="82b96-110">The next example uses a <xref:System.Windows.Media.StreamGeometry> to define a triangle in code.</span></span> <span data-ttu-id="82b96-111">먼저,이 예에서는 만듭니다는 <xref:System.Windows.Media.StreamGeometry>, 획득는 <xref:System.Windows.Media.StreamGeometryContext> 삼각형을 설명 하기 위해 사용 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82b96-111">First, the example creates a <xref:System.Windows.Media.StreamGeometry>, then obtains a <xref:System.Windows.Media.StreamGeometryContext> and uses it to describe the triangle.</span></span>  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#StreamGeometryTriangleExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/StreamGeometryTriangleExample.cs#streamgeometrytriangleexamplewholepage)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#StreamGeometryTriangleExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/streamgeometrytriangleexample.vb#streamgeometrytriangleexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="82b96-112">예</span><span class="sxs-lookup"><span data-stu-id="82b96-112">Example</span></span>  
 <span data-ttu-id="82b96-113">다음 예제를 사용 하는 메서드를 만들어는 <xref:System.Windows.Media.StreamGeometry> 및 <xref:System.Windows.Media.StreamGeometryContext> 를 기반으로 지정 된 매개 변수는 기 하 도형을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="82b96-113">The next example creates a method that uses a <xref:System.Windows.Media.StreamGeometry> and <xref:System.Windows.Media.StreamGeometryContext> to define a geometric shape based on specified parameters.</span></span>  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#StreamGeometryExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/StreamGeometryExample.cs#streamgeometryexamplewholepage)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#StreamGeometryExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/streamgeometryexample.vb#streamgeometryexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="82b96-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="82b96-114">See Also</span></span>  
 <xref:System.Windows.Media.PathGeometry>  
 <xref:System.Windows.Media.StreamGeometry>  
 <xref:System.Windows.Media.StreamGeometryContext>  
 [<span data-ttu-id="82b96-115">PathGeometry를 사용하여 도형 만들기</span><span class="sxs-lookup"><span data-stu-id="82b96-115">Create a Shape by Using a PathGeometry</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)  
 [<span data-ttu-id="82b96-116">Geometry 개요</span><span class="sxs-lookup"><span data-stu-id="82b96-116">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)
