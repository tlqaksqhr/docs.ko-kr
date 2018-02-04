---
title: "형식 문자(Visual Basic)"
ms.custom: 
ms.date: 01/31/2018
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- '&H prefix for hexadecimal values'
- hexadecimal literals [Visual Basic]
- F literal type character [Visual Basic]
- '& identifier type character'
- type characters [Visual Basic]
- octal literals [Visual Basic]
- literals [Visual Basic], hexadecimal
- '&O prefix for octal values'
- literals [Visual Basic], default types
- defaults, literal types
- C literal type character [Visual Basic]
- type characters [Visual Basic], literal
- $ identifier type character
- L literal type character [Visual Basic]
- UI literal type characters [Visual Basic]
- default literal types [Visual Basic]
- D literal type character [Visual Basic]
- literals [Visual Basic], octal
- S literal type character [Visual Basic]
- '! identifier type character'
- US literal type characters [Visual Basic]
- '% identifier type character'
- data types [Visual Basic], type characters
- characters [Visual Basic], identifier type
- type characters [Visual Basic], identifier
- '# identifier type character'
- identifier type characters [Visual Basic]
- literal type characters [Visual Basic]
- I literal type character [Visual Basic]
- R literal type character [Visual Basic]
- '@ identifier type character'
- UL literal type characters [Visual Basic]
- literal types [Visual Basic], default
ms.assetid: 6353cb9b-6ee4-4af6-a5a8-88ce39f90cc5
author: rpetrusha
ms.author: ronpet
ms.manager: wpickett
ms.openlocfilehash: bdb675b9605d03829c95897382daa6d03cf1b041
ms.sourcegitcommit: d2da0142247ef42a219a5d2907f153e62dc6ea0d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/01/2018
---
# <a name="type-characters-visual-basic"></a><span data-ttu-id="90013-102">입력 문자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="90013-102">Type characters (Visual Basic)</span></span>

<span data-ttu-id="90013-103">를 선언문의 데이터 형식을 지정 하는 것 외에도 데이터 형식을 사용 하 여 몇 가지 프로그래밍 요소의 강제로 실행할 수는 *형식 문자*합니다.</span><span class="sxs-lookup"><span data-stu-id="90013-103">In addition to specifying a data type in a declaration statement, you can force the data type of some programming elements with a *type character*.</span></span> <span data-ttu-id="90013-104">형식 문자 어떤 종류의 중간 문자가 없는 요소를 다음에 나와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="90013-104">The type character must immediately follow the element, with no intervening characters of any kind.</span></span>

<span data-ttu-id="90013-105">형식 문자 요소 이름의 일부가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="90013-105">The type character is not part of the name of the element.</span></span> <span data-ttu-id="90013-106">형식 문자 없이 형식 문자를 정의 된 요소를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90013-106">An element defined with a type character can be referenced without the type character.</span></span>

## <a name="identifier-type-characters"></a><span data-ttu-id="90013-107">식별자 형식 문자</span><span class="sxs-lookup"><span data-stu-id="90013-107">Identifier type characters</span></span>

<span data-ttu-id="90013-108">집합을 제공 하는 Visual Basic *식별자 형식 문자* 데이터 형식의 변수 또는 상수를 지정 하는 선언에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90013-108">Visual Basic supplies a set of *identifier type characters* that you can use in a declaration to specify the data type of a variable or constant.</span></span> <span data-ttu-id="90013-109">다음 표에서 사용 예제를 사용할 수 있는 식별자 형식 문자를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="90013-109">The following table shows the available identifier type characters with examples of usage.</span></span>
  
|<span data-ttu-id="90013-110">식별자 형식 문자</span><span class="sxs-lookup"><span data-stu-id="90013-110">Identifier type character</span></span>|<span data-ttu-id="90013-111">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="90013-111">Data type</span></span>|<span data-ttu-id="90013-112">예</span><span class="sxs-lookup"><span data-stu-id="90013-112">Example</span></span>|  
|-------------------------------|---------------|-------------|  
|`%`|`Integer`|`Dim L%`|  
|`&`|`Long`|`Dim M&`|  
|`@`|`Decimal`|`Const W@ = 37.5`|  
|`!`|`Single`|`Dim Q!`|  
|`#`|`Double`|`Dim X#`|  
|`$`|`String`|`Dim V$ = "Secret"`|  
  
 <span data-ttu-id="90013-113">식별자 형식 문자가 없습니다는 `Boolean`, `Byte`, `Char`, `Date`, `Object`, `SByte`, `Short`, `UInteger`, `ULong`, 또는 `UShort` 데이터 형식 또는 배열 또는 구조체와 같은 복합 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="90013-113">No identifier type characters exist for the `Boolean`, `Byte`, `Char`, `Date`, `Object`, `SByte`, `Short`, `UInteger`, `ULong`, or `UShort` data types, or for any composite data types such as arrays or structures.</span></span>

