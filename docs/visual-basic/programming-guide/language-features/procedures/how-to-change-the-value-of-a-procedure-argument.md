---
title: '방법: 프로시저 인수의 값 변경(Visual Basic)'
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
- arguments [Visual Basic], ByRef
- arguments [Visual Basic], changing value
ms.assetid: 6fad2368-5da7-4c07-8bf8-0f4e65a1be67
ms.openlocfilehash: 118dd3389804794801d39e7d67b68ab195bbad3a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33655839"
---
# <a name="how-to-change-the-value-of-a-procedure-argument-visual-basic"></a><span data-ttu-id="1953c-102">방법: 프로시저 인수의 값 변경(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1953c-102">How to: Change the Value of a Procedure Argument (Visual Basic)</span></span>
<span data-ttu-id="1953c-103">프로시저를 호출할 때 각 인수를 제공 하는 프로시저에 정의 된 매개 변수 중 하나에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="1953c-103">When you call a procedure, each argument you supply corresponds to one of the parameters defined in the procedure.</span></span> <span data-ttu-id="1953c-104">경우에 따라 프로시저 코드에서 호출 코드의 기반이 되는 값을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1953c-104">In some cases, the procedure code can change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="1953c-105">다른 경우에 프로시저 자체 로컬 복사본 인수를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1953c-105">In other cases, the procedure can change only its local copy of an argument.</span></span>  
  
 <span data-ttu-id="1953c-106">Visual Basic 전달 되는 모든 인수의 로컬 복사본을 만듭니다는 프로시저를 호출할 때 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1953c-106">When you call the procedure, Visual Basic makes a local copy of every argument that is passed [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span></span> <span data-ttu-id="1953c-107">각 인수에 대해 전달 된 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic 프로시저 코드에 호출 코드의 기반이 되는 프로그래밍 요소에 대 한 직접 참조를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1953c-107">For each argument passed [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic gives the procedure code a direct reference to the programming element underlying the argument in the calling code.</span></span>  
  
 <span data-ttu-id="1953c-108">호출 코드에서 해당 요소는 수정할 수 있고 인수가 전달 될 경우 `ByRef`, 프로시저 코드 호출 코드에서 요소의 값을 변경 하려면 직접 참조를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1953c-108">If the underlying element in the calling code is a modifiable element and the argument is passed `ByRef`, the procedure code can use the direct reference to change the element's value in the calling code.</span></span>  
  
## <a name="changing-the-underlying-value"></a><span data-ttu-id="1953c-109">내부 값을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="1953c-109">Changing the Underlying Value</span></span>  
  
#### <a name="to-change-the-underlying-value-of-a-procedure-argument-in-the-calling-code"></a><span data-ttu-id="1953c-110">프로시저 인수를 호출 하는 코드에 기본 값을 변경 하려면</span><span class="sxs-lookup"><span data-stu-id="1953c-110">To change the underlying value of a procedure argument in the calling code</span></span>  
  
1.  <span data-ttu-id="1953c-111">프로시저 선언에서 지정 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) 인수에 해당 하는 매개 변수에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="1953c-111">In the procedure declaration, specify [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) for the parameter corresponding to the argument.</span></span>  
  
2.  <span data-ttu-id="1953c-112">호출 코드에서 수정할 수 있는 프로그래밍 요소를 인수로 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="1953c-112">In the calling code, pass a modifiable programming element as the argument.</span></span>  
  
3.  <span data-ttu-id="1953c-113">호출 코드에서 인수를 인수 목록에 괄호로 묶지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="1953c-113">In the calling code, do not enclose the argument in parentheses in the argument list.</span></span>  
  
4.  <span data-ttu-id="1953c-114">프로시저 코드에서 매개 변수 이름을 사용 하 여 호출 코드에서 해당 요소에 값을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="1953c-114">In the procedure code, use the parameter name to assign a value to the underlying element in the calling code.</span></span>  
  
 <span data-ttu-id="1953c-115">예제를 참조 하십시오 데모를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="1953c-115">See the example further down for a demonstration.</span></span>  
  
