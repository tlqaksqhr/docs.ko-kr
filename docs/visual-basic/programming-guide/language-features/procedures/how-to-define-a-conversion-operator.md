---
title: '방법: 변환 연산자 정의(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- operators [Visual Basic], defining
- procedures [Visual Basic], operator
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: 54203dfa-c24b-463f-9942-d5153e89e762
ms.openlocfilehash: 24bbe41af67f757cae661a78d482a423ff0ffd85
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648475"
---
# <a name="how-to-define-a-conversion-operator-visual-basic"></a><span data-ttu-id="3ffd2-102">방법: 변환 연산자 정의(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3ffd2-102">How to: Define a Conversion Operator (Visual Basic)</span></span>
<span data-ttu-id="3ffd2-103">클래스 또는 구조체를 정의 하는 경우 클래스 또는 구조체의 형식과 다른 데이터 형식 간에 형식 변환 연산자를 정의할 수 있습니다 (예: `Integer`, `Double`, 또는 `String`).</span><span class="sxs-lookup"><span data-stu-id="3ffd2-103">If you have defined a class or structure, you can define a type conversion operator between the type of your class or structure and another data type (such as `Integer`, `Double`, or `String`).</span></span>  
  
 <span data-ttu-id="3ffd2-104">형식 변환으로 정의 된 [CType 함수](../../../../visual-basic/language-reference/functions/ctype-function.md) 클래스 또는 구조체 내에서 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="3ffd2-104">Define the type conversion as a [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) procedure within the class or structure.</span></span> <span data-ttu-id="3ffd2-105">모든 변환 프로시저 여야 `Public Shared`를 각각 지정 해야 하 고 [Widening](../../../../visual-basic/language-reference/modifiers/widening.md) 또는 [문제의 범위 제한](../../../../visual-basic/language-reference/modifiers/narrowing.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3ffd2-105">All conversion procedures must be `Public Shared`, and each one must specify either [Widening](../../../../visual-basic/language-reference/modifiers/widening.md) or [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md).</span></span>  
  
 <span data-ttu-id="3ffd2-106">클래스 또는 구조체에서 연산자를 정의 라고도 *오버 로드* 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="3ffd2-106">Defining an operator on a class or structure is also called *overloading* the operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3ffd2-107">예제</span><span class="sxs-lookup"><span data-stu-id="3ffd2-107">Example</span></span>  
 <span data-ttu-id="3ffd2-108">다음 예에서는 라는 구조 간의 변환 연산자 정의 `digit` 및 `Byte`합니다.</span><span class="sxs-lookup"><span data-stu-id="3ffd2-108">The following example defines conversion operators between a structure called `digit` and a `Byte`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#27](./codesnippet/VisualBasic/how-to-define-a-conversion-operator_1.vb)]  
  
 <span data-ttu-id="3ffd2-109">구조를 테스트할 수 `digit` 다음 코드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ffd2-109">You can test the structure `digit` with the following code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#28](./codesnippet/VisualBasic/how-to-define-a-conversion-operator_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="3ffd2-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3ffd2-110">See Also</span></span>  
 [<span data-ttu-id="3ffd2-111">연산자 프로시저</span><span class="sxs-lookup"><span data-stu-id="3ffd2-111">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="3ffd2-112">방법: 연산자 정의</span><span class="sxs-lookup"><span data-stu-id="3ffd2-112">How to: Define an Operator</span></span>](./how-to-define-an-operator.md)  
 [<span data-ttu-id="3ffd2-113">방법: 연산자 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="3ffd2-113">How to: Call an Operator Procedure</span></span>](./how-to-call-an-operator-procedure.md)  
 [<span data-ttu-id="3ffd2-114">방법: 연산자를 정의하는 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="3ffd2-114">How to: Use a Class that Defines Operators</span></span>](./how-to-use-a-class-that-defines-operators.md)  
 [<span data-ttu-id="3ffd2-115">Operator 문</span><span class="sxs-lookup"><span data-stu-id="3ffd2-115">Operator Statement</span></span>](../../../../visual-basic/language-reference/statements/operator-statement.md)  
 [<span data-ttu-id="3ffd2-116">Structure 문</span><span class="sxs-lookup"><span data-stu-id="3ffd2-116">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)  
 [<span data-ttu-id="3ffd2-117">방법: 구조체 선언</span><span class="sxs-lookup"><span data-stu-id="3ffd2-117">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [<span data-ttu-id="3ffd2-118">암시적 변환과 명시적 변환</span><span class="sxs-lookup"><span data-stu-id="3ffd2-118">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [<span data-ttu-id="3ffd2-119">확대 변환과 축소 변환</span><span class="sxs-lookup"><span data-stu-id="3ffd2-119">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
