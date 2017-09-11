---
title: "방법: 값 (Visual Basic)를 반환 하는 프로시저를 호출 합니다. | Microsoft 문서"
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
- procedure calls, returning values
- Visual Basic code, procedures
- procedures, calling
- procedures, returning a value
ms.assetid: a445127b-0f5f-465a-98fb-3e514b93d115
caps.latest.revision: 15
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
ms.openlocfilehash: cc1e274a705618213c830d7cf4f61a5e64afd980
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-call-a-procedure-that-returns-a-value-visual-basic"></a><span data-ttu-id="2549c-102">방법: 값을 반환하는 프로시저 호출(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2549c-102">How to: Call a Procedure That Returns a Value (Visual Basic)</span></span>
<span data-ttu-id="2549c-103">A `Function` 프로시저가 호출 코드에 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2549c-103">A `Function` procedure returns a value to the calling code.</span></span> <span data-ttu-id="2549c-104">오른쪽 대입문 이나 식에서 해당 이름 및 인수를 포함 하 여 프로시저를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="2549c-104">You call it by including its name and arguments either on the right side of an assignment statement or in an expression.</span></span>  
  
### <a name="to-call-a-function-procedure-within-an-expression"></a><span data-ttu-id="2549c-105">식 내의 함수 프로시저를 호출 하려면</span><span class="sxs-lookup"><span data-stu-id="2549c-105">To call a Function procedure within an expression</span></span>  
  
1.  <span data-ttu-id="2549c-106">사용 하는 `Function` 프로시저 변수를 사용할 때 동일한 방식으로 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2549c-106">Use the `Function` procedure name the same way you would use a variable.</span></span> <span data-ttu-id="2549c-107">사용할 수는 `Function` 프로시저 호출 원하는 위치에 식에 변수 또는 상수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2549c-107">You can use a `Function` procedure call anywhere you can use a variable or constant in an expression.</span></span>  
  
2.  <span data-ttu-id="2549c-108">괄호로 묶어 인수 목록 프로시저 이름 뒤에.</span><span class="sxs-lookup"><span data-stu-id="2549c-108">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="2549c-109">필요에 따라 인수가 있을 경우 괄호를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2549c-109">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="2549c-110">그러나 괄호를 사용 하는 코드를 읽기 쉽게.</span><span class="sxs-lookup"><span data-stu-id="2549c-110">However, using the parentheses makes your code easier to read.</span></span>  
  
3.  <span data-ttu-id="2549c-111">인수를 괄호로 묶고 쉼표로 구분 된 인수 목록에 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="2549c-111">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="2549c-112">같은 순서로 인수를 지정 해야 하는 `Function` 프로시저는 해당 매개 변수를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="2549c-112">Be sure you supply the arguments in the same order that the `Function` procedure defines the corresponding parameters.</span></span>  
  
     <span data-ttu-id="2549c-113">또는 이름으로 하나 이상의 인수를 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2549c-113">Alternatively, you can pass one or more arguments by name.</span></span> <span data-ttu-id="2549c-114">자세한 내용은 참조 [이름 및 위치도 인수 전달](./passing-arguments-by-position-and-by-name.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2549c-114">For more information, see [Passing Arguments by Position and by Name](./passing-arguments-by-position-and-by-name.md).</span></span>  
  
4.  <span data-ttu-id="2549c-115">상수 또는 변수 값과 마찬가지로 식에 참여 하는 프로시저에서 반환 되는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2549c-115">The value returned from the procedure participates in the expression just as the value of a variable or constant would.</span></span>  
  
### <a name="to-call-a-function-procedure-in-an-assignment-statement"></a><span data-ttu-id="2549c-116">대입문에서 함수 프로시저를 호출 하려면</span><span class="sxs-lookup"><span data-stu-id="2549c-116">To call a Function procedure in an assignment statement</span></span>  
  
1.  <span data-ttu-id="2549c-117">사용 된 `Function` 프로시저 이름 다음에 오는 (`=`) 대입문에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2549c-117">Use the `Function` procedure name following the equal (`=`) sign in the assignment statement.</span></span>  
  
