---
title: "&lt;&lt;연산자 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.<<
helpviewer_keywords:
- bit shift operators [Visual Basic]
- << operator [Visual Basic]
- operator <<, Visual Basic left shift operator
ms.assetid: fdb93d25-81ba-417f-b808-41207bfb8440
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 56cfb227f7e5c68de802c1f2cfb842a770f65ae0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltlt-operator-visual-basic"></a><span data-ttu-id="b4870-102">&lt;&lt;연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b4870-102">&lt;&lt; Operator (Visual Basic)</span></span>
<span data-ttu-id="b4870-103">비트 패턴에 산술 왼쪽된 시프트를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="b4870-103">Performs an arithmetic left shift on a bit pattern.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4870-104">구문</span><span class="sxs-lookup"><span data-stu-id="b4870-104">Syntax</span></span>  
  
```  
result = pattern << amount  
```  
  
## <a name="parts"></a><span data-ttu-id="b4870-105">요소</span><span class="sxs-lookup"><span data-stu-id="b4870-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="b4870-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="b4870-106">Required.</span></span> <span data-ttu-id="b4870-107">정수 계열 숫자 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b4870-107">Integral numeric value.</span></span> <span data-ttu-id="b4870-108">변화 하는 비트 패턴의 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="b4870-108">The result of shifting the bit pattern.</span></span> <span data-ttu-id="b4870-109">데이터 형식이 같습니다 `pattern`합니다.</span><span class="sxs-lookup"><span data-stu-id="b4870-109">The data type is the same as that of `pattern`.</span></span>  
  
 `pattern`  
 <span data-ttu-id="b4870-110">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="b4870-110">Required.</span></span> <span data-ttu-id="b4870-111">정수 계열 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="b4870-111">Integral numeric expression.</span></span> <span data-ttu-id="b4870-112">이동할 비트 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="b4870-112">The bit pattern to be shifted.</span></span> <span data-ttu-id="b4870-113">데이터 형식은 정수 계열 형식 이어야 합니다 (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, 또는 `ULong`).</span><span class="sxs-lookup"><span data-stu-id="b4870-113">The data type must be an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="b4870-114">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="b4870-114">Required.</span></span> <span data-ttu-id="b4870-115">숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="b4870-115">Numeric expression.</span></span> <span data-ttu-id="b4870-116">비트 패턴을 이동할 비트 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4870-116">The number of bits to shift the bit pattern.</span></span> <span data-ttu-id="b4870-117">데이터 형식이 있어야 `Integer` 으로 확장 또는 `Integer`합니다.</span><span class="sxs-lookup"><span data-stu-id="b4870-117">The data type must be `Integer` or widen to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b4870-118">설명</span><span class="sxs-lookup"><span data-stu-id="b4870-118">Remarks</span></span>  
 <span data-ttu-id="b4870-119">이동 하는 산술 형식 이므로 하지 순환, 결과의 한쪽 끝에서 이동 하는 비트는 다른 쪽 끝에서 다시 도입 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b4870-119">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="b4870-120">산술 왼쪽 시프트 연산 결과 데이터 형식의 범위를 넘어 이동 하는 비트는 무시 되 고 오른쪽에 비워진 비트 위치 0으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4870-120">In an arithmetic left shift, the bits shifted beyond the range of the result data type are discarded, and the bit positions vacated on the right are set to zero.</span></span>  
  
 <span data-ttu-id="b4870-121">Visual Basic의 값을 마스크 비트 결과 표시할 수 있는 양보다 더 많은 횟수가 shift를 방지 하려면 `amount` 의 데이터 형식에 해당 하는 크기 마스크로 `pattern`합니다.</span><span class="sxs-lookup"><span data-stu-id="b4870-121">To prevent a shift by more bits than the result can hold, Visual Basic masks the value of `amount` with a size mask that corresponds to the data type of `pattern`.</span></span> <span data-ttu-id="b4870-122">이러한 값의 이진 AND 시프트 횟수에 대 한 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4870-122">The binary AND of these values is used for the shift amount.</span></span> <span data-ttu-id="b4870-123">마스크 크기는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b4870-123">The size masks are as follows:</span></span>  
  
