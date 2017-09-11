---
title: "방법: 두 개체가 (Visual Basic)와 동일한 지 확인 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- testing, objects
- objects [Visual Basic], comparing
- object variables, determining identity
ms.assetid: 7829f817-0d1f-4749-a707-de0b95e0cf5c
caps.latest.revision: 19
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
ms.openlocfilehash: c9621412eb1429ed07d8861114a67a67b6c1d58c
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-determine-whether-two-objects-are-identical-visual-basic"></a><span data-ttu-id="2bc16-102">방법: 두 개체가 동일한지 확인(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2bc16-102">How to: Determine Whether Two Objects Are Identical (Visual Basic)</span></span>
<span data-ttu-id="2bc16-103">[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], 두 변수가 메모리의 동일한 클래스 인스턴스를 가리키는 두 개의 변수 참조의 포인터가 동일한 경우, 즉, 같다고 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2bc16-103">In [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], two variable references are considered identical if their pointers are the same, that is, if both variables point to the same class instance in memory.</span></span> <span data-ttu-id="2bc16-104">예를 들어 Windows Forms 응용 프로그램에서는 수 원하는 확인 하려면 비교를 위해 있는지 여부를 현재 인스턴스 (`Me`)와 같습니다 특정 인스턴스를 같은 `Form2`.</span><span class="sxs-lookup"><span data-stu-id="2bc16-104">For example, in a Windows Forms application, you might want to make a comparison to determine whether the current instance (`Me`) is the same as a particular instance, such as `Form2`.</span></span>  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="2bc16-105">포인터를 비교할 두 연산자를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2bc16-105"> provides two operators to compare pointers.</span></span> <span data-ttu-id="2bc16-106">[Is 연산자](../../../../visual-basic/language-reference/operators/is-operator.md) 반환 `True` 개체가 동일 하면 및 [IsNot 연산자](../../../../visual-basic/language-reference/operators/isnot-operator.md) 반환 `True` 없는 경우.</span><span class="sxs-lookup"><span data-stu-id="2bc16-106">The [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) returns `True` if the objects are identical, and the [IsNot Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md) returns `True` if they are not.</span></span>  
  
## <a name="determining-if-two-objects-are-identical"></a><span data-ttu-id="2bc16-107">두 개체가 동일한 지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2bc16-107">Determining if Two Objects Are Identical</span></span>  
  
#### <a name="to-determine-if-two-objects-are-identical"></a><span data-ttu-id="2bc16-108">두 개체가 동일한 지 확인 하려면</span><span class="sxs-lookup"><span data-stu-id="2bc16-108">To determine if two objects are identical</span></span>  
  
1.  <span data-ttu-id="2bc16-109">설정 된 `Boolean` 테스트할 두 개체 식입니다.</span><span class="sxs-lookup"><span data-stu-id="2bc16-109">Set up a `Boolean` expression to test the two objects.</span></span>  
  
2.  <span data-ttu-id="2bc16-110">테스트 식에서 사용 하 여는 `Is` 연산자와 피연산자로 두 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="2bc16-110">In your testing expression, use the `Is` operator with the two objects as operands.</span></span>  
  
     <span data-ttu-id="2bc16-111">`Is`반환 `True` 는 개체가 동일한 클래스 인스턴스를 가리킬 경우.</span><span class="sxs-lookup"><span data-stu-id="2bc16-111">`Is` returns `True` if the objects point to the same class instance.</span></span>  
  
## <a name="determining-if-two-objects-are-not-identical"></a><span data-ttu-id="2bc16-112">두 개체가 동일한 지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2bc16-112">Determining if Two Objects Are Not Identical</span></span>  
 <span data-ttu-id="2bc16-113">두 개체가 동일 하 고 결합 하기에 불편할 수 작업을 수행 하려는 경우가 `Not` 및 `Is`, 예를 들어 `If Not obj1 Is obj2`합니다.</span><span class="sxs-lookup"><span data-stu-id="2bc16-113">Sometimes you want to perform an action if the two objects are not identical, and it can be awkward to combine `Not` and `Is`, for example `If Not obj1 Is obj2`.</span></span> <span data-ttu-id="2bc16-114">사용할 수 있는 경우에는 `IsNot` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="2bc16-114">In such a case you can use the `IsNot` operator.</span></span>  
  
