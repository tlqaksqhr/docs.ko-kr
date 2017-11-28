---
title: "방법: Windows Form에 세로로 텍스트 그리기"
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
f1_keywords:
- StringFormat.FormatFlags
- Graphics.DrawString
helpviewer_keywords:
- text [Windows Forms], drawing vertical
- strings [Windows Forms], drawing vertical
- text [Windows Forms], drawing
- text [Windows Forms], vertical text
ms.assetid: 717a6131-00f6-4373-b574-9894e8317799
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 76da7be50f9e12454e16e08ec4db494585fae613
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-vertical-text-on-a-windows-form"></a><span data-ttu-id="96032-102">방법: Windows Form에 세로로 텍스트 그리기</span><span class="sxs-lookup"><span data-stu-id="96032-102">How to: Draw Vertical Text on a Windows Form</span></span>
<span data-ttu-id="96032-103">다음 코드 예제를 사용 하 여 폼에 세로 텍스트를 그리는 방법을 보여 줍니다.는 <xref:System.Drawing.Graphics.DrawString%2A> 방식의 <xref:System.Drawing.Graphics>합니다.</span><span class="sxs-lookup"><span data-stu-id="96032-103">The following code example shows how to draw vertical text on a form by using the <xref:System.Drawing.Graphics.DrawString%2A> method of <xref:System.Drawing.Graphics>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="96032-104">예제</span><span class="sxs-lookup"><span data-stu-id="96032-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#8](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#8)]
 [!code-csharp[System.Drawing.ConceptualHowTos#8](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#8)]
 [!code-vb[System.Drawing.ConceptualHowTos#8](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#8)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="96032-105">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="96032-105">Compiling the Code</span></span>  
 <span data-ttu-id="96032-106">이 메서드를 호출할 수 없습니다는 <xref:System.Windows.Forms.Form.Load> 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="96032-106">You cannot call this method in the <xref:System.Windows.Forms.Form.Load> event handler.</span></span> <span data-ttu-id="96032-107">그려지는 콘텐츠 활성 및 비활성 폼 크기를 조정 하거나 다른 형식으로 가려진 경우.</span><span class="sxs-lookup"><span data-stu-id="96032-107">The drawn content will not be redrawn if the form is resized or obscured by another form.</span></span> <span data-ttu-id="96032-108">자동으로 다시 그려야 하 여 콘텐츠를 재정의 해야 하는 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="96032-108">To make your content automatically repaint, you should override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="96032-109">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="96032-109">Robust Programming</span></span>  
 <span data-ttu-id="96032-110">다음 조건에서 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="96032-110">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="96032-111">Arial 글꼴 설치 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="96032-111">The Arial font is not installed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96032-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="96032-112">See Also</span></span>  
 <xref:System.Drawing.Graphics.DrawString%2A>  
 <xref:System.Drawing.StringFormat.FormatFlags%2A>  
 <xref:System.Drawing.StringFormatFlags>  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 [<span data-ttu-id="96032-113">그래픽 프로그래밍 시작</span><span class="sxs-lookup"><span data-stu-id="96032-113">Getting Started with Graphics Programming</span></span>](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [<span data-ttu-id="96032-114">글꼴 및 텍스트 사용</span><span class="sxs-lookup"><span data-stu-id="96032-114">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
