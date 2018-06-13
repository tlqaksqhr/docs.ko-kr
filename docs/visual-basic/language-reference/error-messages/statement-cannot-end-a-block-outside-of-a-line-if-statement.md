---
title: 문 줄 외부의 블록에서 끝날 수 없으며 &#39;경우&#39; 문
ms.date: 07/20/2015
f1_keywords:
- vbc32005
- bc32005
helpviewer_keywords:
- BC32005
ms.assetid: 4039f51b-e0ee-4789-a89b-45d06de06b5d
ms.openlocfilehash: af3006ddc35dfcaa52a54229881baa48cfb7809a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33596686"
---
# <a name="statement-cannot-end-a-block-outside-of-a-line-39if39-statement"></a><span data-ttu-id="a7f0c-102">문 줄 외부의 블록에서 끝날 수 없으며 &#39;경우&#39; 문</span><span class="sxs-lookup"><span data-stu-id="a7f0c-102">Statement cannot end a block outside of a line &#39;If&#39; statement</span></span>
<span data-ttu-id="a7f0c-103">한 줄 `If` 문 중 하나는 콜론 (:)으로 구분 된 여러 문을 포함 한 `End` 문을 한 줄의 외부 제어 블록에 대 한 `If`합니다.</span><span class="sxs-lookup"><span data-stu-id="a7f0c-103">A single-line `If` statement contains several statements separated by colons (:), one of which is an `End` statement for a control block outside the single-line `If`.</span></span> <span data-ttu-id="a7f0c-104">한 줄 `If` 문을 사용 하지 않는 `End If` 문.</span><span class="sxs-lookup"><span data-stu-id="a7f0c-104">Single-line `If` statements do not use the `End If` statement.</span></span>  
  
 <span data-ttu-id="a7f0c-105">**오류 ID:** BC32005</span><span class="sxs-lookup"><span data-stu-id="a7f0c-105">**Error ID:** BC32005</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a7f0c-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="a7f0c-106">To correct this error</span></span>  
  
-   <span data-ttu-id="a7f0c-107">단일 줄 이동 `If` 문을 포함 하는 제어 블록 밖의 `End If` 문.</span><span class="sxs-lookup"><span data-stu-id="a7f0c-107">Move the single-line `If` statement outside the control block that contains the `End If` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7f0c-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a7f0c-108">See Also</span></span>  
 [<span data-ttu-id="a7f0c-109">If...Then...Else 문</span><span class="sxs-lookup"><span data-stu-id="a7f0c-109">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
