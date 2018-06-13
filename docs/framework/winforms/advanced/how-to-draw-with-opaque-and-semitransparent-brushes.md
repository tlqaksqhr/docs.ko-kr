---
title: '방법: 불투명 및 반투명 브러시를 사용하여 그리기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- semi-transparent shapes [Windows Forms], drawing
- transparency [Windows Forms], semi-transparent shapes
- alpha blending [Windows Forms], brush
- brushes [Windows Forms], using semi-transparent
ms.assetid: a4f6f6b8-3bc8-440a-84af-d62ef0f8ff40
ms.openlocfilehash: 91aa3e89e2ff6d20432dbc5e988f2877059b4cdd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33523610"
---
# <a name="how-to-draw-with-opaque-and-semitransparent-brushes"></a><span data-ttu-id="a1c0e-102">방법: 불투명 및 반투명 브러시를 사용하여 그리기</span><span class="sxs-lookup"><span data-stu-id="a1c0e-102">How to: Draw with Opaque and Semitransparent Brushes</span></span>
<span data-ttu-id="a1c0e-103">셰이프를 채울 때 <xref:System.Drawing.Brush> 개체를 <xref:System.Drawing.Graphics> 클래스의 채우기 메서드 중 하나에 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c0e-103">When you fill a shape, you must pass a <xref:System.Drawing.Brush> object to one of the fill methods of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="a1c0e-104"><xref:System.Drawing.SolidBrush.%23ctor%2A> 생성자의 매개 변수 중 하나는 <xref:System.Drawing.Color> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="a1c0e-104">The one parameter of the <xref:System.Drawing.SolidBrush.%23ctor%2A> constructor is a <xref:System.Drawing.Color> object.</span></span> <span data-ttu-id="a1c0e-105">불투명 셰이프를 채우려면 색의 알파 구성 요소를 255로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c0e-105">To fill an opaque shape, set the alpha component of the color to 255.</span></span> <span data-ttu-id="a1c0e-106">반투명 셰이프를 채우려면 알파 구성 요소를 1에서 254 사이의 임의 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c0e-106">To fill a semitransparent shape, set the alpha component to any value from 1 through 254.</span></span>  
  
 <span data-ttu-id="a1c0e-107">반투명 셰이프를 채우면 셰이프 색이 배경색과 혼합됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1c0e-107">When you fill a semitransparent shape, the color of the shape is blended with the colors of the background.</span></span> <span data-ttu-id="a1c0e-108">알파 구성 요소는 셰이프 색과 배경색을 혼합하는 방법을 지정합니다. 알파 값이 0에 가까우면 배경색에 더 많은 가중치가 적용되고 알파 값이 255에 가까우면 셰이프 색에 더 많은 가중치가 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1c0e-108">The alpha component specifies how the shape and background colors are mixed; alpha values near 0 place more weight on the background colors, and alpha values near 255 place more weight on the shape color.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a1c0e-109">예제</span><span class="sxs-lookup"><span data-stu-id="a1c0e-109">Example</span></span>  
 <span data-ttu-id="a1c0e-110">다음 예제에서는 비트맵을 그린 다음 이 비트맵과 겹치는 세 개의 타원을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="a1c0e-110">The following example draws a bitmap and then fills three ellipses that overlap the bitmap.</span></span> <span data-ttu-id="a1c0e-111">첫 번째 타원은 알파 구성 요소 255를 사용하므로 불투명합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c0e-111">The first ellipse uses an alpha component of 255, so it is opaque.</span></span> <span data-ttu-id="a1c0e-112">두 번째 및 세 번째 타원은 알파 구성 요소 128을 사용하므로 반투명합니다. 타원을 통과하는 배경 이미지를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1c0e-112">The second and third ellipses use an alpha component of 128, so they are semitransparent; you can see the background image through the ellipses.</span></span> <span data-ttu-id="a1c0e-113"><xref:System.Drawing.Graphics.CompositingQuality%2A> 속성을 설정하는 호출은 감마 보정과 함께 세 번째 타원에 대한 혼합이 수행되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c0e-113">The call that sets the <xref:System.Drawing.Graphics.CompositingQuality%2A> property causes the blending for the third ellipse to be done in conjunction with gamma correction.</span></span>  
  
 <span data-ttu-id="a1c0e-114">다음 그림에서는 다음 코드의 출력을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a1c0e-114">The following illustration shows the output of the following code.</span></span>  
  
 <span data-ttu-id="a1c0e-115">![불투명 및 반투명](../../../../docs/framework/winforms/advanced/media/compqualellipse.png "compqualellipse")</span><span class="sxs-lookup"><span data-stu-id="a1c0e-115">![Opaque and Semitransparent](../../../../docs/framework/winforms/advanced/media/compqualellipse.png "compqualellipse")</span></span>  
  
 [!code-csharp[System.Drawing.AlphaBlending#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.AlphaBlending#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a1c0e-116">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="a1c0e-116">Compiling the Code</span></span>  
 <span data-ttu-id="a1c0e-117">앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.PaintEventArgs>의 매개 변수인 `e`<xref:System.Windows.Forms.PaintEventHandler>가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c0e-117">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1c0e-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a1c0e-118">See Also</span></span>  
 [<span data-ttu-id="a1c0e-119">Windows Forms의 그래픽 및 그리기</span><span class="sxs-lookup"><span data-stu-id="a1c0e-119">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="a1c0e-120">선 및 채우기 알파 혼합</span><span class="sxs-lookup"><span data-stu-id="a1c0e-120">Alpha Blending Lines and Fills</span></span>](../../../../docs/framework/winforms/advanced/alpha-blending-lines-and-fills.md)  
 [<span data-ttu-id="a1c0e-121">방법: 컨트롤에 투명한 배경 적용</span><span class="sxs-lookup"><span data-stu-id="a1c0e-121">How to: Give Your Control a Transparent Background</span></span>](../../../../docs/framework/winforms/controls/how-to-give-your-control-a-transparent-background.md)  
 [<span data-ttu-id="a1c0e-122">방법: 불투명 및 반투명 선 그리기</span><span class="sxs-lookup"><span data-stu-id="a1c0e-122">How to: Draw Opaque and Semitransparent Lines</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-opaque-and-semitransparent-lines.md)
