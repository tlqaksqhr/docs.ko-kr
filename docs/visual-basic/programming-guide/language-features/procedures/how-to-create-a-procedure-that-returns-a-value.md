---
title: "방법: 값을 반환하는 프로시저 만들기(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], returning a value
ms.assetid: 8ee19f95-a9ef-4033-963b-d224dca207c4
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 787eddc1fd1cdb9dd6b655a8556b75044b2a49dc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-procedure-that-returns-a-value-visual-basic"></a><span data-ttu-id="c10b5-102">방법: 값을 반환하는 프로시저 만들기(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c10b5-102">How to: Create a Procedure that Returns a Value (Visual Basic)</span></span>
<span data-ttu-id="c10b5-103">사용 된 `Function` 프로시저를 호출 하는 코드에 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c10b5-103">You use a `Function` procedure to return a value to the calling code.</span></span>  
  
### <a name="to-create-a-procedure-that-returns-a-value"></a><span data-ttu-id="c10b5-104">값을 반환 하는 프로시저를 만들려면</span><span class="sxs-lookup"><span data-stu-id="c10b5-104">To create a procedure that returns a value</span></span>  
  
1.  <span data-ttu-id="c10b5-105">다른 프로시저 밖에 서 사용 하 여 한 `Function` 문 다음에 `End Function` 문.</span><span class="sxs-lookup"><span data-stu-id="c10b5-105">Outside any other procedure, use a `Function` statement, followed by an `End Function` statement.</span></span>  
  
2.  <span data-ttu-id="c10b5-106">에 `Function` 문을 수행는 `Function` 키워드는 프로시저 및 매개 변수 목록 괄호 안에 이름으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="c10b5-106">In the `Function` statement, follow the `Function` keyword with the name of the procedure, and then the parameter list in parentheses.</span></span>  
  
3.  <span data-ttu-id="c10b5-107">괄호 다음에 `As` 절 반환된 된 값의 데이터 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c10b5-107">Follow the parentheses with an `As` clause to specify the data type of the returned value.</span></span>  
  
4.  <span data-ttu-id="c10b5-108">프로시저의 코드 문을 사이 `Function` 및 `End Function` 문.</span><span class="sxs-lookup"><span data-stu-id="c10b5-108">Place the procedure's code statements between the `Function` and `End Function` statements.</span></span>  
  
5.  <span data-ttu-id="c10b5-109">사용 하 여 한 `Return` 호출 코드에 값을 반환 하는 문입니다.</span><span class="sxs-lookup"><span data-stu-id="c10b5-109">Use a `Return` statement to return the value to the calling code.</span></span>  
  
     <span data-ttu-id="c10b5-110">다음 `Function` 프로시저 가장 긴 면 또는 다른 두 변에 대 한 값을 지정 하는 직각 삼각형의 빗변을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="c10b5-110">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, given the values for the other two sides.</span></span>  
  
     [!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/how-to-create-a-procedure-that-returns-a-value_1.vb)]  
  
     <span data-ttu-id="c10b5-111">다음 예제에서는 호출을 `hypotenuse`합니다.</span><span class="sxs-lookup"><span data-stu-id="c10b5-111">The following example shows a typical call to `hypotenuse`.</span></span>  
  
     [!code-vb[VbVbcnProcedures#6](./codesnippet/VisualBasic/how-to-create-a-procedure-that-returns-a-value_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="c10b5-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c10b5-112">See Also</span></span>  
 [<span data-ttu-id="c10b5-113">절차</span><span class="sxs-lookup"><span data-stu-id="c10b5-113">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="c10b5-114">Sub 프로시저</span><span class="sxs-lookup"><span data-stu-id="c10b5-114">Sub Procedures</span></span>](./sub-procedures.md)  
 [<span data-ttu-id="c10b5-115">속성 프로시저</span><span class="sxs-lookup"><span data-stu-id="c10b5-115">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="c10b5-116">연산자 프로시저</span><span class="sxs-lookup"><span data-stu-id="c10b5-116">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="c10b5-117">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="c10b5-117">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="c10b5-118">Function 문</span><span class="sxs-lookup"><span data-stu-id="c10b5-118">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="c10b5-119">방법: 프로시저에서 값 반환</span><span class="sxs-lookup"><span data-stu-id="c10b5-119">How to: Return a Value from a Procedure</span></span>](./how-to-return-a-value-from-a-procedure.md)  
 [<span data-ttu-id="c10b5-120">방법: 값을 반환하는 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="c10b5-120">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