|<span data-ttu-id="b4870-124">데이터 형식`pattern`</span><span class="sxs-lookup"><span data-stu-id="b4870-124">Data type of `pattern`</span></span>|<span data-ttu-id="b4870-125">크기 마스크 (10 진수)</span><span class="sxs-lookup"><span data-stu-id="b4870-125">Size mask (decimal)</span></span>|<span data-ttu-id="b4870-126">마스크 크기 (16 진수)</span><span class="sxs-lookup"><span data-stu-id="b4870-126">Size mask (hexadecimal)</span></span>|  
|----------------------------|---------------------------|-------------------------------|  
|<span data-ttu-id="b4870-127">`SByte`, `Byte`</span><span class="sxs-lookup"><span data-stu-id="b4870-127">`SByte`, `Byte`</span></span>|<span data-ttu-id="b4870-128">7</span><span class="sxs-lookup"><span data-stu-id="b4870-128">7</span></span>|<span data-ttu-id="b4870-129">& H00000007</span><span class="sxs-lookup"><span data-stu-id="b4870-129">&H00000007</span></span>|  
|<span data-ttu-id="b4870-130">`Short`, `UShort`</span><span class="sxs-lookup"><span data-stu-id="b4870-130">`Short`, `UShort`</span></span>|<span data-ttu-id="b4870-131">15</span><span class="sxs-lookup"><span data-stu-id="b4870-131">15</span></span>|<span data-ttu-id="b4870-132">& H0000000F</span><span class="sxs-lookup"><span data-stu-id="b4870-132">&H0000000F</span></span>|  
|<span data-ttu-id="b4870-133">`Integer`, `UInteger`</span><span class="sxs-lookup"><span data-stu-id="b4870-133">`Integer`, `UInteger`</span></span>|<span data-ttu-id="b4870-134">31</span><span class="sxs-lookup"><span data-stu-id="b4870-134">31</span></span>|<span data-ttu-id="b4870-135">& H0000001F</span><span class="sxs-lookup"><span data-stu-id="b4870-135">&H0000001F</span></span>|  
|<span data-ttu-id="b4870-136">`Long`, `ULong`</span><span class="sxs-lookup"><span data-stu-id="b4870-136">`Long`, `ULong`</span></span>|<span data-ttu-id="b4870-137">63</span><span class="sxs-lookup"><span data-stu-id="b4870-137">63</span></span>|<span data-ttu-id="b4870-138">& H0000003F</span><span class="sxs-lookup"><span data-stu-id="b4870-138">&H0000003F</span></span>|  
  
 <span data-ttu-id="b4870-139">경우 `amount` 0의 값이 `result` 의 값과 일치 `pattern`합니다.</span><span class="sxs-lookup"><span data-stu-id="b4870-139">If `amount` is zero, the value of `result` is identical to the value of `pattern`.</span></span> <span data-ttu-id="b4870-140">경우 `amount` 가 음수 이면 해당 부호 없는 값으로 취급 되며 적절 한 크기 마스크를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4870-140">If `amount` is negative, it is taken as an unsigned value and masked with the appropriate size mask.</span></span>  
  
 <span data-ttu-id="b4870-141">이동 하는 산술 오버플로 예외를 생성 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b4870-141">Arithmetic shifts never generate overflow exceptions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b4870-142">`<<` 연산자 될 수 있습니다 *오버 로드 된*, 클래스 또는 구조체 수 할의 동작에 해당 클래스 또는 구조체의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b4870-142">The `<<` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="b4870-143">이 연산자를 사용 하 여 이러한 클래스나 구조체에는 코드를 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4870-143">If your code uses this operator on such a class or structure, be sure that you understand its redefined behavior.</span></span> <span data-ttu-id="b4870-144">자세한 내용은 참조 [연산자 프로시저](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b4870-144">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b4870-145">예제</span><span class="sxs-lookup"><span data-stu-id="b4870-145">Example</span></span>  
 <span data-ttu-id="b4870-146">다음 예제에서는 `<<` 연산자 왼쪽 시프트 정수 값에 산술 연산을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4870-146">The following example uses the `<<` operator to perform arithmetic left shifts on integral values.</span></span> <span data-ttu-id="b4870-147">결과는 항상 동일한 데이터 이동 되는 식과 같은 형식을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="b4870-147">The result always has the same data type as that of the expression being shifted.</span></span>  
  
 [!code-vb[VbVbalrOperators#12](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/left-shift-operator_1.vb)]  
  
 <span data-ttu-id="b4870-148">이전 예의 결과 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b4870-148">The results of the previous example are as follows:</span></span>  
  
-   <span data-ttu-id="b4870-149">`result1`192 (0000 0000 1100 0000)입니다.</span><span class="sxs-lookup"><span data-stu-id="b4870-149">`result1` is 192 (0000 0000 1100 0000).</span></span>  
  
-   <span data-ttu-id="b4870-150">`result2`3072 (1100 0000 0000 0000)입니다.</span><span class="sxs-lookup"><span data-stu-id="b4870-150">`result2` is 3072 (0000 1100 0000 0000).</span></span>  
  
-   <span data-ttu-id="b4870-151">`result3`-32768 (0000 0000 0000 1000)입니다.</span><span class="sxs-lookup"><span data-stu-id="b4870-151">`result3` is -32768 (1000 0000 0000 0000).</span></span>  
  
-   <span data-ttu-id="b4870-152">`result4`384 (0001 1000 0000 0000)입니다.</span><span class="sxs-lookup"><span data-stu-id="b4870-152">`result4` is 384 (0000 0001 1000 0000).</span></span>  
  
-   <span data-ttu-id="b4870-153">`result5`0 (왼쪽으로 15 자리 이동된)입니다.</span><span class="sxs-lookup"><span data-stu-id="b4870-153">`result5` is 0 (shifted 15 places to the left).</span></span>  
  
 <span data-ttu-id="b4870-154">에 대 한 시프트 횟수가 `result4` 17 같이 계산 됩니다. 1 및 15입니다.</span><span class="sxs-lookup"><span data-stu-id="b4870-154">The shift amount for `result4` is calculated as 17 AND 15, which equals 1.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4870-155">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b4870-155">See Also</span></span>  
 [<span data-ttu-id="b4870-156">비트 시프트 연산자</span><span class="sxs-lookup"><span data-stu-id="b4870-156">Bit Shift Operators</span></span>](../../../visual-basic/language-reference/operators/bit-shift-operators.md)  
 [<span data-ttu-id="b4870-157">할당 연산자</span><span class="sxs-lookup"><span data-stu-id="b4870-157">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [<span data-ttu-id="b4870-158"><<= 연산자</span><span class="sxs-lookup"><span data-stu-id="b4870-158"><<= Operator</span></span>](../../../visual-basic/language-reference/operators/left-shift-assignment-operator.md)  
 [<span data-ttu-id="b4870-159">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="b4870-159">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="b4870-160">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="b4870-160">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="b4870-161">Visual Basic의 산술 연산자</span><span class="sxs-lookup"><span data-stu-id="b4870-161">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
