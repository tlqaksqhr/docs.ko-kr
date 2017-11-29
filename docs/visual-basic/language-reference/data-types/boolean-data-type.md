---
title: "Boolean 데이터 형식(Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.FALSE
- vb.TRUE
- vb.Boolean
helpviewer_keywords:
- Boolean data type
- Boolean values [Visual Basic], False keyword
- False keyword [Visual Basic]
- True keyword [Visual Basic]
- Boolean values [Visual Basic], True keyword
ms.assetid: 4858e630-4813-4216-a55e-f4d0feb884e4
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bdc106f1ec874c1a2165df069d5f3485fe5b2e43
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="boolean-data-type-visual-basic"></a><span data-ttu-id="d4440-102">Boolean 데이터 형식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d4440-102">Boolean Data Type (Visual Basic)</span></span>
<span data-ttu-id="d4440-103">값만 될 수 있는 포함 `True` 또는 `False`합니다.</span><span class="sxs-lookup"><span data-stu-id="d4440-103">Holds values that can be only `True` or `False`.</span></span> <span data-ttu-id="d4440-104">키워드 `True` 및 `False` 의 두 가지 상태에 해당 `Boolean` 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="d4440-104">The keywords `True` and `False` correspond to the two states of `Boolean` variables.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4440-105">설명</span><span class="sxs-lookup"><span data-stu-id="d4440-105">Remarks</span></span>  
 <span data-ttu-id="d4440-106">사용 하 여는 [Boolean 데이터 형식 (Visual Basic)](../../../visual-basic/language-reference/data-types/boolean-data-type.md) 예/아니요 또는 켜기/끄기 true/false 같은 두 가지 상태 값을 포함 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4440-106">Use the [Boolean Data Type (Visual Basic)](../../../visual-basic/language-reference/data-types/boolean-data-type.md) to contain two-state values such as true/false, yes/no, or on/off.</span></span>  
  
 <span data-ttu-id="d4440-107">`Boolean`의 기본값은 `False`입니다.</span><span class="sxs-lookup"><span data-stu-id="d4440-107">The default value of `Boolean` is `False`.</span></span>  
  
 <span data-ttu-id="d4440-108">`Boolean`값이 숫자로 저장 되지 않습니다 및 저장 된 값은 숫자에 해당 되지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4440-108">`Boolean` values are not stored as numbers, and the stored values are not intended to be equivalent to numbers.</span></span> <span data-ttu-id="d4440-109">해당 하는 숫자 값을 사용 하는 코드를 작성 하지 마십시오 `True` 및 `False`합니다.</span><span class="sxs-lookup"><span data-stu-id="d4440-109">You should never write code that relies on equivalent numeric values for `True` and `False`.</span></span> <span data-ttu-id="d4440-110">용도 제한 해야 가능 하면 항상 `Boolean` 변수도 설계 된 논리 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d4440-110">Whenever possible, you should restrict usage of `Boolean` variables to the logical values for which they are designed.</span></span>  
  
## <a name="type-conversions"></a><span data-ttu-id="d4440-111">형식 변환</span><span class="sxs-lookup"><span data-stu-id="d4440-111">Type Conversions</span></span>  
 <span data-ttu-id="d4440-112">Visual Basic 숫자 데이터 형식 값을 변환 하는 경우 `Boolean`, 0은 `False` 고 다른 모든 값은 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="d4440-112">When Visual Basic converts numeric data type values to `Boolean`, 0 becomes `False` and all other values become `True`.</span></span> <span data-ttu-id="d4440-113">Visual Basic로 변환 하는 경우 `Boolean` 값을 숫자 형식 `False` 0이 되 고 `True` 는-1입니다.</span><span class="sxs-lookup"><span data-stu-id="d4440-113">When Visual Basic converts `Boolean` values to numeric types, `False` becomes 0 and `True` becomes -1.</span></span>  
  
 <span data-ttu-id="d4440-114">간에 변환할 때 `Boolean` 값 및 숫자 데이터 형식을 염두에.NET Framework의 변환 메서드는 항상 Visual Basic 변환 키워드와 동일한 결과 생성 하 고 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d4440-114">When you convert between `Boolean` values and numeric data types, keep in mind that the .NET Framework conversion methods do not always produce the same results as the Visual Basic conversion keywords.</span></span> <span data-ttu-id="d4440-115">이 Visual Basic 변환 이전 버전과 호환 동작을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4440-115">This is because the Visual Basic conversion retains behavior compatible with previous versions.</span></span> <span data-ttu-id="d4440-116">자세한 내용은 "부울 형식 않습니다 변환에 숫자 형식이 정확 하 게"의 참조 [데이터 형식 문제 해결](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d4440-116">For more information, see "Boolean Type Does Not Convert to Numeric Type Accurately" in [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="d4440-117">프로그래밍 팁</span><span class="sxs-lookup"><span data-stu-id="d4440-117">Programming Tips</span></span>  
  
-   <span data-ttu-id="d4440-118">**음수입니다.**</span><span class="sxs-lookup"><span data-stu-id="d4440-118">**Negative Numbers.**</span></span> <span data-ttu-id="d4440-119">`Boolean`숫자 형식이 아닌 및 음수 값을 나타낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d4440-119">`Boolean` is not a numeric type and cannot represent a negative value.</span></span> <span data-ttu-id="d4440-120">사용 하지 않아야 어떤 경우 든, `Boolean` 숫자 값을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4440-120">In any case, you should not use `Boolean` to hold numeric values.</span></span>  
  
-   <span data-ttu-id="d4440-121">**형식 문자입니다.**</span><span class="sxs-lookup"><span data-stu-id="d4440-121">**Type Characters.**</span></span> <span data-ttu-id="d4440-122">`Boolean`에 리터럴 형식 문자 또는 식별자 형식 문자가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d4440-122">`Boolean` has no literal type character or identifier type character.</span></span>  
  
-   <span data-ttu-id="d4440-123">**Framework 형식입니다.**</span><span class="sxs-lookup"><span data-stu-id="d4440-123">**Framework Type.**</span></span> <span data-ttu-id="d4440-124">.NET Framework에서 해당하는 형식은 <xref:System.Boolean?displayProperty=nameWithType> 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="d4440-124">The corresponding type in the .NET Framework is the <xref:System.Boolean?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d4440-125">예제</span><span class="sxs-lookup"><span data-stu-id="d4440-125">Example</span></span>  
 <span data-ttu-id="d4440-126">다음 예에서 `runningVB` 는 `Boolean` 예/아니요 설정 하는 간단한 저장 하는 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="d4440-126">In the following example, `runningVB` is a `Boolean` variable, which stores a simple yes/no setting.</span></span>  
  
```  
Dim runningVB As Boolean  
' Check to see if program is running on Visual Basic engine.  
If scriptEngine = "VB" Then  
    runningVB = True  
End If  
```  
  
## <a name="see-also"></a><span data-ttu-id="d4440-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d4440-127">See Also</span></span>  
 <xref:System.Boolean?displayProperty=nameWithType>  
 [<span data-ttu-id="d4440-128">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="d4440-128">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="d4440-129">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="d4440-129">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="d4440-130">변환 요약</span><span class="sxs-lookup"><span data-stu-id="d4440-130">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="d4440-131">데이터 형식의 효율적 사용</span><span class="sxs-lookup"><span data-stu-id="d4440-131">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)  
 [<span data-ttu-id="d4440-132">데이터 형식 문제 해결</span><span class="sxs-lookup"><span data-stu-id="d4440-132">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [<span data-ttu-id="d4440-133">CType 함수</span><span class="sxs-lookup"><span data-stu-id="d4440-133">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)
