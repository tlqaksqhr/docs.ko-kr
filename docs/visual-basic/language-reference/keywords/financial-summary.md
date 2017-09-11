---
title: "회계 요약 (Visual Basic) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- financial functions
- payment
ms.assetid: 474f973e-7103-42b7-aa4d-367c935e07e1
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 47224a79942bd2b4adbe652f920be774e9f1c73d
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="financial-summary-visual-basic"></a><span data-ttu-id="d90fe-102">회계 요약(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d90fe-102">Financial Summary (Visual Basic)</span></span>
[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="d90fe-103">언어 키워드와 런타임 라이브러리 멤버 용도 따라 구성 됩니다 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d90fe-103"> language keywords and run-time library members are organized by purpose and use.</span></span>  
  
|<span data-ttu-id="d90fe-104">작업</span><span class="sxs-lookup"><span data-stu-id="d90fe-104">Action</span></span>|<span data-ttu-id="d90fe-105">언어 요소</span><span class="sxs-lookup"><span data-stu-id="d90fe-105">Language element</span></span>|  
|------------|----------------------|  
|<span data-ttu-id="d90fe-106">감가상각을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="d90fe-106">Calculate depreciation.</span></span>|<span data-ttu-id="d90fe-107"><xref:Microsoft.VisualBasic.Financial.DDB%2A>, <xref:Microsoft.VisualBasic.Financial.SLN%2A>, <xref:Microsoft.VisualBasic.Financial.SYD%2A></xref:Microsoft.VisualBasic.Financial.SYD%2A></xref:Microsoft.VisualBasic.Financial.SLN%2A></xref:Microsoft.VisualBasic.Financial.DDB%2A></span><span class="sxs-lookup"><span data-stu-id="d90fe-107"><xref:Microsoft.VisualBasic.Financial.DDB%2A>, <xref:Microsoft.VisualBasic.Financial.SLN%2A>, <xref:Microsoft.VisualBasic.Financial.SYD%2A></span></span>|  
|<span data-ttu-id="d90fe-108">미래 가치를 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="d90fe-108">Calculate future value.</span></span>|<span data-ttu-id="d90fe-109"><xref:Microsoft.VisualBasic.Financial.FV%2A></xref:Microsoft.VisualBasic.Financial.FV%2A></span><span class="sxs-lookup"><span data-stu-id="d90fe-109"><xref:Microsoft.VisualBasic.Financial.FV%2A></span></span>|  
|<span data-ttu-id="d90fe-110">이자율을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="d90fe-110">Calculate interest rate.</span></span>|<span data-ttu-id="d90fe-111"><xref:Microsoft.VisualBasic.Financial.Rate%2A></xref:Microsoft.VisualBasic.Financial.Rate%2A></span><span class="sxs-lookup"><span data-stu-id="d90fe-111"><xref:Microsoft.VisualBasic.Financial.Rate%2A></span></span>|  
|<span data-ttu-id="d90fe-112">내부 수익률을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="d90fe-112">Calculate internal rate of return.</span></span>|<span data-ttu-id="d90fe-113"><xref:Microsoft.VisualBasic.Financial.IRR%2A>,<xref:Microsoft.VisualBasic.Financial.MIRR%2A></xref:Microsoft.VisualBasic.Financial.MIRR%2A></xref:Microsoft.VisualBasic.Financial.IRR%2A></span><span class="sxs-lookup"><span data-stu-id="d90fe-113"><xref:Microsoft.VisualBasic.Financial.IRR%2A>, <xref:Microsoft.VisualBasic.Financial.MIRR%2A></span></span>|  
|<span data-ttu-id="d90fe-114">기간 수를 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="d90fe-114">Calculate number of periods.</span></span>|<span data-ttu-id="d90fe-115"><xref:Microsoft.VisualBasic.Financial.NPer%2A></xref:Microsoft.VisualBasic.Financial.NPer%2A></span><span class="sxs-lookup"><span data-stu-id="d90fe-115"><xref:Microsoft.VisualBasic.Financial.NPer%2A></span></span>|  
|<span data-ttu-id="d90fe-116">지불을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="d90fe-116">Calculate payments.</span></span>|<span data-ttu-id="d90fe-117"><xref:Microsoft.VisualBasic.Financial.IPmt%2A>, <xref:Microsoft.VisualBasic.Financial.Pmt%2A>, <xref:Microsoft.VisualBasic.Financial.PPmt%2A></xref:Microsoft.VisualBasic.Financial.PPmt%2A></xref:Microsoft.VisualBasic.Financial.Pmt%2A></xref:Microsoft.VisualBasic.Financial.IPmt%2A></span><span class="sxs-lookup"><span data-stu-id="d90fe-117"><xref:Microsoft.VisualBasic.Financial.IPmt%2A>, <xref:Microsoft.VisualBasic.Financial.Pmt%2A>, <xref:Microsoft.VisualBasic.Financial.PPmt%2A></span></span>|  
|<span data-ttu-id="d90fe-118">현재 가치를 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="d90fe-118">Calculate present value.</span></span>|<span data-ttu-id="d90fe-119"><xref:Microsoft.VisualBasic.Financial.NPV%2A>,<xref:Microsoft.VisualBasic.Financial.PV%2A></xref:Microsoft.VisualBasic.Financial.PV%2A></xref:Microsoft.VisualBasic.Financial.NPV%2A></span><span class="sxs-lookup"><span data-stu-id="d90fe-119"><xref:Microsoft.VisualBasic.Financial.NPV%2A>, <xref:Microsoft.VisualBasic.Financial.PV%2A></span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d90fe-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d90fe-120">See Also</span></span>  
 <span data-ttu-id="d90fe-121">[키워드](../../../visual-basic/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="d90fe-121">[Keywords](../../../visual-basic/language-reference/keywords/index.md) </span></span>  
<span data-ttu-id="d90fe-122"> [Visual Basic 런타임 라이브러리 멤버](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="d90fe-122"> [Visual Basic Runtime Library Members](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>
