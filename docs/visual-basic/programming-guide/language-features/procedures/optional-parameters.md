---
title: 선택적 매개 변수(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- parameters [Visual Basic], optional
- Visual Basic code, procedures
- procedures [Visual Basic], optional arguments
- optional arguments
- named arguments [Visual Basic], and optional arguments
- optional parameters
- Optional keyword [Visual Basic], optional arguments
- arguments [Visual Basic], optional
- optional arguments [Visual Basic], and named arguments
ms.assetid: 398d2845-1069-4e94-b934-a73b545c8b87
ms.openlocfilehash: a438455668310769c5267a6d42a2e694bb7b01dc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33651611"
---
# <a name="optional-parameters-visual-basic"></a><span data-ttu-id="906ac-102">선택적 매개 변수(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="906ac-102">Optional Parameters (Visual Basic)</span></span>
<span data-ttu-id="906ac-103">프로시저 매개 변수를 선택적 요소로 지정하여 프로시저를 호출할 때 인수를 지정하지 않아도 되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="906ac-103">You can specify that a procedure parameter is optional and no argument has to be supplied for it when the procedure is called.</span></span> <span data-ttu-id="906ac-104">*선택적 매개 변수* 으로 표시 됩니다는 `Optional` 프로시저 정의에 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="906ac-104">*Optional parameters* are indicated by the `Optional` keyword in the procedure definition.</span></span> <span data-ttu-id="906ac-105">이 때 적용되는 규칙은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="906ac-105">The following rules apply:</span></span>  
  
-   <span data-ttu-id="906ac-106">프로시저 정의의 모든 선택적 매개 변수에는 기본값을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="906ac-106">Every optional parameter in the procedure definition must specify a default value.</span></span>  
  
-   <span data-ttu-id="906ac-107">선택적 매개 변수의 기본값은 상수 식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="906ac-107">The default value for an optional parameter must be a constant expression.</span></span>  
  
-   <span data-ttu-id="906ac-108">프로시저 정의에서 선택적 매개 변수 뒤에 오는 매개 변수도 모두 선택적 요소여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="906ac-108">Every parameter following an optional parameter in the procedure definition must also be optional.</span></span>  
  
 <span data-ttu-id="906ac-109">다음 구문은 선택적 매개 변수를 사용하여 프로시저를 선언하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="906ac-109">The following syntax shows a procedure declaration with an optional parameter:</span></span>  
  
```vb  
Sub name(ByVal parameter1 As datatype1, Optional ByVal parameter2 As datatype2 = defaultvalue)  
```  
  
## <a name="calling-procedures-with-optional-parameters"></a><span data-ttu-id="906ac-110">선택적 매개 변수가 있는 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="906ac-110">Calling Procedures with Optional Parameters</span></span>  
 <span data-ttu-id="906ac-111">선택적 매개 변수가 있는 프로시저를 호출하는 경우 해당 인수를 지정할지 여부를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="906ac-111">When you call a procedure with an optional parameter, you can choose whether to supply the argument.</span></span> <span data-ttu-id="906ac-112">선택하지 않으면 선택적 매개 변수에 대해 선언된 기본값이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="906ac-112">If you do not, the procedure uses the default value declared for that parameter.</span></span>  
  
 <span data-ttu-id="906ac-113">인수 목록에서 하나 이상의 선택적 인수를 생략하는 경우 그 자리에 쉼표를 사용하여 생략된 위치를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="906ac-113">When you omit one or more optional arguments in the argument list, you use successive commas to mark their positions.</span></span> <span data-ttu-id="906ac-114">다음 호출 샘플에서는 첫 번째와 네 번째 인수가 제공되고 두 번째와 세 번째 인수는 제공되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="906ac-114">The following example call supplies the first and fourth arguments but not the second or third:</span></span>  
  
```vb  
Sub name(argument 1, , , argument 4)  
```  
  
 <span data-ttu-id="906ac-115">다음 예제에서는 `MsgBox` 함수를 여러 번 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="906ac-115">The following example makes several calls to the `MsgBox` function.</span></span> <span data-ttu-id="906ac-116">`MsgBox`에는 필수적 매개 변수 하나와 선택적 매개 변수 두 개가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="906ac-116">`MsgBox` has one required parameter and two optional parameters.</span></span>  
  
 <span data-ttu-id="906ac-117">`MsgBox`에 대한 첫 번째 호출에서 `MsgBox`에서 정의하는 순서대로 세 개의 인수를 모두 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="906ac-117">The first call to `MsgBox` supplies all three arguments in the order that `MsgBox` defines them.</span></span> <span data-ttu-id="906ac-118">두 번째 호출에서는 필수적 인수만 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="906ac-118">The second call supplies only the required argument.</span></span> <span data-ttu-id="906ac-119">세 번째와 네 번째 호출에서는 첫 번째 인수와 세 번째 인수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="906ac-119">The third and fourth calls supply the first and third arguments.</span></span> <span data-ttu-id="906ac-120">세 번째 호출에서는 위치로 인수를 지정하고, 네 번째 호출에서는 이름으로 인수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="906ac-120">The third call does this by position, and the fourth call does it by name.</span></span>  
  
 [!code-vb[VbVbcnProcedures#47](./codesnippet/VisualBasic/optional-parameters_1.vb)]  
  
## <a name="determining-whether-an-optional-argument-is-present"></a><span data-ttu-id="906ac-121">선택적 인수의 존재 여부 확인</span><span class="sxs-lookup"><span data-stu-id="906ac-121">Determining Whether an Optional Argument Is Present</span></span>  
 <span data-ttu-id="906ac-122">프로시저는 지정된 인수가 생략되었는지 또는 호출 코드가 명시적으로 기본값을 제공했는지 여부를 런타임에서 감지할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="906ac-122">A procedure cannot detect at run time whether a given argument has been omitted or the calling code has explicitly supplied the default value.</span></span> <span data-ttu-id="906ac-123">이를 알아보려면 특이한 값을 기본값으로 설정하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="906ac-123">If you need to make this distinction, you can set an unlikely value as the default.</span></span> <span data-ttu-id="906ac-124">다음 절차는 선택적 매개 변수를 정의 `office`, 해당 기본값에 대 한 테스트 및 `QJZ`, 호출에서 생략 되었는지 확인 하려면:</span><span class="sxs-lookup"><span data-stu-id="906ac-124">The following procedure defines the optional parameter `office`, and tests for its default value, `QJZ`, to see if it has been omitted in the call:</span></span>  
  
 [!code-vb[VbVbcnProcedures#46](./codesnippet/VisualBasic/optional-parameters_2.vb)]  
  
 <span data-ttu-id="906ac-125">선택적 매개 변수가 `String`과 같은 참조 형식일 경우 `Nothing`이 그 인수에 예상된 값이 아니면 이 값을 기본값으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="906ac-125">If the optional parameter is a reference type such as a `String`, you can use `Nothing` as the default value, provided this is not an expected value for the argument.</span></span>  
  
## <a name="optional-parameters-and-overloading"></a><span data-ttu-id="906ac-126">선택적 매개 변수 및 오버로드</span><span class="sxs-lookup"><span data-stu-id="906ac-126">Optional Parameters and Overloading</span></span>  
 <span data-ttu-id="906ac-127">선택적 매개 변수가 있는 프로시저를 정의하는 또 다른 방법은 오버로드를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="906ac-127">Another way to define a procedure with optional parameters is to use overloading.</span></span> <span data-ttu-id="906ac-128">선택적 매개 변수가 하나이면 프로시저의 오버로드된 두 버전을 매개 변수를 사용하는 버전과 매개 변수를 사용하지 않는 버전으로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="906ac-128">If you have one optional parameter, you can define two overloaded versions of the procedure, one accepting the parameter and one without it.</span></span> <span data-ttu-id="906ac-129">이러한 방식은 선택적 매개 변수의 개수가 증가할수록 더욱 복잡해지지만</span><span class="sxs-lookup"><span data-stu-id="906ac-129">This approach becomes more complicated as the number of optional parameters increases.</span></span> <span data-ttu-id="906ac-130">호출 프로그램이 각 선택적 인수를 제공했는지 여부를 확실히 알 수 있다는 장점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="906ac-130">However, its advantage is that you can be absolutely sure whether the calling program supplied each optional argument.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="906ac-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="906ac-131">See Also</span></span>  
 [<span data-ttu-id="906ac-132">절차</span><span class="sxs-lookup"><span data-stu-id="906ac-132">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="906ac-133">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="906ac-133">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="906ac-134">값 또는 참조로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="906ac-134">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="906ac-135">위치 및 이름으로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="906ac-135">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)  
 [<span data-ttu-id="906ac-136">매개 변수 배열</span><span class="sxs-lookup"><span data-stu-id="906ac-136">Parameter Arrays</span></span>](./parameter-arrays.md)  
 [<span data-ttu-id="906ac-137">프로시저 오버로딩</span><span class="sxs-lookup"><span data-stu-id="906ac-137">Procedure Overloading</span></span>](./procedure-overloading.md)  
 [<span data-ttu-id="906ac-138">선택 사항</span><span class="sxs-lookup"><span data-stu-id="906ac-138">Optional</span></span>](../../../../visual-basic/language-reference/modifiers/optional.md)  
 [<span data-ttu-id="906ac-139">ParamArray</span><span class="sxs-lookup"><span data-stu-id="906ac-139">ParamArray</span></span>](../../../../visual-basic/language-reference/modifiers/paramarray.md)
