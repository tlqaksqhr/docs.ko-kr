---
title: "ULong 데이터 형식(Visual Basic)"
ms.date: 04/20/2017
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.ulong
helpviewer_keywords:
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- literal type characters [Visual Basic], UL
- ULong data type
- UL literal type characters [Visual Basic]
ms.assetid: 017e0702-774e-44ae-bedc-786b424ca84e
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: afc52bfd16541feed599d5445adad7aba04f8e9d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ulong-data-type-visual-basic"></a><span data-ttu-id="8bf63-102">ULong 데이터 형식 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8bf63-102">ULong data type (Visual Basic)</span></span>

<span data-ttu-id="8bf63-103">값은 0에서 18446744073709551615 까지의 부호 없는 64 비트 (8 바이트) 정수를 포함 (1.84 이상 10 ^19).</span><span class="sxs-lookup"><span data-stu-id="8bf63-103">Holds unsigned 64-bit (8-byte) integers ranging in value from 0 through 18,446,744,073,709,551,615 (more than 1.84 times 10 ^ 19).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8bf63-104">설명</span><span class="sxs-lookup"><span data-stu-id="8bf63-104">Remarks</span></span>

<span data-ttu-id="8bf63-105">사용 하 여는 `ULong` 데이터 형식에 대해 너무 큰 이진 데이터를 포함 하도록 `UInteger`, 가장 큰 부호 없는 정수 값 또는 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bf63-105">Use the `ULong` data type to contain binary data too large for `UInteger`, or the largest possible unsigned integer values.</span></span>  
  
<span data-ttu-id="8bf63-106">`ULong`의 기본값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="8bf63-106">The default value of `ULong` is 0.</span></span>

## <a name="literal-assignments"></a><span data-ttu-id="8bf63-107">리터럴 할당</span><span class="sxs-lookup"><span data-stu-id="8bf63-107">Literal assignments</span></span>

<span data-ttu-id="8bf63-108">선언 하 고 초기화는 `ULong` 10 진 리터럴, 16 진수 리터럴을 8 진수 리터럴을 할당 (부터는 Visual Basic 2017) 이진 리터럴 또는 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="8bf63-108">You can declare and initialize a `ULong` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="8bf63-109">정수 리터럴이 `ULong` 범위를 벗어나는 경우(즉 <xref:System.UInt64.MinValue?displayProperty=nameWithType>보다 작거나 <xref:System.UInt64.MaxValue?displayProperty=nameWithType>보다 큰 경우) 컴파일 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="8bf63-109">If the integer literal is outside the range of `ULong` (that is, if it is less than <xref:System.UInt64.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="8bf63-110">다음 예제에서는 10진수, 16진수 및 이진 리터럴로 표현된 7,934,076,125와 같은 정수가 `ULong` 값에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bf63-110">In the following example, integers equal to 7,934,076,125 that are represented as decimal, hexadecimal, and binary literals are assigned to `ULong` values.</span></span>
  
[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ULong)]

> [!NOTE] 
> <span data-ttu-id="8bf63-111">접두사를 사용 `&h` 또는 `&H` 를 나타내는 16 진수 리터럴을, 접두사 `&b` 또는 `&B` 이진 리터럴와 접두사를 나타내기 위해 `&o` 또는 `&O` 8 진수 리터럴을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8bf63-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="8bf63-112">10진수 리터럴에는 접두사가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8bf63-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="8bf63-113">Visual Basic 2017 부터는 사용할 수도 있습니다는 밑줄 문자 `_`, 가독성을 향상 시키기 위해 숫자 구분 기호,으로 다음 예제와 같이 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8bf63-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

<span data-ttu-id="8bf63-114">숫자 리터럴을 포함할 수는 `UL` 또는 `ul` [형식 문자](../../programming-guide\language-features\data-types/type-characters.md) 를 표시 하는 `ULong` 다음 예제와 같이 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="8bf63-114">Numeric literals can also include the `UL` or `ul` [type character](../../programming-guide\language-features\data-types/type-characters.md) to denote the `ULong` data type, as the following example shows.</span></span>

```vb
Dim number = &H00_00_0A_96_2F_AC_14_D7ul
```

## <a name="programming-tips"></a><span data-ttu-id="8bf63-115">프로그래밍 팁</span><span class="sxs-lookup"><span data-stu-id="8bf63-115">Programming tips</span></span>
  
-   <span data-ttu-id="8bf63-116">**음수입니다.**</span><span class="sxs-lookup"><span data-stu-id="8bf63-116">**Negative Numbers.**</span></span> <span data-ttu-id="8bf63-117">때문에 `ULong` 부호 없는 정수 형식이 면 음수를 나타낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8bf63-117">Because `ULong` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="8bf63-118">단항 빼기를 사용 하는 경우 (`-`) 형식으로 계산 되는 식에 연산자 `ULong`, Visual Basic 식을 변환 `Decimal` 첫 번째입니다.</span><span class="sxs-lookup"><span data-stu-id="8bf63-118">If you use the unary minus (`-`) operator on an expression that evaluates to type `ULong`, Visual Basic converts the expression to `Decimal` first.</span></span>  
  
