---
title: "방법: 사용자 지정 파선 그리기"
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
- lines [Windows Forms], custom
- lines [Windows Forms], drawing
- lines [Windows Forms], dashed
ms.assetid: cd0ed96a-cce4-47b9-b58a-3bae2e3d1bee
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 90fcc99414e8d5c9542d643677c85d4ff670f50f
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-draw-a-custom-dashed-line"></a><span data-ttu-id="63ff4-102">방법: 사용자 지정 파선 그리기</span><span class="sxs-lookup"><span data-stu-id="63ff4-102">How to: Draw a Custom Dashed Line</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="63ff4-103">에 나열 된 몇 가지 대시 스타일을 제공 된 <xref:System.Drawing.Drawing2D.DashStyle> 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="63ff4-103"> provides several dash styles that are listed in the <xref:System.Drawing.Drawing2D.DashStyle> enumeration.</span></span> <span data-ttu-id="63ff4-104">해당 표준 대시 스타일 사용자 요구에 적합 하지 않는 경우 사용자 지정 대시 패턴을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63ff4-104">If those standard dash styles do not suit your needs, you can create a custom dash pattern.</span></span>  
  
## <a name="example"></a><span data-ttu-id="63ff4-105">예제</span><span class="sxs-lookup"><span data-stu-id="63ff4-105">Example</span></span>  
 <span data-ttu-id="63ff4-106">사용자 지정 파선 그리기, 대시와 공백의 길이 배열에 배치할 및의 값으로 배열을 할당는 <xref:System.Drawing.Pen.DashPattern%2A> 속성은 <xref:System.Drawing.Pen> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="63ff4-106">To draw a custom dashed line, put the lengths of the dashes and spaces in an array and assign the array as the value of the <xref:System.Drawing.Pen.DashPattern%2A> property of a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="63ff4-107">다음 예제에서는 배열을 기반으로 하는 사용자 지정 파선된 선을 그립니다 `{5, 2, 15, 4}`합니다.</span><span class="sxs-lookup"><span data-stu-id="63ff4-107">The following example draws a custom dashed line based on the array `{5, 2, 15, 4}`.</span></span> <span data-ttu-id="63ff4-108">배열 요소의 5의 펜 너비를 곱하면 경우 얻게 `{25, 10, 75, 20}`합니다.</span><span class="sxs-lookup"><span data-stu-id="63ff4-108">If you multiply the elements of the array by the pen width of 5, you get `{25, 10, 75, 20}`.</span></span> <span data-ttu-id="63ff4-109">표시 된 대시 25와 75, 사이의 길이가 대체 하 고 길이가 10과 20 사이의 공간을 교대로 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="63ff4-109">The displayed dashes alternate in length between 25 and 75, and the spaces alternate in length between 10 and 20.</span></span>  
  
 <span data-ttu-id="63ff4-110">다음은 결과 파선입니다.</span><span class="sxs-lookup"><span data-stu-id="63ff4-110">The following illustration shows the resulting dashed line.</span></span> <span data-ttu-id="63ff4-111">마지막 대시 줄 끝 수 있도록 25 단위 미만 이어야 하는 참고 (405, 5).</span><span class="sxs-lookup"><span data-stu-id="63ff4-111">Note that the final dash has to be shorter than 25 units so that the line can end at (405, 5).</span></span>  
  
 <span data-ttu-id="63ff4-112">![펜](../../../../docs/framework/winforms/advanced/media/pens6.gif "pens6")</span><span class="sxs-lookup"><span data-stu-id="63ff4-112">![Pens](../../../../docs/framework/winforms/advanced/media/pens6.gif "pens6")</span></span>  
  
 [!code-csharp[System.Drawing.UsingAPen#51](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.UsingAPen#51](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="63ff4-113">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="63ff4-113">Compiling the Code</span></span>  
 <span data-ttu-id="63ff4-114">Windows Form 만들기 및 폼의 처리 <xref:System.Windows.Forms.Control.Paint> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="63ff4-114">Create a Windows Form and handle the form's <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="63ff4-115">앞의 코드에 붙여는 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="63ff4-115">Paste the preceding code into the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63ff4-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="63ff4-116">See Also</span></span>  
 [<span data-ttu-id="63ff4-117">펜을 사용하여 선과 도형 그리기</span><span class="sxs-lookup"><span data-stu-id="63ff4-117">Using a Pen to Draw Lines and Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
