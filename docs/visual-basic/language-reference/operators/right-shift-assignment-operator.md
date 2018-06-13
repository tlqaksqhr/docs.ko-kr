---
title: '&gt;&gt;= 연산자 (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.>>=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator >>= [Visual Basic]
- compound assignment statements [Visual Basic]
- '>>= operator [Visual Basic]'
ms.assetid: 2bcd9abb-7a8c-4229-b75d-8816ff1dc700
ms.openlocfilehash: d0c0ea819741f80e30e55a960b1187699898a3bb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604109"
---
# <a name="gtgt-operator-visual-basic"></a><span data-ttu-id="99bc8-102">&gt;&gt;= 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="99bc8-102">&gt;&gt;= Operator (Visual Basic)</span></span>
<span data-ttu-id="99bc8-103">변수 또는 속성의 값에 산술 오른쪽 시프트를 수행 하 고 결과 다시 변수 또는 속성에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="99bc8-103">Performs an arithmetic right shift on the value of a variable or property and assigns the result back to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99bc8-104">구문</span><span class="sxs-lookup"><span data-stu-id="99bc8-104">Syntax</span></span>  
  
```  
variableorproperty >>= amount  
```  
  
## <a name="parts"></a><span data-ttu-id="99bc8-105">요소</span><span class="sxs-lookup"><span data-stu-id="99bc8-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="99bc8-106">필수.</span><span class="sxs-lookup"><span data-stu-id="99bc8-106">Required.</span></span> <span data-ttu-id="99bc8-107">변수 또는 정수 계열 형식의 속성 (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, 또는 `ULong`).</span><span class="sxs-lookup"><span data-stu-id="99bc8-107">Variable or property of an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="99bc8-108">필수.</span><span class="sxs-lookup"><span data-stu-id="99bc8-108">Required.</span></span> <span data-ttu-id="99bc8-109">숫자 식으로 확대 되는 데이터 형식의 `Integer`합니다.</span><span class="sxs-lookup"><span data-stu-id="99bc8-109">Numeric expression of a data type that widens to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="99bc8-110">설명</span><span class="sxs-lookup"><span data-stu-id="99bc8-110">Remarks</span></span>  
 <span data-ttu-id="99bc8-111">왼쪽에 요소는 `>>=` 연산자는 간단한 스칼라 변수, 속성 또는 배열의 요소 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99bc8-111">The element on the left side of the `>>=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="99bc8-112">변수 또는 속성 수 없습니다 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="99bc8-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="99bc8-113">`>>=` 연산자 먼저 변수 또는 속성의 값에 산술 오른쪽 시프트를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="99bc8-113">The `>>=` operator first performs an arithmetic right shift on the value of the variable or property.</span></span> <span data-ttu-id="99bc8-114">연산자는 다음 다시 변수 또는 속성에 해당 작업의 결과 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="99bc8-114">The operator then assigns the result of that operation back to the variable or property.</span></span>  
  
 <span data-ttu-id="99bc8-115">이동 하는 산술 형식 이므로 하지 순환, 결과의 한쪽 끝에서 이동 하는 비트는 다른 쪽 끝에서 다시 도입 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99bc8-115">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="99bc8-116">산술 오른쪽 시프트 연산 가장 오른쪽 위치를 넘어 이동 하는 비트는 무시 되 고 왼쪽 비트는 비워진 왼쪽 비트 위치로 전파 됩니다.</span><span class="sxs-lookup"><span data-stu-id="99bc8-116">In an arithmetic right shift, the bits shifted beyond the rightmost bit position are discarded, and the leftmost bit is propagated into the bit positions vacated at the left.</span></span> <span data-ttu-id="99bc8-117">즉 `variableorproperty` 음수 값을 가진 비워진된 위치 1로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="99bc8-117">This means that if `variableorproperty` has a negative value, the vacated positions are set to one.</span></span> <span data-ttu-id="99bc8-118">경우 `variableorproperty` 이 양수인 경우 또는 해당 데이터 형식이 부호 없는 형식이 면 하는 경우 비워진된 위치 0으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="99bc8-118">If `variableorproperty` is positive, or if its data type is an unsigned type, the vacated positions are set to zero.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="99bc8-119">오버로딩</span><span class="sxs-lookup"><span data-stu-id="99bc8-119">Overloading</span></span>  
 <span data-ttu-id="99bc8-120">[>> 연산자](../../../visual-basic/language-reference/operators/right-shift-operator.md) 수 *오버 로드 된*, 클래스 또는 구조체 수 할의 동작에 해당 클래스 또는 구조체의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="99bc8-120">The [>> Operator](../../../visual-basic/language-reference/operators/right-shift-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="99bc8-121">오버 로드는 `>>` 연산자의 동작에 영향을 줍니다는 `>>=` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="99bc8-121">Overloading the `>>` operator affects the behavior of the `>>=` operator.</span></span> <span data-ttu-id="99bc8-122">코드에서 `>>=` 클래스 또는 구조체에 오버 로드에서 `>>`, 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99bc8-122">If your code uses `>>=` on a class or structure that overloads `>>`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="99bc8-123">자세한 내용은 참조 [연산자 프로시저](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="99bc8-123">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="99bc8-124">예제</span><span class="sxs-lookup"><span data-stu-id="99bc8-124">Example</span></span>  
 <span data-ttu-id="99bc8-125">다음 예제에서는 `>>=` 의 비트 패턴을 이동할 연산자는 `Integer` 변수 오른쪽으로 지정 된 크기 및 결과를 변수에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="99bc8-125">The following example uses the `>>=` operator to shift the bit pattern of an `Integer` variable right by the specified amount and assign the result to the variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#15](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/right-shift-assignment-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="99bc8-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="99bc8-126">See Also</span></span>  
 [<span data-ttu-id="99bc8-127">>> 연산자</span><span class="sxs-lookup"><span data-stu-id="99bc8-127">>> Operator</span></span>](../../../visual-basic/language-reference/operators/right-shift-operator.md)  
 [<span data-ttu-id="99bc8-128">할당 연산자</span><span class="sxs-lookup"><span data-stu-id="99bc8-128">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [<span data-ttu-id="99bc8-129">비트 시프트 연산자</span><span class="sxs-lookup"><span data-stu-id="99bc8-129">Bit Shift Operators</span></span>](../../../visual-basic/language-reference/operators/bit-shift-operators.md)  
 [<span data-ttu-id="99bc8-130">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="99bc8-130">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="99bc8-131">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="99bc8-131">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="99bc8-132">문</span><span class="sxs-lookup"><span data-stu-id="99bc8-132">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
