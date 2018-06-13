---
title: '방법: 값 변경에 대해 프로시저 인수 보호(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- procedure arguments
- arguments [Visual Basic], passing by reference
- Visual Basic code, procedures
- arguments [Visual Basic], ByVal
- arguments [Visual Basic], passing by value
- procedure parameters
- procedures [Visual Basic], calling
- arguments [Visual Basic], ByRef
- arguments [Visual Basic], changing value
ms.assetid: d2b7c766-ce16-4d2c-8d79-3fc0e7ba2227
ms.openlocfilehash: d2e131b770d8498a634d946a5900f9b373ca7e56
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33651520"
---
# <a name="how-to-protect-a-procedure-argument-against-value-changes-visual-basic"></a><span data-ttu-id="8ed42-102">방법: 값 변경에 대해 프로시저 인수 보호(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8ed42-102">How to: Protect a Procedure Argument Against Value Changes (Visual Basic)</span></span>
<span data-ttu-id="8ed42-103">프로시저 매개 변수로 선언 된 경우 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic 프로시저 코드에 호출 코드의 기반이 되는 프로그래밍 요소에 대 한 직접 참조를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ed42-103">If a procedure declares a parameter as [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic gives the procedure code a direct reference to the programming element underlying the argument in the calling code.</span></span> <span data-ttu-id="8ed42-104">이렇게 하면 프로시저가 호출 코드의 기반이 되는 값을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ed42-104">This permits the procedure to change the value underlying the argument in the calling code.</span></span> <span data-ttu-id="8ed42-105">일부 경우에서는 호출 코드에서 이러한 변경 으로부터 보호 하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ed42-105">In some cases the calling code might want to protect against such a change.</span></span>  
  
 <span data-ttu-id="8ed42-106">해당 매개 변수를 선언 하 여 변경 내용으로 인해 인수를 항상 방지할 수 있습니다 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) 절차에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ed42-106">You can always protect an argument from change by declaring the corresponding parameter [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) in the procedure.</span></span> <span data-ttu-id="8ed42-107">일부 경우에 지정 된 인수를 변경할 수 있게 되기를 원하는 경우 파일을 선언할 수 `ByRef` 호출 코드에서 각 호출에 전달 메커니즘을 결정 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ed42-107">If you want to be able to change a given argument in some cases but not others, you can declare it `ByRef` and let the calling code determine the passing mechanism in each call.</span></span> <span data-ttu-id="8ed42-108">해당 인수를 값으로 전달할 괄호로 묶어 또는 참조로 전달 하려면 괄호에 포함 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8ed42-108">It does this by enclosing the corresponding argument in parentheses to pass it by value, or not enclosing it in parentheses to pass it by reference.</span></span> <span data-ttu-id="8ed42-109">자세한 내용은 참조 [하는 방법: 인수가 값으로 전달 되도록 설정](./how-to-force-an-argument-to-be-passed-by-value.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8ed42-109">For more information, see [How to: Force an Argument to Be Passed by Value](./how-to-force-an-argument-to-be-passed-by-value.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ed42-110">예제</span><span class="sxs-lookup"><span data-stu-id="8ed42-110">Example</span></span>  
 <span data-ttu-id="8ed42-111">다음 예제에서는 요소를 사용 하는 배열 변수를 받아 두 개의 프로시저를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8ed42-111">The following example shows two procedures that take an array variable and operate on its elements.</span></span> <span data-ttu-id="8ed42-112">`increase` 프로시저 단순히 각 요소에 1을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ed42-112">The `increase` procedure simply adds one to each element.</span></span> <span data-ttu-id="8ed42-113">`replace` 프로시저 매개 변수는 새 배열을 할당 `a()` 다음 각 요소에 1을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ed42-113">The `replace` procedure assigns a new array to the parameter `a()` and then adds one to each element.</span></span> <span data-ttu-id="8ed42-114">그러나 다시 할당 호출 코드의 내부 배열 변수 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8ed42-114">However, the reassignment does not affect the underlying array variable in the calling code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#35](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#38](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#37](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_3.vb)]  
  
 <span data-ttu-id="8ed42-115">첫 번째 `MsgBox` 표시 호출 "increase(n) 후: 11, 21, 31, 41"입니다.</span><span class="sxs-lookup"><span data-stu-id="8ed42-115">The first `MsgBox` call displays "After increase(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="8ed42-116">때문에 배열 `n` 참조 형식인 `replace` 전달 메커니즘이 해당 멤버를 변경할 수 있습니다 `ByVal`합니다.</span><span class="sxs-lookup"><span data-stu-id="8ed42-116">Because the array `n` is a reference type, `replace` can change its members, even though the passing mechanism is `ByVal`.</span></span>  
  
 <span data-ttu-id="8ed42-117">두 번째 `MsgBox` 표시 호출 "replace(n) 후: 11, 21, 31, 41"입니다.</span><span class="sxs-lookup"><span data-stu-id="8ed42-117">The second `MsgBox` call displays "After replace(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="8ed42-118">때문에 `n` 전달 `ByVal`, `replace` 변수를 수정할 수 없습니다 `n` 새 배열을 할당 하 여 호출 코드에서.</span><span class="sxs-lookup"><span data-stu-id="8ed42-118">Because `n` is passed `ByVal`, `replace` cannot modify the variable `n` in the calling code by assigning a new array to it.</span></span> <span data-ttu-id="8ed42-119">때 `replace` 배열의 새 인스턴스를 만듭니다. `k` 로컬 변수에 할당 하 고 `a`에 대 한 참조를 잃을 `n` 호출 코드에 의해 전달 된입니다.</span><span class="sxs-lookup"><span data-stu-id="8ed42-119">When `replace` creates the new array instance `k` and assigns it to the local variable `a`, it loses the reference to `n` passed in by the calling code.</span></span> <span data-ttu-id="8ed42-120">멤버를 변경할 때 `a`, 지역 배열만 `k` 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="8ed42-120">When it changes the members of `a`, only the local array `k` is affected.</span></span> <span data-ttu-id="8ed42-121">따라서 `replace` 배열 값을 늘리지 않습니다 `n` 호출 코드에서.</span><span class="sxs-lookup"><span data-stu-id="8ed42-121">Therefore, `replace` does not increment the values of array `n` in the calling code.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8ed42-122">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="8ed42-122">Compiling the Code</span></span>  
 <span data-ttu-id="8ed42-123">Visual Basic의 기본값인 값으로 인수 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ed42-123">The default in Visual Basic is to pass arguments by value.</span></span> <span data-ttu-id="8ed42-124">그러나 것이 바람직한 프로그래밍 습관 하나를 포함 하는 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) 또는 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) 키워드 모든 선언 된 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ed42-124">However, it is good programming practice to include either the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="8ed42-125">이렇게 하면 코드를 보다 쉽게 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ed42-125">This makes your code easier to read.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ed42-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8ed42-126">See Also</span></span>  
 [<span data-ttu-id="8ed42-127">절차</span><span class="sxs-lookup"><span data-stu-id="8ed42-127">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="8ed42-128">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="8ed42-128">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="8ed42-129">방법: 프로시저에 인수 전달</span><span class="sxs-lookup"><span data-stu-id="8ed42-129">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)  
 [<span data-ttu-id="8ed42-130">값 또는 참조로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="8ed42-130">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="8ed42-131">수정할 수 있는 인수와 수정할 수 없는 인수 사이의 차이점</span><span class="sxs-lookup"><span data-stu-id="8ed42-131">Differences Between Modifiable and Nonmodifiable Arguments</span></span>](./differences-between-modifiable-and-nonmodifiable-arguments.md)  
 [<span data-ttu-id="8ed42-132">인수를 값으로 전달할 때와 참조로 전달할 때의 차이점</span><span class="sxs-lookup"><span data-stu-id="8ed42-132">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)  
 [<span data-ttu-id="8ed42-133">방법: 프로시저 인수의 값 변경</span><span class="sxs-lookup"><span data-stu-id="8ed42-133">How to: Change the Value of a Procedure Argument</span></span>](./how-to-change-the-value-of-a-procedure-argument.md)  
 [<span data-ttu-id="8ed42-134">방법: 인수가 값으로 전달되도록 설정</span><span class="sxs-lookup"><span data-stu-id="8ed42-134">How to: Force an Argument to Be Passed by Value</span></span>](./how-to-force-an-argument-to-be-passed-by-value.md)  
 [<span data-ttu-id="8ed42-135">위치 및 이름으로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="8ed42-135">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)  
 [<span data-ttu-id="8ed42-136">값 형식과 참조 형식</span><span class="sxs-lookup"><span data-stu-id="8ed42-136">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
