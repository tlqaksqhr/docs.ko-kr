---
title: Char 데이터 형식(Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Char
helpviewer_keywords:
- literal type characters [Visual Basic], C
- Char data type
- C literal type character [Visual Basic]
- data types [Visual Basic], assigning
- Char data type [Visual Basic], character literals
ms.assetid: cd7547a9-7855-4e8e-b216-35d74a362657
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 16ff547fccbf4481d31ca79537962cc7090fc9b0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="char-data-type-visual-basic"></a><span data-ttu-id="0a23f-102">Char 데이터 형식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0a23f-102">Char Data Type (Visual Basic)</span></span>
<span data-ttu-id="0a23f-103">값은 0에서 65535 까지의 부호 없는 16 비트 (2 바이트) 코드 포인트를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a23f-103">Holds unsigned 16-bit (2-byte) code points ranging in value from 0 through 65535.</span></span> <span data-ttu-id="0a23f-104">각 *코드 포인트*, 또는 문자 코드 단일 유니코드 문자를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0a23f-104">Each *code point*, or character code, represents a single Unicode character.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0a23f-105">설명</span><span class="sxs-lookup"><span data-stu-id="0a23f-105">Remarks</span></span>  
 <span data-ttu-id="0a23f-106">사용 하 여는 `Char` 하나만 포함 해야 하는 경우 데이터 형식 및 오버 헤드가 필요 하지 않는 문자 `String`합니다.</span><span class="sxs-lookup"><span data-stu-id="0a23f-106">Use the `Char` data type when you need to hold only a single character and do not need the overhead of `String`.</span></span> <span data-ttu-id="0a23f-107">일부 경우에 사용할 수 있습니다 `Char()`, 배열을 `Char` 여러 문자를 저장할 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="0a23f-107">In some cases you can use `Char()`, an array of `Char` elements, to hold multiple characters.</span></span>  
  
 <span data-ttu-id="0a23f-108">기본값 `Char` 0의 코드 포인트와 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="0a23f-108">The default value of `Char` is the character with a code point of 0.</span></span>  
  
## <a name="unicode-characters"></a><span data-ttu-id="0a23f-109">유니코드 문자</span><span class="sxs-lookup"><span data-stu-id="0a23f-109">Unicode Characters</span></span>  
 <span data-ttu-id="0a23f-110">유니코드는 첫 번째 128 개 코드 포인트 (0-127) 문자와 기호 미국 표준 키보드에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a23f-110">The first 128 code points (0–127) of Unicode correspond to the letters and symbols on a standard U.S. keyboard.</span></span> <span data-ttu-id="0a23f-111">이러한 128 개 코드 포인트는 ASCII 문자 집합에 정의 된 것과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a23f-111">These first 128 code points are the same as those the ASCII character set defines.</span></span> <span data-ttu-id="0a23f-112">두 번째 128 개 코드 포인트 (128-255) 라틴어 기반 알파벳 글자, 악센트, 통화 기호 및 조각 등의 특수 문자를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0a23f-112">The second 128 code points (128–255) represent special characters, such as Latin-based alphabet letters, accents, currency symbols, and fractions.</span></span> <span data-ttu-id="0a23f-113">유니코드에 대 한 기호를 전 세계의 텍스트 문자, 분음 기호, 수학 및 기술 기호 등의 다양 한 나머지 코드 포인트 (256-65535)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a23f-113">Unicode uses the remaining code points (256-65535) for a wide variety of symbols, including worldwide textual characters, diacritics, and mathematical and technical symbols.</span></span>  
  
 <span data-ttu-id="0a23f-114">와 같은 메서드를 사용할 수 있습니다 <xref:System.Char.IsDigit%2A> 및 <xref:System.Char.IsPunctuation%2A> 에 `Char` 변수를 유니코드 분류를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a23f-114">You can use methods like <xref:System.Char.IsDigit%2A> and <xref:System.Char.IsPunctuation%2A> on a `Char` variable to determine its Unicode classification.</span></span>  
  
## <a name="type-conversions"></a><span data-ttu-id="0a23f-115">형식 변환</span><span class="sxs-lookup"><span data-stu-id="0a23f-115">Type Conversions</span></span>  
 <span data-ttu-id="0a23f-116">Visual Basic 사이 직접 변환 되지 않습니다. `Char` 및 숫자 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="0a23f-116">Visual Basic does not convert directly between `Char` and the numeric types.</span></span> <span data-ttu-id="0a23f-117">사용할 수는 <xref:Microsoft.VisualBasic.Strings.Asc%2A> 또는 <xref:Microsoft.VisualBasic.Strings.AscW%2A> 변환 하는 함수는 `Char` 값을 `Integer` 해당 코드 포인트를 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="0a23f-117">You can use the <xref:Microsoft.VisualBasic.Strings.Asc%2A> or <xref:Microsoft.VisualBasic.Strings.AscW%2A> function to convert a `Char` value to an `Integer` that represents its code point.</span></span> <span data-ttu-id="0a23f-118">사용할 수 있습니다는 <xref:Microsoft.VisualBasic.Strings.Chr%2A> 또는 <xref:Microsoft.VisualBasic.Strings.ChrW%2A> 변환 하는 함수는 `Integer` 값을 `Char` 있는 코드 포인트입니다.</span><span class="sxs-lookup"><span data-stu-id="0a23f-118">You can use the <xref:Microsoft.VisualBasic.Strings.Chr%2A> or <xref:Microsoft.VisualBasic.Strings.ChrW%2A> function to convert an `Integer` value to a `Char` that has that code point.</span></span>  
  
 <span data-ttu-id="0a23f-119">형식 검사 스위치 하는 경우 ([Option Strict 문](../../../visual-basic/language-reference/statements/option-strict-statement.md))를로 식별 하기 리터럴 단일 문자 문자열 리터럴 형식 문자를 추가 해야이 설정의 `Char` 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="0a23f-119">If the type checking switch ([Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md)) is on, you must append the literal type character to a single-character string literal to identify it as the `Char` data type.</span></span> <span data-ttu-id="0a23f-120">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="0a23f-120">The following example illustrates this.</span></span>  
  
```  
Option Strict On  
Dim charVar As Char  
' The following statement attempts to convert a String literal to Char.  
' Because Option Strict is On, it generates a compiler error.  
charVar = "Z"  
' The following statement succeeds because it specifies a Char literal.  
charVar = "Z"C  
```  
  
## <a name="programming-tips"></a><span data-ttu-id="0a23f-121">프로그래밍 팁</span><span class="sxs-lookup"><span data-stu-id="0a23f-121">Programming Tips</span></span>  
  
-   <span data-ttu-id="0a23f-122">**음수입니다.**</span><span class="sxs-lookup"><span data-stu-id="0a23f-122">**Negative Numbers.**</span></span> <span data-ttu-id="0a23f-123">`Char`부호 없는 형식 및 음수 값을 나타낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0a23f-123">`Char` is an unsigned type and cannot represent a negative value.</span></span> <span data-ttu-id="0a23f-124">사용 하지 않아야 어떤 경우 든, `Char` 숫자 값을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a23f-124">In any case, you should not use `Char` to hold numeric values.</span></span>  
  
-   <span data-ttu-id="0a23f-125">**Interop 고려 사항입니다.**</span><span class="sxs-lookup"><span data-stu-id="0a23f-125">**Interop Considerations.**</span></span> <span data-ttu-id="0a23f-126">.NET Framework에 대해 작성 되지 않은 구성 요소와 인터페이스 하는 경우 예제 Automation 또는 COM 개체에 대 한 기억 문자 형식을 다른 데이터 너비 (8 비트) 한지 다른 환경에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a23f-126">If you interface with components not written for the .NET Framework, for example Automation or COM objects, remember that character types have a different data width (8 bits) in other environments.</span></span> <span data-ttu-id="0a23f-127">이러한 구성 요소에는 8 비트 인수를 전달 하는 경우로 선언 `Byte` 대신 `Char` 새 Visual Basic 코드에서.</span><span class="sxs-lookup"><span data-stu-id="0a23f-127">If you pass an 8-bit argument to such a component, declare it as `Byte` instead of `Char` in your new Visual Basic code.</span></span>  
  
-   <span data-ttu-id="0a23f-128">**확대 합니다.**</span><span class="sxs-lookup"><span data-stu-id="0a23f-128">**Widening.**</span></span> <span data-ttu-id="0a23f-129">`Char` 데이터 형식으로 확대 되 `String`합니다.</span><span class="sxs-lookup"><span data-stu-id="0a23f-129">The `Char` data type widens to `String`.</span></span> <span data-ttu-id="0a23f-130">즉, 변환할 수 `Char` 를 `String` 발생 없이 <xref:System.OverflowException?displayProperty=nameWithType> 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="0a23f-130">This means you can convert `Char` to `String` and will not encounter a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
-   <span data-ttu-id="0a23f-131">**형식 문자입니다.**</span><span class="sxs-lookup"><span data-stu-id="0a23f-131">**Type Characters.**</span></span> <span data-ttu-id="0a23f-132">리터럴 형식 문자 추가 `C` 를 단일 문자 문자열 리터럴에 `Char` 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="0a23f-132">Appending the literal type character `C` to a single-character string literal forces it to the `Char` data type.</span></span> <span data-ttu-id="0a23f-133">`Char`에 식별자 형식 문자가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0a23f-133">`Char` has no identifier type character.</span></span>  
  
-   <span data-ttu-id="0a23f-134">**Framework 형식입니다.**</span><span class="sxs-lookup"><span data-stu-id="0a23f-134">**Framework Type.**</span></span> <span data-ttu-id="0a23f-135">.NET Framework에서 해당하는 형식은 <xref:System.Char?displayProperty=nameWithType> 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="0a23f-135">The corresponding type in the .NET Framework is the <xref:System.Char?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a23f-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0a23f-136">See Also</span></span>  
 <xref:System.Char?displayProperty=nameWithType>  
 <xref:Microsoft.VisualBasic.Strings.Asc%2A>  
 <xref:Microsoft.VisualBasic.Strings.AscW%2A>  
 <xref:Microsoft.VisualBasic.Strings.Chr%2A>  
 <xref:Microsoft.VisualBasic.Strings.ChrW%2A>  
 [<span data-ttu-id="0a23f-137">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="0a23f-137">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="0a23f-138">String 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="0a23f-138">String Data Type</span></span>](../../../visual-basic/language-reference/data-types/string-data-type.md)  
 [<span data-ttu-id="0a23f-139">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="0a23f-139">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="0a23f-140">변환 요약</span><span class="sxs-lookup"><span data-stu-id="0a23f-140">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="0a23f-141">방법: 부호 없는 형식을 사용하는 Windows 함수 호출</span><span class="sxs-lookup"><span data-stu-id="0a23f-141">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)  
 [<span data-ttu-id="0a23f-142">데이터 형식의 효율적 사용</span><span class="sxs-lookup"><span data-stu-id="0a23f-142">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
