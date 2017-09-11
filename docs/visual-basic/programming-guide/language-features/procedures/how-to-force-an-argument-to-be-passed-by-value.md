---
title: "방법: 인수가 값 (Visual Basic)으로 전달 되도록 설정 | Microsoft 문서"
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
- procedures, arguments
- procedures, parameters
- procedure arguments
- Visual Basic code, procedures
- arguments [Visual Basic], ByVal
- arguments [Visual Basic], passing by value
- procedure parameters
- procedures, calling
- arguments [Visual Basic], in parentheses
- procedure arguments, in parentheses
- arguments [Visual Basic], changing value
ms.assetid: 77b4f2d2-1055-4c2f-a521-874d1db86946
caps.latest.revision: 16
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
ms.openlocfilehash: b151c319489ccda357faa082ce0b3c1addad0458
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-force-an-argument-to-be-passed-by-value-visual-basic"></a><span data-ttu-id="10a9a-102">방법: 인수가 값으로 전달되도록 설정(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="10a9a-102">How to: Force an Argument to Be Passed by Value (Visual Basic)</span></span>
<span data-ttu-id="10a9a-103">프로시저 선언 전달 메커니즘을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="10a9a-103">The procedure declaration determines the passing mechanism.</span></span> <span data-ttu-id="10a9a-104">매개 변수가 선언 된 경우 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 참조로 해당 인수를 전달 하려면 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="10a9a-104">If a parameter is declared [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] expects to pass the corresponding argument by reference.</span></span> <span data-ttu-id="10a9a-105">이렇게 하면 호출 코드에서 인수를 기본 프로그래밍 요소의 값을 변경 하는 절차입니다.</span><span class="sxs-lookup"><span data-stu-id="10a9a-105">This allows the procedure to change the value of the programming element underlying the argument in the calling code.</span></span> <span data-ttu-id="10a9a-106">이러한 변경 으로부터 내부 요소를 보호 하려는 경우 재정의할 수 있습니다는 `ByRef` 인수 이름을 괄호로 묶어 호출 프로시저에 전달 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="10a9a-106">If you wish to protect the underlying element against such change, you can override the `ByRef` passing mechanism in the procedure call by enclosing the argument name in parentheses.</span></span> <span data-ttu-id="10a9a-107">이 괄호는 호출에 인수 목록을 묶는 괄호는 별개입니다.</span><span class="sxs-lookup"><span data-stu-id="10a9a-107">These parentheses are in addition to the parentheses enclosing the argument list in the call.</span></span>  
  
 <span data-ttu-id="10a9a-108">재정의할 수 없습니다. 호출 하는 코드는 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="10a9a-108">The calling code cannot override a [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) mechanism.</span></span>  
  
### <a name="to-force-an-argument-to-be-passed-by-value"></a><span data-ttu-id="10a9a-109">인수가 값으로 전달 되도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="10a9a-109">To force an argument to be passed by value</span></span>  
  
-   <span data-ttu-id="10a9a-110">해당 매개 변수가 선언 된 경우 `ByVal` 프로시저를 추가 단계를 수행할 필요가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10a9a-110">If the corresponding parameter is declared `ByVal` in the procedure, you do not need to take any additional steps.</span></span> [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="10a9a-111">이미 값으로 인수 전달이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="10a9a-111"> already expects to pass the argument by value.</span></span>  
  
-   <span data-ttu-id="10a9a-112">해당 매개 변수가 선언 된 경우 `ByRef` 절차에서는 프로시저 호출에서 괄호 안에 인수를 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="10a9a-112">If the corresponding parameter is declared `ByRef` in the procedure, enclose the argument in parentheses in the procedure call.</span></span>  
  
