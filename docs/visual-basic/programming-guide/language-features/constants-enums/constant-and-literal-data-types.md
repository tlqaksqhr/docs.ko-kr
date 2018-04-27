---
title: 상수 및 리터럴 데이터 형식(Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- declaring constants [Visual Basic], literal data types
- data types [Visual Basic], declaring
- constants [Visual Basic], declaring
- explicit declarations
- literals [Visual Basic], coercing data type
- declarations [Visual Basic], data types
ms.assetid: 057206d2-3a5b-40b9-b3af-57446f9b52fa
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 58fa1e8c6c659c80cd7998a88d07849ea223750f
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="constant-and-literal-data-types-visual-basic"></a><span data-ttu-id="4927e-102">상수 및 리터럴 데이터 형식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4927e-102">Constant and Literal Data Types (Visual Basic)</span></span>
<span data-ttu-id="4927e-103">리터럴은 변수의 값 또는 3 숫자 또는 문자열 "Hello"와 같은 식의 결과가 아닌 자체로 표시 되는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="4927e-103">A literal is a value that is expressed as itself rather than as a variable's value or the result of an expression, such as the number 3 or the string "Hello".</span></span> <span data-ttu-id="4927e-104">상수는 리터럴 대신 하며 값 변경 될 수 있습니다 변수와 달리 프로그램 전체이 동일한 값을 유지 하는 의미 있는 이름을.</span><span class="sxs-lookup"><span data-stu-id="4927e-104">A constant is a meaningful name that takes the place of a literal and retains this same value throughout the program, as opposed to a variable, whose value may change.</span></span>  
  
 <span data-ttu-id="4927e-105">때 [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) 은 `Off` 및 [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) 은 `On`, 데이터 형식으로 모든 상수를 명시적으로 선언 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4927e-105">When [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) is `Off` and [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) is `On`, you must declare all constants explicitly with a data type.</span></span> <span data-ttu-id="4927e-106">다음 예제에서는 데이터의 형식 `MyByte` 데이터 형식으로 명시적 선언 된 `Byte`:</span><span class="sxs-lookup"><span data-stu-id="4927e-106">In the following example, the data type of `MyByte` is explicitly declared as data type `Byte`:</span></span>  
  
 [!code-vb[VbVbalrConstants#1](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_1.vb)]  
  
 <span data-ttu-id="4927e-107">때 `Option Infer` 은 `On` 또는 `Option Strict` 은 `Off`, 데이터 형식으로 지정 하지 않고 상수를 선언할 수 있습니다는 `As` 절.</span><span class="sxs-lookup"><span data-stu-id="4927e-107">When `Option Infer` is `On` or `Option Strict` is `Off`, you can declare a constant without specifying a data type with an `As` clause.</span></span> <span data-ttu-id="4927e-108">컴파일러에는 상수 식의 형식에서의 유형을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="4927e-108">The compiler determines the type of the constant from the type of the expression.</span></span> <span data-ttu-id="4927e-109">기본적으로 숫자 정수 리터럴은 캐스팅 되는 `Integer` 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="4927e-109">A numeric integer literal is cast by default to the `Integer` data type.</span></span> <span data-ttu-id="4927e-110">부동 소수점 숫자 기본 데이터 형식 `Double`, 키워드 및 `True` 및 `False` 지정는 `Boolean` 상수입니다.</span><span class="sxs-lookup"><span data-stu-id="4927e-110">The default data type for floating-point numbers is `Double`, and the keywords `True` and `False` specify a `Boolean` constant.</span></span>  
  
## <a name="literals-and-type-coercion"></a><span data-ttu-id="4927e-111">리터럴 및 형식 강제 변환</span><span class="sxs-lookup"><span data-stu-id="4927e-111">Literals and Type Coercion</span></span>  
 <span data-ttu-id="4927e-112">특정 데이터 형식; 리터럴을 적용 하려는 경우에 따라 예를 들어 매우 큰 정수 리터럴 값 형식의 변수에 할당할 때 `Decimal`합니다.</span><span class="sxs-lookup"><span data-stu-id="4927e-112">In some cases, you might want to force a literal to a particular data type; for example, when assigning a particularly large integral literal value to a variable of type `Decimal`.</span></span> <span data-ttu-id="4927e-113">다음 예에서는 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="4927e-113">The following example produces an error:</span></span>  
  
```  
Dim myDecimal as Decimal  
myDecimal = 100000000000000000000   ' This causes a compiler error.  
```  
  
 <span data-ttu-id="4927e-114">리터럴 표현에서 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="4927e-114">The error results from the representation of the literal.</span></span> <span data-ttu-id="4927e-115">`Decimal` 데이터 형식을 큰 값을 보유할 수 있지만 리터럴으로 암시적으로 표시 되는 `Long`, 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4927e-115">The `Decimal` data type can hold a value this large, but the literal is implicitly represented as a `Long`, which cannot.</span></span>  
  
 <span data-ttu-id="4927e-116">두 가지 방법으로 특정 데이터 형식에는 리터럴 강제 변환할 수 있습니다: 형식 문자를를 추가 하거나 묶기 문자 안에 배치 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="4927e-116">You can coerce a literal to a particular data type in two ways: by appending a type character to it, or by placing it within enclosing characters.</span></span> <span data-ttu-id="4927e-117">형식 문자 또는 문자를 포함 해야 즉시 리터럴 앞 이나 뒤에서, 공백이 나 어떤 종류의 문자 없이 합니다.</span><span class="sxs-lookup"><span data-stu-id="4927e-117">A type character or enclosing characters must immediately precede and/or follow the literal, with no intervening space or characters of any kind.</span></span>  
  
 <span data-ttu-id="4927e-118">이전 예제가 제대로 실행 되도록 하려면 추가 하는 `D` 형식으로 나타낼 수를 발생 시키는 리터럴 문자는 `Decimal`:</span><span class="sxs-lookup"><span data-stu-id="4927e-118">To make the previous example work, you can append the `D` type character to the literal, which causes it to be represented as a `Decimal`:</span></span>  
  
 [!code-vb[VbVbalrConstants#2](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_2.vb)]  
  
 <span data-ttu-id="4927e-119">다음 예제에서는 형식 문자와 바깥쪽 변수의 올바른 사용법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4927e-119">The following example demonstrates correct usage of type characters and enclosing characters:</span></span>  
  
 [!code-vb[VbVbalrConstants#3](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_3.vb)]  
  
 <span data-ttu-id="4927e-120">다음 표에 나와 바깥쪽 문자 및 Visual Basic에서 사용할 수 있는 형식 문자.</span><span class="sxs-lookup"><span data-stu-id="4927e-120">The following table shows the enclosing characters and type characters available in Visual Basic.</span></span>  
  
|<span data-ttu-id="4927e-121">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4927e-121">Data type</span></span>|<span data-ttu-id="4927e-122">구분 기호</span><span class="sxs-lookup"><span data-stu-id="4927e-122">Enclosing character</span></span>|<span data-ttu-id="4927e-123">추가 된 형식 문자</span><span class="sxs-lookup"><span data-stu-id="4927e-123">Appended type character</span></span>|  
|---|---|---|  
|`Boolean`|<span data-ttu-id="4927e-124">(없음)</span><span class="sxs-lookup"><span data-stu-id="4927e-124">(none)</span></span>|<span data-ttu-id="4927e-125">(없음)</span><span class="sxs-lookup"><span data-stu-id="4927e-125">(none)</span></span>|  
|`Byte`|<span data-ttu-id="4927e-126">(없음)</span><span class="sxs-lookup"><span data-stu-id="4927e-126">(none)</span></span>|<span data-ttu-id="4927e-127">(없음)</span><span class="sxs-lookup"><span data-stu-id="4927e-127">(none)</span></span>|  
|`Char`|<span data-ttu-id="4927e-128">"</span><span class="sxs-lookup"><span data-stu-id="4927e-128">"</span></span>|<span data-ttu-id="4927e-129">C</span><span class="sxs-lookup"><span data-stu-id="4927e-129">C</span></span>|  
|`Date`|#|<span data-ttu-id="4927e-130">(없음)</span><span class="sxs-lookup"><span data-stu-id="4927e-130">(none)</span></span>|  
|`Decimal`|<span data-ttu-id="4927e-131">(없음)</span><span class="sxs-lookup"><span data-stu-id="4927e-131">(none)</span></span>|<span data-ttu-id="4927e-132">D 또는 @</span><span class="sxs-lookup"><span data-stu-id="4927e-132">D or @</span></span>|  
|`Double`|<span data-ttu-id="4927e-133">(없음)</span><span class="sxs-lookup"><span data-stu-id="4927e-133">(none)</span></span>|<span data-ttu-id="4927e-134">R 또는 #</span><span class="sxs-lookup"><span data-stu-id="4927e-134">R or #</span></span>|  
|`Integer`|<span data-ttu-id="4927e-135">(없음)</span><span class="sxs-lookup"><span data-stu-id="4927e-135">(none)</span></span>|<span data-ttu-id="4927e-136">I 또는 %</span><span class="sxs-lookup"><span data-stu-id="4927e-136">I or %</span></span>|  
|`Long`|<span data-ttu-id="4927e-137">(없음)</span><span class="sxs-lookup"><span data-stu-id="4927e-137">(none)</span></span>|<span data-ttu-id="4927e-138">L 또는 &</span><span class="sxs-lookup"><span data-stu-id="4927e-138">L or &</span></span>|  
|`Short`|<span data-ttu-id="4927e-139">(없음)</span><span class="sxs-lookup"><span data-stu-id="4927e-139">(none)</span></span>|<span data-ttu-id="4927e-140">S</span><span class="sxs-lookup"><span data-stu-id="4927e-140">S</span></span>|  
|`Single`|<span data-ttu-id="4927e-141">(없음)</span><span class="sxs-lookup"><span data-stu-id="4927e-141">(none)</span></span>|<span data-ttu-id="4927e-142">F 또는!</span><span class="sxs-lookup"><span data-stu-id="4927e-142">F or !</span></span>|  
|`String`|<span data-ttu-id="4927e-143">"</span><span class="sxs-lookup"><span data-stu-id="4927e-143">"</span></span>|<span data-ttu-id="4927e-144">(없음)</span><span class="sxs-lookup"><span data-stu-id="4927e-144">(none)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4927e-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4927e-145">See Also</span></span>  
 [<span data-ttu-id="4927e-146">사용자 정의 상수</span><span class="sxs-lookup"><span data-stu-id="4927e-146">User-Defined Constants</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md)  
 [<span data-ttu-id="4927e-147">방법: 상수 선언</span><span class="sxs-lookup"><span data-stu-id="4927e-147">How to: Declare A Constant</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)  
 [<span data-ttu-id="4927e-148">상수 개요</span><span class="sxs-lookup"><span data-stu-id="4927e-148">Constants Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)  
 [<span data-ttu-id="4927e-149">Option Strict 문</span><span class="sxs-lookup"><span data-stu-id="4927e-149">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [<span data-ttu-id="4927e-150">Option Explicit 문</span><span class="sxs-lookup"><span data-stu-id="4927e-150">Option Explicit Statement</span></span>](../../../../visual-basic/language-reference/statements/option-explicit-statement.md)  
 [<span data-ttu-id="4927e-151">열거형 개요</span><span class="sxs-lookup"><span data-stu-id="4927e-151">Enumerations Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)  
 [<span data-ttu-id="4927e-152">방법: 열거형 선언</span><span class="sxs-lookup"><span data-stu-id="4927e-152">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)  
 [<span data-ttu-id="4927e-153">열거형 및 이름 한정</span><span class="sxs-lookup"><span data-stu-id="4927e-153">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [<span data-ttu-id="4927e-154">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4927e-154">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="4927e-155">상수 및 열거형</span><span class="sxs-lookup"><span data-stu-id="4927e-155">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
