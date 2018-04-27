---
title: '방법: 프로시저의 매개 변수 정의(Visual Basic)'
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedure parameters [Visual Basic], defining data types for
- procedures [Visual Basic], parameters
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedure parameters [Visual Basic], defining
ms.assetid: 7962808d-407e-4e84-984e-43e9857c53c9
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: eb4bac9208c03fd18e1904f58b247824d2c215da
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-define-a-parameter-for-a-procedure-visual-basic"></a><span data-ttu-id="54655-102">방법: 프로시저의 매개 변수 정의(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="54655-102">How to: Define a Parameter for a Procedure (Visual Basic)</span></span>
<span data-ttu-id="54655-103">A *매개 변수* 호출 코드를 호출할 때 프로시저에 값을 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54655-103">A *parameter* allows the calling code to pass a value to the procedure when it calls it.</span></span> <span data-ttu-id="54655-104">동일한 방식으로 변수를 선언 이름 및 데이터 형식을 지정 하는 프로시저에 대 한 각 매개 변수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="54655-104">You declare each parameter for a procedure the same way you declare a variable, specifying its name and data type.</span></span> <span data-ttu-id="54655-105">전달 메커니즘을 지정할 수도 및 매개 변수는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="54655-105">You also specify the passing mechanism, and whether the parameter is optional.</span></span>  
  
 <span data-ttu-id="54655-106">자세한 내용은 참조 [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="54655-106">For more information, see [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md).</span></span>  
  
### <a name="to-define-a-procedure-parameter"></a><span data-ttu-id="54655-107">프로시저 매개 변수를 정의 하려면</span><span class="sxs-lookup"><span data-stu-id="54655-107">To define a procedure parameter</span></span>  
  
1.  <span data-ttu-id="54655-108">프로시저 선언에서 매개 변수 이름을 다른 매개 변수에서 쉼표로 구분 되는 프로시저의 매개 변수 목록에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="54655-108">In the procedure declaration, add the parameter name to the procedure's parameter list, separating it from other parameters by commas.</span></span>  
  
2.  <span data-ttu-id="54655-109">매개 변수의 데이터 형식을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="54655-109">Decide the data type of the parameter.</span></span>  
  
3.  <span data-ttu-id="54655-110">매개 변수 이름 뒤에 `As` 절 데이터 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="54655-110">Follow the parameter name with an `As` clause to specify the data type.</span></span>  
  
4.  <span data-ttu-id="54655-111">매개 변수에 대해 사용할 전달 메커니즘을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="54655-111">Decide the passing mechanism you want for the parameter.</span></span> <span data-ttu-id="54655-112">일반적으로 프로시저에서 호출 코드의 해당 값을 변경할 수를 사용 하려는 경우가 아니면 값 매개 변수 전달.</span><span class="sxs-lookup"><span data-stu-id="54655-112">Normally you pass a parameter by value, unless you want the procedure to be able to change its value in the calling code.</span></span>  
  
5.  <span data-ttu-id="54655-113">매개 변수 이름 앞 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) 또는 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) 전달 메커니즘을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="54655-113">Precede the parameter name with [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) to specify the passing mechanism.</span></span> <span data-ttu-id="54655-114">자세한 내용은 참조 [차이점 사이의 값과 참조로 인수를 전달](./differences-between-passing-an-argument-by-value-and-by-reference.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="54655-114">For more information, see [Differences Between Passing an Argument By Value and By Reference](./differences-between-passing-an-argument-by-value-and-by-reference.md).</span></span>  
  
6.  <span data-ttu-id="54655-115">매개 변수가 선택적 이면 앞 전달 메커니즘 [옵션](../../../../visual-basic/language-reference/modifiers/optional.md) 등호로 매개 변수 데이터 형식에 따라 (`=`) 및 기본 값입니다.</span><span class="sxs-lookup"><span data-stu-id="54655-115">If the parameter is optional, precede the passing mechanism with [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) and follow the parameter data type with an equal sign (`=`) and a default value.</span></span>  
  
     <span data-ttu-id="54655-116">다음 예제에서는 정의의 개요는 `Sub` 세 개의 매개 변수가 있는 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="54655-116">The following example defines the outline of a `Sub` procedure with three parameters.</span></span> <span data-ttu-id="54655-117">처음 두 필요 하며 세 번째는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="54655-117">The first two are required and the third is optional.</span></span> <span data-ttu-id="54655-118">매개 변수 선언 매개 변수 목록에 쉼표로 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54655-118">The parameter declarations are separated in the parameter list by commas.</span></span>  
  
     [!code-vb[VbVbcnProcedures#33](./codesnippet/VisualBasic/how-to-define-a-parameter-for-a-procedure_1.vb)]  
  
     <span data-ttu-id="54655-119">첫 번째 매개 변수가 허용는 `customer` 개체 및 `updateCustomer` 에 전달 된 변수를 직접 업데이트할 수 `c` 인수 전달 되기 때문에 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="54655-119">The first parameter accepts a `customer` object, and `updateCustomer` can directly update the variable passed to `c` because the argument is passed [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md).</span></span> <span data-ttu-id="54655-120">프로시저 전달 되기 때문에 마지막 두 인수 값을 변경할 수 없습니다 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="54655-120">The procedure cannot change the values of the last two arguments because they are passed [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span></span>  
  
     <span data-ttu-id="54655-121">호출 코드에 대 한 값을 제공 하지 않는 경우는 `level` 매개 변수, Visual Basic 설정 기본값인 0입니다.</span><span class="sxs-lookup"><span data-stu-id="54655-121">If the calling code does not supply a value for the `level` parameter, Visual Basic sets it to the default value of 0.</span></span>  
  
     <span data-ttu-id="54655-122">형식 검사 스위치 하는 경우 ([Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md))은 `Off`, `As` 매개 변수를 정의할 때 절은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="54655-122">If the type checking switch ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) is `Off`, the `As` clause is optional when you define a parameter.</span></span> <span data-ttu-id="54655-123">그러나 하나의 매개 변수를 사용 하는 경우는 `As` 절을 모두 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="54655-123">However, if any one parameter uses an `As` clause, all of them must use it.</span></span> <span data-ttu-id="54655-124">형식 검사 스위치 이면 `On`, `As` 절은 모든 매개 변수 정의에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="54655-124">If the type checking switch is `On`, the `As` clause is required for every parameter definition.</span></span>  
  
     <span data-ttu-id="54655-125">모든 프로그래밍 요소에 대 한 데이터 형식 지정 이라고 *강력한 형식 지정*합니다.</span><span class="sxs-lookup"><span data-stu-id="54655-125">Specifying data types for all your programming elements is known as *strong typing*.</span></span> <span data-ttu-id="54655-126">설정 하는 경우 `Option Strict On`, Visual Basic에서 강력한 형식 지정을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="54655-126">When you set `Option Strict On`, Visual Basic enforces strong typing.</span></span> <span data-ttu-id="54655-127">이 것이 좋습니다 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="54655-127">This is strongly recommended, for the following reasons:</span></span>  
  
    -   <span data-ttu-id="54655-128">변수 및 매개 변수에 대 한 IntelliSense 지원도를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54655-128">It enables IntelliSense support for your variables and parameters.</span></span> <span data-ttu-id="54655-129">그러면 코드에서 입력할 때 해당 속성 및 기타 멤버를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54655-129">This allows you to see their properties and other members as you type in your code.</span></span>  
  
    -   <span data-ttu-id="54655-130">컴파일러를 형식 검사를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54655-130">It allows the compiler to perform type checking.</span></span> <span data-ttu-id="54655-131">이렇게 하면 catch 문을 오버플로와 같은 오류로 인해 런타임에 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54655-131">This helps catch statements that can fail at run time due to errors such as overflow.</span></span> <span data-ttu-id="54655-132">또한 지원 하지 않는 개체에 메서드 호출을 catch 합니다.</span><span class="sxs-lookup"><span data-stu-id="54655-132">It also catches calls to methods on objects that do not support them.</span></span>  
  
    -   <span data-ttu-id="54655-133">코드의 더 빠른 실행에서 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="54655-133">It results in faster execution of your code.</span></span> <span data-ttu-id="54655-134">이 대 한 한 가지 이유는 경우 프로그래밍 요소에 대 한 데이터 형식을 지정 하지 않으면, Visual Basic 컴파일러 할당은 `Object` 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="54655-134">One reason for this is that if you do not specify a data type for a programming element, the Visual Basic compiler assigns it the `Object` type.</span></span> <span data-ttu-id="54655-135">컴파일된 코드 사이 변환 해야 할 수 `Object` 및 다른 데이터 형식의 경우 성능이 떨어집니다.</span><span class="sxs-lookup"><span data-stu-id="54655-135">Your compiled code might have to convert back and forth between `Object` and other data types, which reduces performance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54655-136">참고자료</span><span class="sxs-lookup"><span data-stu-id="54655-136">See also</span></span>

 [<span data-ttu-id="54655-137">절차</span><span class="sxs-lookup"><span data-stu-id="54655-137">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="54655-138">Sub 프로시저</span><span class="sxs-lookup"><span data-stu-id="54655-138">Sub Procedures</span></span>](./sub-procedures.md)  
 [<span data-ttu-id="54655-139">Function 프로시저</span><span class="sxs-lookup"><span data-stu-id="54655-139">Function Procedures</span></span>](./function-procedures.md)  
 [<span data-ttu-id="54655-140">방법: 프로시저에 인수 전달</span><span class="sxs-lookup"><span data-stu-id="54655-140">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)  
 [<span data-ttu-id="54655-141">값 또는 참조로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="54655-141">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="54655-142">재귀 프로시저</span><span class="sxs-lookup"><span data-stu-id="54655-142">Recursive Procedures</span></span>](./recursive-procedures.md)  
 [<span data-ttu-id="54655-143">프로시저 오버로딩</span><span class="sxs-lookup"><span data-stu-id="54655-143">Procedure Overloading</span></span>](./procedure-overloading.md)  
 [<span data-ttu-id="54655-144">개체 및 클래스</span><span class="sxs-lookup"><span data-stu-id="54655-144">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [<span data-ttu-id="54655-145">개체 지향 프로그래밍(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="54655-145">Object-Oriented Programming (Visual Basic)</span></span>](../../concepts/object-oriented-programming.md)  
