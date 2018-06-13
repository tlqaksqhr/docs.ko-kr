---
title: '방법: 이미지로 영역 그리기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [WPF], painting with
- painting [WPF], with images
- brushes [WPF], painting with images
ms.assetid: 3432c533-1fc7-492d-94ee-0b13d60125ae
ms.openlocfilehash: 4efecc3c8083396d4c06d86d9ece01bd584a1c6d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33560960"
---
# <a name="how-to-paint-an-area-with-an-image"></a><span data-ttu-id="07520-102">방법: 이미지로 영역 그리기</span><span class="sxs-lookup"><span data-stu-id="07520-102">How to: Paint an Area with an Image</span></span>
<span data-ttu-id="07520-103">사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.ImageBrush> 이미지 영역을 그리는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="07520-103">This example shows how to use the <xref:System.Windows.Media.ImageBrush> class to paint an area with an image.</span></span> <span data-ttu-id="07520-104"><xref:System.Windows.Media.ImageBrush> 변수에 지정 된 단일 이미지를 표시 합니다. 해당 <xref:System.Windows.Media.ImageBrush.ImageSource%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="07520-104">An <xref:System.Windows.Media.ImageBrush> displays a single image, which is specified by its <xref:System.Windows.Media.ImageBrush.ImageSource%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="07520-105">예제</span><span class="sxs-lookup"><span data-stu-id="07520-105">Example</span></span>  
 <span data-ttu-id="07520-106">다음 예제에서는 그리기는 <xref:System.Windows.Controls.Control.Background%2A> 를 사용 하 여 단추는 <xref:System.Windows.Media.ImageBrush>합니다.</span><span class="sxs-lookup"><span data-stu-id="07520-106">The following example paints the <xref:System.Windows.Controls.Control.Background%2A> of a button by using an <xref:System.Windows.Media.ImageBrush>.</span></span>  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/PaintingWithImagesExample.cs#imagebrushexamplewholepage)]  
  
 <span data-ttu-id="07520-107">기본적으로는 <xref:System.Windows.Media.ImageBrush> 완전히 사용자 칠하고 있는 영역을 채우도록 이미지를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="07520-107">By default, an <xref:System.Windows.Media.ImageBrush> stretches its image to completely fill the area that you are painting.</span></span> <span data-ttu-id="07520-108">위의 예제에서는 이미지가 단추를 채우도록 확장되므로 이미지가 왜곡될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07520-108">In the preceding example, the image is stretched to fill the button, possibly distorting the image.</span></span> <span data-ttu-id="07520-109">설정 하 여이 동작을 제어할 수는 <xref:System.Windows.Media.TileBrush.Stretch%2A> 속성 <xref:System.Windows.Media.TileBrush> 를 <xref:System.Windows.Media.Stretch.Uniform> 또는 <xref:System.Windows.Media.Stretch.UniformToFill>, 이미지의 가로 세로 비율을 유지 하도록 브러시에 이르게 합니다.</span><span class="sxs-lookup"><span data-stu-id="07520-109">You can control this behavior by setting the <xref:System.Windows.Media.TileBrush.Stretch%2A> property of <xref:System.Windows.Media.TileBrush> to <xref:System.Windows.Media.Stretch.Uniform> or <xref:System.Windows.Media.Stretch.UniformToFill>, which causes the brush to preserve the aspect ratio of the image.</span></span>  
  
 <span data-ttu-id="07520-110">설정 하는 경우는 <xref:System.Windows.Media.TileBrush.Viewport%2A> 및 <xref:System.Windows.Media.TileBrush.TileMode%2A> 속성의는 <xref:System.Windows.Media.ImageBrush>, 반복을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07520-110">If you set the <xref:System.Windows.Media.TileBrush.Viewport%2A> and <xref:System.Windows.Media.TileBrush.TileMode%2A> properties of an <xref:System.Windows.Media.ImageBrush>, you can create a repeating pattern.</span></span> <span data-ttu-id="07520-111">다음 예제에서는 이미지에서 만들어지는 패턴을 사용하여 단추를 그립니다.</span><span class="sxs-lookup"><span data-stu-id="07520-111">The following example paints a button by using a pattern that is created from an image.</span></span>  
  
 [!code-csharp[UsingImageBrush_snip#TiledImageBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TiledImageBrushExample.cs#tiledimagebrushexamplewholepage)]
 [!code-vb[UsingImageBrush_snip#TiledImageBrushExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UsingImageBrush_snip/VisualBasic/TiledImageBrushExample.vb#tiledimagebrushexamplewholepage)]  
  
 <span data-ttu-id="07520-112">에 대 한 자세한 내용은 <xref:System.Windows.Media.ImageBrush> 클래스를 참조 하십시오. [이미지, 그리기, 및 시각적 개체를 사용 하 여 그리기](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="07520-112">For more information about the <xref:System.Windows.Media.ImageBrush> class, see [Painting with Images, Drawings, and Visuals](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).</span></span>  
  
 <span data-ttu-id="07520-113">이 코드 예제는 제공 된 큰 예제의 일부는 <xref:System.Windows.Media.ImageBrush> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="07520-113">This code example is part of a larger example that is provided for the <xref:System.Windows.Media.ImageBrush> class.</span></span> <span data-ttu-id="07520-114">전체 샘플을 참조 하십시오. [ImageBrush 샘플](http://go.microsoft.com/fwlink/?LinkID=160005)합니다.</span><span class="sxs-lookup"><span data-stu-id="07520-114">For the complete sample, see [ImageBrush Sample](http://go.microsoft.com/fwlink/?LinkID=160005).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07520-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="07520-115">See Also</span></span>  
 [<span data-ttu-id="07520-116">이미지, 그림 및 시각적 표시로 그리기</span><span class="sxs-lookup"><span data-stu-id="07520-116">Painting with Images, Drawings, and Visuals</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
