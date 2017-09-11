---
title: "Delegate 문 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Delegate
dev_langs:
- VB
helpviewer_keywords:
- delegate keyword
- Delegate statement
ms.assetid: f799c518-0817-40cc-ad0b-4da846fdba57
caps.latest.revision: 27
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
ms.openlocfilehash: 052ef837dfe4f9d34081839eea47e35bc4824afd
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="delegate-statement"></a><span data-ttu-id="a6284-102">Delegate 문</span><span class="sxs-lookup"><span data-stu-id="a6284-102">Delegate Statement</span></span>
<span data-ttu-id="a6284-103">대리자를 선언 하는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6284-103">Used to declare a delegate.</span></span> <span data-ttu-id="a6284-104">대리자는 참조 형식을 참조 하는 `Shared` 형식 또는 개체의 인스턴스 메서드 메서드.</span><span class="sxs-lookup"><span data-stu-id="a6284-104">A delegate is a reference type that refers to a `Shared` method of a type or to an instance method of an object.</span></span> <span data-ttu-id="a6284-105">이 대리자 클래스의 인스턴스를 만드는 매개 변수 및 반환 형식을 일치 하는 모든 프로시저를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6284-105">Any procedure with matching parameter and return types can be used to create an instance of this delegate class.</span></span> <span data-ttu-id="a6284-106">다음 대리자 인스턴스를 사용 하 여는 프로시저에 나중에 호출 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6284-106">The procedure can then later be invoked by means of the delegate instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6284-107">구문</span><span class="sxs-lookup"><span data-stu-id="a6284-107">Syntax</span></span>  
  
```  
[ <attrlist> ] [ accessmodifier ] _  
[ Shadows ] Delegate [ Sub | Function ] name [( Of typeparamlist )] [([ parameterlist ])] [ As type ]  
```  
  
## <a name="parts"></a><span data-ttu-id="a6284-108">요소</span><span class="sxs-lookup"><span data-stu-id="a6284-108">Parts</span></span>  
  
