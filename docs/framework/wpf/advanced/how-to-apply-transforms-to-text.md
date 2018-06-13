---
title: '방법: 텍스트에 변환 적용'
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], rotated text
- typography [WPF], scaled text
- skewed text [WPF]
- typography [WPF], translated text
- typography [WPF], shadowed text
- rotated text [WPF]
- translated text [WPF]
- shadowed text [WPF]
- transforms in text [WPF]
- typography [WPF], transforms
- scaled text [WPF]
- typography [WPF], skewed text
ms.assetid: 0d61678a-4185-4f2a-85c6-c1d020f96fa0
ms.openlocfilehash: 531537013ab3bbfba278ca63e14155341eefc826
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33544924"
---
# <a name="how-to-apply-transforms-to-text"></a><span data-ttu-id="ab43e-102">방법: 텍스트에 변환 적용</span><span class="sxs-lookup"><span data-stu-id="ab43e-102">How to: Apply Transforms to Text</span></span>
<span data-ttu-id="ab43e-103">변환을 통해 응용 프로그램에서 텍스트 표시를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab43e-103">Transforms can alter the display of text in your application.</span></span> <span data-ttu-id="ab43e-104">다음 예에서는 다양 한 유형의 렌더링 변환의 텍스트 표시에 영향을 사용 하 여 한 <xref:System.Windows.Controls.TextBlock> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab43e-104">The following examples use different types of rendering transforms to affect the display of text in a <xref:System.Windows.Controls.TextBlock> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ab43e-105">예제</span><span class="sxs-lookup"><span data-stu-id="ab43e-105">Example</span></span>  
 <span data-ttu-id="ab43e-106">다음 예에서는 2차원 x-y 평면에서 지정된 점을 기준으로 회전하는 텍스트를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab43e-106">The following example shows text rotated about a specified point in the two-dimensional x-y plane.</span></span>  
  
 <span data-ttu-id="ab43e-107">![RotateTransform을 사용 하 여 회전 된 텍스트](../../../../docs/framework/wpf/advanced/media/transformedtext01.jpg "TransformedText01")</span><span class="sxs-lookup"><span data-stu-id="ab43e-107">![Text rotated using a RotateTransform](../../../../docs/framework/wpf/advanced/media/transformedtext01.jpg "TransformedText01")</span></span>  
