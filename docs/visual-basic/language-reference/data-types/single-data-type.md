---
title: "Single 데이터 형식(Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Single
helpviewer_keywords:
- Single data type
- F literal type character [Visual Basic]
- trailing zeros
- real numbers
- literal type characters [Visual Basic], F
- trailing 0 characters [Visual Basic]
- identifier type characters [Visual Basic], !
- single-precision numbers
- '! identifier type character'
- 0 characters [Visual Basic], trailing
- data types [Visual Basic], assigning
- floating-point numbers [Visual Basic], Single data type
- numbers [Visual Basic], real
- zeros, trailing
- numbers [Visual Basic], floating point
ms.assetid: 224a2795-4cd5-496c-8f7a-a4f05a06d45d
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c91dbdf73ed1e26393518001ec8651557e5b780f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="single-data-type-visual-basic"></a><span data-ttu-id="2e0b4-102">Single 데이터 형식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2e0b4-102">Single Data Type (Visual Basic)</span></span>
<span data-ttu-id="2e0b4-103">부호 있는 IEEE 32 비트 (4 바이트) 단 정밀도 부동 소수점 숫자 값의 범위가-3.4028235 e + 38에서 저장-1.401298 e을 통해-음수 값 1.401298 e에서 45-45 3.4028235 e + 38 양수 값에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e0b4-103">Holds signed IEEE 32-bit (4-byte) single-precision floating-point numbers ranging in value from -3.4028235E+38 through -1.401298E-45 for negative values and from 1.401298E-45 through 3.4028235E+38 for positive values.</span></span> <span data-ttu-id="2e0b4-104">단 정밀도 수는 실수의 근사값을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e0b4-104">Single-precision numbers store an approximation of a real number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2e0b4-105">설명</span><span class="sxs-lookup"><span data-stu-id="2e0b4-105">Remarks</span></span>  
 <span data-ttu-id="2e0b4-106">사용 하 여는 `Single` 데이터 형식으로의 데이터를 전체 너비가 필요 하지 않은 부동 소수점 값을 저장할 `Double`합니다.</span><span class="sxs-lookup"><span data-stu-id="2e0b4-106">Use the `Single` data type to contain floating-point values that do not require the full data width of `Double`.</span></span> <span data-ttu-id="2e0b4-107">일부 경우에 공용 언어 런타임 압축할 수 있습니다 프로그램 `Single` 변수 긴밀 한 협력을 및 메모리 소비를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e0b4-107">In some cases the common language runtime might be able to pack your `Single` variables closely together and save memory consumption.</span></span>  
  
 <span data-ttu-id="2e0b4-108">`Single`의 기본값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="2e0b4-108">The default value of `Single` is 0.</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="2e0b4-109">프로그래밍 팁</span><span class="sxs-lookup"><span data-stu-id="2e0b4-109">Programming Tips</span></span>  
  
-   <span data-ttu-id="2e0b4-110">**전체 자릿수입니다.**</span><span class="sxs-lookup"><span data-stu-id="2e0b4-110">**Precision.**</span></span> <span data-ttu-id="2e0b4-111">부동 소수점 숫자를 작업할 때는 항상 없는 정확한 표시 메모리에 염두에 둬야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e0b4-111">When you work with floating-point numbers, keep in mind that they do not always have a precise representation in memory.</span></span> <span data-ttu-id="2e0b4-112">값 비교 같은 특정 작업에서 예기치 않은 결과가 발생할 수 및 `Mod` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="2e0b4-112">This could lead to unexpected results from certain operations, such as value comparison and the `Mod` operator.</span></span> <span data-ttu-id="2e0b4-113">자세한 내용은 참조 [데이터 형식 문제 해결](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2e0b4-113">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
-   <span data-ttu-id="2e0b4-114">**확대 합니다.**</span><span class="sxs-lookup"><span data-stu-id="2e0b4-114">**Widening.**</span></span> <span data-ttu-id="2e0b4-115">`Single` 데이터 형식으로 확대 되 `Double`합니다.</span><span class="sxs-lookup"><span data-stu-id="2e0b4-115">The `Single` data type widens to `Double`.</span></span> <span data-ttu-id="2e0b4-116">즉, 변환할 수 `Single` 를 `Double` 발생 없이 <xref:System.OverflowException?displayProperty=nameWithType> 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="2e0b4-116">This means you can convert `Single` to `Double` without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
-   <span data-ttu-id="2e0b4-117">**뒤에 오는 0입니다.**</span><span class="sxs-lookup"><span data-stu-id="2e0b4-117">**Trailing Zeros.**</span></span> <span data-ttu-id="2e0b4-118">부동 소수점 데이터 형식 후행 0 문자의 모든 내부 표현이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2e0b4-118">The floating-point data types do not have any internal representation of trailing 0 characters.</span></span> <span data-ttu-id="2e0b4-119">예를 들어 이러한 구분 하지 않습니다 4.2000 및 4.2 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e0b4-119">For example, they do not distinguish between 4.2000 and 4.2.</span></span> <span data-ttu-id="2e0b4-120">따라서 후행 0 문자 표시 하거나 부동 소수점 값을 인쇄 하는 경우에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2e0b4-120">Consequently, trailing 0 characters do not appear when you display or print floating-point values.</span></span>  
  
-   <span data-ttu-id="2e0b4-121">**형식 문자입니다.**</span><span class="sxs-lookup"><span data-stu-id="2e0b4-121">**Type Characters.**</span></span> <span data-ttu-id="2e0b4-122">리터럴 형식 문자 `F`를 리터럴에 추가하면 `Single` 데이터 형식이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e0b4-122">Appending the literal type character `F` to a literal forces it to the `Single` data type.</span></span> <span data-ttu-id="2e0b4-123">식별자 형식 문자 `!`를 식별자에 추가하면 `Single`가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e0b4-123">Appending the identifier type character `!` to any identifier forces it to `Single`.</span></span>  
  
-   <span data-ttu-id="2e0b4-124">**Framework 형식입니다.**</span><span class="sxs-lookup"><span data-stu-id="2e0b4-124">**Framework Type.**</span></span> <span data-ttu-id="2e0b4-125">.NET Framework에서 해당하는 형식은 <xref:System.Single?displayProperty=nameWithType> 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="2e0b4-125">The corresponding type in the .NET Framework is the <xref:System.Single?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e0b4-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2e0b4-126">See Also</span></span>  
 <xref:System.Single?displayProperty=nameWithType>  
 [<span data-ttu-id="2e0b4-127">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="2e0b4-127">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="2e0b4-128">Decimal 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="2e0b4-128">Decimal Data Type</span></span>](../../../visual-basic/language-reference/data-types/decimal-data-type.md)  
 [<span data-ttu-id="2e0b4-129">Double 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="2e0b4-129">Double Data Type</span></span>](../../../visual-basic/language-reference/data-types/double-data-type.md)  
 [<span data-ttu-id="2e0b4-130">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="2e0b4-130">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="2e0b4-131">변환 요약</span><span class="sxs-lookup"><span data-stu-id="2e0b4-131">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="2e0b4-132">데이터 형식의 효율적 사용</span><span class="sxs-lookup"><span data-stu-id="2e0b4-132">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)  
 [<span data-ttu-id="2e0b4-133">데이터 형식 문제 해결</span><span class="sxs-lookup"><span data-stu-id="2e0b4-133">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
