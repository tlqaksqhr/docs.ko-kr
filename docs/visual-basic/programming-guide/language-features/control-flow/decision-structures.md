---
title: "즉, 의사 결정 구조 (Visual Basic) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- statements [Visual Basic], control flow
- If statement, decision structures
- If statement, If...Then...Else
- control flow, decision structures
- decision structures
- conditional statements, decision structures
ms.assetid: 2e2e0895-4483-442a-b17c-26aead751ec2
caps.latest.revision: 29
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
ms.openlocfilehash: dcbfb4bc3318d5f79870d04e606fab8bfa2dafb9
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="decision-structures-visual-basic"></a><span data-ttu-id="edb39-102">판단 구조(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="edb39-102">Decision Structures (Visual Basic)</span></span>
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="edb39-103">조건을 테스트 하 고 해당 테스트의 결과 따라 다른 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edb39-103"> lets you test conditions and perform different operations depending on the results of that test.</span></span> <span data-ttu-id="edb39-104">True 또는 false 이면 식의 다양 한 값 또는 일련의 문 실행할 때 생성 되는 다양 한 예외에 대 한 조건에 대해 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edb39-104">You can test for a condition being true or false, for various values of an expression, or for various exceptions generated when you execute a series of statements.</span></span>  
  
 <span data-ttu-id="edb39-105">다음 그림에는 조건이 true 인지 테스트 하 고 true 또는 false 인지에 따라 다른 작업을 수행 하는 의사 결정 구조를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="edb39-105">The following illustration shows a decision structure that tests for a condition being true and takes different actions depending on whether it is true or false.</span></span>  
  
 <span data-ttu-id="edb39-106">![If의 순서도... 다음 중... 다른 생성](../../../../visual-basic/programming-guide/language-features/control-flow/media/ifthenelse.gif "IfThenElse")</span><span class="sxs-lookup"><span data-stu-id="edb39-106">![Flow chart of an If...Then...Else construction](../../../../visual-basic/programming-guide/language-features/control-flow/media/ifthenelse.gif "IfThenElse")</span></span>  
<span data-ttu-id="edb39-107">조건이 true와 false 하는 경우 다른 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="edb39-107">Taking different actions when a condition is true and when it is false</span></span>  
  
## <a name="ifthenelse-construction"></a><span data-ttu-id="edb39-108">다음과 같은 경우... 다음 중... 다른 생성</span><span class="sxs-lookup"><span data-stu-id="edb39-108">If...Then...Else Construction</span></span>  
 <span data-ttu-id="edb39-109">`If...Then...Else`구문을 사용 하면 하나 이상의 조건을 테스트 하 고 각 조건에 따라 하나 이상의 문을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="edb39-109">`If...Then...Else` constructions let you test for one or more conditions and run one or more statements depending on each condition.</span></span> <span data-ttu-id="edb39-110">조건을 테스트 하 고 다음과 같은 방법으로 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edb39-110">You can test conditions and take actions in the following ways:</span></span>  
  
-   <span data-ttu-id="edb39-111">조건이 하나 이상의 문 실행`True`</span><span class="sxs-lookup"><span data-stu-id="edb39-111">Run one or more statements if a condition is `True`</span></span>  
  
-   <span data-ttu-id="edb39-112">조건이 하나 이상의 문 실행`False`</span><span class="sxs-lookup"><span data-stu-id="edb39-112">Run one or more statements if a condition is `False`</span></span>  
  
-   <span data-ttu-id="edb39-113">조건이 일부 문을 실행 `True` 및 다른 경우`False`</span><span class="sxs-lookup"><span data-stu-id="edb39-113">Run some statements if a condition is `True` and others if it is `False`</span></span>  
  
-   <span data-ttu-id="edb39-114">이전 조건이 추가 조건을 테스트 합니다.`False`</span><span class="sxs-lookup"><span data-stu-id="edb39-114">Test an additional condition if a prior condition is `False`</span></span>  
  
 <span data-ttu-id="edb39-115">이러한 모든 가능성을 제공 하는 제어 구조는 [경우... 다음 중... Else 문](../../../../visual-basic/language-reference/statements/if-then-else-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="edb39-115">The control structure that offers all these possibilities is the [If...Then...Else Statement](../../../../visual-basic/language-reference/statements/if-then-else-statement.md).</span></span> <span data-ttu-id="edb39-116">하나의 테스트와 실행 하는 문이 있는 경우 단일 행 버전을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edb39-116">You can use a single-line version if you have just one test and one statement to run.</span></span> <span data-ttu-id="edb39-117">좀 더 복잡 한 조건 및 작업 집합이 있으면 여러 행 버전을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edb39-117">If you have a more complex set of conditions and actions, you can use the multiple-line version.</span></span>  
  
## <a name="selectcase-construction"></a><span data-ttu-id="edb39-118">선택... Case 구문</span><span class="sxs-lookup"><span data-stu-id="edb39-118">Select...Case Construction</span></span>  
 <span data-ttu-id="edb39-119">`Select...Case` 생성 식을 한 번 평가 하 고 여러 다른 가능한 값을 기반으로 하는 문을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edb39-119">The `Select...Case` construction lets you evaluate an expression one time and run different sets of statements based on different possible values.</span></span> <span data-ttu-id="edb39-120">자세한 내용은 참조 [선택... Case 문](../../../../visual-basic/language-reference/statements/select-case-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="edb39-120">For more information, see [Select...Case Statement](../../../../visual-basic/language-reference/statements/select-case-statement.md).</span></span>  
  
## <a name="trycatchfinally-construction"></a><span data-ttu-id="edb39-121">시도 중... Catch... 마지막으로 생성</span><span class="sxs-lookup"><span data-stu-id="edb39-121">Try...Catch...Finally Construction</span></span>  
 <span data-ttu-id="edb39-122">`Try...Catch...Finally`구문을 사용 하 여 문 중 하나는 예외가 발생 하는 경우 제어를 유지 하는 환경에서 문 집합을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edb39-122">`Try...Catch...Finally` constructions let you run a set of statements under an environment that retains control if any one of your statements causes an exception.</span></span> <span data-ttu-id="edb39-123">다른 예외에 대 한 다양 한 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="edb39-123">You can take different actions for different exceptions.</span></span> <span data-ttu-id="edb39-124">전체를 종료 하기 전에 실행 되는 코드 블록을 선택적으로 지정할 수 `Try...Catch...Finally` 어떤 일이 발생 하는 것에 관계 없이 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="edb39-124">You can optionally specify a block of code that runs before you exit the whole `Try...Catch...Finally` construction, regardless of what occurs.</span></span> <span data-ttu-id="edb39-125">자세한 내용은 참조 [시도 중... Catch... Finally 문](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="edb39-125">For more information, see [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="edb39-126">대부분의 제어 구조에 대 한 키워드를 클릭할 때 모든 구조에 키워드가 강조 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="edb39-126">For many control structures, when you click a keyword, all of the keywords in the structure are highlighted.</span></span> <span data-ttu-id="edb39-127">예를 들어, 클릭 하면 `If` 에 `If...Then...Else` 생성, 모든 인스턴스의 `If`, `Then`, `ElseIf`, `Else`, 및 `End If` 생성에서의 강조 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="edb39-127">For instance, when you click `If` in an `If...Then...Else` construction, all instances of `If`, `Then`, `ElseIf`, `Else`, and `End If` in the construction are highlighted.</span></span> <span data-ttu-id="edb39-128">다음 또는 이전 강조 표시 된 키워드를 이동 하려면 CTRL + SHIFT + 아래쪽 화살표 또는 CTRL + SHIFT + 위쪽 화살표 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="edb39-128">To move to the next or previous highlighted keyword, press CTRL+SHIFT+DOWN ARROW or CTRL+SHIFT+UP ARROW.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edb39-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="edb39-129">See Also</span></span>  
 <span data-ttu-id="edb39-130">[제어 흐름](../../../../visual-basic/programming-guide/language-features/control-flow/index.md) </span><span class="sxs-lookup"><span data-stu-id="edb39-130">[Control Flow](../../../../visual-basic/programming-guide/language-features/control-flow/index.md) </span></span>  
<span data-ttu-id="edb39-131"> [루프 구조](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md) </span><span class="sxs-lookup"><span data-stu-id="edb39-131"> [Loop Structures](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md) </span></span>  
<span data-ttu-id="edb39-132"> [기타 제어 구조](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md) </span><span class="sxs-lookup"><span data-stu-id="edb39-132"> [Other Control Structures](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md) </span></span>  
<span data-ttu-id="edb39-133"> [중첩된 제어 구조](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md) </span><span class="sxs-lookup"><span data-stu-id="edb39-133"> [Nested Control Structures](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md) </span></span>  
<span data-ttu-id="edb39-134"> [If 연산자](../../../../visual-basic/language-reference/operators/if-operator.md)</span><span class="sxs-lookup"><span data-stu-id="edb39-134"> [If Operator](../../../../visual-basic/language-reference/operators/if-operator.md)</span></span>
