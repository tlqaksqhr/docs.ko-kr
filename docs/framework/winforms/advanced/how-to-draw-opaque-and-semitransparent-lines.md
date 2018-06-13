---
title: '방법: 불투명 및 반투명 선 그리기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drawing [Windows Forms], lines
- transparency [Windows Forms], lines
- lines [Windows Forms], drawing alpha blended
- alpha blending [Windows Forms], drawing lines
ms.assetid: 8f2508af-f495-4223-b5cc-646cbbb520eb
ms.openlocfilehash: f6667b3ac5bbe5dd82198f7bf23047f01cd7350a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33524224"
---
# <a name="how-to-draw-opaque-and-semitransparent-lines"></a><span data-ttu-id="f9528-102">방법: 불투명 및 반투명 선 그리기</span><span class="sxs-lookup"><span data-stu-id="f9528-102">How to: Draw Opaque and Semitransparent Lines</span></span>
<span data-ttu-id="f9528-103">선을 그리는 경우 <xref:System.Drawing.Pen> 개체를 <xref:System.Drawing.Graphics> 클래스의 <xref:System.Drawing.Graphics.DrawLine%2A> 메서드에 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9528-103">When you draw a line, you must pass a <xref:System.Drawing.Pen> object to the <xref:System.Drawing.Graphics.DrawLine%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="f9528-104"><xref:System.Drawing.Pen.%23ctor%2A> 생성자의 매개 변수 중 하나는 <xref:System.Drawing.Color> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="f9528-104">One of the parameters of the <xref:System.Drawing.Pen.%23ctor%2A> constructor is a <xref:System.Drawing.Color> object.</span></span> <span data-ttu-id="f9528-105">불투명 선을 그리려면 색의 알파 구성 요소를 255로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f9528-105">To draw an opaque line, set the alpha component of the color to 255.</span></span> <span data-ttu-id="f9528-106">반투명 선을 그리려면 알파 구성 요소를 1에서 254 사이의 임의 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f9528-106">To draw a semitransparent line, set the alpha component to any value from 1 through 254.</span></span>  
  
 <span data-ttu-id="f9528-107">배경 위에 반투명 선을 그리면 선 색이 배경색과 혼합됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9528-107">When you draw a semitransparent line over a background, the color of the line is blended with the colors of the background.</span></span> <span data-ttu-id="f9528-108">알파 구성 요소는 선 색과 배경색을 혼합하는 방법을 지정합니다. 알파 값이 0에 가까우면 배경색에 더 많은 가중치가 적용되고 알파 값이 255에 가까우면 선 색에 더 많은 가중치가 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f9528-108">The alpha component specifies how the line and background colors are mixed; alpha values near 0 place more weight on the background colors, and alpha values near 255 place more weight on the line color.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f9528-109">예제</span><span class="sxs-lookup"><span data-stu-id="f9528-109">Example</span></span>  
 <span data-ttu-id="f9528-110">다음 예제에서는 비트맵을 그린 다음 이 비트맵을 배경으로 사용하는 세 개의 선을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="f9528-110">The following example draws a bitmap and then draws three lines that use the bitmap as a background.</span></span> <span data-ttu-id="f9528-111">첫 번째 선은 알파 구성 요소 255를 사용하므로 불투명합니다.</span><span class="sxs-lookup"><span data-stu-id="f9528-111">The first line uses an alpha component of 255, so it is opaque.</span></span> <span data-ttu-id="f9528-112">두 번째 및 세 번째 선은 알파 구성 요소 128을 사용하므로 반투명합니다. 선을 통과하는 배경 이미지를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f9528-112">The second and third lines use an alpha component of 128, so they are semitransparent; you can see the background image through the lines.</span></span> <span data-ttu-id="f9528-113"><xref:System.Drawing.Graphics.CompositingQuality%2A> 속성을 설정하는 문은 감마 보정과 함께 세 번째 선에 대한 혼합이 수행되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9528-113">The statement that sets the <xref:System.Drawing.Graphics.CompositingQuality%2A> property causes the blending for the third line to be done in conjunction with gamma correction.</span></span>  
  
 <span data-ttu-id="f9528-114">다음 그림에서는 다음 코드의 출력을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f9528-114">The following illustration shows the output of the following code.</span></span>  
  
 <span data-ttu-id="f9528-115">![불투명 및 반투명](../../../../docs/framework/winforms/advanced/media/compqualline.png "compqualline")</span><span class="sxs-lookup"><span data-stu-id="f9528-115">![Opaque and Semitransparent](../../../../docs/framework/winforms/advanced/media/compqualline.png "compqualline")</span></span>  
  
 [!code-csharp[System.Drawing.AlphaBlending#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.AlphaBlending#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f9528-116">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="f9528-116">Compiling the Code</span></span>  
 <span data-ttu-id="f9528-117">앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.PaintEventArgs> 이벤트 처리기의 매개 변수인 `e`<xref:System.Windows.Forms.Control.Paint>가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f9528-117">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9528-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f9528-118">See Also</span></span>  
 [<span data-ttu-id="f9528-119">선 및 채우기 알파 혼합</span><span class="sxs-lookup"><span data-stu-id="f9528-119">Alpha Blending Lines and Fills</span></span>](../../../../docs/framework/winforms/advanced/alpha-blending-lines-and-fills.md)  
 [<span data-ttu-id="f9528-120">방법: 컨트롤에 투명한 배경 적용</span><span class="sxs-lookup"><span data-stu-id="f9528-120">How to: Give Your Control a Transparent Background</span></span>](../../../../docs/framework/winforms/controls/how-to-give-your-control-a-transparent-background.md)  
 [<span data-ttu-id="f9528-121">방법: 불투명 및 반투명 브러시를 사용하여 그리기</span><span class="sxs-lookup"><span data-stu-id="f9528-121">How to: Draw with Opaque and Semitransparent Brushes</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-with-opaque-and-semitransparent-brushes.md)
