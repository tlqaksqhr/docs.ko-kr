---
title: "방법: 프로시저 (Visual Basic)에 대 한 매개 변수를 정의 합니다. | Microsoft 문서"
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
- procedure parameters, defining data types for
- procedures, parameters
- procedures, defining
- Visual Basic code, procedures
- procedure parameters, defining
ms.assetid: 7962808d-407e-4e84-984e-43e9857c53c9
caps.latest.revision: 15
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
ms.openlocfilehash: 5a29bab1c18920d293c51d83d4d8cffdcefe936c
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-define-a-parameter-for-a-procedure-visual-basic"></a><span data-ttu-id="25e6c-102">방법: 프로시저의 매개 변수 정의(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="25e6c-102">How to: Define a Parameter for a Procedure (Visual Basic)</span></span>
<span data-ttu-id="25e6c-103">A *매개 변수* 호출 코드를 호출할 때 프로시저에 값을 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25e6c-103">A *parameter* allows the calling code to pass a value to the procedure when it calls it.</span></span> <span data-ttu-id="25e6c-104">동일한 방식으로 변수를 선언 하면 해당 이름 및 데이터 형식을 지정 하는 프로시저에 대 한 각 매개 변수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="25e6c-104">You declare each parameter for a procedure the same way you declare a variable, specifying its name and data type.</span></span> <span data-ttu-id="25e6c-105">또한 전달 메커니즘을 지정 및 매개 변수는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="25e6c-105">You also specify the passing mechanism, and whether the parameter is optional.</span></span>  
  
 <span data-ttu-id="25e6c-106">자세한 내용은 참조 [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="25e6c-106">For more information, see [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md).</span></span>  
  
### <a name="to-define-a-procedure-parameter"></a><span data-ttu-id="25e6c-107">프로시저 매개 변수를 정의 하려면</span><span class="sxs-lookup"><span data-stu-id="25e6c-107">To define a procedure parameter</span></span>  
  
1.  <span data-ttu-id="25e6c-108">프로시저 선언에서 매개 변수 이름이 다른 매개 변수에서 쉼표로 구분 되는 프로시저의 매개 변수 목록에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="25e6c-108">In the procedure declaration, add the parameter name to the procedure's parameter list, separating it from other parameters by commas.</span></span>  
  
2.  <span data-ttu-id="25e6c-109">매개 변수의 데이터 형식을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="25e6c-109">Decide the data type of the parameter.</span></span>  
  
3.  <span data-ttu-id="25e6c-110">매개 변수 이름 뒤에 `As` 데이터 형식을 지정 하는 절.</span><span class="sxs-lookup"><span data-stu-id="25e6c-110">Follow the parameter name with an `As` clause to specify the data type.</span></span>  
  
4.  <span data-ttu-id="25e6c-111">매개 변수에 대해 원하는 전달 메커니즘을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="25e6c-111">Decide the passing mechanism you want for the parameter.</span></span> <span data-ttu-id="25e6c-112">일반적으로 프로시저 호출 코드에서 해당 값을 변경할 수 있게 되기를 원하지 않는 한 값으로 매개 변수를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="25e6c-112">Normally you pass a parameter by value, unless you want the procedure to be able to change its value in the calling code.</span></span>  
  
5.  <span data-ttu-id="25e6c-113">매개 변수 이름 앞에 야 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) 또는 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) 전달 메커니즘을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="25e6c-113">Precede the parameter name with [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) to specify the passing mechanism.</span></span> <span data-ttu-id="25e6c-114">자세한 내용은 참조 [차이 사이 값과 참조로 인수를 전달](./differences-between-passing-an-argument-by-value-and-by-reference.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="25e6c-114">For more information, see [Differences Between Passing an Argument By Value and By Reference](./differences-between-passing-an-argument-by-value-and-by-reference.md).</span></span>  
  
6.  <span data-ttu-id="25e6c-115">경우에 매개 변수는 선택 사항, 전달 메커니즘 앞에 [옵션](../../../../visual-basic/language-reference/modifiers/optional.md) 등호로 매개 변수 데이터 형식에 따라 (`=`) 및 기본 값입니다.</span><span class="sxs-lookup"><span data-stu-id="25e6c-115">If the parameter is optional, precede the passing mechanism with [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) and follow the parameter data type with an equal sign (`=`) and a default value.</span></span>  
  
     <span data-ttu-id="25e6c-116">개요를 정의 하는 다음 예제는 `Sub` 세 개의 매개 변수가 있는 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="25e6c-116">The following example defines the outline of a `Sub` procedure with three parameters.</span></span> <span data-ttu-id="25e6c-117">처음 두 개의 필수 필드 이며 세 번째는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="25e6c-117">The first two are required and the third is optional.</span></span> <span data-ttu-id="25e6c-118">매개 변수 선언 매개 변수 목록에 쉼표로 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25e6c-118">The parameter declarations are separated in the parameter list by commas.</span></span>  
  
     <span data-ttu-id="25e6c-119">[!code-vb[VbVbcnProcedures #&33;](./codesnippet/VisualBasic/how-to-define-a-parameter-for-a-procedure_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="25e6c-119">[!code-vb[VbVbcnProcedures#33](./codesnippet/VisualBasic/how-to-define-a-parameter-for-a-procedure_1.vb)]</span></span>  
  
     <span data-ttu-id="25e6c-120">첫 번째 매개 변수가 허용는 `customer` 개체 및 `updateCustomer` 에 전달 된 변수를 직접 업데이트할 수 `c` 인수 전달 되기 때문에 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="25e6c-120">The first parameter accepts a `customer` object, and `updateCustomer` can directly update the variable passed to `c` because the argument is passed [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md).</span></span> <span data-ttu-id="25e6c-121">프로시저 전달 되므로 마지막 두 인수 값을 변경할 수 없습니다 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="25e6c-121">The procedure cannot change the values of the last two arguments because they are passed [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span></span>  
  
     <span data-ttu-id="25e6c-122">호출 코드에 대 한 값을 제공 하지 않는 경우는 `level` 매개 변수를 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 기본값인 0으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="25e6c-122">If the calling code does not supply a value for the `level` parameter, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] sets it to the default value of 0.</span></span>  
  
     <span data-ttu-id="25e6c-123">전환 하는 형식 검사 ([Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md))은 `Off`, `As` 매개 변수를 정의 하는 경우 절은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="25e6c-123">If the type checking switch ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) is `Off`, the `As` clause is optional when you define a parameter.</span></span> <span data-ttu-id="25e6c-124">그러나 하나의 매개 변수를 사용 하는 경우는 `As` 절 모두에 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="25e6c-124">However, if any one parameter uses an `As` clause, all of them must use it.</span></span> <span data-ttu-id="25e6c-125">형식 검사 스위치가 경우 `On`, `As` 절은 모든 매개 변수 정의에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="25e6c-125">If the type checking switch is `On`, the `As` clause is required for every parameter definition.</span></span>  
  
     <span data-ttu-id="25e6c-126">모든 프로그래밍 요소에 대 한 데이터 형식 지정 이라고 *강력한 형식 지정*합니다.</span><span class="sxs-lookup"><span data-stu-id="25e6c-126">Specifying data types for all your programming elements is known as *strong typing*.</span></span> <span data-ttu-id="25e6c-127">설정한 경우 `Option Strict On`, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 강력한 형식 지정을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="25e6c-127">When you set `Option Strict On`, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] enforces strong typing.</span></span> <span data-ttu-id="25e6c-128">이 것이 좋습니다 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="25e6c-128">This is strongly recommended, for the following reasons:</span></span>  
  
    -   <span data-ttu-id="25e6c-129">변수 및 매개 변수에 대 한 IntelliSense 지원도를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25e6c-129">It enables IntelliSense support for your variables and parameters.</span></span> <span data-ttu-id="25e6c-130">이렇게 하면 코드의 입력 속성 및 다른 멤버를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25e6c-130">This allows you to see their properties and other members as you type in your code.</span></span>  
  
    -   <span data-ttu-id="25e6c-131">컴파일러를에 형식 검사를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25e6c-131">It allows the compiler to perform type checking.</span></span> <span data-ttu-id="25e6c-132">이렇게 하면 catch 문을 런타임에 오버플로와 같은 오류로 인해 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25e6c-132">This helps catch statements that can fail at run time due to errors such as overflow.</span></span> <span data-ttu-id="25e6c-133">또한 지원 하지 않는 개체에 메서드 호출을 찾아냅니다.</span><span class="sxs-lookup"><span data-stu-id="25e6c-133">It also catches calls to methods on objects that do not support them.</span></span>  
  
    -   <span data-ttu-id="25e6c-134">그 결과, 코드의 실행이 빨라집니다.</span><span class="sxs-lookup"><span data-stu-id="25e6c-134">It results in faster execution of your code.</span></span> <span data-ttu-id="25e6c-135">이 대 한 한 가지 이유 하는 경우 프로그래밍 요소에 대 한 데이터 형식을 지정 하지 않으면는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 컴파일러가 할당은 `Object` 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="25e6c-135">One reason for this is that if you do not specify a data type for a programming element, the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler assigns it the `Object` type.</span></span> <span data-ttu-id="25e6c-136">컴파일된 코드 사이 변환 해야 할 수 `Object` 및 다른 데이터 형식의 경우 성능이 떨어집니다.</span><span class="sxs-lookup"><span data-stu-id="25e6c-136">Your compiled code might have to convert back and forth between `Object` and other data types, which reduces performance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25e6c-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="25e6c-137">See Also</span></span>  
 <span data-ttu-id="25e6c-138">[프로시저](./index.md) </span><span class="sxs-lookup"><span data-stu-id="25e6c-138">[Procedures](./index.md) </span></span>  
<span data-ttu-id="25e6c-139"> [Sub 프로시저](./sub-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="25e6c-139"> [Sub Procedures](./sub-procedures.md) </span></span>  
<span data-ttu-id="25e6c-140"> [Function 프로시저](./function-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="25e6c-140"> [Function Procedures](./function-procedures.md) </span></span>  
<span data-ttu-id="25e6c-141"> [방법: 프로시저에 인수 전달](./how-to-pass-arguments-to-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="25e6c-141"> [How to: Pass Arguments to a Procedure](./how-to-pass-arguments-to-a-procedure.md) </span></span>  
<span data-ttu-id="25e6c-142"> [값 및 참조로 인수 전달](./passing-arguments-by-value-and-by-reference.md) </span><span class="sxs-lookup"><span data-stu-id="25e6c-142"> [Passing Arguments by Value and by Reference](./passing-arguments-by-value-and-by-reference.md) </span></span>  
<span data-ttu-id="25e6c-143"> [재귀 프로시저](./recursive-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="25e6c-143"> [Recursive Procedures](./recursive-procedures.md) </span></span>  
<span data-ttu-id="25e6c-144"> [프로시저 오버 로드](./procedure-overloading.md) </span><span class="sxs-lookup"><span data-stu-id="25e6c-144"> [Procedure Overloading](./procedure-overloading.md) </span></span>  
<span data-ttu-id="25e6c-145"> [개체 및 클래스](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) </span><span class="sxs-lookup"><span data-stu-id="25e6c-145"> [Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) </span></span>  
<span data-ttu-id="25e6c-146"> [개체 지향 프로그래밍](http://msdn.microsoft.com/library/1cf6e655-3f30-45f1-9a5d-4a88ca24a1c2)</span><span class="sxs-lookup"><span data-stu-id="25e6c-146"> [Object-Oriented Programming](http://msdn.microsoft.com/library/1cf6e655-3f30-45f1-9a5d-4a88ca24a1c2)</span></span>
