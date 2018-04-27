---
title: '방법: 프로시저에서 값 반환(Visual Basic)'
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], returning from
- procedures [Visual Basic], returning a value
ms.assetid: 4bcc4724-2b4e-4df8-9b4b-16054607f87d
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: affcb25951a6647604286bc91dcaec8898fe2e30
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-return-a-value-from-a-procedure-visual-basic"></a><span data-ttu-id="0169d-102">방법: 프로시저에서 값 반환(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0169d-102">How to: Return a Value from a Procedure (Visual Basic)</span></span>
<span data-ttu-id="0169d-103">A `Function` 프로시저가 반환 값을 호출 하는 코드 실행 하거나 한 `Return` 문 또는 발생 하 여는 `Exit Function` 또는 `End Function` 문.</span><span class="sxs-lookup"><span data-stu-id="0169d-103">A `Function` procedure returns a value to the calling code either by executing a `Return` statement or by encountering an `Exit Function` or `End Function` statement.</span></span>  
  
### <a name="to-return-a-value-using-the-return-statement"></a><span data-ttu-id="0169d-104">Return 문을 사용 하 여 값을 반환 하려면</span><span class="sxs-lookup"><span data-stu-id="0169d-104">To return a value using the Return statement</span></span>  
  
1.  <span data-ttu-id="0169d-105">배치는 `Return` 프로시저의 작업이 완료 되는 지점에 문의 합니다.</span><span class="sxs-lookup"><span data-stu-id="0169d-105">Put a `Return` statement at the point where the procedure's task is completed.</span></span>  
  
2.  <span data-ttu-id="0169d-106">에 따라는 `Return` 호출 코드에 반환 하려는 값을 생성 하는 식으로 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="0169d-106">Follow the `Return` keyword with an expression that yields the value you want to return to the calling code.</span></span>  
  
3.  <span data-ttu-id="0169d-107">동일한 프로시저에 `Return` 문을 둘 이상 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0169d-107">You can have more than one `Return` statement in the same procedure.</span></span>  
  
     <span data-ttu-id="0169d-108">다음 `Function` 프로시저가 가장 긴 측 또는 직각 삼각형의 빗변 계산 하 고 호출 코드에 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0169d-108">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, and returns it to the calling code.</span></span>  
  
     [!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/how-to-return-a-value-from-a-procedure_1.vb)]  
  
     <span data-ttu-id="0169d-109">다음 예제에서는 호출을 `hypotenuse`, 반환된 된 값을 저장 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="0169d-109">The following example shows a typical call to `hypotenuse`, which stores the returned value.</span></span>  
  
     [!code-vb[VbVbcnProcedures#6](./codesnippet/VisualBasic/how-to-return-a-value-from-a-procedure_2.vb)]  
  
### <a name="to-return-a-value-using-exit-function-or-end-function"></a><span data-ttu-id="0169d-110">Exit 함수 또는 최종 함수를 사용 하 여 값을 반환 하려면</span><span class="sxs-lookup"><span data-stu-id="0169d-110">To return a value using Exit Function or End Function</span></span>  
  
1.  <span data-ttu-id="0169d-111">적어도 한 위치에 `Function` 프로시저를 프로시저의 이름에 값 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="0169d-111">In at least one place in the `Function` procedure, assign a value to the procedure's name.</span></span>  
  
2.  <span data-ttu-id="0169d-112">실행 하는 동안는 `Exit Function` 또는 `End Function` 문, Visual Basic 프로시저의 이름에 가장 최근에 할당 된 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0169d-112">When you execute an `Exit Function` or `End Function` statement, Visual Basic returns the value most recently assigned to the procedure's name.</span></span>  
  
3.  <span data-ttu-id="0169d-113">동일한 프로시저에 `Exit Function` 문을 둘 이상 사용할 수 있으며, `Return` 및 `Exit Function` 문을 혼합할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0169d-113">You can have more than one `Exit Function` statement in the same procedure, and you can mix `Return` and `Exit Function` statements in the same procedure.</span></span>  
  
4.  <span data-ttu-id="0169d-114">하나만 사용할 수 있습니다 `End Function` 의 문에서 `Function` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="0169d-114">You can have only one `End Function` statement in a `Function` procedure.</span></span>  
  
     <span data-ttu-id="0169d-115">자세한 내용 및 예제에 대 한 "반환 값이"의 참조 [Function 문](../../../../visual-basic/language-reference/statements/function-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0169d-115">For more information and an example, see "Return Value" in [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0169d-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0169d-116">See Also</span></span>  
 [<span data-ttu-id="0169d-117">절차</span><span class="sxs-lookup"><span data-stu-id="0169d-117">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="0169d-118">Sub 프로시저</span><span class="sxs-lookup"><span data-stu-id="0169d-118">Sub Procedures</span></span>](./sub-procedures.md)  
 [<span data-ttu-id="0169d-119">속성 프로시저</span><span class="sxs-lookup"><span data-stu-id="0169d-119">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="0169d-120">연산자 프로시저</span><span class="sxs-lookup"><span data-stu-id="0169d-120">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="0169d-121">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="0169d-121">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="0169d-122">Function 문</span><span class="sxs-lookup"><span data-stu-id="0169d-122">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="0169d-123">Return 문</span><span class="sxs-lookup"><span data-stu-id="0169d-123">Return Statement</span></span>](../../../../visual-basic/language-reference/statements/return-statement.md)  
 [<span data-ttu-id="0169d-124">방법: 값을 반환하는 프로시저 만들기</span><span class="sxs-lookup"><span data-stu-id="0169d-124">How to: Create a Procedure that Returns a Value</span></span>](./how-to-create-a-procedure-that-returns-a-value.md)  
 [<span data-ttu-id="0169d-125">방법: 값을 반환하는 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="0169d-125">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
