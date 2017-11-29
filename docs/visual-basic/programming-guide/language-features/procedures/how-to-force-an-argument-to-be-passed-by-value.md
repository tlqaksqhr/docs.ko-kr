---
title: "방법: 인수가 값으로 전달되도록 설정(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- procedure arguments
- Visual Basic code, procedures
- arguments [Visual Basic], ByVal
- arguments [Visual Basic], passing by value
- procedure parameters
- procedures [Visual Basic], calling
- arguments [Visual Basic], in parentheses
- procedure arguments [Visual Basic], in parentheses
- arguments [Visual Basic], changing value
ms.assetid: 77b4f2d2-1055-4c2f-a521-874d1db86946
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fdb2df7e114f49c23db9f5b322ca9dd32135ac88
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-force-an-argument-to-be-passed-by-value-visual-basic"></a><span data-ttu-id="14dc1-102">방법: 인수가 값으로 전달되도록 설정(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="14dc1-102">How to: Force an Argument to Be Passed by Value (Visual Basic)</span></span>
<span data-ttu-id="14dc1-103">프로시저 선언 전달 메커니즘을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="14dc1-103">The procedure declaration determines the passing mechanism.</span></span> <span data-ttu-id="14dc1-104">매개 변수가 선언 된 경우 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 참조로 해당 인수를 전달 하는 예상 합니다.</span><span class="sxs-lookup"><span data-stu-id="14dc1-104">If a parameter is declared [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] expects to pass the corresponding argument by reference.</span></span> <span data-ttu-id="14dc1-105">따라서 프로시저를를 호출 코드의 기반이 되는 프로그래밍 요소의 값을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14dc1-105">This allows the procedure to change the value of the programming element underlying the argument in the calling code.</span></span> <span data-ttu-id="14dc1-106">이러한 변경 으로부터 내부 요소를 보호 하려는 경우 재정의할 수 있습니다는 `ByRef` 프로시저에 전달 메커니즘 괄호 안에 인수 이름을 포함 하 여 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="14dc1-106">If you wish to protect the underlying element against such change, you can override the `ByRef` passing mechanism in the procedure call by enclosing the argument name in parentheses.</span></span> <span data-ttu-id="14dc1-107">이 괄호는 호출에 인수 목록을 묶는 괄호는 별개입니다.</span><span class="sxs-lookup"><span data-stu-id="14dc1-107">These parentheses are in addition to the parentheses enclosing the argument list in the call.</span></span>  
  
 <span data-ttu-id="14dc1-108">호출 코드에서 재정의할 수 없습니다. 한 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="14dc1-108">The calling code cannot override a [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) mechanism.</span></span>  
  
### <a name="to-force-an-argument-to-be-passed-by-value"></a><span data-ttu-id="14dc1-109">인수가 값으로 전달 되도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="14dc1-109">To force an argument to be passed by value</span></span>  
  
-   <span data-ttu-id="14dc1-110">해당 매개 변수가 선언 된 경우 `ByVal` 절차에서는 필요가 없습니다 모든 추가 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14dc1-110">If the corresponding parameter is declared `ByVal` in the procedure, you do not need to take any additional steps.</span></span> [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="14dc1-111">값으로 인수를 전달 하는 이미 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="14dc1-111"> already expects to pass the argument by value.</span></span>  
  
-   <span data-ttu-id="14dc1-112">해당 매개 변수가 선언 된 경우 `ByRef` 프로시저에서 프로시저 호출에서 괄호 안에 인수를 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="14dc1-112">If the corresponding parameter is declared `ByRef` in the procedure, enclose the argument in parentheses in the procedure call.</span></span>  
  
