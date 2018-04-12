---
title: IsTrue 연산자(Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.istrue
helpviewer_keywords:
- IsTrue operator [Visual Basic]
- OrElse operator [Visual Basic]
ms.assetid: b6cec0f2-61b1-4331-a7f0-4d07ee3179d6
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c0d261186ce68f06cec95251e815248a189f6da5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="istrue-operator-visual-basic"></a><span data-ttu-id="3dfbe-102">IsTrue 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3dfbe-102">IsTrue Operator (Visual Basic)</span></span>
<span data-ttu-id="3dfbe-103">식이 인지 결정 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="3dfbe-103">Determines whether an expression is `True`.</span></span>  
  
 <span data-ttu-id="3dfbe-104">호출할 수 없습니다 `IsTrue` 명시적으로 코드 하지만 Visual Basic에서 컴파일러 있습니다 사용할에서 코드를 생성할 `OrElse` 절.</span><span class="sxs-lookup"><span data-stu-id="3dfbe-104">You cannot call `IsTrue` explicitly in your code, but the Visual Basic compiler can use it to generate code from `OrElse` clauses.</span></span> <span data-ttu-id="3dfbe-105">클래스 또는 구조체 정의 다음에 해당 형식의 변수를 사용 하는 경우는 `OrElse` 정의 해야 절 `IsTrue` 해당 클래스 또는 구조체에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="3dfbe-105">If you define a class or structure and then use a variable of that type in an `OrElse` clause, you must define `IsTrue` on that class or structure.</span></span>  
  
 <span data-ttu-id="3dfbe-106">컴파일러 있다고 간주는 `IsTrue` 및 `IsFalse` 으로 연산자는 *일치 하는 쌍*합니다.</span><span class="sxs-lookup"><span data-stu-id="3dfbe-106">The compiler considers the `IsTrue` and `IsFalse` operators as a *matched pair*.</span></span> <span data-ttu-id="3dfbe-107">이 둘 중 하나를 정의 하는 경우도 정의 해야 다른 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="3dfbe-107">This means that if you define one of them, you must also define the other one.</span></span>  
  
## <a name="compiler-use-of-istrue"></a><span data-ttu-id="3dfbe-108">IsTrue 컴파일러 사용</span><span class="sxs-lookup"><span data-stu-id="3dfbe-108">Compiler Use of IsTrue</span></span>  
 <span data-ttu-id="3dfbe-109">클래스 또는 구조체를 정의에서 해당 형식의 변수를 사용할 수 있습니다는 `For`, `If`, `Else``If`, 또는 `While` 문, 또는 `When` 절.</span><span class="sxs-lookup"><span data-stu-id="3dfbe-109">When you have defined a class or structure, you can use a variable of that type in a `For`, `If`, `Else``If`, or `While` statement, or in a `When` clause.</span></span> <span data-ttu-id="3dfbe-110">이 작업을 수행 하는 경우 컴파일러가 프로그램 형식으로 변환 하는 연산자가 필요는 `Boolean` 조건을 테스트할 수 있도록 값입니다.</span><span class="sxs-lookup"><span data-stu-id="3dfbe-110">If you do this, the compiler requires an operator that converts your type into a `Boolean` value so it can test a condition.</span></span> <span data-ttu-id="3dfbe-111">적합 한 연산자는 다음 순서 대로 검색 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3dfbe-111">It searches for a suitable operator in the following order:</span></span>  
  
1.  <span data-ttu-id="3dfbe-112">확대 변환 연산자를 클래스 또는 구조를 `Boolean`합니다.</span><span class="sxs-lookup"><span data-stu-id="3dfbe-112">A widening conversion operator from your class or structure to `Boolean`.</span></span>  
  
2.  <span data-ttu-id="3dfbe-113">확대 변환 연산자를 클래스 또는 구조를 `Boolean?`합니다.</span><span class="sxs-lookup"><span data-stu-id="3dfbe-113">A widening conversion operator from your class or structure to `Boolean?`.</span></span>  
  
3.  <span data-ttu-id="3dfbe-114">`IsTrue` 클래스 또는 구조체에서 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="3dfbe-114">The `IsTrue` operator on your class or structure.</span></span>  
  
4.  <span data-ttu-id="3dfbe-115">범위가 좁은 `Boolean?` 변환 포함 하지 않는 `Boolean` 를 `Boolean?`합니다.</span><span class="sxs-lookup"><span data-stu-id="3dfbe-115">A narrowing conversion to `Boolean?` that does not involve a conversion from `Boolean` to `Boolean?`.</span></span>  
  
5.  <span data-ttu-id="3dfbe-116">축소 변환 연산자를 클래스 또는 구조를 `Boolean`합니다.</span><span class="sxs-lookup"><span data-stu-id="3dfbe-116">A narrowing conversion operator from your class or structure to `Boolean`.</span></span>  
  
 <span data-ttu-id="3dfbe-117">으로 변환이 정의 되지 않은 경우 `Boolean` 또는 `IsTrue` 연산자, 컴파일러에서 오류를 알립니다.</span><span class="sxs-lookup"><span data-stu-id="3dfbe-117">If you have not defined any conversion to `Boolean` or an `IsTrue` operator, the compiler signals an error.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3dfbe-118">`IsTrue` 연산자 될 수 있습니다 *오버 로드 된*, 클래스 또는 구조체 수 할의 동작에 해당 클래스 또는 구조체의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="3dfbe-118">The `IsTrue` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="3dfbe-119">이 연산자를 사용 하 여 이러한 클래스나 구조체에는 코드를 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3dfbe-119">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="3dfbe-120">자세한 내용은 참조 [연산자 프로시저](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3dfbe-120">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3dfbe-121">예제</span><span class="sxs-lookup"><span data-stu-id="3dfbe-121">Example</span></span>  
 <span data-ttu-id="3dfbe-122">다음 코드 예제에 대 한 정의 포함 하는 구조체의 개요를 정의 고 `IsFalse` 및 `IsTrue` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="3dfbe-122">The following code example defines the outline of a structure that includes definitions for the `IsFalse` and `IsTrue` operators.</span></span>  
  
 [!code-vb[VbVbalrOperators#28](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/istrue-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="3dfbe-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3dfbe-123">See Also</span></span>  
 [<span data-ttu-id="3dfbe-124">IsFalse 연산자</span><span class="sxs-lookup"><span data-stu-id="3dfbe-124">IsFalse Operator</span></span>](../../../visual-basic/language-reference/operators/isfalse-operator.md)  
 [<span data-ttu-id="3dfbe-125">방법: 연산자 정의</span><span class="sxs-lookup"><span data-stu-id="3dfbe-125">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [<span data-ttu-id="3dfbe-126">OrElse 연산자</span><span class="sxs-lookup"><span data-stu-id="3dfbe-126">OrElse Operator</span></span>](../../../visual-basic/language-reference/operators/orelse-operator.md)
