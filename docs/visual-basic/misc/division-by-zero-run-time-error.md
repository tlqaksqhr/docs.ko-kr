---
title: "0으로 나누기(Visual Basic 런타임 오류)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID11
ms.assetid: 5b9bc5d6-792e-48bc-a974-012e07ad95f3
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9a913e3b55b38430c0908f77aac79cb342e78719
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="division-by-zero-visual-basic-run-time-error"></a><span data-ttu-id="02923-102">0으로 나누기(Visual Basic 런타임 오류)</span><span class="sxs-lookup"><span data-stu-id="02923-102">Division by zero (Visual Basic Run-Time Error)</span></span>
<span data-ttu-id="02923-103">제수로 사용할 식에 0 값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02923-103">An expression being used as a divisor has a value of zero.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="02923-104">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="02923-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="02923-105">식에서 변수의 철자를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="02923-105">Check the spelling of variables in the expression.</span></span> <span data-ttu-id="02923-106">철자가 잘못된 변수 이름은 0으로 초기화되는 숫자 변수를 암시적으로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02923-106">A misspelled variable name can implicitly create a numeric variable that is initialized to zero.</span></span>  
  
2.  <span data-ttu-id="02923-107">이전 작업에서 식의 변수 특히, 다른 프로시저에서 해당 프로시저로 인수로 전달된 변수를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="02923-107">Check previous operations on variables in the expression, especially those passed into the procedure as arguments from other procedures.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02923-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="02923-108">See Also</span></span>  
 [<span data-ttu-id="02923-109">값 또는 참조로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="02923-109">Passing Arguments by Value and by Reference</span></span>](../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="02923-110">매개 변수 Visual Basic의 메커니즘 변경 전달</span><span class="sxs-lookup"><span data-stu-id="02923-110">Parameter Passing Mechanism Changes in Visual Basic</span></span>](http://msdn.microsoft.com/en-us/0fa2b0dc-aa1c-4797-bbd6-aa13c611cab2)
