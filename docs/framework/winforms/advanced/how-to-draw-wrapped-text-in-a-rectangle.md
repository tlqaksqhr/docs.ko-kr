---
title: '방법: 사각형 안에 줄 바꿈된 텍스트 그리기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, drawing text in a rectangle
- text [Windows Forms], drawing in a rectangle
- strings [Windows Forms], drawing in a rectangle
ms.assetid: e1fb432a-dc90-48b5-9b6b-acc14507133d
ms.openlocfilehash: c753be6a200f166e59e1330c7dbcf1fadc7588a6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33524975"
---
# <a name="how-to-draw-wrapped-text-in-a-rectangle"></a><span data-ttu-id="a666c-102">방법: 사각형 안에 줄 바꿈된 텍스트 그리기</span><span class="sxs-lookup"><span data-stu-id="a666c-102">How to: Draw Wrapped Text in a Rectangle</span></span>
<span data-ttu-id="a666c-103">사용 하 여 사각형 안에 줄 바꿈된 텍스트를 그릴 수 있습니다는 <xref:System.Drawing.Graphics.DrawString%2A> 의 메서드를 오버 로드는 <xref:System.Drawing.Graphics> 클래스를 사용 하는 <xref:System.Drawing.Rectangle> 또는 <xref:System.Drawing.RectangleF> 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="a666c-103">You can draw wrapped text in a rectangle by using the <xref:System.Drawing.Graphics.DrawString%2A> overloaded method of the <xref:System.Drawing.Graphics> class that takes a <xref:System.Drawing.Rectangle> or <xref:System.Drawing.RectangleF> parameter.</span></span> <span data-ttu-id="a666c-104">사용할 수도 있습니다는 <xref:System.Drawing.Brush> 및 <xref:System.Drawing.Font>합니다.</span><span class="sxs-lookup"><span data-stu-id="a666c-104">You will also use a <xref:System.Drawing.Brush> and a <xref:System.Drawing.Font>.</span></span>  
  
 <span data-ttu-id="a666c-105">사용 하 여 사각형 안에 줄 바꿈된 텍스트를 그릴 수도 있습니다는 <xref:System.Windows.Forms.TextRenderer.DrawText%2A> 의 메서드를 오버 로드는 <xref:System.Windows.Forms.TextRenderer> 를 사용 하는 <xref:System.Drawing.Rectangle> 및 <xref:System.Windows.Forms.TextFormatFlags> 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="a666c-105">You can also draw wrapped text in a rectangle by using the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> overloaded method of the <xref:System.Windows.Forms.TextRenderer> that takes a <xref:System.Drawing.Rectangle> and a <xref:System.Windows.Forms.TextFormatFlags> parameter.</span></span> <span data-ttu-id="a666c-106">사용할 수도 있습니다는 <xref:System.Drawing.Color> 및 <xref:System.Drawing.Font>합니다.</span><span class="sxs-lookup"><span data-stu-id="a666c-106">You will also use a <xref:System.Drawing.Color> and a <xref:System.Drawing.Font>.</span></span>  
  
 <span data-ttu-id="a666c-107">다음 그림과 텍스트 출력을 사용 하 여 그린 사각형에는 <xref:System.Drawing.Graphics.DrawString%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="a666c-107">The following illustration shows the output of text drawn in the rectangle when you use the <xref:System.Drawing.Graphics.DrawString%2A> method.</span></span>  
  
 <span data-ttu-id="a666c-108">![글꼴 텍스트](../../../../docs/framework/winforms/advanced/media/csfontstext2.png "csfontstext2")</span><span class="sxs-lookup"><span data-stu-id="a666c-108">![Fonts Text](../../../../docs/framework/winforms/advanced/media/csfontstext2.png "csfontstext2")</span></span>  
  
### <a name="to-draw-wrapped-text-in-a-rectangle-with-gdi"></a><span data-ttu-id="a666c-109">GDI + 사용 하 여 사각형 안에 줄 바꿈된 텍스트를 그리기</span><span class="sxs-lookup"><span data-stu-id="a666c-109">To draw wrapped text in a rectangle with GDI+</span></span>  
  
1.  <span data-ttu-id="a666c-110">사용 하 여는 <xref:System.Drawing.Graphics.DrawString%2A> 텍스트를 전달 하는 메서드를 오버 로드 된 <xref:System.Drawing.Rectangle> 또는 <xref:System.Drawing.RectangleF>, <xref:System.Drawing.Font> 및 <xref:System.Drawing.Brush>합니다.</span><span class="sxs-lookup"><span data-stu-id="a666c-110">Use the <xref:System.Drawing.Graphics.DrawString%2A> overloaded method, passing the text you want, <xref:System.Drawing.Rectangle> or <xref:System.Drawing.RectangleF>, <xref:System.Drawing.Font> and <xref:System.Drawing.Brush>.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#50](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#50)]
     [!code-vb[System.Drawing.AlignDrawnText#50](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#50)]  
  
### <a name="to-draw-wrapped-text-in-a-rectangle-with-gdi"></a><span data-ttu-id="a666c-111">GDI 사용 하 여 사각형 안에 줄 바꿈된 텍스트를 그리기</span><span class="sxs-lookup"><span data-stu-id="a666c-111">To draw wrapped text in a rectangle with GDI</span></span>  
  
1.  <span data-ttu-id="a666c-112">사용 하 여는 <xref:System.Windows.Forms.TextFormatFlags> 와 텍스트를 지정 하려면 열거형 값을 래핑하는 <xref:System.Windows.Forms.TextRenderer.DrawText%2A> 텍스트를 전달 하는 메서드를 오버 로드 된 <xref:System.Drawing.Rectangle>, <xref:System.Drawing.Font> 및 <xref:System.Drawing.Color>합니다.</span><span class="sxs-lookup"><span data-stu-id="a666c-112">Use the <xref:System.Windows.Forms.TextFormatFlags> enumeration value to specify the text should be wrapped with the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> overloaded method, passing the text you want, <xref:System.Drawing.Rectangle>, <xref:System.Drawing.Font> and <xref:System.Drawing.Color>.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#60](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#60)]
     [!code-vb[System.Drawing.AlignDrawnText#60](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#60)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a666c-113">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="a666c-113">Compiling the Code</span></span>  
 <span data-ttu-id="a666c-114">이전 예제 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a666c-114">The previous examples require:</span></span>  
  
-   <span data-ttu-id="a666c-115"><xref:System.Windows.Forms.PaintEventArgs> `e`의 매개 변수인 <xref:System.Windows.Forms.PaintEventHandler>합니다.</span><span class="sxs-lookup"><span data-stu-id="a666c-115"><xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a666c-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a666c-116">See Also</span></span>  
 [<span data-ttu-id="a666c-117">방법: GDI를 사용하여 텍스트 그리기</span><span class="sxs-lookup"><span data-stu-id="a666c-117">How to: Draw Text with GDI</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)  
 [<span data-ttu-id="a666c-118">글꼴 및 텍스트 사용</span><span class="sxs-lookup"><span data-stu-id="a666c-118">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)  
 [<span data-ttu-id="a666c-119">방법: 글꼴 패밀리 및 글꼴 만들기</span><span class="sxs-lookup"><span data-stu-id="a666c-119">How to: Construct Font Families and Fonts</span></span>](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)  
 [<span data-ttu-id="a666c-120">방법: 지정된 위치에 텍스트 그리기</span><span class="sxs-lookup"><span data-stu-id="a666c-120">How to: Draw Text at a Specified Location</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-text-at-a-specified-location.md)
