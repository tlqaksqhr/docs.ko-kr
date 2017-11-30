---
title: "루프 구조(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- control flow [Visual Basic], loops
- For keyword [Visual Basic], loop structures
- loops
- loop structures [Visual Basic]
- statements [Visual Basic], loop
- Do statement [Visual Basic], Do loops
- conditional statements [Visual Basic], loop structures
ms.assetid: ecacb09b-a4c9-42be-98b2-a15d368b5db8
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2f813a555677e3828297c9c360b7a47217c39524
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="loop-structures-visual-basic"></a><span data-ttu-id="eee98-102">루프 구조(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eee98-102">Loop Structures (Visual Basic)</span></span>
[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="eee98-103">루프 구조를 사용 하면 하나 이상의 코드 줄을 반복 해 서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eee98-103"> loop structures allow you to run one or more lines of code repetitively.</span></span> <span data-ttu-id="eee98-104">조건이 될 때까지 루프 구조에서 문을 반복할 수 `True`조건이 될 때까지 `False`, 컬렉션에서 각 요소에 대해 한 번 횟수 또는 번호를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="eee98-104">You can repeat the statements in a loop structure until a condition is `True`, until a condition is `False`, a specified number of times, or once for each element in a collection.</span></span>  
  
 <span data-ttu-id="eee98-105">다음 그림에는 조건이 true가 될 때까지 문 집합을 실행 하는 루프 구조를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="eee98-105">The following illustration shows a loop structure that runs a set of statements until a condition becomes true.</span></span>  
  
 <span data-ttu-id="eee98-106">![순서도 Do... Until 루프](../../../../visual-basic/programming-guide/language-features/control-flow/media/dountilloop.gif "DoUntilLoop")</span><span class="sxs-lookup"><span data-stu-id="eee98-106">![Flow chart of a Do...Until loop](../../../../visual-basic/programming-guide/language-features/control-flow/media/dountilloop.gif "DoUntilLoop")</span></span>  
<span data-ttu-id="eee98-107">조건이 true가 될 때까지 문 집합을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="eee98-107">Running a set of statements until a condition becomes true</span></span>  
  
## <a name="while-loops"></a><span data-ttu-id="eee98-108">While 루프</span><span class="sxs-lookup"><span data-stu-id="eee98-108">While Loops</span></span>  
 <span data-ttu-id="eee98-109">`While`... `End While` 구문은에 지정 된 조건으로 여러 개의 문이 실행 된 `While` 문이 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="eee98-109">The `While`...`End While` construction runs a set of statements as long as the condition specified in the `While` statement is `True`.</span></span> <span data-ttu-id="eee98-110">자세한 내용은 참조 [동안... While 문 종료](../../../../visual-basic/language-reference/statements/while-end-while-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="eee98-110">For more information, see [While...End While Statement](../../../../visual-basic/language-reference/statements/while-end-while-statement.md).</span></span>  
  
## <a name="do-loops"></a><span data-ttu-id="eee98-111">Do 루프</span><span class="sxs-lookup"><span data-stu-id="eee98-111">Do Loops</span></span>  
 <span data-ttu-id="eee98-112">`Do`... `Loop` 구문을 시작 또는 끝에 루프 구조에서 조건을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eee98-112">The `Do`...`Loop` construction allows you to test a condition at either the beginning or the end of a loop structure.</span></span> <span data-ttu-id="eee98-113">조건이 동안 루프를 반복할지 여부를 지정할 수도 있습니다 `True` 될 때까지 또는 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="eee98-113">You can also specify whether to repeat the loop while the condition remains `True` or until it becomes `True`.</span></span> <span data-ttu-id="eee98-114">자세한 내용은 참조 [수행... 문은 루프](../../../../visual-basic/language-reference/statements/do-loop-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="eee98-114">For more information, see [Do...Loop Statement](../../../../visual-basic/language-reference/statements/do-loop-statement.md).</span></span>  
  
## <a name="for-loops"></a><span data-ttu-id="eee98-115">For 루프</span><span class="sxs-lookup"><span data-stu-id="eee98-115">For Loops</span></span>  
 <span data-ttu-id="eee98-116">`For`... `Next` 구문은 루프 횟수 만큼 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="eee98-116">The `For`...`Next` construction performs the loop a set number of times.</span></span> <span data-ttu-id="eee98-117">라고도 하는 루프 제어 변수를 사용 하 여 한 *카운터*, 반복을 추적 합니다.</span><span class="sxs-lookup"><span data-stu-id="eee98-117">It uses a loop control variable, also called a *counter*, to keep track of the repetitions.</span></span> <span data-ttu-id="eee98-118">시작 및 끝이 카운터에 대 한 값을 지정 하 고 필요에 따라 증가 하 한 반복에서 다음 크기를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eee98-118">You specify the starting and ending values for this counter, and you can optionally specify the amount by which it increases from one repetition to the next.</span></span> <span data-ttu-id="eee98-119">자세한 내용은 참조 [에 대 한... 다음 문](../../../../visual-basic/language-reference/statements/for-next-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="eee98-119">For more information, see [For...Next Statement](../../../../visual-basic/language-reference/statements/for-next-statement.md).</span></span>  
  
## <a name="for-each-loops"></a><span data-ttu-id="eee98-120">각 루프에 대 한</span><span class="sxs-lookup"><span data-stu-id="eee98-120">For Each Loops</span></span>  
 <span data-ttu-id="eee98-121">`For Each`... `Next` 구문은 컬렉션의 각 요소에 대해 한 번씩 문 집합을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="eee98-121">The `For Each`...`Next` construction runs a set of statements once for each element in a collection.</span></span> <span data-ttu-id="eee98-122">루프 제어 변수를 지정 하지만 시작 또는 끝 값을 확인할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eee98-122">You specify the loop control variable, but you do not have to determine starting or ending values for it.</span></span> <span data-ttu-id="eee98-123">자세한 내용은 참조 [각각에 대해... 다음 문](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="eee98-123">For more information, see [For Each...Next Statement](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eee98-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eee98-124">See Also</span></span>  
 [<span data-ttu-id="eee98-125">제어 흐름</span><span class="sxs-lookup"><span data-stu-id="eee98-125">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)  
 [<span data-ttu-id="eee98-126">판단 구조</span><span class="sxs-lookup"><span data-stu-id="eee98-126">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)  
 [<span data-ttu-id="eee98-127">기타 제어 구조</span><span class="sxs-lookup"><span data-stu-id="eee98-127">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)  
 [<span data-ttu-id="eee98-128">중첩 제어 구조</span><span class="sxs-lookup"><span data-stu-id="eee98-128">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
