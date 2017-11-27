---
title: "하위 식(Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- lambda expressions [Visual Basic], sub expression
- Sub Expression [Visual Basic]
- subroutines [Visual Basic], sub expressions
ms.assetid: 36b6bfd1-6539-4d8f-a5eb-6541a745ffde
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 43e35bd0386bc56478603ec36437981785cc8ffb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="sub-expression-visual-basic"></a><span data-ttu-id="1497b-102">하위 식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1497b-102">Sub Expression (Visual Basic)</span></span>
<span data-ttu-id="1497b-103">매개 변수 및 서브루틴 람다 식을 정의 하는 코드를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="1497b-103">Declares the parameters and code that define a subroutine lambda expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1497b-104">구문</span><span class="sxs-lookup"><span data-stu-id="1497b-104">Syntax</span></span>  
  
```  
Sub ( [ parameterlist ] ) statement  
- or -  
Sub ( [ parameterlist ] )  
  [ statements ]  
End Sub  
```  
  
## <a name="parts"></a><span data-ttu-id="1497b-105">요소</span><span class="sxs-lookup"><span data-stu-id="1497b-105">Parts</span></span>  
  
|<span data-ttu-id="1497b-106">용어</span><span class="sxs-lookup"><span data-stu-id="1497b-106">Term</span></span>|<span data-ttu-id="1497b-107">정의</span><span class="sxs-lookup"><span data-stu-id="1497b-107">Definition</span></span>|  
|---|---|  
|`parameterlist`|<span data-ttu-id="1497b-108">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="1497b-108">Optional.</span></span> <span data-ttu-id="1497b-109">목록 프로시저의 매개 변수를 나타내는 지역 변수 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1497b-109">A list of local variable names that represent the parameters of the procedure.</span></span> <span data-ttu-id="1497b-110">괄호는 목록이 비어 있는 경우에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1497b-110">The parentheses must be present even when the list is empty.</span></span> <span data-ttu-id="1497b-111">자세한 내용은 참조 [매개 변수 목록](../../../visual-basic/language-reference/statements/parameter-list.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1497b-111">For more information, see [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span></span>|  
|`statement`|<span data-ttu-id="1497b-112">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="1497b-112">Required.</span></span> <span data-ttu-id="1497b-113">단일 문입니다.</span><span class="sxs-lookup"><span data-stu-id="1497b-113">A single statement.</span></span>|  
|`statements`|<span data-ttu-id="1497b-114">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="1497b-114">Required.</span></span> <span data-ttu-id="1497b-115">문 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="1497b-115">A list of statements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1497b-116">설명</span><span class="sxs-lookup"><span data-stu-id="1497b-116">Remarks</span></span>  
 <span data-ttu-id="1497b-117">A *람다 식을* 이름을 없는 서브루틴은 및 하나 이상의 문을 실행 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="1497b-117">A *lambda expression* is a subroutine that does not have a name and that executes one or more statements.</span></span> <span data-ttu-id="1497b-118">어디 람다 식을 사용할 수는 있습니다으로 사용할 수 대리자 형식을 제외 하 고 인수를 `RemoveHandler`합니다.</span><span class="sxs-lookup"><span data-stu-id="1497b-118">You can use a lambda expression anywhere that you can use a delegate type, except as an argument to `RemoveHandler`.</span></span> <span data-ttu-id="1497b-119">대리자 및 대리자와 람다 식 사용 하는 방법에 대 한 자세한 내용은 참조 [대리자 문을](../../../visual-basic/language-reference/statements/delegate-statement.md) 및 [완화 된 대리자 변환](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1497b-119">For more information about delegates, and the use of lambda expressions with delegates, see [Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md) and [Relaxed Delegate Conversion](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span>  
  
## <a name="lambda-expression-syntax"></a><span data-ttu-id="1497b-120">람다 식 구문</span><span class="sxs-lookup"><span data-stu-id="1497b-120">Lambda Expression Syntax</span></span>  
 <span data-ttu-id="1497b-121">람다 식의 구문은 유사 표준 서브루틴의 합니다.</span><span class="sxs-lookup"><span data-stu-id="1497b-121">The syntax of a lambda expression resembles that of a standard subroutine.</span></span> <span data-ttu-id="1497b-122">차이점은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1497b-122">The differences are as follows:</span></span>  
  
-   <span data-ttu-id="1497b-123">람다 식에 이름이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1497b-123">A lambda expression does not have a name.</span></span>  
  
-   <span data-ttu-id="1497b-124">람다 식에는 한정자와 같은 없습니다 `Overloads` 또는 `Overrides`합니다.</span><span class="sxs-lookup"><span data-stu-id="1497b-124">A lambda expression cannot have a modifier, such as `Overloads` or `Overrides`.</span></span>  
  
-   <span data-ttu-id="1497b-125">한 줄 람다 식의 본문에는 문, 식 하지 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1497b-125">The body of a single-line lambda expression must be a statement, not an expression.</span></span> <span data-ttu-id="1497b-126">Sub 프로시저를 호출 하지만 function 프로시저를 호출 하지 본문 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1497b-126">The body can consist of a call to a sub procedure, but not a call to a function procedure.</span></span>  
  
-   <span data-ttu-id="1497b-127">람다 식에서 모든 매개 변수에 지정 된 데이터 형식이 나 모든 매개 변수를 유추 합니다.</span><span class="sxs-lookup"><span data-stu-id="1497b-127">In a lambda expression, either all parameters must have specified data types or all parameters must be inferred.</span></span>  
  
-   <span data-ttu-id="1497b-128">선택적 및 `ParamArray` 매개 변수는 람다 식에 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1497b-128">Optional and `ParamArray` parameters are not permitted in lambda expressions.</span></span>  
  
-   <span data-ttu-id="1497b-129">제네릭 매개 변수 람다 식에 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1497b-129">Generic parameters are not permitted in lambda expressions.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1497b-130">예제</span><span class="sxs-lookup"><span data-stu-id="1497b-130">Example</span></span>  
 <span data-ttu-id="1497b-131">다음은 콘솔에는 값을 작성 하는 람다 식의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="1497b-131">Following is an example of a lambda expression that writes a value to the console.</span></span> <span data-ttu-id="1497b-132">서브루틴에 대 한 두에서는 한 줄 및 여러 줄 람다 식 구문을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1497b-132">The example shows both the single-line and multiline lambda expression syntax for a subroutine.</span></span> <span data-ttu-id="1497b-133">더 많은 예제를 참조 하십시오. [람다 식](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1497b-133">For more examples, see [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
 [!code-vb[VbVbalrLambdas#15](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/sub-expression_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="1497b-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1497b-134">See Also</span></span>  
 [<span data-ttu-id="1497b-135">Sub 문</span><span class="sxs-lookup"><span data-stu-id="1497b-135">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="1497b-136">람다 식</span><span class="sxs-lookup"><span data-stu-id="1497b-136">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)  
 [<span data-ttu-id="1497b-137">연산자 및 식</span><span class="sxs-lookup"><span data-stu-id="1497b-137">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [<span data-ttu-id="1497b-138">문</span><span class="sxs-lookup"><span data-stu-id="1497b-138">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)  
 [<span data-ttu-id="1497b-139">완화된 대리자 변환</span><span class="sxs-lookup"><span data-stu-id="1497b-139">Relaxed Delegate Conversion</span></span>](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
