---
title: "상수 개요 (Visual Basic) | Microsoft 문서"
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
- constants
ms.assetid: 29016fe8-78b3-4dc8-90b8-1cfec2fa8ac9
caps.latest.revision: 14
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
ms.openlocfilehash: 2df21b9e3e814c654b355472aa645481060c6f68
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="constants-overview-visual-basic"></a><span data-ttu-id="38b57-102">상수 개요(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="38b57-102">Constants Overview (Visual Basic)</span></span>
<span data-ttu-id="38b57-103">상수는 숫자 또는 변경 되지 않는 문자열의 발생 하는 의미 있는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="38b57-103">A constant is a meaningful name that takes the place of a number or string that does not change.</span></span> <span data-ttu-id="38b57-104">상수 이름에서 알 수 있듯이 응용 프로그램의 실행 하는 동안 동일 하 게 유지 하는 값을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="38b57-104">Constants store values that, as the name implies, remain the same throughout the execution of an application.</span></span> <span data-ttu-id="38b57-105">크게 코드의 가독성을 향상 시킬 수 있으며 쉽게 상수를 사용 하 여 유지.</span><span class="sxs-lookup"><span data-stu-id="38b57-105">You can greatly improve the readability of your code and make it easier to maintain by using constants.</span></span> <span data-ttu-id="38b57-106">다시 나타나는 값을 포함 하는 코드에서 사용 하거나 기억 하거나 의미가 명확 하지 않은 하기 어려운 특정 숫자에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="38b57-106">Use them in code that contains values that reappear or that depends on certain numbers that are difficult to remember or have no obvious meaning.</span></span>  
  
## <a name="how-to-create-and-use-constants"></a><span data-ttu-id="38b57-107">만들기 및 상수를 사용 하는 방법</span><span class="sxs-lookup"><span data-stu-id="38b57-107">How to Create and Use Constants</span></span>  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="38b57-108">다양 한 인쇄 및 표시를 위해 주로 사용 하는 미리 정의 된 상수를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="38b57-108"> contains a number of predefined constants, mainly using for printing and displaying.</span></span> <span data-ttu-id="38b57-109">사용자 고유의 상수를 만들 수도 있습니다는 `Const` 변수 이름을 만들 때와 동일한 방법 사용 하 여 문.</span><span class="sxs-lookup"><span data-stu-id="38b57-109">You can also create your own constants with the `Const` statement, using the same guidelines you would for creating a variable name.</span></span> <span data-ttu-id="38b57-110">경우 `Option Strict` 는 `On`, 상수 형식을 명시적으로 선언 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38b57-110">If `Option Strict` is `On`, you must explicitly declare the constant type.</span></span>  
  
 <span data-ttu-id="38b57-111">이름을 한정 하지 않고 변수를 참조할 수 있는 모든 코드 집합이 있는 상수의 범위를 동일한 위치에 선언 된 변수에와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="38b57-111">A constant's scope, which is the set of all code that can refer to it without qualifying its name, is the same as that of a variable declared in the same location.</span></span> <span data-ttu-id="38b57-112">특정 절차의 범위 내에 존재 하는 상수를 만들려면 해당 프로시저를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="38b57-112">To create a constant that exists within the scope of a particular procedure, declare it inside that procedure.</span></span> <span data-ttu-id="38b57-113">응용 프로그램을 통해 사용할 수 있는 상수를 만들려면 사용 하 여 선언 된 `Public` 클래스의 선언 섹션에서 키워드.</span><span class="sxs-lookup"><span data-stu-id="38b57-113">To create a constant that is available throughout an application, declare it using the `Public` keyword in the declarations section of the class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="38b57-114">상수 변수 다소과 비슷한 있지만 다음에 수정 하거나 변수를 사용할 때 처럼에 새 값을 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="38b57-114">Although constants somewhat resemble variables, you cannot modify them or assign new values to them as you can to variables.</span></span>  
  
 <span data-ttu-id="38b57-115">컨트롤 또는 함께 작업 하는 구성 요소에 대 한 개체 모델에서 코드에 사용할 상수를 정의할 수 또는 사용자 정의 될 수 있습니다 (즉, 직접 만든).</span><span class="sxs-lookup"><span data-stu-id="38b57-115">The constants you use in your code can be defined by the object model for controls or components you work with, or they can be user-defined (that is, those you create yourself).</span></span>  
  
## <a name="compile-time-and-run-time-constants"></a><span data-ttu-id="38b57-116">컴파일 타임 및 런타임 상수</span><span class="sxs-lookup"><span data-stu-id="38b57-116">Compile-time and Run-time Constants</span></span>  
 <span data-ttu-id="38b57-117">컴파일 타임 상수는 응용 프로그램이 실행 되는 동안에 런타임 상수를 계산할 수 있지만 코드를 컴파일하는 시간에서 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38b57-117">A compile-time constant is computed at the time the code is compiled, while a run-time constant can only be computed while the application is running.</span></span> <span data-ttu-id="38b57-118">컴파일 타임 상수 런타임 상수 될 때마다 변경 될 수 있지만 응용 프로그램을 실행할 때마다 동일한 값이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38b57-118">A compile-time constant will have the same value each time an application runs, while a run-time constant may change each time.</span></span> <span data-ttu-id="38b57-119">컴파일 타임 상수는 열거자 이니셜라이저, 배열 및 case 식 등의 경우에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="38b57-119">Compile-time constants are required for cases such as array bounds, case expressions, or enumerator initializers.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="38b57-120">단원 내용</span><span class="sxs-lookup"><span data-stu-id="38b57-120">In This Section</span></span>  
  
|<span data-ttu-id="38b57-121">정의</span><span class="sxs-lookup"><span data-stu-id="38b57-121">Definition</span></span>|<span data-ttu-id="38b57-122">용어</span><span class="sxs-lookup"><span data-stu-id="38b57-122">Term</span></span>|  
|---|---|  
|[<span data-ttu-id="38b57-123">방법: 상수 선언</span><span class="sxs-lookup"><span data-stu-id="38b57-123">How to: Declare A Constant</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)|<span data-ttu-id="38b57-124">사용 하는 방법에 설명 된 `Const` 상수를 선언 하 고 해당 값을 설정 하는 문을 상수를 선언 하 여 값에 의미 있는 이름을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="38b57-124">Explains how to use the `Const` statement to declare a constant and set its value; by declaring a constant, you assign a meaningful name to the value.</span></span>|  
|[<span data-ttu-id="38b57-125">사용자 정의 상수</span><span class="sxs-lookup"><span data-stu-id="38b57-125">User-Defined Constants</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md)|<span data-ttu-id="38b57-126">범위 지정에 대 한 정보를 포함 하 여 사용자 자신의 상수를 만드는 방법 및 순환 참조를 방지 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="38b57-126">Describes how to create your own constants, including information on scoping and how to avoid circular references.</span></span>|  
|[<span data-ttu-id="38b57-127">상수 및 리터럴 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="38b57-127">Constant and Literal Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)|<span data-ttu-id="38b57-128">방법에 대해 설명 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 컴파일러 상수를 초기화 하는 경우 `Option Explicit` 꺼져 합니다.</span><span class="sxs-lookup"><span data-stu-id="38b57-128">Provides information on how the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler initializes constants when `Option Explicit` is turned off.</span></span>|  
|[<span data-ttu-id="38b57-129">방법: 관련 상수 값 그룹화</span><span class="sxs-lookup"><span data-stu-id="38b57-129">How to: Group Related Constant Values Together</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-group-related-constant-values-together.md)|<span data-ttu-id="38b57-130">관련 된 상수 값을 그룹화 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="38b57-130">Demonstrates how to group constant values that are related.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="38b57-131">참조</span><span class="sxs-lookup"><span data-stu-id="38b57-131">Reference</span></span>  
  
|<span data-ttu-id="38b57-132">정의</span><span class="sxs-lookup"><span data-stu-id="38b57-132">Definition</span></span>|<span data-ttu-id="38b57-133">용어</span><span class="sxs-lookup"><span data-stu-id="38b57-133">Term</span></span>|  
|---|---|  
|[<span data-ttu-id="38b57-134">상수 및 열거형</span><span class="sxs-lookup"><span data-stu-id="38b57-134">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)|<span data-ttu-id="38b57-135">미리 정의 된 상수를 나열 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="38b57-135">Lists the constants predefined by [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>|  
|[<span data-ttu-id="38b57-136">Const 문</span><span class="sxs-lookup"><span data-stu-id="38b57-136">Const Statement</span></span>](../../../../visual-basic/language-reference/statements/const-statement.md)|<span data-ttu-id="38b57-137">설명의 `Const` 문 및 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="38b57-137">Describes the `Const` statement and its use.</span></span>|  
|[<span data-ttu-id="38b57-138">Option Strict 문</span><span class="sxs-lookup"><span data-stu-id="38b57-138">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)|<span data-ttu-id="38b57-139">설명의 `Option Strict` 문 및 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="38b57-139">Describes the `Option Strict` statement and its use.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="38b57-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="38b57-140">See Also</span></span>  
 <span data-ttu-id="38b57-141">[열거형 개요](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md) </span><span class="sxs-lookup"><span data-stu-id="38b57-141">[Enumerations Overview](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md) </span></span>  
<span data-ttu-id="38b57-142"> [방법: Visual Basic에서 배열 변수 초기화](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)</span><span class="sxs-lookup"><span data-stu-id="38b57-142"> [How to: Initialize an Array Variable in Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md)</span></span>
