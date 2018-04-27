---
title: '방법: 두 개체가 동일한지 확인(Visual Basic)'
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- testing [Visual Basic], objects
- objects [Visual Basic], comparing
- object variables [Visual Basic], determining identity
ms.assetid: 7829f817-0d1f-4749-a707-de0b95e0cf5c
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 266e878e7f5fa8deb1c8cd91795af8d63ded0177
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-determine-whether-two-objects-are-identical-visual-basic"></a><span data-ttu-id="ef4d6-102">방법: 두 개체가 동일한지 확인(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ef4d6-102">How to: Determine Whether Two Objects Are Identical (Visual Basic)</span></span>
<span data-ttu-id="ef4d6-103">Visual Basic에서는 두 변수는 메모리의 동일한 클래스 인스턴스를 가리킬 경우에 두 개의 변수 참조를의 포인터가 동일한 경우, 즉, 같다고 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef4d6-103">In Visual Basic, two variable references are considered identical if their pointers are the same, that is, if both variables point to the same class instance in memory.</span></span> <span data-ttu-id="ef4d6-104">예를 들어 Windows Forms 응용 프로그램에서는 수 원하는 확인 하려면 비교를 위해 있는지 여부를 현재 인스턴스 (`Me`)와 같은 특정 인스턴스와 같은 `Form2`합니다.</span><span class="sxs-lookup"><span data-stu-id="ef4d6-104">For example, in a Windows Forms application, you might want to make a comparison to determine whether the current instance (`Me`) is the same as a particular instance, such as `Form2`.</span></span>  
  
 <span data-ttu-id="ef4d6-105">Visual Basic 포인터를 비교 하려면 두 연산자를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef4d6-105">Visual Basic provides two operators to compare pointers.</span></span> <span data-ttu-id="ef4d6-106">[Is 연산자](../../../../visual-basic/language-reference/operators/is-operator.md) 반환 `True` 개체가 동일 하면 및 [IsNot 연산자](../../../../visual-basic/language-reference/operators/isnot-operator.md) 반환 `True` 그렇지 않은 경우.</span><span class="sxs-lookup"><span data-stu-id="ef4d6-106">The [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) returns `True` if the objects are identical, and the [IsNot Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md) returns `True` if they are not.</span></span>  
  
## <a name="determining-if-two-objects-are-identical"></a><span data-ttu-id="ef4d6-107">두 개체가 동일한 지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef4d6-107">Determining if Two Objects Are Identical</span></span>  
  
#### <a name="to-determine-if-two-objects-are-identical"></a><span data-ttu-id="ef4d6-108">두 개체가 동일한 지 확인 하려면</span><span class="sxs-lookup"><span data-stu-id="ef4d6-108">To determine if two objects are identical</span></span>  
  
1.  <span data-ttu-id="ef4d6-109">설정 된 `Boolean` 두 개체를 테스트 하는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="ef4d6-109">Set up a `Boolean` expression to test the two objects.</span></span>  
  
2.  <span data-ttu-id="ef4d6-110">테스트 식에서 사용 하 여는 `Is` 연산자 피연산자와 두 개의 개체와 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef4d6-110">In your testing expression, use the `Is` operator with the two objects as operands.</span></span>  
  
     <span data-ttu-id="ef4d6-111">`Is` 반환 `True` 는 개체가 동일한 클래스 인스턴스를 가리킬 경우.</span><span class="sxs-lookup"><span data-stu-id="ef4d6-111">`Is` returns `True` if the objects point to the same class instance.</span></span>  
  
## <a name="determining-if-two-objects-are-not-identical"></a><span data-ttu-id="ef4d6-112">두 개체가 동일 하지 않은지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef4d6-112">Determining if Two Objects Are Not Identical</span></span>  
 <span data-ttu-id="ef4d6-113">두 개체가 동일 하 고 결합 하 좋지 않을 수 있습니다 하는 경우 작업을 수행 하려는 경우에 따라 `Not` 및 `Is`, 예를 들어 `If Not obj1 Is obj2`합니다.</span><span class="sxs-lookup"><span data-stu-id="ef4d6-113">Sometimes you want to perform an action if the two objects are not identical, and it can be awkward to combine `Not` and `Is`, for example `If Not obj1 Is obj2`.</span></span> <span data-ttu-id="ef4d6-114">이러한 경우에 사용할 수 있습니다는 `IsNot` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="ef4d6-114">In such a case you can use the `IsNot` operator.</span></span>  
  
#### <a name="to-determine-if-two-objects-are-not-identical"></a><span data-ttu-id="ef4d6-115">두 개체가 동일한 지 확인 하려면</span><span class="sxs-lookup"><span data-stu-id="ef4d6-115">To determine if two objects are not identical</span></span>  
  
1.  <span data-ttu-id="ef4d6-116">설정 된 `Boolean` 두 개체를 테스트 하는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="ef4d6-116">Set up a `Boolean` expression to test the two objects.</span></span>  
  
2.  <span data-ttu-id="ef4d6-117">테스트 식에서 사용 하 여는 `IsNot` 연산자 피연산자와 두 개의 개체와 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef4d6-117">In your testing expression, use the `IsNot` operator with the two objects as operands.</span></span>  
  
     <span data-ttu-id="ef4d6-118">`IsNot` 반환 `True` 개체가 동일한 클래스 인스턴스를 가리키지 않을 경우.</span><span class="sxs-lookup"><span data-stu-id="ef4d6-118">`IsNot` returns `True` if the objects do not point to the same class instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ef4d6-119">예제</span><span class="sxs-lookup"><span data-stu-id="ef4d6-119">Example</span></span>  
 <span data-ttu-id="ef4d6-120">다음 예에서는 쌍을 테스트 `Object` 변수를 동일한 클래스 인스턴스를 가리키는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef4d6-120">The following example tests pairs of `Object` variables to see if they point to the same class instance.</span></span>  
  
 [!code-vb[VbVbalrKeywords#14](../../../../visual-basic/language-reference/codesnippet/VisualBasic/how-to-determine-whether-two-objects-are-identical_1.vb)]  
  
 <span data-ttu-id="ef4d6-121">앞의 예제는 다음과 같은 출력을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef4d6-121">The preceding example displays the following output.</span></span>  
  
 `objA different from objB? True`  
  
 `objA identical to objC? True`  
  
## <a name="see-also"></a><span data-ttu-id="ef4d6-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ef4d6-122">See Also</span></span>  
 [<span data-ttu-id="ef4d6-123">Object 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="ef4d6-123">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [<span data-ttu-id="ef4d6-124">개체 변수</span><span class="sxs-lookup"><span data-stu-id="ef4d6-124">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [<span data-ttu-id="ef4d6-125">개체 변수 값</span><span class="sxs-lookup"><span data-stu-id="ef4d6-125">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)  
 [<span data-ttu-id="ef4d6-126">Is 연산자</span><span class="sxs-lookup"><span data-stu-id="ef4d6-126">Is Operator</span></span>](../../../../visual-basic/language-reference/operators/is-operator.md)  
 [<span data-ttu-id="ef4d6-127">IsNot 연산자</span><span class="sxs-lookup"><span data-stu-id="ef4d6-127">IsNot Operator</span></span>](../../../../visual-basic/language-reference/operators/isnot-operator.md)  
 [<span data-ttu-id="ef4d6-128">방법: 두 개체가 관련이 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="ef4d6-128">How to: Determine Whether Two Objects Are Related</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)  
 [<span data-ttu-id="ef4d6-129">Me, My, MyBase 및 MyClass</span><span class="sxs-lookup"><span data-stu-id="ef4d6-129">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
