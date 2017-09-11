---
title: "상수 및 리터럴 데이터 형식 (Visual Basic) | Microsoft 문서"
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
- declaring constants, literal data types
- data types [Visual Basic], declaring
- constants, declaring
- explicit declarations
- literals, coercing data type
- declarations, data types
ms.assetid: 057206d2-3a5b-40b9-b3af-57446f9b52fa
caps.latest.revision: 19
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
ms.openlocfilehash: 29a997ee0dd847e8505d1a5c24cacfdfdb0a42cc
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="constant-and-literal-data-types-visual-basic"></a><span data-ttu-id="ba78e-102">상수 및 리터럴 데이터 형식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ba78e-102">Constant and Literal Data Types (Visual Basic)</span></span>
<span data-ttu-id="ba78e-103">리터럴은은 변수 값 또는 "Hello" 문자열 또는 숫자 3 등 식의 결과가 아닌 자체로 표현 되는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ba78e-103">A literal is a value that is expressed as itself rather than as a variable's value or the result of an expression, such as the number 3 or the string "Hello".</span></span> <span data-ttu-id="ba78e-104">상수는 리터럴 자리를 차지 하 고 값이 변경 될 수 있습니다 변수와 달리 프로그램 전체에서 동일한 값이 그대로 유지 하는 의미 있는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ba78e-104">A constant is a meaningful name that takes the place of a literal and retains this same value throughout the program, as opposed to a variable, whose value may change.</span></span>  
  
 <span data-ttu-id="ba78e-105">때 [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) 는 `Off` 및 [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) 는 `On`, 데이터 형식으로 모든 상수를 명시적으로 선언 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba78e-105">When [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) is `Off` and [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) is `On`, you must declare all constants explicitly with a data type.</span></span> <span data-ttu-id="ba78e-106">다음 예제에서는 데이터의 형식 `MyByte` 데이터 형식으로 명시적으로 선언 된 `Byte`:</span><span class="sxs-lookup"><span data-stu-id="ba78e-106">In the following example, the data type of `MyByte` is explicitly declared as data type `Byte`:</span></span>  
  
 <span data-ttu-id="ba78e-107">[!code-vb[VbVbalrConstants #&1;](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="ba78e-107">[!code-vb[VbVbalrConstants#1](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_1.vb)]</span></span>  
  
 <span data-ttu-id="ba78e-108">때 `Option Infer` 는 `On` 또는 `Option Strict` 는 `Off`, 데이터 형식으로 지정 하지 않고 상수를 선언할 수는 `As` 절.</span><span class="sxs-lookup"><span data-stu-id="ba78e-108">When `Option Infer` is `On` or `Option Strict` is `Off`, you can declare a constant without specifying a data type with an `As` clause.</span></span> <span data-ttu-id="ba78e-109">컴파일러에는 상수 식의 형식에서 형식을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba78e-109">The compiler determines the type of the constant from the type of the expression.</span></span> <span data-ttu-id="ba78e-110">기본적으로 숫자 정수 리터럴은 캐스팅 되는 `Integer` 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ba78e-110">A numeric integer literal is cast by default to the `Integer` data type.</span></span> <span data-ttu-id="ba78e-111">부동 소수점 숫자에 대 한 기본 데이터 형식 `Double`, 키워드 및 `True` 및 `False` 지정는 `Boolean` 상수입니다.</span><span class="sxs-lookup"><span data-stu-id="ba78e-111">The default data type for floating-point numbers is `Double`, and the keywords `True` and `False` specify a `Boolean` constant.</span></span>  
  
## <a name="literals-and-type-coercion"></a><span data-ttu-id="ba78e-112">리터럴 및 형식 강제 변환</span><span class="sxs-lookup"><span data-stu-id="ba78e-112">Literals and Type Coercion</span></span>  
 <span data-ttu-id="ba78e-113">일부 경우에는 특정 데이터 형식에 리터럴을 강제로 하려는 예를 들어, 매우 큰 정수 리터럴 값 형식의 변수에 할당할 때 `Decimal`합니다.</span><span class="sxs-lookup"><span data-stu-id="ba78e-113">In some cases, you might want to force a literal to a particular data type; for example, when assigning a particularly large integral literal value to a variable of type `Decimal`.</span></span> <span data-ttu-id="ba78e-114">다음 예제에서는 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba78e-114">The following example produces an error:</span></span>  
  
```  
Dim myDecimal as Decimal  
myDecimal = 100000000000000000000   ' This causes a compiler error.  
```  
  
 <span data-ttu-id="ba78e-115">리터럴 표현에서 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba78e-115">The error results from the representation of the literal.</span></span> <span data-ttu-id="ba78e-116">`Decimal` 데이터 형식을 큰 값을 가질 수 있지만 리터럴으로 암시적으로 표시 됩니다는 `Long`, 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ba78e-116">The `Decimal` data type can hold a value this large, but the literal is implicitly represented as a `Long`, which cannot.</span></span>  
  
 <span data-ttu-id="ba78e-117">두 가지 방법으로 특정 데이터 형식에 리터럴 강제 변환할 수 있습니다: 형식 문자를 추가 하 여 또는 묶기 문자 안에 배치 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba78e-117">You can coerce a literal to a particular data type in two ways: by appending a type character to it, or by placing it within enclosing characters.</span></span> <span data-ttu-id="ba78e-118">형식 문자 또는 문자를 포함 해야 바로 앞 이나 뒤에 없는 중간 공백이 나 기타 모든 종류의 문자는 리터럴.</span><span class="sxs-lookup"><span data-stu-id="ba78e-118">A type character or enclosing characters must immediately precede and/or follow the literal, with no intervening space or characters of any kind.</span></span>  
  
 <span data-ttu-id="ba78e-119">이전 예제가 제대로 실행 되도록 하려면 추가 하는 `D` 형식으로 나타낼 수를 발생 시키는 리터럴 문자는 `Decimal`:</span><span class="sxs-lookup"><span data-stu-id="ba78e-119">To make the previous example work, you can append the `D` type character to the literal, which causes it to be represented as a `Decimal`:</span></span>  
  
 <span data-ttu-id="ba78e-120">[!code-vb[VbVbalrConstants #&2;](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="ba78e-120">[!code-vb[VbVbalrConstants#2](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_2.vb)]</span></span>  
  
 <span data-ttu-id="ba78e-121">다음 예제에서는 형식 문자 및 바깥쪽 문자 변수의 올바른 사용법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ba78e-121">The following example demonstrates correct usage of type characters and enclosing characters:</span></span>  
  
 <span data-ttu-id="ba78e-122">[!code-vb[VbVbalrConstants #&3;](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="ba78e-122">[!code-vb[VbVbalrConstants#3](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_3.vb)]</span></span>  
  
 <span data-ttu-id="ba78e-123">바깥쪽 문자와 형식에서 사용할 수 있는 문자는 다음 표에 나와 있는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="ba78e-123">The following table shows the enclosing characters and type characters available in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>  
  
|<span data-ttu-id="ba78e-124">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="ba78e-124">Data type</span></span>|<span data-ttu-id="ba78e-125">구분 기호</span><span class="sxs-lookup"><span data-stu-id="ba78e-125">Enclosing character</span></span>|<span data-ttu-id="ba78e-126">추가 된 형식 문자</span><span class="sxs-lookup"><span data-stu-id="ba78e-126">Appended type character</span></span>|  
|---|---|---|  
|`Boolean`|<span data-ttu-id="ba78e-127">(없음)</span><span class="sxs-lookup"><span data-stu-id="ba78e-127">(none)</span></span>|<span data-ttu-id="ba78e-128">(없음)</span><span class="sxs-lookup"><span data-stu-id="ba78e-128">(none)</span></span>|  
|`Byte`|<span data-ttu-id="ba78e-129">(없음)</span><span class="sxs-lookup"><span data-stu-id="ba78e-129">(none)</span></span>|<span data-ttu-id="ba78e-130">(없음)</span><span class="sxs-lookup"><span data-stu-id="ba78e-130">(none)</span></span>|  
|`Char`|<span data-ttu-id="ba78e-131">"</span><span class="sxs-lookup"><span data-stu-id="ba78e-131">"</span></span>|<span data-ttu-id="ba78e-132">C</span><span class="sxs-lookup"><span data-stu-id="ba78e-132">C</span></span>|  
|`Date`|#|<span data-ttu-id="ba78e-133">(없음)</span><span class="sxs-lookup"><span data-stu-id="ba78e-133">(none)</span></span>|  
|`Decimal`|<span data-ttu-id="ba78e-134">(없음)</span><span class="sxs-lookup"><span data-stu-id="ba78e-134">(none)</span></span>|<span data-ttu-id="ba78e-135">D 또는 @</span><span class="sxs-lookup"><span data-stu-id="ba78e-135">D or @</span></span>|  
|`Double`|<span data-ttu-id="ba78e-136">(없음)</span><span class="sxs-lookup"><span data-stu-id="ba78e-136">(none)</span></span>|<span data-ttu-id="ba78e-137">R 또는</span><span class="sxs-lookup"><span data-stu-id="ba78e-137">R or</span></span> #|  
|`Integer`|<span data-ttu-id="ba78e-138">(없음)</span><span class="sxs-lookup"><span data-stu-id="ba78e-138">(none)</span></span>|<span data-ttu-id="ba78e-139">I 또는 %</span><span class="sxs-lookup"><span data-stu-id="ba78e-139">I or %</span></span>|  
|`Long`|<span data-ttu-id="ba78e-140">(없음)</span><span class="sxs-lookup"><span data-stu-id="ba78e-140">(none)</span></span>|<span data-ttu-id="ba78e-141">L 또는 / /</span><span class="sxs-lookup"><span data-stu-id="ba78e-141">L or &</span></span>|  
|`Short`|<span data-ttu-id="ba78e-142">(없음)</span><span class="sxs-lookup"><span data-stu-id="ba78e-142">(none)</span></span>|<span data-ttu-id="ba78e-143">S</span><span class="sxs-lookup"><span data-stu-id="ba78e-143">S</span></span>|  
|`Single`|<span data-ttu-id="ba78e-144">(없음)</span><span class="sxs-lookup"><span data-stu-id="ba78e-144">(none)</span></span>|<span data-ttu-id="ba78e-145">F 또는!</span><span class="sxs-lookup"><span data-stu-id="ba78e-145">F or !</span></span>|  
|`String`|<span data-ttu-id="ba78e-146">"</span><span class="sxs-lookup"><span data-stu-id="ba78e-146">"</span></span>|<span data-ttu-id="ba78e-147">(없음)</span><span class="sxs-lookup"><span data-stu-id="ba78e-147">(none)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ba78e-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ba78e-148">See Also</span></span>  
 <span data-ttu-id="ba78e-149">[사용자 정의 상수](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md) </span><span class="sxs-lookup"><span data-stu-id="ba78e-149">[User-Defined Constants](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md) </span></span>  
<span data-ttu-id="ba78e-150"> [방법: 상수 선언](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md) </span><span class="sxs-lookup"><span data-stu-id="ba78e-150"> [How to: Declare A Constant](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md) </span></span>  
<span data-ttu-id="ba78e-151"> [상수 개요](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md) </span><span class="sxs-lookup"><span data-stu-id="ba78e-151"> [Constants Overview](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md) </span></span>  
<span data-ttu-id="ba78e-152"> [Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md) </span><span class="sxs-lookup"><span data-stu-id="ba78e-152"> [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) </span></span>  
<span data-ttu-id="ba78e-153"> [Option Explicit 문](../../../../visual-basic/language-reference/statements/option-explicit-statement.md) </span><span class="sxs-lookup"><span data-stu-id="ba78e-153"> [Option Explicit Statement](../../../../visual-basic/language-reference/statements/option-explicit-statement.md) </span></span>  
<span data-ttu-id="ba78e-154"> [열거형 개요](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md) </span><span class="sxs-lookup"><span data-stu-id="ba78e-154"> [Enumerations Overview](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md) </span></span>  
<span data-ttu-id="ba78e-155"> [방법: 열거형 선언](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md) </span><span class="sxs-lookup"><span data-stu-id="ba78e-155"> [How to: Declare an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md) </span></span>  
<span data-ttu-id="ba78e-156"> [열거형 및 이름 한정](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md) </span><span class="sxs-lookup"><span data-stu-id="ba78e-156"> [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md) </span></span>  
<span data-ttu-id="ba78e-157"> [데이터 형식](../../../../visual-basic/language-reference/data-types/data-type-summary.md) </span><span class="sxs-lookup"><span data-stu-id="ba78e-157"> [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md) </span></span>  
<span data-ttu-id="ba78e-158"> [상수 및 열거형](../../../../visual-basic/language-reference/constants-and-enumerations.md)</span><span class="sxs-lookup"><span data-stu-id="ba78e-158"> [Constants and Enumerations](../../../../visual-basic/language-reference/constants-and-enumerations.md)</span></span>