<span data-ttu-id="90013-114">일부 경우에 추가할 수는 `$` Visual Basic 함수 예를 들어 문자 `Left$` 대신 `Left`형식의 반환된 값을 얻기 위해 `String`합니다.</span><span class="sxs-lookup"><span data-stu-id="90013-114">In some cases, you can append the `$` character to a Visual Basic function, for example `Left$` instead of `Left`, to obtain a returned value of type `String`.</span></span>

<span data-ttu-id="90013-115">모든 경우에 식별자 형식 문자 바로 뒤에 붙여야 식별자 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="90013-115">In all cases, the identifier type character must immediately follow the identifier name.</span></span>

## <a name="literal-type-characters"></a><span data-ttu-id="90013-116">리터럴 형식 문자</span><span class="sxs-lookup"><span data-stu-id="90013-116">Literal type characters</span></span>

<span data-ttu-id="90013-117">A *리터럴* 데이터 형식의 특정 값의 텍스트 표현입니다.</span><span class="sxs-lookup"><span data-stu-id="90013-117">A *literal* is a textual representation of a particular value of a data type.</span></span>  

### <a name="default-literal-types"></a><span data-ttu-id="90013-118">기본 리터럴 형식</span><span class="sxs-lookup"><span data-stu-id="90013-118">Default literal types</span></span>

<span data-ttu-id="90013-119">리터럴 형태가 일반적으로 코드에 표시 된 대로 해당 데이터 형식을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="90013-119">The form of a literal as it appears in your code ordinarily determines its data type.</span></span> <span data-ttu-id="90013-120">다음 표에서 이러한 기본 유형을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="90013-120">The following table shows these default types.</span></span>  
  
|<span data-ttu-id="90013-121">리터럴 텍스트 형식</span><span class="sxs-lookup"><span data-stu-id="90013-121">Textual form of literal</span></span>|<span data-ttu-id="90013-122">기본 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="90013-122">Default data type</span></span>|<span data-ttu-id="90013-123">예제</span><span class="sxs-lookup"><span data-stu-id="90013-123">Example</span></span>|  
|-----------------------------|-----------------------|-------------|  
|<span data-ttu-id="90013-124">숫자, 더 소수 부분</span><span class="sxs-lookup"><span data-stu-id="90013-124">Numeric, no fractional part</span></span>|`Integer`|`2147483647`|  
|<span data-ttu-id="90013-125">너무 커서 숫자, 더 소수 부분`Integer`</span><span class="sxs-lookup"><span data-stu-id="90013-125">Numeric, no fractional part, too large for `Integer`</span></span>|`Long`|`2147483648`|  
|<span data-ttu-id="90013-126">숫자, 소수 부분</span><span class="sxs-lookup"><span data-stu-id="90013-126">Numeric, fractional part</span></span>|`Double`|`1.2`|  
|<span data-ttu-id="90013-127">큰따옴표로 묶인</span><span class="sxs-lookup"><span data-stu-id="90013-127">Enclosed in double quotation marks</span></span>|`String`|`"A"`|  
|<span data-ttu-id="90013-128">숫자 기호 사이 포함 된</span><span class="sxs-lookup"><span data-stu-id="90013-128">Enclosed within number signs</span></span>|`Date`|`#5/17/1993 9:32 AM#`|  

### <a name="forced-literal-types"></a><span data-ttu-id="90013-129">강제 리터럴 형식</span><span class="sxs-lookup"><span data-stu-id="90013-129">Forced literal types</span></span>

<span data-ttu-id="90013-130">집합을 제공 하는 Visual Basic *리터럴 형식 문자*, 리터럴을 이외의 데이터 형식을 형태로 취하도록을 강제 적용 하는 데 사용할 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="90013-130">Visual Basic supplies a set of *literal type characters*, which you can use to force a literal to assume a data type other than the one its form indicates.</span></span> <span data-ttu-id="90013-131">리터럴의 끝에 문자를 추가 하 여이 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="90013-131">You do this by appending the character to the end of the literal.</span></span> <span data-ttu-id="90013-132">다음 표에서 사용 예제를 사용할 수 있는 리터럴 형식 문자를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="90013-132">The following table shows the available literal type characters with examples of usage.</span></span>
  
