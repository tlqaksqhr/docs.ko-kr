---
title: 완화된 대리자 변환(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- relaxed delegate conversion [Visual Basic]
- delegates [Visual Basic], relaxed conversion
- conversions [Visual Basic], relaxed delegate
ms.assetid: 64f371d0-5416-4f65-b23b-adcbf556e81c
ms.openlocfilehash: c4a41bf74716a6ea7d3c1139651834acccf27657
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650831"
---
# <a name="relaxed-delegate-conversion-visual-basic"></a><span data-ttu-id="02b6f-102">완화된 대리자 변환(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="02b6f-102">Relaxed Delegate Conversion (Visual Basic)</span></span>
<span data-ttu-id="02b6f-103">완화 된 대리자 변환에는 해당 서명이 동일 하지 않은 경우에 처리기에 sub 및 함수를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02b6f-103">Relaxed delegate conversion enables you to assign subs and functions to delegates or handlers even when their signatures are not identical.</span></span> <span data-ttu-id="02b6f-104">따라서 대리자에는 바인딩이 이미 메서드 호출에 대해 허용 된 바인딩과 일치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02b6f-104">Therefore, binding to delegates becomes consistent with the binding already allowed for method invocations.</span></span>  
  
## <a name="parameters-and-return-type"></a><span data-ttu-id="02b6f-105">매개 변수 및 반환 형식</span><span class="sxs-lookup"><span data-stu-id="02b6f-105">Parameters and Return Type</span></span>  
 <span data-ttu-id="02b6f-106">서명이 완전히 일치 하는 대신 완화 된 변환 필요 합니다. 다음 조건이 충족 될 때 `Option Strict` 로 설정 된 `On`:</span><span class="sxs-lookup"><span data-stu-id="02b6f-106">In place of exact signature match, relaxed conversion requires that the following conditions be met when `Option Strict` is set to `On`:</span></span>  
  
-   <span data-ttu-id="02b6f-107">할당 된 함수는 해당 매개 변수의 데이터 형식으로 각 대리자 매개 변수의 데이터 형식에서 확대 변환이 있어야 또는 `Sub`합니다.</span><span class="sxs-lookup"><span data-stu-id="02b6f-107">A widening conversion must exist from the data type of each delegate parameter to the data type of the corresponding parameter of the assigned function or `Sub`.</span></span> <span data-ttu-id="02b6f-108">다음 예제에서는 대리자 `Del1` 하나의 매개 변수가 있는 `Integer`합니다.</span><span class="sxs-lookup"><span data-stu-id="02b6f-108">In the following example, the delegate `Del1` has one parameter, an `Integer`.</span></span> <span data-ttu-id="02b6f-109">매개 변수 `m` 할당된 된 람다 식에서의 확대 변환이 없는 데이터 형식이 있어야 `Integer`와 같은 `Long` 또는 `Double`합니다.</span><span class="sxs-lookup"><span data-stu-id="02b6f-109">Parameter `m` in the assigned lambda expressions must have a data type for which there is a widening conversion from `Integer`, such as `Long` or `Double`.</span></span>  
  
     [!code-vb[VbVbalrRelaxedDelegates#1](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_1.vb)]  
  
     [!code-vb[VbVbalrRelaxedDelegates#2](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_2.vb)]  
  
     <span data-ttu-id="02b6f-110">축소 변환은 경우에만 허용 됩니다 `Option Strict` 로 설정 된 `Off`합니다.</span><span class="sxs-lookup"><span data-stu-id="02b6f-110">Narrowing conversions are permitted only when `Option Strict` is set to `Off`.</span></span>  
  
     [!code-vb[VbVbalrRelaxedDelegates#8](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_3.vb)]  
  
-   <span data-ttu-id="02b6f-111">할당 된 함수 반환 형식에서 반대 방향으로 확대 변환이 있어야 합니다. 또는 `Sub` 대리자의 반환 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="02b6f-111">A widening conversion must exist in the opposite direction from the return type of the assigned function or `Sub` to the return type of the delegate.</span></span> <span data-ttu-id="02b6f-112">다음 예제에서 각 할당 된 람다 식의 본문으로 확대 되는 데이터 형식으로 계산 되어야 `Integer` 의 반환 형식인 `del1` 은 `Integer`합니다.</span><span class="sxs-lookup"><span data-stu-id="02b6f-112">In the following examples, the body of each assigned lambda expression must evaluate to a data type that widens to `Integer` because the return type of `del1` is `Integer`.</span></span>  
  
     [!code-vb[VbVbalrRelaxedDelegates#3](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_4.vb)]  
  
 <span data-ttu-id="02b6f-113">경우 `Option Strict` 로 설정 된 `Off`, 두 방향에서 제한 확대가 제거 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="02b6f-113">If `Option Strict` is set to `Off`, the widening restriction is removed in both directions.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#4](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_5.vb)]  
  
## <a name="omitting-parameter-specifications"></a><span data-ttu-id="02b6f-114">매개 변수 사양 생략</span><span class="sxs-lookup"><span data-stu-id="02b6f-114">Omitting Parameter Specifications</span></span>  
 <span data-ttu-id="02b6f-115">또한 완화 된 대리자를 통해 할당 된 메서드의 매개 변수 사양 완전히 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02b6f-115">Relaxed delegates also allow you to completely omit parameter specifications in the assigned method:</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#5](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_6.vb)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#6](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_7.vb)]  
  
 <span data-ttu-id="02b6f-116">참고 일부 매개 변수를 지정 되 고 다른 사용자를 생략할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="02b6f-116">Note that you cannot specify some parameters and omit others.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#15](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_8.vb)]  
  
 <span data-ttu-id="02b6f-117">매개 변수를 생략 하는 기능 복잡 한 여러 매개 변수 관련 된 이벤트 처리기를 정의 하는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="02b6f-117">The ability to omit parameters is helpful in a situation such as defining an event handler, where several complex parameters are involved.</span></span> <span data-ttu-id="02b6f-118">일부 이벤트 처리기에 대 한 인수는 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="02b6f-118">The arguments to some event handlers are not used.</span></span> <span data-ttu-id="02b6f-119">대신, 처리기 이벤트를 등록 및 인수를 무시 하는 컨트롤의 상태를 직접 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="02b6f-119">Instead, the handler directly accesses the state of the control on which the event is registered, and ignores the arguments.</span></span> <span data-ttu-id="02b6f-120">완화 된 대리자를 통해 모호성이 없는 선언에서 인수를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02b6f-120">Relaxed delegates allow you to omit the arguments in such declarations when no ambiguities result.</span></span> <span data-ttu-id="02b6f-121">다음 예제에서는 완전 하 게 지정 된 메서드 `OnClick` 로 다시 작성 `RelaxedOnClick`합니다.</span><span class="sxs-lookup"><span data-stu-id="02b6f-121">In the following example, the fully specified method `OnClick` can be rewritten as `RelaxedOnClick`.</span></span>  
  
```vb  
Sub OnClick(ByVal sender As Object, ByVal e As EventArgs) Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
  
Sub RelaxedOnClick() Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
```  
  
## <a name="addressof-examples"></a><span data-ttu-id="02b6f-122">AddressOf 예제</span><span class="sxs-lookup"><span data-stu-id="02b6f-122">AddressOf Examples</span></span>  
 <span data-ttu-id="02b6f-123">람다 식은 형식 관계를 쉽게 확인할 수 있도록 이전 예제에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="02b6f-123">Lambda expressions are used in the previous examples to make the type relationships easy to see.</span></span> <span data-ttu-id="02b6f-124">동일한 relaxations 사용 하는 대리자 할당에 허용 되는 반면 `AddressOf`, `Handles`, 또는 `AddHandler`합니다.</span><span class="sxs-lookup"><span data-stu-id="02b6f-124">However, the same relaxations are permitted for delegate assignments that use `AddressOf`, `Handles`, or `AddHandler`.</span></span>  
  
 <span data-ttu-id="02b6f-125">다음 예제에서는 작동 `f1`, `f2`, `f3`, 및 `f4` 모두에 할당할 수 있습니다 `Del1`합니다.</span><span class="sxs-lookup"><span data-stu-id="02b6f-125">In the following example, functions `f1`, `f2`, `f3`, and `f4` can all be assigned to `Del1`.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#1](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_1.vb)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#7](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_9.vb)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#9](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_10.vb)]  
  
 <span data-ttu-id="02b6f-126">다음 예제는 경우에만 유효 `Option Strict` 로 설정 된 `Off`합니다.</span><span class="sxs-lookup"><span data-stu-id="02b6f-126">The following example is valid only when `Option Strict` is set to `Off`.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#14](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_11.vb)]  
  
## <a name="dropping-function-returns"></a><span data-ttu-id="02b6f-127">함수 반환 값 삭제</span><span class="sxs-lookup"><span data-stu-id="02b6f-127">Dropping Function Returns</span></span>  
 <span data-ttu-id="02b6f-128">완화 된 대리자 변환을 사용 하면 함수를 할당할 수는 `Sub` 대리자를 효과적으로 함수의 반환 값을 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="02b6f-128">Relaxed delegate conversion enables you to assign a function to a `Sub` delegate, effectively ignoring the return value of the function.</span></span> <span data-ttu-id="02b6f-129">그러나, 할당할 수 없습니다는 `Sub` 함수 대리자입니다.</span><span class="sxs-lookup"><span data-stu-id="02b6f-129">However, you cannot assign a `Sub` to a function delegate.</span></span> <span data-ttu-id="02b6f-130">다음 예제에서는 함수의 주소로 `doubler` 에 할당 된 `Sub` 위임 `Del3`합니다.</span><span class="sxs-lookup"><span data-stu-id="02b6f-130">In the following example, the address of function `doubler` is assigned to `Sub` delegate `Del3`.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#10](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_12.vb)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#11](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_13.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="02b6f-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="02b6f-131">See Also</span></span>  
 [<span data-ttu-id="02b6f-132">람다 식</span><span class="sxs-lookup"><span data-stu-id="02b6f-132">Lambda Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)  
 [<span data-ttu-id="02b6f-133">확대 변환과 축소 변환</span><span class="sxs-lookup"><span data-stu-id="02b6f-133">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [<span data-ttu-id="02b6f-134">대리자</span><span class="sxs-lookup"><span data-stu-id="02b6f-134">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [<span data-ttu-id="02b6f-135">방법: Visual Basic에서 프로시저에 다른 프로시저 전달</span><span class="sxs-lookup"><span data-stu-id="02b6f-135">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)  
 [<span data-ttu-id="02b6f-136">지역 형식 유추</span><span class="sxs-lookup"><span data-stu-id="02b6f-136">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [<span data-ttu-id="02b6f-137">Option Strict 문</span><span class="sxs-lookup"><span data-stu-id="02b6f-137">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
