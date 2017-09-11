---
title: "Property 프로시저 (Visual Basic) | Microsoft 문서"
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
- Set statement, Property procedures
- Visual Basic code, procedures
- return values, Property procedures
- syntax, Property procedures
- procedures, property
- Visual Basic code, properties
- procedures, calling
- properties [Visual Basic], custom
- property procedures
- Get statement, property procedures
ms.assetid: 46a98379-e1a2-45dd-a48c-b51213f5ab07
caps.latest.revision: 22
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 6ba662a8cf9748b719bfbd7205ce65989e79d05a
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="property-procedures-visual-basic"></a><span data-ttu-id="c81cf-102">Property 프로시저(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c81cf-102">Property Procedures (Visual Basic)</span></span>
<span data-ttu-id="c81cf-103">속성 프로시저는 일련의 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 모듈, 클래스 또는 구조체에서 사용자 지정 속성을 조작 하는 문입니다.</span><span class="sxs-lookup"><span data-stu-id="c81cf-103">A property procedure is a series of [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] statements that manipulate a custom property on a module, class, or structure.</span></span> <span data-ttu-id="c81cf-104">속성 프로시저는 라고도 *속성 접근자*합니다.</span><span class="sxs-lookup"><span data-stu-id="c81cf-104">Property procedures are also known as *property accessors*.</span></span>  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="c81cf-105">다음 속성 프로시저를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c81cf-105"> provides for the following property procedures:</span></span>  
  
-   <span data-ttu-id="c81cf-106">A `Get` 프로시저 속성의 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c81cf-106">A `Get` procedure returns the value of a property.</span></span> <span data-ttu-id="c81cf-107">식에서 속성에 액세스할 때 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c81cf-107">It is called when you access the property in an expression.</span></span>  
  
-   <span data-ttu-id="c81cf-108">A `Set` 프로시저 개체 참조를 포함 하는 값으로 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c81cf-108">A `Set` procedure sets a property to a value, including an object reference.</span></span> <span data-ttu-id="c81cf-109">속성에 값을 할당할 때 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c81cf-109">It is called when you assign a value to the property.</span></span>  
  
 <span data-ttu-id="c81cf-110">일반적으로 사용 하 여 쌍에 속성 프로시저를 정의 `Get` 및 `Set` 문, 있지만 속성이 읽기 전용 이면 두 프로시저 중 하나만 정의할 수 있습니다 ([Get 문을](../../../../visual-basic/language-reference/statements/get-statement.md)) 또는 쓰기 전용 ([Set 문을](../../../../visual-basic/language-reference/statements/set-statement.md)).</span><span class="sxs-lookup"><span data-stu-id="c81cf-110">You usually define property procedures in pairs, using the `Get` and `Set` statements, but you can define either procedure alone if the property is read-only ([Get Statement](../../../../visual-basic/language-reference/statements/get-statement.md)) or write-only ([Set Statement](../../../../visual-basic/language-reference/statements/set-statement.md)).</span></span>  
  
 <span data-ttu-id="c81cf-111">생략할 수는 `Get` 및 `Set` 프로시저는 자동 구현 속성을 사용 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="c81cf-111">You can omit the `Get` and `Set` procedure when using an auto-implemented property.</span></span> <span data-ttu-id="c81cf-112">자세한 내용은 참조 [자동으로 구현 된 속성](./auto-implemented-properties.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c81cf-112">For more information, see [Auto-Implemented Properties](./auto-implemented-properties.md).</span></span>  
  
 <span data-ttu-id="c81cf-113">클래스, 구조체 및 모듈의 속성을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c81cf-113">You can define properties in classes, structures, and modules.</span></span> <span data-ttu-id="c81cf-114">속성은 `Public` 어디에서 나 호출할 수 있습니다 즉 기본적으로 속성의 컨테이너에 액세스할 수 있는 응용 프로그램에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c81cf-114">Properties are `Public` by default, which means you can call them from anywhere in your application that can access the property's container.</span></span>  
  
 <span data-ttu-id="c81cf-115">속성 및 변수는 비교를 참조 하십시오. [속성 간의 차이점 및 Visual Basic의 변수](./differences-between-properties-and-variables.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c81cf-115">For a comparison of properties and variables, see [Differences Between Properties and Variables in Visual Basic](./differences-between-properties-and-variables.md).</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="c81cf-116">선언 구문</span><span class="sxs-lookup"><span data-stu-id="c81cf-116">Declaration Syntax</span></span>  
 <span data-ttu-id="c81cf-117">속성 자체 내에 포함 하는 코드 블록을 정의한는 [Property 문](../../../../visual-basic/language-reference/statements/property-statement.md) 및 `End Property` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="c81cf-117">A property itself is defined by a block of code enclosed within the [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md) and the `End Property` statement.</span></span> <span data-ttu-id="c81cf-118">이 블록 내의 각 속성 프로시저 선언 문 내에 포함 하는 내부 블록으로 나타납니다 (`Get` 또는 `Set`)와 일치 하는 `End` 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="c81cf-118">Inside this block, each property procedure appears as an internal block enclosed within a declaration statement (`Get` or `Set`) and the matching `End` declaration.</span></span>  
  
 <span data-ttu-id="c81cf-119">속성 및 해당 프로시저를 선언 하기 위한 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c81cf-119">The syntax for declaring a property and its procedures is as follows:</span></span>  
  
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
  
 <span data-ttu-id="c81cf-120">`Modifiers` 지정할 수 액세스 수준 및 오버 로드, 재정의 공유 및 숨김에 대 한 정보 뿐만 아니라 읽기 전용 또는 쓰기 전용 속성 인지 합니다.</span><span class="sxs-lookup"><span data-stu-id="c81cf-120">The `Modifiers` can specify access level and information regarding overloading, overriding, sharing, and shadowing, as well as whether the property is read-only or write-only.</span></span> <span data-ttu-id="c81cf-121">`AccessLevel` 에 `Get` 또는 `Set` 프로시저 속성 자체에 대해 지정 된 액세스 수준 보다 더 제한적으로 수준을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c81cf-121">The `AccessLevel` on the `Get` or `Set` procedure can be any level that is more restrictive than the access level specified for the property itself.</span></span> <span data-ttu-id="c81cf-122">자세한 내용은 참조 [Property 문](../../../../visual-basic/language-reference/statements/property-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c81cf-122">For more information, see [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md).</span></span>  
  
### <a name="data-type"></a><span data-ttu-id="c81cf-123">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c81cf-123">Data Type</span></span>  
 <span data-ttu-id="c81cf-124">속성의 데이터 형식 및 보안 주체 액세스 수준에 정의 되어는 `Property` 속성 프로시저에 없는 문입니다.</span><span class="sxs-lookup"><span data-stu-id="c81cf-124">A property's data type and principal access level are defined in the `Property` statement, not in the property procedures.</span></span> <span data-ttu-id="c81cf-125">속성에는 하나의 데이터 형식이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c81cf-125">A property can have only one data type.</span></span> <span data-ttu-id="c81cf-126">저장 하는 속성을 정의할 수 없습니다 예를 들어 한 `Decimal` 하지만 검색는 `Double` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c81cf-126">For example, you cannot define a property to store a `Decimal` value but retrieve a `Double` value.</span></span>  
  
### <a name="access-level"></a><span data-ttu-id="c81cf-127">액세스 수준</span><span class="sxs-lookup"><span data-stu-id="c81cf-127">Access Level</span></span>  
 <span data-ttu-id="c81cf-128">그러나 속성에 대 한 보안 주체 액세스 수준을 정의 하 고 속성 프로시저 중 하나에 대 한 액세스 수준을 더욱 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c81cf-128">However, you can define a principal access level for a property and further restrict the access level in one of its property procedures.</span></span> <span data-ttu-id="c81cf-129">예를 들어 정의할 수 있습니다는 `Public` 속성 다음 정의 `Private Set` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="c81cf-129">For example, you can define a `Public` property and then define a `Private Set` procedure.</span></span> <span data-ttu-id="c81cf-130">`Get` 프로시저 남아 `Public`합니다.</span><span class="sxs-lookup"><span data-stu-id="c81cf-130">The `Get` procedure remains `Public`.</span></span> <span data-ttu-id="c81cf-131">속성의 절차 중 하나에 액세스 수준을 변경할 수 및 보안 주체 액세스 수준 보다 더 제한적 으로만 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c81cf-131">You can change the access level in only one of a property's procedures, and you can only make it more restrictive than the principal access level.</span></span> <span data-ttu-id="c81cf-132">자세한 내용은 참조 [하는 방법: 액세스 수준이 혼합 된 속성 선언](./how-to-declare-a-property-with-mixed-access-levels.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c81cf-132">For more information, see [How to: Declare a Property with Mixed Access Levels](./how-to-declare-a-property-with-mixed-access-levels.md).</span></span>  
  
## <a name="parameter-declaration"></a><span data-ttu-id="c81cf-133">매개 변수 선언</span><span class="sxs-lookup"><span data-stu-id="c81cf-133">Parameter Declaration</span></span>  
 <span data-ttu-id="c81cf-134">에 대 한와 동일한 방식으로 각 매개 변수를 선언 [Sub 프로시저](./sub-procedures.md)는 전달 해야 한다는 점을 제외 하 고, `ByVal`합니다.</span><span class="sxs-lookup"><span data-stu-id="c81cf-134">You declare each parameter the same way you do for [Sub Procedures](./sub-procedures.md), except that the passing mechanism must be `ByVal`.</span></span>  
  
 <span data-ttu-id="c81cf-135">매개 변수 목록에서 각 매개 변수에 대 한 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c81cf-135">The syntax for each parameter in the parameter list is as follows:</span></span>  
  
 `[Optional] ByVal [ParamArray] parametername As datatype`  
  
 <span data-ttu-id="c81cf-136">매개 변수는 선택 사항, 선언의 일부로 기본값을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c81cf-136">If the parameter is optional, you must also supply a default value as part of its declaration.</span></span> <span data-ttu-id="c81cf-137">기본값을 지정 하기 위한 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c81cf-137">The syntax for specifying a default value is as follows:</span></span>  
  
 `Optional ByVal parametername As datatype = defaultvalue`  
  
## <a name="property-value"></a><span data-ttu-id="c81cf-138">속성 값</span><span class="sxs-lookup"><span data-stu-id="c81cf-138">Property Value</span></span>  
 <span data-ttu-id="c81cf-139">에 `Get` 프로시저 반환 값 속성의 값으로 호출 식에 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c81cf-139">In a `Get` procedure, the return value is supplied to the calling expression as the value of the property.</span></span>  
  
 <span data-ttu-id="c81cf-140">에 `Set` 절차에서는 새 속성 값의 매개 변수로 전달 되는 `Set` 문.</span><span class="sxs-lookup"><span data-stu-id="c81cf-140">In a `Set` procedure, the new property value is passed to the parameter of the `Set` statement.</span></span> <span data-ttu-id="c81cf-141">매개 변수를 명시적으로 선언 하는 경우 동일한 데이터 형식의 속성으로 선언 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c81cf-141">If you explicitly declare a parameter, you must declare it with the same data type as the property.</span></span> <span data-ttu-id="c81cf-142">매개 변수를 선언 하지 않으면 컴파일러는 암시적 매개 변수 사용 `Value` 속성에 할당할 새 값으로 나타내기.</span><span class="sxs-lookup"><span data-stu-id="c81cf-142">If you do not declare a parameter, the compiler uses the implicit parameter `Value` to represent the new value to be assigned to the property.</span></span>  
  
## <a name="calling-syntax"></a><span data-ttu-id="c81cf-143">호출 구문</span><span class="sxs-lookup"><span data-stu-id="c81cf-143">Calling Syntax</span></span>  
 <span data-ttu-id="c81cf-144">속성을 참조 하 여 속성 프로시저를 암시적으로 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="c81cf-144">You invoke a property procedure implicitly by making reference to the property.</span></span> <span data-ttu-id="c81cf-145">사용 속성의 이름, 변수 이름을 사용 하는 동일한 방식으로 선택적 인수가 아닌 모든 인수에 대 한 값을 제공 해야 한다는 점을 제외 하면 하 고 인수 목록을 괄호로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c81cf-145">You use the name of the property the same way you would use the name of a variable, except that you must provide values for all arguments that are not optional, and you must enclose the argument list in parentheses.</span></span> <span data-ttu-id="c81cf-146">없는 인수를 제공 하는 경우에 필요에 따라 괄호를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c81cf-146">If no arguments are supplied, you can optionally omit the parentheses.</span></span>  
  
 <span data-ttu-id="c81cf-147">암시적으로 호출 하는 구문은 `Set` 절차는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c81cf-147">The syntax for an implicit call to a `Set` procedure is as follows:</span></span>  
  
 `propertyname[(argumentlist)] = expression`  
  
 <span data-ttu-id="c81cf-148">암시적으로 호출 하는 구문은 `Get` 절차는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c81cf-148">The syntax for an implicit call to a `Get` procedure is as follows:</span></span>  
  
 `lvalue = propertyname[(argumentlist)]`  
  
 `Do While (propertyname[(argumentlist)] > expression)`  
  
### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="c81cf-149">선언 및 호출의 그림</span><span class="sxs-lookup"><span data-stu-id="c81cf-149">Illustration of Declaration and Call</span></span>  
 <span data-ttu-id="c81cf-150">다음과 같은 속성이 두 구성 요소 이름, 첫 번째 이름과 마지막 이름으로 전체 이름을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="c81cf-150">The following property stores a full name as two constituent names, the first name and the last name.</span></span> <span data-ttu-id="c81cf-151">호출 코드에서 읽을 때 `fullName`, `Get` 프로시저는 두 개의 구성 요소 이름을 결합을 전체 이름을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c81cf-151">When the calling code reads `fullName`, the `Get` procedure combines the two constituent names and returns the full name.</span></span> <span data-ttu-id="c81cf-152">호출 코드에서 새 전체 이름을 할당 하는 경우는 `Set` 프로시저를 두 개의 구성 요소 이름으로 분해 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="c81cf-152">When the calling code assigns a new full name, the `Set` procedure attempts to break it into two constituent names.</span></span> <span data-ttu-id="c81cf-153">공간을 찾지 못하면, 모든 첫 번째 이름으로 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="c81cf-153">If it does not find a space, it stores it all as the first name.</span></span>  
  
 <span data-ttu-id="c81cf-154">[!code-vb[VbVbcnProcedures #&8;](./codesnippet/VisualBasic/property-procedures_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="c81cf-154">[!code-vb[VbVbcnProcedures#8](./codesnippet/VisualBasic/property-procedures_1.vb)]</span></span>  
  
 <span data-ttu-id="c81cf-155">다음 예제에서는의 속성 프로시저를 호출 하는 일반적인 `fullName`합니다.</span><span class="sxs-lookup"><span data-stu-id="c81cf-155">The following example shows typical calls to the property procedures of `fullName`.</span></span>  
  
 <span data-ttu-id="c81cf-156">[!code-vb[VbVbcnProcedures #&9;](./codesnippet/VisualBasic/property-procedures_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="c81cf-156">[!code-vb[VbVbcnProcedures#9](./codesnippet/VisualBasic/property-procedures_2.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c81cf-157">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c81cf-157">See Also</span></span>  
 <span data-ttu-id="c81cf-158">[프로시저](./index.md) </span><span class="sxs-lookup"><span data-stu-id="c81cf-158">[Procedures](./index.md) </span></span>  
<span data-ttu-id="c81cf-159"> [Function 프로시저](./function-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="c81cf-159"> [Function Procedures](./function-procedures.md) </span></span>  
<span data-ttu-id="c81cf-160"> [연산자 프로시저](./operator-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="c81cf-160"> [Operator Procedures](./operator-procedures.md) </span></span>  
<span data-ttu-id="c81cf-161"> [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="c81cf-161"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="c81cf-162"> [Visual Basic에서 속성과 변수의 차이점](./differences-between-properties-and-variables.md) </span><span class="sxs-lookup"><span data-stu-id="c81cf-162"> [Differences Between Properties and Variables in Visual Basic](./differences-between-properties-and-variables.md) </span></span>  
<span data-ttu-id="c81cf-163"> [방법: 속성 만들기](./how-to-create-a-property.md) </span><span class="sxs-lookup"><span data-stu-id="c81cf-163"> [How to: Create a Property](./how-to-create-a-property.md) </span></span>  
<span data-ttu-id="c81cf-164"> [방법: 속성 프로시저 호출](./how-to-call-a-property-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="c81cf-164"> [How to: Call a Property Procedure](./how-to-call-a-property-procedure.md) </span></span>  
<span data-ttu-id="c81cf-165"> [방법: 선언 하 고 Visual Basic의 기본 속성 호출](./how-to-declare-and-call-a-default-property.md) </span><span class="sxs-lookup"><span data-stu-id="c81cf-165"> [How to: Declare and Call a Default Property in Visual Basic](./how-to-declare-and-call-a-default-property.md) </span></span>  
<span data-ttu-id="c81cf-166"> [방법: 속성 값 입력](./how-to-put-a-value-in-a-property.md) </span><span class="sxs-lookup"><span data-stu-id="c81cf-166"> [How to: Put a Value in a Property](./how-to-put-a-value-in-a-property.md) </span></span>  
<span data-ttu-id="c81cf-167"> [방법: 속성에서 값 가져오기](./how-to-get-a-value-from-a-property.md)</span><span class="sxs-lookup"><span data-stu-id="c81cf-167"> [How to: Get a Value from a Property](./how-to-get-a-value-from-a-property.md)</span></span>
