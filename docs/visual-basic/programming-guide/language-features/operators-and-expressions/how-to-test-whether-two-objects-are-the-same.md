---
title: "방법: 두 개체가 동일한지 테스트(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- variables [Visual Basic], reference
- Is operator [Visual Basic], comparing objects
- reference variables [Visual Basic]
- variables [Visual Basic], referring to same object
- objects [Visual Basic], variables referring to same
- Visual Basic code, operators
ms.assetid: f760e828-8704-4256-bc2d-c22a4c93b524
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 76f5c19386cce84207f80d217326d2e3babf4e44
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-test-whether-two-objects-are-the-same-visual-basic"></a><span data-ttu-id="c910a-102">방법: 두 개체가 동일한지 테스트(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c910a-102">How to: Test Whether Two Objects Are the Same (Visual Basic)</span></span>
<span data-ttu-id="c910a-103">개체 참조 하는 두 개의 변수를 설정한 경우 사용할 수 있습니다는 `Is` 또는 `IsNot` 연산자, 또는 둘 다를 동일한 인스턴스를 참조 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c910a-103">If you have two variables that refer to objects, you can use either the `Is` or `IsNot` operator, or both, to determine whether they refer to the same instance.</span></span>  
  
### <a name="to-test-whether-two-objects-are-the-same"></a><span data-ttu-id="c910a-104">두 개체가 동일한 지 여부를 테스트 하려면</span><span class="sxs-lookup"><span data-stu-id="c910a-104">To test whether two objects are the same</span></span>  
  
-   <span data-ttu-id="c910a-105">사용 하 여는 [Is 연산자](../../../../visual-basic/language-reference/operators/is-operator.md) 또는 [IsNot 연산자](../../../../visual-basic/language-reference/operators/isnot-operator.md) 피연산자로 두 변수가 있는 합니다.</span><span class="sxs-lookup"><span data-stu-id="c910a-105">Use the [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) or the [IsNot Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md) with the two variables as operands.</span></span>  
  
     [!code-vb[VbVbalrOperators#69](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-test-whether-two-objects-are-the-same_1.vb)]  
  
 <span data-ttu-id="c910a-106">두 개체가 같은 인스턴스를 참조 하는 여부에 따라 특정 작업을 백업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c910a-106">You might want to take a certain action depending on whether two objects refer to the same instance.</span></span> <span data-ttu-id="c910a-107">앞의 예제 컨트롤 비교 `c` 폼에 있는 활성 컨트롤에 대해 `f`합니다.</span><span class="sxs-lookup"><span data-stu-id="c910a-107">The preceding example compares control `c` against the active control on form `f`.</span></span> <span data-ttu-id="c910a-108">활성 컨트롤이 없는 없거나 없을 경우 하나 하지 않은와 동일한 컨트롤 인스턴스에 `c`, 하면 `If` 추가 처리 하지 않고 문이 실패 하 고 프로시저를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c910a-108">If there is no active control, or if there is one but it is not the same control instance as `c`, then the `If` statement fails and the procedure returns without further processing.</span></span>  
  
 <span data-ttu-id="c910a-109">사용 하 든 `Is` 또는 `IsNot` 은 개인 편의를 위해의 문제입니다.</span><span class="sxs-lookup"><span data-stu-id="c910a-109">Whether you use `Is` or `IsNot` is a matter of personal convenience to you.</span></span> <span data-ttu-id="c910a-110">하나는 지정된 된 식에서 다른 보다 읽기 쉬울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c910a-110">One might be easier to read than the other in a given expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c910a-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c910a-111">See Also</span></span>  
 [<span data-ttu-id="c910a-112">Visual Basic의 비교 연산자</span><span class="sxs-lookup"><span data-stu-id="c910a-112">Comparison Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
