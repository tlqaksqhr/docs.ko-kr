---
title: Double 데이터 형식(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Double
helpviewer_keywords:
- 'identifier type characters [Visual Basic], #'
- trailing zeros
- real numbers
- trailing 0 characters [Visual Basic]
- 0 characters [Visual Basic], trailing
- literal type characters [Visual Basic], R
- data types [Visual Basic], assigning
- Double data type [Visual Basic]
- '# identifier type character'
- double-precision numbers
- floating-point numbers [Visual Basic], Double data type
- R literal type character [Visual Basic]
- zeros, trailing
- Double data type
ms.assetid: 0c5670f7-fcb1-453a-bef1-374730cd38fd
ms.openlocfilehash: c2d3d7d360ccb240bafbe0e19e9f396adfba7f7e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33590266"
---
# <a name="double-data-type-visual-basic"></a><span data-ttu-id="96c62-102">Double 데이터 형식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="96c62-102">Double Data Type (Visual Basic)</span></span>
<span data-ttu-id="96c62-103">부호 있는 IEEE 64 비트 (8 바이트) 배정밀 부동 소수점 숫자 값에서-1.79769313486231570 e + 308에서-범위에 있는 저장 4.94065645841246544E-324 음수 경우 4.94065645841246544 e에서-324 1.79769313486231570 e + 308 양수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="96c62-103">Holds signed IEEE 64-bit (8-byte) double-precision floating-point numbers that range in value from -1.79769313486231570E+308 through -4.94065645841246544E-324 for negative values and from 4.94065645841246544E-324 through 1.79769313486231570E+308 for positive values.</span></span> <span data-ttu-id="96c62-104">두 자리 숫자는 실수의 근사값을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="96c62-104">Double-precision numbers store an approximation of a real number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="96c62-105">설명</span><span class="sxs-lookup"><span data-stu-id="96c62-105">Remarks</span></span>  
 <span data-ttu-id="96c62-106">`Double` 숫자 데이터 형식을 사용할 수 있는 가장 큰와 가장 작은 크기를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="96c62-106">The `Double` data type provides the largest and smallest possible magnitudes for a number.</span></span>  
  
 <span data-ttu-id="96c62-107">`Double`의 기본값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="96c62-107">The default value of `Double` is 0.</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="96c62-108">프로그래밍 팁</span><span class="sxs-lookup"><span data-stu-id="96c62-108">Programming Tips</span></span>  
  
-   <span data-ttu-id="96c62-109">**전체 자릿수입니다.**</span><span class="sxs-lookup"><span data-stu-id="96c62-109">**Precision.**</span></span> <span data-ttu-id="96c62-110">부동 소수점 숫자를 작업할 때에 항상 없는 정확한 표시 메모리에 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96c62-110">When you work with floating-point numbers, remember that they do not always have a precise representation in memory.</span></span> <span data-ttu-id="96c62-111">값 비교 같은 특정 작업에서 예기치 않은 결과가 발생할 수 및 `Mod` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="96c62-111">This could lead to unexpected results from certain operations, such as value comparison and the `Mod` operator.</span></span> <span data-ttu-id="96c62-112">자세한 내용은 참조 [데이터 형식 문제 해결](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="96c62-112">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
-   <span data-ttu-id="96c62-113">**뒤에 오는 0입니다.**</span><span class="sxs-lookup"><span data-stu-id="96c62-113">**Trailing Zeros.**</span></span> <span data-ttu-id="96c62-114">부동 소수점 데이터 형식에는 후행 0 문자 모든 내부 표현이지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="96c62-114">The floating-point data types do not have any internal representation of trailing zero characters.</span></span> <span data-ttu-id="96c62-115">예를 들어 이러한 구분 하지 않습니다 4.2000 및 4.2 합니다.</span><span class="sxs-lookup"><span data-stu-id="96c62-115">For example, they do not distinguish between 4.2000 and 4.2.</span></span> <span data-ttu-id="96c62-116">따라서 후행 0 문자를 표시할 때 또는 인쇄 부동 소수점 값 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="96c62-116">Consequently, trailing zero characters do not appear when you display or print floating-point values.</span></span>  
  
-   <span data-ttu-id="96c62-117">**형식 문자입니다.**</span><span class="sxs-lookup"><span data-stu-id="96c62-117">**Type Characters.**</span></span> <span data-ttu-id="96c62-118">리터럴 형식 문자 `R`를 리터럴에 추가하면 `Double` 데이터 형식이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96c62-118">Appending the literal type character `R` to a literal forces it to the `Double` data type.</span></span> <span data-ttu-id="96c62-119">예를 들어, 다음에 정수 값 되 면 `R`, 값이 변경 되는 `Double`합니다.</span><span class="sxs-lookup"><span data-stu-id="96c62-119">For example, if an integer value is followed by `R`, the value is changed to a `Double`.</span></span>  
  
    ```  
    ' Visual Basic expands the 4 in the statement Dim dub As Double = 4R to 4.0:  
    Dim dub As Double = 4.0R  
    ```  
  
     <span data-ttu-id="96c62-120">식별자 형식 문자 `#`를 식별자에 추가하면 `Double`가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="96c62-120">Appending the identifier type character `#` to any identifier forces it to `Double`.</span></span> <span data-ttu-id="96c62-121">다음 예에서 변수 `num` 로 형식화 되는 `Double`:</span><span class="sxs-lookup"><span data-stu-id="96c62-121">In the following example, the variable `num` is typed as a `Double`:</span></span>  
  
    ```  
    Dim num# = 3  
    ```  
  
-   <span data-ttu-id="96c62-122">**Framework 형식입니다.**</span><span class="sxs-lookup"><span data-stu-id="96c62-122">**Framework Type.**</span></span> <span data-ttu-id="96c62-123">.NET Framework에서 해당하는 형식은 <xref:System.Double?displayProperty=nameWithType> 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="96c62-123">The corresponding type in the .NET Framework is the <xref:System.Double?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96c62-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="96c62-124">See Also</span></span>  
 <xref:System.Double?displayProperty=nameWithType>  
 [<span data-ttu-id="96c62-125">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="96c62-125">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="96c62-126">Decimal 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="96c62-126">Decimal Data Type</span></span>](../../../visual-basic/language-reference/data-types/decimal-data-type.md)  
 [<span data-ttu-id="96c62-127">Single 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="96c62-127">Single Data Type</span></span>](../../../visual-basic/language-reference/data-types/single-data-type.md)  
 [<span data-ttu-id="96c62-128">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="96c62-128">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="96c62-129">변환 요약</span><span class="sxs-lookup"><span data-stu-id="96c62-129">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="96c62-130">데이터 형식의 효율적 사용</span><span class="sxs-lookup"><span data-stu-id="96c62-130">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)  
 [<span data-ttu-id="96c62-131">데이터 형식 문제 해결</span><span class="sxs-lookup"><span data-stu-id="96c62-131">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [<span data-ttu-id="96c62-132">형식 문자</span><span class="sxs-lookup"><span data-stu-id="96c62-132">Type Characters</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
