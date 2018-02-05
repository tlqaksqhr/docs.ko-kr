---
title: "위치 및 이름으로 인수 전달(Visual Basic)"
ms.custom: 
ms.date: 02/01/2018
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- arguments [Visual Basic], passing by name
- procedures [Visual Basic], arguments
- := passing arguments
- procedure arguments
- Visual Basic code, procedures
- named arguments [Visual Basic], passing arguments
- arguments [Visual Basic], passing by position
- Function procedures [Visual Basic], passing arguments
- named parameters [Visual Basic], passing arguments
- named arguments
- passing parameters [Visual Basic], named parameter arguments
- passing parameters [Visual Basic], by position
- procedures [Visual Basic], calling
- named parameters
- Sub procedures [Visual Basic], passing arguments
- argument passing
- passing parameters [Visual Basic], by name
- argument passing [Visual Basic], by position
- arguments [Visual Basic], listing by name
ms.assetid: 1ad7358f-1da9-48da-a95b-f3c7ed41eff3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 13f5e5a8da6a899d4920a25b250ca88b2a21f559
ms.sourcegitcommit: 099aa20d9b6450d1b7452d782a55771a6ad8ff35
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2018
---
# <a name="passing-arguments-by-position-and-by-name-visual-basic"></a><span data-ttu-id="3dbed-102">위치 및 이름으로 인수 전달(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3dbed-102">Passing Arguments by Position and by Name (Visual Basic)</span></span>
<span data-ttu-id="3dbed-103">호출 하는 경우는 `Sub` 또는 `Function` 프로시저 인수를 전달할 수 있습니다 *위치별* -프로시저의 정의에 나타나는 순서로-하거나 전달할 수 있습니다 *이름별*, 하지 않고 위치에 관계를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3dbed-103">When you call a `Sub` or `Function` procedure, you can pass arguments *by position* — in the order in which they appear in the procedure's definition — or you can pass them *by name*, without regard to position.</span></span>  
  
 <span data-ttu-id="3dbed-104">인수 선언 된 이름에 콜론과 등호가 뒤에 지정할 이름으로 인수를 전달 하는 경우 (`:=`), 인수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="3dbed-104">When you pass an argument by name, you specify the argument's declared name followed by a colon and an equal sign (`:=`), followed by the argument value.</span></span> <span data-ttu-id="3dbed-105">순서에 관계 없이 명명 된 인수를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3dbed-105">You can supply named arguments in any order.</span></span>  
  
 <span data-ttu-id="3dbed-106">예를 들어, 다음 `Sub` 프로시저는 세 개의 인수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3dbed-106">For example, the following `Sub` procedure takes three arguments:</span></span>  
  
 [!code-vb[SampleProcedure](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#1)]  
  
 <span data-ttu-id="3dbed-107">이 프로시저를 호출할 때 위치, 이름, 또는 둘 모두를 사용 하 여 인수를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3dbed-107">When you call this procedure, you can supply the arguments by position, by name, or by using a mixture of both.</span></span>  
  
## <a name="passing-arguments-by-position"></a><span data-ttu-id="3dbed-108">위치로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="3dbed-108">Passing Arguments by Position</span></span>  
 <span data-ttu-id="3dbed-109">호출할 수 있습니다는 `Display` 메서드 인수를 위치에 의해 전달 하 고 다음 예제와 같이 쉼표로 구분 된:</span><span class="sxs-lookup"><span data-stu-id="3dbed-109">You can call the `Display` method with its arguments passed by position and delimited by commas, as shown in the following example:</span></span>  
  
[!code-vb[ByPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#2)] 
  
 <span data-ttu-id="3dbed-110">위치 인수 목록에서 선택적 인수를 생략 하면 쉼표로 대신을 보유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3dbed-110">If you omit an optional argument in a positional argument list, you must hold its place with a comma.</span></span> <span data-ttu-id="3dbed-111">다음 예제에서는 `Display` 메서드 없이 `age` 인수:</span><span class="sxs-lookup"><span data-stu-id="3dbed-111">The following example calls the `Display` method without the `age` argument:</span></span>  
  
[!code-vb[ByPositionWithOptionalArgument](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#3)] 
  
## <a name="passing-arguments-by-name"></a><span data-ttu-id="3dbed-112">이름으로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="3dbed-112">Passing Arguments by Name</span></span>  
 <span data-ttu-id="3dbed-113">호출할 수 있습니다 `Display` 이름으로 전달 된 인수, 또한 쉼표로 구분한 다음 예제와 같이:</span><span class="sxs-lookup"><span data-stu-id="3dbed-113">Alternatively, you can call `Display` with the arguments passed by name, also delimited by commas, as shown in the following example:</span></span>  
  
[!code-vb[ByName](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#4)] 

 <span data-ttu-id="3dbed-114">이러한 방식으로 이름으로 인수 전달 선택적 인수를 여러 개 있는 프로시저를 호출 하는 경우 특히 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3dbed-114">Passing arguments by name in this way is especially useful when you call a procedure that has more than one optional argument.</span></span> <span data-ttu-id="3dbed-115">이름으로 인수를 제공 하는 경우 연속 쉼표를 사용 하 여 생략 된 위치 인수를 나타내기 위해 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3dbed-115">If you supply arguments by name, you do not have to use consecutive commas to denote missing positional arguments.</span></span> <span data-ttu-id="3dbed-116">이름으로 인수 전달 또한 쉽게 전달 하는 고 생략 되는 기능과 인수를 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3dbed-116">Passing arguments by name also makes it easier to keep track of which arguments you are passing and which ones you are omitting.</span></span>  
  
## <a name="mixing-arguments-by-position-and-by-name"></a><span data-ttu-id="3dbed-117">이름 및 위치 인수 혼합</span><span class="sxs-lookup"><span data-stu-id="3dbed-117">Mixing Arguments by Position and by Name</span></span>  

<span data-ttu-id="3dbed-118">다음 예제와 같이 위치 하 고 하나의 프로시저 호출에서 이름으로 인수를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3dbed-118">You can supply arguments both by position and by name in a single procedure call, as shown in the following example:</span></span>  
  
[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#5)] 
  
 <span data-ttu-id="3dbed-119">앞의 예에서 쉼표로 생략 된 위치를 보유 하는 데 필요한 `age` 인수를 이후 `birth` 이름으로 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3dbed-119">In the preceding example, no extra comma is necessary to hold the place of the omitted `age` argument, since `birth` is passed by name.</span></span>  
  
<span data-ttu-id="3dbed-120">15.5 이전 버전의 Visual Basic, 위치 및 이름, 위치 인수를 사용 하 여 인수를 제공 하는 경우 모든 먼저와 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3dbed-120">In versions of Visual Basic before 15.5, when you supply arguments by a mixture of position and name, the positional arguments must all come first.</span></span> <span data-ttu-id="3dbed-121">이름으로 인수를 지정할 때는 되 면 나머지 인수는 모두 모든 전달 되어야 합니다 이름별으로.</span><span class="sxs-lookup"><span data-stu-id="3dbed-121">Once you supply an argument by name, any remaining arguments must all be passed by name.</span></span>  <span data-ttu-id="3dbed-122">다음을 호출 하는 예를 들어는 `Display` 메서드는 컴파일러 오류 표시 [BC30241: 명명 된 인수를 예상](../../../misc/bc30241.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3dbed-122">For example, the following call to the `Display` method displays compiler error [BC30241: Named argument expected](../../../misc/bc30241.md).</span></span>

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#6)] 

<span data-ttu-id="3dbed-123">Visual Basic 15.5 부터는 위치 인수를 따르면 명명 된 인수 끝 위치 인수 올바른 위치에 있는 경우 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3dbed-123">Starting with Visual Basic 15.5, positional arguments can follow named arguments if the ending positional arguments are in the correct position.</span></span> <span data-ttu-id="3dbed-124">Visual Basic 15.5에 대 한 이전 호출에서 컴파일된 경우는 `Display` 메서드가 성공적으로 컴파일되고 컴파일러 오류가 더 이상 [BC30241](../../../misc/bc30241.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3dbed-124">If compiled under Visual Basic 15.5, the previous call to the `Display` method compiles successfully and no longer generates compiler error [BC30241](../../../misc/bc30241.md).</span></span>  

<span data-ttu-id="3dbed-125">순서에 관계 없이 명명 된 인수와 위치와 일치 하 고 혼합이 기능을 명명된 된 인수를 사용 하 여 코드를 더 쉽게 읽을 수 있도록 하려는 경우 특히 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3dbed-125">This ability to mix and match named and positional arguments in any order is particularly useful when you want to use a named argument to make your code more readable.</span></span> <span data-ttu-id="3dbed-126">예를 들어, 다음 `Person` 클래스 생성자를 사용 하려면 형식의 두 인수 `Person`, 둘 다 수 `Nothing`합니다.</span><span class="sxs-lookup"><span data-stu-id="3dbed-126">For example, the following `Person` class constructor requires two arguments of type `Person`, both of which can be `Nothing`.</span></span> 

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#7)] 

<span data-ttu-id="3dbed-127">코드의 의도 확인 하는 데 도움이 될 때의 선택을 취소 하는 혼합 된 명명 된 인수와 위치 인수를 사용 하 여의 값은 `father` 및 `mother` 인수는 `Nothing`:</span><span class="sxs-lookup"><span data-stu-id="3dbed-127">Using mixed named and positional arguments helps to make the intent of the code clear when the value of the `father` and `mother` arguments is `Nothing`:</span></span>

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#8)] 

<span data-ttu-id="3dbed-128">명명 된 인수 위치 인수를 수행 하려면 Visual Basic 프로젝트에 다음 요소를 추가 해야 (\*.vbproj) 파일:</span><span class="sxs-lookup"><span data-stu-id="3dbed-128">To follow positional arguments with named arguments, you must add the following element to your Visual Basic project (\*.vbproj) file:</span></span>

```xml
<PropertyGroup>
  <LangVersion>15.5</LangVersion>
</PropertyGroup>
```

## <a name="restrictions-on-supplying-arguments-by-name"></a><span data-ttu-id="3dbed-129">이름으로 인수에 대 한 제한</span><span class="sxs-lookup"><span data-stu-id="3dbed-129">Restrictions on Supplying Arguments by Name</span></span>  

<span data-ttu-id="3dbed-130">필수 인수를 입력 하지 못하도록 하려면 이름으로 인수를 전달할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3dbed-130">You cannot pass arguments by name to avoid entering required arguments.</span></span> <span data-ttu-id="3dbed-131">선택적 인수에만 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3dbed-131">You can omit only the optional arguments.</span></span>  
  
<span data-ttu-id="3dbed-132">매개 변수 배열을 이름으로 전달할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3dbed-132">You cannot pass a parameter array by name.</span></span> <span data-ttu-id="3dbed-133">즉는 프로시저를 호출할 때 불특정 개수의 매개 변수 배열에 대 한 쉼표로 구분 된 인수를 제공 하 고 컴파일러가 단일 이름으로 둘 이상의 인수를 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3dbed-133">This is because when you call the procedure, you supply an indefinite number of comma-separated arguments for the parameter array, and the compiler cannot associate more than one argument with a single name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3dbed-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3dbed-134">See Also</span></span>  
 [<span data-ttu-id="3dbed-135">절차</span><span class="sxs-lookup"><span data-stu-id="3dbed-135">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="3dbed-136">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="3dbed-136">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="3dbed-137">방법: 프로시저에 인수 전달</span><span class="sxs-lookup"><span data-stu-id="3dbed-137">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)  
 [<span data-ttu-id="3dbed-138">값 또는 참조로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="3dbed-138">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="3dbed-139">선택적 매개 변수</span><span class="sxs-lookup"><span data-stu-id="3dbed-139">Optional Parameters</span></span>](./optional-parameters.md)  
 [<span data-ttu-id="3dbed-140">매개 변수 배열</span><span class="sxs-lookup"><span data-stu-id="3dbed-140">Parameter Arrays</span></span>](./parameter-arrays.md)  
 [<span data-ttu-id="3dbed-141">선택 사항</span><span class="sxs-lookup"><span data-stu-id="3dbed-141">Optional</span></span>](../../../../visual-basic/language-reference/modifiers/optional.md)  
 [<span data-ttu-id="3dbed-142">ParamArray</span><span class="sxs-lookup"><span data-stu-id="3dbed-142">ParamArray</span></span>](../../../../visual-basic/language-reference/modifiers/paramarray.md)
