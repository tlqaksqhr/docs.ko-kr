---
title: '&amp; 연산자 (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.&
helpviewer_keywords:
- And (&) operator
- ampersand operator (&)
- '& operator'
- concatenation operators [Visual Basic], syntax
- strings [Visual Basic], concatenating
ms.assetid: fefc3d00-cbf1-475c-8c5e-6fb213b3f85a
ms.openlocfilehash: 28d8cdb22974d77edf055ab9b2c6c767872e6783
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604304"
---
# <a name="amp-operator-visual-basic"></a><span data-ttu-id="524d3-102">&amp; 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="524d3-102">&amp; Operator (Visual Basic)</span></span>
<span data-ttu-id="524d3-103">두 식의 문자열 연결을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="524d3-103">Generates a string concatenation of two expressions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="524d3-104">구문</span><span class="sxs-lookup"><span data-stu-id="524d3-104">Syntax</span></span>  
  
```  
result = expression1 & expression2  
```  
  
## <a name="parts"></a><span data-ttu-id="524d3-105">요소</span><span class="sxs-lookup"><span data-stu-id="524d3-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="524d3-106">필수.</span><span class="sxs-lookup"><span data-stu-id="524d3-106">Required.</span></span> <span data-ttu-id="524d3-107">모든 `String` 또는 `Object` 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="524d3-107">Any `String` or `Object` variable.</span></span>  
  
 `expression1`  
 <span data-ttu-id="524d3-108">필수.</span><span class="sxs-lookup"><span data-stu-id="524d3-108">Required.</span></span> <span data-ttu-id="524d3-109">모든 식으로 확장 되는 데이터 형식과 `String`합니다.</span><span class="sxs-lookup"><span data-stu-id="524d3-109">Any expression with a data type that widens to `String`.</span></span>  
  
 `expression2`  
 <span data-ttu-id="524d3-110">필수.</span><span class="sxs-lookup"><span data-stu-id="524d3-110">Required.</span></span> <span data-ttu-id="524d3-111">모든 식으로 확장 되는 데이터 형식과 `String`합니다.</span><span class="sxs-lookup"><span data-stu-id="524d3-111">Any expression with a data type that widens to `String`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="524d3-112">설명</span><span class="sxs-lookup"><span data-stu-id="524d3-112">Remarks</span></span>  
 <span data-ttu-id="524d3-113">데이터 형식이 `expression1` 또는 `expression2` 않습니다 `String` 로 확대 하지만 `String`로 변환 됩니다 `String`합니다.</span><span class="sxs-lookup"><span data-stu-id="524d3-113">If the data type of `expression1` or `expression2` is not `String` but widens to `String`, it is converted to `String`.</span></span> <span data-ttu-id="524d3-114">하는 경우 데이터 형식 중 하나가 확대 변환 되지 않으면에 `String`, 컴파일러에 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="524d3-114">If either of the data types does not widen to `String`, the compiler generates an error.</span></span>  
  
 <span data-ttu-id="524d3-115">데이터 형식이 `result` 은 `String`합니다.</span><span class="sxs-lookup"><span data-stu-id="524d3-115">The data type of `result` is `String`.</span></span> <span data-ttu-id="524d3-116">하나 또는 두 식의 계산 하는 경우 [Nothing](../../../visual-basic/language-reference/nothing.md) 의 값이 있는 <xref:System.DBNull.Value?displayProperty=nameWithType>, 처리 되는 값이 문자열 ""입니다.</span><span class="sxs-lookup"><span data-stu-id="524d3-116">If one or both expressions evaluate to [Nothing](../../../visual-basic/language-reference/nothing.md) or have a value of <xref:System.DBNull.Value?displayProperty=nameWithType>, they are treated as a string with a value of "".</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="524d3-117">`&` 연산자 될 수 있습니다 *오버 로드 된*, 클래스 또는 구조체 수 할의 동작에 해당 클래스 또는 구조체의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="524d3-117">The `&` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="524d3-118">이 연산자를 사용 하 여 이러한 클래스나 구조체에는 코드를 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="524d3-118">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="524d3-119">자세한 내용은 참조 [연산자 프로시저](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="524d3-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="524d3-120">앰퍼샌드 (&) 문자 사용할 수도 있습니다 형식으로 변수를 식별 하 `Long`합니다.</span><span class="sxs-lookup"><span data-stu-id="524d3-120">The ampersand (&) character can also be used to identify variables as type `Long`.</span></span> <span data-ttu-id="524d3-121">자세한 내용은 참조 [형식 문자](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="524d3-121">For more information, see [Type Characters](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="524d3-122">예제</span><span class="sxs-lookup"><span data-stu-id="524d3-122">Example</span></span>  
 <span data-ttu-id="524d3-123">사용 하 여이 예제는 `&` 문자열을 연결 하는 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="524d3-123">This example uses the `&` operator to force string concatenation.</span></span> <span data-ttu-id="524d3-124">결과 두 문자열 피연산자의 연결을 나타내는 문자열 값입니다.</span><span class="sxs-lookup"><span data-stu-id="524d3-124">The result is a string value representing the concatenation of the two string operands.</span></span>  
  
 [!code-vb[VbVbalrOperators#2](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/concatenation-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="524d3-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="524d3-125">See Also</span></span>  
 [<span data-ttu-id="524d3-126">&= 연산자</span><span class="sxs-lookup"><span data-stu-id="524d3-126">&= Operator</span></span>](../../../visual-basic/language-reference/operators/and-assignment-operator.md)  
 [<span data-ttu-id="524d3-127">연결 연산자</span><span class="sxs-lookup"><span data-stu-id="524d3-127">Concatenation Operators</span></span>](../../../visual-basic/language-reference/operators/concatenation-operators.md)  
 [<span data-ttu-id="524d3-128">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="524d3-128">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="524d3-129">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="524d3-129">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="524d3-130">Visual Basic의 연결 연산자</span><span class="sxs-lookup"><span data-stu-id="524d3-130">Concatenation Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
