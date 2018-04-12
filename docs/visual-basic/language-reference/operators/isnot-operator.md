---
title: IsNot 연산자(Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.isnot
helpviewer_keywords:
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 969fdebdf15a1f779075c58616ccd16c64976a35
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="isnot-operator-visual-basic"></a><span data-ttu-id="8d03e-102">IsNot 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8d03e-102">IsNot Operator (Visual Basic)</span></span>
<span data-ttu-id="8d03e-103">두 개체 참조 변수를 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="8d03e-103">Compares two object reference variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d03e-104">구문</span><span class="sxs-lookup"><span data-stu-id="8d03e-104">Syntax</span></span>  
  
```  
result = object1 IsNot object2  
```  
  
## <a name="parts"></a><span data-ttu-id="8d03e-105">요소</span><span class="sxs-lookup"><span data-stu-id="8d03e-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="8d03e-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="8d03e-106">Required.</span></span> <span data-ttu-id="8d03e-107">`Boolean` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8d03e-107">A `Boolean` value.</span></span>  
  
 `object1`  
 <span data-ttu-id="8d03e-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="8d03e-108">Required.</span></span> <span data-ttu-id="8d03e-109">모든 `Object` 변수 또는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="8d03e-109">Any `Object` variable or expression.</span></span>  
  
 `object2`  
 <span data-ttu-id="8d03e-110">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="8d03e-110">Required.</span></span> <span data-ttu-id="8d03e-111">모든 `Object` 변수 또는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="8d03e-111">Any `Object` variable or expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8d03e-112">설명</span><span class="sxs-lookup"><span data-stu-id="8d03e-112">Remarks</span></span>  
 <span data-ttu-id="8d03e-113">`IsNot` 연산자 두 개체 참조가 서로 다른 개체 참조 하는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d03e-113">The `IsNot` operator determines if two object references refer to different objects.</span></span> <span data-ttu-id="8d03e-114">그러나 값 비교를 수행 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8d03e-114">However, it does not perform value comparisons.</span></span> <span data-ttu-id="8d03e-115">경우 `object1` 및 `object2` 정확히 동일한 개체 인스턴스를 둘 다 참조 `result` 은 `False`그렇지 않은 경우 `result` 은 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="8d03e-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `False`; if they do not, `result` is `True`.</span></span>  
  
 <span data-ttu-id="8d03e-116">`IsNot`반대 되는 `Is` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="8d03e-116">`IsNot` is the opposite of the `Is` operator.</span></span> <span data-ttu-id="8d03e-117">이점은 `IsNot` 는 것을 피할 수 있는 복잡 한 구문이 `Not` 및 `Is`를 읽기 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d03e-117">The advantage of `IsNot` is that you can avoid awkward syntax with `Not` and `Is`, which can be difficult to read.</span></span>  
  
 <span data-ttu-id="8d03e-118">사용할 수는 `Is` 및 `IsNot` 모두 초기 바인딩 및 런타임에 바인딩된 개체를 테스트 하는 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="8d03e-118">You can use the `Is` and `IsNot` operators to test both early-bound and late-bound objects.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8d03e-119">`IsNot` 식에서 반환 된 비교 연산자를 사용할 수 없습니다는 `TypeOf` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="8d03e-119">The `IsNot` operator cannot be used to compare expressions returned from the `TypeOf` operator.</span></span> <span data-ttu-id="8d03e-120">를 대신 사용 해야는 `Not` 및 `Is` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="8d03e-120">Instead, you must use the `Not` and `Is` operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8d03e-121">예제</span><span class="sxs-lookup"><span data-stu-id="8d03e-121">Example</span></span>  
 <span data-ttu-id="8d03e-122">다음 코드 예제에서는 모두를 사용 하는 `Is` 연산자 및 `IsNot` 연산자 동일한 비교를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d03e-122">The following code example uses both the `Is` operator and the `IsNot` operator to accomplish the same comparison.</span></span>  
  
 [!code-vb[VbVbalrOperators#29](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/isnot-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="8d03e-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8d03e-123">See Also</span></span>  
 [<span data-ttu-id="8d03e-124">Is 연산자</span><span class="sxs-lookup"><span data-stu-id="8d03e-124">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)  
 [<span data-ttu-id="8d03e-125">TypeOf 연산자</span><span class="sxs-lookup"><span data-stu-id="8d03e-125">TypeOf Operator</span></span>](../../../visual-basic/language-reference/operators/typeof-operator.md)  
 [<span data-ttu-id="8d03e-126">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="8d03e-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="8d03e-127">방법: 두 개체가 동일한지 테스트</span><span class="sxs-lookup"><span data-stu-id="8d03e-127">How to: Test Whether Two Objects Are the Same</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