## <a name="changing-local-copies"></a><span data-ttu-id="1953c-116">로컬 복사본을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="1953c-116">Changing Local Copies</span></span>  
 <span data-ttu-id="1953c-117">호출 코드에서 기본 요소는 수정할 수 없는 요소 또는 인수가 전달 될 경우 `ByVal`, 프로시저가 호출 코드에서 해당 값을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1953c-117">If the underlying element in the calling code is a nonmodifiable element, or if the argument is passed `ByVal`, the procedure cannot change its value in the calling code.</span></span> <span data-ttu-id="1953c-118">그러나 프로시저 이러한 인수의 자체 로컬 복사본을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1953c-118">However, the procedure can change its local copy of such an argument.</span></span>  
  
#### <a name="to-change-the-copy-of-a-procedure-argument-in-the-procedure-code"></a><span data-ttu-id="1953c-119">프로시저 코드의 프로시저 인수의 복사본을 변경 하려면</span><span class="sxs-lookup"><span data-stu-id="1953c-119">To change the copy of a procedure argument in the procedure code</span></span>  
  
1.  <span data-ttu-id="1953c-120">프로시저 선언에서 지정 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) 인수에 해당 하는 매개 변수에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="1953c-120">In the procedure declaration, specify [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) for the parameter corresponding to the argument.</span></span>  
  
     <span data-ttu-id="1953c-121">-또는-</span><span class="sxs-lookup"><span data-stu-id="1953c-121">-or-</span></span>  
  
     <span data-ttu-id="1953c-122">호출 코드에서 인수 목록의 괄호 안에 인수를 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="1953c-122">In the calling code, enclose the argument in parentheses in the argument list.</span></span> <span data-ttu-id="1953c-123">이렇게 하면 Visual Basic 값으로 인수를 전달 하 여 해당 매개 변수를 지정 하는 경우에 `ByRef`합니다.</span><span class="sxs-lookup"><span data-stu-id="1953c-123">This forces Visual Basic to pass the argument by value, even if the corresponding parameter specifies `ByRef`.</span></span>  
  
