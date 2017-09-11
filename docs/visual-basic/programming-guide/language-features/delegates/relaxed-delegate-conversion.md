---
title: "완화 대리자 변환 (Visual Basic) | Microsoft 문서"
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
- relaxed delegate conversion [Visual Basic]
- delegates [Visual Basic], relaxed conversion
- conversions, relaxed delegate
ms.assetid: 64f371d0-5416-4f65-b23b-adcbf556e81c
caps.latest.revision: 19
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
ms.openlocfilehash: 016c808145f7faba26a288cd5075f10d7f5279d5
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="relaxed-delegate-conversion-visual-basic"></a><span data-ttu-id="7b403-102">완화된 대리자 변환(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7b403-102">Relaxed Delegate Conversion (Visual Basic)</span></span>
<span data-ttu-id="7b403-103">완화 된 대리자 변환에는 해당 서명이 동일 하지 않은 경우에 처리기에 sub 및 함수를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b403-103">Relaxed delegate conversion enables you to assign subs and functions to delegates or handlers even when their signatures are not identical.</span></span> <span data-ttu-id="7b403-104">따라서, 대리자에 대 한 바인딩 메서드 호출에 대해 이미 허용 된 바인딩과 일치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b403-104">Therefore, binding to delegates becomes consistent with the binding already allowed for method invocations.</span></span>  
  
## <a name="parameters-and-return-type"></a><span data-ttu-id="7b403-105">매개 변수 및 반환 형식</span><span class="sxs-lookup"><span data-stu-id="7b403-105">Parameters and Return Type</span></span>  
 <span data-ttu-id="7b403-106">서명이 완전히 일치 하는 대신 완화 된 변환을 수행 하려면 다음 조건이 충족 될 때 `Option Strict` 로 설정 된 `On`:</span><span class="sxs-lookup"><span data-stu-id="7b403-106">In place of exact signature match, relaxed conversion requires that the following conditions be met when `Option Strict` is set to `On`:</span></span>  
  
-   <span data-ttu-id="7b403-107">확대 변환에서 각 대리자 매개 변수의 데이터 형식에서 할당 된 함수는 해당 매개 변수의 데이터 형식에 존재 해야 합니다 또는 `Sub`합니다.</span><span class="sxs-lookup"><span data-stu-id="7b403-107">A widening conversion must exist from the data type of each delegate parameter to the data type of the corresponding parameter of the assigned function or `Sub`.</span></span> <span data-ttu-id="7b403-108">다음 예제에서는 대리자에서에서 `Del1` 하나의 매개 변수가 있는 `Integer`합니다.</span><span class="sxs-lookup"><span data-stu-id="7b403-108">In the following example, the delegate `Del1` has one parameter, an `Integer`.</span></span> <span data-ttu-id="7b403-109">매개 변수 `m` 할당된 된 람다 식에서 확대 변환 되는 데이터 형식이 있어야 `Integer`, 예: `Long` 또는 `Double`합니다.</span><span class="sxs-lookup"><span data-stu-id="7b403-109">Parameter `m` in the assigned lambda expressions must have a data type for which there is a widening conversion from `Integer`, such as `Long` or `Double`.</span></span>  
  
     <span data-ttu-id="7b403-110">[!code-vb[VbVbalrRelaxedDelegates #&1;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="7b403-110">[!code-vb[VbVbalrRelaxedDelegates#1](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_1.vb)]</span></span>  
  
     <span data-ttu-id="7b403-111">[!code-vb[VbVbalrRelaxedDelegates #&2;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="7b403-111">[!code-vb[VbVbalrRelaxedDelegates#2](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_2.vb)]</span></span>  
  
     <span data-ttu-id="7b403-112">축소 변환에는 경우에만 허용 됩니다 `Option Strict` 로 설정 된 `Off`합니다.</span><span class="sxs-lookup"><span data-stu-id="7b403-112">Narrowing conversions are permitted only when `Option Strict` is set to `Off`.</span></span>  
  
     <span data-ttu-id="7b403-113">[!code-vb[VbVbalrRelaxedDelegates #&8;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="7b403-113">[!code-vb[VbVbalrRelaxedDelegates#8](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_3.vb)]</span></span>  
  
-   <span data-ttu-id="7b403-114">확대 변환 할당 된 함수의 반환 형식에서 반대 방향으로 존재 해야 합니다 또는 `Sub` 대리자의 반환 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7b403-114">A widening conversion must exist in the opposite direction from the return type of the assigned function or `Sub` to the return type of the delegate.</span></span> <span data-ttu-id="7b403-115">다음 예제에서 각 할당 된 람다 식의 본문은 확대 변환 되는 데이터 형식으로 계산 되어야 `Integer` 의 반환 형식이 때문에 `del1` 는 `Integer`합니다.</span><span class="sxs-lookup"><span data-stu-id="7b403-115">In the following examples, the body of each assigned lambda expression must evaluate to a data type that widens to `Integer` because the return type of `del1` is `Integer`.</span></span>  
  
     <span data-ttu-id="7b403-116">[!code-vb[VbVbalrRelaxedDelegates #&3;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="7b403-116">[!code-vb[VbVbalrRelaxedDelegates#3](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_4.vb)]</span></span>  
  
 <span data-ttu-id="7b403-117">경우 `Option Strict` 로 설정 된 `Off`, 제한 확대 각 방향에서 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b403-117">If `Option Strict` is set to `Off`, the widening restriction is removed in both directions.</span></span>  
  
 <span data-ttu-id="7b403-118">[!code-vb[VbVbalrRelaxedDelegates #&4;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="7b403-118">[!code-vb[VbVbalrRelaxedDelegates#4](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_5.vb)]</span></span>  
  
## <a name="omitting-parameter-specifications"></a><span data-ttu-id="7b403-119">매개 변수 사양 생략</span><span class="sxs-lookup"><span data-stu-id="7b403-119">Omitting Parameter Specifications</span></span>  
 <span data-ttu-id="7b403-120">완화 된 대리자 할당 된 메서드에서 매개 변수 사양 완전히 생략할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b403-120">Relaxed delegates also allow you to completely omit parameter specifications in the assigned method:</span></span>  
  
 <span data-ttu-id="7b403-121">[!code-vb[VbVbalrRelaxedDelegates #&5;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="7b403-121">[!code-vb[VbVbalrRelaxedDelegates#5](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_6.vb)]</span></span>  
  
 <span data-ttu-id="7b403-122">[!code-vb[VbVbalrRelaxedDelegates #&6;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="7b403-122">[!code-vb[VbVbalrRelaxedDelegates#6](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_7.vb)]</span></span>  
  
 <span data-ttu-id="7b403-123">참고 일부 매개 변수를 지정 되 고 다른 사용자를 생략할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7b403-123">Note that you cannot specify some parameters and omit others.</span></span>  
  
 <span data-ttu-id="7b403-124">[!code-vb[VbVbalrRelaxedDelegates #&15;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_8.vb)]</span><span class="sxs-lookup"><span data-stu-id="7b403-124">[!code-vb[VbVbalrRelaxedDelegates#15](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_8.vb)]</span></span>  
  
 <span data-ttu-id="7b403-125">매개 변수를 생략 하는 기능 몇 가지 복잡 한 매개 변수 수행 되는 이벤트 처리기를 정의 하는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b403-125">The ability to omit parameters is helpful in a situation such as defining an event handler, where several complex parameters are involved.</span></span> <span data-ttu-id="7b403-126">일부 이벤트 처리기에 대 한 인수는 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7b403-126">The arguments to some event handlers are not used.</span></span> <span data-ttu-id="7b403-127">대신, 처리기는 이벤트를 등록 하 고는 인수를 무시 하는 컨트롤의 상태를 직접 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b403-127">Instead, the handler directly accesses the state of the control on which the event is registered, and ignores the arguments.</span></span> <span data-ttu-id="7b403-128">완화 된 대리자를 통해 모호성이 없는 선언에서 인수를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b403-128">Relaxed delegates allow you to omit the arguments in such declarations when no ambiguities result.</span></span> <span data-ttu-id="7b403-129">다음 예제에서는 완전 하 게 지정 된 메서드가에서 `OnClick` 으로 다시 작성할 수 있습니다 `RelaxedOnClick`합니다.</span><span class="sxs-lookup"><span data-stu-id="7b403-129">In the following example, the fully specified method `OnClick` can be rewritten as `RelaxedOnClick`.</span></span>  
  
```vb  
Sub OnClick(ByVal sender As Object, ByVal e As EventArgs) Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
  
Sub RelaxedOnClick() Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
```  
  
## <a name="addressof-examples"></a><span data-ttu-id="7b403-130">AddressOf 예제</span><span class="sxs-lookup"><span data-stu-id="7b403-130">AddressOf Examples</span></span>  
 <span data-ttu-id="7b403-131">람다 식은 형식 관계를 쉽게 확인할 수 있도록 이전 예제에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b403-131">Lambda expressions are used in the previous examples to make the type relationships easy to see.</span></span> <span data-ttu-id="7b403-132">동일한 relaxations 사용 하는 대리자 할당에 허용 되는 반면 `AddressOf`, `Handles`, 또는 `AddHandler`합니다.</span><span class="sxs-lookup"><span data-stu-id="7b403-132">However, the same relaxations are permitted for delegate assignments that use `AddressOf`, `Handles`, or `AddHandler`.</span></span>  
  
 <span data-ttu-id="7b403-133">다음 예제에서는 함수 `f1`, `f2`, `f3`, 및 `f4` 모두에 할당할 수 있습니다 `Del1`합니다.</span><span class="sxs-lookup"><span data-stu-id="7b403-133">In the following example, functions `f1`, `f2`, `f3`, and `f4` can all be assigned to `Del1`.</span></span>  
  
 <span data-ttu-id="7b403-134">[!code-vb[VbVbalrRelaxedDelegates #&1;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="7b403-134">[!code-vb[VbVbalrRelaxedDelegates#1](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_1.vb)]</span></span>  
  
 <span data-ttu-id="7b403-135">[!code-vb[VbVbalrRelaxedDelegates #&7;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_9.vb)]</span><span class="sxs-lookup"><span data-stu-id="7b403-135">[!code-vb[VbVbalrRelaxedDelegates#7](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_9.vb)]</span></span>  
  
 <span data-ttu-id="7b403-136">[!code-vb[VbVbalrRelaxedDelegates #&9;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_10.vb)]</span><span class="sxs-lookup"><span data-stu-id="7b403-136">[!code-vb[VbVbalrRelaxedDelegates#9](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_10.vb)]</span></span>  
  
 <span data-ttu-id="7b403-137">다음 예제는 경우에만 유효 `Option Strict` 로 설정 된 `Off`합니다.</span><span class="sxs-lookup"><span data-stu-id="7b403-137">The following example is valid only when `Option Strict` is set to `Off`.</span></span>  
  
 <span data-ttu-id="7b403-138">[!code-vb[VbVbalrRelaxedDelegates #&14;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_11.vb)]</span><span class="sxs-lookup"><span data-stu-id="7b403-138">[!code-vb[VbVbalrRelaxedDelegates#14](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_11.vb)]</span></span>  
  
## <a name="dropping-function-returns"></a><span data-ttu-id="7b403-139">함수 반환 값 삭제</span><span class="sxs-lookup"><span data-stu-id="7b403-139">Dropping Function Returns</span></span>  
 <span data-ttu-id="7b403-140">완화 된 대리자 변환을 사용 하면 함수를 할당 하는 `Sub` 대리자를 효과적으로 함수의 반환 값을 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b403-140">Relaxed delegate conversion enables you to assign a function to a `Sub` delegate, effectively ignoring the return value of the function.</span></span> <span data-ttu-id="7b403-141">그러나, 할당할 수 없습니다는 `Sub` 함수 대리자입니다.</span><span class="sxs-lookup"><span data-stu-id="7b403-141">However, you cannot assign a `Sub` to a function delegate.</span></span> <span data-ttu-id="7b403-142">다음 예제에서는 함수의 주소에서에서 `doubler` 에 할당 된 `Sub` 위임 `Del3`합니다.</span><span class="sxs-lookup"><span data-stu-id="7b403-142">In the following example, the address of function `doubler` is assigned to `Sub` delegate `Del3`.</span></span>  
  
 <span data-ttu-id="7b403-143">[!code-vb[VbVbalrRelaxedDelegates #&10;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_12.vb)]</span><span class="sxs-lookup"><span data-stu-id="7b403-143">[!code-vb[VbVbalrRelaxedDelegates#10](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_12.vb)]</span></span>  
  
 <span data-ttu-id="7b403-144">[!code-vb[VbVbalrRelaxedDelegates #&11;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_13.vb)]</span><span class="sxs-lookup"><span data-stu-id="7b403-144">[!code-vb[VbVbalrRelaxedDelegates#11](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_13.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b403-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7b403-145">See Also</span></span>  
 <span data-ttu-id="7b403-146">[람다 식](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="7b403-146">[Lambda Expressions](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md) </span></span>  
<span data-ttu-id="7b403-147"> [확대 변환과 축소 변환](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="7b403-147"> [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) </span></span>  
<span data-ttu-id="7b403-148"> [대리자](../../../../visual-basic/programming-guide/language-features/delegates/index.md) </span><span class="sxs-lookup"><span data-stu-id="7b403-148"> [Delegates](../../../../visual-basic/programming-guide/language-features/delegates/index.md) </span></span>  
<span data-ttu-id="7b403-149"> [방법: 프로시저에 Visual Basic에서 다른 프로시저 전달](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="7b403-149"> [How to: Pass Procedures to Another Procedure in Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md) </span></span>  
<span data-ttu-id="7b403-150"> [지역 형식 유추](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) </span><span class="sxs-lookup"><span data-stu-id="7b403-150"> [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) </span></span>  
<span data-ttu-id="7b403-151"> [Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md)</span><span class="sxs-lookup"><span data-stu-id="7b403-151"> [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)</span></span>
