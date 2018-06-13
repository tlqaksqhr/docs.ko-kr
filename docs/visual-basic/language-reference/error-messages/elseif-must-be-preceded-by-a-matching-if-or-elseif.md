---
title: '&#39;#ElseIf&#39; 짝이 되는 뒤에 야 &#39;#If&#39; 또는 &#39;#ElseIf&#39;'
ms.date: 07/20/2015
f1_keywords:
- vbc30014
- bc30014
helpviewer_keywords:
- BC30014
ms.assetid: 5215585e-2efa-485a-9efe-9833a1cc83a0
ms.openlocfilehash: ef904173b1791309f6c2722bd959cabdad1d71da
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588150"
---
# <a name="39elseif39-must-be-preceded-by-a-matching-39if39-or-39elseif39"></a><span data-ttu-id="7a688-102">&#39;#ElseIf&#39; 짝이 되는 뒤에 야 &#39;#If&#39; 또는 &#39;#ElseIf&#39;</span><span class="sxs-lookup"><span data-stu-id="7a688-102">&#39;#ElseIf&#39; must be preceded by a matching &#39;#If&#39; or &#39;#ElseIf&#39;</span></span>
<span data-ttu-id="7a688-103">`#ElseIf`는 조건부 컴파일 지시문입니다.</span><span class="sxs-lookup"><span data-stu-id="7a688-103">`#ElseIf` is a conditional compilation directive.</span></span> <span data-ttu-id="7a688-104">`#ElseIf` 는 일치 하는 절 뒤에 야 `#If` 또는 `#ElseIf` 절.</span><span class="sxs-lookup"><span data-stu-id="7a688-104">An `#ElseIf` clause must be preceded by a matching `#If` or `#ElseIf` clause.</span></span>  
  
 <span data-ttu-id="7a688-105">**오류 ID:** BC30014</span><span class="sxs-lookup"><span data-stu-id="7a688-105">**Error ID:** BC30014</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7a688-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="7a688-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="7a688-107">있는지 여부를 확인 앞에 오는 `#If` 또는 `#ElseIf` 이에서 분리가 `#ElseIf` 간섭 조건부 컴파일 블록 또는 잘못 배치 하 여 `#End If`합니다.</span><span class="sxs-lookup"><span data-stu-id="7a688-107">Check that a preceding `#If` or `#ElseIf` has not been separated from this `#ElseIf` by an intervening conditional compilation block or an incorrectly placed `#End If`.</span></span>  
  
2.  <span data-ttu-id="7a688-108">경우는 `#ElseIf` 뒤에 옵니다는 `#Else` 지시문, 제거 하거나는 `#Else` 로 변경 된 `#ElseIf`합니다.</span><span class="sxs-lookup"><span data-stu-id="7a688-108">If the `#ElseIf` is preceded by a `#Else` directive, either remove the `#Else` or change it to an `#ElseIf`.</span></span>  
  
3.  <span data-ttu-id="7a688-109">다른 모든 항목의 순서가 올바른 경우 `#If` 지시문을 조건부 컴파일 블록의 시작 부분에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7a688-109">If everything else is in order, add an `#If` directive to the beginning of the conditional compilation block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a688-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7a688-110">See Also</span></span>  
 [<span data-ttu-id="7a688-111">#If...Then...#Else 지시문</span><span class="sxs-lookup"><span data-stu-id="7a688-111">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
