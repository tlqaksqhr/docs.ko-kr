---
title: '방법: 기하학적 경로를 사용하여 개체 회전'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- geometric paths [WPF], rotating objects by
- rotating objects by geometric paths [WPF]
ms.assetid: cb31ca4d-f05a-4c6b-9a18-4b6faaf38d45
ms.openlocfilehash: 5a73ee967be0aae7dc3f1ef82229c2bcb2f9ade2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33560718"
---
# <a name="how-to-rotate-an-object-by-using-a-geometric-path"></a><span data-ttu-id="12314-102">방법: 기하학적 경로를 사용하여 개체 회전</span><span class="sxs-lookup"><span data-stu-id="12314-102">How to: Rotate an Object by Using a Geometric Path</span></span>
<span data-ttu-id="12314-103">이 예제에서 정의 된 기하학적 경로 따라 개체 (피벗)를 회전 하는 방법을 보여 줍니다는 <xref:System.Windows.Media.PathGeometry> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="12314-103">This example shows how to rotate (pivot) an object along a geometric path that is defined by a <xref:System.Windows.Media.PathGeometry> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="12314-104">예제</span><span class="sxs-lookup"><span data-stu-id="12314-104">Example</span></span>  
 <span data-ttu-id="12314-105">다음 예제에서는 세 개의 <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> 사각형 기하학적 경로 따라 이동 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="12314-105">The following example uses three <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> objects to move a rectangle along a geometric path.</span></span>  
  
-   <span data-ttu-id="12314-106">첫 번째 <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> 애니메이션 효과 적용 한 <xref:System.Windows.Media.RotateTransform> 사각형에 적용 되는 합니다.</span><span class="sxs-lookup"><span data-stu-id="12314-106">The first <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> animates a <xref:System.Windows.Media.RotateTransform> that is applied to the rectangle.</span></span> <span data-ttu-id="12314-107">애니메이션은 각도 값을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="12314-107">The animation generates angle values.</span></span> <span data-ttu-id="12314-108">이를 통해 사각형이 경로 윤곽을 따라 회전(피벗)하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="12314-108">It makes the rectangle rotate (pivot) along the contours of the path.</span></span>  
  
-   <span data-ttu-id="12314-109">다른 두 개의 개체에 애니메이션을 적용는 <xref:System.Windows.Media.TranslateTransform.X%2A> 및 <xref:System.Windows.Media.TranslateTransform.Y%2A> 의 값을 <xref:System.Windows.Media.TranslateTransform> 사각형에 적용 되는 합니다.</span><span class="sxs-lookup"><span data-stu-id="12314-109">The other two objects animate the <xref:System.Windows.Media.TranslateTransform.X%2A> and <xref:System.Windows.Media.TranslateTransform.Y%2A> values of a <xref:System.Windows.Media.TranslateTransform> that is applied to the rectangle.</span></span> <span data-ttu-id="12314-110">이를 통해 사각형이 경로를 따라 가로 및 세로로 이동하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="12314-110">They make the rectangle move horizontally and vertically along the path.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#RotateAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/rotateanimationusingpathexample.xaml#rotateanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#RotateAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/RotateAnimationUsingPathExample.cs#rotateanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#RotateAnimationUsingPathWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/RotateAnimationUsingPathExample.vb#rotateanimationusingpathwholepage)]  
  
 <span data-ttu-id="12314-111">기하학적 경로 사용 하 여 개체를 회전 하는 다른 방법은 사용 하는 것을 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> 개체 및 설정의 <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> 속성을 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="12314-111">Another way to rotate an object by using a geometric path is to use a <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> object and set its <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> property to `true`.</span></span> <span data-ttu-id="12314-112">자세한 내용 및 예제에 대 한 참조 [기하학적 경로 (매트릭스 애니메이션)을 사용 하 여 개체를 회전](../../../../docs/framework/wpf/graphics-multimedia/how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="12314-112">For more information and an example, see [Rotate an Object by Using a Geometric Path (Matrix Animation)](../../../../docs/framework/wpf/graphics-multimedia/how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation.md).</span></span>  
  
 <span data-ttu-id="12314-113">전체 샘플을 참조 하십시오. [경로 애니메이션 샘플](http://go.microsoft.com/fwlink/?LinkID=160028)합니다.</span><span class="sxs-lookup"><span data-stu-id="12314-113">For the complete sample, see [Path Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160028).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12314-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="12314-114">See Also</span></span>  
 [<span data-ttu-id="12314-115">애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="12314-115">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="12314-116">경로 애니메이션 샘플</span><span class="sxs-lookup"><span data-stu-id="12314-116">Path Animation Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=160028)  
 [<span data-ttu-id="12314-117">경로 애니메이션 방법 항목</span><span class="sxs-lookup"><span data-stu-id="12314-117">Path Animation How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)
