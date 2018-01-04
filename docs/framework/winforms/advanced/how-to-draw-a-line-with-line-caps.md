---
title: "방법: 선 끝이 있는 선 그리기"
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
- drawing [Windows Forms], lines
- lines [Windows Forms], drawing
- pens [Windows Forms], drawing lines
- drawing lines [Windows Forms], line caps
ms.assetid: eb68c3e1-c400-4886-8a04-76978a429cb6
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4048757e11724aa1e175d8b18c47f48d22d807e4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-draw-a-line-with-line-caps"></a><span data-ttu-id="7c5ea-102">방법: 선 끝이 있는 선 그리기</span><span class="sxs-lookup"><span data-stu-id="7c5ea-102">How to: Draw a Line with Line Caps</span></span>
<span data-ttu-id="7c5ea-103">선 끝을 호출 하는 여러 셰이프 중 하나에 시작 또는 끝 줄을 그릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c5ea-103">You can draw the start or end of a line in one of several shapes called line caps.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="7c5ea-104">화살촉이 라운드, 사각형, 다이아몬드 등 여러 선 끝을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="7c5ea-104"> supports several line caps, such as round, square, diamond, and arrowhead.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7c5ea-105">예</span><span class="sxs-lookup"><span data-stu-id="7c5ea-105">Example</span></span>  
 <span data-ttu-id="7c5ea-106">선 끝 줄 (시작 cap), (end cap) 줄의 끝 또는 대시 (대시 cap) 파선의 시작에 대 한를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c5ea-106">You can specify line caps for the start of a line (start cap), the end of a line (end cap), or the dashes of a dashed line (dash cap).</span></span>  
  
 <span data-ttu-id="7c5ea-107">다음 예제에서는 다른 쪽 끝에서 둥근 단면 화살촉이 한쪽 끝에 선을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="7c5ea-107">The following example draws a line with an arrowhead at one end and a round cap at the other end.</span></span> <span data-ttu-id="7c5ea-108">그림에는 결과 선을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7c5ea-108">The illustration shows the resulting line:</span></span>  
  
 <span data-ttu-id="7c5ea-109">![펜](../../../../docs/framework/winforms/advanced/media/pens4.gif "pens4")</span><span class="sxs-lookup"><span data-stu-id="7c5ea-109">![Pens](../../../../docs/framework/winforms/advanced/media/pens4.gif "pens4")</span></span>  
  
 [!code-csharp[System.Drawing.UsingAPen#71](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.UsingAPen#71](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7c5ea-110">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="7c5ea-110">Compiling the Code</span></span>  
  
-   <span data-ttu-id="7c5ea-111">Windows Form 만들기 및 폼의 처리 <xref:System.Windows.Forms.Control.Paint> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="7c5ea-111">Create a Windows Form and handle the form's <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="7c5ea-112">예제 코드를 붙여는 <xref:System.Windows.Forms.Control.Paint> 전달 하는 이벤트 처리기 `e` 으로 <xref:System.Windows.Forms.PaintEventArgs>합니다.</span><span class="sxs-lookup"><span data-stu-id="7c5ea-112">Paste the example code into the <xref:System.Windows.Forms.Control.Paint> event handler passing `e` as <xref:System.Windows.Forms.PaintEventArgs>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c5ea-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7c5ea-113">See Also</span></span>  
 <xref:System.Drawing.Pen?displayProperty=nameWithType>  
 <xref:System.Drawing.Drawing2D.LineCap?displayProperty=nameWithType>  
 [<span data-ttu-id="7c5ea-114">Windows Forms의 그래픽 및 그리기</span><span class="sxs-lookup"><span data-stu-id="7c5ea-114">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="7c5ea-115">펜을 사용하여 선과 도형 그리기</span><span class="sxs-lookup"><span data-stu-id="7c5ea-115">Using a Pen to Draw Lines and Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
