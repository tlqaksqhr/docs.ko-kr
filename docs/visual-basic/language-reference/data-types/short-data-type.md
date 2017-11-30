---
title: "Short 데이터 형식(Visual Basic)"
ms.date: 04/20/2017
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
author: rpetrusha
ms.author: ronpet
f1_keywords: vb.Short
helpviewer_keywords:
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- S literal type character [Visual Basic]
- Short data type
- literal type characters [Visual Basic], S
ms.assetid: 65fcbcf3-a841-400e-885e-301497729a8b
ms.openlocfilehash: fef948debed69cf9fb7b0e6bb65eb0ddbe497a92
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="short-data-type-visual-basic"></a><span data-ttu-id="a73df-102">Short 데이터 형식 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a73df-102">Short data type (Visual Basic)</span></span>
<span data-ttu-id="a73df-103">부호 있는 16 비트 (2 바이트) 정수 값 범위에 있는-32, 768에서 32, 767 까지의 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="a73df-103">Holds signed 16-bit (2-byte) integers that range in value from -32,768 through 32,767.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a73df-104">설명</span><span class="sxs-lookup"><span data-stu-id="a73df-104">Remarks</span></span>  
 <span data-ttu-id="a73df-105">사용 하 여는 `Short` 데이터 형식으로의 데이터를 전체 너비가 필요 하지 않은 정수 값을 저장할 `Integer`합니다.</span><span class="sxs-lookup"><span data-stu-id="a73df-105">Use the `Short` data type to contain integer values that do not require the full data width of `Integer`.</span></span> <span data-ttu-id="a73df-106">경우에 따라 공용 언어 런타임 압축할 수 있습니다 프로그램 `Short` 변수 긴밀 한 협력을 및 메모리 소비를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="a73df-106">In some cases, the common language runtime can pack your `Short` variables closely together and save memory consumption.</span></span>  
  
 <span data-ttu-id="a73df-107">`Short`의 기본값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="a73df-107">The default value of `Short` is 0.</span></span>  
  
## <a name="literal-assignments"></a><span data-ttu-id="a73df-108">리터럴 할당</span><span class="sxs-lookup"><span data-stu-id="a73df-108">Literal assignments</span></span>

<span data-ttu-id="a73df-109">선언 하 고 초기화는 `Short` 10 진 리터럴, 16 진수 리터럴을 8 진수 리터럴을 할당 (부터는 Visual Basic 2017) 이진 리터럴 또는 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="a73df-109">You can declare and initialize a `Short` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="a73df-110">정수 리터럴이 `Short` 범위를 벗어나는 경우(즉 <xref:System.Int16.MinValue?displayProperty=nameWithType>보다 작거나 <xref:System.Int16.MaxValue?displayProperty=nameWithType>보다 큰 경우) 컴파일 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="a73df-110">If the integer literal is outside the range of `Short` (that is, if it is less than <xref:System.Int16.MinValue?displayProperty=nameWithType> or greater than <xref:System.Int16.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="a73df-111">다음 예제에서는 정수 같지 1,034 표현 되는 10 진수, 16 진수 및 이진 리터럴에서 암시적으로 변환 된 [정수](integer-data-type.md) 를 `Short` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="a73df-111">In the following example, integers equal to 1,034 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [Integer](integer-data-type.md) to `Short` values.</span></span>

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Short)]

> [!NOTE]
> <span data-ttu-id="a73df-112">접두사를 사용 `&h` 또는 `&H` 를 나타내는 16 진수 리터럴을, 접두사 `&b` 또는 `&B` 이진 리터럴와 접두사를 나타내기 위해 `&o` 또는 `&O` 8 진수 리터럴을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a73df-112">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="a73df-113">10진수 리터럴에는 접두사가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a73df-113">Decimal literals have no prefix.</span></span>

<span data-ttu-id="a73df-114">Visual Basic 2017 부터는 사용할 수도 있습니다는 밑줄 문자 `_`, 가독성을 향상 시키기 위해 숫자 구분 기호,으로 다음 예제와 같이 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a73df-114">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ShortS)]

<span data-ttu-id="a73df-115">숫자 리터럴을 포함할 수는 `S` [형식 문자](../../programming-guide\language-features\data-types/type-characters.md) 를 표시 하는 `Short` 다음 예제와 같이 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a73df-115">Numeric literals can also include the `S` [type character](../../programming-guide\language-features\data-types/type-characters.md) to denote the `Short` data type, as the following example shows.</span></span>

```vb
Dim number = &H0326S
```

## <a name="programming-tips"></a><span data-ttu-id="a73df-116">프로그래밍 팁</span><span class="sxs-lookup"><span data-stu-id="a73df-116">Programming tips</span></span>

-   <span data-ttu-id="a73df-117">**확대 합니다.**</span><span class="sxs-lookup"><span data-stu-id="a73df-117">**Widening.**</span></span> <span data-ttu-id="a73df-118">`Short` 데이터 형식으로 확대 되 `Integer`, `Long`, `Decimal`, `Single`, 또는 `Double`합니다.</span><span class="sxs-lookup"><span data-stu-id="a73df-118">The `Short` data type widens to `Integer`, `Long`, `Decimal`, `Single`, or `Double`.</span></span> <span data-ttu-id="a73df-119">이는 `Short` 오류 발생 없이 <xref:System.OverflowException?displayProperty=nameWithType>를 이러한 형식 중 하나로 변환할 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="a73df-119">This means you can convert `Short` to any one of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
-   <span data-ttu-id="a73df-120">**형식 문자입니다.**</span><span class="sxs-lookup"><span data-stu-id="a73df-120">**Type Characters.**</span></span> <span data-ttu-id="a73df-121">리터럴 형식 문자 `S`를 리터럴에 추가하면 `Short` 데이터 형식이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a73df-121">Appending the literal type character `S` to a literal forces it to the `Short` data type.</span></span> <span data-ttu-id="a73df-122">`Short`에 식별자 형식 문자가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a73df-122">`Short` has no identifier type character.</span></span>  
  
-   <span data-ttu-id="a73df-123">**Framework 형식입니다.**</span><span class="sxs-lookup"><span data-stu-id="a73df-123">**Framework Type.**</span></span> <span data-ttu-id="a73df-124">.NET Framework에서 해당하는 형식은 <xref:System.Int16?displayProperty=nameWithType> 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="a73df-124">The corresponding type in the .NET Framework is the <xref:System.Int16?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a73df-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a73df-125">See also</span></span>

 <xref:System.Int16?displayProperty=nameWithType>  
 [<span data-ttu-id="a73df-126">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="a73df-126">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="a73df-127">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="a73df-127">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="a73df-128">변환 요약</span><span class="sxs-lookup"><span data-stu-id="a73df-128">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="a73df-129">Integer 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="a73df-129">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)  
 [<span data-ttu-id="a73df-130">Long 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="a73df-130">Long Data Type</span></span>](../../../visual-basic/language-reference/data-types/long-data-type.md)  
 [<span data-ttu-id="a73df-131">데이터 형식의 효율적 사용</span><span class="sxs-lookup"><span data-stu-id="a73df-131">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