2.  <span data-ttu-id="2549c-118">괄호로 묶어 인수 목록 프로시저 이름 뒤에.</span><span class="sxs-lookup"><span data-stu-id="2549c-118">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="2549c-119">필요에 따라 인수가 있을 경우 괄호를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2549c-119">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="2549c-120">그러나 괄호를 사용 하는 코드를 읽기 쉽게.</span><span class="sxs-lookup"><span data-stu-id="2549c-120">However, using the parentheses makes your code easier to read.</span></span>  
  
3.  <span data-ttu-id="2549c-121">인수를 괄호로 묶고 쉼표로 구분 된 인수 목록에 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="2549c-121">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="2549c-122">같은 순서로 인수를 지정 해야 하는 `Function` 으로 전달 하는 이름으로 하지 않으면 프로시저는 해당 매개 변수를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="2549c-122">Be sure you supply the arguments in the same order that the `Function` procedure defines the corresponding parameters, unless you are passing them by name.</span></span>  
  
4.  <span data-ttu-id="2549c-123">프로시저에서 반환 되는 값은 변수 또는 대입문의 왼쪽에는 속성에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2549c-123">The value returned from the procedure is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2549c-124">예제</span><span class="sxs-lookup"><span data-stu-id="2549c-124">Example</span></span>  
 <span data-ttu-id="2549c-125">다음 예제에서는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] <xref:Microsoft.VisualBasic.Interaction.Environ%2A>운영 체제 환경 변수의 값을 검색 합니다.</xref:Microsoft.VisualBasic.Interaction.Environ%2A></span><span class="sxs-lookup"><span data-stu-id="2549c-125">The following example calls the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] <xref:Microsoft.VisualBasic.Interaction.Environ%2A> to retrieve the value of an operating system environment variable.</span></span> <span data-ttu-id="2549c-126">첫 번째 줄에서는 `Environ` 내에서 식을 두 번째 줄에서는 것 대입문에서.</span><span class="sxs-lookup"><span data-stu-id="2549c-126">The first line calls `Environ` within an expression, and the second line calls it in an assignment statement.</span></span> <span data-ttu-id="2549c-127">`Environ`유일한 인수로 변수 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2549c-127">`Environ` takes the variable name as its sole argument.</span></span> <span data-ttu-id="2549c-128">호출 코드에 변수의 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2549c-128">It returns the variable's value to the calling code.</span></span>  
  
 <span data-ttu-id="2549c-129">[!code-vb[VbVbcnProcedures #&7;](./codesnippet/VisualBasic/how-to-call-a-procedure-that-returns-a-value_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="2549c-129">[!code-vb[VbVbcnProcedures#7](./codesnippet/VisualBasic/how-to-call-a-procedure-that-returns-a-value_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2549c-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2549c-130">See Also</span></span>  
 <span data-ttu-id="2549c-131">[Function 프로시저](./function-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="2549c-131">[Function Procedures](./function-procedures.md) </span></span>  
<span data-ttu-id="2549c-132"> [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="2549c-132"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="2549c-133"> [Function 문](../../../../visual-basic/language-reference/statements/function-statement.md) </span><span class="sxs-lookup"><span data-stu-id="2549c-133"> [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md) </span></span>  
<span data-ttu-id="2549c-134"> [방법: 값을 반환 하는 프로시저 만들기](./how-to-create-a-procedure-that-returns-a-value.md) </span><span class="sxs-lookup"><span data-stu-id="2549c-134"> [How to: Create a Procedure that Returns a Value](./how-to-create-a-procedure-that-returns-a-value.md) </span></span>  
<span data-ttu-id="2549c-135"> [방법: 프로시저에서 값을 반환 합니다.](./how-to-return-a-value-from-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="2549c-135"> [How to: Return a Value from a Procedure](./how-to-return-a-value-from-a-procedure.md) </span></span>  
<span data-ttu-id="2549c-136"> [방법: 값을 반환하지 않는 프로시저 호출](./how-to-call-a-procedure-that-does-not-return-a-value.md)</span><span class="sxs-lookup"><span data-stu-id="2549c-136"> [How to: Call a Procedure that Does Not Return a Value](./how-to-call-a-procedure-that-does-not-return-a-value.md)</span></span>
