---
title: "방법: 연산자 프로시저 (Visual Basic)를 호출 합니다. | Microsoft 문서"
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
- operator procedures, calling
- procedures, operator
- procedure calls, operator overloading
- syntax, Operator procedures
- operators [Visual Basic], overloading
- return values, Operator procedures
- overloaded operators, calling
- operator overloading
ms.assetid: 0dce42cc-f0b0-4c14-9f62-018b21f33497
caps.latest.revision: 16
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
ms.openlocfilehash: cd85a14a6f5534e90497268134f4b2b0cc292249
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-call-an-operator-procedure-visual-basic"></a><span data-ttu-id="15ee2-102">방법: 연산자 프로시저 호출(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="15ee2-102">How to: Call an Operator Procedure (Visual Basic)</span></span>
<span data-ttu-id="15ee2-103">연산자 기호를 사용 하 여 식에서 연산자 프로시저를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="15ee2-103">You call an operator procedure by using the operator symbol in an expression.</span></span> <span data-ttu-id="15ee2-104">변환 연산자의 경우 호출 된 [CType 함수](../../../../visual-basic/language-reference/functions/ctype-function.md) 다른 값의 데이터 형식을 변환 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="15ee2-104">In the case of a conversion operator, you call the [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) to convert a value from one data type to another.</span></span>  
  
 <span data-ttu-id="15ee2-105">연산자 프로시저를 명시적으로 호출 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="15ee2-105">You do not call operator procedures explicitly.</span></span> <span data-ttu-id="15ee2-106">연산자를 사용 또는 `CType` 대입문 이나 일반적으로 연산자를 사용 하면 동일한 방식으로 식에서 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="15ee2-106">You just use the operator, or the `CType` function, in an assignment statement or an expression, the same way you ordinarily use an operator.</span></span> [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="15ee2-107">연산자 프로시저를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="15ee2-107"> makes the call to the operator procedure.</span></span>  
  
 <span data-ttu-id="15ee2-108">연산자를 정의 하는 클래스 또는 구조체에는 라고도 *오버 로드* 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="15ee2-108">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
### <a name="to-call-an-operator-procedure"></a><span data-ttu-id="15ee2-109">연산자 프로시저를 호출 하려면</span><span class="sxs-lookup"><span data-stu-id="15ee2-109">To call an operator procedure</span></span>  
  
1.  <span data-ttu-id="15ee2-110">일반적인 방법으로 식에서 연산자 기호를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="15ee2-110">Use the operator symbol in an expression in the ordinary way.</span></span>  
  
2.  <span data-ttu-id="15ee2-111">피연산자의 데이터 형식에 적합 한 연산자를 올바른 순서로 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="15ee2-111">Be sure the data types of the operands are appropriate for the operator, and in the correct order.</span></span>  
  
3.  <span data-ttu-id="15ee2-112">연산자는 예상 대로 식의 값에 기여 합니다.</span><span class="sxs-lookup"><span data-stu-id="15ee2-112">The operator contributes to the value of the expression as expected.</span></span>  
  
### <a name="to-call-a-conversion-operator-procedure"></a><span data-ttu-id="15ee2-113">변환 연산자 프로시저를 호출 하려면</span><span class="sxs-lookup"><span data-stu-id="15ee2-113">To call a conversion operator procedure</span></span>  
  
1.  <span data-ttu-id="15ee2-114">사용 하 여 `CType` 식 안에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15ee2-114">Use `CType` inside an expression.</span></span>  
  
2.  <span data-ttu-id="15ee2-115">변환에 적합 한 올바른 순서로 피연산자의 데이터 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="15ee2-115">Be sure the data types of the operands are appropriate for the conversion, and in the correct order.</span></span>  
  
3.  <span data-ttu-id="15ee2-116">`CType`변환 연산자 프로시저를 호출 하 고 변환 된 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="15ee2-116">`CType` calls the conversion operator procedure and returns the converted value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="15ee2-117">예제</span><span class="sxs-lookup"><span data-stu-id="15ee2-117">Example</span></span>  
 <span data-ttu-id="15ee2-118">다음 예제에서는 두 개의 <xref:System.TimeSpan>구조를 함께 추가 하 고 세 번째 결과 저장 <xref:System.TimeSpan>구조.</xref:System.TimeSpan> </xref:System.TimeSpan></span><span class="sxs-lookup"><span data-stu-id="15ee2-118">The following example creates two <xref:System.TimeSpan> structures, adds them together, and stores the result in a third <xref:System.TimeSpan> structure.</span></span> <span data-ttu-id="15ee2-119"><xref:System.TimeSpan>구조 연산자 프로시저를 여러 표준 연산자를 오버 로드를 정의 합니다.</xref:System.TimeSpan></span><span class="sxs-lookup"><span data-stu-id="15ee2-119">The <xref:System.TimeSpan> structure defines operator procedures to overload several standard operators.</span></span>  
  
 <span data-ttu-id="15ee2-120">[!code-vb[VbVbcnProcedures #&29;](./codesnippet/VisualBasic/how-to-call-an-operator-procedure_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="15ee2-120">[!code-vb[VbVbcnProcedures#29](./codesnippet/VisualBasic/how-to-call-an-operator-procedure_1.vb)]</span></span>  
  
 <span data-ttu-id="15ee2-121">때문에 <xref:System.TimeSpan>표준 오버 로드 `+` 연산자 앞의 예제 프로시저를 호출 연산자의 값을 계산할 때 `combinedSpan`.</xref:System.TimeSpan></span><span class="sxs-lookup"><span data-stu-id="15ee2-121">Because <xref:System.TimeSpan> overloads the standard `+` operator, the previous example calls an operator procedure when it calculates the value of `combinedSpan`.</span></span>  
  
 <span data-ttu-id="15ee2-122">변환 연산자 프로시저 호출의 예제를 참조 하십시오. [하는 방법: 클래스는 정의 연산자를 사용 하는 여](./how-to-use-a-class-that-defines-operators.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="15ee2-122">For an example of calling a conversation operator procedure, see [How to: Use a Class that Defines Operators](./how-to-use-a-class-that-defines-operators.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="15ee2-123">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="15ee2-123">Compiling the Code</span></span>  
 <span data-ttu-id="15ee2-124">클래스 또는 구조체를 사용 하는 데 사용할 연산자를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="15ee2-124">Be sure the class or structure you are using defines the operator you want to use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15ee2-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="15ee2-125">See Also</span></span>  
 <span data-ttu-id="15ee2-126">[연산자 프로시저](./operator-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="15ee2-126">[Operator Procedures](./operator-procedures.md) </span></span>  
<span data-ttu-id="15ee2-127"> [방법: 연산자 정의](./how-to-define-an-operator.md) </span><span class="sxs-lookup"><span data-stu-id="15ee2-127"> [How to: Define an Operator](./how-to-define-an-operator.md) </span></span>  
<span data-ttu-id="15ee2-128"> [방법: 변환 연산자 정의](./how-to-define-a-conversion-operator.md) </span><span class="sxs-lookup"><span data-stu-id="15ee2-128"> [How to: Define a Conversion Operator](./how-to-define-a-conversion-operator.md) </span></span>  
<span data-ttu-id="15ee2-129"> [Operator 문](../../../../visual-basic/language-reference/statements/operator-statement.md) </span><span class="sxs-lookup"><span data-stu-id="15ee2-129"> [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md) </span></span>  
<span data-ttu-id="15ee2-130"> [확대 변환](../../../../visual-basic/language-reference/modifiers/widening.md) </span><span class="sxs-lookup"><span data-stu-id="15ee2-130"> [Widening](../../../../visual-basic/language-reference/modifiers/widening.md) </span></span>  
<span data-ttu-id="15ee2-131"> [축소](../../../../visual-basic/language-reference/modifiers/narrowing.md) </span><span class="sxs-lookup"><span data-stu-id="15ee2-131"> [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md) </span></span>  
<span data-ttu-id="15ee2-132"> [Structure 문](../../../../visual-basic/language-reference/statements/structure-statement.md) </span><span class="sxs-lookup"><span data-stu-id="15ee2-132"> [Structure Statement](../../../../visual-basic/language-reference/statements/structure-statement.md) </span></span>  
<span data-ttu-id="15ee2-133"> [방법: 구조체 선언](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md) </span><span class="sxs-lookup"><span data-stu-id="15ee2-133"> [How to: Declare a Structure](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md) </span></span>  
<span data-ttu-id="15ee2-134"> [암시적 변환과 명시적 변환](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="15ee2-134"> [Implicit and Explicit Conversions](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) </span></span>  
<span data-ttu-id="15ee2-135"> [확대 변환과 축소 변환](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)</span><span class="sxs-lookup"><span data-stu-id="15ee2-135"> [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)</span></span>
