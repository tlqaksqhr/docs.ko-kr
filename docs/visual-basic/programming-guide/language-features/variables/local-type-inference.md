---
title: 지역 형식 유추(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- local type inference
- vb.TypeInfer
helpviewer_keywords:
- Option Infer statement [Visual Basic]
- local type inference [Visual Basic]
- implicitly-typed local variables [Visual Basic]
- variables [Visual Basic], type inference
- inference [Visual Basic]
- type inference [Visual Basic]
ms.assetid: b8307f18-2e56-4ab3-a45a-826873f400f6
ms.openlocfilehash: b33b8b2d17c240e380377528d4f5d2f511381a7d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33655325"
---
# <a name="local-type-inference-visual-basic"></a><span data-ttu-id="e61d9-102">지역 형식 유추(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e61d9-102">Local Type Inference (Visual Basic)</span></span>
<span data-ttu-id="e61d9-103">Visual Basic 컴파일러를 사용 하 여 *형식 유추* 없이 선언 된 지역 변수의 데이터 형식을 결정 하는 `As` 절.</span><span class="sxs-lookup"><span data-stu-id="e61d9-103">The Visual Basic compiler uses *type inference* to determine the data types of local variables declared without an `As` clause.</span></span> <span data-ttu-id="e61d9-104">컴파일러는 초기화 식의 형식에서 변수의 형식을 유추합니다.</span><span class="sxs-lookup"><span data-stu-id="e61d9-104">The compiler infers the type of the variable from the type of the initialization expression.</span></span> <span data-ttu-id="e61d9-105">그러면 다음 예제와 같이 형식을 명시적으로 선언 하지 않고 변수를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e61d9-105">This enables you to declare variables without explicitly stating a type, as shown in the following example.</span></span> <span data-ttu-id="e61d9-106">선언 결과로 둘 다 `num1` 및 `num2` 는 정수로 강력한 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="e61d9-106">As a result of the declarations, both `num1` and `num2` are strongly typed as integers.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#1](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_1.vb)]  
 
> [!NOTE]
>  <span data-ttu-id="e61d9-107">원하지 않는 경우 `num2` 형식으로 이전 예제에는 `Integer`, 같은 선언을 사용 하 여 다른 형식을 지정할 수 있습니다 `Dim num3 As Object = 3` 또는 `Dim num4 As Double = 3`합니다.</span><span class="sxs-lookup"><span data-stu-id="e61d9-107">If you do not want `num2` in the previous example to be typed as an `Integer`, you can specify another type by using a declaration like `Dim num3 As Object = 3` or `Dim num4 As Double = 3`.</span></span>  

> [!NOTE]
>  <span data-ttu-id="e61d9-108">형식 유추에서 비정적 지역 변수;에 사용할 수 있습니다. 클래스 필드, 속성 또는 함수 형식을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e61d9-108">Type inference can be used only for non-static local variables; it cannot be used to determine the type of class fields, properties, or functions.</span></span>
 
 <span data-ttu-id="e61d9-109">지역 형식 유추는 프로시저 수준에서 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e61d9-109">Local type inference applies at procedure level.</span></span> <span data-ttu-id="e61d9-110">(클래스, 구조체, 모듈 또는 인터페이스를 제외한 내 블록 또는 프로시저일) 모듈 수준 변수를 선언 하는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e61d9-110">It cannot be used to declare variables at module level (within a class, structure, module, or interface but not within a procedure or block).</span></span> <span data-ttu-id="e61d9-111">경우 `num2` 이전 예제에서 프로시저의 지역 변수 대신 클래스의 필드에서 선언 된 오류를 발생 시키는 `Option Strict` on, 분류 및 `num2` 로 `Object` 와 `Option Strict` 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="e61d9-111">If `num2` in the previous example were a field of a class instead of a local variable in a procedure, the declaration would cause an error with `Option Strict` on, and would classify `num2` as an `Object` with `Option Strict` off.</span></span> <span data-ttu-id="e61d9-112">마찬가지로, 지역 형식 유추로 선언 된 프로시저 수준 변수에 적용 되지 않습니다 `Static`합니다.</span><span class="sxs-lookup"><span data-stu-id="e61d9-112">Similarly, local type inference does not apply to procedure level variables declared as `Static`.</span></span>  
  
## <a name="type-inference-vs-late-binding"></a><span data-ttu-id="e61d9-113">형식 유추와 런타임에 바인딩</span><span class="sxs-lookup"><span data-stu-id="e61d9-113">Type Inference vs. Late Binding</span></span>  
 <span data-ttu-id="e61d9-114">형식 유추를 사용 하는 코드는 런타임에 바인딩을 사용 하는 코드와 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="e61d9-114">Code that uses type inference resembles code that relies on late binding.</span></span> <span data-ttu-id="e61d9-115">그러나 형식 유추로 두는 대신 변수를 강력한 형식 `Object`합니다.</span><span class="sxs-lookup"><span data-stu-id="e61d9-115">However, type inference strongly types the variable instead of leaving it as `Object`.</span></span> <span data-ttu-id="e61d9-116">컴파일러는 변수 이니셜라이저를 사용 하 여 초기 바인딩 코드를 생성 하기 위해 컴파일 타임에 다음이 변수의 유형을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e61d9-116">The compiler uses a variable's initializer to determine the variable's type at compile time to produce early-bound code.</span></span> <span data-ttu-id="e61d9-117">이전 예에서 `num2`처럼 `num1`로 형식화 되는 `Integer`합니다.</span><span class="sxs-lookup"><span data-stu-id="e61d9-117">In the previous example, `num2`, like `num1`, is typed as an `Integer`.</span></span>  
  
 <span data-ttu-id="e61d9-118">런타임에 바인딩된 변수를 런타임에만 형식이 알려져의 초기 바인딩된 변수의 동작은 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="e61d9-118">The behavior of early-bound variables differs from that of late-bound variables, for which the type is known only at run time.</span></span> <span data-ttu-id="e61d9-119">초기 형식을 알 컴파일러를를 실행 하기 전에 문제를 식별, 정확 하 게, 메모리 할당 및 기타 최적화를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e61d9-119">Knowing the type early enables the compiler to identify problems before execution, allocate memory precisely, and perform other optimizations.</span></span> <span data-ttu-id="e61d9-120">초기 바인딩 Visual Basic 통합된 개발 환경을 (IDE) 개체의 멤버에 대 한 IntelliSense 도움말을 사용할 수 있도록 해줍니다.</span><span class="sxs-lookup"><span data-stu-id="e61d9-120">Early binding also enables the Visual Basic integrated development environment (IDE) to provide IntelliSense Help about the members of an object.</span></span> <span data-ttu-id="e61d9-121">초기 바인딩 성능에 대 한 기본 설정 이기도합니다.</span><span class="sxs-lookup"><span data-stu-id="e61d9-121">Early binding is also preferred for performance.</span></span> <span data-ttu-id="e61d9-122">런타임에 바인딩된 변수에 저장 된 모든 데이터 형식으로 래핑되어야 때문에 이것이 `Object`, 속도가 느린 프로그램을 사용 하면 런타임에 형식의 멤버에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="e61d9-122">This is because all data stored in a late-bound variable must be wrapped as type `Object`, and accessing members of the type at run time makes the program slower.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="e61d9-123">예제</span><span class="sxs-lookup"><span data-stu-id="e61d9-123">Examples</span></span>  
 <span data-ttu-id="e61d9-124">형식 유추는 지역 변수를 선언 하지 하는 경우에 발생 한 `As` 절 되 고 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="e61d9-124">Type inference occurs when a local variable is declared without an `As` clause and initialized.</span></span> <span data-ttu-id="e61d9-125">변수의 유형으로 할당 된 초기 값의 형식을 사용 하는 컴파일러입니다.</span><span class="sxs-lookup"><span data-stu-id="e61d9-125">The compiler uses the type of the assigned initial value as the type of the variable.</span></span> <span data-ttu-id="e61d9-126">코드의 다음 줄은 각각 형식의 변수 선언 하는 예를 들어 `String`합니다.</span><span class="sxs-lookup"><span data-stu-id="e61d9-126">For example, each of the following lines of code declares a variable of type `String`.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#2](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_2.vb)]  
  
 <span data-ttu-id="e61d9-127">다음 코드에는 정수의 배열을 만드는 데 두 해당 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e61d9-127">The following code demonstrates two equivalent ways to create an array of integers.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#3](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_3.vb)]  
  
 <span data-ttu-id="e61d9-128">형식 유추를 사용 하 여 루프 제어 변수의 형식을 결정 하는 것이 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e61d9-128">It is convenient to use type inference to determine the type of a loop control variable.</span></span> <span data-ttu-id="e61d9-129">다음 코드에서는 컴파일러에서 유추 하는 `number` 는 `Integer` 때문에 `someNumbers2` 이전 예제에서 정수 배열이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e61d9-129">In the following code, the compiler infers that `number` is an `Integer` because `someNumbers2` from the previous example is an array of integers.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#4](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_4.vb)]  
  
 <span data-ttu-id="e61d9-130">지역 형식 유추에서 사용할 수 있습니다 `Using` 다음 예제에서 보여 주듯이 리소스 이름의 형식을 설정 하는 문입니다.</span><span class="sxs-lookup"><span data-stu-id="e61d9-130">Local type inference can be used in `Using` statements to establish the type of the resource name, as the following example demonstrates.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#7](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_5.vb)]  
  
 <span data-ttu-id="e61d9-131">다음 예제에서 보여 주듯이 변수 형식은 함수, 반환 값에서 유추할 수도 합니다.</span><span class="sxs-lookup"><span data-stu-id="e61d9-131">The type of a variable can also be inferred from the return values of functions, as the following example demonstrates.</span></span> <span data-ttu-id="e61d9-132">둘 다 `pList1` 및 `pList2` 때문에 프로세스의 배열 `Process.GetProcesses` 프로세스의 배열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e61d9-132">Both `pList1` and `pList2` are arrays of processes because `Process.GetProcesses` returns an array of processes.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#5](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_6.vb)]  
  
## <a name="option-infer"></a><span data-ttu-id="e61d9-133">Option Infer</span><span class="sxs-lookup"><span data-stu-id="e61d9-133">Option Infer</span></span>  
 <span data-ttu-id="e61d9-134">`Option Infer` 지역 형식 유추 특정 파일에서 허용 되는지 여부를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e61d9-134">`Option Infer` enables you specify whether local type inference is allowed in a particular file.</span></span> <span data-ttu-id="e61d9-135">사용 하도록 설정 하려면 또는 옵션을 차단 하는 파일의 시작 부분에 다음 문 중 하나를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e61d9-135">To enable or to block the option, type one of the following statements at the start of the file.</span></span>  
  
 `Option Infer On`  
  
 `Option Infer Off`  
  
 <span data-ttu-id="e61d9-136">에 대 한 값을 지정 하지 않으면 `Option Infer` 컴파일러 기본값은 코드에서 `Option Infer On`합니다.</span><span class="sxs-lookup"><span data-stu-id="e61d9-136">If you do not specify a value for `Option Infer` in your code, the compiler default is `Option Infer On`.</span></span> <span data-ttu-id="e61d9-137">업그레이드 된 프로젝트에 대해 [!INCLUDE[vb_orcas_long](~/includes/vb-orcas-long-md.md)] 컴파일러 기본값은 이전 버전에서는 `Option Infer Off`합니다.</span><span class="sxs-lookup"><span data-stu-id="e61d9-137">For projects upgraded from [!INCLUDE[vb_orcas_long](~/includes/vb-orcas-long-md.md)] or earlier, the compiler default is `Option Infer Off`.</span></span>  
  
 <span data-ttu-id="e61d9-138">파일에서 `Option Infer`에 대해 설정된 값이 IDE 또는 명령줄에 설정된 값과 충돌하는 경우에는 파일의 값이 우선적으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e61d9-138">If the value set for `Option Infer` in a file conflicts with the value set in the IDE or on the command line, the value in the file has precedence.</span></span>  
  
 <span data-ttu-id="e61d9-139">자세한 내용은 참조 [Option Infer 문](../../../../visual-basic/language-reference/statements/option-infer-statement.md) 및 [컴파일 페이지, 프로젝트 디자이너 (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)합니다.</span><span class="sxs-lookup"><span data-stu-id="e61d9-139">For more information, see [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md) and [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e61d9-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e61d9-140">See Also</span></span>  
 [<span data-ttu-id="e61d9-141">익명 형식</span><span class="sxs-lookup"><span data-stu-id="e61d9-141">Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 [<span data-ttu-id="e61d9-142">초기 바인딩 및 런타임에 바인딩</span><span class="sxs-lookup"><span data-stu-id="e61d9-142">Early and Late Binding</span></span>](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)  
 [<span data-ttu-id="e61d9-143">For Each...Next 문</span><span class="sxs-lookup"><span data-stu-id="e61d9-143">For Each...Next Statement</span></span>](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)  
 [<span data-ttu-id="e61d9-144">For...Next 문</span><span class="sxs-lookup"><span data-stu-id="e61d9-144">For...Next Statement</span></span>](../../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [<span data-ttu-id="e61d9-145">Option Infer 문</span><span class="sxs-lookup"><span data-stu-id="e61d9-145">Option Infer Statement</span></span>](../../../../visual-basic/language-reference/statements/option-infer-statement.md)  
 [<span data-ttu-id="e61d9-146">/optioninfer</span><span class="sxs-lookup"><span data-stu-id="e61d9-146">/optioninfer</span></span>](../../../../visual-basic/reference/command-line-compiler/optioninfer.md)  
 [<span data-ttu-id="e61d9-147">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="e61d9-147">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