|<span data-ttu-id="90013-133">리터럴 형식 문자</span><span class="sxs-lookup"><span data-stu-id="90013-133">Literal type character</span></span>|<span data-ttu-id="90013-134">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="90013-134">Data type</span></span>|<span data-ttu-id="90013-135">예</span><span class="sxs-lookup"><span data-stu-id="90013-135">Example</span></span>|  
|----------------------------|---------------|-------------|  
|`S`|`Short`|`I = 347S`|
|`I`|`Integer`|`J = 347I`|
|`L`|`Long`|`K = 347L`|
|`D`|`Decimal`|`X = 347D`|
|`F`|`Single`|`Y = 347F`|
|`R`|`Double`|`Z = 347R`|
|`US`|`UShort`|`L = 347US`|
|`UI`|`UInteger`|`M = 347UI`|
|`UL`|`ULong`|`N = 347UL`|
|`C`|`Char`|`Q = "."C`|

<span data-ttu-id="90013-136">리터럴 형식 문자가 없습니다는 `Boolean`, `Byte`, `Date`, `Object`, `SByte`, 또는 `String` 데이터 형식 또는 배열 또는 구조체와 같은 복합 데이터 형식에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="90013-136">No literal type characters exist for the `Boolean`, `Byte`, `Date`, `Object`, `SByte`, or `String` data types, or for any composite data types such as arrays or structures.</span></span>

<span data-ttu-id="90013-137">리터럴 식별자 형식 문자를 사용할 수도 있습니다 (`%`, `&`, `@`, `!`, `#`, `$`), 변수, 상수, 및 식 처럼 합니다.</span><span class="sxs-lookup"><span data-stu-id="90013-137">Literals can also use the identifier type characters (`%`, `&`, `@`, `!`, `#`, `$`), as can variables, constants, and expressions.</span></span> <span data-ttu-id="90013-138">그러나 리터럴 형식 문자 (`S`, `I`, `L`, `D`, `F`, `R`, `C`) 리터럴 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90013-138">However, the literal type characters (`S`, `I`, `L`, `D`, `F`, `R`, `C`) can be used only with literals.</span></span>

<span data-ttu-id="90013-139">모든 경우에 리터럴 형식 문자 바로 뒤에 붙여야 리터럴 값입니다.</span><span class="sxs-lookup"><span data-stu-id="90013-139">In all cases, the literal type character must immediately follow the literal value.</span></span>

## <a name="hexadecimal-binary-and-octal-literals"></a><span data-ttu-id="90013-140">16 진수, 이진 및 8 진수 리터럴</span><span class="sxs-lookup"><span data-stu-id="90013-140">Hexadecimal, binary, and octal literals</span></span>

<span data-ttu-id="90013-141">컴파일러는 일반적으로 10 진수 (밑수 10) 번호 시스템에는 정수 리터럴로 해석 합니다.</span><span class="sxs-lookup"><span data-stu-id="90013-141">The compiler normally interprets an integer literal to be in the decimal (base 10) number system.</span></span> <span data-ttu-id="90013-142">과 함께 16 진수 (밑수 16) 숫자로 정수 리터럴을 정의할 수도 있습니다는 `&H` 접두사를 포함 하 여 이진 (밑 2) 숫자로 `&B` 접두사는 8 진수 8으로 번호를 `&O` 접두사 합니다.</span><span class="sxs-lookup"><span data-stu-id="90013-142">You can also define an integer literal as a hexadecimal (base 16) number with the `&H` prefix, as a binary (base 2) number with the `&B` prefix, and as an octal (base 8) number with the `&O` prefix.</span></span> <span data-ttu-id="90013-143">접두사 뒤의 숫자는 체계에 적합 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="90013-143">The digits that follow the prefix must be appropriate for the number system.</span></span> <span data-ttu-id="90013-144">다음 표에서이 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="90013-144">The following table illustrates this.</span></span>  
  
