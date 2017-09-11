---
title: "방법: 프로시저 (Visual Basic)에서 값 반환 | Microsoft 문서"
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
- Visual Basic code, procedures
- procedures, returning from
- procedures, returning a value
ms.assetid: 4bcc4724-2b4e-4df8-9b4b-16054607f87d
caps.latest.revision: 12
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
ms.openlocfilehash: 601cd3adca0105eb829bb6156f94289b5c9f5f72
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-return-a-value-from-a-procedure-visual-basic"></a><span data-ttu-id="71608-102">방법: 프로시저에서 값 반환(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="71608-102">How to: Return a Value from a Procedure (Visual Basic)</span></span>
<span data-ttu-id="71608-103">A `Function` 프로시저에 값을 반환 호출 코드를 실행 하 여 하나는 `Return` 문 또는 발생 하 여는 `Exit Function` 또는 `End Function` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="71608-103">A `Function` procedure returns a value to the calling code either by executing a `Return` statement or by encountering an `Exit Function` or `End Function` statement.</span></span>  
  
### <a name="to-return-a-value-using-the-return-statement"></a><span data-ttu-id="71608-104">Return 문을 사용 하 여 값을 반환 하려면</span><span class="sxs-lookup"><span data-stu-id="71608-104">To return a value using the Return statement</span></span>  
  
1.  <span data-ttu-id="71608-105">배치는 `Return` 프로시저의 작업이 완료 되는 지점에 문의 합니다.</span><span class="sxs-lookup"><span data-stu-id="71608-105">Put a `Return` statement at the point where the procedure's task is completed.</span></span>  
  
2.  <span data-ttu-id="71608-106">에 따라는 `Return` 호출 코드로 반환 하려는 키워드 값을 생성 하는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="71608-106">Follow the `Return` keyword with an expression that yields the value you want to return to the calling code.</span></span>  
  
3.  <span data-ttu-id="71608-107">둘 이상의 `Return` 동일한 절차에는 문입니다.</span><span class="sxs-lookup"><span data-stu-id="71608-107">You can have more than one `Return` statement in the same procedure.</span></span>  
  
     <span data-ttu-id="71608-108">다음 `Function` 프로시저 가장 긴 면 또는 직각 삼각형의 빗변을 계산 하 고 호출 코드에 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="71608-108">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, and returns it to the calling code.</span></span>  
  
     <span data-ttu-id="71608-109">[!code-vb[VbVbcnProcedures #&1;](./codesnippet/VisualBasic/how-to-return-a-value-from-a-procedure_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="71608-109">[!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/how-to-return-a-value-from-a-procedure_1.vb)]</span></span>  
  
     <span data-ttu-id="71608-110">다음 예제에서는 호출을 `hypotenuse`, 반환된 된 값을 저장 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="71608-110">The following example shows a typical call to `hypotenuse`, which stores the returned value.</span></span>  
  
     <span data-ttu-id="71608-111">[!code-vb[VbVbcnProcedures #&6;](./codesnippet/VisualBasic/how-to-return-a-value-from-a-procedure_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="71608-111">[!code-vb[VbVbcnProcedures#6](./codesnippet/VisualBasic/how-to-return-a-value-from-a-procedure_2.vb)]</span></span>  
  
### <a name="to-return-a-value-using-exit-function-or-end-function"></a><span data-ttu-id="71608-112">Exit 함수 또는 End 함수를 사용 하 여 값을 반환 하려면</span><span class="sxs-lookup"><span data-stu-id="71608-112">To return a value using Exit Function or End Function</span></span>  
  
1.  <span data-ttu-id="71608-113">하나 이상의 위치에는 `Function` 프로시저는 프로시저의 이름으로이 값을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="71608-113">In at least one place in the `Function` procedure, assign a value to the procedure's name.</span></span>  
  
2.  <span data-ttu-id="71608-114">실행 하는 경우는 `Exit Function` 또는 `End Function` 문을 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 프로시저의 이름에 가장 최근에 할당 된 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="71608-114">When you execute an `Exit Function` or `End Function` statement, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] returns the value most recently assigned to the procedure's name.</span></span>  
  
3.  <span data-ttu-id="71608-115">둘 이상의 `Exit Function` 문을 동일한 절차에 혼합할 수 `Return` 및 `Exit Function` 동일한 프로시저의 문이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71608-115">You can have more than one `Exit Function` statement in the same procedure, and you can mix `Return` and `Exit Function` statements in the same procedure.</span></span>  
  
4.  <span data-ttu-id="71608-116">하나씩만 있을 수 `End Function` 문에서 `Function` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="71608-116">You can have only one `End Function` statement in a `Function` procedure.</span></span>  
  
     <span data-ttu-id="71608-117">자세한 내용 및 예제에 대 한 "반환 값이"의 참조 [Function 문의](../../../../visual-basic/language-reference/statements/function-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="71608-117">For more information and an example, see "Return Value" in [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71608-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="71608-118">See Also</span></span>  
 <span data-ttu-id="71608-119">[프로시저](./index.md) </span><span class="sxs-lookup"><span data-stu-id="71608-119">[Procedures](./index.md) </span></span>  
<span data-ttu-id="71608-120"> [Sub 프로시저](./sub-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="71608-120"> [Sub Procedures](./sub-procedures.md) </span></span>  
<span data-ttu-id="71608-121"> [속성 프로시저](./property-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="71608-121"> [Property Procedures](./property-procedures.md) </span></span>  
<span data-ttu-id="71608-122"> [연산자 프로시저](./operator-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="71608-122"> [Operator Procedures](./operator-procedures.md) </span></span>  
<span data-ttu-id="71608-123"> [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="71608-123"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="71608-124"> [Function 문](../../../../visual-basic/language-reference/statements/function-statement.md) </span><span class="sxs-lookup"><span data-stu-id="71608-124"> [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md) </span></span>  
<span data-ttu-id="71608-125"> [Return 문](../../../../visual-basic/language-reference/statements/return-statement.md) </span><span class="sxs-lookup"><span data-stu-id="71608-125"> [Return Statement](../../../../visual-basic/language-reference/statements/return-statement.md) </span></span>  
<span data-ttu-id="71608-126"> [방법: 값을 반환 하는 프로시저 만들기](./how-to-create-a-procedure-that-returns-a-value.md) </span><span class="sxs-lookup"><span data-stu-id="71608-126"> [How to: Create a Procedure that Returns a Value](./how-to-create-a-procedure-that-returns-a-value.md) </span></span>  
<span data-ttu-id="71608-127"> [방법: 값을 반환하는 프로시저 호출](./how-to-call-a-procedure-that-returns-a-value.md)</span><span class="sxs-lookup"><span data-stu-id="71608-127"> [How to: Call a Procedure That Returns a Value](./how-to-call-a-procedure-that-returns-a-value.md)</span></span>