-   <span data-ttu-id="8bf63-119">**CLS 규격입니다.**</span><span class="sxs-lookup"><span data-stu-id="8bf63-119">**CLS Compliance.**</span></span> <span data-ttu-id="8bf63-120">`ULong` 데이터 형식이 아니므로의 일부가 [공용 언어 사양](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), 지므로 CLS 규격 코드를 사용 하는 구성 요소를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8bf63-120">The `ULong` data type is not part of the [Common Language Specification](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>  
  
-   <span data-ttu-id="8bf63-121">**Interop 고려 사항입니다.**</span><span class="sxs-lookup"><span data-stu-id="8bf63-121">**Interop Considerations.**</span></span> <span data-ttu-id="8bf63-122">Automation 또는 COM 개체를 위한.NET Framework에 대해 작성 되지 않은 구성 요소와 상호 작용 하는 경우 유의 같은 형식은 `ulong` 다른 환경에서 다른 데이터 너비 (32 비트)를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bf63-122">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that types such as `ulong` can have a different data width (32 bits) in other environments.</span></span> <span data-ttu-id="8bf63-123">이러한 구성 요소를 32 비트 인수를 전달 하는 경우로 선언 `UInteger` 대신 `ULong` 관리 되는 Visual Basic 코드에서.</span><span class="sxs-lookup"><span data-stu-id="8bf63-123">If you are passing a 32-bit argument to such a component, declare it as `UInteger` instead of `ULong` in your managed Visual Basic code.</span></span>  
  
     <span data-ttu-id="8bf63-124">또한 자동화는 Windows 95, Windows 98, Windows ME 또는 Windows 2000에서 64 비트 정수를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8bf63-124">Furthermore, Automation does not support 64-bit integers on Windows 95, Windows 98, Windows ME, or Windows 2000.</span></span> <span data-ttu-id="8bf63-125">Visual Basic을 전달할 수 없으며 `ULong` 이러한 플랫폼에서 자동화 구성 요소에 대 한 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="8bf63-125">You cannot pass a Visual Basic `ULong` argument to an Automation component on these platforms.</span></span>  
  
-   <span data-ttu-id="8bf63-126">**확대 합니다.**</span><span class="sxs-lookup"><span data-stu-id="8bf63-126">**Widening.**</span></span> <span data-ttu-id="8bf63-127">`ULong` 데이터 형식으로 확대 되 `Decimal`, `Single`, 및 `Double`합니다.</span><span class="sxs-lookup"><span data-stu-id="8bf63-127">The `ULong` data type widens to `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="8bf63-128">즉, 변환할 수 `ULong` 발생 없이 이러한 유형 중 하나로 <xref:System.OverflowException?displayProperty=nameWithType> 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="8bf63-128">This means you can convert `ULong` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
-   <span data-ttu-id="8bf63-129">**형식 문자입니다.**</span><span class="sxs-lookup"><span data-stu-id="8bf63-129">**Type Characters.**</span></span> <span data-ttu-id="8bf63-130">리터럴 형식 문자를 추가 `UL` 리터럴에 리터럴에 `ULong` 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="8bf63-130">Appending the literal type characters `UL` to a literal forces it to the `ULong` data type.</span></span> <span data-ttu-id="8bf63-131">`ULong`에 식별자 형식 문자가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8bf63-131">`ULong` has no identifier type character.</span></span>
  
-   <span data-ttu-id="8bf63-132">**Framework 형식입니다.**</span><span class="sxs-lookup"><span data-stu-id="8bf63-132">**Framework Type.**</span></span> <span data-ttu-id="8bf63-133">.NET Framework에서 해당하는 형식은 <xref:System.UInt64?displayProperty=nameWithType> 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="8bf63-133">The corresponding type in the .NET Framework is the <xref:System.UInt64?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bf63-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8bf63-134">See also</span></span>

 <xref:System.UInt64>  
 [<span data-ttu-id="8bf63-135">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="8bf63-135">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="8bf63-136">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="8bf63-136">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="8bf63-137">변환 요약</span><span class="sxs-lookup"><span data-stu-id="8bf63-137">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="8bf63-138">방법: 부호 없는 형식을 사용하는 Windows 함수 호출</span><span class="sxs-lookup"><span data-stu-id="8bf63-138">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)  
 [<span data-ttu-id="8bf63-139">데이터 형식의 효율적 사용</span><span class="sxs-lookup"><span data-stu-id="8bf63-139">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
