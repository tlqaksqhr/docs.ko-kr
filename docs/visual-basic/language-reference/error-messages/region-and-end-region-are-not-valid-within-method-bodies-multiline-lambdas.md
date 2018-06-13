---
title: '&#39;#Region&#39; 및 &#39;#End 지역&#39; 문은 메서드 본문 여러 줄 람다 식 내에서 유효 하지 않습니다.'
ms.date: 07/20/2015
f1_keywords:
- bc32025
- vbc32025
helpviewer_keywords:
- BC32025
ms.assetid: 43707bf1-1c6b-4d82-b081-e5a17dca51c1
ms.openlocfilehash: bf3843e0ec3009f3dc7d60e91c340a7f20543231
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33593235"
---
# <a name="39region39-and-39end-region39-statements-are-not-valid-within-method-bodiesmultiline-lambdas"></a><span data-ttu-id="35449-102">&#39;#Region&#39; 및 &#39;#End 지역&#39; 문은 메서드 본문/여러 줄 람다 식 내에서 유효 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="35449-102">&#39;#Region&#39; and &#39;#End Region&#39; statements are not valid within method bodies/multiline lambdas</span></span>
<span data-ttu-id="35449-103">`#Region` 블록 클래스, 모듈 또는 네임 스페이스 수준에서 선언 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="35449-103">The `#Region` block must be declared at a class, module, or namespace level.</span></span> <span data-ttu-id="35449-104">축소 가능한 영역에는 하나 이상의 프로시저 포함할 수 있지만 시작 되거나 프로시저 내부에서 완료 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="35449-104">A collapsible region can include one or more procedures, but it cannot begin or end inside of a procedure.</span></span>  
  
 <span data-ttu-id="35449-105">**오류 ID:** BC32025</span><span class="sxs-lookup"><span data-stu-id="35449-105">**Error ID:** BC32025</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="35449-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="35449-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="35449-107">앞의 절차와 올바르게 종료 되었는지 확인 하십시오는 `End Function` 또는 `End Sub` 문.</span><span class="sxs-lookup"><span data-stu-id="35449-107">Ensure that the preceding procedure is properly terminated with an `End Function` or `End Sub` statement.</span></span>  
  
2.  <span data-ttu-id="35449-108">확인 하는 `#Region` 및 `#End Region` 지시문은 같은 코드 블록에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35449-108">Ensure that the `#Region` and `#End Region` directives are in the same code block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35449-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="35449-109">See Also</span></span>  
 [<span data-ttu-id="35449-110">#Region 지시문</span><span class="sxs-lookup"><span data-stu-id="35449-110">#Region Directive</span></span>](../../../visual-basic/language-reference/directives/region-directive.md)
