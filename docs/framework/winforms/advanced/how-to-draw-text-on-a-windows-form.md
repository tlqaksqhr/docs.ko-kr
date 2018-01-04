---
title: "방법: Windows Form에 텍스트 그리기"
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
- cpp
helpviewer_keywords:
- forms [Windows Forms], drawing text
- text [Windows Forms], drawing
ms.assetid: 5d2447a9-21a1-4adc-b954-5516f2bb9b2c
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 03e663f455a348b2699331ec5bf1ea6df2e54493
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-draw-text-on-a-windows-form"></a><span data-ttu-id="73583-102">방법: Windows Form에 텍스트 그리기</span><span class="sxs-lookup"><span data-stu-id="73583-102">How to: Draw Text on a Windows Form</span></span>
<span data-ttu-id="73583-103">다음 코드 예제를 사용 하는 방법을 보여 줍니다는 <xref:System.Drawing.Graphics.DrawString%2A> 의 메서드는 <xref:System.Drawing.Graphics> 폼에 텍스트를 그리는 합니다.</span><span class="sxs-lookup"><span data-stu-id="73583-103">The following code example shows how to use the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> to draw text on a form.</span></span> <span data-ttu-id="73583-104">사용할 수 있습니다 <xref:System.Windows.Forms.TextRenderer> 폼에 텍스트를 그리기 위한 합니다.</span><span class="sxs-lookup"><span data-stu-id="73583-104">Alternatively, you can use <xref:System.Windows.Forms.TextRenderer> for drawing text on a form.</span></span> <span data-ttu-id="73583-105">자세한 내용은 참조 [하는 방법: GDI와 텍스트 그리기](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="73583-105">For more information, see [How to: Draw Text with GDI](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="73583-106">예</span><span class="sxs-lookup"><span data-stu-id="73583-106">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#7](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#7)]
 [!code-csharp[System.Drawing.ConceptualHowTos#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#7)]
 [!code-vb[System.Drawing.ConceptualHowTos#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#7)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="73583-107">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="73583-107">Compiling the Code</span></span>  
 <span data-ttu-id="73583-108">호출할 수 없습니다는 <xref:System.Drawing.Graphics.DrawString%2A> 에서 메서드는 <xref:System.Windows.Forms.Form.Load> 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="73583-108">You cannot call the <xref:System.Drawing.Graphics.DrawString%2A> method in the <xref:System.Windows.Forms.Form.Load> event handler.</span></span> <span data-ttu-id="73583-109">그려지는 콘텐츠 활성 및 비활성 폼 크기를 조정 하거나 다른 형식으로 가려진 경우.</span><span class="sxs-lookup"><span data-stu-id="73583-109">The drawn content will not be redrawn if the form is resized or obscured by another form.</span></span> <span data-ttu-id="73583-110">자동으로 다시 그려야 하 여 콘텐츠를 재정의 해야 하는 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="73583-110">To make your content automatically repaint, you should override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="73583-111">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="73583-111">Robust Programming</span></span>  
 <span data-ttu-id="73583-112">다음 조건에서 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="73583-112">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="73583-113">Arial 글꼴 설치 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="73583-113">The Arial font is not installed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73583-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="73583-114">See Also</span></span>  
 <xref:System.Drawing.Graphics.DrawString%2A>  
 <xref:System.Windows.Forms.TextRenderer.DrawText%2A>  
 <xref:System.Drawing.StringFormat.FormatFlags%2A>  
 <xref:System.Drawing.StringFormatFlags>  
 <xref:System.Windows.Forms.TextFormatFlags>  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 [<span data-ttu-id="73583-115">그래픽 프로그래밍 시작</span><span class="sxs-lookup"><span data-stu-id="73583-115">Getting Started with Graphics Programming</span></span>](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [<span data-ttu-id="73583-116">방법: GDI를 사용하여 텍스트 그리기</span><span class="sxs-lookup"><span data-stu-id="73583-116">How to: Draw Text with GDI</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)
