---
title: "방법: 값 변경 (Visual Basic)에 대해 프로시저 인수 보호 | Microsoft 문서"
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
- arguments [Visual Basic], passing by reference
- Visual Basic code, procedures
- arguments [Visual Basic], ByVal
- arguments [Visual Basic], passing by value
- procedure parameters
- procedures, calling
- arguments [Visual Basic], ByRef
- arguments [Visual Basic], changing value
ms.assetid: d2b7c766-ce16-4d2c-8d79-3fc0e7ba2227
caps.latest.revision: 14
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
ms.openlocfilehash: db40b3426256e7789a5273ab4d0afc8d5b47c8a7
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-protect-a-procedure-argument-against-value-changes-visual-basic"></a><span data-ttu-id="8e603-102">방법: 값 변경에 대해 프로시저 인수 보호(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8e603-102">How to: Protect a Procedure Argument Against Value Changes (Visual Basic)</span></span>
<span data-ttu-id="8e603-103">프로시저는 매개 변수를 선언 하는 경우 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 프로시저 코드에 호출 코드에서 인수를 기본 프로그래밍 요소에 대 한 직접 참조를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e603-103">If a procedure declares a parameter as [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] gives the procedure code a direct reference to the programming element underlying the argument in the calling code.</span></span> <span data-ttu-id="8e603-104">이렇게 하면 호출 코드에서 인수를 내부 값을 변경 하는 절차입니다.</span><span class="sxs-lookup"><span data-stu-id="8e603-104">This permits the procedure to change the value underlying the argument in the calling code.</span></span> <span data-ttu-id="8e603-105">일부 경우에 호출 코드에서 이러한 변경 으로부터 보호 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e603-105">In some cases the calling code might want to protect against such a change.</span></span>  
  
 <span data-ttu-id="8e603-106">해당 매개 변수를 선언 하 여 변경에서 인수를 항상 방지할 수 있습니다 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) 절차에서입니다.</span><span class="sxs-lookup"><span data-stu-id="8e603-106">You can always protect an argument from change by declaring the corresponding parameter [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) in the procedure.</span></span> <span data-ttu-id="8e603-107">일부 경우에는 지정 된 인수가 변경 하려는 경우 파일에 선언할 수 `ByRef` 호출 코드에서 각 호출에 전달 메커니즘을 결정 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e603-107">If you want to be able to change a given argument in some cases but not others, you can declare it `ByRef` and let the calling code determine the passing mechanism in each call.</span></span> <span data-ttu-id="8e603-108">해당 하는 인수를 값에 의해 전달를 괄호로 묶어 또는 참조로 전달 하는 괄호에 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e603-108">It does this by enclosing the corresponding argument in parentheses to pass it by value, or not enclosing it in parentheses to pass it by reference.</span></span> <span data-ttu-id="8e603-109">자세한 내용은 참조 [하는 방법: 인수가 값으로 전달 되도록 설정](./how-to-force-an-argument-to-be-passed-by-value.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8e603-109">For more information, see [How to: Force an Argument to Be Passed by Value](./how-to-force-an-argument-to-be-passed-by-value.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e603-110">예제</span><span class="sxs-lookup"><span data-stu-id="8e603-110">Example</span></span>  
 <span data-ttu-id="8e603-111">다음 예제에서는 요소를 사용 하는 배열 변수를 받아 두 가지 절차를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8e603-111">The following example shows two procedures that take an array variable and operate on its elements.</span></span> <span data-ttu-id="8e603-112">`increase` 프로시저 단순히 각 요소에&1;을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e603-112">The `increase` procedure simply adds one to each element.</span></span> <span data-ttu-id="8e603-113">`replace` 프로시저 매개 변수에 새 배열을 할당 `a()` 다음 각 요소에&1;을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e603-113">The `replace` procedure assigns a new array to the parameter `a()` and then adds one to each element.</span></span> <span data-ttu-id="8e603-114">그러나 다시 할당 호출 코드의 내부 배열 변수 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e603-114">However, the reassignment does not affect the underlying array variable in the calling code.</span></span>  
  
 <span data-ttu-id="8e603-115">[!code-vb[VbVbcnProcedures #&35;](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="8e603-115">[!code-vb[VbVbcnProcedures#35](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_1.vb)]</span></span>  
  
 <span data-ttu-id="8e603-116">[!code-vb[VbVbcnProcedures #&38;](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="8e603-116">[!code-vb[VbVbcnProcedures#38](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_2.vb)]</span></span>  
  
 <span data-ttu-id="8e603-117">[!code-vb[VbVbcnProcedures #&37;](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="8e603-117">[!code-vb[VbVbcnProcedures#37](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_3.vb)]</span></span>  
  
 <span data-ttu-id="8e603-118">첫 번째 `MsgBox` 표시 호출 "increase(n) 후: 11, 21, 31, 41"입니다.</span><span class="sxs-lookup"><span data-stu-id="8e603-118">The first `MsgBox` call displays "After increase(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="8e603-119">때문에 배열의 `n` 참조 형식인 `replace` 전달 메커니즘은 경우에 해당 멤버를 변경할 수 `ByVal`합니다.</span><span class="sxs-lookup"><span data-stu-id="8e603-119">Because the array `n` is a reference type, `replace` can change its members, even though the passing mechanism is `ByVal`.</span></span>  
  
 <span data-ttu-id="8e603-120">두 번째 `MsgBox` 표시 호출 "replace(n) 후: 11, 21, 31, 41"입니다.</span><span class="sxs-lookup"><span data-stu-id="8e603-120">The second `MsgBox` call displays "After replace(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="8e603-121">때문에 `n` 전달 `ByVal`, `replace` 변수를 수정할 수 없습니다 `n` 새 배열에 할당 하 여 호출 코드에서.</span><span class="sxs-lookup"><span data-stu-id="8e603-121">Because `n` is passed `ByVal`, `replace` cannot modify the variable `n` in the calling code by assigning a new array to it.</span></span> <span data-ttu-id="8e603-122">때 `replace` 새 배열 인스턴스를 만듭니다 `k` 로컬 변수에 할당 하 고 `a`에 대 한 참조를 잃을 `n` 호출 코드에 의해 전달 된 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e603-122">When `replace` creates the new array instance `k` and assigns it to the local variable `a`, it loses the reference to `n` passed in by the calling code.</span></span> <span data-ttu-id="8e603-123">멤버를 변경할 때 `a`, 지역 배열만 `k` 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="8e603-123">When it changes the members of `a`, only the local array `k` is affected.</span></span> <span data-ttu-id="8e603-124">따라서 `replace` 배열의 값을 늘리지 않습니다 `n` 호출 코드에서.</span><span class="sxs-lookup"><span data-stu-id="8e603-124">Therefore, `replace` does not increment the values of array `n` in the calling code.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8e603-125">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="8e603-125">Compiling the Code</span></span>  
 <span data-ttu-id="8e603-126">대화 상자에서 기본 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 값으로 인수를 전달 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8e603-126">The default in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] is to pass arguments by value.</span></span> <span data-ttu-id="8e603-127">그러나 것이 바람직한 프로그래밍 습관 하나를 포함 하는 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) 또는 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) 키워드 선언 된 모든 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e603-127">However, it is good programming practice to include either the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="8e603-128">이렇게 하면 코드를 보다 쉽게 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e603-128">This makes your code easier to read.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e603-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8e603-129">See Also</span></span>  
 <span data-ttu-id="8e603-130">[프로시저](./index.md) </span><span class="sxs-lookup"><span data-stu-id="8e603-130">[Procedures](./index.md) </span></span>  
<span data-ttu-id="8e603-131"> [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="8e603-131"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="8e603-132"> [방법: 프로시저에 인수 전달](./how-to-pass-arguments-to-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="8e603-132"> [How to: Pass Arguments to a Procedure](./how-to-pass-arguments-to-a-procedure.md) </span></span>  
<span data-ttu-id="8e603-133"> [값 및 참조로 인수 전달](./passing-arguments-by-value-and-by-reference.md) </span><span class="sxs-lookup"><span data-stu-id="8e603-133"> [Passing Arguments by Value and by Reference](./passing-arguments-by-value-and-by-reference.md) </span></span>  
<span data-ttu-id="8e603-134"> [수정할 수 있는 인수와 수정할 수 없는 인수 사이의 차이점](./differences-between-modifiable-and-nonmodifiable-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="8e603-134"> [Differences Between Modifiable and Nonmodifiable Arguments](./differences-between-modifiable-and-nonmodifiable-arguments.md) </span></span>  
<span data-ttu-id="8e603-135"> [참조 및 값으로 인수를 전달 간의 차이점](./differences-between-passing-an-argument-by-value-and-by-reference.md) </span><span class="sxs-lookup"><span data-stu-id="8e603-135"> [Differences Between Passing an Argument By Value and By Reference](./differences-between-passing-an-argument-by-value-and-by-reference.md) </span></span>  
<span data-ttu-id="8e603-136"> [방법: 프로시저 인수의 값 변경](./how-to-change-the-value-of-a-procedure-argument.md) </span><span class="sxs-lookup"><span data-stu-id="8e603-136"> [How to: Change the Value of a Procedure Argument](./how-to-change-the-value-of-a-procedure-argument.md) </span></span>  
<span data-ttu-id="8e603-137"> [방법: 인수가 값으로 전달 되도록 설정](./how-to-force-an-argument-to-be-passed-by-value.md) </span><span class="sxs-lookup"><span data-stu-id="8e603-137"> [How to: Force an Argument to Be Passed by Value](./how-to-force-an-argument-to-be-passed-by-value.md) </span></span>  
<span data-ttu-id="8e603-138"> [위치 및 이름으로 인수 전달](./passing-arguments-by-position-and-by-name.md) </span><span class="sxs-lookup"><span data-stu-id="8e603-138"> [Passing Arguments by Position and by Name](./passing-arguments-by-position-and-by-name.md) </span></span>  
<span data-ttu-id="8e603-139"> [값 형식과 참조 형식](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)</span><span class="sxs-lookup"><span data-stu-id="8e603-139"> [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)</span></span>
