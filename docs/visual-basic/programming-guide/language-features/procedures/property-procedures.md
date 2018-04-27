---
title: Property 프로시저(Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Set statement [Visual Basic], Property procedures
- Visual Basic code, procedures
- return values [Visual Basic], Property procedures
- syntax [Visual Basic], Property procedures
- procedures [Visual Basic], property
- Visual Basic code, properties
- procedures [Visual Basic], calling
- properties [Visual Basic], custom
- property procedures
- Get statement [Visual Basic], property procedures
ms.assetid: 46a98379-e1a2-45dd-a48c-b51213f5ab07
caps.latest.revision: 22
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0d9df6f381c89263aa16315fb06a2b3b0d645bbf
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="property-procedures-visual-basic"></a><span data-ttu-id="4d1b4-102">Property 프로시저(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4d1b4-102">Property Procedures (Visual Basic)</span></span>
<span data-ttu-id="4d1b4-103">속성 프로시저는 일련의 모듈, 클래스 또는 구조체에서 사용자 지정 속성을 조작 하는 Visual Basic 문입니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b4-103">A property procedure is a series of Visual Basic statements that manipulate a custom property on a module, class, or structure.</span></span> <span data-ttu-id="4d1b4-104">속성 프로시저는 라고도 *속성 접근자*합니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b4-104">Property procedures are also known as *property accessors*.</span></span>  
  
 <span data-ttu-id="4d1b4-105">다음 속성 프로시저에 대 한 Visual Basic을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b4-105">Visual Basic provides for the following property procedures:</span></span>  
  
-   <span data-ttu-id="4d1b4-106">A `Get` 프로시저가 속성의 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b4-106">A `Get` procedure returns the value of a property.</span></span> <span data-ttu-id="4d1b4-107">식에서 속성에 액세스할 때 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b4-107">It is called when you access the property in an expression.</span></span>  
  
-   <span data-ttu-id="4d1b4-108">A `Set` 프로시저 개체 참조를 포함 하는 값으로 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b4-108">A `Set` procedure sets a property to a value, including an object reference.</span></span> <span data-ttu-id="4d1b4-109">속성에 값을 할당할 때 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b4-109">It is called when you assign a value to the property.</span></span>  
  
 <span data-ttu-id="4d1b4-110">일반적으로 사용 하 여 쌍에 속성 프로시저를 정의 고 `Get` 및 `Set` 문, 하지만 속성이 읽기 전용 이면 두 프로시저 중 하나만 정의할 수 ([Get 문을](../../../../visual-basic/language-reference/statements/get-statement.md)) 또는 쓰기 전용 ([설정 문](../../../../visual-basic/language-reference/statements/set-statement.md)).</span><span class="sxs-lookup"><span data-stu-id="4d1b4-110">You usually define property procedures in pairs, using the `Get` and `Set` statements, but you can define either procedure alone if the property is read-only ([Get Statement](../../../../visual-basic/language-reference/statements/get-statement.md)) or write-only ([Set Statement](../../../../visual-basic/language-reference/statements/set-statement.md)).</span></span>  
  
 <span data-ttu-id="4d1b4-111">생략할 수 있습니다는 `Get` 및 `Set` 자동 구현 속성을 사용할 때 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b4-111">You can omit the `Get` and `Set` procedure when using an auto-implemented property.</span></span> <span data-ttu-id="4d1b4-112">자세한 내용은 [자동으로 구현된 속성](./auto-implemented-properties.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4d1b4-112">For more information, see [Auto-Implemented Properties](./auto-implemented-properties.md).</span></span>  
  
 <span data-ttu-id="4d1b4-113">클래스, 구조체 및 모듈의 속성을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b4-113">You can define properties in classes, structures, and modules.</span></span> <span data-ttu-id="4d1b4-114">속성은 `Public` 어디에서 나 호출할 수 즉 기본적으로 속성의 컨테이너에 액세스할 수 있는 응용 프로그램에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b4-114">Properties are `Public` by default, which means you can call them from anywhere in your application that can access the property's container.</span></span>  
  
 <span data-ttu-id="4d1b4-115">속성 및 변수 비교를 참조 하세요. [속성 간의 차이점 및 Visual Basic의 변수](./differences-between-properties-and-variables.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b4-115">For a comparison of properties and variables, see [Differences Between Properties and Variables in Visual Basic](./differences-between-properties-and-variables.md).</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="4d1b4-116">선언 구문</span><span class="sxs-lookup"><span data-stu-id="4d1b4-116">Declaration Syntax</span></span>  
 <span data-ttu-id="4d1b4-117">둘러싸인 코드 블록에 의해 정의 된 속성 자체는 [Property 문](../../../../visual-basic/language-reference/statements/property-statement.md) 및 `End Property` 문.</span><span class="sxs-lookup"><span data-stu-id="4d1b4-117">A property itself is defined by a block of code enclosed within the [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md) and the `End Property` statement.</span></span> <span data-ttu-id="4d1b4-118">이 블록에서 각 속성 프로시저는 선언문 싸인 내부 블록으로 나타납니다 (`Get` 또는 `Set`)와 일치 하는 `End` 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b4-118">Inside this block, each property procedure appears as an internal block enclosed within a declaration statement (`Get` or `Set`) and the matching `End` declaration.</span></span>  
  
 <span data-ttu-id="4d1b4-119">속성과 해당 프로시저를 선언 하기 위한 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b4-119">The syntax for declaring a property and its procedures is as follows:</span></span>  
  
```  
[Default] [Modifiers] Property PropertyName[(ParameterList)] [As DataType]  
    [AccessLevel] Get  
        ' Statements of the Get procedure.  
        ' The following statement returns an expression as the property's value.  
        Return Expression  
    End Get  
    [AccessLevel] Set[(ByVal NewValue As DataType)]  
        ' Statements of the Set procedure.  
        ' The following statement assigns newvalue as the property's value.  
        LValue = NewValue  
    End Set  
End Property  
- or -  
[Default] [Modifiers] Property PropertyName [(ParameterList)] [As DataType]  
```  
  
 <span data-ttu-id="4d1b4-120">`Modifiers` 지정할 수 액세스 수준 및 오버 로드, 재정의 공유 및 숨김에 대 한 정보 뿐만 아니라 읽기 전용 이거나 쓰기 전용 속성 인지 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b4-120">The `Modifiers` can specify access level and information regarding overloading, overriding, sharing, and shadowing, as well as whether the property is read-only or write-only.</span></span> <span data-ttu-id="4d1b4-121">`AccessLevel` 에 `Get` 또는 `Set` 프로시저 속성 자체에 대해 지정 된 액세스 수준 보다 더 제한적으로 수준을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b4-121">The `AccessLevel` on the `Get` or `Set` procedure can be any level that is more restrictive than the access level specified for the property itself.</span></span> <span data-ttu-id="4d1b4-122">자세한 내용은 참조 [Property 문](../../../../visual-basic/language-reference/statements/property-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b4-122">For more information, see [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md).</span></span>  
  
### <a name="data-type"></a><span data-ttu-id="4d1b4-123">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4d1b4-123">Data Type</span></span>  
 <span data-ttu-id="4d1b4-124">속성의 데이터 형식 및 보안 주체 액세스 수준에 정의 되어는 `Property` 문, property 프로시저에 없는 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b4-124">A property's data type and principal access level are defined in the `Property` statement, not in the property procedures.</span></span> <span data-ttu-id="4d1b4-125">속성에는 하나의 데이터 형식이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b4-125">A property can have only one data type.</span></span> <span data-ttu-id="4d1b4-126">저장 하는 속성을 정의할 수 없습니다 예를 들어 한 `Decimal` 값을 검색 하지만 `Double` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b4-126">For example, you cannot define a property to store a `Decimal` value but retrieve a `Double` value.</span></span>  
  
### <a name="access-level"></a><span data-ttu-id="4d1b4-127">액세스 수준</span><span class="sxs-lookup"><span data-stu-id="4d1b4-127">Access Level</span></span>  
 <span data-ttu-id="4d1b4-128">그러나 속성에 대 한 보안 주체 액세스 수준을 정의 하 고 해당 속성 프로시저 중 하나에 대 한 액세스 수준을 더욱 제한할 수입니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b4-128">However, you can define a principal access level for a property and further restrict the access level in one of its property procedures.</span></span> <span data-ttu-id="4d1b4-129">예를 들어 정의할 수 있습니다는 `Public` 속성 다음 정의 `Private Set` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b4-129">For example, you can define a `Public` property and then define a `Private Set` procedure.</span></span> <span data-ttu-id="4d1b4-130">`Get` 프로시저 남아 `Public`합니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b4-130">The `Get` procedure remains `Public`.</span></span> <span data-ttu-id="4d1b4-131">속성 프로시저 중 하나 에서만 액세스 수준을 변경할 수 있습니다 및 보안 주체 액세스 수준 보다 제한적 으로만 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b4-131">You can change the access level in only one of a property's procedures, and you can only make it more restrictive than the principal access level.</span></span> <span data-ttu-id="4d1b4-132">자세한 내용은 참조 [하는 방법: 액세스 수준이 혼합 된 속성을 선언](./how-to-declare-a-property-with-mixed-access-levels.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b4-132">For more information, see [How to: Declare a Property with Mixed Access Levels](./how-to-declare-a-property-with-mixed-access-levels.md).</span></span>  
  
## <a name="parameter-declaration"></a><span data-ttu-id="4d1b4-133">매개 변수 선언</span><span class="sxs-lookup"><span data-stu-id="4d1b4-133">Parameter Declaration</span></span>  
 <span data-ttu-id="4d1b4-134">에 대 한 작업을 수행한 동일한 방식으로 각 매개 변수를 선언 [Sub 프로시저](./sub-procedures.md)한다는 점을 제외 하 고 전달 해야 한다는 `ByVal`합니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b4-134">You declare each parameter the same way you do for [Sub Procedures](./sub-procedures.md), except that the passing mechanism must be `ByVal`.</span></span>  
  
 <span data-ttu-id="4d1b4-135">매개 변수 목록에서 각 매개 변수에 대 한 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b4-135">The syntax for each parameter in the parameter list is as follows:</span></span>  
  
 `[Optional] ByVal [ParamArray] parametername As datatype`  
  
 <span data-ttu-id="4d1b4-136">매개 변수가 선택적 이면 해당 선언의 일부로 기본값도 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b4-136">If the parameter is optional, you must also supply a default value as part of its declaration.</span></span> <span data-ttu-id="4d1b4-137">기본값을 지정 하기 위한 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b4-137">The syntax for specifying a default value is as follows:</span></span>  
  
 `Optional ByVal parametername As datatype = defaultvalue`  
  
## <a name="property-value"></a><span data-ttu-id="4d1b4-138">속성 값</span><span class="sxs-lookup"><span data-stu-id="4d1b4-138">Property Value</span></span>  
 <span data-ttu-id="4d1b4-139">에 `Get` 프로시저 반환 값은 속성의 호출 식 값으로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b4-139">In a `Get` procedure, the return value is supplied to the calling expression as the value of the property.</span></span>  
  
 <span data-ttu-id="4d1b4-140">에 `Set` 프로시저 새 속성 값의 매개 변수로 전달 되는 `Set` 문.</span><span class="sxs-lookup"><span data-stu-id="4d1b4-140">In a `Set` procedure, the new property value is passed to the parameter of the `Set` statement.</span></span> <span data-ttu-id="4d1b4-141">매개 변수를 명시적으로 선언 하는 경우 동일한 데이터 형식의 속성으로 선언 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b4-141">If you explicitly declare a parameter, you must declare it with the same data type as the property.</span></span> <span data-ttu-id="4d1b4-142">매개 변수를 선언 하지 않으면 컴파일러는 암시적 매개 변수 사용 `Value` 속성에 할당할 새 값을 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b4-142">If you do not declare a parameter, the compiler uses the implicit parameter `Value` to represent the new value to be assigned to the property.</span></span>  
  
## <a name="calling-syntax"></a><span data-ttu-id="4d1b4-143">호출 구문</span><span class="sxs-lookup"><span data-stu-id="4d1b4-143">Calling Syntax</span></span>  
 <span data-ttu-id="4d1b4-144">속성을 참조 하 여 속성 프로시저를 암시적으로 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b4-144">You invoke a property procedure implicitly by making reference to the property.</span></span> <span data-ttu-id="4d1b4-145">사용 속성의 이름을의 변수 이름을 사용 하 게 동일한 방식으로 모든 인수는 옵션에 대 한 값을 제공 해야 한다는 점을 제외 하 고 인수 목록을 괄호로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b4-145">You use the name of the property the same way you would use the name of a variable, except that you must provide values for all arguments that are not optional, and you must enclose the argument list in parentheses.</span></span> <span data-ttu-id="4d1b4-146">인수를 제공 하는 경우 괄호를 선택적으로 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b4-146">If no arguments are supplied, you can optionally omit the parentheses.</span></span>  
  
 <span data-ttu-id="4d1b4-147">암시적으로 호출 하는 구문은 `Set` 절차는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b4-147">The syntax for an implicit call to a `Set` procedure is as follows:</span></span>  
  
 `propertyname[(argumentlist)] = expression`  
  
 <span data-ttu-id="4d1b4-148">암시적으로 호출 하는 구문은 `Get` 절차는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b4-148">The syntax for an implicit call to a `Get` procedure is as follows:</span></span>  
  
 `lvalue = propertyname[(argumentlist)]`  
  
 `Do While (propertyname[(argumentlist)] > expression)`  
  
### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="4d1b4-149">선언 및 호출의 그림</span><span class="sxs-lookup"><span data-stu-id="4d1b4-149">Illustration of Declaration and Call</span></span>  
 <span data-ttu-id="4d1b4-150">다음과 같은 속성이 두 개의 구성 요소 이름, 성 및 last name 전체 이름을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b4-150">The following property stores a full name as two constituent names, the first name and the last name.</span></span> <span data-ttu-id="4d1b4-151">호출 코드를 읽을 때 `fullName`, `Get` 프로시저가 두 구성 요소 이름을 결합 하 고 전체 이름을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b4-151">When the calling code reads `fullName`, the `Get` procedure combines the two constituent names and returns the full name.</span></span> <span data-ttu-id="4d1b4-152">새 전체 이름을 할당 하는 호출 하는 코드는 `Set` 프로시저가 두 구성 요소 이름으로 나누는 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b4-152">When the calling code assigns a new full name, the `Set` procedure attempts to break it into two constituent names.</span></span> <span data-ttu-id="4d1b4-153">공백을 찾지 못하면 하는 경우 모든 이름으로 저장 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b4-153">If it does not find a space, it stores it all as the first name.</span></span>  
  
 [!code-vb[VbVbcnProcedures#8](./codesnippet/VisualBasic/property-procedures_1.vb)]  
  
 <span data-ttu-id="4d1b4-154">다음 예제에서는의 속성 프로시저를 호출 하는 일반적인 `fullName`합니다.</span><span class="sxs-lookup"><span data-stu-id="4d1b4-154">The following example shows typical calls to the property procedures of `fullName`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#9](./codesnippet/VisualBasic/property-procedures_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="4d1b4-155">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4d1b4-155">See Also</span></span>  
 [<span data-ttu-id="4d1b4-156">절차</span><span class="sxs-lookup"><span data-stu-id="4d1b4-156">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="4d1b4-157">Function 프로시저</span><span class="sxs-lookup"><span data-stu-id="4d1b4-157">Function Procedures</span></span>](./function-procedures.md)  
 [<span data-ttu-id="4d1b4-158">연산자 프로시저</span><span class="sxs-lookup"><span data-stu-id="4d1b4-158">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="4d1b4-159">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="4d1b4-159">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="4d1b4-160">Visual Basic에서 속성과 변수의 차이점</span><span class="sxs-lookup"><span data-stu-id="4d1b4-160">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)  
 [<span data-ttu-id="4d1b4-161">방법: 속성 만들기</span><span class="sxs-lookup"><span data-stu-id="4d1b4-161">How to: Create a Property</span></span>](./how-to-create-a-property.md)  
 [<span data-ttu-id="4d1b4-162">방법: 속성 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="4d1b4-162">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)  
 [<span data-ttu-id="4d1b4-163">방법: 선언 하 고 Visual Basic의 기본 속성 호출</span><span class="sxs-lookup"><span data-stu-id="4d1b4-163">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)  
 [<span data-ttu-id="4d1b4-164">방법: 속성 값 입력</span><span class="sxs-lookup"><span data-stu-id="4d1b4-164">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)  
 [<span data-ttu-id="4d1b4-165">방법: 속성에서 값 가져오기</span><span class="sxs-lookup"><span data-stu-id="4d1b4-165">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
