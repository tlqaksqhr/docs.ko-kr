---
title: '&gt;&gt; 연산자 (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.>>
helpviewer_keywords:
- operator>>
- '>> operator [Visual Basic]'
- bit shift operators [Visual Basic]
- operator >>
- right shift operators [Visual Basic]
ms.assetid: 054dc6a6-47d9-47ef-82da-cfa2b59fbf8f
ms.openlocfilehash: 9bb8e82b3f5451417fe1867d08b7601ee1acb036
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33605409"
---
# <a name="gtgt-operator-visual-basic"></a><span data-ttu-id="f5146-102">&gt;&gt; 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f5146-102">&gt;&gt; Operator (Visual Basic)</span></span>
<span data-ttu-id="f5146-103">비트 패턴에 산술 오른쪽 시프트를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f5146-103">Performs an arithmetic right shift on a bit pattern.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5146-104">구문</span><span class="sxs-lookup"><span data-stu-id="f5146-104">Syntax</span></span>  
  
```  
result = pattern >> amount  
```  
  
## <a name="parts"></a><span data-ttu-id="f5146-105">요소</span><span class="sxs-lookup"><span data-stu-id="f5146-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="f5146-106">필수.</span><span class="sxs-lookup"><span data-stu-id="f5146-106">Required.</span></span> <span data-ttu-id="f5146-107">정수 계열 숫자 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f5146-107">Integral numeric value.</span></span> <span data-ttu-id="f5146-108">변화 하는 비트 패턴의 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="f5146-108">The result of shifting the bit pattern.</span></span> <span data-ttu-id="f5146-109">데이터 형식이 같습니다 `pattern`합니다.</span><span class="sxs-lookup"><span data-stu-id="f5146-109">The data type is the same as that of `pattern`.</span></span>  
  
 `pattern`  
 <span data-ttu-id="f5146-110">필수.</span><span class="sxs-lookup"><span data-stu-id="f5146-110">Required.</span></span> <span data-ttu-id="f5146-111">정수 계열 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="f5146-111">Integral numeric expression.</span></span> <span data-ttu-id="f5146-112">이동할 비트 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="f5146-112">The bit pattern to be shifted.</span></span> <span data-ttu-id="f5146-113">데이터 형식은 정수 계열 형식 이어야 합니다 (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, 또는 `ULong`).</span><span class="sxs-lookup"><span data-stu-id="f5146-113">The data type must be an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).</span></span>  
  
 `amount`  
 <span data-ttu-id="f5146-114">필수.</span><span class="sxs-lookup"><span data-stu-id="f5146-114">Required.</span></span> <span data-ttu-id="f5146-115">숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="f5146-115">Numeric expression.</span></span> <span data-ttu-id="f5146-116">비트 패턴을 이동할 비트 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5146-116">The number of bits to shift the bit pattern.</span></span> <span data-ttu-id="f5146-117">데이터 형식이 있어야 `Integer` 으로 확장 또는 `Integer`합니다.</span><span class="sxs-lookup"><span data-stu-id="f5146-117">The data type must be `Integer` or widen to `Integer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f5146-118">설명</span><span class="sxs-lookup"><span data-stu-id="f5146-118">Remarks</span></span>  
 <span data-ttu-id="f5146-119">이동 하는 산술 형식 이므로 하지 순환, 결과의 한쪽 끝에서 이동 하는 비트는 다른 쪽 끝에서 다시 도입 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f5146-119">Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end.</span></span> <span data-ttu-id="f5146-120">산술 오른쪽 시프트 연산 가장 오른쪽 위치를 넘어 이동 하는 비트는 무시 되 고 맨 왼쪽 (기호) 비트는 비워진 왼쪽 비트 위치로 전파 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5146-120">In an arithmetic right shift, the bits shifted beyond the rightmost bit position are discarded, and the leftmost (sign) bit is propagated into the bit positions vacated at the left.</span></span> <span data-ttu-id="f5146-121">즉 `pattern` 음수 값을 가진 비워진된 위치 1로 설정 됩니다; 그렇지 않으면 0으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5146-121">This means that if `pattern` has a negative value, the vacated positions are set to one; otherwise they are set to zero.</span></span>  
  
 <span data-ttu-id="f5146-122">데이터 형식 `Byte`, `UShort`, `UInteger`, 및 `ULong` 전파할 수 없는 부호 비트 이므로 서명 되지 않은 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5146-122">Note that the data types `Byte`, `UShort`, `UInteger`, and `ULong` are unsigned, so there is no sign bit to propagate.</span></span> <span data-ttu-id="f5146-123">경우 `pattern` 의 부호 없는 형식이, 빈된 위치는 항상 0으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5146-123">If `pattern` is of any unsigned type, the vacated positions are always set to zero.</span></span>  
  
 <span data-ttu-id="f5146-124">Visual Basic로 결과 표시할 수 있는 양보다 더 많은 비트 시프트를 방지 하려면의 값을 마스크 `amount` 의 데이터 형식에 해당 하는 크기 마스크로 `pattern`합니다.</span><span class="sxs-lookup"><span data-stu-id="f5146-124">To prevent shifting by more bits than the result can hold, Visual Basic masks the value of `amount` with a size mask corresponding to the data type of `pattern`.</span></span> <span data-ttu-id="f5146-125">이러한 값의 이진 AND 시프트 횟수에 대 한 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5146-125">The binary AND of these values is used for the shift amount.</span></span> <span data-ttu-id="f5146-126">마스크 크기는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f5146-126">The size masks are as follows:</span></span>  
  
