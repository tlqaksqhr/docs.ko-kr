---
title: "SByte 데이터 형식(Visual Basic)"
ms.date: 04/20/2017
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.sbyte
helpviewer_keywords:
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- SByte data type
ms.assetid: 5c38374a-18a1-4cc2-b493-299e3dcaa60f
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d391d7eea27ec7696dbb4c28da8916c744712f32
ms.sourcegitcommit: d2da0142247ef42a219a5d2907f153e62dc6ea0d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/01/2018
---
# <a name="sbyte-data-type-visual-basic"></a><span data-ttu-id="6413f-102">SByte 데이터 형식 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6413f-102">SByte data type (Visual Basic)</span></span>

<span data-ttu-id="6413f-103">부호 있는 8 비트 (1 바이트) 정수 값 범위에 있는-128에서 127 까지의 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="6413f-103">Holds signed 8-bit (1-byte) integers that range in value from -128 through 127.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6413f-104">설명</span><span class="sxs-lookup"><span data-stu-id="6413f-104">Remarks</span></span>

<span data-ttu-id="6413f-105">사용 하 여는 `SByte` 의 데이터를 전체 너비가 필요 하지 않은 정수 값을 포함 하는 데이터 형식을 `Integer` 의 절반 데이터 너비 또는 `Short`합니다.</span><span class="sxs-lookup"><span data-stu-id="6413f-105">Use the `SByte` data type to contain integer values that do not require the full data width of `Integer` or even the half data width of `Short`.</span></span> <span data-ttu-id="6413f-106">경우에 따라 공용 언어 런타임 압축할 수 있습니다 프로그램 `SByte` 변수 긴밀 한 협력을 및 메모리 소비를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="6413f-106">In some cases, the common language runtime might be able to pack your `SByte` variables closely together and save memory consumption.</span></span>

<span data-ttu-id="6413f-107">`SByte`의 기본값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="6413f-107">The default value of `SByte` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="6413f-108">리터럴 할당</span><span class="sxs-lookup"><span data-stu-id="6413f-108">Literal assignments</span></span>
  
<span data-ttu-id="6413f-109">선언 하 고 초기화는 `SByte` 10 진 리터럴, 16 진수 리터럴을 8 진수 리터럴을 할당 (부터는 Visual Basic 2017) 이진 리터럴 또는 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="6413f-109">You can declare and initialize an `SByte` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span>

<span data-ttu-id="6413f-110">다음 예제에서는 정수 같지-102 10 진수, 16 진수로 표현 되는 및에 할당 된 이진 리터럴 `SByte` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="6413f-110">In the following example, integers equal to -102 that are represented as decimal, hexadecimal, and binary literals are assigned to `SByte` values.</span></span> <span data-ttu-id="6413f-111">이 예제에서는 사용 하 여 컴파일하는 `/removeintchecks` 컴파일러 스위치입니다.</span><span class="sxs-lookup"><span data-stu-id="6413f-111">This example requires that you compile with the `/removeintchecks` compiler switch.</span></span>

[!code-vb[SByte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByte)]  

> [!NOTE] 
> <span data-ttu-id="6413f-112">접두사를 사용 `&h` 또는 `&H` 를 나타내는 16 진수 리터럴을, 접두사 `&b` 또는 `&B` 이진 리터럴와 접두사를 나타내기 위해 `&o` 또는 `&O` 8 진수 리터럴을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6413f-112">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="6413f-113">10진수 리터럴에는 접두사가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6413f-113">Decimal literals have no prefix.</span></span>

<span data-ttu-id="6413f-114">Visual Basic 2017 부터는 사용할 수도 있습니다는 밑줄 문자 `_`, 가독성을 향상 시키기 위해 숫자 구분 기호,으로 다음 예제와 같이 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6413f-114">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[SByteSeparator](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByteS)]  

<span data-ttu-id="6413f-115">Visual Basic 15.5 부터는 사용할 수도 있습니다는 밑줄 문자 (`_`)는 접두사와 16 진수, 이진 또는 8 진수 숫자 사이의 선행 구분 기호로 합니다.</span><span class="sxs-lookup"><span data-stu-id="6413f-115">Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits.</span></span> <span data-ttu-id="6413f-116">예:</span><span class="sxs-lookup"><span data-stu-id="6413f-116">For example:</span></span>

