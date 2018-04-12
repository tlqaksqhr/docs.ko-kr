---
title: GoTo 문
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.GoTo
helpviewer_keywords:
- GoTo statement [Visual Basic]
- control flow [Visual Basic], branching
- unconditional branching [Visual Basic]
- branching [Visual Basic]
- branching [Visual Basic], unconditional
- branching [Visual Basic], conditional
- conditional statements [Visual Basic], GoTo statement
- GoTo statement [Visual Basic], syntax
ms.assetid: 313274c2-8ab3-4b9c-9ba3-0fd6798e4f6d
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 22a6315e69cd6c797d462d0835e85bb1dde67dcc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="goto-statement"></a><span data-ttu-id="d7f0c-102">GoTo 문</span><span class="sxs-lookup"><span data-stu-id="d7f0c-102">GoTo Statement</span></span>
<span data-ttu-id="d7f0c-103">프로시저에 지정된 된 줄으로 무조건 분기 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7f0c-103">Branches unconditionally to a specified line in a procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7f0c-104">구문</span><span class="sxs-lookup"><span data-stu-id="d7f0c-104">Syntax</span></span>  
  
```  
GoTo line  
```  
  
## <a name="part"></a><span data-ttu-id="d7f0c-105">파트</span><span class="sxs-lookup"><span data-stu-id="d7f0c-105">Part</span></span>  
 `line`  
 <span data-ttu-id="d7f0c-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="d7f0c-106">Required.</span></span> <span data-ttu-id="d7f0c-107">모든 줄 레이블을 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7f0c-107">Any line label.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d7f0c-108">설명</span><span class="sxs-lookup"><span data-stu-id="d7f0c-108">Remarks</span></span>  
 <span data-ttu-id="d7f0c-109">`GoTo` 문은 나타나는 프로시저의 줄에만 분기할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7f0c-109">The `GoTo` statement can branch only to lines in the procedure in which it appears.</span></span> <span data-ttu-id="d7f0c-110">줄에 있는 줄 레이블이 있어야 `GoTo` 를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7f0c-110">The line must have a line label that `GoTo` can refer to.</span></span> <span data-ttu-id="d7f0c-111">자세한 내용은 참조 [하는 방법: Label 문](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d7f0c-111">For more information, see [How to: Label Statements](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d7f0c-112">`GoTo`문은 코드를 읽고 관리 하기 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7f0c-112">`GoTo` statements can make code difficult to read and maintain.</span></span> <span data-ttu-id="d7f0c-113">가능 하면 제어 구조를 대신 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7f0c-113">Whenever possible, use a control structure instead.</span></span> <span data-ttu-id="d7f0c-114">자세한 내용은 참조 [제어 흐름](../../../visual-basic/programming-guide/language-features/control-flow/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d7f0c-114">For more information, see [Control Flow](../../../visual-basic/programming-guide/language-features/control-flow/index.md).</span></span>  
  
 <span data-ttu-id="d7f0c-115">사용할 수 없습니다는 `GoTo` 문 외부에서 분기에는 `For`... `Next`, `For Each`... `Next`, `SyncLock`... `End SyncLock`, `Try`... `Catch`... `Finally`, `With`... `End With`, 또는 `Using`... `End Using` 내부의 레이블로 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7f0c-115">You cannot use a `GoTo` statement to branch from outside a `For`...`Next`, `For Each`...`Next`, `SyncLock`...`End SyncLock`, `Try`...`Catch`...`Finally`, `With`...`End With`, or `Using`...`End Using` construction to a label inside.</span></span>  
  
## <a name="branching-and-try-constructions"></a><span data-ttu-id="d7f0c-116">분기 및 생성을 시도 하십시오</span><span class="sxs-lookup"><span data-stu-id="d7f0c-116">Branching and Try Constructions</span></span>  
 <span data-ttu-id="d7f0c-117">내에서 한 `Try`... `Catch`... `Finally` 생성, 다음과 같은 규칙이 적용 된 분기는 `GoTo` 문.</span><span class="sxs-lookup"><span data-stu-id="d7f0c-117">Within a `Try`...`Catch`...`Finally` construction, the following rules apply to branching with the `GoTo` statement.</span></span>  
  
|<span data-ttu-id="d7f0c-118">블록 또는 지역</span><span class="sxs-lookup"><span data-stu-id="d7f0c-118">Block or region</span></span>|<span data-ttu-id="d7f0c-119">외부에서 분기</span><span class="sxs-lookup"><span data-stu-id="d7f0c-119">Branching in from outside</span></span>|<span data-ttu-id="d7f0c-120">내부에서 외부로 분기</span><span class="sxs-lookup"><span data-stu-id="d7f0c-120">Branching out from inside</span></span>|  
|---------------------|-------------------------------|-------------------------------|  
|<span data-ttu-id="d7f0c-121">`Try`블록</span><span class="sxs-lookup"><span data-stu-id="d7f0c-121">`Try` block</span></span>|<span data-ttu-id="d7f0c-122">에서만 `Catch` 동일한 생성의 블록 <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="d7f0c-122">Only from a `Catch` block of the same construction <sup>1</sup></span></span>|<span data-ttu-id="d7f0c-123">에 전체 구문의 외부</span><span class="sxs-lookup"><span data-stu-id="d7f0c-123">Only to outside the whole construction</span></span>|  
|<span data-ttu-id="d7f0c-124">`Catch`블록</span><span class="sxs-lookup"><span data-stu-id="d7f0c-124">`Catch` block</span></span>|<span data-ttu-id="d7f0c-125">사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d7f0c-125">Never allowed</span></span>|<span data-ttu-id="d7f0c-126">에 전체 구문의 외부 또는 `Try` 동일한 생성의 블록 <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="d7f0c-126">Only to outside the whole construction, or to the `Try` block of the same construction <sup>1</sup></span></span>|  
|<span data-ttu-id="d7f0c-127">`Finally`블록</span><span class="sxs-lookup"><span data-stu-id="d7f0c-127">`Finally` block</span></span>|<span data-ttu-id="d7f0c-128">사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d7f0c-128">Never allowed</span></span>|<span data-ttu-id="d7f0c-129">사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d7f0c-129">Never allowed</span></span>|  
  
 <span data-ttu-id="d7f0c-130"><sup>1</sup> 경우 `Try`... `Catch`... `Finally` 생성 다른 안으로 중첩 됩니다는 `Catch` 블록으로 분기할 수는 `Try` 자체 중첩 수준에 포함 되지 않습니다 다른 블록 `Try` 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="d7f0c-130"><sup>1</sup> If one `Try`...`Catch`...`Finally` construction is nested within another, a `Catch` block can branch into the `Try` block at its own nesting level, but not into any other `Try` block.</span></span> <span data-ttu-id="d7f0c-131">중첩 된 `Try`... `Catch`... `Finally` 생성에 완전히 포함 되어야 합니다는 `Try` 또는 `Catch` 블록의 중첩 된 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7f0c-131">A nested `Try`...`Catch`...`Finally` construction must be contained completely in a `Try` or `Catch` block of the construction within which it is nested.</span></span>  
  
 <span data-ttu-id="d7f0c-132">다음 그림에 나와 하나 `Try` 다른 내에 중첩 된 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7f0c-132">The following illustration shows one `Try` construction nested within another.</span></span> <span data-ttu-id="d7f0c-133">두 구문의 블록 간에 다양 한 분기 유효한 지 여부로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7f0c-133">Various branches among the blocks of the two constructions are indicated as valid or invalid.</span></span>  
  
 <span data-ttu-id="d7f0c-134">![Try 생성에서 분기의 그래픽 다이어그램](../../../visual-basic/language-reference/statements/media/trybranching.gif "TryBranching")</span><span class="sxs-lookup"><span data-stu-id="d7f0c-134">![Graphic diagram of branching in Try constructions](../../../visual-basic/language-reference/statements/media/trybranching.gif "TryBranching")</span></span>  
<span data-ttu-id="d7f0c-135">Try 생성에서 유효 하지 않은 분기</span><span class="sxs-lookup"><span data-stu-id="d7f0c-135">Valid and invalid branches in Try constructions</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7f0c-136">예제</span><span class="sxs-lookup"><span data-stu-id="d7f0c-136">Example</span></span>  
 <span data-ttu-id="d7f0c-137">다음 예제에서는 `GoTo` 문을 프로시저의 줄 레이블로 분기 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7f0c-137">The following example uses the `GoTo` statement to branch to line labels in a procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#31](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/goto-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="d7f0c-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d7f0c-138">See Also</span></span>  
 [<span data-ttu-id="d7f0c-139">Do...Loop 문</span><span class="sxs-lookup"><span data-stu-id="d7f0c-139">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)  
 [<span data-ttu-id="d7f0c-140">For...Next 문</span><span class="sxs-lookup"><span data-stu-id="d7f0c-140">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [<span data-ttu-id="d7f0c-141">For Each...Next 문</span><span class="sxs-lookup"><span data-stu-id="d7f0c-141">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)  
 [<span data-ttu-id="d7f0c-142">If...Then...Else 문</span><span class="sxs-lookup"><span data-stu-id="d7f0c-142">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)  
 [<span data-ttu-id="d7f0c-143">Select...Case 문</span><span class="sxs-lookup"><span data-stu-id="d7f0c-143">Select...Case Statement</span></span>](../../../visual-basic/language-reference/statements/select-case-statement.md)  
 [<span data-ttu-id="d7f0c-144">Try...Catch...Finally 문</span><span class="sxs-lookup"><span data-stu-id="d7f0c-144">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [<span data-ttu-id="d7f0c-145">While...End While 문</span><span class="sxs-lookup"><span data-stu-id="d7f0c-145">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)  
 [<span data-ttu-id="d7f0c-146">With...End With 문</span><span class="sxs-lookup"><span data-stu-id="d7f0c-146">With...End With Statement</span></span>](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
