---
title: '방법: Visual Basic에서 프로시저에 다른 프로시저 전달'
ms.date: 07/20/2015
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- delegates [Visual Basic], passing procedures
ms.assetid: 5adbba15-5a1d-413f-ab3e-3ff6cc0a4669
ms.openlocfilehash: c28ac7a640ec863b37bd7407d0273a1918964ac4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647240"
---
# <a name="how-to-pass-procedures-to-another-procedure-in-visual-basic"></a><span data-ttu-id="1839f-102">방법: Visual Basic에서 프로시저에 다른 프로시저 전달</span><span class="sxs-lookup"><span data-stu-id="1839f-102">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>
<span data-ttu-id="1839f-103">이 예제에서는 대리자를 사용 하는 프로시저를 다른 프로시저에 전달 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1839f-103">This example shows how to use delegates to pass a procedure to another procedure.</span></span>  
  
 <span data-ttu-id="1839f-104">대리자 형식이 Visual Basic에서 다른 형식 처럼 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1839f-104">A delegate is a type that you can use like any other type in Visual Basic.</span></span> <span data-ttu-id="1839f-105">`AddressOf` 연산자 프로시저 이름에 적용 될 때 대리자 개체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1839f-105">The `AddressOf` operator returns a delegate object when applied to a procedure name.</span></span>  
  
 <span data-ttu-id="1839f-106">이 예제에 다른 프로시저를 사용 하 여 얻은에 대 한 참조를 사용할 수 있는 대리자 매개 변수가 있는 프로시저는 `AddressOf` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="1839f-106">This example has a procedure with a delegate parameter that can take a reference to another procedure, obtained with the `AddressOf` operator.</span></span>  
  
### <a name="create-the-delegate-and-matching-procedures"></a><span data-ttu-id="1839f-107">대리자와 일치 하는 프로시저 만들기</span><span class="sxs-lookup"><span data-stu-id="1839f-107">Create the delegate and matching procedures</span></span>  
  
1.  <span data-ttu-id="1839f-108">라는 대리자를 만들 `MathOperator`합니다.</span><span class="sxs-lookup"><span data-stu-id="1839f-108">Create a delegate named `MathOperator`.</span></span>  
  
     [!code-vb[VbVbalrDelegates#1](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_1.vb)]  
  
2.  <span data-ttu-id="1839f-109">라는 프로시저를 만들어 `AddNumbers` 매개 변수와 일치 하는 반환 값 `MathOperator`서명이 일치 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1839f-109">Create a procedure named `AddNumbers` with parameters and return value that match those of `MathOperator`, so that the signatures match.</span></span>  
  
     [!code-vb[VbVbalrDelegates#2](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_2.vb)]  
  
3.  <span data-ttu-id="1839f-110">라는 프로시저를 만들어 `SubtractNumbers` 일치 하는 서명이 `MathOperator`합니다.</span><span class="sxs-lookup"><span data-stu-id="1839f-110">Create a procedure named `SubtractNumbers` with a signature that matches `MathOperator`.</span></span>  
  
     [!code-vb[VbVbalrDelegates#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_3.vb)]  
  
4.  <span data-ttu-id="1839f-111">라는 프로시저를 만들어 `DelegateTest` 대리자를 매개 변수로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1839f-111">Create a procedure named `DelegateTest` that takes a delegate as a parameter.</span></span>  
  
     <span data-ttu-id="1839f-112">이 절차에 대 한 참조를 허용할 수 `AddNumbers` 또는 `SubtractNumbers`에서는는 `MathOperator` 서명 합니다.</span><span class="sxs-lookup"><span data-stu-id="1839f-112">This procedure can accept a reference to `AddNumbers` or `SubtractNumbers`, because their signatures match the `MathOperator` signature.</span></span>  
  
     [!code-vb[VbVbalrDelegates#4](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_4.vb)]  
  
5.  <span data-ttu-id="1839f-113">라는 프로시저를 만들어 `Test` 를 호출 하 `DelegateTest` 한 번에 대 한 대리자와 `AddNumbers` 을 매개 변수로 사용 하 고 다시에 대 한 대리자와 `SubtractNumbers` 매개 변수로 합니다.</span><span class="sxs-lookup"><span data-stu-id="1839f-113">Create a procedure named `Test` that calls `DelegateTest` once with the delegate for `AddNumbers` as a parameter, and again with the delegate for `SubtractNumbers` as a parameter.</span></span>  
  
     [!code-vb[VbVbalrDelegates#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_5.vb)]  
  
     <span data-ttu-id="1839f-114">때 `Test` 은 호출 먼저 표시의 결과 `AddNumbers` 실행 `5` 및 `3`, 하는 8입니다.</span><span class="sxs-lookup"><span data-stu-id="1839f-114">When `Test` is called, it first displays the result of `AddNumbers` acting on `5` and `3`, which is 8.</span></span> <span data-ttu-id="1839f-115">결과 `SubtractNumbers` 작업할 `9` 및 `3` 표시 되 면 6이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1839f-115">Then the result of `SubtractNumbers` acting on `9` and `3` is displayed, which is 6.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1839f-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1839f-116">See Also</span></span>  
 [<span data-ttu-id="1839f-117">대리자</span><span class="sxs-lookup"><span data-stu-id="1839f-117">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [<span data-ttu-id="1839f-118">AddressOf 연산자</span><span class="sxs-lookup"><span data-stu-id="1839f-118">AddressOf Operator</span></span>](../../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [<span data-ttu-id="1839f-119">Delegate 문</span><span class="sxs-lookup"><span data-stu-id="1839f-119">Delegate Statement</span></span>](../../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [<span data-ttu-id="1839f-120">방법: 대리자 메서드 호출</span><span class="sxs-lookup"><span data-stu-id="1839f-120">How to: Invoke a Delegate Method</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