|<span data-ttu-id="90013-145">기 수</span><span class="sxs-lookup"><span data-stu-id="90013-145">Number base</span></span>|<span data-ttu-id="90013-146">접두사</span><span class="sxs-lookup"><span data-stu-id="90013-146">Prefix</span></span>|<span data-ttu-id="90013-147">유효한 숫자 값</span><span class="sxs-lookup"><span data-stu-id="90013-147">Valid digit values</span></span>|<span data-ttu-id="90013-148">예</span><span class="sxs-lookup"><span data-stu-id="90013-148">Example</span></span>|
|-----------------|------------|------------------------|-------------|
|<span data-ttu-id="90013-149">16진수</span><span class="sxs-lookup"><span data-stu-id="90013-149">Hexadecimal (base 16)</span></span>|`&H`|<span data-ttu-id="90013-150">0-9 및 A-F</span><span class="sxs-lookup"><span data-stu-id="90013-150">0-9 and A-F</span></span>|`&HFFFF`|
|<span data-ttu-id="90013-151">이진 (밑 2)</span><span class="sxs-lookup"><span data-stu-id="90013-151">Binary (base 2)</span></span>|`0B`|<span data-ttu-id="90013-152">0-1</span><span class="sxs-lookup"><span data-stu-id="90013-152">0-1</span></span>|`&B01111100`|
|<span data-ttu-id="90013-153">8진수</span><span class="sxs-lookup"><span data-stu-id="90013-153">Octal (base 8)</span></span>|`&O`|<span data-ttu-id="90013-154">0-7</span><span class="sxs-lookup"><span data-stu-id="90013-154">0-7</span></span>|`&O77`|

<span data-ttu-id="90013-155">Visual Basic 2017 년부터 밑줄만 사용할 수 있습니다 (`_`) 정수 계열 리터럴의 가독성 향상을 위해 그룹 구분 기호로 합니다.</span><span class="sxs-lookup"><span data-stu-id="90013-155">Starting in Visual Basic 2017, you can use the underscore character (`_`) as a group separator to enhance the readability of an integral literal.</span></span> <span data-ttu-id="90013-156">사용 하 여 다음 예제는 `_` 문자 리터럴 이진 8 비트 그룹으로 그룹화입니다.</span><span class="sxs-lookup"><span data-stu-id="90013-156">The following example uses the `_` character to group a binary literal into 8-bit groups:</span></span>

```vb
Dim number As Integer = &B00100010_11000101_11001111_11001101
```

<span data-ttu-id="90013-157">접두사가 붙은 리터럴 형식 문자 리터럴을 따를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90013-157">You can follow a prefixed literal with a literal type character.</span></span> <span data-ttu-id="90013-158">다음 예제에서는이 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="90013-158">The following example shows this.</span></span>

```vb
Dim counter As Short = &H8000S
Dim flags As UShort = &H8000US
```

<span data-ttu-id="90013-159">이전 예에서 `counter` -32768 10 진수 값 및 `flags` 에 10 진수 값 + 32768을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="90013-159">In the previous example, `counter` has the decimal value of -32768, and `flags` has the decimal value of +32768.</span></span>

<span data-ttu-id="90013-160">Visual Basic 15.5 부터는 사용할 수도 있습니다는 밑줄 문자 (`_`)는 접두사와 16 진수, 이진 또는 8 진수 숫자 사이의 선행 구분 기호로 합니다.</span><span class="sxs-lookup"><span data-stu-id="90013-160">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="90013-161">예:</span><span class="sxs-lookup"><span data-stu-id="90013-161">For example:</span></span>

```vb
Dim number As Integer = &H_C305_F860
```

[!INCLUDE [supporting-underscores](../../../../../includes/vb-separator-langversion.md)]

## <a name="see-also"></a><span data-ttu-id="90013-162">참고 항목</span><span class="sxs-lookup"><span data-stu-id="90013-162">See Also</span></span>

 [<span data-ttu-id="90013-163">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="90013-163">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [<span data-ttu-id="90013-164">기본 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="90013-164">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [<span data-ttu-id="90013-165">값 형식과 참조 형식</span><span class="sxs-lookup"><span data-stu-id="90013-165">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [<span data-ttu-id="90013-166">Visual Basic의 형식 변환</span><span class="sxs-lookup"><span data-stu-id="90013-166">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [<span data-ttu-id="90013-167">데이터 형식 문제 해결</span><span class="sxs-lookup"><span data-stu-id="90013-167">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [<span data-ttu-id="90013-168">변수 선언</span><span class="sxs-lookup"><span data-stu-id="90013-168">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [<span data-ttu-id="90013-169">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="90013-169">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/data-type-summary.md)
