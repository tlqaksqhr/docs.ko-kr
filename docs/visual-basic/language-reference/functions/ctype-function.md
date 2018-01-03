---
title: "CType 함수(Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.CType
helpviewer_keywords:
- expression conversion results
- explicit data type conversions [Visual Basic]
- CType function
- conversions [Visual Basic], expression
ms.assetid: dd4b29e7-6fa1-428c-877e-69955420bb72
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d804ce75929592675068fdc434a1ba7429fa5373
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="ctype-function-visual-basic"></a><span data-ttu-id="896ab-102">CType 함수(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="896ab-102">CType Function (Visual Basic)</span></span>
<span data-ttu-id="896ab-103">명시적으로 지정 된 데이터 형식, 개체, 구조체, 클래스 또는 인터페이스에는 식을 변환한 결과를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="896ab-103">Returns the result of explicitly converting an expression to a specified data type, object, structure, class, or interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="896ab-104">구문</span><span class="sxs-lookup"><span data-stu-id="896ab-104">Syntax</span></span>  
  
```  
CType(expression, typename)  
```  
  
## <a name="parts"></a><span data-ttu-id="896ab-105">요소</span><span class="sxs-lookup"><span data-stu-id="896ab-105">Parts</span></span>  
 `expression`  
 <span data-ttu-id="896ab-106">모든 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="896ab-106">Any valid expression.</span></span> <span data-ttu-id="896ab-107">하는 경우의 값 `expression` 에서 허용 되는 범위를 벗어납니다 `typename`, Visual Basic 예외를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="896ab-107">If the value of `expression` is outside the range allowed by `typename`, Visual Basic throws an exception.</span></span>  
  
 `typename`  
 <span data-ttu-id="896ab-108">유효한 모든 식은 `As` 절에는 `Dim` 문, 즉, 데이터 형식, 개체, 구조체, 클래스 또는 인터페이스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="896ab-108">Any expression that is legal within an `As` clause in a `Dim` statement, that is, the name of any data type, object, structure, class, or interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="896ab-109">설명</span><span class="sxs-lookup"><span data-stu-id="896ab-109">Remarks</span></span>  
  
> [!TIP]
>  <span data-ttu-id="896ab-110">또한 형식 변환을 수행 하려면 다음 함수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="896ab-110">You can also use the following functions to perform a type conversion:</span></span>  
>   
>  -   <span data-ttu-id="896ab-111">변환 함수를 같은 입력 `CByte`, `CDbl`, 및 `CInt` 특정 데이터 형식으로의 변환을 수행 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="896ab-111">Type conversion functions such as `CByte`, `CDbl`, and `CInt` that perform a conversion to a specific data type.</span></span> <span data-ttu-id="896ab-112">자세한 내용은 참조 [형식 변환 함수](../../../visual-basic/language-reference/functions/type-conversion-functions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="896ab-112">For more information, see [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md).</span></span>  
> -   <span data-ttu-id="896ab-113">[DirectCast 연산자](../../../visual-basic/language-reference/operators/directcast-operator.md) 또는 [TryCast 연산자](../../../visual-basic/language-reference/operators/trycast-operator.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="896ab-113">[DirectCast Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) or [TryCast Operator](../../../visual-basic/language-reference/operators/trycast-operator.md).</span></span> <span data-ttu-id="896ab-114">이러한 연산자는 한 형식에서 상속 하거나 다른 형식을 구현에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="896ab-114">These operators require that one type inherit from or implement the other type.</span></span> <span data-ttu-id="896ab-115">보다 약간 더 나은 성능을 제공 하 `CType` 에서 변환 하는 경우는 `Object` 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="896ab-115">They can provide somewhat better performance than `CType` when converting to and from the `Object` data type.</span></span>  
  
 <span data-ttu-id="896ab-116">`CType`즉, 형식 변환 식을 계산 하는 코드의 일부 컴파일된 인라인으로가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="896ab-116">`CType` is compiled inline, which means that the conversion code is part of the code that evaluates the expression.</span></span> <span data-ttu-id="896ab-117">경우에 따라 코드가 더 빠르게 실행에서 변환을 수행할 호출 되므로 프로시저가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="896ab-117">In some cases, the code runs faster because no procedures are called to perform the conversion.</span></span>  
  
 <span data-ttu-id="896ab-118">정의 된 변환이 없는 경우 `expression` 를 `typename` (예:에서 `Integer` 를 `Date`), Visual Basic 컴파일 타임 오류 메시지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="896ab-118">If no conversion is defined from `expression` to `typename` (for example, from `Integer` to `Date`), Visual Basic displays a compile-time error message.</span></span>  
  
 <span data-ttu-id="896ab-119">런타임에 변환에 실패 하면 해당 예외가 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="896ab-119">If a conversion fails at run time, the appropriate exception is thrown.</span></span> <span data-ttu-id="896ab-120">축소 변환에 실패 하면는 <xref:System.OverflowException> 은 가장 일반적인 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="896ab-120">If a narrowing conversion fails, an <xref:System.OverflowException> is the most common result.</span></span> <span data-ttu-id="896ab-121">정의 되지 않으면 경우는 <xref:System.InvalidCastException> throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="896ab-121">If the conversion is undefined, an <xref:System.InvalidCastException> in thrown.</span></span> <span data-ttu-id="896ab-122">예를 들어 이러한 경우 `expression` 유형의 `Object` 해당 런타임 형식에는 변환 되지 않습니다 및 `typename`합니다.</span><span class="sxs-lookup"><span data-stu-id="896ab-122">For example, this can happen  if `expression` is of type `Object` and its run-time type has no conversion to `typename`.</span></span>  
  
 <span data-ttu-id="896ab-123">데이터 형식이 `expression` 또는 `typename` 클래스 또는 구조를 정의 했으면 정의할 수 있습니다 `CType` 해당 클래스 또는 변환 연산자와 구조에서.</span><span class="sxs-lookup"><span data-stu-id="896ab-123">If the data type of `expression` or `typename` is a class or structure you've defined, you can define `CType` on that class or structure as a conversion operator.</span></span> <span data-ttu-id="896ab-124">이렇게 하면 `CType` 프록시로 *오버 로드 된 연산자*합니다.</span><span class="sxs-lookup"><span data-stu-id="896ab-124">This makes `CType` act as an *overloaded operator*.</span></span> <span data-ttu-id="896ab-125">이 작업을 수행 하는 경우에 클래스 또는 구조체를 throw 할 수 있는 예외를 포함 하 여에서 변환 하 고 동작을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="896ab-125">If you do this, you can control the behavior of conversions to and from your class or structure, including the exceptions that can be thrown.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="896ab-126">오버로딩</span><span class="sxs-lookup"><span data-stu-id="896ab-126">Overloading</span></span>  
 <span data-ttu-id="896ab-127">`CType` 연산자 클래스 또는 코드 외부에 정의 된 구조체에 오버 로드 될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="896ab-127">The `CType` operator can also be overloaded on a class or structure defined outside your code.</span></span> <span data-ttu-id="896ab-128">코드로 변환 되 면 해당 클래스 또는 구조에서 사용할의 동작을 알고 있어야 해당 `CType` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="896ab-128">If your code converts to or from such a class or structure, be sure you understand the behavior of its `CType` operator.</span></span> <span data-ttu-id="896ab-129">자세한 내용은 참조 [연산자 프로시저](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="896ab-129">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="converting-dynamic-objects"></a><span data-ttu-id="896ab-130">동적 개체 변환</span><span class="sxs-lookup"><span data-stu-id="896ab-130">Converting Dynamic Objects</span></span>  
 <span data-ttu-id="896ab-131">동적 개체의 형식 변환을 사용 하는 사용자 지정 동적 변환을 수행한는 <xref:System.Dynamic.DynamicObject.TryConvert%2A> 또는 <xref:System.Dynamic.DynamicMetaObject.BindConvert%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="896ab-131">Type conversions of dynamic objects are performed by user-defined dynamic conversions that use the <xref:System.Dynamic.DynamicObject.TryConvert%2A> or <xref:System.Dynamic.DynamicMetaObject.BindConvert%2A> methods.</span></span> <span data-ttu-id="896ab-132">동적 개체를 사용 하는 경우 사용 된 <xref:Microsoft.VisualBasic.Conversion.CTypeDynamic%2A> 동적 개체를 변환 하는 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="896ab-132">If you're working with dynamic objects, use the <xref:Microsoft.VisualBasic.Conversion.CTypeDynamic%2A> method to convert the dynamic object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="896ab-133">예</span><span class="sxs-lookup"><span data-stu-id="896ab-133">Example</span></span>  
 <span data-ttu-id="896ab-134">다음 예제에서는 `CType` 식으로 변환 하는 함수는 `Single` 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="896ab-134">The following example uses the `CType` function to convert an expression to the `Single` data type.</span></span>  
  
 [!code-vb[VbVbalrFunctions#24](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/ctype-function_1.vb)]  
  
 <span data-ttu-id="896ab-135">추가 예제를 참조 하십시오. [암시적 변환과 명시적 변환](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="896ab-135">For additional examples, see [Implicit and Explicit Conversions](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="896ab-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="896ab-136">See Also</span></span>  
 <xref:System.OverflowException>  
 <xref:System.InvalidCastException>  
 [<span data-ttu-id="896ab-137">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="896ab-137">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="896ab-138">변환 함수</span><span class="sxs-lookup"><span data-stu-id="896ab-138">Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/conversion-functions.md)  
 [<span data-ttu-id="896ab-139">Operator 문</span><span class="sxs-lookup"><span data-stu-id="896ab-139">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
 [<span data-ttu-id="896ab-140">방법: 변환 연산자 정의</span><span class="sxs-lookup"><span data-stu-id="896ab-140">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)  
 [<span data-ttu-id="896ab-141">.NET Framework의 형식 변환</span><span class="sxs-lookup"><span data-stu-id="896ab-141">Type Conversion in the .NET Framework</span></span>](../../../standard/base-types/type-conversion.md)