|<span data-ttu-id="a6284-109">용어</span><span class="sxs-lookup"><span data-stu-id="a6284-109">Term</span></span>|<span data-ttu-id="a6284-110">정의</span><span class="sxs-lookup"><span data-stu-id="a6284-110">Definition</span></span>|  
|---|---|  
|`attrlist`|<span data-ttu-id="a6284-111">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="a6284-111">Optional.</span></span> <span data-ttu-id="a6284-112">이 대리자에 적용 되는 특성의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="a6284-112">List of attributes that apply to this delegate.</span></span> <span data-ttu-id="a6284-113">여러 특성은 쉼표로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="a6284-113">Multiple attributes are separated by commas.</span></span> <span data-ttu-id="a6284-114">묶어야는 [특성 목록](../../../visual-basic/language-reference/statements/attribute-list.md) 꺾쇠 괄호에서 ("`<`"및"`>`").</span><span class="sxs-lookup"><span data-stu-id="a6284-114">You must enclose the [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md) in angle brackets ("`<`" and "`>`").</span></span>|  
|`accessmodifier`|<span data-ttu-id="a6284-115">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="a6284-115">Optional.</span></span> <span data-ttu-id="a6284-116">대리자에 액세스할 수 있는 코드를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6284-116">Specifies what code can access the delegate.</span></span> <span data-ttu-id="a6284-117">다음 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6284-117">Can be one of the following:</span></span><br /><br /><span data-ttu-id="a6284-118"> -   [공용](../../../visual-basic/language-reference/modifiers/public.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a6284-118"> -   [Public](../../../visual-basic/language-reference/modifiers/public.md).</span></span> <span data-ttu-id="a6284-119">대리자를 선언 하는 요소에 액세스할 수 있는 모든 코드를 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6284-119">Any code that can access the element that declares the delegate can access it.</span></span><br /><span data-ttu-id="a6284-120">-   [보호 된](../../../visual-basic/language-reference/modifiers/protected.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a6284-120">-   [Protected](../../../visual-basic/language-reference/modifiers/protected.md).</span></span> <span data-ttu-id="a6284-121">대리자의 클래스 또는 파생된 클래스 내에서 코드에만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6284-121">Only code within the delegate's class or a derived class can access it.</span></span><br /><span data-ttu-id="a6284-122">-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a6284-122">-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md).</span></span> <span data-ttu-id="a6284-123">동일한 어셈블리 내 코드만 대리자를 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6284-123">Only code within the same assembly can access the delegate.</span></span><br /><span data-ttu-id="a6284-124">-   [개인](../../../visual-basic/language-reference/modifiers/private.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a6284-124">-   [Private](../../../visual-basic/language-reference/modifiers/private.md).</span></span> <span data-ttu-id="a6284-125">대리자를 선언 하는 요소 내의 코드에만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6284-125">Only code within the element that declares the delegate can access it.</span></span><br /><br /> <span data-ttu-id="a6284-126">지정할 수 있습니다 `Protected Friend` 코드 대리자의 클래스나 파생된 클래스에서 동일한 어셈블리 내에서 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6284-126">You can specify `Protected Friend` to enable access from code within the delegate's class, a derived class, or the same assembly.</span></span>|  
|`Shadows`|<span data-ttu-id="a6284-127">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="a6284-127">Optional.</span></span> <span data-ttu-id="a6284-128">이 대리자는 같은 이름의 프로그래밍 요소 또는 기본 클래스의 오버 로드 된 요소 집합을 다시 선언 하 고 숨기도록 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a6284-128">Indicates that this delegate redeclares and hides an identically named programming element, or set of overloaded elements, in a base class.</span></span> <span data-ttu-id="a6284-129">모든 종류의 선언된 요소를 다른 종류로 섀도잉할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6284-129">You can shadow any kind of declared element with any other kind.</span></span><br /><br /> <span data-ttu-id="a6284-130">섀도잉된 요소는 섀도잉 요소에 액세스할 수 없는 위치를 제외하고 해당 요소를 섀도잉하는 파생 클래스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a6284-130">A shadowed element is unavailable from within the derived class that shadows it, except from where the shadowing element is inaccessible.</span></span> <span data-ttu-id="a6284-131">예를 들어 하는 경우는 `Private` 요소 기본 클래스 요소를 액세스할 수 있는 권한이 없는 코드를 숨기면는 `Private` 요소 기본 클래스 요소에 대신 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6284-131">For example, if a `Private` element shadows a base class element, code that does not have permission to access the `Private` element accesses the base class element instead.</span></span>|  
|`Sub`|<span data-ttu-id="a6284-132">선택적 `Sub` 또는 `Function` 나타나야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6284-132">Optional, but either `Sub` or `Function` must appear.</span></span> <span data-ttu-id="a6284-133">이 절차를 대리자로 선언 `Sub` 값을 반환 하지 않는 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="a6284-133">Declares this procedure as a delegate `Sub` procedure that does not return a value.</span></span>|  
|`Function`|<span data-ttu-id="a6284-134">선택적 `Sub` 또는 `Function` 나타나야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6284-134">Optional, but either `Sub` or `Function` must appear.</span></span> <span data-ttu-id="a6284-135">이 절차를 대리자로 선언 `Function` 값을 반환 하는 절차입니다.</span><span class="sxs-lookup"><span data-stu-id="a6284-135">Declares this procedure as a delegate `Function` procedure that returns a value.</span></span>|  
|`name`|<span data-ttu-id="a6284-136">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="a6284-136">Required.</span></span> <span data-ttu-id="a6284-137">대리자 형식의 이름 표준 변수 명명 규칙을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="a6284-137">Name of the delegate type; follows standard variable naming conventions.</span></span>|  
|`typeparamlist`|<span data-ttu-id="a6284-138">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="a6284-138">Optional.</span></span> <span data-ttu-id="a6284-139">이 대리자에 대 한 형식 매개 변수 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="a6284-139">List of type parameters for this delegate.</span></span> <span data-ttu-id="a6284-140">여러 형식 매개 변수는 쉼표로 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6284-140">Multiple type parameters are separated by commas.</span></span> <span data-ttu-id="a6284-141">필요에 따라 각 형식 매개 변수가 선언할 수 있습니다 variant를 사용 하 여 `In` 및 `Out` 제네릭 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="a6284-141">Optionally, each type parameter can be declared variant by using `In` and `Out` generic modifiers.</span></span> <span data-ttu-id="a6284-142">묶어야는 [유형 목록](../../../visual-basic/language-reference/statements/type-list.md) 괄호 안에 사용 하 여 정의 하 고는 `Of` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="a6284-142">You must enclose the [Type List](../../../visual-basic/language-reference/statements/type-list.md) in parentheses and introduce it with the `Of` keyword.</span></span>|  
|`parameterlist`|<span data-ttu-id="a6284-143">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="a6284-143">Optional.</span></span> <span data-ttu-id="a6284-144">호출 될 때 프로시저에 전달 되는 매개 변수 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="a6284-144">List of parameters that are passed to the procedure when it is called.</span></span> <span data-ttu-id="a6284-145">묶어야는 [매개 변수 목록](../../../visual-basic/language-reference/statements/parameter-list.md) 괄호 안에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6284-145">You must enclose the [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md) in parentheses.</span></span>|  
|`type`|<span data-ttu-id="a6284-146">지정 하는 경우 필요한는 `Function` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="a6284-146">Required if you specify a `Function` procedure.</span></span> <span data-ttu-id="a6284-147">반환 값의 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a6284-147">Data type of the return value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a6284-148">주의</span><span class="sxs-lookup"><span data-stu-id="a6284-148">Remarks</span></span>  
 <span data-ttu-id="a6284-149">`Delegate` 문은 대리자 클래스의 매개 변수 및 반환 형식을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6284-149">The `Delegate` statement defines the parameter and return types of a delegate class.</span></span> <span data-ttu-id="a6284-150">이 대리자 클래스의 인스턴스를 만드는 매개 변수 및 반환 형식에 일치 하는 모든 프로시저를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6284-150">Any procedure with matching parameters and return types can be used to create an instance of this delegate class.</span></span> <span data-ttu-id="a6284-151">프로시저 수 나중에 호출 될 대리자 인스턴스를 통해 대리자의 호출 하 여 `Invoke` 메서드.</span><span class="sxs-lookup"><span data-stu-id="a6284-151">The procedure can then later be invoked by means of the delegate instance, by calling the delegate's `Invoke` method.</span></span>  
  
 <span data-ttu-id="a6284-152">프로시저 내부가 아니라 네임 스페이스, 모듈, 클래스 또는 구조 수준에서 대리자를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6284-152">Delegates can be declared at the namespace, module, class, or structure level, but not within a procedure.</span></span>  
  
 <span data-ttu-id="a6284-153">각 대리자 클래스는 개체 메서드의 사양이 전달되는 생성자를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a6284-153">Each delegate class defines a constructor that is passed the specification of an object method.</span></span> <span data-ttu-id="a6284-154">대리자 생성자에 인수로 메서드 또는 람다 식에 대 한 참조 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6284-154">An argument to a delegate constructor must be a reference to a method, or a lambda expression.</span></span>  
  
 <span data-ttu-id="a6284-155">메서드에 대 한 참조를 지정 하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6284-155">To specify a reference to a method, use the following syntax:</span></span>  
  
 <span data-ttu-id="a6284-156">`AddressOf` [`expression`.]`methodname`</span><span class="sxs-lookup"><span data-stu-id="a6284-156">`AddressOf` [`expression`.]`methodname`</span></span>  
  
 <span data-ttu-id="a6284-157">컴파일 타임 형식은 `expression` 클래스 또는 서명이 대리자 클래스의 서명과 일치 하는 지정 된 이름의 메서드를 포함 하는 인터페이스의 이름 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6284-157">The compile-time type of the `expression` must be the name of a class or an interface that contains a method of the specified name whose signature matches the signature of the delegate class.</span></span> <span data-ttu-id="a6284-158">`methodname` 공유 메서드 또는 인스턴스 메서드 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6284-158">The `methodname` can be either a shared method or an instance method.</span></span> <span data-ttu-id="a6284-159">`methodname` 은 반드시 기본 클래스의 메서드에 대 한 대리자를 만드는 경우에 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6284-159">The `methodname` is not optional, even if you create a delegate for the default method of the class.</span></span>  
  
 <span data-ttu-id="a6284-160">람다 식을 지정 하려면 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6284-160">To specify a lambda expression, use the following syntax:</span></span>  
  
 <span data-ttu-id="a6284-161">`Function`([`parm` As `type`, `parm2` As `type2`, ...])`expression`</span><span class="sxs-lookup"><span data-stu-id="a6284-161">`Function` ([`parm` As `type`, `parm2` As `type2`, ...]) `expression`</span></span>  
  
 <span data-ttu-id="a6284-162">함수의 서명이 대리자 형식의 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6284-162">The signature of the function must match that of the delegate type.</span></span> <span data-ttu-id="a6284-163">람다 식에 대한 자세한 내용은 [람다 식](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a6284-163">For more information about lambda expressions, see [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
 <span data-ttu-id="a6284-164">대리자에 대 한 자세한 내용은 참조 [대리자](../../../visual-basic/programming-guide/language-features/delegates/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a6284-164">For more information about delegates, see [Delegates](../../../visual-basic/programming-guide/language-features/delegates/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6284-165">예제</span><span class="sxs-lookup"><span data-stu-id="a6284-165">Example</span></span>  
 <span data-ttu-id="a6284-166">다음 예제에서는 `Delegate` 두 숫자에 대해 작동 하 고 숫자를 반환 하는 것에 대 한 대리자를 선언 하는 문입니다.</span><span class="sxs-lookup"><span data-stu-id="a6284-166">The following example uses the `Delegate` statement to declare a delegate for operating on two numbers and returning a number.</span></span> <span data-ttu-id="a6284-167">`DelegateTest` 메서드가 형식의 대리자의 인스턴스를 사용 하 고 사용 하 여 숫자의 쌍입니다.</span><span class="sxs-lookup"><span data-stu-id="a6284-167">The `DelegateTest` method takes an instance of a delegate of this type and uses it to operate on pairs of numbers.</span></span>  
  
 <span data-ttu-id="a6284-168">[!code-vb[VbVbalrDelegates #&14;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/delegate-statement_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="a6284-168">[!code-vb[VbVbalrDelegates#14](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/delegate-statement_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6284-169">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a6284-169">See Also</span></span>  
 <span data-ttu-id="a6284-170">[AddressOf 연산자](../../../visual-basic/language-reference/operators/addressof-operator.md) </span><span class="sxs-lookup"><span data-stu-id="a6284-170">[AddressOf Operator](../../../visual-basic/language-reference/operators/addressof-operator.md) </span></span>  
<span data-ttu-id="a6284-171"> [Of](../../../visual-basic/language-reference/statements/of-clause.md) </span><span class="sxs-lookup"><span data-stu-id="a6284-171"> [Of](../../../visual-basic/language-reference/statements/of-clause.md) </span></span>  
<span data-ttu-id="a6284-172"> [대리자](../../../visual-basic/programming-guide/language-features/delegates/index.md) </span><span class="sxs-lookup"><span data-stu-id="a6284-172"> [Delegates](../../../visual-basic/programming-guide/language-features/delegates/index.md) </span></span>  
<span data-ttu-id="a6284-173"> [방법: 제네릭 클래스 사용](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md) </span><span class="sxs-lookup"><span data-stu-id="a6284-173"> [How to: Use a Generic Class](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md) </span></span>  
<span data-ttu-id="a6284-174"> [Visual Basic의 제네릭 형식](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md) </span><span class="sxs-lookup"><span data-stu-id="a6284-174"> [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md) </span></span>  
<span data-ttu-id="a6284-175"> [공 분산과 반공 분산](http://msdn.microsoft.com/library/a58cc086-276f-4f91-a366-85b7f95f38b8) </span><span class="sxs-lookup"><span data-stu-id="a6284-175"> [Covariance and Contravariance](http://msdn.microsoft.com/library/a58cc086-276f-4f91-a366-85b7f95f38b8) </span></span>  
<span data-ttu-id="a6284-176"> [에서](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md) </span><span class="sxs-lookup"><span data-stu-id="a6284-176"> [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md) </span></span>  
<span data-ttu-id="a6284-177"> [아웃](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)</span><span class="sxs-lookup"><span data-stu-id="a6284-177"> [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)</span></span>
