---
title: 프로시저 매개 변수 및 인수(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], argument lists
- values [Visual Basic], passing to procedures
- arguments [Visual Basic], passing
- procedures [Visual Basic], parameters
- Visual Basic code, argument lists
- Visual Basic code, procedures
- parameters [Visual Basic], Visual Basic procedures
- parameters [Visual Basic], lists
- arguments [Visual Basic], Visual Basic procedures
- arguments [Visual Basic], procedures
- parameter lists [Visual Basic]
- Visual Basic code, parameter lists
- argument lists [Visual Basic]
- procedures [Visual Basic], parameter lists
ms.assetid: ff275aff-aa13-40df-bd4c-63486db8c1e9
ms.openlocfilehash: b0ab186945b456d7fb4dde3f52724b08a99e2827
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33652502"
---
# <a name="procedure-parameters-and-arguments-visual-basic"></a><span data-ttu-id="15284-102">프로시저 매개 변수 및 인수(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="15284-102">Procedure Parameters and Arguments (Visual Basic)</span></span>
<span data-ttu-id="15284-103">대부분의 경우에서 프로시저는 호출 된 있는 상황에 대 한 몇 가지 정보가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="15284-103">In most cases, a procedure needs some information about the circumstances in which it has been called.</span></span> <span data-ttu-id="15284-104">반복 또는 공유 작업을 수행 하는 프로시저는 각 호출에 대 한 다른 정보를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="15284-104">A procedure that performs repeated or shared tasks uses different information for each call.</span></span> <span data-ttu-id="15284-105">이 정보는 변수, 상수, 및 호출 하면 프로시저에 전달 하는 식으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="15284-105">This information consists of variables, constants, and expressions that you pass to the procedure when you call it.</span></span>  
  
 <span data-ttu-id="15284-106">A *매개 변수* 프로시저 프로시저를 호출할 때 제공 해야 하는 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="15284-106">A *parameter* represents a value that the procedure expects you to supply when you call it.</span></span> <span data-ttu-id="15284-107">프로시저의 선언 매개 변수를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="15284-107">The procedure's declaration defines its parameters.</span></span>  
  
 <span data-ttu-id="15284-108">매개 변수 없이 매개 변수 하나 또는 여러 개를 사용 하 여 프로시저를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15284-108">You can define a procedure with no parameters, one parameter, or more than one.</span></span> <span data-ttu-id="15284-109">매개 변수를 지정 하는 프로시저 정의의 일부 라고는 *매개 변수 목록*합니다.</span><span class="sxs-lookup"><span data-stu-id="15284-109">The part of the procedure definition that specifies the parameters is called the *parameter list*.</span></span>  
  
 <span data-ttu-id="15284-110">*인수* 는 프로시저를 호출할 때 프로시저 매개 변수에 제공 하는 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="15284-110">An *argument* represents the value you supply to a procedure parameter when you call the procedure.</span></span> <span data-ttu-id="15284-111">호출 하는 코드는 프로시저를 호출할 때 인수를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="15284-111">The calling code supplies the arguments when it calls the procedure.</span></span> <span data-ttu-id="15284-112">인수를 지정 하는 프로시저 호출의 일부 라고는 *인수 목록*합니다.</span><span class="sxs-lookup"><span data-stu-id="15284-112">The part of the procedure call that specifies the arguments is called the *argument list*.</span></span>  
  
 <span data-ttu-id="15284-113">다음 그림은 프로시저를 호출 하는 코드를 보여 줍니다. `safeSquareRoot` 서로 다른 두 위치에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="15284-113">The following illustration shows code calling the procedure `safeSquareRoot` from two different places.</span></span> <span data-ttu-id="15284-114">변수 값을 전달 하는 첫 번째 호출 `x` (4.0) 매개 변수에 `number`, 및 반환 값에 `root` (2.0)를 변수에 할당할 `y`합니다.</span><span class="sxs-lookup"><span data-stu-id="15284-114">The first call passes the value of the variable `x` (4.0) to the parameter `number`, and the return value in `root` (2.0) is assigned to the variable `y`.</span></span> <span data-ttu-id="15284-115">두 번째 호출 하는 리터럴 값 9.0 전달 `number`, 반환 값 (3.0) 변수에 할당 `z`합니다.</span><span class="sxs-lookup"><span data-stu-id="15284-115">The second call passes the literal value 9.0 to `number`, and assigns the return value (3.0) to variable `z`.</span></span>  
  
 <span data-ttu-id="15284-116">![매개 변수에 인수를 전달 하는 그래픽 다이어그램](./media/parametersargue.gif "ParametersArgue")</span><span class="sxs-lookup"><span data-stu-id="15284-116">![Graphic diagram of passing argument to parameter](./media/parametersargue.gif "ParametersArgue")</span></span>  
