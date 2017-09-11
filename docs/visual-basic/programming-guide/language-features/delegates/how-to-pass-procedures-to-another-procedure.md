---
title: "방법: 프로시저에 Visual Basic에서 다른 프로시저 전달 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- AddressOf operator
- delegates [Visual Basic], passing procedures
ms.assetid: 5adbba15-5a1d-413f-ab3e-3ff6cc0a4669
caps.latest.revision: 9
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
ms.openlocfilehash: 95cbcf836b0dad875851052a367666c00cd54e37
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-pass-procedures-to-another-procedure-in-visual-basic"></a><span data-ttu-id="86285-102">방법: Visual Basic에서 프로시저에 다른 프로시저 전달</span><span class="sxs-lookup"><span data-stu-id="86285-102">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>
<span data-ttu-id="86285-103">이 예제에서는 대리자를 사용 하 여 프로시저에 다른 프로시저 전달 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="86285-103">This example shows how to use delegates to pass a procedure to another procedure.</span></span>  
  
 <span data-ttu-id="86285-104">대리자는 형식에서 다른 형식 처럼 사용할 수 있는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="86285-104">A delegate is a type that you can use like any other type in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span> <span data-ttu-id="86285-105">`AddressOf` 연산자 프로시저 이름에 적용 될 때 대리자 개체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="86285-105">The `AddressOf` operator returns a delegate object when applied to a procedure name.</span></span>  
  
 <span data-ttu-id="86285-106">이 예제에 다른 프로시저를 사용 하 여 얻은에 대 한 참조를 사용할 수 있는 대리자 매개 변수가 있는 프로시저는 `AddressOf` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="86285-106">This example has a procedure with a delegate parameter that can take a reference to another procedure, obtained with the `AddressOf` operator.</span></span>  
  
### <a name="create-the-delegate-and-matching-procedures"></a><span data-ttu-id="86285-107">대리자 및 일치 하는 프로시저 만들기</span><span class="sxs-lookup"><span data-stu-id="86285-107">Create the delegate and matching procedures</span></span>  
  
1.  <span data-ttu-id="86285-108">명명 된 대리자를 만들고 `MathOperator`합니다.</span><span class="sxs-lookup"><span data-stu-id="86285-108">Create a delegate named `MathOperator`.</span></span>  
  
     <span data-ttu-id="86285-109">[!code-vb[VbVbalrDelegates #&1;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="86285-109">[!code-vb[VbVbalrDelegates#1](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_1.vb)]</span></span>  
  
2.  <span data-ttu-id="86285-110">라는 프로시저를 만들어 `AddNumbers` 매개 변수 및 반환 값의 일치 하는 `MathOperator`서명이 일치 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="86285-110">Create a procedure named `AddNumbers` with parameters and return value that match those of `MathOperator`, so that the signatures match.</span></span>  
  
     <span data-ttu-id="86285-111">[!code-vb[VbVbalrDelegates #&2;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="86285-111">[!code-vb[VbVbalrDelegates#2](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_2.vb)]</span></span>  
  
3.  <span data-ttu-id="86285-112">라는 프로시저를 만들어 `SubtractNumbers` 일치 하는 서명을 사용 하 여 `MathOperator`합니다.</span><span class="sxs-lookup"><span data-stu-id="86285-112">Create a procedure named `SubtractNumbers` with a signature that matches `MathOperator`.</span></span>  
  
     <span data-ttu-id="86285-113">[!code-vb[VbVbalrDelegates #&3;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="86285-113">[!code-vb[VbVbalrDelegates#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_3.vb)]</span></span>  
  
4.  <span data-ttu-id="86285-114">라는 프로시저를 만들어 `DelegateTest` 대리자를 매개 변수로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="86285-114">Create a procedure named `DelegateTest` that takes a delegate as a parameter.</span></span>  
  
     <span data-ttu-id="86285-115">이 절차에 대 한 참조를 수락할 수 있는 `AddNumbers` 또는 `SubtractNumbers`해당 서명이 일치 하기 때문에는 `MathOperator` 서명 합니다.</span><span class="sxs-lookup"><span data-stu-id="86285-115">This procedure can accept a reference to `AddNumbers` or `SubtractNumbers`, because their signatures match the `MathOperator` signature.</span></span>  
  
     <span data-ttu-id="86285-116">[!code-vb[VbVbalrDelegates #&4;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="86285-116">[!code-vb[VbVbalrDelegates#4](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_4.vb)]</span></span>  
  
5.  <span data-ttu-id="86285-117">라는 프로시저를 만듭니다 `Test` 호출 하는 `DelegateTest` 에 대 한 대리자를 두 번 `AddNumbers` 및 다시에 대 한 대리자를 매개 변수로 `SubtractNumbers` 매개 변수로 합니다.</span><span class="sxs-lookup"><span data-stu-id="86285-117">Create a procedure named `Test` that calls `DelegateTest` once with the delegate for `AddNumbers` as a parameter, and again with the delegate for `SubtractNumbers` as a parameter.</span></span>  
  
     <span data-ttu-id="86285-118">[!code-vb[VbVbalrDelegates #&5;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="86285-118">[!code-vb[VbVbalrDelegates#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_5.vb)]</span></span>  
  
     <span data-ttu-id="86285-119">때 `Test` 은 호출 먼저 표시의 결과 `AddNumbers` 실행 `5` 및 `3`은 8입니다.</span><span class="sxs-lookup"><span data-stu-id="86285-119">When `Test` is called, it first displays the result of `AddNumbers` acting on `5` and `3`, which is 8.</span></span> <span data-ttu-id="86285-120">결과 `SubtractNumbers` 작업할 `9` 및 `3` 표시 되 면 6이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86285-120">Then the result of `SubtractNumbers` acting on `9` and `3` is displayed, which is 6.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86285-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="86285-121">See Also</span></span>  
 <span data-ttu-id="86285-122">[대리자](../../../../visual-basic/programming-guide/language-features/delegates/index.md) </span><span class="sxs-lookup"><span data-stu-id="86285-122">[Delegates](../../../../visual-basic/programming-guide/language-features/delegates/index.md) </span></span>  
<span data-ttu-id="86285-123"> [AddressOf 연산자](../../../../visual-basic/language-reference/operators/addressof-operator.md) </span><span class="sxs-lookup"><span data-stu-id="86285-123"> [AddressOf Operator](../../../../visual-basic/language-reference/operators/addressof-operator.md) </span></span>  
<span data-ttu-id="86285-124"> [Delegate 문](../../../../visual-basic/language-reference/statements/delegate-statement.md) </span><span class="sxs-lookup"><span data-stu-id="86285-124"> [Delegate Statement](../../../../visual-basic/language-reference/statements/delegate-statement.md) </span></span>  
<span data-ttu-id="86285-125"> [방법: 대리자 메서드 호출](../../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)</span><span class="sxs-lookup"><span data-stu-id="86285-125"> [How to: Invoke a Delegate Method](../../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)</span></span>
