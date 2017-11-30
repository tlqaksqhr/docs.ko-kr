---
title: "인수 &#39; NPer &#39; 0 보다 커야 합니다."
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrRate_NPerMustBeGTZero
ms.assetid: d49242df-dbd1-4b26-bd8c-ed56d24fdfcd
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fa19f1842bcfa82908fe79f6fda69bbc5dd9499c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="argument-39nper39-must-be-greater-than-zero"></a><span data-ttu-id="4b2f7-102">인수 &#39; NPer &#39; 0 보다 커야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b2f7-102">Argument &#39;NPer&#39; must be greater than zero</span></span>
<span data-ttu-id="4b2f7-103">일정 기간의 고정 지불액과 고정 이자율을 기준으로 연금의 기간 수를 지정하는 `NPer` 을 반환하는 `Double` 함수에는 0보다 큰 인수가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4b2f7-103">The `NPer` function, which returns a `Double` specifying the number of periods for an annuity based on periodic fixed payments and a fixed interest rate, requires an argument greater than zero.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4b2f7-104">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="4b2f7-104">To correct this error</span></span>  
  
-   <span data-ttu-id="4b2f7-105">식에서 인수의 철자를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="4b2f7-105">Check the spelling of arguments in the expression.</span></span> <span data-ttu-id="4b2f7-106">철자가 잘못된 변수 이름은 0으로 초기화되는 숫자 변수를 암시적으로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b2f7-106">A misspelled variable name can implicitly create a numeric variable that is initialized to zero.</span></span>  
  
-   <span data-ttu-id="4b2f7-107">이전 작업에서 식의 변수 특히, 다른 프로시저에서 해당 프로시저로 인수로 전달된 변수를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="4b2f7-107">Check previous operations on variables in the expression, especially those passed into the procedure as arguments from other procedures.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b2f7-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4b2f7-108">See Also</span></span>  
 [<span data-ttu-id="4b2f7-109">빌드에 없음: NPer 함수</span><span class="sxs-lookup"><span data-stu-id="4b2f7-109">NOT IN BUILD: NPer Function</span></span>](http://msdn.microsoft.com/en-us/56567d16-29f7-4928-b05f-b4cd56d4fd42)  
 [<span data-ttu-id="4b2f7-110">값 또는 참조로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="4b2f7-110">Passing Arguments by Value and by Reference</span></span>](../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