## <a name="example"></a><span data-ttu-id="14dc1-113">예제</span><span class="sxs-lookup"><span data-stu-id="14dc1-113">Example</span></span>  
 <span data-ttu-id="14dc1-114">다음 예제에서는 재정의 `ByRef` 매개 변수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="14dc1-114">The following example overrides a `ByRef` parameter declaration.</span></span> <span data-ttu-id="14dc1-115">강제로 수행 하는 호출에 `ByVal`, 두 가지 수준의 괄호에 유의 합니다.</span><span class="sxs-lookup"><span data-stu-id="14dc1-115">In the call that forces `ByVal`, note the two levels of parentheses.</span></span>  
  
 [!code-vb[VbVbcnProcedures#39](./codesnippet/VisualBasic/how-to-force-an-argument-to-be-passed-by-value_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#40](./codesnippet/VisualBasic/how-to-force-an-argument-to-be-passed-by-value_2.vb)]  
  
 <span data-ttu-id="14dc1-116">때 `str` 인수 목록에서 추가 괄호로 묶인는 `setNewString` 프로시저가 호출 코드에서 해당 값을 변경할 수 없습니다 및 `MsgBox` "대체할 수 없는 byval로 전달 되는 경우" 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14dc1-116">When `str` is enclosed in extra parentheses within the argument list, the `setNewString` procedure cannot change its value in the calling code, and `MsgBox` displays "Cannot be replaced if passed ByVal".</span></span> <span data-ttu-id="14dc1-117">때 `str` 묶여 있지 않은 추가 괄호로 프로시저를 변경할 수 및 `MsgBox` "inString 인수에 대 한 새 값입니다."를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="14dc1-117">When `str` is not enclosed in extra parentheses, the procedure can change it, and `MsgBox` displays "This is a new value for the inString argument."</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="14dc1-118">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="14dc1-118">Compiling the Code</span></span>  
 <span data-ttu-id="14dc1-119">참조 하 여 변수를 전달할 때 사용 해야는 `ByRef` 키워드가이 메커니즘을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="14dc1-119">When you pass a variable by reference, you must use the `ByRef` keyword to specify this mechanism.</span></span>  
  
 <span data-ttu-id="14dc1-120">대화 상자에서 기본 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 값으로 인수를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="14dc1-120">The default in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] is to pass arguments by value.</span></span> <span data-ttu-id="14dc1-121">그러나 것이 바람직한 프로그래밍 습관 하나를 포함 하는 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) 또는 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) 키워드 모든 선언 된 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="14dc1-121">However, it is good programming practice to include either the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="14dc1-122">이렇게 하면 코드를 보다 쉽게 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14dc1-122">This makes your code easier to read.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="14dc1-123">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="14dc1-123">Robust Programming</span></span>  
 <span data-ttu-id="14dc1-124">프로시저 매개 변수를 선언한 경우 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)을 올바르게 실행 되는 코드의 호출 코드에서 기본 요소를 변경할 수 있는지에 따라 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14dc1-124">If a procedure declares a parameter [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), the correct execution of the code might depend on being able to change the underlying element in the calling code.</span></span> <span data-ttu-id="14dc1-125">호출 코드에 있는 괄호 안에 인수를 포함 하 여이 호출 하는 메커니즘을 재정의 하거나 수정할 수 없는 인수를 전달 하는 경우 프로시저는 내부 요소를 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="14dc1-125">If the calling code overrides this calling mechanism by enclosing the argument in parentheses, or if it passes a nonmodifiable argument, the procedure cannot change the underlying element.</span></span> <span data-ttu-id="14dc1-126">이 호출 코드에 예기치 않은 결과가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14dc1-126">This might produce unexpected results in the calling code.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="14dc1-127">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="14dc1-127">.NET Framework Security</span></span>  
 <span data-ttu-id="14dc1-128">호출 코드의 기반이 되는 값을 변경 하는 절차를 허용할 경우 잠재적인 위험이 항상 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14dc1-128">There is always a potential risk in allowing a procedure to change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="14dc1-129">변경 되 고 사용 하기 전에 유효성을 검사할 수 있도록 준비 하려면이 값을 예상 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14dc1-129">Make sure you expect this value to be changed, and be prepared to check it for validity before using it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14dc1-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="14dc1-130">See Also</span></span>  
 [<span data-ttu-id="14dc1-131">절차</span><span class="sxs-lookup"><span data-stu-id="14dc1-131">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="14dc1-132">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="14dc1-132">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="14dc1-133">방법: 프로시저에 인수 전달</span><span class="sxs-lookup"><span data-stu-id="14dc1-133">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)  
 [<span data-ttu-id="14dc1-134">값 또는 참조로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="14dc1-134">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="14dc1-135">수정할 수 있는 인수와 수정할 수 없는 인수 사이의 차이점</span><span class="sxs-lookup"><span data-stu-id="14dc1-135">Differences Between Modifiable and Nonmodifiable Arguments</span></span>](./differences-between-modifiable-and-nonmodifiable-arguments.md)  
 [<span data-ttu-id="14dc1-136">인수를 값으로 전달할 때와 참조로 전달할 때의 차이점</span><span class="sxs-lookup"><span data-stu-id="14dc1-136">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)  
 [<span data-ttu-id="14dc1-137">방법: 프로시저 인수의 값 변경</span><span class="sxs-lookup"><span data-stu-id="14dc1-137">How to: Change the Value of a Procedure Argument</span></span>](./how-to-change-the-value-of-a-procedure-argument.md)  
 [<span data-ttu-id="14dc1-138">방법: 값 변경에 대해 프로시저 인수 보호</span><span class="sxs-lookup"><span data-stu-id="14dc1-138">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)  
 [<span data-ttu-id="14dc1-139">위치 및 이름으로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="14dc1-139">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)  
 [<span data-ttu-id="14dc1-140">값 형식과 참조 형식</span><span class="sxs-lookup"><span data-stu-id="14dc1-140">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