#### <a name="to-determine-if-two-objects-are-not-identical"></a><span data-ttu-id="2bc16-115">두 개체가 동일한 지 확인 하려면</span><span class="sxs-lookup"><span data-stu-id="2bc16-115">To determine if two objects are not identical</span></span>  
  
1.  <span data-ttu-id="2bc16-116">설정 된 `Boolean` 테스트할 두 개체 식입니다.</span><span class="sxs-lookup"><span data-stu-id="2bc16-116">Set up a `Boolean` expression to test the two objects.</span></span>  
  
2.  <span data-ttu-id="2bc16-117">테스트 식에서 사용 하 여는 `IsNot` 연산자와 피연산자로 두 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="2bc16-117">In your testing expression, use the `IsNot` operator with the two objects as operands.</span></span>  
  
     <span data-ttu-id="2bc16-118">`IsNot`반환 `True` 개체가 동일한 클래스 인스턴스를 가리키지 않을 경우.</span><span class="sxs-lookup"><span data-stu-id="2bc16-118">`IsNot` returns `True` if the objects do not point to the same class instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2bc16-119">예제</span><span class="sxs-lookup"><span data-stu-id="2bc16-119">Example</span></span>  
 <span data-ttu-id="2bc16-120">다음 예에서는 쌍을 테스트 `Object` 변수를 동일한 클래스 인스턴스를 가리키는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2bc16-120">The following example tests pairs of `Object` variables to see if they point to the same class instance.</span></span>  
  
 <span data-ttu-id="2bc16-121">[!code-vb[VbVbalrKeywords #&14;](../../../../visual-basic/language-reference/codesnippet/VisualBasic/how-to-determine-whether-two-objects-are-identical_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="2bc16-121">[!code-vb[VbVbalrKeywords#14](../../../../visual-basic/language-reference/codesnippet/VisualBasic/how-to-determine-whether-two-objects-are-identical_1.vb)]</span></span>  
  
 <span data-ttu-id="2bc16-122">앞의 예제는 다음과 같은 출력을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="2bc16-122">The preceding example displays the following output.</span></span>  
  
 `objA different from objB? True`  
  
 `objA identical to objC? True`  
  
## <a name="see-also"></a><span data-ttu-id="2bc16-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2bc16-123">See Also</span></span>  
 <span data-ttu-id="2bc16-124">[Object 데이터 형식](../../../../visual-basic/language-reference/data-types/object-data-type.md) </span><span class="sxs-lookup"><span data-stu-id="2bc16-124">[Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) </span></span>  
<span data-ttu-id="2bc16-125"> [개체 변수](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md) </span><span class="sxs-lookup"><span data-stu-id="2bc16-125"> [Object Variables](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md) </span></span>  
<span data-ttu-id="2bc16-126"> [개체 변수 값](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md) </span><span class="sxs-lookup"><span data-stu-id="2bc16-126"> [Object Variable Values](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md) </span></span>  
<span data-ttu-id="2bc16-127"> [Is 연산자](../../../../visual-basic/language-reference/operators/is-operator.md) </span><span class="sxs-lookup"><span data-stu-id="2bc16-127"> [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) </span></span>  
<span data-ttu-id="2bc16-128"> [IsNot 연산자](../../../../visual-basic/language-reference/operators/isnot-operator.md) </span><span class="sxs-lookup"><span data-stu-id="2bc16-128"> [IsNot Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md) </span></span>  
<span data-ttu-id="2bc16-129"> [방법: 두 개체가 관련이 있는지 확인](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md) </span><span class="sxs-lookup"><span data-stu-id="2bc16-129"> [How to: Determine Whether Two Objects Are Related](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md) </span></span>  
<span data-ttu-id="2bc16-130"> [Me, My, MyBase 및 MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)</span><span class="sxs-lookup"><span data-stu-id="2bc16-130"> [Me, My, MyBase, and MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)</span></span>