## <a name="example"></a><span data-ttu-id="10a9a-113">예제</span><span class="sxs-lookup"><span data-stu-id="10a9a-113">Example</span></span>  
 <span data-ttu-id="10a9a-114">다음 예제에서는 재정의 `ByRef` 매개 변수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="10a9a-114">The following example overrides a `ByRef` parameter declaration.</span></span> <span data-ttu-id="10a9a-115">강제로 실행 하는 호출에서 `ByVal`, 괄호를 두 개를 기록해 둡니다.</span><span class="sxs-lookup"><span data-stu-id="10a9a-115">In the call that forces `ByVal`, note the two levels of parentheses.</span></span>  
  
 <span data-ttu-id="10a9a-116">[!code-vb[VbVbcnProcedures #&39;](./codesnippet/VisualBasic/how-to-force-an-argument-to-be-passed-by-value_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="10a9a-116">[!code-vb[VbVbcnProcedures#39](./codesnippet/VisualBasic/how-to-force-an-argument-to-be-passed-by-value_1.vb)]</span></span>  
  
 <span data-ttu-id="10a9a-117">[!code-vb[VbVbcnProcedures #&40;](./codesnippet/VisualBasic/how-to-force-an-argument-to-be-passed-by-value_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="10a9a-117">[!code-vb[VbVbcnProcedures#40](./codesnippet/VisualBasic/how-to-force-an-argument-to-be-passed-by-value_2.vb)]</span></span>  
  
 <span data-ttu-id="10a9a-118">때 `str` 인수 목록에서 추가 괄호로 묶인는 `setNewString` 프로시저 호출 코드에서 해당 값을 변경할 수 없습니다 및 `MsgBox` "대체할 수 없는 byval로 전달 되는 경우"를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="10a9a-118">When `str` is enclosed in extra parentheses within the argument list, the `setNewString` procedure cannot change its value in the calling code, and `MsgBox` displays "Cannot be replaced if passed ByVal".</span></span> <span data-ttu-id="10a9a-119">때 `str` 에 포함 되지 않은 추가 괄호 안의 프로시저를 변경할 수 및 `MsgBox` "inString 인수에 대 한 새 값입니다."를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="10a9a-119">When `str` is not enclosed in extra parentheses, the procedure can change it, and `MsgBox` displays "This is a new value for the inString argument."</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="10a9a-120">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="10a9a-120">Compiling the Code</span></span>  
 <span data-ttu-id="10a9a-121">참조로 변수를 전달 하는 경우 사용 해야는 `ByRef` 키워드가이 메커니즘을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="10a9a-121">When you pass a variable by reference, you must use the `ByRef` keyword to specify this mechanism.</span></span>  
  
 <span data-ttu-id="10a9a-122">대화 상자에서 기본 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 값으로 인수를 전달 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="10a9a-122">The default in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] is to pass arguments by value.</span></span> <span data-ttu-id="10a9a-123">그러나 것이 바람직한 프로그래밍 습관 하나를 포함 하는 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) 또는 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) 키워드 선언 된 모든 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="10a9a-123">However, it is good programming practice to include either the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="10a9a-124">이렇게 하면 코드를 보다 쉽게 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10a9a-124">This makes your code easier to read.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="10a9a-125">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="10a9a-125">Robust Programming</span></span>  
 <span data-ttu-id="10a9a-126">프로시저 매개 변수를 선언 하는 경우 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)을 올바르게 실행 되는 코드의 호출 코드에서 기본 요소를 변경할 수 있는지에 따라 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10a9a-126">If a procedure declares a parameter [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), the correct execution of the code might depend on being able to change the underlying element in the calling code.</span></span> <span data-ttu-id="10a9a-127">호출 코드에서 인수를 괄호로 묶어이 호출 하는 메커니즘을 재정의 하거나 수정할 수 없는 인수를 전달 하는 경우 프로시저는 내부 요소를 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="10a9a-127">If the calling code overrides this calling mechanism by enclosing the argument in parentheses, or if it passes a nonmodifiable argument, the procedure cannot change the underlying element.</span></span> <span data-ttu-id="10a9a-128">이 호출 코드에서 예기치 않은 결과가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10a9a-128">This might produce unexpected results in the calling code.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="10a9a-129">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="10a9a-129">.NET Framework Security</span></span>  
 <span data-ttu-id="10a9a-130">에 없는 경우 항상 한 잠재적인 위험을 호출 하는 코드에 있는 인수를 내부 값을 변경 하는 절차를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="10a9a-130">There is always a potential risk in allowing a procedure to change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="10a9a-131">변경 되 고 사용 하기 전에 유효성을 검사할 수 있도록 준비 하려면이 값을 예상 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10a9a-131">Make sure you expect this value to be changed, and be prepared to check it for validity before using it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10a9a-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="10a9a-132">See Also</span></span>  
 <span data-ttu-id="10a9a-133">[프로시저](./index.md) </span><span class="sxs-lookup"><span data-stu-id="10a9a-133">[Procedures](./index.md) </span></span>  
<span data-ttu-id="10a9a-134"> [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="10a9a-134"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="10a9a-135"> [방법: 프로시저에 인수 전달](./how-to-pass-arguments-to-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="10a9a-135"> [How to: Pass Arguments to a Procedure](./how-to-pass-arguments-to-a-procedure.md) </span></span>  
<span data-ttu-id="10a9a-136"> [값 및 참조로 인수 전달](./passing-arguments-by-value-and-by-reference.md) </span><span class="sxs-lookup"><span data-stu-id="10a9a-136"> [Passing Arguments by Value and by Reference](./passing-arguments-by-value-and-by-reference.md) </span></span>  
<span data-ttu-id="10a9a-137"> [수정할 수 있는 인수와 수정할 수 없는 인수 사이의 차이점](./differences-between-modifiable-and-nonmodifiable-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="10a9a-137"> [Differences Between Modifiable and Nonmodifiable Arguments](./differences-between-modifiable-and-nonmodifiable-arguments.md) </span></span>  
<span data-ttu-id="10a9a-138"> [참조 및 값으로 인수를 전달 간의 차이점](./differences-between-passing-an-argument-by-value-and-by-reference.md) </span><span class="sxs-lookup"><span data-stu-id="10a9a-138"> [Differences Between Passing an Argument By Value and By Reference](./differences-between-passing-an-argument-by-value-and-by-reference.md) </span></span>  
<span data-ttu-id="10a9a-139"> [방법: 프로시저 인수의 값 변경](./how-to-change-the-value-of-a-procedure-argument.md) </span><span class="sxs-lookup"><span data-stu-id="10a9a-139"> [How to: Change the Value of a Procedure Argument](./how-to-change-the-value-of-a-procedure-argument.md) </span></span>  
<span data-ttu-id="10a9a-140"> [방법: 값 변경에 대해 프로시저 인수 보호](./how-to-protect-a-procedure-argument-against-value-changes.md) </span><span class="sxs-lookup"><span data-stu-id="10a9a-140"> [How to: Protect a Procedure Argument Against Value Changes](./how-to-protect-a-procedure-argument-against-value-changes.md) </span></span>  
<span data-ttu-id="10a9a-141"> [위치 및 이름으로 인수 전달](./passing-arguments-by-position-and-by-name.md) </span><span class="sxs-lookup"><span data-stu-id="10a9a-141"> [Passing Arguments by Position and by Name](./passing-arguments-by-position-and-by-name.md) </span></span>  
<span data-ttu-id="10a9a-142"> [값 형식과 참조 형식](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)</span><span class="sxs-lookup"><span data-stu-id="10a9a-142"> [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)</span></span>
