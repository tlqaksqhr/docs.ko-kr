---
title: "위치 및 이름으로 인수 전달(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
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
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 164f69fcf23049441a0acbe05058c792d5363a03
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="passing-arguments-by-position-and-by-name-visual-basic"></a><span data-ttu-id="d777f-102">위치 및 이름으로 인수 전달(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d777f-102">Passing Arguments by Position and by Name (Visual Basic)</span></span>
<span data-ttu-id="d777f-103">호출 하는 경우는 `Sub` 또는 `Function` 프로시저 인수를 전달할 수 있습니다 *위치별* -프로시저의 정의에 나타나는 순서로-하거나 전달할 수 있습니다 *이름별*, 하지 않고 위치에 관계를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d777f-103">When you call a `Sub` or `Function` procedure, you can pass arguments *by position* — in the order in which they appear in the procedure's definition — or you can pass them *by name*, without regard to position.</span></span>  
  
 <span data-ttu-id="d777f-104">인수 선언 된 이름에 콜론과 등호가 뒤에 지정할 이름으로 인수를 전달 하는 경우 (`:=`), 인수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d777f-104">When you pass an argument by name, you specify the argument's declared name followed by a colon and an equal sign (`:=`), followed by the argument value.</span></span> <span data-ttu-id="d777f-105">순서에 관계 없이 명명 된 인수를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d777f-105">You can supply named arguments in any order.</span></span>  
  
 <span data-ttu-id="d777f-106">예를 들어, 다음 `Sub` 프로시저는 세 개의 인수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d777f-106">For example, the following `Sub` procedure takes three arguments:</span></span>  
  
 [!code-vb[VbVbcnProcedures#41](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_1.vb)]  
  
 <span data-ttu-id="d777f-107">이 프로시저를 호출할 때 위치, 이름, 또는 둘 모두를 사용 하 여 인수를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d777f-107">When you call this procedure, you can supply the arguments by position, by name, or by using a mixture of both.</span></span>  
  
## <a name="passing-arguments-by-position"></a><span data-ttu-id="d777f-108">위치로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="d777f-108">Passing Arguments by Position</span></span>  
 <span data-ttu-id="d777f-109">프로시저를 호출할 수 `studentInfo` 위치로 전달 된 다음 예에서 같이 쉼표로 구분 된 인수:</span><span class="sxs-lookup"><span data-stu-id="d777f-109">You can call the procedure `studentInfo` with its arguments passed by position and delimited by commas, as shown in the following example:</span></span>  
  
 [!code-vb[VbVbcnProcedures#42](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_2.vb)]  
  
 <span data-ttu-id="d777f-110">위치 인수 목록에서 선택적 인수를 생략 하면 쉼표로 대신을 보유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d777f-110">If you omit an optional argument in a positional argument list, you must hold its place with a comma.</span></span> <span data-ttu-id="d777f-111">다음 예제에서는 `studentInfo` 없이 `age` 인수:</span><span class="sxs-lookup"><span data-stu-id="d777f-111">The following example calls `studentInfo` without the `age` argument:</span></span>  
  
 [!code-vb[VbVbcnProcedures#43](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_3.vb)]  
  
## <a name="passing-arguments-by-name"></a><span data-ttu-id="d777f-112">이름으로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="d777f-112">Passing Arguments by Name</span></span>  
 <span data-ttu-id="d777f-113">호출할 수 있습니다 `studentInfo` 이름으로 전달 된 인수, 또한 쉼표로 구분한 다음 예제와 같이:</span><span class="sxs-lookup"><span data-stu-id="d777f-113">Alternatively, you can call `studentInfo` with the arguments passed by name, also delimited by commas, as shown in the following example:</span></span>  
  
 [!code-vb[VbVbcnProcedures#44](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_4.vb)]  
  
## <a name="mixing-arguments-by-position-and-by-name"></a><span data-ttu-id="d777f-114">이름 및 위치 인수 혼합</span><span class="sxs-lookup"><span data-stu-id="d777f-114">Mixing Arguments by Position and by Name</span></span>  
 <span data-ttu-id="d777f-115">다음 예제와 같이 위치 하 고 하나의 프로시저 호출에서 이름으로 인수를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d777f-115">You can supply arguments both by position and by name in a single procedure call, as shown in the following example:</span></span>  
  
 [!code-vb[VbVbcnProcedures#45](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_5.vb)]  
  
 <span data-ttu-id="d777f-116">앞의 예에서 쉼표로 생략 된 위치를 보유 하는 데 필요한 `age` 인수를 이후 `birth` 이름으로 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d777f-116">In the preceding example, no extra comma is necessary to hold the place of the omitted `age` argument, since `birth` is passed by name.</span></span>  
  
 <span data-ttu-id="d777f-117">위치 및 이름, 위치 인수를 사용 하 여 인수를 제공 하는 경우 모든 먼저와 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d777f-117">When you supply arguments by a mixture of position and name, the positional arguments must all come first.</span></span> <span data-ttu-id="d777f-118">이름으로 인수를 지정할 때는 되 면 나머지 인수 모두 이름별 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d777f-118">Once you supply an argument by name, the remaining arguments must all be by name.</span></span>  
  
## <a name="supplying-optional-arguments-by-name"></a><span data-ttu-id="d777f-119">이름으로 선택적 인수를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d777f-119">Supplying Optional Arguments by Name</span></span>  
 <span data-ttu-id="d777f-120">이름으로 인수 전달 선택적 인수를 여러 개 있는 프로시저를 호출 하는 경우 특히 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d777f-120">Passing arguments by name is especially useful when you call a procedure that has more than one optional argument.</span></span> <span data-ttu-id="d777f-121">이름으로 인수를 제공 하는 경우 연속 쉼표를 사용 하 여 생략 된 위치 인수를 나타내기 위해 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d777f-121">If you supply arguments by name, you do not have to use consecutive commas to denote missing positional arguments.</span></span> <span data-ttu-id="d777f-122">이름으로 인수 전달 또한 쉽게 전달 하는 고 생략 되는 기능과 인수를 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d777f-122">Passing arguments by name also makes it easier to keep track of which arguments you are passing and which ones you are omitting.</span></span>  
  
## <a name="restrictions-on-supplying-arguments-by-name"></a><span data-ttu-id="d777f-123">이름으로 인수에 대 한 제한</span><span class="sxs-lookup"><span data-stu-id="d777f-123">Restrictions on Supplying Arguments by Name</span></span>  
 <span data-ttu-id="d777f-124">필수 인수를 입력 하지 못하도록 하려면 이름으로 인수를 전달할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d777f-124">You cannot pass arguments by name to avoid entering required arguments.</span></span> <span data-ttu-id="d777f-125">선택적 인수에만 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d777f-125">You can omit only the optional arguments.</span></span>  
  
 <span data-ttu-id="d777f-126">매개 변수 배열을 이름으로 전달할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d777f-126">You cannot pass a parameter array by name.</span></span> <span data-ttu-id="d777f-127">즉는 프로시저를 호출할 때 불특정 개수의 매개 변수 배열에 대 한 쉼표로 구분 된 인수를 제공 하 고 컴파일러가 단일 이름으로 둘 이상의 인수를 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d777f-127">This is because when you call the procedure, you supply an indefinite number of comma-separated arguments for the parameter array, and the compiler cannot associate more than one argument with a single name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d777f-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d777f-128">See Also</span></span>  
 [<span data-ttu-id="d777f-129">절차</span><span class="sxs-lookup"><span data-stu-id="d777f-129">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="d777f-130">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="d777f-130">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="d777f-131">방법: 프로시저에 인수 전달</span><span class="sxs-lookup"><span data-stu-id="d777f-131">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)  
 [<span data-ttu-id="d777f-132">값 또는 참조로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="d777f-132">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="d777f-133">선택적 매개 변수</span><span class="sxs-lookup"><span data-stu-id="d777f-133">Optional Parameters</span></span>](./optional-parameters.md)  
 [<span data-ttu-id="d777f-134">매개 변수 배열</span><span class="sxs-lookup"><span data-stu-id="d777f-134">Parameter Arrays</span></span>](./parameter-arrays.md)  
 [<span data-ttu-id="d777f-135">선택 사항</span><span class="sxs-lookup"><span data-stu-id="d777f-135">Optional</span></span>](../../../../visual-basic/language-reference/modifiers/optional.md)  
 [<span data-ttu-id="d777f-136">ParamArray</span><span class="sxs-lookup"><span data-stu-id="d777f-136">ParamArray</span></span>](../../../../visual-basic/language-reference/modifiers/paramarray.md)
