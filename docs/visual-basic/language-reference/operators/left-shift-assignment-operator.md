---
title: '&lt;&lt;= 연산자 (Visual Basic)'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.<<=
helpviewer_keywords:
- operator <<=
- assignment statements [Visual Basic], compound
- <<= operator [Visual Basic]
- statements [Visual Basic], compound assignment
- operator<<=
- compound assignment statements [Visual Basic]
ms.assetid: 8ad26613-faff-4e2f-89ee-63feee33bfda
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5c5c36e4f91155c09d01b448777483941d018d9a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltlt-operator-visual-basic"></a><span data-ttu-id="0e66a-102">&lt;&lt;= 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0e66a-102">&lt;&lt;= Operator (Visual Basic)</span></span>
<span data-ttu-id="0e66a-103">변수 또는 속성의 값에 산술 왼쪽된 시프트를 수행 하 고 변수 또는 속성에 다시 결과 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e66a-103">Performs an arithmetic left shift on the value of a variable or property and assigns the result back to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e66a-104">구문</span><span class="sxs-lookup"><span data-stu-id="0e66a-104">Syntax</span></span>  
  
```  
variableorproperty <<= amount  
```  
  
## <a name="parts"></a><span data-ttu-id="0e66a-105">요소</span><span class="sxs-lookup"><span data-stu-id="0e66a-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="0e66a-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="0e66a-106">Required.</span></span> <span data-ttu-id="0e66a-107">변수 또는 정수 계열 형식의 속성 (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, 또는 `ULong`).</span><span class="sxs-lookup"><span data-stu-id="0e66a-107">Variable or property of an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="0e66a-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="0e66a-108">Required.</span></span> <span data-ttu-id="0e66a-109">숫자 식으로 확대 되는 데이터 형식의 `Integer`합니다.</span><span class="sxs-lookup"><span data-stu-id="0e66a-109">Numeric expression of a data type that widens to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0e66a-110">설명</span><span class="sxs-lookup"><span data-stu-id="0e66a-110">Remarks</span></span>  
 <span data-ttu-id="0e66a-111">왼쪽에 요소는 `<<=` 연산자는 간단한 스칼라 변수, 속성 또는 배열의 요소 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e66a-111">The element on the left side of the `<<=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="0e66a-112">변수 또는 속성 수 없습니다 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0e66a-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="0e66a-113">`<<=` 연산자 먼저 변수 또는 속성의 값에 산술 왼쪽된 시프트를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e66a-113">The `<<=` operator first performs an arithmetic left shift on the value of the variable or property.</span></span> <span data-ttu-id="0e66a-114">연산자는 다음 다시 해당 변수 또는 속성에 해당 작업의 결과 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e66a-114">The operator then assigns the result of that operation back to that variable or property.</span></span>  
  
 <span data-ttu-id="0e66a-115">이동 하는 산술 형식 이므로 하지 순환, 결과의 한쪽 끝에서 이동 하는 비트는 다른 쪽 끝에서 다시 도입 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0e66a-115">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="0e66a-116">산술 왼쪽 시프트 연산 결과 데이터 형식의 범위를 넘어 이동 하는 비트는 무시 되 고 오른쪽에 비워진 비트 위치 0으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e66a-116">In an arithmetic left shift, the bits shifted beyond the range of the result data type are discarded, and the bit positions vacated on the right are set to zero.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="0e66a-117">오버로딩</span><span class="sxs-lookup"><span data-stu-id="0e66a-117">Overloading</span></span>  
 <span data-ttu-id="0e66a-118">[<< 연산자](../../../visual-basic/language-reference/operators/left-shift-operator.md) 수 *오버 로드 된*, 클래스 또는 구조체 수 할의 동작에 해당 클래스 또는 구조체의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="0e66a-118">The [<< Operator](../../../visual-basic/language-reference/operators/left-shift-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="0e66a-119">오버 로드는 `<<` 연산자의 동작에 영향을 줍니다는 `<<=` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="0e66a-119">Overloading the `<<` operator affects the behavior of the `<<=` operator.</span></span> <span data-ttu-id="0e66a-120">코드에서 `<<=` 클래스 또는 구조체에 오버 로드에서 `<<`, 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e66a-120">If your code uses `<<=` on a class or structure that overloads `<<`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="0e66a-121">자세한 내용은 참조 [연산자 프로시저](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0e66a-121">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0e66a-122">예제</span><span class="sxs-lookup"><span data-stu-id="0e66a-122">Example</span></span>  
 <span data-ttu-id="0e66a-123">다음 예제에서는 `<<=` 연산자의 비트 패턴을 이동할는 `Integer` 변수에 변수 만큼 왼쪽으로 지정 된 크기 및 결과 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e66a-123">The following example uses the `<<=` operator to shift the bit pattern of an `Integer` variable left by the specified amount and assign the result to the variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#13](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/left-shift-assignment-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="0e66a-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0e66a-124">See Also</span></span>  
 [<span data-ttu-id="0e66a-125"><< 연산자</span><span class="sxs-lookup"><span data-stu-id="0e66a-125"><< Operator</span></span>](../../../visual-basic/language-reference/operators/left-shift-operator.md)  
 [<span data-ttu-id="0e66a-126">할당 연산자</span><span class="sxs-lookup"><span data-stu-id="0e66a-126">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [<span data-ttu-id="0e66a-127">비트 시프트 연산자</span><span class="sxs-lookup"><span data-stu-id="0e66a-127">Bit Shift Operators</span></span>](../../../visual-basic/language-reference/operators/bit-shift-operators.md)  
 [<span data-ttu-id="0e66a-128">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="0e66a-128">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="0e66a-129">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="0e66a-129">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="0e66a-130">문</span><span class="sxs-lookup"><span data-stu-id="0e66a-130">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
