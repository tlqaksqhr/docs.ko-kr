---
title: "문자열 이름을 사용하여 속성 또는 메서드 호출(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- passing operators [Visual Basic]
- strings [Visual Basic], passing new operators as
- objects [Visual Basic], setting properties
- setting properties, object properties at run time
- method calls [Visual Basic], strings
- methods [Visual Basic], calling with string names
- calling methods [Visual Basic], string names
- properties [Visual Basic], setting at run time
- CallByName function
ms.assetid: 79a7b8b4-b8c7-4ad8-aca8-12a9a2b32f03
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c5974257fb82fe83c66a480225da200c14338898
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="calling-a-property-or-method-using-a-string-name-visual-basic"></a><span data-ttu-id="7bb6c-102">문자열 이름을 사용하여 속성 또는 메서드 호출(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7bb6c-102">Calling a Property or Method Using a String Name (Visual Basic)</span></span>
<span data-ttu-id="7bb6c-103">대부분의 경우에서 디자인 타임에 개체의 메서드와 속성을 검색 하 고 처리 하기 위한 코드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb6c-103">In most cases, you can discover the properties and methods of an object at design time, and write code to handle them.</span></span> <span data-ttu-id="7bb6c-104">그러나 경우에 따라 있습니다 모를 수도 개체의 속성 및 메서드에 대 한 사전에 있고 속성을 지정 하거나 실행 시 메서드를 실행 하려면 최종 사용자의 유연성 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb6c-104">However, in some cases you may not know about an object's properties and methods in advance, or you may just want the flexibility of enabling an end user to specify properties or execute methods at run time.</span></span>  
  
## <a name="callbyname-function"></a><span data-ttu-id="7bb6c-105">CallByName 함수</span><span class="sxs-lookup"><span data-stu-id="7bb6c-105">CallByName Function</span></span>  
 <span data-ttu-id="7bb6c-106">예를 들어 COM 구성 요소는 연산자를 전달 하 여 사용자가 입력 한 식을 계산 하는 클라이언트 응용 프로그램을 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb6c-106">Consider, for example, a client application that evaluates expressions entered by the user by passing an operator to a COM component.</span></span> <span data-ttu-id="7bb6c-107">지속적으로 새 기능에 추가할 새 연산자를 필요로 하는 구성 요소를 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb6c-107">Suppose you are constantly adding new functions to the component that require new operators.</span></span> <span data-ttu-id="7bb6c-108">표준 개체 액세스 기술을 사용 하는 경우 다시 컴파일해야 하 고 새 연산자를 사용 하려면 클라이언트 응용 프로그램을 재배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb6c-108">When you use standard object access techniques, you must recompile and redistribute the client application before it could use the new operators.</span></span> <span data-ttu-id="7bb6c-109">이 문제를 방지 하려면 사용할 수 있습니다는 `CallByName` 함수를 응용 프로그램을 변경 하지 않고도 새 연산자를 문자열로 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb6c-109">To avoid this, you can use the `CallByName` function to pass the new operators as strings, without changing the application.</span></span>  
  
 <span data-ttu-id="7bb6c-110">`CallByName` 함수는 문자열을 사용 하 여 런타임 시 속성이 나 메서드를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb6c-110">The `CallByName` function lets you use a string to specify a property or method at run time.</span></span> <span data-ttu-id="7bb6c-111">에 대 한 시그니처는 `CallByName` 함수는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb6c-111">The signature for the `CallByName` function looks like this:</span></span>  
  
 <span data-ttu-id="7bb6c-112">*결과* = `CallByName`(*개체*, *ProcedureName*, *CallType*, *인수*())</span><span class="sxs-lookup"><span data-stu-id="7bb6c-112">*Result* = `CallByName`(*Object*, *ProcedureName*, *CallType*, *Arguments*())</span></span>  
  
 <span data-ttu-id="7bb6c-113">첫 번째 인수 *개체*, 작업을 수행할 원하는 개체의 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb6c-113">The first argument, *Object*, takes the name of the object you want to act upon.</span></span> <span data-ttu-id="7bb6c-114">*ProcedureName* 인수에는 호출할 메서드 또는 속성 프로시저의 이름을 포함 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="7bb6c-114">The *ProcedureName* argument takes a string that contains the name of the method or property procedure to be invoked.</span></span> <span data-ttu-id="7bb6c-115">*CallType* 인수를 호출 하는 프로시저의 종류를 나타내는 상수에는: 메서드 (`Microsoft.VisualBasic.CallType.Method`), 속성 읽기 (`Microsoft.VisualBasic.CallType.Get`), 또는 속성 설정 (`Microsoft.VisualBasic.CallType.Set`).</span><span class="sxs-lookup"><span data-stu-id="7bb6c-115">The *CallType* argument takes a constant that represents the type of procedure to invoke: a method (`Microsoft.VisualBasic.CallType.Method`), a property read (`Microsoft.VisualBasic.CallType.Get`), or a property set (`Microsoft.VisualBasic.CallType.Set`).</span></span> <span data-ttu-id="7bb6c-116">*인수* 인수는 선택 항목인 형식의 배열을 사용 `Object` 프로시저에 인수를 포함 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb6c-116">The *Arguments* argument, which is optional, takes an array of type `Object` that contains any arguments to the procedure.</span></span>  
  
 <span data-ttu-id="7bb6c-117">사용할 수 있습니다 `CallByName` 에서 개체를 늘리거나 현재 솔루션에 클래스를 가장 많이 사용 하 여 COM 개체에 액세스할 수 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="7bb6c-117">You can use `CallByName` with classes in your current solution, but it is most often used to access COM objects or objects from [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] assemblies.</span></span>  
  
 <span data-ttu-id="7bb6c-118">클래스를 포함 하는 어셈블리에 대 한 참조를 추가 한다고 가정 `MathClass`, 라는 새 함수가 `SquareRoot`다음 코드에 나온 것 처럼:</span><span class="sxs-lookup"><span data-stu-id="7bb6c-118">Suppose you add a reference to an assembly that contains a class named `MathClass`, which has a new function named `SquareRoot`, as shown in the following code:</span></span>  
  
 [!code-vb[VbVbalrOOP#53](../../../../visual-basic/misc/codesnippet/VisualBasic/calling-a-property-or-method-using-a-string-name_1.vb)]  
  
 <span data-ttu-id="7bb6c-119">응용 프로그램 제어 호출 되는 메서드 및 해당 인수에 텍스트 상자 컨트롤을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb6c-119">Your application could use text box controls to control which method will be called and its arguments.</span></span> <span data-ttu-id="7bb6c-120">예를 들어 경우 `TextBox1` 계산 되도록 식을 포함 하 고 `TextBox2` 는 함수 이름을 입력 하는 데 사용을 하는 데 다음 코드를 호출는 `SquareRoot` 의 식에서 함수 `TextBox1`:</span><span class="sxs-lookup"><span data-stu-id="7bb6c-120">For example, if `TextBox1` contains the expression to be evaluated, and `TextBox2` is used to enter the name of the function, you can use the following code to invoke the `SquareRoot` function on the expression in `TextBox1`:</span></span>  
  
 [!code-vb[VbVbalrOOP#54](../../../../visual-basic/misc/codesnippet/VisualBasic/calling-a-property-or-method-using-a-string-name_2.vb)]  
  
 <span data-ttu-id="7bb6c-121">"64"를 입력 하는 경우 `TextBox1`, "SquareRoot" `TextBox2`, 한 다음 호출에서 `CallMath` 프로시저, 된 숫자의 제곱근 `TextBox1` 평가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7bb6c-121">If you enter "64" in `TextBox1`, "SquareRoot" in `TextBox2`, and then call the `CallMath` procedure, the square root of the number in `TextBox1` is evaluated.</span></span> <span data-ttu-id="7bb6c-122">예제에서 코드 호출는 `SquareRoot` (사용 하는 필수 인수도 계산 되는 식을 포함 하는 문자열) 작동 하 고 "8" 반환 `TextBox1` (64의 제곱근).</span><span class="sxs-lookup"><span data-stu-id="7bb6c-122">The code in the example invokes the `SquareRoot` function (which takes a string that contains the expression to be evaluated as a required argument) and returns "8" in `TextBox1` (the square root of 64).</span></span> <span data-ttu-id="7bb6c-123">물론:의 잘못 된 문자열을 입력할 경우 `TextBox2`메서드 추가적인 필수 인수가 있으면 런타임에 오류가 발생 하는 경우 문자열에는 메서드 대신 속성의 이름을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bb6c-123">Of course, if the user enters an invalid string in `TextBox2`, if the string contains the name of a property instead of a method, or if the method had an additional required argument, a run-time error occurs.</span></span> <span data-ttu-id="7bb6c-124">사용 하는 경우 오류 처리 코드를 추가 해야 `CallByName` 이러한 열 데이터 나 다른 오류를 예상할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb6c-124">You have to add robust error-handling code when you use `CallByName` to anticipate these or any other errors.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7bb6c-125">동안는 `CallByName` 함수 일부 경우에 유용할 수 있지만, 성능에 미치는 영향에 대 한 유용성 균형을 맞춰야-를 사용 하 여 `CallByName` 프로시저를 호출 하는 런타임에 바인딩된 호출 보다 약간 더 느려집니다.</span><span class="sxs-lookup"><span data-stu-id="7bb6c-125">While the `CallByName` function may be useful in some cases, you must weigh its usefulness against the performance implications — using `CallByName` to invoke a procedure is slightly slower than a late-bound call.</span></span> <span data-ttu-id="7bb6c-126">반복적으로 호출 되, 예: 루프 내부으로 하는 함수를 호출 하는 경우 `CallByName` 성능에 심각한 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bb6c-126">If you are invoking a function that is called repeatedly, such as inside a loop, `CallByName` can have a severe effect on performance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bb6c-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7bb6c-127">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Interaction.CallByName%2A>  
 [<span data-ttu-id="7bb6c-128">개체 형식 확인</span><span class="sxs-lookup"><span data-stu-id="7bb6c-128">Determining Object Type</span></span>](../../../../visual-basic/programming-guide/language-features/early-late-binding/determining-object-type.md)