<span data-ttu-id="15284-117">매개 변수에 인수를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="15284-117">Passing an argument to a parameter</span></span>  
  
 <span data-ttu-id="15284-118">자세한 내용은 참조 [차이점 간의 매개 변수 및 인수](./differences-between-parameters-and-arguments.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="15284-118">For more information, see [Differences Between Parameters and Arguments](./differences-between-parameters-and-arguments.md).</span></span>  
  
## <a name="parameter-data-type"></a><span data-ttu-id="15284-119">매개 변수 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="15284-119">Parameter Data Type</span></span>  
 <span data-ttu-id="15284-120">매개 변수에 대 한 데이터 형식을 사용 하 여 정의 된 `As` 선언에는 절.</span><span class="sxs-lookup"><span data-stu-id="15284-120">You define a data type for a parameter by using the `As` clause in its declaration.</span></span> <span data-ttu-id="15284-121">예를 들어 다음 함수는 문자열과 정수를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="15284-121">For example, the following function accepts a string and an integer.</span></span>  
  
 [!code-vb[VbVbcnProcedures#32](./codesnippet/VisualBasic/procedure-parameters-and-arguments_1.vb)]  
  
 <span data-ttu-id="15284-122">형식 검사 스위치 하는 경우 ([Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md))은 `Off,` 는 `As` 제외 하 고 모든 매개 변수에서 사용 해야 매개 변수 하나를 사용 하면 절은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="15284-122">If the type checking switch ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) is `Off,` the `As` clause is optional, except that if any one parameter uses it, all parameters must use it.</span></span> <span data-ttu-id="15284-123">형식 검사를 통과 하는 경우 `On`, `As` 절이 모든 프로시저 매개 변수에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="15284-123">If type checking is `On`, the `As` clause is required for all procedure parameters.</span></span>  
  
 <span data-ttu-id="15284-124">호출 코드에서는 해당 매개 변수를와 다른 데이터 형식과 같은 인수를 제공 하는 경우 `Byte` 에 `String` 매개 변수를 다음 중 하나를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="15284-124">If the calling code expects to supply an argument with a data type different from that of its corresponding parameter, such as `Byte` to a `String` parameter, it must do one of the following:</span></span>  
  
-   <span data-ttu-id="15284-125">인수만 지정; 매개 변수 데이터 형식으로 확장 된 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="15284-125">Supply only arguments with data types that widen to the parameter data type;</span></span>  
  
-   <span data-ttu-id="15284-126">설정 `Option Strict Off` 암시적 축소 변환을; 수 있도록 또는</span><span class="sxs-lookup"><span data-stu-id="15284-126">Set `Option Strict Off` to allow implicit narrowing conversions; or</span></span>  
  
-   <span data-ttu-id="15284-127">변환 키워드를 사용 하 여 데이터 형식을 명시적으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="15284-127">Use a conversion keyword to explicitly convert the data type.</span></span>  
  
### <a name="type-parameters"></a><span data-ttu-id="15284-128">형식 매개 변수</span><span class="sxs-lookup"><span data-stu-id="15284-128">Type Parameters</span></span>  
 <span data-ttu-id="15284-129">A *제네릭 프로시저* 하나 이상의 정의 *형식 매개 변수* 일반 매개 변수 외에도 합니다.</span><span class="sxs-lookup"><span data-stu-id="15284-129">A *generic procedure* also defines one or more *type parameters* in addition to its normal parameters.</span></span> <span data-ttu-id="15284-130">제네릭 프로시저가 호출 코드를를 데이터 형식을 각 개별 호출의 요구 사항에 맞게 제대로 조정할 수 있도록는 프로시저를 호출할 때마다 다른 데이터 형식을 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15284-130">A generic procedure allows the calling code to pass different data types each time it calls the procedure, so it can tailor the data types to the requirements of each individual call.</span></span> <span data-ttu-id="15284-131">[Generic Procedures in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="15284-131">See [Generic Procedures in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15284-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="15284-132">See Also</span></span>  
 [<span data-ttu-id="15284-133">절차</span><span class="sxs-lookup"><span data-stu-id="15284-133">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="15284-134">Sub 프로시저</span><span class="sxs-lookup"><span data-stu-id="15284-134">Sub Procedures</span></span>](./sub-procedures.md)  
 [<span data-ttu-id="15284-135">Function 프로시저</span><span class="sxs-lookup"><span data-stu-id="15284-135">Function Procedures</span></span>](./function-procedures.md)  
 [<span data-ttu-id="15284-136">속성 프로시저</span><span class="sxs-lookup"><span data-stu-id="15284-136">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="15284-137">연산자 프로시저</span><span class="sxs-lookup"><span data-stu-id="15284-137">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="15284-138">방법: 프로시저의 매개 변수 정의</span><span class="sxs-lookup"><span data-stu-id="15284-138">How to: Define a Parameter for a Procedure</span></span>](./how-to-define-a-parameter-for-a-procedure.md)  
 [<span data-ttu-id="15284-139">방법: 프로시저에 인수 전달</span><span class="sxs-lookup"><span data-stu-id="15284-139">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)  
 [<span data-ttu-id="15284-140">값 또는 참조로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="15284-140">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="15284-141">프로시저 오버로딩</span><span class="sxs-lookup"><span data-stu-id="15284-141">Procedure Overloading</span></span>](./procedure-overloading.md)  
 [<span data-ttu-id="15284-142">Visual Basic의 형식 변환</span><span class="sxs-lookup"><span data-stu-id="15284-142">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
