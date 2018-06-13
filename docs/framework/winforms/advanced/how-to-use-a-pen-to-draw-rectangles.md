---
title: '방법: 펜을 사용하여 사각형 그리기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- rectangles [Windows Forms], drawing
- pens [Windows Forms], drawing rectangles
ms.assetid: 54a7fa14-3ad8-4d64-b424-2a12005b250c
ms.openlocfilehash: ad5b436f7162c282198c7a9d3cce4d3ce3fd3c6f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33524009"
---
# <a name="how-to-use-a-pen-to-draw-rectangles"></a><span data-ttu-id="dd322-102">방법: 펜을 사용하여 사각형 그리기</span><span class="sxs-lookup"><span data-stu-id="dd322-102">How to: Use a Pen to Draw Rectangles</span></span>
<span data-ttu-id="dd322-103">사각형 그리기, 하려면는 <xref:System.Drawing.Graphics> 개체 및 <xref:System.Drawing.Pen> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="dd322-103">To draw rectangles, you need a <xref:System.Drawing.Graphics> object and a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="dd322-104"><xref:System.Drawing.Graphics> 개체를 제공는 <xref:System.Drawing.Graphics.DrawRectangle%2A> 메서드, 및 <xref:System.Drawing.Pen> 개체 선의 색 및 너비와 같은 기능을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd322-104">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.DrawRectangle%2A> method, and the <xref:System.Drawing.Pen> object stores features of the line, such as color and width.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dd322-105">예제</span><span class="sxs-lookup"><span data-stu-id="dd322-105">Example</span></span>  
 <span data-ttu-id="dd322-106">다음 예제에서는 왼쪽 위 모퉁이가으로 사각형을 그립니다 (10, 10).</span><span class="sxs-lookup"><span data-stu-id="dd322-106">The following example draws a rectangle with its upper-left corner at (10, 10).</span></span> <span data-ttu-id="dd322-107">사각형의 너비를 100 고 50 높이입니다.</span><span class="sxs-lookup"><span data-stu-id="dd322-107">The rectangle has a width of 100 and a height of 50.</span></span> <span data-ttu-id="dd322-108">에 전달 되는 두 번째 인수는 <xref:System.Drawing.Pen.%23ctor%2A> 생성자 펜 너비는 5 픽셀 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="dd322-108">The second argument passed to the <xref:System.Drawing.Pen.%23ctor%2A> constructor indicates that the pen width is 5 pixels.</span></span>  
  
 <span data-ttu-id="dd322-109">사각형을 그릴 때 펜 사각형의 경계에서 가운데 맞춤 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd322-109">When the rectangle is drawn, the pen is centered on the rectangle's boundary.</span></span> <span data-ttu-id="dd322-110">사각형의 면은 그려지는 5 픽셀의 펜 너비는 5 이므로 해당 1 픽셀 그려집니다 너비로 자체 경계에 2 픽셀은 내부적으로 그려지며 2 픽셀 바깥쪽에 그려집니다.</span><span class="sxs-lookup"><span data-stu-id="dd322-110">Because the pen width is 5, the sides of the rectangle are drawn 5 pixels wide, such that 1 pixel is drawn on the boundary itself, 2 pixels are drawn on the inside, and 2 pixels are drawn on the outside.</span></span> <span data-ttu-id="dd322-111">펜 맞춤에 대 한 자세한 내용은 참조 하십시오. [하는 방법: 펜 굵기 설정 및 맞춤](../../../../docs/framework/winforms/advanced/how-to-set-pen-width-and-alignment.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="dd322-111">For more details on pen alignment, see [How to: Set Pen Width and Alignment](../../../../docs/framework/winforms/advanced/how-to-set-pen-width-and-alignment.md).</span></span>  
  
 <span data-ttu-id="dd322-112">다음 그림에서는 결과 사각형을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dd322-112">The following illustration shows the resulting rectangle.</span></span> <span data-ttu-id="dd322-113">여기서 사각형 그려지는 펜 굵기 하나의 픽셀 했다면 점선은 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd322-113">The dotted lines show where the rectangle would have been drawn if the pen width had been one pixel.</span></span> <span data-ttu-id="dd322-114">사각형의 왼쪽 위 모퉁이의 확대 뷰 두꺼운 검정 선 가운데 해당 텍스트에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd322-114">The enlarged view of the upper-left corner of the rectangle shows that the thick black lines are centered on those dotted lines.</span></span>  
  
 <span data-ttu-id="dd322-115">![펜](../../../../docs/framework/winforms/advanced/media/pens1.gif "pens1")</span><span class="sxs-lookup"><span data-stu-id="dd322-115">![Pens](../../../../docs/framework/winforms/advanced/media/pens1.gif "pens1")</span></span>  
  
 [!code-csharp[System.Drawing.UsingAPen#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.UsingAPen#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="dd322-116">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="dd322-116">Compiling the Code</span></span>  
 <span data-ttu-id="dd322-117">앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.PaintEventArgs> 이벤트 처리기의 매개 변수인 `e`<xref:System.Windows.Forms.Control.Paint>가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="dd322-117">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd322-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dd322-118">See Also</span></span>  
 [<span data-ttu-id="dd322-119">펜을 사용하여 선과 도형 그리기</span><span class="sxs-lookup"><span data-stu-id="dd322-119">Using a Pen to Draw Lines and Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
