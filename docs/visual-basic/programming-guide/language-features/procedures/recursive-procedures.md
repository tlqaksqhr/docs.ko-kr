---
title: "재귀 프로시저(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], that call themselves
- procedures [Visual Basic], recursive
- procedures [Visual Basic], calling
- recursive procedures
- functions [Visual Basic], calling recursively
- recursion
ms.assetid: ba1d3962-b4c3-48d3-875e-96fdb4198327
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 444eeaf043cf3710c5154fd7e8577590e3ce7d1e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="recursive-procedures-visual-basic"></a><span data-ttu-id="ad2c4-102">재귀 프로시저(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ad2c4-102">Recursive Procedures (Visual Basic)</span></span>
<span data-ttu-id="ad2c4-103">A *재귀* 절차는 자신을 호출 하는 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="ad2c4-103">A *recursive* procedure is one that calls itself.</span></span> <span data-ttu-id="ad2c4-104">일반적으로 이것이 작성 하는 가장 효과적인 방법 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="ad2c4-104">In general, this is not the most effective way to write [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] code.</span></span>  
  
 <span data-ttu-id="ad2c4-105">다음 절차 재귀를 사용 하 여 원래 인수의 계승값을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad2c4-105">The following procedure uses recursion to calculate the factorial of its original argument.</span></span>  
  
 [!code-vb[VbVbcnProcedures#51](./codesnippet/VisualBasic/recursive-procedures_1.vb)]  
  
## <a name="considerations-with-recursive-procedures"></a><span data-ttu-id="ad2c4-106">재귀 프로시저에 대 한 고려 사항</span><span class="sxs-lookup"><span data-stu-id="ad2c4-106">Considerations with Recursive Procedures</span></span>  
 <span data-ttu-id="ad2c4-107">**제한 조건**합니다.</span><span class="sxs-lookup"><span data-stu-id="ad2c4-107">**Limiting Conditions**.</span></span> <span data-ttu-id="ad2c4-108">재귀를 종료할 수 있는 하나 이상의 조건에 대해 테스트 하는 재귀 프로시저를 디자인 해야 하 고 재귀적 호출 수를 적절 한 내 없는 이러한 조건이 충족 되는 위치 하는 경우도 처리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad2c4-108">You must design a recursive procedure to test for at least one condition that can terminate the recursion, and you must also handle the case where no such condition is satisfied within a reasonable number of recursive calls.</span></span> <span data-ttu-id="ad2c4-109">오류 없이 충족 될 수 있는 하나 이상의 조건 없는 프로시저 무한 루프로 실행의 위험 수준이 높은 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad2c4-109">Without at least one condition that can be met without fail, your procedure runs a high risk of executing in an infinite loop.</span></span>  
  
 <span data-ttu-id="ad2c4-110">**메모리 사용량**.</span><span class="sxs-lookup"><span data-stu-id="ad2c4-110">**Memory Usage**.</span></span> <span data-ttu-id="ad2c4-111">응용 프로그램에 제한 된 양의 지역 변수에 대 한 공간.</span><span class="sxs-lookup"><span data-stu-id="ad2c4-111">Your application has a limited amount of space for local variables.</span></span> <span data-ttu-id="ad2c4-112">프로시저가 자신을 호출할 때마다 사용 된 공간 중 지역 변수가의 추가 복사본에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad2c4-112">Each time a procedure calls itself, it uses more of that space for additional copies of its local variables.</span></span> <span data-ttu-id="ad2c4-113">이 프로세스는 무기한 계속 됩니다, 결국 하면는 <xref:System.StackOverflowException> 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="ad2c4-113">If this process continues indefinitely, it eventually causes a <xref:System.StackOverflowException> error.</span></span>  
  
 <span data-ttu-id="ad2c4-114">**효율성**합니다.</span><span class="sxs-lookup"><span data-stu-id="ad2c4-114">**Efficiency**.</span></span> <span data-ttu-id="ad2c4-115">거의 항상 재귀에 대 한 루프를 대체할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad2c4-115">You can almost always substitute a loop for recursion.</span></span> <span data-ttu-id="ad2c4-116">루프에는 인수 전달 추가 저장소를 초기화 하 고 값을 반환 하는 오버 헤드가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ad2c4-116">A loop does not have the overhead of passing arguments, initializing additional storage, and returning values.</span></span> <span data-ttu-id="ad2c4-117">성능 재귀 호출 하지 않고 훨씬 향상 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad2c4-117">Your performance can be much better without recursive calls.</span></span>  
  
 <span data-ttu-id="ad2c4-118">**상호 재귀**합니다.</span><span class="sxs-lookup"><span data-stu-id="ad2c4-118">**Mutual Recursion**.</span></span> <span data-ttu-id="ad2c4-119">두 절차 서로 호출 하는 경우 성능이 매우 저하 또는 심지어 무한 루프를 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad2c4-119">You might observe very poor performance, or even an infinite loop, if two procedures call each other.</span></span> <span data-ttu-id="ad2c4-120">이러한 디자인 단일 재귀 절차와 동일한 문제가 되지만, 검색 하 고 디버그 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad2c4-120">Such a design presents the same problems as a single recursive procedure, but can be harder to detect and debug.</span></span>  
  
 <span data-ttu-id="ad2c4-121">**괄호를 사용한 호출**합니다.</span><span class="sxs-lookup"><span data-stu-id="ad2c4-121">**Calling with Parentheses**.</span></span> <span data-ttu-id="ad2c4-122">경우는 `Function` 프로시저가 자신을 호출 재귀적으로, 인수 목록이 없는 경우에 프로시저 이름 뒤에 괄호를 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad2c4-122">When a `Function` procedure calls itself recursively, you must follow the procedure name with parentheses, even if there is no argument list.</span></span> <span data-ttu-id="ad2c4-123">그렇지 않은 경우 함수 이름은 함수의 반환 값을 나타내는 것으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad2c4-123">Otherwise, the function name is taken as representing the return value of the function.</span></span>  
  
 <span data-ttu-id="ad2c4-124">**테스트**합니다.</span><span class="sxs-lookup"><span data-stu-id="ad2c4-124">**Testing**.</span></span> <span data-ttu-id="ad2c4-125">재귀 프로시저를 작성 하는 경우 항상 제한 일부 조건이 충족 되었는지 확인 하려면 매우 신중 하 게 테스트 해야 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad2c4-125">If you write a recursive procedure, you should test it very carefully to make sure it always meets some limiting condition.</span></span> <span data-ttu-id="ad2c4-126">또한 재귀 호출이 너무 많이 메모리에서 실행할 수 없음을 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad2c4-126">You should also ensure that you cannot run out of memory due to having too many recursive calls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad2c4-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ad2c4-127">See Also</span></span>  
 <xref:System.StackOverflowException>  
 [<span data-ttu-id="ad2c4-128">절차</span><span class="sxs-lookup"><span data-stu-id="ad2c4-128">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="ad2c4-129">Sub 프로시저</span><span class="sxs-lookup"><span data-stu-id="ad2c4-129">Sub Procedures</span></span>](./sub-procedures.md)  
 [<span data-ttu-id="ad2c4-130">Function 프로시저</span><span class="sxs-lookup"><span data-stu-id="ad2c4-130">Function Procedures</span></span>](./function-procedures.md)  
 [<span data-ttu-id="ad2c4-131">속성 프로시저</span><span class="sxs-lookup"><span data-stu-id="ad2c4-131">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="ad2c4-132">연산자 프로시저</span><span class="sxs-lookup"><span data-stu-id="ad2c4-132">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="ad2c4-133">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="ad2c4-133">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="ad2c4-134">프로시저 오버로딩</span><span class="sxs-lookup"><span data-stu-id="ad2c4-134">Procedure Overloading</span></span>](./procedure-overloading.md)  
 [<span data-ttu-id="ad2c4-135">프로시저 문제 해결</span><span class="sxs-lookup"><span data-stu-id="ad2c4-135">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)  
 [<span data-ttu-id="ad2c4-136">루프 구조</span><span class="sxs-lookup"><span data-stu-id="ad2c4-136">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [<span data-ttu-id="ad2c4-137">예외 문제 해결: System.StackOverflowException</span><span class="sxs-lookup"><span data-stu-id="ad2c4-137">Troubleshooting Exceptions: System.StackOverflowException</span></span>](http://msdn.microsoft.com/library/51b71217-c507-4f5b-bc35-0236180d7968)
