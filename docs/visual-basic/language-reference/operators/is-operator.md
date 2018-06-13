---
title: Is 연산자(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.is
helpviewer_keywords:
- comparison operators [Visual Basic]
- equivalent objects
- TypeOf...Is expression
- Is operator [Visual Basic]
ms.assetid: 8045a6c8-2a83-45b6-ad47-d09a704c656d
ms.openlocfilehash: 8beca1dc8788514224f70cacc5b8ede0974f5230
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33601952"
---
# <a name="is-operator-visual-basic"></a><span data-ttu-id="461ab-102">Is 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="461ab-102">Is Operator (Visual Basic)</span></span>
<span data-ttu-id="461ab-103">두 개체 참조 변수를 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="461ab-103">Compares two object reference variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="461ab-104">구문</span><span class="sxs-lookup"><span data-stu-id="461ab-104">Syntax</span></span>  
  
```  
result = object1 Is object2  
```  
  
## <a name="parts"></a><span data-ttu-id="461ab-105">요소</span><span class="sxs-lookup"><span data-stu-id="461ab-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="461ab-106">필수.</span><span class="sxs-lookup"><span data-stu-id="461ab-106">Required.</span></span> <span data-ttu-id="461ab-107">모든 `Boolean` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="461ab-107">Any `Boolean` value.</span></span>  
  
 `object1`  
 <span data-ttu-id="461ab-108">필수.</span><span class="sxs-lookup"><span data-stu-id="461ab-108">Required.</span></span> <span data-ttu-id="461ab-109">모든 `Object` 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="461ab-109">Any `Object` name.</span></span>  
  
 `object2`  
 <span data-ttu-id="461ab-110">필수.</span><span class="sxs-lookup"><span data-stu-id="461ab-110">Required.</span></span> <span data-ttu-id="461ab-111">모든 `Object` 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="461ab-111">Any `Object` name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="461ab-112">설명</span><span class="sxs-lookup"><span data-stu-id="461ab-112">Remarks</span></span>  
 <span data-ttu-id="461ab-113">`Is` 연산자 두 개체 참조가 동일한 개체를 참조 하는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="461ab-113">The `Is` operator determines if two object references refer to the same object.</span></span> <span data-ttu-id="461ab-114">그러나 값 비교를 수행 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="461ab-114">However, it does not perform value comparisons.</span></span> <span data-ttu-id="461ab-115">경우 `object1` 및 `object2` 정확히 동일한 개체 인스턴스를 둘 다 참조 `result` 은 `True`그렇지 않은 경우 `result` 은 `False`합니다.</span><span class="sxs-lookup"><span data-stu-id="461ab-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `True`; if they do not, `result` is `False`.</span></span>  
  
 <span data-ttu-id="461ab-116">`Is` 함께 사용할 수도 `TypeOf` 있도록 키워드는 `TypeOf`... `Is` 개체 변수 데이터 형식과 호환 되는지 여부를 테스트 하는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="461ab-116">`Is` can also be used with the `TypeOf` keyword to make a `TypeOf`...`Is` expression, which tests whether an object variable is compatible with a data type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="461ab-117">`Is` 키워드는 또한는 [선택... Case 문](../../../visual-basic/language-reference/statements/select-case-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="461ab-117">The `Is` keyword is also used in the [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="461ab-118">예제</span><span class="sxs-lookup"><span data-stu-id="461ab-118">Example</span></span>  
 <span data-ttu-id="461ab-119">다음 예제에서는 `Is` 개체 참조의 쌍을 비교 연산자.</span><span class="sxs-lookup"><span data-stu-id="461ab-119">The following example uses the `Is` operator to compare pairs of object references.</span></span> <span data-ttu-id="461ab-120">결과에 할당 되는 `Boolean` 두 개체가 동일한 지 여부를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="461ab-120">The results are assigned to a `Boolean` value representing whether the two objects are identical.</span></span>  
  
 [!code-vb[VbVbalrOperators#27](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/is-operator_1.vb)]  
  
 <span data-ttu-id="461ab-121">사용할 수 있습니다 앞의 예제에서 보여 주듯이는 `Is` 모두 테스트할 연산자 초기 바인딩 및 런타임에 바인딩된 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="461ab-121">As the preceding example demonstrates, you can use the `Is` operator to test both early bound and late bound objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="461ab-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="461ab-122">See Also</span></span>  
 [<span data-ttu-id="461ab-123">TypeOf 연산자</span><span class="sxs-lookup"><span data-stu-id="461ab-123">TypeOf Operator</span></span>](../../../visual-basic/language-reference/operators/typeof-operator.md)  
 [<span data-ttu-id="461ab-124">IsNot 연산자</span><span class="sxs-lookup"><span data-stu-id="461ab-124">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)  
 [<span data-ttu-id="461ab-125">Visual Basic의 비교 연산자</span><span class="sxs-lookup"><span data-stu-id="461ab-125">Comparison Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [<span data-ttu-id="461ab-126">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="461ab-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="461ab-127">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="461ab-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="461ab-128">연산자 및 식</span><span class="sxs-lookup"><span data-stu-id="461ab-128">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
