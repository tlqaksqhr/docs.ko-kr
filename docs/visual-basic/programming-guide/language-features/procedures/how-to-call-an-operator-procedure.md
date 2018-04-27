---
title: '방법: 연산자 프로시저 호출(Visual Basic)'
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- operator procedures [Visual Basic], calling
- procedures [Visual Basic], operator
- procedure calls [Visual Basic], operator overloading
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- overloaded operators [Visual Basic], calling
- operator overloading
ms.assetid: 0dce42cc-f0b0-4c14-9f62-018b21f33497
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 21545f2488bfabd0abc9c6e316d21bbc4d5aeb91
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-call-an-operator-procedure-visual-basic"></a><span data-ttu-id="f353d-102">방법: 연산자 프로시저 호출(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f353d-102">How to: Call an Operator Procedure (Visual Basic)</span></span>
<span data-ttu-id="f353d-103">연산자 기호를 사용 하 여 식에서 연산자 프로시저를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="f353d-103">You call an operator procedure by using the operator symbol in an expression.</span></span> <span data-ttu-id="f353d-104">호출 하 여 변환 연산자의 경우는 [CType 함수](../../../../visual-basic/language-reference/functions/ctype-function.md) 다른 값의 데이터 형식을 변환 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="f353d-104">In the case of a conversion operator, you call the [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) to convert a value from one data type to another.</span></span>  
  
 <span data-ttu-id="f353d-105">연산자 프로시저를 명시적으로 호출 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f353d-105">You do not call operator procedures explicitly.</span></span> <span data-ttu-id="f353d-106">연산자를 사용 또는 `CType` 대입문 또는 식에서 일반적으로 연산자를 사용 하면 동일한 방식으로 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="f353d-106">You just use the operator, or the `CType` function, in an assignment statement or an expression, the same way you ordinarily use an operator.</span></span> <span data-ttu-id="f353d-107">Visual Basic 연산자 프로시저를 호출을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f353d-107">Visual Basic makes the call to the operator procedure.</span></span>  
  
 <span data-ttu-id="f353d-108">클래스 또는 구조체에서 연산자를 정의 라고도 *오버 로드* 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="f353d-108">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
### <a name="to-call-an-operator-procedure"></a><span data-ttu-id="f353d-109">연산자 프로시저를 호출 하려면</span><span class="sxs-lookup"><span data-stu-id="f353d-109">To call an operator procedure</span></span>  
  
1.  <span data-ttu-id="f353d-110">일반적인 방법으로 식에 연산자 기호를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f353d-110">Use the operator symbol in an expression in the ordinary way.</span></span>  
  
2.  <span data-ttu-id="f353d-111">피연산자의 데이터 형식에 적합 한 연산자를 올바른 순서로 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f353d-111">Be sure the data types of the operands are appropriate for the operator, and in the correct order.</span></span>  
  
3.  <span data-ttu-id="f353d-112">예상 대로 연산자는 식의 값에 기여 합니다.</span><span class="sxs-lookup"><span data-stu-id="f353d-112">The operator contributes to the value of the expression as expected.</span></span>  
  
### <a name="to-call-a-conversion-operator-procedure"></a><span data-ttu-id="f353d-113">변환 연산자 프로시저를 호출 하려면</span><span class="sxs-lookup"><span data-stu-id="f353d-113">To call a conversion operator procedure</span></span>  
  
1.  <span data-ttu-id="f353d-114">사용 하 여 `CType` 식 안에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f353d-114">Use `CType` inside an expression.</span></span>  
  
2.  <span data-ttu-id="f353d-115">피연산자의 데이터 형식에 적합 한 변환, 올바른 순서로 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f353d-115">Be sure the data types of the operands are appropriate for the conversion, and in the correct order.</span></span>  
  
