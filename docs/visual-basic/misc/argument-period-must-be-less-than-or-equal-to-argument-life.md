---
title: "인수 &#39; 기간 &#39; 인수 보다 작거나 &#39; 이어야 합니다. 수명 &#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrFinancial_PeriodLELife
ms.assetid: dc575d41-b376-4b05-bbbe-6de1e98385f1
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: be51edf01d39437032c24613165c5d86b6831a51
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="argument-39period39-must-be-less-than-or-equal-to-argument-39life39"></a><span data-ttu-id="e3c6d-102">인수 &#39; 기간 &#39; 인수 보다 작거나 &#39; 이어야 합니다. 수명 &#39;</span><span class="sxs-lookup"><span data-stu-id="e3c6d-102">Argument &#39;Period&#39; must be less than or equal to argument &#39;Life&#39;</span></span>
<span data-ttu-id="e3c6d-103">자산 감가상각이 계산되는 기간을 지정하는 `Period` 인수 값이 `Life` 인수 값보다 큽니다.</span><span class="sxs-lookup"><span data-stu-id="e3c6d-103">The value of the `Period` argument, which specifies the period for which asset depreciation is calculated, is greater than the value of the `Life` argument.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e3c6d-104">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="e3c6d-104">To correct this error</span></span>  
  
-   <span data-ttu-id="e3c6d-105">`Life` 와 `Period` 인수는 같은 단위로 표현되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3c6d-105">Ensure that the `Life` and `Period` arguments are expressed in the same units.</span></span> <span data-ttu-id="e3c6d-106">예를 들어 `Life` 가 월 단위로 측정되면 `Period` 도 월 단위로 측정되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3c6d-106">For example, if `Life` is measured in months, `Period` should be as well.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3c6d-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e3c6d-107">See Also</span></span>  
   
   
 [<span data-ttu-id="e3c6d-108">값 또는 참조로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="e3c6d-108">Passing Arguments by Value and by Reference</span></span>](../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
