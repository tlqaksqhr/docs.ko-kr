---
title: "UInteger 데이터 형식"
ms.date: 04/20/2017
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.uinteger
helpviewer_keywords:
- numbers [Visual Basic], whole
- UInteger data type
- literal type characters [Visual Basic], UI
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- UI literal type characters [Visual Basic]
- data types [Visual Basic], integral
ms.assetid: db7ddd34-4f23-46f5-84dd-8b0f83bb8729
caps.latest.revision: "19"
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3f3852bd56d11c19e327e6c2f3e23cfb082a54e0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="uinteger-data-type"></a><span data-ttu-id="5d275-102">UInteger 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="5d275-102">UInteger data type</span></span>

<span data-ttu-id="5d275-103">값은 0에서 4294967295 까지의 부호 없는 32 비트 (4 바이트) 정수를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d275-103">Holds unsigned 32-bit (4-byte) integers ranging in value from 0 through 4,294,967,295.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5d275-104">설명</span><span class="sxs-lookup"><span data-stu-id="5d275-104">Remarks</span></span>

 <span data-ttu-id="5d275-105">`UInteger` 데이터 형식은 가장 효율적인 데이터 너비의 부호 없는 큰 값을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d275-105">The `UInteger` data type provides the largest unsigned value in the most efficient data width.</span></span>  
  
 <span data-ttu-id="5d275-106">`UInteger`의 기본값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="5d275-106">The default value of `UInteger` is 0.</span></span>  
  
## <a name="literal-assignments"></a><span data-ttu-id="5d275-107">리터럴 할당</span><span class="sxs-lookup"><span data-stu-id="5d275-107">Literal assignments</span></span>

<span data-ttu-id="5d275-108">선언 하 고 초기화는 `UInteger` 10 진 리터럴, 16 진수 리터럴을 8 진수 리터럴을 할당 (부터는 Visual Basic 2017) 이진 리터럴 또는 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="5d275-108">You can declare and initialize a `UInteger` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal.</span></span> <span data-ttu-id="5d275-109">정수 리터럴이 `UInteger` 범위를 벗어나는 경우(즉 <xref:System.UInt32.MinValue?displayProperty=nameWithType>보다 작거나 <xref:System.UInt32.MaxValue?displayProperty=nameWithType>보다 큰 경우) 컴파일 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="5d275-109">If the integer literal is outside the range of `UInteger` (that is, if it is less than <xref:System.UInt32.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt32.MaxValue?displayProperty=nameWithType>, a compilation error occurs.</span></span>

<span data-ttu-id="5d275-110">다음 예제에서는 10진수, 16진수 및 이진 리터럴로 표현된 3,000,000,000과 같은 정수가 `UInteger` 값에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d275-110">In the following example, integers equal to 3,000,000,000 that are represented as decimal, hexadecimal, and binary literals are assigned to `UInteger` values.</span></span>
  
[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UInt)]  

> [!NOTE] 
> <span data-ttu-id="5d275-111">접두사를 사용 `&h` 또는 `&H` 를 나타내는 16 진수 리터럴을, 접두사 `&b` 또는 `&B` 이진 리터럴와 접두사를 나타내기 위해 `&o` 또는 `&O` 8 진수 리터럴을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5d275-111">You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal.</span></span> <span data-ttu-id="5d275-112">10진수 리터럴에는 접두사가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5d275-112">Decimal literals have no prefix.</span></span>

<span data-ttu-id="5d275-113">Visual Basic 2017 부터는 사용할 수도 있습니다는 밑줄 문자 `_`, 가독성을 향상 시키기 위해 숫자 구분 기호,으로 다음 예제와 같이 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5d275-113">Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.</span></span>

[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UIntS)]  

<span data-ttu-id="5d275-114">숫자 리터럴을 포함할 수는 `UI` 또는 `ui` [형식 문자](../../programming-guide\language-features\data-types/type-characters.md) 를 표시 하는 `UInteger` 다음 예제와 같이 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5d275-114">Numeric literals can also include the `UI` or `ui` [type character](../../programming-guide\language-features\data-types/type-characters.md) to denote the `UInteger` data type, as the following example shows.</span></span>

```vb
Dim number = &H0FAC14D7ui
```

## <a name="programming-tips"></a><span data-ttu-id="5d275-115">프로그래밍 팁</span><span class="sxs-lookup"><span data-stu-id="5d275-115">Programming tips</span></span>

 <span data-ttu-id="5d275-116">`UInteger` 및 `Integer` 데이터 형식 때문에 32 비트 프로세서에서 최적의 성능을 제공 작은 정수 형식 (`UShort`, `Short`, `Byte`, 및 `SByte`) 사용 하는 비트 수가, 시간이 더 길어집니다 로드, 저장 및 인출 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d275-116">The `UInteger` and `Integer` data types provide optimal performance on a 32-bit processor, because the smaller integer types (`UShort`, `Short`, `Byte`, and `SByte`), even though they use fewer bits, take more time to load, store, and fetch.</span></span>  
  
