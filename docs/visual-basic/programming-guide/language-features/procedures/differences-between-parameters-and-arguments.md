---
title: 매개 변수와 인수의 차이점(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- parameters [Visual Basic], and arguments
- procedure arguments
- Visual Basic code, procedures
- arguments [Visual Basic], and parameters
- procedure parameters
- parameters [Visual Basic], definition
ms.assetid: c237c056-74f4-4749-9f2c-15864f139a31
ms.openlocfilehash: a5075c218371b754ac883b97475ab941811966b5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650688"
---
# <a name="differences-between-parameters-and-arguments-visual-basic"></a><span data-ttu-id="b7338-102">매개 변수와 인수의 차이점(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b7338-102">Differences Between Parameters and Arguments (Visual Basic)</span></span>
<span data-ttu-id="b7338-103">대부분의 경우에서 프로시저 호출 된 있는 상황에 대 한 정보가 제공 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7338-103">In most cases, a procedure must have some information about the circumstances in which it has been called.</span></span> <span data-ttu-id="b7338-104">반복 또는 공유 작업을 수행 하는 프로시저는 각 호출에 대 한 다른 정보를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7338-104">A procedure that performs repeated or shared tasks uses different information for each call.</span></span> <span data-ttu-id="b7338-105">이 정보는 변수, 상수, 및 호출 하면 프로시저에 전달 하는 식으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7338-105">This information consists of variables, constants, and expressions that you pass to the procedure when you call it.</span></span>  
  
 <span data-ttu-id="b7338-106">이 정보를 프로시저에 전달 하기 위해 프로시저는 다음과 같이 정의 됩니다. 한 *매개 변수*, 호출 코드에서 전달 하 고는 *인수* 해당 매개 변수에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7338-106">To communicate this information to the procedure, the procedure defines a *parameter*, and the calling code passes an *argument* to that parameter.</span></span> <span data-ttu-id="b7338-107">주차 공간으로 매개 변수 및 인수는 자동차 라고 생각할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7338-107">You can think of the parameter as a parking space and the argument as an automobile.</span></span> <span data-ttu-id="b7338-108">방금 처럼 다른 자동차 수 주차 공간에서 서로 다른 시간에, 호출 코드 전달할 수 있습니다 다른 인수를 동일한 매개 변수에 한다는 프로시저를 호출할 때마다 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7338-108">Just as different automobiles can park in a parking space at different times, the calling code can pass a different argument to the same parameter every time that it calls the procedure.</span></span>  
  
## <a name="parameters"></a><span data-ttu-id="b7338-109">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b7338-109">Parameters</span></span>  
 <span data-ttu-id="b7338-110">A *매개 변수* 프로시저는 호출할 때 전달 되어야 하는 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b7338-110">A *parameter* represents a value that the procedure expects you to pass when you call it.</span></span> <span data-ttu-id="b7338-111">프로시저의 선언 매개 변수를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b7338-111">The procedure's declaration defines its parameters.</span></span>  
  
 <span data-ttu-id="b7338-112">정의 하는 경우는 `Function` 또는 `Sub` 지정 프로시저는 *매개 변수 목록* 프로시저 이름 바로 다음 괄호로 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7338-112">When you define a `Function` or `Sub` procedure, you specify a *parameter list* in parentheses immediately following the procedure name.</span></span> <span data-ttu-id="b7338-113">이름, 데이터 형식 및 전달 메커니즘 지정 각 매개 변수에 대해 ([ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) 또는 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)).</span><span class="sxs-lookup"><span data-stu-id="b7338-113">For each parameter, you specify a name, a data type, and a passing mechanism ([ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)).</span></span> <span data-ttu-id="b7338-114">매개 변수가 옵션 임을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7338-114">You can also indicate that a parameter is optional.</span></span> <span data-ttu-id="b7338-115">즉, 호출 코드에 대 한 값을 전달할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b7338-115">This means that the calling code does not have to pass a value for it.</span></span>  
  
 <span data-ttu-id="b7338-116">각 매개 변수의 이름은로 사용 된 *지역 변수* 절차에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7338-116">The name of each parameter serves as a *local variable* in the procedure.</span></span> <span data-ttu-id="b7338-117">다른 변수를 사용 하 여 동일한 방식으로 매개 변수 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7338-117">You use the parameter name the same way you use any other variable.</span></span>  
  
## <a name="arguments"></a><span data-ttu-id="b7338-118">인수</span><span class="sxs-lookup"><span data-stu-id="b7338-118">Arguments</span></span>  
 <span data-ttu-id="b7338-119">*인수* 는 프로시저를 호출할 때 프로시저 매개 변수에 전달 하는 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b7338-119">An *argument* represents the value that you pass to a procedure parameter when you call the procedure.</span></span> <span data-ttu-id="b7338-120">호출 하는 코드는 프로시저를 호출할 때 인수를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7338-120">The calling code supplies the arguments when it calls the procedure.</span></span>  
  
 <span data-ttu-id="b7338-121">호출 하는 경우는 `Function` 또는 `Sub` 포함 하는 프로시저는 *인수 목록* 프로시저 이름 바로 다음 괄호로 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7338-121">When you call a `Function` or `Sub` procedure, you include an *argument list* in parentheses immediately following the procedure name.</span></span> <span data-ttu-id="b7338-122">각 인수 목록에서 같은 위치에 매개 변수에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7338-122">Each argument corresponds to the parameter in the same position in the list.</span></span>  
  
 <span data-ttu-id="b7338-123">매개 변수 정의와 달리 인수의 이름이 필요 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b7338-123">In contrast to parameter definition, arguments do not have names.</span></span> <span data-ttu-id="b7338-124">각 인수는 0 이상의 변수, 상수 및 리터럴 포함할 수 있는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="b7338-124">Each argument is an expression, which can contain zero or more variables, constants, and literals.</span></span> <span data-ttu-id="b7338-125">계산된 식의 데이터 형식은 일반적으로 해당 매개 변수에 대해 정의 된 데이터 형식과 같아야 하 고 어떤 경우 든 매개 변수 형식으로 변환할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7338-125">The data type of the evaluated expression should typically match the data type defined for the corresponding parameter, and in any case it must be convertible to the parameter type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7338-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b7338-126">See Also</span></span>  
 [<span data-ttu-id="b7338-127">절차</span><span class="sxs-lookup"><span data-stu-id="b7338-127">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="b7338-128">Sub 프로시저</span><span class="sxs-lookup"><span data-stu-id="b7338-128">Sub Procedures</span></span>](./sub-procedures.md)  
 [<span data-ttu-id="b7338-129">Function 프로시저</span><span class="sxs-lookup"><span data-stu-id="b7338-129">Function Procedures</span></span>](./function-procedures.md)  
 [<span data-ttu-id="b7338-130">속성 프로시저</span><span class="sxs-lookup"><span data-stu-id="b7338-130">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="b7338-131">연산자 프로시저</span><span class="sxs-lookup"><span data-stu-id="b7338-131">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="b7338-132">방법: 프로시저의 매개 변수 정의</span><span class="sxs-lookup"><span data-stu-id="b7338-132">How to: Define a Parameter for a Procedure</span></span>](./how-to-define-a-parameter-for-a-procedure.md)  
 [<span data-ttu-id="b7338-133">방법: 프로시저에 인수 전달</span><span class="sxs-lookup"><span data-stu-id="b7338-133">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)  
 [<span data-ttu-id="b7338-134">값 또는 참조로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="b7338-134">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="b7338-135">재귀 프로시저</span><span class="sxs-lookup"><span data-stu-id="b7338-135">Recursive Procedures</span></span>](./recursive-procedures.md)  
 [<span data-ttu-id="b7338-136">프로시저 오버로딩</span><span class="sxs-lookup"><span data-stu-id="b7338-136">Procedure Overloading</span></span>](./procedure-overloading.md)
