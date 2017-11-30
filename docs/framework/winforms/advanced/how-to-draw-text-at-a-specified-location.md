---
title: "방법: 지정된 위치에 텍스트 그리기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], drawing at specified locations [Windows Forms]
- drawing text
- drawing text [Windows Forms], specified locations [Windows Forms]
- Windows Forms, drawing text a a specified location
ms.assetid: 60816423-1c38-465e-980d-2c2b64d74086
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: aab9570b98caec5b3975a5b3ff6f1e62d4ad303b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-text-at-a-specified-location"></a><span data-ttu-id="74ad7-102">방법: 지정된 위치에 텍스트 그리기</span><span class="sxs-lookup"><span data-stu-id="74ad7-102">How to: Draw Text at a Specified Location</span></span>
<span data-ttu-id="74ad7-103">사용자 지정 그리기를 수행 하는 경우 지정된 된 위치 에서부터 단일 가로 줄의 텍스트를 그릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74ad7-103">When you perform custom drawing, you can draw text in a single horizontal line starting at a specified point.</span></span> <span data-ttu-id="74ad7-104">사용 하 여 이런이 방식으로 텍스트를 그릴 수 있습니다는 <xref:System.Drawing.Graphics.DrawString%2A> 의 메서드를 오버 로드는 <xref:System.Drawing.Graphics> 클래스를 사용 하는 <xref:System.Drawing.Point> 또는 <xref:System.Drawing.PointF> 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="74ad7-104">You can draw text in this manner by using the <xref:System.Drawing.Graphics.DrawString%2A> overloaded method of the <xref:System.Drawing.Graphics> class that takes a <xref:System.Drawing.Point> or <xref:System.Drawing.PointF> parameter.</span></span> <span data-ttu-id="74ad7-105"><xref:System.Drawing.Graphics.DrawString%2A> 방법을 사용 하려면 한 <xref:System.Drawing.Brush> 및<xref:System.Drawing.Font></span><span class="sxs-lookup"><span data-stu-id="74ad7-105">The <xref:System.Drawing.Graphics.DrawString%2A> method also requires a <xref:System.Drawing.Brush> and <xref:System.Drawing.Font></span></span>  
  
 <span data-ttu-id="74ad7-106">사용할 수도 있습니다는 <xref:System.Windows.Forms.TextRenderer.DrawText%2A> 의 메서드를 오버 로드는 <xref:System.Windows.Forms.TextRenderer> 를 사용 하는 <xref:System.Drawing.Point>합니다.</span><span class="sxs-lookup"><span data-stu-id="74ad7-106">You can also use the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> overloaded method of the <xref:System.Windows.Forms.TextRenderer> that takes a <xref:System.Drawing.Point>.</span></span> <span data-ttu-id="74ad7-107"><xref:System.Windows.Forms.TextRenderer.DrawText%2A>또한 필요는 <xref:System.Drawing.Color> 및 <xref:System.Drawing.Font>합니다.</span><span class="sxs-lookup"><span data-stu-id="74ad7-107"><xref:System.Windows.Forms.TextRenderer.DrawText%2A> also requires a <xref:System.Drawing.Color> and a <xref:System.Drawing.Font>.</span></span>  
  
 <span data-ttu-id="74ad7-108">다음 그림과 사용 하 여 지정 된 기간의 그린 텍스트의 출력은 <xref:System.Drawing.Graphics.DrawString%2A> 오버 로드 된 메서드.</span><span class="sxs-lookup"><span data-stu-id="74ad7-108">The following illustration shows the output of text drawn at a specified point when you use the <xref:System.Drawing.Graphics.DrawString%2A> overloaded method.</span></span>  
  
 <span data-ttu-id="74ad7-109">![글꼴 텍스트](../../../../docs/framework/winforms/advanced/media/csfontstext1.png "csfontstext1")</span><span class="sxs-lookup"><span data-stu-id="74ad7-109">![Fonts Text](../../../../docs/framework/winforms/advanced/media/csfontstext1.png "csfontstext1")</span></span>  
  
### <a name="to-draw-a-line-of-text-with-gdi"></a><span data-ttu-id="74ad7-110">GDI + 된 텍스트의 선을 그리려면</span><span class="sxs-lookup"><span data-stu-id="74ad7-110">To draw a line of text with GDI+</span></span>  
  
1.  <span data-ttu-id="74ad7-111">사용 하 여는 <xref:System.Drawing.Graphics.DrawString%2A> 텍스트를 전달 하는 메서드, <xref:System.Drawing.Point> 또는 <xref:System.Drawing.PointF>, <xref:System.Drawing.Font>, 및 <xref:System.Drawing.Brush>합니다.</span><span class="sxs-lookup"><span data-stu-id="74ad7-111">Use the <xref:System.Drawing.Graphics.DrawString%2A> method, passing the text you want, <xref:System.Drawing.Point> or <xref:System.Drawing.PointF>, <xref:System.Drawing.Font>, and <xref:System.Drawing.Brush>.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#30)]
     [!code-vb[System.Drawing.AlignDrawnText#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#30)]  
  
### <a name="to-draw-a-line-of-text-with-gdi"></a><span data-ttu-id="74ad7-112">GDI 된 텍스트의 선을 그리려면</span><span class="sxs-lookup"><span data-stu-id="74ad7-112">To draw a line of text with GDI</span></span>  
  
1.  <span data-ttu-id="74ad7-113">사용 하 여는 <xref:System.Windows.Forms.TextRenderer.DrawText%2A> 텍스트를 전달 하는 메서드, <xref:System.Drawing.Point>, <xref:System.Drawing.Font>, 및 <xref:System.Drawing.Color>합니다.</span><span class="sxs-lookup"><span data-stu-id="74ad7-113">Use the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> method, passing the text you want, <xref:System.Drawing.Point>, <xref:System.Drawing.Font>, and <xref:System.Drawing.Color>.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#40](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#40)]
     [!code-vb[System.Drawing.AlignDrawnText#40](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#40)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="74ad7-114">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="74ad7-114">Compiling the Code</span></span>  
 <span data-ttu-id="74ad7-115">이전 예제 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="74ad7-115">The previous examples require:</span></span>  
  
-   <span data-ttu-id="74ad7-116"><xref:System.Windows.Forms.PaintEventArgs>  `e`의 매개 변수인 <xref:System.Windows.Forms.PaintEventHandler>합니다.</span><span class="sxs-lookup"><span data-stu-id="74ad7-116"><xref:System.Windows.Forms.PaintEventArgs>  `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74ad7-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="74ad7-117">See Also</span></span>  
 [<span data-ttu-id="74ad7-118">방법: GDI를 사용하여 텍스트 그리기</span><span class="sxs-lookup"><span data-stu-id="74ad7-118">How to: Draw Text with GDI</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)  
 [<span data-ttu-id="74ad7-119">글꼴 및 텍스트 사용</span><span class="sxs-lookup"><span data-stu-id="74ad7-119">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)  
 [<span data-ttu-id="74ad7-120">방법: 글꼴 패밀리 및 글꼴 만들기</span><span class="sxs-lookup"><span data-stu-id="74ad7-120">How to: Construct Font Families and Fonts</span></span>](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)  
 [<span data-ttu-id="74ad7-121">방법: 사각형 안에 줄 바꿈된 텍스트 그리기</span><span class="sxs-lookup"><span data-stu-id="74ad7-121">How to: Draw Wrapped Text in a Rectangle</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-wrapped-text-in-a-rectangle.md)
