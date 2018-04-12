---
title: '연산자 선언 중 하나 여야 합니다: +,-, *,-,-, ^, &amp;, 같은, Mod, 및, Or, Xor, Not, &lt; &lt;, &gt; &gt;, =, &lt; &gt;, &lt;, &lt;=, &gt; &gt;=, CType, IsTrue, IsFalse'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc33000
- vbc33000
helpviewer_keywords:
- BC33000
ms.assetid: 15c5d8eb-3a8c-4141-8f41-33151afabf97
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 80c8358dd13105c18e73e94735a51b02d5bd22c5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="operator-declaration-must-be-one-of----amp-like-mod-and-or-xor-not-ltlt-gtgt"></a><span data-ttu-id="a65f6-102">연산자 선언 중 하나 여야 합니다: +,-, \*,\,/, ^, &amp;, 같은, Mod, 및, Or, Xor, Not, &lt; &lt;, &gt; &gt;...</span><span class="sxs-lookup"><span data-stu-id="a65f6-102">Operator declaration must be one of:  +,-,\*,\,/,^, &amp;, Like, Mod, And, Or, Xor, Not, &lt;&lt;, &gt;&gt;...</span></span>
<span data-ttu-id="a65f6-103">오버 로드할 수 있는 연산자만 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a65f6-103">You can declare only an operator that is eligible for overloading.</span></span> <span data-ttu-id="a65f6-104">다음 표에서 연산자를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a65f6-104">The following table lists the operators you can declare.</span></span>  
  
|<span data-ttu-id="a65f6-105">형식</span><span class="sxs-lookup"><span data-stu-id="a65f6-105">Type</span></span>|<span data-ttu-id="a65f6-106">연산자</span><span class="sxs-lookup"><span data-stu-id="a65f6-106">Operators</span></span>|  
|----------|---------------|  
|<span data-ttu-id="a65f6-107">단항</span><span class="sxs-lookup"><span data-stu-id="a65f6-107">Unary</span></span>|<span data-ttu-id="a65f6-108">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span><span class="sxs-lookup"><span data-stu-id="a65f6-108">`+`, `-`, `IsFalse`, `IsTrue`, `Not`</span></span>|  
|<span data-ttu-id="a65f6-109">이항</span><span class="sxs-lookup"><span data-stu-id="a65f6-109">Binary</span></span>|<span data-ttu-id="a65f6-110">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span><span class="sxs-lookup"><span data-stu-id="a65f6-110">`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`</span></span>|  
|<span data-ttu-id="a65f6-111">변환(단항)</span><span class="sxs-lookup"><span data-stu-id="a65f6-111">Conversion (unary)</span></span>|`CType`|  
  
 <span data-ttu-id="a65f6-112">`=` 이진 목록의 연산자는 비교 연산자, 대입 연산자가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a65f6-112">Note that the `=` operator in the binary list is the comparison operator, not the assignment operator.</span></span>  
  
 <span data-ttu-id="a65f6-113">**오류 ID:** BC33000</span><span class="sxs-lookup"><span data-stu-id="a65f6-113">**Error ID:** BC33000</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a65f6-114">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="a65f6-114">To correct this error</span></span>  
  
1.  <span data-ttu-id="a65f6-115">오버로드할 수 있는 연산자 집합에서 연산자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a65f6-115">Select an operator from the set of overloadable operators.</span></span>  
  
2.  <span data-ttu-id="a65f6-116">직접 오버로드할 수 없는 연산자 오버로드 기능이 필요할 경우 적절한 매개 변수를 사용하고 적절한 값을 반환하는 `Function` 프로시저를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a65f6-116">If you need the functionality of overloading an operator that you cannot overload directly, create a `Function` procedure that takes the appropriate parameters and returns the appropriate value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a65f6-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a65f6-117">See Also</span></span>  
 [<span data-ttu-id="a65f6-118">Operator 문</span><span class="sxs-lookup"><span data-stu-id="a65f6-118">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
 [<span data-ttu-id="a65f6-119">연산자 프로시저</span><span class="sxs-lookup"><span data-stu-id="a65f6-119">Operator Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)  
 [<span data-ttu-id="a65f6-120">방법: 연산자 정의</span><span class="sxs-lookup"><span data-stu-id="a65f6-120">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [<span data-ttu-id="a65f6-121">방법: 변환 연산자 정의</span><span class="sxs-lookup"><span data-stu-id="a65f6-121">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)  
 [<span data-ttu-id="a65f6-122">Function 문</span><span class="sxs-lookup"><span data-stu-id="a65f6-122">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