```vb
Dim number As SByte = &H_F9
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

<span data-ttu-id="6413f-117">정수 리터럴이 `SByte` 범위를 벗어나는 경우(즉 <xref:System.SByte.MinValue?displayProperty=nameWithType>보다 작거나 <xref:System.SByte.MaxValue?displayProperty=nameWithType>보다 큰 경우) 컴파일 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="6413f-117">If the integer literal is outside the range of `SByte` (that is, if it is less than <xref:System.SByte.MinValue?displayProperty=nameWithType> or greater than <xref:System.SByte.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span> <span data-ttu-id="6413f-118">정수 리터럴 접미사가 없는 [정수](integer-data-type.md) 유추 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6413f-118">When an integer literal has no suffix, an [Integer](integer-data-type.md) is inferred.</span></span> <span data-ttu-id="6413f-119">정수 리터럴이의 범위를 벗어나는 경우는 `Integer` 종류는 [긴](long-data-type.md) 유추 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6413f-119">If the integer literal is outside the range of the `Integer` type, a [Long](long-data-type.md) is inferred.</span></span> <span data-ttu-id="6413f-120">즉, 이전 예제에서는 숫자 리터럴 `0x9A` 및 `0b10011010` 초과 하는 값의 156, 32 비트 부호 있는 정수로 해석 <xref:System.SByte.MaxValue?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="6413f-120">This means that, in the previous examples, the numeric literals `0x9A` and `0b10011010` are interpreted as 32-bit signed integers with a value of 156, which exceeds <xref:System.SByte.MaxValue?displayProperty=nameWithType>.</span></span> <span data-ttu-id="6413f-121">성공적으로 10 진수가 아닌 정수를 할당 하는 다음과 같은 코드를 컴파일하려면는 `SByte`, 다음 중 하나를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6413f-121">To successfully compile code like this that assigns a non-decimal integer to an `SByte`, you can do either of the following:</span></span>

- <span data-ttu-id="6413f-122">사용 하 여 컴파일하면 정수 범위 검사를 사용 하지 않도록 설정 된 `/removeintchecks` 컴파일러 스위치입니다.</span><span class="sxs-lookup"><span data-stu-id="6413f-122">Disable integer bounds checks by compiling with the `/removeintchecks` compiler switch.</span></span>

- <span data-ttu-id="6413f-123">사용 하 여 한 [형식 문자](../../programming-guide\language-features\data-types/type-characters.md) 을 할당할 리터럴 값을 명시적으로 정의 하는 `SByte`합니다.</span><span class="sxs-lookup"><span data-stu-id="6413f-123">Use a [type character](../../programming-guide\language-features\data-types/type-characters.md) to explicitly define the literal value that you want to assign to the `SByte`.</span></span> <span data-ttu-id="6413f-124">다음 예제에서는 할당 음수 리터럴 `Short` 값을 `SByte`합니다.</span><span class="sxs-lookup"><span data-stu-id="6413f-124">The following example assigns a negative literal `Short` value to an `SByte`.</span></span> <span data-ttu-id="6413f-125">유의 음수에 대 한, 숫자 리터럴 상위 단어의 상위 비트를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6413f-125">Note that, for negative numbers, the high-order bit of the high-order word of the numeric literal must be set.</span></span> <span data-ttu-id="6413f-126">이 예제의 경우이 비트 리터럴 15 `Short` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="6413f-126">In the case of our example, this is bit 15 of the literal `Short` value.</span></span>

   [!code-vb[SByteTypeChars](../../../../samples/snippets/visualbasic/language-reference/data-types/sbyte-assignment.vb#1)]

## <a name="programming-tips"></a><span data-ttu-id="6413f-127">프로그래밍 팁</span><span class="sxs-lookup"><span data-stu-id="6413f-127">Programming tips</span></span>
  
-   <span data-ttu-id="6413f-128">**CLS 규격입니다.**</span><span class="sxs-lookup"><span data-stu-id="6413f-128">**CLS Compliance.**</span></span> <span data-ttu-id="6413f-129">`SByte` 데이터 형식이 아니므로의 일부가 [공용 언어 사양](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), 지므로 CLS 규격 코드를 사용 하는 구성 요소를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6413f-129">The `SByte` data type is not part of the [Common Language Specification](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>

-   <span data-ttu-id="6413f-130">**확대 합니다.**</span><span class="sxs-lookup"><span data-stu-id="6413f-130">**Widening.**</span></span> <span data-ttu-id="6413f-131">`SByte` 데이터 형식으로 확대 되 `Short`, `Integer`, `Long`, `Decimal`, `Single`, 및 `Double`합니다.</span><span class="sxs-lookup"><span data-stu-id="6413f-131">The `SByte` data type widens to `Short`, `Integer`, `Long`, `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="6413f-132">즉, 변환할 수 `SByte` 발생 없이 이러한 유형 중 하나로 <xref:System.OverflowException?displayProperty=nameWithType> 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="6413f-132">This means you can convert `SByte` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>
  
-   <span data-ttu-id="6413f-133">**형식 문자입니다.**</span><span class="sxs-lookup"><span data-stu-id="6413f-133">**Type Characters.**</span></span> <span data-ttu-id="6413f-134">`SByte`에 리터럴 형식 문자 또는 식별자 형식 문자가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6413f-134">`SByte` has no literal type character or identifier type character.</span></span>  
  
-   <span data-ttu-id="6413f-135">**Framework 형식입니다.**</span><span class="sxs-lookup"><span data-stu-id="6413f-135">**Framework Type.**</span></span> <span data-ttu-id="6413f-136">.NET Framework에서 해당하는 형식은 <xref:System.SByte?displayProperty=nameWithType> 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="6413f-136">The corresponding type in the .NET Framework is the <xref:System.SByte?displayProperty=nameWithType> structure.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6413f-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6413f-137">See also</span></span>

 <xref:System.SByte?displayProperty=nameWithType>  
 [<span data-ttu-id="6413f-138">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="6413f-138">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="6413f-139">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="6413f-139">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="6413f-140">변환 요약</span><span class="sxs-lookup"><span data-stu-id="6413f-140">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="6413f-141">Short 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="6413f-141">Short Data Type</span></span>](../../../visual-basic/language-reference/data-types/short-data-type.md)  
 [<span data-ttu-id="6413f-142">Integer 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="6413f-142">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)  
 [<span data-ttu-id="6413f-143">Long 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="6413f-143">Long Data Type</span></span>](../../../visual-basic/language-reference/data-types/long-data-type.md)  
 [<span data-ttu-id="6413f-144">데이터 형식의 효율적 사용</span><span class="sxs-lookup"><span data-stu-id="6413f-144">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
