---
title: '&amp;= 연산자 (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.&=
helpviewer_keywords:
- operator &=
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- '&= operator [Visual Basic]'
- compound assignment statements [Visual Basic]
ms.assetid: 0cf262fc-1a05-419a-a503-60013f111c8a
ms.openlocfilehash: c3db2d4095600f32af92d1a4ce1f806a3f032af0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33601883"
---
# <a name="amp-operator-visual-basic"></a><span data-ttu-id="92db1-102">&amp;= 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="92db1-102">&amp;= Operator (Visual Basic)</span></span>
<span data-ttu-id="92db1-103">연결 하는 `String` 식을 `String` 변수 또는 속성 변수 또는 속성에는 결과 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="92db1-103">Concatenates a `String` expression to a `String` variable or property and assigns the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92db1-104">구문</span><span class="sxs-lookup"><span data-stu-id="92db1-104">Syntax</span></span>  
  
```  
variableorproperty &= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="92db1-105">요소</span><span class="sxs-lookup"><span data-stu-id="92db1-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="92db1-106">필수.</span><span class="sxs-lookup"><span data-stu-id="92db1-106">Required.</span></span> <span data-ttu-id="92db1-107">모든 `String` 변수 또는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="92db1-107">Any `String` variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="92db1-108">필수.</span><span class="sxs-lookup"><span data-stu-id="92db1-108">Required.</span></span> <span data-ttu-id="92db1-109">임의의 `String` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="92db1-109">Any `String` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="92db1-110">설명</span><span class="sxs-lookup"><span data-stu-id="92db1-110">Remarks</span></span>  
 <span data-ttu-id="92db1-111">왼쪽에 요소는 `&=` 연산자는 간단한 스칼라 변수, 속성 또는 배열의 요소 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92db1-111">The element on the left side of the `&=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="92db1-112">변수 또는 속성 수 없습니다 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="92db1-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span> <span data-ttu-id="92db1-113">`&=` 연산자는 연결의 `String` 는 오른쪽에 식이 `String` 변수나 속성의 왼쪽에는 결과를 변수나 속성의 왼쪽에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="92db1-113">The `&=` operator concatenates the `String` expression on its right to the `String` variable or property on its left, and assigns the result to the variable or property on its left.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="92db1-114">오버로딩</span><span class="sxs-lookup"><span data-stu-id="92db1-114">Overloading</span></span>  
 <span data-ttu-id="92db1-115">[& 연산자](../../../visual-basic/language-reference/operators/concatenation-operator.md) 수 *오버 로드 된*, 클래스 또는 구조체 수 할의 동작에 해당 클래스 또는 구조체의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="92db1-115">The [& Operator](../../../visual-basic/language-reference/operators/concatenation-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="92db1-116">오버 로드는 `&` 연산자의 동작에 영향을 줍니다는 `&=` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="92db1-116">Overloading the `&` operator affects the behavior of the `&=` operator.</span></span> <span data-ttu-id="92db1-117">코드에서 `&=` 클래스 또는 구조체에 오버 로드에서 `&`, 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="92db1-117">If your code uses `&=` on a class or structure that overloads `&`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="92db1-118">자세한 내용은 참조 [연산자 프로시저](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="92db1-118">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="92db1-119">예제</span><span class="sxs-lookup"><span data-stu-id="92db1-119">Example</span></span>  
 <span data-ttu-id="92db1-120">다음 예제에서는 `&=` 연산자를 두 개의 `String` 변수 및 결과 첫 번째 변수에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="92db1-120">The following example uses the `&=` operator to concatenate two `String` variables and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#3](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/and-assignment-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="92db1-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="92db1-121">See Also</span></span>  
 [<span data-ttu-id="92db1-122">& 연산자</span><span class="sxs-lookup"><span data-stu-id="92db1-122">& Operator</span></span>](../../../visual-basic/language-reference/operators/concatenation-operator.md)  
 [<span data-ttu-id="92db1-123">+= 연산자</span><span class="sxs-lookup"><span data-stu-id="92db1-123">+= Operator</span></span>](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)  
 [<span data-ttu-id="92db1-124">할당 연산자</span><span class="sxs-lookup"><span data-stu-id="92db1-124">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [<span data-ttu-id="92db1-125">연결 연산자</span><span class="sxs-lookup"><span data-stu-id="92db1-125">Concatenation Operators</span></span>](../../../visual-basic/language-reference/operators/concatenation-operators.md)  
 [<span data-ttu-id="92db1-126">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="92db1-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="92db1-127">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="92db1-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="92db1-128">문</span><span class="sxs-lookup"><span data-stu-id="92db1-128">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