|<span data-ttu-id="f5146-127">데이터 형식 `pattern`</span><span class="sxs-lookup"><span data-stu-id="f5146-127">Data type of `pattern`</span></span>|<span data-ttu-id="f5146-128">크기 마스크 (10 진수)</span><span class="sxs-lookup"><span data-stu-id="f5146-128">Size mask (decimal)</span></span>|<span data-ttu-id="f5146-129">마스크 크기 (16 진수)</span><span class="sxs-lookup"><span data-stu-id="f5146-129">Size mask (hexadecimal)</span></span>|  
|----------------------------|---------------------------|-------------------------------|  
|<span data-ttu-id="f5146-130">`SByte`, `Byte`</span><span class="sxs-lookup"><span data-stu-id="f5146-130">`SByte`, `Byte`</span></span>|<span data-ttu-id="f5146-131">7</span><span class="sxs-lookup"><span data-stu-id="f5146-131">7</span></span>|<span data-ttu-id="f5146-132">&AMP; H00000007</span><span class="sxs-lookup"><span data-stu-id="f5146-132">&H00000007</span></span>|  
|<span data-ttu-id="f5146-133">`Short`, `UShort`</span><span class="sxs-lookup"><span data-stu-id="f5146-133">`Short`, `UShort`</span></span>|<span data-ttu-id="f5146-134">15</span><span class="sxs-lookup"><span data-stu-id="f5146-134">15</span></span>|<span data-ttu-id="f5146-135">&AMP; H0000000F</span><span class="sxs-lookup"><span data-stu-id="f5146-135">&H0000000F</span></span>|  
|<span data-ttu-id="f5146-136">`Integer`, `UInteger`</span><span class="sxs-lookup"><span data-stu-id="f5146-136">`Integer`, `UInteger`</span></span>|<span data-ttu-id="f5146-137">31</span><span class="sxs-lookup"><span data-stu-id="f5146-137">31</span></span>|<span data-ttu-id="f5146-138">&AMP; H0000001F</span><span class="sxs-lookup"><span data-stu-id="f5146-138">&H0000001F</span></span>|  
|<span data-ttu-id="f5146-139">`Long`, `ULong`</span><span class="sxs-lookup"><span data-stu-id="f5146-139">`Long`, `ULong`</span></span>|<span data-ttu-id="f5146-140">63</span><span class="sxs-lookup"><span data-stu-id="f5146-140">63</span></span>|<span data-ttu-id="f5146-141">&AMP; H0000003F</span><span class="sxs-lookup"><span data-stu-id="f5146-141">&H0000003F</span></span>|  
  
 <span data-ttu-id="f5146-142">경우 `amount` 0의 값이 `result` 의 값과 일치 `pattern`합니다.</span><span class="sxs-lookup"><span data-stu-id="f5146-142">If `amount` is zero, the value of `result` is identical to the value of `pattern`.</span></span> <span data-ttu-id="f5146-143">경우 `amount` 가 음수 이면 해당 부호 없는 값으로 취급 되며 적절 한 크기 마스크를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5146-143">If `amount` is negative, it is taken as an unsigned value and masked with the appropriate size mask.</span></span>  
  
 <span data-ttu-id="f5146-144">이동 하는 산술 오버플로 예외를 생성 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f5146-144">Arithmetic shifts never generate overflow exceptions.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="f5146-145">오버로딩</span><span class="sxs-lookup"><span data-stu-id="f5146-145">Overloading</span></span>  
 <span data-ttu-id="f5146-146">`>>` 연산자 될 수 있습니다 *오버 로드 된*, 클래스 또는 구조체 수 할의 동작에 해당 클래스 또는 구조체의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="f5146-146">The `>>` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="f5146-147">이 연산자를 사용 하 여 이러한 클래스나 구조체에는 코드를 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5146-147">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="f5146-148">자세한 내용은 참조 [연산자 프로시저](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f5146-148">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f5146-149">예제</span><span class="sxs-lookup"><span data-stu-id="f5146-149">Example</span></span>  
 <span data-ttu-id="f5146-150">다음 예제에서는 `>>` 정수 값에 산술 오른쪽 시프트 연산을 수행 하는 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="f5146-150">The following example uses the `>>` operator to perform arithmetic right shifts on integral values.</span></span> <span data-ttu-id="f5146-151">결과는 항상 동일한 데이터 이동 되는 식과 같은 형식을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="f5146-151">The result always has the same data type as that of the expression being shifted.</span></span>  
  
 [!code-vb[VbVbalrOperators#14](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/right-shift-operator_1.vb)]  
  
 <span data-ttu-id="f5146-152">위 예의 결과 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f5146-152">The results of the preceding example are as follows:</span></span>  
  
-   <span data-ttu-id="f5146-153">`result1` 2560 (0000 1010 0000 0000)입니다.</span><span class="sxs-lookup"><span data-stu-id="f5146-153">`result1` is 2560 (0000 1010 0000 0000).</span></span>  
  
-   <span data-ttu-id="f5146-154">`result2` 160 (0000 0000 1010 0000)입니다.</span><span class="sxs-lookup"><span data-stu-id="f5146-154">`result2` is 160 (0000 0000 1010 0000).</span></span>  
  
-   <span data-ttu-id="f5146-155">`result3` 2 (0000 0000 0000 0010)입니다.</span><span class="sxs-lookup"><span data-stu-id="f5146-155">`result3` is 2 (0000 0000 0000 0010).</span></span>  
  
-   <span data-ttu-id="f5146-156">`result4` 640 (0010 1000 0000 0000)입니다.</span><span class="sxs-lookup"><span data-stu-id="f5146-156">`result4` is 640 (0000 0010 1000 0000).</span></span>  
  
-   <span data-ttu-id="f5146-157">`result5` 0 (오른쪽으로 15 자리 이동된)입니다.</span><span class="sxs-lookup"><span data-stu-id="f5146-157">`result5` is 0 (shifted 15 places to the right).</span></span>  
  
 <span data-ttu-id="f5146-158">에 대 한 시프트 횟수가 `result4` 18로 계산 됩니다가 2 및 15입니다.</span><span class="sxs-lookup"><span data-stu-id="f5146-158">The shift amount for `result4` is calculated as 18 AND 15, which equals 2.</span></span>  
  
 <span data-ttu-id="f5146-159">다음 예제에서는 음수 값을 산술 시프트 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5146-159">The following example shows arithmetic shifts on a negative value.</span></span>  
  
 [!code-vb[VbVbalrOperators#55](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/right-shift-operator_2.vb)]  
  
 <span data-ttu-id="f5146-160">위 예의 결과 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f5146-160">The results of the preceding example are as follows:</span></span>  
  
-   <span data-ttu-id="f5146-161">`negresult1` -512 (1111 1110 0000 0000)입니다.</span><span class="sxs-lookup"><span data-stu-id="f5146-161">`negresult1` is -512 (1111 1110 0000 0000).</span></span>  
  
-   <span data-ttu-id="f5146-162">`negresult2` -1 (부호 비트 전파 됨 입니다).</span><span class="sxs-lookup"><span data-stu-id="f5146-162">`negresult2` is -1 (the sign bit is propagated).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5146-163">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f5146-163">See Also</span></span>  
 [<span data-ttu-id="f5146-164">비트 시프트 연산자</span><span class="sxs-lookup"><span data-stu-id="f5146-164">Bit Shift Operators</span></span>](../../../visual-basic/language-reference/operators/bit-shift-operators.md)  
 [<span data-ttu-id="f5146-165">할당 연산자</span><span class="sxs-lookup"><span data-stu-id="f5146-165">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [<span data-ttu-id="f5146-166">>>= 연산자</span><span class="sxs-lookup"><span data-stu-id="f5146-166">>>= Operator</span></span>](../../../visual-basic/language-reference/operators/right-shift-assignment-operator.md)  
 [<span data-ttu-id="f5146-167">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="f5146-167">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="f5146-168">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="f5146-168">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="f5146-169">Visual Basic의 산술 연산자</span><span class="sxs-lookup"><span data-stu-id="f5146-169">Arithmetic Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