-   <span data-ttu-id="5d275-117">**음수입니다.**</span><span class="sxs-lookup"><span data-stu-id="5d275-117">**Negative Numbers.**</span></span> <span data-ttu-id="5d275-118">때문에 `UInteger` 부호 없는 정수 형식이 면 음수를 나타낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5d275-118">Because `UInteger` is an unsigned type, it cannot represent a negative number.</span></span> <span data-ttu-id="5d275-119">단항 빼기를 사용 하는 경우 (`-`) 형식으로 계산 되는 식에 연산자 `UInteger`, Visual Basic 식을 변환 `Long` 첫 번째입니다.</span><span class="sxs-lookup"><span data-stu-id="5d275-119">If you use the unary minus (`-`) operator on an expression that evaluates to type `UInteger`, Visual Basic converts the expression to `Long` first.</span></span>  
  
-   <span data-ttu-id="5d275-120">**CLS 규격입니다.**</span><span class="sxs-lookup"><span data-stu-id="5d275-120">**CLS Compliance.**</span></span> <span data-ttu-id="5d275-121">`UInteger` 데이터 형식이 아니므로의 일부가 [공용 언어 사양](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), 지므로 CLS 규격 코드를 사용 하는 구성 요소를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5d275-121">The `UInteger` data type is not part of the [Common Language Specification](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), so CLS-compliant code cannot consume a component that uses it.</span></span>
  
-   <span data-ttu-id="5d275-122">**Interop 고려 사항입니다.**</span><span class="sxs-lookup"><span data-stu-id="5d275-122">**Interop Considerations.**</span></span> <span data-ttu-id="5d275-123">Automation 또는 COM 개체를 위한.NET Framework에 대해 작성 되지 않은 구성 요소와 상호 작용 하는 경우 유의 같은 형식은 `uint` 다른 환경에서 다른 데이터 너비 (16 비트)를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d275-123">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that types such as `uint` can have a different data width (16 bits) in other environments.</span></span> <span data-ttu-id="5d275-124">이러한 구성 요소를 16 비트 인수를 전달 하는 경우로 선언 `UShort` 대신 `UInteger` 관리 되는 Visual Basic 코드에서.</span><span class="sxs-lookup"><span data-stu-id="5d275-124">If you are passing a 16-bit argument to such a component, declare it as `UShort` instead of `UInteger` in your managed Visual Basic code.</span></span>  
  
-   <span data-ttu-id="5d275-125">**확대 합니다.**</span><span class="sxs-lookup"><span data-stu-id="5d275-125">**Widening.**</span></span> <span data-ttu-id="5d275-126">`UInteger` 데이터 형식으로 확대 되 `Long`, `ULong`, `Decimal`, `Single`, 및 `Double`합니다.</span><span class="sxs-lookup"><span data-stu-id="5d275-126">The `UInteger` data type widens to `Long`, `ULong`, `Decimal`, `Single`, and `Double`.</span></span> <span data-ttu-id="5d275-127">즉, 변환할 수 `UInteger` 발생 없이 이러한 유형 중 하나로 <xref:System.OverflowException?displayProperty=nameWithType> 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="5d275-127">This means you can convert `UInteger` to any of these types without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
-   <span data-ttu-id="5d275-128">**형식 문자입니다.**</span><span class="sxs-lookup"><span data-stu-id="5d275-128">**Type Characters.**</span></span> <span data-ttu-id="5d275-129">리터럴 형식 문자를 추가 `UI` 리터럴에 리터럴에 `UInteger` 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5d275-129">Appending the literal type characters `UI` to a literal forces it to the `UInteger` data type.</span></span> <span data-ttu-id="5d275-130">`UInteger`에 식별자 형식 문자가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5d275-130">`UInteger` has no identifier type character.</span></span>  
  
-   <span data-ttu-id="5d275-131">**Framework 형식입니다.**</span><span class="sxs-lookup"><span data-stu-id="5d275-131">**Framework Type.**</span></span> <span data-ttu-id="5d275-132">.NET Framework에서 해당하는 형식은 <xref:System.UInt32?displayProperty=nameWithType> 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="5d275-132">The corresponding type in the .NET Framework is the <xref:System.UInt32?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d275-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5d275-133">See Also</span></span>  
 <xref:System.UInt32>  
 [<span data-ttu-id="5d275-134">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="5d275-134">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="5d275-135">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="5d275-135">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="5d275-136">변환 요약</span><span class="sxs-lookup"><span data-stu-id="5d275-136">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="5d275-137">방법: 부호 없는 형식을 사용하는 Windows 함수 호출</span><span class="sxs-lookup"><span data-stu-id="5d275-137">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)  
 [<span data-ttu-id="5d275-138">데이터 형식의 효율적 사용</span><span class="sxs-lookup"><span data-stu-id="5d275-138">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
