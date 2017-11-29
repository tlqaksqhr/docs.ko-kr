---
title: "판단 구조(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- statements [Visual Basic], control flow
- If statement [Visual Basic], decision structures
- If statement [Visual Basic], If...Then...Else
- control flow [Visual Basic], decision structures
- decision structures [Visual Basic]
- conditional statements [Visual Basic], decision structures
ms.assetid: 2e2e0895-4483-442a-b17c-26aead751ec2
caps.latest.revision: "29"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 38820b6ca0a8f716dcaa28644bb25eb4899bd511
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="decision-structures-visual-basic"></a><span data-ttu-id="ed989-102">판단 구조(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ed989-102">Decision Structures (Visual Basic)</span></span>
[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="ed989-103">조건을 테스트 하 고 해당 테스트의 결과 따라 다른 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed989-103"> lets you test conditions and perform different operations depending on the results of that test.</span></span> <span data-ttu-id="ed989-104">조건이 true 또는 false를 반환 하는 식의 다양 한 값에 대 한 또는 일련의 문 실행할 때 생성 되는 다양 한 예외에 대 한 인지 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed989-104">You can test for a condition being true or false, for various values of an expression, or for various exceptions generated when you execute a series of statements.</span></span>  
  
 <span data-ttu-id="ed989-105">다음 그림에는 조건이 true 인지 테스트 하 고 true 또는 false 인지에 따라 다른 작업을 수행 하는 의사 결정 구조를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ed989-105">The following illustration shows a decision structure that tests for a condition being true and takes different actions depending on whether it is true or false.</span></span>  
  
 <span data-ttu-id="ed989-106">![순서도 If... 다음 중... Else 생성](../../../../visual-basic/programming-guide/language-features/control-flow/media/ifthenelse.gif "IfThenElse")</span><span class="sxs-lookup"><span data-stu-id="ed989-106">![Flow chart of an If...Then...Else construction](../../../../visual-basic/programming-guide/language-features/control-flow/media/ifthenelse.gif "IfThenElse")</span></span>  
<span data-ttu-id="ed989-107">True 및 false 인 경우 조건이 일 때 다른 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed989-107">Taking different actions when a condition is true and when it is false</span></span>  
  
## <a name="ifthenelse-construction"></a><span data-ttu-id="ed989-108">다음과 같은 경우... 다음 중... Else 생성</span><span class="sxs-lookup"><span data-stu-id="ed989-108">If...Then...Else Construction</span></span>  
 <span data-ttu-id="ed989-109">`If...Then...Else`구문을 사용 하나 이상의 조건을 테스트 하 고 각 조건에 따라 하나 이상의 문을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed989-109">`If...Then...Else` constructions let you test for one or more conditions and run one or more statements depending on each condition.</span></span> <span data-ttu-id="ed989-110">조건을 테스트 하 고 다음과 같은 방법으로 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed989-110">You can test conditions and take actions in the following ways:</span></span>  
  
-   <span data-ttu-id="ed989-111">조건이 하나 이상의 문 실행`True`</span><span class="sxs-lookup"><span data-stu-id="ed989-111">Run one or more statements if a condition is `True`</span></span>  
  
-   <span data-ttu-id="ed989-112">조건이 하나 이상의 문 실행`False`</span><span class="sxs-lookup"><span data-stu-id="ed989-112">Run one or more statements if a condition is `False`</span></span>  
  
-   <span data-ttu-id="ed989-113">조건이 일부 문이 실행 `True` 와 다른 경우`False`</span><span class="sxs-lookup"><span data-stu-id="ed989-113">Run some statements if a condition is `True` and others if it is `False`</span></span>  
  
-   <span data-ttu-id="ed989-114">이전 조건이 경우 추가 조건을 테스트 합니다.`False`</span><span class="sxs-lookup"><span data-stu-id="ed989-114">Test an additional condition if a prior condition is `False`</span></span>  
  
 <span data-ttu-id="ed989-115">이러한 모든 가능성을 제공 하는 제어 구조는 [경우... 다음 중... Else 문](../../../../visual-basic/language-reference/statements/if-then-else-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ed989-115">The control structure that offers all these possibilities is the [If...Then...Else Statement](../../../../visual-basic/language-reference/statements/if-then-else-statement.md).</span></span> <span data-ttu-id="ed989-116">단일 테스트와 실행 문이 있는 경우 단일 행 버전을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed989-116">You can use a single-line version if you have just one test and one statement to run.</span></span> <span data-ttu-id="ed989-117">조건 및 동작의 더 복잡 한 집합을 사용 하는 경우에 여러 행 버전을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed989-117">If you have a more complex set of conditions and actions, you can use the multiple-line version.</span></span>  
  
## <a name="selectcase-construction"></a><span data-ttu-id="ed989-118">선택... Case 구문</span><span class="sxs-lookup"><span data-stu-id="ed989-118">Select...Case Construction</span></span>  
 <span data-ttu-id="ed989-119">`Select...Case` 생성 식을 한 번 평가 하 고 여러 다른 가능한 값을 기반으로 하는 문을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed989-119">The `Select...Case` construction lets you evaluate an expression one time and run different sets of statements based on different possible values.</span></span> <span data-ttu-id="ed989-120">자세한 내용은 참조 [선택... Case 문](../../../../visual-basic/language-reference/statements/select-case-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ed989-120">For more information, see [Select...Case Statement](../../../../visual-basic/language-reference/statements/select-case-statement.md).</span></span>  
  
## <a name="trycatchfinally-construction"></a><span data-ttu-id="ed989-121">시도 중... Catch 하는 중... 마지막으로 생성</span><span class="sxs-lookup"><span data-stu-id="ed989-121">Try...Catch...Finally Construction</span></span>  
 <span data-ttu-id="ed989-122">`Try...Catch...Finally`구문을 사용 여러 문 중 하나라도 문의 하면 예외가 발생 하는 경우 제어를 유지 하는 환경에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed989-122">`Try...Catch...Finally` constructions let you run a set of statements under an environment that retains control if any one of your statements causes an exception.</span></span> <span data-ttu-id="ed989-123">서로 다른 예외에 대 한 다른 동작을 취할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed989-123">You can take different actions for different exceptions.</span></span> <span data-ttu-id="ed989-124">필요에 따라 전체를 종료 하기 전에 실행 되는 코드 블록을 지정할 수 있습니다 `Try...Catch...Finally` 수행 되는 동작에 관계 없이 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed989-124">You can optionally specify a block of code that runs before you exit the whole `Try...Catch...Finally` construction, regardless of what occurs.</span></span> <span data-ttu-id="ed989-125">자세한 내용은 [Try...Catch...Finally 문](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ed989-125">For more information, see [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ed989-126">대부분의 제어 구조에 대 한 키워드를 클릭할 때 모든 키워드 구조에서 강조 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed989-126">For many control structures, when you click a keyword, all of the keywords in the structure are highlighted.</span></span> <span data-ttu-id="ed989-127">예를 들어, 클릭 하면 `If` 에 `If...Then...Else` 생성, 함수의 모든 인스턴스의 `If`, `Then`, `ElseIf`, `Else`, 및 `End If` 생성에서의 강조 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed989-127">For instance, when you click `If` in an `If...Then...Else` construction, all instances of `If`, `Then`, `ElseIf`, `Else`, and `End If` in the construction are highlighted.</span></span> <span data-ttu-id="ed989-128">다음 또는 이전 강조 표시 된 키워드를 이동 하려면 CTRL + SHIFT + 아래쪽 화살표 또는 CTRL + SHIFT + 위쪽 화살표 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="ed989-128">To move to the next or previous highlighted keyword, press CTRL+SHIFT+DOWN ARROW or CTRL+SHIFT+UP ARROW.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed989-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ed989-129">See Also</span></span>  
 [<span data-ttu-id="ed989-130">제어 흐름</span><span class="sxs-lookup"><span data-stu-id="ed989-130">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)  
 [<span data-ttu-id="ed989-131">루프 구조</span><span class="sxs-lookup"><span data-stu-id="ed989-131">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [<span data-ttu-id="ed989-132">기타 제어 구조</span><span class="sxs-lookup"><span data-stu-id="ed989-132">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)  
 [<span data-ttu-id="ed989-133">중첩 제어 구조</span><span class="sxs-lookup"><span data-stu-id="ed989-133">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [<span data-ttu-id="ed989-134">If 연산자</span><span class="sxs-lookup"><span data-stu-id="ed989-134">If Operator</span></span>](../../../../visual-basic/language-reference/operators/if-operator.md)