2.  <span data-ttu-id="1953c-124">프로시저 코드에서 매개 변수 이름을 사용 하 여 인수의 로컬 복사본에 값을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="1953c-124">In the procedure code, use the parameter name to assign a value to the local copy of the argument.</span></span> <span data-ttu-id="1953c-125">호출 코드에서 기본 값이 변경 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1953c-125">The underlying value in the calling code is not changed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1953c-126">예제</span><span class="sxs-lookup"><span data-stu-id="1953c-126">Example</span></span>  
 <span data-ttu-id="1953c-127">다음 예제에서는 요소를 사용 하는 배열 변수를 받아 두 개의 프로시저를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1953c-127">The following example shows two procedures that take an array variable and operate on its elements.</span></span> <span data-ttu-id="1953c-128">`increase` 프로시저 단순히 각 요소에 1을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="1953c-128">The `increase` procedure simply adds one to each element.</span></span> <span data-ttu-id="1953c-129">`replace` 프로시저 매개 변수는 새 배열을 할당 `a()` 다음 각 요소에 1을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="1953c-129">The `replace` procedure assigns a new array to the parameter `a()` and then adds one to each element.</span></span>  
  
 [!code-vb[VbVbcnProcedures#35](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#36](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#37](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_3.vb)]  
  
 <span data-ttu-id="1953c-130">첫 번째 `MsgBox` 표시 호출 "increase(n) 후: 11, 21, 31, 41"입니다.</span><span class="sxs-lookup"><span data-stu-id="1953c-130">The first `MsgBox` call displays "After increase(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="1953c-131">때문에 배열 `n` 참조 형식인 `replace` 전달 메커니즘이 해당 멤버를 변경할 수 있습니다 `ByVal`합니다.</span><span class="sxs-lookup"><span data-stu-id="1953c-131">Because the array `n` is a reference type, `replace` can change its members, even though the passing mechanism is `ByVal`.</span></span>  
  
 <span data-ttu-id="1953c-132">두 번째 `MsgBox` 표시 호출 "replace(n) 후: 101, 201, 301"입니다.</span><span class="sxs-lookup"><span data-stu-id="1953c-132">The second `MsgBox` call displays "After replace(n): 101, 201, 301".</span></span> <span data-ttu-id="1953c-133">때문에 `n` 전달 `ByRef`, `replace` 변수를 수정할 수 `n` 에 새 배열 할당할 고 호출 코드에서.</span><span class="sxs-lookup"><span data-stu-id="1953c-133">Because `n` is passed `ByRef`, `replace` can modify the variable `n` in the calling code and assign a new array to it.</span></span> <span data-ttu-id="1953c-134">때문에 `n` 참조 형식인 `replace` 해당 멤버를 변경할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1953c-134">Because `n` is a reference type, `replace` can also change its members.</span></span>  
  
 <span data-ttu-id="1953c-135">프로시저가 호출 코드에서 변수 자체를 수정할 수 없도록 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1953c-135">You can prevent the procedure from modifying the variable itself in the calling code.</span></span> <span data-ttu-id="1953c-136">참조 [하는 방법: 값 변경에 대해 프로시저 인수 보호](./how-to-protect-a-procedure-argument-against-value-changes.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1953c-136">See [How to: Protect a Procedure Argument Against Value Changes](./how-to-protect-a-procedure-argument-against-value-changes.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1953c-137">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="1953c-137">Compiling the Code</span></span>  
 <span data-ttu-id="1953c-138">참조 하 여 변수를 전달할 때 사용 해야는 `ByRef` 키워드가이 메커니즘을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1953c-138">When you pass a variable by reference, you must use the `ByRef` keyword to specify this mechanism.</span></span>  
  
 <span data-ttu-id="1953c-139">Visual Basic의 기본값인 값으로 인수 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="1953c-139">The default in Visual Basic is to pass arguments by value.</span></span> <span data-ttu-id="1953c-140">그러나 것이 바람직한 프로그래밍 습관 하나를 포함 하는 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) 또는 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) 키워드 모든 선언 된 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1953c-140">However, it is good programming practice to include either the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="1953c-141">이렇게 하면 코드를 보다 쉽게 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1953c-141">This makes your code easier to read.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="1953c-142">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="1953c-142">.NET Framework Security</span></span>  
 <span data-ttu-id="1953c-143">호출 코드의 기반이 되는 값을 변경 하는 절차를 허용할 경우 잠재적인 위험이 항상 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1953c-143">There is always a potential risk in allowing a procedure to change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="1953c-144">변경 되 고 사용 하기 전에 유효성을 검사할 수 있도록 준비 하려면이 값을 예상 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1953c-144">Make sure you expect this value to be changed, and be prepared to check it for validity before using it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1953c-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1953c-145">See Also</span></span>  
 [<span data-ttu-id="1953c-146">절차</span><span class="sxs-lookup"><span data-stu-id="1953c-146">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="1953c-147">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="1953c-147">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="1953c-148">방법: 프로시저에 인수 전달</span><span class="sxs-lookup"><span data-stu-id="1953c-148">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)  
 [<span data-ttu-id="1953c-149">값 또는 참조로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="1953c-149">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="1953c-150">수정할 수 있는 인수와 수정할 수 없는 인수 사이의 차이점</span><span class="sxs-lookup"><span data-stu-id="1953c-150">Differences Between Modifiable and Nonmodifiable Arguments</span></span>](./differences-between-modifiable-and-nonmodifiable-arguments.md)  
 [<span data-ttu-id="1953c-151">인수를 값으로 전달할 때와 참조로 전달할 때의 차이점</span><span class="sxs-lookup"><span data-stu-id="1953c-151">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)  
 [<span data-ttu-id="1953c-152">방법: 값 변경에 대해 프로시저 인수 보호</span><span class="sxs-lookup"><span data-stu-id="1953c-152">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)  
 [<span data-ttu-id="1953c-153">방법: 인수가 값으로 전달되도록 설정</span><span class="sxs-lookup"><span data-stu-id="1953c-153">How to: Force an Argument to Be Passed by Value</span></span>](./how-to-force-an-argument-to-be-passed-by-value.md)  
 [<span data-ttu-id="1953c-154">위치 및 이름으로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="1953c-154">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)  
 [<span data-ttu-id="1953c-155">값 형식과 참조 형식</span><span class="sxs-lookup"><span data-stu-id="1953c-155">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
