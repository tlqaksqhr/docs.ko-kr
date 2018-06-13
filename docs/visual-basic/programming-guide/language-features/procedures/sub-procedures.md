---
title: Sub 프로시저(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Sub procedures [Visual Basic], about Sub procedures
- statement blocks
- Sub procedures [Visual Basic], calling
- procedures [Visual Basic], calling
- Sub procedures [Visual Basic], syntax
- Sub procedures
- procedures [Visual Basic], Sub
- syntax [Visual Basic], Sub procedures
ms.assetid: 6a0a4958-ed0a-4d3d-8d31-0772c82bda58
ms.openlocfilehash: 3286df1a5babfcf7d6b759ff5c9a920bb44f51ab
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33652567"
---
# <a name="sub-procedures-visual-basic"></a><span data-ttu-id="ec215-102">Sub 프로시저(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ec215-102">Sub Procedures (Visual Basic)</span></span>
<span data-ttu-id="ec215-103">A `Sub` 절차는 일련의 Visual Basic 문으로 둘러싸인는 `Sub` 및 `End Sub` 문.</span><span class="sxs-lookup"><span data-stu-id="ec215-103">A `Sub` procedure is a series of Visual Basic statements enclosed by the `Sub` and `End Sub` statements.</span></span> <span data-ttu-id="ec215-104">`Sub` 프로시저는 작업을 수행한 다음 호출 코드에 제어를 반환 하지만 호출 코드에는 값을 반환 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ec215-104">The `Sub` procedure performs a task and then returns control to the calling code, but it does not return a value to the calling code.</span></span>  
  
 <span data-ttu-id="ec215-105">프로시저가 호출 될 때마다 해당 문이 실행 됩니다, 다음 실행 첫 번째 문에서 시작 하는 경우는 `Sub` 문과 여 첫 번째 `End Sub`, `Exit Sub`, 또는 `Return` 문을 발견 했습니다.</span><span class="sxs-lookup"><span data-stu-id="ec215-105">Each time the procedure is called, its statements are executed, starting with the first executable statement after the `Sub` statement and ending with the first `End Sub`, `Exit Sub`, or `Return` statement encountered.</span></span>  
  
 <span data-ttu-id="ec215-106">정의할 수는 `Sub` 모듈, 클래스 및 구조체의 절차입니다.</span><span class="sxs-lookup"><span data-stu-id="ec215-106">You can define a `Sub` procedure in modules, classes, and structures.</span></span> <span data-ttu-id="ec215-107">기본적으로는 `Public`을 호출할 수 어디에서 모듈, 클래스 또는 정의 된 구조체에 액세스 권한이 있는 응용 프로그램에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec215-107">By default, it is `Public`, which means you can call it from anywhere in your application that has access to the module, class, or structure in which you defined it.</span></span> <span data-ttu-id="ec215-108">용어 *메서드*, 설명는 `Sub` 또는 `Function` 프로시저는 정의 외부에서 액세스 되는 모듈, 클래스 또는 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="ec215-108">The term, *method*, describes a `Sub` or `Function` procedure that is accessed from outside its defining module, class, or structure.</span></span> <span data-ttu-id="ec215-109">자세한 내용은 [프로시저](./index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ec215-109">For more information, see [Procedures](./index.md).</span></span>  
  
 <span data-ttu-id="ec215-110">A `Sub` 프로시저 상수, 변수 또는 호출 코드에 의해 전달 된 식 등의 인수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec215-110">A `Sub` procedure can take arguments, such as constants, variables, or expressions, which are passed to it by the calling code.</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="ec215-111">선언 구문</span><span class="sxs-lookup"><span data-stu-id="ec215-111">Declaration Syntax</span></span>  
 <span data-ttu-id="ec215-112">선언 구문이 `Sub` 절차는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ec215-112">The syntax for declaring a `Sub` procedure is as follows:</span></span>  
  
 <span data-ttu-id="ec215-113">`[` *한정자* `] Sub` *subname* `[(` *parameterlist* `)]`</span><span class="sxs-lookup"><span data-stu-id="ec215-113">`[` *modifiers* `] Sub`  *subname* `[(` *parameterlist* `)]`</span></span>  
  
 `' Statements of the Sub procedure.`  
  
 `End Sub`  
  
 <span data-ttu-id="ec215-114">`modifiers` 오버 로드, 재정의 공유 및 숨김 하는 방법에 대 한 정보와 액세스 수준을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec215-114">The `modifiers` can specify access level and information about overloading, overriding, sharing, and shadowing.</span></span> <span data-ttu-id="ec215-115">자세한 내용은 참조 [Sub 문](../../../../visual-basic/language-reference/statements/sub-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ec215-115">For more information, see [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md).</span></span>  
  
## <a name="parameter-declaration"></a><span data-ttu-id="ec215-116">매개 변수 선언</span><span class="sxs-lookup"><span data-stu-id="ec215-116">Parameter Declaration</span></span>  
 <span data-ttu-id="ec215-117">유사 하 게 어떻게 변수를 선언 하면, 매개 변수 이름과 데이터 형식을 지정 하면 각 프로시저 매개 변수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec215-117">You declare each procedure parameter similarly to how you declare a variable, specifying the parameter name and data type.</span></span> <span data-ttu-id="ec215-118">전달 메커니즘을 지정할 수 있습니다 및 선택적 매개 변수 인지 또는 매개 변수 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="ec215-118">You can also specify the passing mechanism, and whether the parameter is optional or a parameter array.</span></span>  
  
 <span data-ttu-id="ec215-119">매개 변수 목록에서 각 매개 변수에 대 한 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ec215-119">The syntax for each parameter in the parameter list is as follows:</span></span>  
  
 <span data-ttu-id="ec215-120">`[Optional] [ByVal | ByRef] [ParamArray]`  *parametername*`As`*데이터 형식*</span><span class="sxs-lookup"><span data-stu-id="ec215-120">`[Optional] [ByVal | ByRef] [ParamArray]`  *parametername*  `As`  *datatype*</span></span>  
  
 <span data-ttu-id="ec215-121">매개 변수가 선택적 이면 해당 선언의 일부로 기본값도 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec215-121">If the parameter is optional, you must also supply a default value as part of its declaration.</span></span> <span data-ttu-id="ec215-122">기본값을 지정 하기 위한 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ec215-122">The syntax for specifying a default value is as follows:</span></span>  
  
 <span data-ttu-id="ec215-123">`Optional [ByVal | ByRef]`  *parametername*`As`*datatype*`=`*defaultvalue*</span><span class="sxs-lookup"><span data-stu-id="ec215-123">`Optional [ByVal | ByRef]`  *parametername*  `As`  *datatype*  `=`  *defaultvalue*</span></span>  
  
### <a name="parameters-as-local-variables"></a><span data-ttu-id="ec215-124">지역 변수로 매개 변수</span><span class="sxs-lookup"><span data-stu-id="ec215-124">Parameters as Local Variables</span></span>  
 <span data-ttu-id="ec215-125">제어 절차를 전달 하는 경우 각 매개 변수에 지역 변수로 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec215-125">When control passes to the procedure, each parameter is treated as a local variable.</span></span> <span data-ttu-id="ec215-126">즉, 프로시저의 수명이 같습니다 해당 범위는 전체 절차입니다.</span><span class="sxs-lookup"><span data-stu-id="ec215-126">This means that its lifetime is the same as that of the procedure, and its scope is the whole procedure.</span></span>  
  
## <a name="calling-syntax"></a><span data-ttu-id="ec215-127">호출 구문</span><span class="sxs-lookup"><span data-stu-id="ec215-127">Calling Syntax</span></span>  
 <span data-ttu-id="ec215-128">호출 된 `Sub` 독립 실행형 호출 문 명시적으로 사용 하 여 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="ec215-128">You invoke a `Sub` procedure explicitly with a stand-alone calling statement.</span></span> <span data-ttu-id="ec215-129">식에서 해당 이름을 사용 하 여 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ec215-129">You cannot call it by using its name in an expression.</span></span> <span data-ttu-id="ec215-130">모든 인수는 옵션에 대 한 값을 제공 해야 하 고 인수 목록을 괄호로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec215-130">You must provide values for all arguments that are not optional, and you must enclose the argument list in parentheses.</span></span> <span data-ttu-id="ec215-131">인수를 제공 하는 경우 괄호를 선택적으로 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec215-131">If no arguments are supplied, you can optionally omit the parentheses.</span></span> <span data-ttu-id="ec215-132">사용은 `Call` 키워드는 선택 사항 이지만 권장 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ec215-132">The use of the `Call` keyword is optional but not recommended.</span></span>  
  
 <span data-ttu-id="ec215-133">에 대 한 호출에 대 한 구문은 `Sub` 절차는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ec215-133">The syntax for a call to a `Sub` procedure is as follows:</span></span>  
  
 <span data-ttu-id="ec215-134">`[Call]`  *subname* `[(` *argumentlist* `)]`</span><span class="sxs-lookup"><span data-stu-id="ec215-134">`[Call]`  *subname* `[(` *argumentlist* `)]`</span></span>  
  
 <span data-ttu-id="ec215-135">호출할 수 있습니다는 `Sub` 정의 하는 클래스 외부에서 메서드.</span><span class="sxs-lookup"><span data-stu-id="ec215-135">You can call a `Sub` method from outside the class that defines it.</span></span> <span data-ttu-id="ec215-136">사용 해야 하는 첫째, 고 `New` 키워드는 클래스의 인스턴스를 만들거나 메서드를 호출 하는 클래스의 인스턴스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec215-136">First, you have to use the `New` keyword to create an instance of the class, or call a method that returns an instance of the class.</span></span> <span data-ttu-id="ec215-137">자세한 내용은 참조 [New 연산자](../../../../visual-basic/language-reference/operators/new-operator.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ec215-137">For more information, see [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md).</span></span> <span data-ttu-id="ec215-138">그런 다음, 호출 하려면 다음 구문을 사용할 수는 `Sub` 인스턴스 개체에서 메서드:</span><span class="sxs-lookup"><span data-stu-id="ec215-138">Then, you can use the following syntax to call the `Sub` method on the instance object:</span></span>  
  
 <span data-ttu-id="ec215-139">*개체*. *methodname*`[(`*argumentlist*`)]`</span><span class="sxs-lookup"><span data-stu-id="ec215-139">*Object*.*methodname*`[(`*argumentlist*`)]`</span></span>  
  
### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="ec215-140">선언 및 호출의 그림</span><span class="sxs-lookup"><span data-stu-id="ec215-140">Illustration of Declaration and Call</span></span>  
 <span data-ttu-id="ec215-141">다음 `Sub` 프로시저는 응용 프로그램에서 수행 하려는 작업을 컴퓨터 사용자에 게 알려도 타임 스탬프가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec215-141">The following `Sub` procedure tells the computer operator which task the application is about to perform, and also displays a time stamp.</span></span> <span data-ttu-id="ec215-142">모든 작업의 시작 부분에이 코드를 복제 하는 대신 응용 프로그램 호출 `tellOperator` 다양 한 위치에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec215-142">Instead of duplicating this code at the start of every task, the application just calls `tellOperator` from various locations.</span></span> <span data-ttu-id="ec215-143">각 호출에서 문자열을 전달 하는 `task` 시작 하려는 작업을 식별 하는 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="ec215-143">Each call passes a string in the `task` argument that identifies the task being started.</span></span>  
  
 [!code-vb[VbVbcnProcedures#2](./codesnippet/VisualBasic/sub-procedures_1.vb)]  
  
 <span data-ttu-id="ec215-144">다음 예제에서는 호출을 `tellOperator`합니다.</span><span class="sxs-lookup"><span data-stu-id="ec215-144">The following example shows a typical call to `tellOperator`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#3](./codesnippet/VisualBasic/sub-procedures_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="ec215-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ec215-145">See Also</span></span>  
 [<span data-ttu-id="ec215-146">절차</span><span class="sxs-lookup"><span data-stu-id="ec215-146">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="ec215-147">Function 프로시저</span><span class="sxs-lookup"><span data-stu-id="ec215-147">Function Procedures</span></span>](./function-procedures.md)  
 [<span data-ttu-id="ec215-148">속성 프로시저</span><span class="sxs-lookup"><span data-stu-id="ec215-148">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="ec215-149">연산자 프로시저</span><span class="sxs-lookup"><span data-stu-id="ec215-149">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="ec215-150">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="ec215-150">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="ec215-151">Sub 문</span><span class="sxs-lookup"><span data-stu-id="ec215-151">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="ec215-152">방법: 값을 반환하지 않는 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="ec215-152">How to: Call a Procedure that Does Not Return a Value</span></span>](./how-to-call-a-procedure-that-does-not-return-a-value.md)  
 [<span data-ttu-id="ec215-153">방법: Visual Basic의 이벤트 처리기를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec215-153">How to: Call an Event Handler in Visual Basic</span></span>](./how-to-call-an-event-handler.md)