3.  <span data-ttu-id="f353d-116">`CType` 변환 연산자 프로시저를 호출 하 고 변환 된 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f353d-116">`CType` calls the conversion operator procedure and returns the converted value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f353d-117">예제</span><span class="sxs-lookup"><span data-stu-id="f353d-117">Example</span></span>  
 <span data-ttu-id="f353d-118">다음 예제에서는 두 개의 <xref:System.TimeSpan> 구조가 함께 추가 하 고 세 번째 결과 저장 <xref:System.TimeSpan> 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="f353d-118">The following example creates two <xref:System.TimeSpan> structures, adds them together, and stores the result in a third <xref:System.TimeSpan> structure.</span></span> <span data-ttu-id="f353d-119"><xref:System.TimeSpan> 구조는 여러 가지 표준 연산자를 오버 로드할 연산자 프로시저를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="f353d-119">The <xref:System.TimeSpan> structure defines operator procedures to overload several standard operators.</span></span>  
  
 [!code-vb[VbVbcnProcedures#29](./codesnippet/VisualBasic/how-to-call-an-operator-procedure_1.vb)]  
  
 <span data-ttu-id="f353d-120">때문에 <xref:System.TimeSpan> 표준 오버 로드 `+` 연산자 앞의 예제 연산자 프로시저 호출의 값을 계산할 때 `combinedSpan`합니다.</span><span class="sxs-lookup"><span data-stu-id="f353d-120">Because <xref:System.TimeSpan> overloads the standard `+` operator, the previous example calls an operator procedure when it calculates the value of `combinedSpan`.</span></span>  
  
 <span data-ttu-id="f353d-121">변환 연산자 프로시저 호출 예를 참조 하십시오. [하는 방법: 해당 정의 연산자는 클래스를 사용 하 여](./how-to-use-a-class-that-defines-operators.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f353d-121">For an example of calling a conversation operator procedure, see [How to: Use a Class that Defines Operators](./how-to-use-a-class-that-defines-operators.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f353d-122">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="f353d-122">Compiling the Code</span></span>  
 <span data-ttu-id="f353d-123">클래스 또는 구조체를 사용 하는 데 사용할 연산자를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f353d-123">Be sure the class or structure you are using defines the operator you want to use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f353d-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f353d-124">See Also</span></span>  
 [<span data-ttu-id="f353d-125">연산자 프로시저</span><span class="sxs-lookup"><span data-stu-id="f353d-125">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="f353d-126">방법: 연산자 정의</span><span class="sxs-lookup"><span data-stu-id="f353d-126">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)  
 [<span data-ttu-id="f353d-127">방법: 변환 연산자 정의</span><span class="sxs-lookup"><span data-stu-id="f353d-127">How to: Define a Conversion Operator</span></span>](./how-to-define-a-conversion-operator.md)  
 [<span data-ttu-id="f353d-128">Operator 문</span><span class="sxs-lookup"><span data-stu-id="f353d-128">Operator Statement</span></span>](../../../../visual-basic/language-reference/statements/operator-statement.md)  
 [<span data-ttu-id="f353d-129">확장</span><span class="sxs-lookup"><span data-stu-id="f353d-129">Widening</span></span>](../../../../visual-basic/language-reference/modifiers/widening.md)  
 [<span data-ttu-id="f353d-130">Narrowing</span><span class="sxs-lookup"><span data-stu-id="f353d-130">Narrowing</span></span>](../../../../visual-basic/language-reference/modifiers/narrowing.md)  
 [<span data-ttu-id="f353d-131">Structure 문</span><span class="sxs-lookup"><span data-stu-id="f353d-131">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)  
 [<span data-ttu-id="f353d-132">방법: 구조체 선언</span><span class="sxs-lookup"><span data-stu-id="f353d-132">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [<span data-ttu-id="f353d-133">암시적 변환과 명시적 변환</span><span class="sxs-lookup"><span data-stu-id="f353d-133">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [<span data-ttu-id="f353d-134">확대 변환과 축소 변환</span><span class="sxs-lookup"><span data-stu-id="f353d-134">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
