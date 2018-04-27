---
title: 상수 개요(Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- constants [Visual Basic]
ms.assetid: 29016fe8-78b3-4dc8-90b8-1cfec2fa8ac9
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 40330e8c2c60c866200e009a8280c7ec9c855435
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="constants-overview-visual-basic"></a><span data-ttu-id="50c1c-102">상수 개요(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="50c1c-102">Constants Overview (Visual Basic)</span></span>
<span data-ttu-id="50c1c-103">상수는 숫자 또는 변경 되지 않는 문자열의 일어나는 의미 있는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="50c1c-103">A constant is a meaningful name that takes the place of a number or string that does not change.</span></span> <span data-ttu-id="50c1c-104">상수 이름에서 알 수 있듯이 응용 프로그램의 실행 전체에서 동일 하 게 유지 하는 값을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="50c1c-104">Constants store values that, as the name implies, remain the same throughout the execution of an application.</span></span> <span data-ttu-id="50c1c-105">코드의 가독성을 개선 하 고 상수를 사용 하 여 유지 쉽게 크게 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50c1c-105">You can greatly improve the readability of your code and make it easier to maintain by using constants.</span></span> <span data-ttu-id="50c1c-106">더 이상 표시 하는 값을 포함 하는 코드에서 사용 하거나 기억 하거나 의미가 명확 하지 않은 하기 어려운 특정 숫자에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="50c1c-106">Use them in code that contains values that reappear or that depends on certain numbers that are difficult to remember or have no obvious meaning.</span></span>  
  
## <a name="how-to-create-and-use-constants"></a><span data-ttu-id="50c1c-107">만들기 및 상수를 사용 하는 방법</span><span class="sxs-lookup"><span data-stu-id="50c1c-107">How to Create and Use Constants</span></span>  
 <span data-ttu-id="50c1c-108">Visual Basic을 인쇄 하 고 표시를 주로 사용 하 여 다양 한 미리 정의 된 상수를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="50c1c-108">Visual Basic contains a number of predefined constants, mainly using for printing and displaying.</span></span> <span data-ttu-id="50c1c-109">사용자 고유의 상수를 만들 수도 있습니다는 `Const` 변수 이름을 만들 때와 동일한 방법을 사용 하 여 문입니다.</span><span class="sxs-lookup"><span data-stu-id="50c1c-109">You can also create your own constants with the `Const` statement, using the same guidelines you would for creating a variable name.</span></span> <span data-ttu-id="50c1c-110">경우 `Option Strict` 은 `On`, 상수 형식을 명시적으로 선언 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="50c1c-110">If `Option Strict` is `On`, you must explicitly declare the constant type.</span></span>  
  
 <span data-ttu-id="50c1c-111">이름을 한정 하지 않고 변수를 참조할 수 있는 모든 코드 집합은 상수 범위와 동일한 위치에 선언 된 변수는 같습니다.</span><span class="sxs-lookup"><span data-stu-id="50c1c-111">A constant's scope, which is the set of all code that can refer to it without qualifying its name, is the same as that of a variable declared in the same location.</span></span> <span data-ttu-id="50c1c-112">특정 프로시저의 범위 내에 존재 하는 상수를 만들려면 해당 프로시저를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="50c1c-112">To create a constant that exists within the scope of a particular procedure, declare it inside that procedure.</span></span> <span data-ttu-id="50c1c-113">응용 프로그램에서 사용할 수 있는 상수를 만들려면 사용 하 여 선언 된 `Public` 클래스의 선언 섹션에는 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="50c1c-113">To create a constant that is available throughout an application, declare it using the `Public` keyword in the declarations section of the class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="50c1c-114">상수 변수 다소과 비슷한 있지만 수정 하거나 변수를 눌러도에 새 값을 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="50c1c-114">Although constants somewhat resemble variables, you cannot modify them or assign new values to them as you can to variables.</span></span>  
  
 <span data-ttu-id="50c1c-115">컨트롤이 나 함께 작업 하는 구성 요소에 대 한 개체 모델에서 코드에 사용할 상수를 정의할 수 있습니다 또는 사용자 정의 될 수 있습니다 (즉, 직접 만든).</span><span class="sxs-lookup"><span data-stu-id="50c1c-115">The constants you use in your code can be defined by the object model for controls or components you work with, or they can be user-defined (that is, those you create yourself).</span></span>  
  
## <a name="compile-time-and-run-time-constants"></a><span data-ttu-id="50c1c-116">컴파일 시간 및 런타임 상수</span><span class="sxs-lookup"><span data-stu-id="50c1c-116">Compile-time and Run-time Constants</span></span>  
 <span data-ttu-id="50c1c-117">컴파일 타임 상수 응용 프로그램이 실행 되는 동안에 실행 시간 상수를 계산할 수 하는 동안 코드를 컴파일하는 시간에 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="50c1c-117">A compile-time constant is computed at the time the code is compiled, while a run-time constant can only be computed while the application is running.</span></span> <span data-ttu-id="50c1c-118">컴파일 타임 상수 런타임 상수 될 때마다 변경 될 수 있지만 응용 프로그램을 실행 될 때마다 동일한 값을 갖게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="50c1c-118">A compile-time constant will have the same value each time an application runs, while a run-time constant may change each time.</span></span> <span data-ttu-id="50c1c-119">컴파일 시간 상수는 배열 범위, case 식 또는 열거자 이니셜라이저 등의 경우에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="50c1c-119">Compile-time constants are required for cases such as array bounds, case expressions, or enumerator initializers.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="50c1c-120">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="50c1c-120">In This Section</span></span>  
  
|<span data-ttu-id="50c1c-121">정의</span><span class="sxs-lookup"><span data-stu-id="50c1c-121">Definition</span></span>|<span data-ttu-id="50c1c-122">용어</span><span class="sxs-lookup"><span data-stu-id="50c1c-122">Term</span></span>|  
|---|---|  
|[<span data-ttu-id="50c1c-123">방법: 상수 선언</span><span class="sxs-lookup"><span data-stu-id="50c1c-123">How to: Declare A Constant</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)|<span data-ttu-id="50c1c-124">사용 하는 방법에 설명 된 `Const` 상수를 선언 하 고 해당 값을 설정 하는 문을 상수를 선언 하 여 값에 의미 있는 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="50c1c-124">Explains how to use the `Const` statement to declare a constant and set its value; by declaring a constant, you assign a meaningful name to the value.</span></span>|  
|[<span data-ttu-id="50c1c-125">사용자 정의 상수</span><span class="sxs-lookup"><span data-stu-id="50c1c-125">User-Defined Constants</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md)|<span data-ttu-id="50c1c-126">범위 지정에 대 한 정보를 포함 하 여 사용자 자신의 상수를 만드는 방법과 순환 참조가 발생 하지 않도록 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="50c1c-126">Describes how to create your own constants, including information on scoping and how to avoid circular references.</span></span>|  
|[<span data-ttu-id="50c1c-127">상수 및 리터럴 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="50c1c-127">Constant and Literal Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)|<span data-ttu-id="50c1c-128">Visual Basic 컴파일러를 상수를 초기화 하는 방법에 대해 설명 때 `Option Explicit` 꺼져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50c1c-128">Provides information on how the Visual Basic compiler initializes constants when `Option Explicit` is turned off.</span></span>|  
|[<span data-ttu-id="50c1c-129">방법: 관련 상수 값 그룹화</span><span class="sxs-lookup"><span data-stu-id="50c1c-129">How to: Group Related Constant Values Together</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-group-related-constant-values-together.md)|<span data-ttu-id="50c1c-130">관련 된 상수 값을 그룹화 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="50c1c-130">Demonstrates how to group constant values that are related.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="50c1c-131">참조</span><span class="sxs-lookup"><span data-stu-id="50c1c-131">Reference</span></span>  
  
|<span data-ttu-id="50c1c-132">정의</span><span class="sxs-lookup"><span data-stu-id="50c1c-132">Definition</span></span>|<span data-ttu-id="50c1c-133">용어</span><span class="sxs-lookup"><span data-stu-id="50c1c-133">Term</span></span>|  
|---|---|  
|[<span data-ttu-id="50c1c-134">상수 및 열거형</span><span class="sxs-lookup"><span data-stu-id="50c1c-134">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)|<span data-ttu-id="50c1c-135">Visual Basic에서 미리 정의 된 상수를 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="50c1c-135">Lists the constants predefined by Visual Basic.</span></span>|  
|[<span data-ttu-id="50c1c-136">Const 문</span><span class="sxs-lookup"><span data-stu-id="50c1c-136">Const Statement</span></span>](../../../../visual-basic/language-reference/statements/const-statement.md)|<span data-ttu-id="50c1c-137">설명의 `Const` 문 및 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="50c1c-137">Describes the `Const` statement and its use.</span></span>|  
|[<span data-ttu-id="50c1c-138">Option Strict 문</span><span class="sxs-lookup"><span data-stu-id="50c1c-138">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)|<span data-ttu-id="50c1c-139">설명의 `Option Strict` 문 및 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="50c1c-139">Describes the `Option Strict` statement and its use.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="50c1c-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="50c1c-140">See Also</span></span>  
 [<span data-ttu-id="50c1c-141">열거형 개요</span><span class="sxs-lookup"><span data-stu-id="50c1c-141">Enumerations Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)  
 [<span data-ttu-id="50c1c-142">방법: Visual Basic에서 배열 변수 초기화</span><span class="sxs-lookup"><span data-stu-id="50c1c-142">How to: Initialize an Array Variable in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)
