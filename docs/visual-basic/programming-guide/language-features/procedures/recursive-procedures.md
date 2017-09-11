---
title: "재귀 프로시저 (Visual Basic) | Microsoft 문서"
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
- Visual Basic code, procedures
- procedures, that call themselves
- procedures, recursive
- procedures, calling
- recursive procedures
- functions [Visual Basic], calling recursively
- recursion
ms.assetid: ba1d3962-b4c3-48d3-875e-96fdb4198327
caps.latest.revision: 13
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
ms.openlocfilehash: 5e4838bb14125dcfd27798acf0c196f351ba5b90
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="recursive-procedures-visual-basic"></a><span data-ttu-id="8cf7e-102">재귀 프로시저(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8cf7e-102">Recursive Procedures (Visual Basic)</span></span>
<span data-ttu-id="8cf7e-103">A *재귀* 절차는 자신을 호출 하는 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="8cf7e-103">A *recursive* procedure is one that calls itself.</span></span> <span data-ttu-id="8cf7e-104">일반적으로 이것이 작성 하는 가장 효과적인 방법은 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="8cf7e-104">In general, this is not the most effective way to write [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] code.</span></span>  
  
 <span data-ttu-id="8cf7e-105">다음 절차에서는 원래 인수의 계승 계산을 재귀를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cf7e-105">The following procedure uses recursion to calculate the factorial of its original argument.</span></span>  
  
 <span data-ttu-id="8cf7e-106">[!code-vb[VbVbcnProcedures #&51;](./codesnippet/VisualBasic/recursive-procedures_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="8cf7e-106">[!code-vb[VbVbcnProcedures#51](./codesnippet/VisualBasic/recursive-procedures_1.vb)]</span></span>  
  
## <a name="considerations-with-recursive-procedures"></a><span data-ttu-id="8cf7e-107">재귀 프로시저에 대 한 고려 사항</span><span class="sxs-lookup"><span data-stu-id="8cf7e-107">Considerations with Recursive Procedures</span></span>  
 <span data-ttu-id="8cf7e-108">**제한 조건**합니다.</span><span class="sxs-lookup"><span data-stu-id="8cf7e-108">**Limiting Conditions**.</span></span> <span data-ttu-id="8cf7e-109">재귀를 종료할 수 있는 하나 이상의 조건에 대해 테스트 하는 재귀 프로시저를 디자인 해야 하 고 적절 한 횟수의 재귀 호출 내에서 없는 이러한 조건을 충족 하는 경우를도 처리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cf7e-109">You must design a recursive procedure to test for at least one condition that can terminate the recursion, and you must also handle the case where no such condition is satisfied within a reasonable number of recursive calls.</span></span> <span data-ttu-id="8cf7e-110">오류 없이 충족 될 수 있는 하나 이상의 조건 없이 프로시저는 무한 루프를 실행 한 높은 위험을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cf7e-110">Without at least one condition that can be met without fail, your procedure runs a high risk of executing in an infinite loop.</span></span>  
  
 <span data-ttu-id="8cf7e-111">**메모리 사용량**합니다.</span><span class="sxs-lookup"><span data-stu-id="8cf7e-111">**Memory Usage**.</span></span> <span data-ttu-id="8cf7e-112">응용 프로그램에 제한 된 양의 지역 변수에 대 한 공간.</span><span class="sxs-lookup"><span data-stu-id="8cf7e-112">Your application has a limited amount of space for local variables.</span></span> <span data-ttu-id="8cf7e-113">프로시저는 자신을 호출할 때마다 사용 하 여 그만큼의 공간이 더는 지역 변수의의 추가 복사본에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cf7e-113">Each time a procedure calls itself, it uses more of that space for additional copies of its local variables.</span></span> <span data-ttu-id="8cf7e-114">이 프로세스는 무기한 계속 되 면 그로 인해는 <xref:System.StackOverflowException>오류.</xref:System.StackOverflowException></span><span class="sxs-lookup"><span data-stu-id="8cf7e-114">If this process continues indefinitely, it eventually causes a <xref:System.StackOverflowException> error.</span></span>  
  
 <span data-ttu-id="8cf7e-115">**효율성**합니다.</span><span class="sxs-lookup"><span data-stu-id="8cf7e-115">**Efficiency**.</span></span> <span data-ttu-id="8cf7e-116">거의 항상 재귀에 대 한 루프를 대체할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cf7e-116">You can almost always substitute a loop for recursion.</span></span> <span data-ttu-id="8cf7e-117">루프는 인수 전달 추가 저장소를 초기화 하 고 값을 반환 하는 오버 헤드는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8cf7e-117">A loop does not have the overhead of passing arguments, initializing additional storage, and returning values.</span></span> <span data-ttu-id="8cf7e-118">성능 재귀 호출 하지 않고 훨씬 향상 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cf7e-118">Your performance can be much better without recursive calls.</span></span>  
  
 <span data-ttu-id="8cf7e-119">**상호 재귀**합니다.</span><span class="sxs-lookup"><span data-stu-id="8cf7e-119">**Mutual Recursion**.</span></span> <span data-ttu-id="8cf7e-120">두 절차 서로 호출 하는 경우 성능이 매우 저하 또는 심지어는 무한 루프를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cf7e-120">You might observe very poor performance, or even an infinite loop, if two procedures call each other.</span></span> <span data-ttu-id="8cf7e-121">이러한 디자인을 단일 재귀 프로시저와 같은 문제를 표시 하지만 검색 하 고 디버그 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cf7e-121">Such a design presents the same problems as a single recursive procedure, but can be harder to detect and debug.</span></span>  
  
 <span data-ttu-id="8cf7e-122">**괄호를 사용한 호출**합니다.</span><span class="sxs-lookup"><span data-stu-id="8cf7e-122">**Calling with Parentheses**.</span></span> <span data-ttu-id="8cf7e-123">경우는 `Function` 재귀적으로 프로시저 호출, 인수 목록이 없는 경우에 프로시저 이름 뒤에 괄호를 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cf7e-123">When a `Function` procedure calls itself recursively, you must follow the procedure name with parentheses, even if there is no argument list.</span></span> <span data-ttu-id="8cf7e-124">그렇지 않은 경우 함수 이름은 함수의 반환 값을 나타내는 것으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cf7e-124">Otherwise, the function name is taken as representing the return value of the function.</span></span>  
  
 <span data-ttu-id="8cf7e-125">**테스트**합니다.</span><span class="sxs-lookup"><span data-stu-id="8cf7e-125">**Testing**.</span></span> <span data-ttu-id="8cf7e-126">재귀 프로시저를 작성 하는 경우 항상 제한 일부 조건이 충족 되었는지 확인 하려면 신중 하 게 테스트 해야 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cf7e-126">If you write a recursive procedure, you should test it very carefully to make sure it always meets some limiting condition.</span></span> <span data-ttu-id="8cf7e-127">또한 재귀 호출이 너무 많아서 인해 메모리가 부족 해지지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cf7e-127">You should also ensure that you cannot run out of memory due to having too many recursive calls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cf7e-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8cf7e-128">See Also</span></span>  
 <span data-ttu-id="8cf7e-129"><xref:System.StackOverflowException></xref:System.StackOverflowException></span><span class="sxs-lookup"><span data-stu-id="8cf7e-129"><xref:System.StackOverflowException></span></span>   
<span data-ttu-id="8cf7e-130"> [프로시저](./index.md) </span><span class="sxs-lookup"><span data-stu-id="8cf7e-130"> [Procedures](./index.md) </span></span>  
<span data-ttu-id="8cf7e-131"> [Sub 프로시저](./sub-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="8cf7e-131"> [Sub Procedures](./sub-procedures.md) </span></span>  
<span data-ttu-id="8cf7e-132"> [Function 프로시저](./function-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="8cf7e-132"> [Function Procedures](./function-procedures.md) </span></span>  
<span data-ttu-id="8cf7e-133"> [속성 프로시저](./property-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="8cf7e-133"> [Property Procedures](./property-procedures.md) </span></span>  
<span data-ttu-id="8cf7e-134"> [연산자 프로시저](./operator-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="8cf7e-134"> [Operator Procedures](./operator-procedures.md) </span></span>  
<span data-ttu-id="8cf7e-135"> [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="8cf7e-135"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="8cf7e-136"> [프로시저 오버 로드](./procedure-overloading.md) </span><span class="sxs-lookup"><span data-stu-id="8cf7e-136"> [Procedure Overloading](./procedure-overloading.md) </span></span>  
<span data-ttu-id="8cf7e-137"> [문제 해결 절차](./troubleshooting-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="8cf7e-137"> [Troubleshooting Procedures](./troubleshooting-procedures.md) </span></span>  
<span data-ttu-id="8cf7e-138"> [루프 구조](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md) </span><span class="sxs-lookup"><span data-stu-id="8cf7e-138"> [Loop Structures](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md) </span></span>  
<span data-ttu-id="8cf7e-139"> [예외 문제 해결: System.StackOverflowException](http://msdn.microsoft.com/library/51b71217-c507-4f5b-bc35-0236180d7968)</span><span class="sxs-lookup"><span data-stu-id="8cf7e-139"> [Troubleshooting Exceptions: System.StackOverflowException](http://msdn.microsoft.com/library/51b71217-c507-4f5b-bc35-0236180d7968)</span></span>