<span data-ttu-id="ab43e-108">90도 회전된 텍스트 예</span><span class="sxs-lookup"><span data-stu-id="ab43e-108">Example of text rotated 90 degrees</span></span>  
  
 <span data-ttu-id="ab43e-109">다음 코드 예제에서는 한 <xref:System.Windows.Media.RotateTransform> 텍스트 회전 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab43e-109">The following code example uses a <xref:System.Windows.Media.RotateTransform> to rotate text.</span></span> <span data-ttu-id="ab43e-110"><xref:System.Windows.Media.RotateTransform.Angle%2A> 값이 90 요소를 시계 반대 방향으로 90도 회전 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab43e-110">An <xref:System.Windows.Media.RotateTransform.Angle%2A> value of 90 rotates the element 90 degrees clockwise.</span></span>  
  
 [!code-xaml[TextTransformSample#TextTransformSample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample1)]  
  
 <span data-ttu-id="ab43e-111">다음 예에서는 텍스트의 두 번째 라인은 x축을 따라 배율을 150% 조정하여 보여주고, 텍스트의 세 번째 라인은 y축을 따라 배율을 150% 조정하여 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab43e-111">The following example shows the second line of text scaled by 150% along the x-axis, and the third line of text scaled by 150% along the y-axis.</span></span>  
  
 <span data-ttu-id="ab43e-112">![ScaleTransform을 사용 하 여 배율 조정 된 텍스트](../../../../docs/framework/wpf/advanced/media/transformedtext02.jpg "TransformedText02")</span><span class="sxs-lookup"><span data-stu-id="ab43e-112">![Text scaled using a ScaleTransform](../../../../docs/framework/wpf/advanced/media/transformedtext02.jpg "TransformedText02")</span></span>  
<span data-ttu-id="ab43e-113">배율 조정된 텍스트의 예</span><span class="sxs-lookup"><span data-stu-id="ab43e-113">Example of scaled text</span></span>  
  
 <span data-ttu-id="ab43e-114">다음 코드 예제에서는 한 <xref:System.Windows.Media.ScaleTransform> 원래 크기에서 텍스트 크기 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab43e-114">The following code example uses a <xref:System.Windows.Media.ScaleTransform> to scale text from its original size.</span></span>  
  
 [!code-xaml[TextTransformSample#TextTransformSample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample2)]  
  
> [!NOTE]
>  <span data-ttu-id="ab43e-115">텍스트의 배율 조정은 텍스트의 글꼴 크기를 늘리는 것과는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="ab43e-115">Scaling text is not the same as increasing the font size of text.</span></span> <span data-ttu-id="ab43e-116">여러 다른 크기에서 최상의 해상도를 제공하기 위해 글꼴 크기는 서로 독립적으로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab43e-116">Font sizes are calculated independently of each other in order to provide the best resolution at different sizes.</span></span> <span data-ttu-id="ab43e-117">한편 배율 조정된 크기는 원래 크기의 텍스트에 계속 비례합니다.</span><span class="sxs-lookup"><span data-stu-id="ab43e-117">Scaled text, on the other hand, preserves the proportions of the original-sized text.</span></span>  
  
 <span data-ttu-id="ab43e-118">다음 예에서는 x축을 따라 기울어진 텍스트를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab43e-118">The following example shows text skewed along the x-axis.</span></span>  
  
 <span data-ttu-id="ab43e-119">![SkewTransform을 사용 하 여 기울인 텍스트](../../../../docs/framework/wpf/advanced/media/transformedtext03.jpg "TransformedText03")</span><span class="sxs-lookup"><span data-stu-id="ab43e-119">![Text skewed using a SkewTransform](../../../../docs/framework/wpf/advanced/media/transformedtext03.jpg "TransformedText03")</span></span>  
<span data-ttu-id="ab43e-120">기울어진 텍스트의 예</span><span class="sxs-lookup"><span data-stu-id="ab43e-120">Example of skewed text</span></span>  
  
 <span data-ttu-id="ab43e-121">다음 코드 예제에서는 한 <xref:System.Windows.Media.SkewTransform> 를 텍스트를 기울입니다.</span><span class="sxs-lookup"><span data-stu-id="ab43e-121">The following code example uses a <xref:System.Windows.Media.SkewTransform> to skew text.</span></span> <span data-ttu-id="ab43e-122">전단이라고도 하는 기울이기는 일관되지 않은 방식으로 좌표 공간을 늘리는 변환입니다.</span><span class="sxs-lookup"><span data-stu-id="ab43e-122">A skew, also known as a shear, is a transformation that stretches the coordinate space in a non-uniform manner.</span></span> <span data-ttu-id="ab43e-123">이 예에서 두 텍스트 문자열은 x축을 따라 -30°와 30°를 기울입니다.</span><span class="sxs-lookup"><span data-stu-id="ab43e-123">In this example, the two text strings are skewed -30° and 30° along the x-coordinate.</span></span>  
  
 [!code-xaml[TextTransformSample#TextTransformSample3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample3)]  
  
 <span data-ttu-id="ab43e-124">다음 예에서는 x축과 y축을 따라 변환 또는 이동되는 텍스트를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab43e-124">The following example shows text translated, or moved, along the x- and y-axis.</span></span>  
  
 <span data-ttu-id="ab43e-125">![Translatetransform을 사용한 텍스트 오프셋](../../../../docs/framework/wpf/advanced/media/transformedtext04.jpg "TransformedText04")</span><span class="sxs-lookup"><span data-stu-id="ab43e-125">![Text offset using a TranslateTransform](../../../../docs/framework/wpf/advanced/media/transformedtext04.jpg "TransformedText04")</span></span>  
<span data-ttu-id="ab43e-126">변환된 텍스트의 예</span><span class="sxs-lookup"><span data-stu-id="ab43e-126">Example of translated text</span></span>  
  
 <span data-ttu-id="ab43e-127">다음 코드 예제에서는 한 <xref:System.Windows.Media.TranslateTransform> 텍스트 오프셋 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab43e-127">The following code example uses a <xref:System.Windows.Media.TranslateTransform> to offset text.</span></span> <span data-ttu-id="ab43e-128">이 예제에서 기본 텍스트 아래에 있는 약간 오프셋된 텍스트 복사본이 그림자 효과를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ab43e-128">In this example, a slightly offset copy of text below the primary text creates a shadow effect.</span></span>  
  
 [!code-xaml[TextTransformSample#TextTransformSample4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample4)]  
  
> [!NOTE]
>  <span data-ttu-id="ab43e-129"><xref:System.Windows.Media.Effects.DropShadowBitmapEffect> 그림자 효과 제공 하는 것에 대 한 다양 한 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab43e-129">The <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> provides a rich set of features for providing shadow effects.</span></span> <span data-ttu-id="ab43e-130">자세한 내용은 참조 [만들 텍스트 그림자가 적용 된](../../../../docs/framework/wpf/advanced/how-to-create-text-with-a-shadow.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ab43e-130">For more information, see [Create Text with a Shadow](../../../../docs/framework/wpf/advanced/how-to-create-text-with-a-shadow.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab43e-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ab43e-131">See Also</span></span>  
 [<span data-ttu-id="ab43e-132">텍스트에 애니메이션 적용</span><span class="sxs-lookup"><span data-stu-id="ab43e-132">Apply Animations to Text</span></span>](../../../../docs/framework/wpf/advanced/how-to-apply-animations-to-text.md)
