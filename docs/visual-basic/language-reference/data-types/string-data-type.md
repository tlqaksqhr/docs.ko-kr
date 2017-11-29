---
title: "String 데이터 형식(Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.String
helpviewer_keywords:
- strings [Visual Basic], character
- strings [Visual Basic], fixed-length
- string keyword [Visual Basic]
- fixed-length strings [Visual Basic], string data type
- literals [Visual Basic], string
- text [Visual Basic], String data type
- $ identifier type character
- String data type
- fixed-length strings
- string literals [Visual Basic]
- data types [Visual Basic], assigning
- String literals [Visual Basic]
- identifier type characters [Visual Basic], $
ms.assetid: 15ac03f5-cabd-42cc-a754-1df3893c25d9
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 90f126a5cca36969617446e81a8d13434e39df75
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="string-data-type-visual-basic"></a><span data-ttu-id="a7a88-102">String 데이터 형식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a7a88-102">String Data Type (Visual Basic)</span></span>
<span data-ttu-id="a7a88-103">0에서 65535 까지의 값에서 부호 없는 16 비트 (2 바이트) 코드 포인트의 시퀀스를 범위에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7a88-103">Holds sequences of unsigned 16-bit (2-byte) code points that range in value from 0 through 65535.</span></span> <span data-ttu-id="a7a88-104">각 *코드 포인트*, 또는 문자 코드 단일 유니코드 문자를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a7a88-104">Each *code point*, or character code, represents a single Unicode character.</span></span> <span data-ttu-id="a7a88-105">0에서 약 2 십억 문자열로 포함할 수 있습니다 (2 ^31) 유니코드 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="a7a88-105">A string can contain from 0 to approximately two billion (2 ^ 31) Unicode characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a7a88-106">설명</span><span class="sxs-lookup"><span data-stu-id="a7a88-106">Remarks</span></span>  
 <span data-ttu-id="a7a88-107">사용 하 여는 `String` 배열 관리 오버 헤드 없이 여러 문자를 저장할 데이터 형식을 `Char()`, 배열을 `Char` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="a7a88-107">Use the `String` data type to hold multiple characters without the array management overhead of `Char()`, an array of `Char` elements.</span></span>  
  
 <span data-ttu-id="a7a88-108">기본값 `String` 은 `Nothing` (null 참조).</span><span class="sxs-lookup"><span data-stu-id="a7a88-108">The default value of `String` is `Nothing` (a null reference).</span></span> <span data-ttu-id="a7a88-109">이 하지 빈 문자열과 (값 `""`).</span><span class="sxs-lookup"><span data-stu-id="a7a88-109">Note that this is not the same as the empty string (value `""`).</span></span>  
  
## <a name="unicode-characters"></a><span data-ttu-id="a7a88-110">유니코드 문자</span><span class="sxs-lookup"><span data-stu-id="a7a88-110">Unicode Characters</span></span>  
 <span data-ttu-id="a7a88-111">유니코드는 첫 번째 128 개 코드 포인트 (0-127) 문자와 기호 미국 표준 키보드에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7a88-111">The first 128 code points (0–127) of Unicode correspond to the letters and symbols on a standard U.S. keyboard.</span></span> <span data-ttu-id="a7a88-112">이러한 128 개 코드 포인트는 ASCII 문자 집합에 정의 된 것과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7a88-112">These first 128 code points are the same as those the ASCII character set defines.</span></span> <span data-ttu-id="a7a88-113">두 번째 128 개 코드 포인트 (128-255) 라틴어 기반 알파벳 글자, 악센트, 통화 기호 및 조각 등의 특수 문자를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a7a88-113">The second 128 code points (128–255) represent special characters, such as Latin-based alphabet letters, accents, currency symbols, and fractions.</span></span> <span data-ttu-id="a7a88-114">유니코드는 다양 한 기호에 대 한 나머지 코드 포인트 (256-65535)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a7a88-114">Unicode uses the remaining code points (256-65535) for a wide variety of symbols.</span></span> <span data-ttu-id="a7a88-115">전 세계의 텍스트 문자, 분음 부호 및 수학 및 기술 기호가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7a88-115">This includes worldwide textual characters, diacritics, and mathematical and technical symbols.</span></span>  
  
 <span data-ttu-id="a7a88-116">와 같은 방법을 사용할 수 있습니다 <xref:System.Char.IsDigit%2A> 및 <xref:System.Char.IsPunctuation%2A> 개별 문자에는 `String` 유니코드 분류를 결정 하는 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="a7a88-116">You can use methods such as <xref:System.Char.IsDigit%2A> and <xref:System.Char.IsPunctuation%2A> on an individual character in a `String` variable to determine its Unicode classification.</span></span>  
  
## <a name="format-requirements"></a><span data-ttu-id="a7a88-117">형식 요구 사항</span><span class="sxs-lookup"><span data-stu-id="a7a88-117">Format Requirements</span></span>  
 <span data-ttu-id="a7a88-118">묶어야는 `String` 리터럴은 따옴표 (`" "`).</span><span class="sxs-lookup"><span data-stu-id="a7a88-118">You must enclose a `String` literal within quotation marks (`" "`).</span></span> <span data-ttu-id="a7a88-119">두 개의 연속 된 따옴표를 사용 하는 인용 부호는 문자열에 있는 문자 중 하나로 포함 해야 합니다 (`""`).</span><span class="sxs-lookup"><span data-stu-id="a7a88-119">If you must include a quotation mark as one of the characters in the string, you use two contiguous quotation marks (`""`).</span></span> <span data-ttu-id="a7a88-120">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="a7a88-120">The following example illustrates this.</span></span>  
  
```  
Dim j As String = "Joe said ""Hello"" to me."  
Dim h As String = "Hello"  
' The following messages all display the same thing:  
' "Joe said "Hello" to me."  
MsgBox(j)  
MsgBox("Joe said " & """" & h & """" & " to me.")  
MsgBox("Joe said """ & h & """ to me.")  
```  
  
 <span data-ttu-id="a7a88-121">문자열에 인용 부호를 나타내는 연속 인용 부호는 독립적으로 시작 되 고 종료 하는 따옴표는 `String` 리터럴.</span><span class="sxs-lookup"><span data-stu-id="a7a88-121">Note that the contiguous quotation marks that represent a quotation mark in the string are independent of the quotation marks that begin and end the `String` literal.</span></span>  
  
## <a name="string-manipulations"></a><span data-ttu-id="a7a88-122">문자열 조작</span><span class="sxs-lookup"><span data-stu-id="a7a88-122">String Manipulations</span></span>  
 <span data-ttu-id="a7a88-123">에 문자열을 할당 한 `String` 변수를 해당 문자열은 *변경할 수 없는*, 길이 또는 내용을 변경할 수 없습니다 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a7a88-123">Once you assign a string to a `String` variable, that string is *immutable*, which means you cannot change its length or contents.</span></span> <span data-ttu-id="a7a88-124">어떤 방식으로 문자열을 변경 하는 경우 Visual Basic 새 문자열을 만들고 이전을 중단 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7a88-124">When you alter a string in any way, Visual Basic creates a new string and abandons the previous one.</span></span> <span data-ttu-id="a7a88-125">`String` 다음 새 문자열 변수를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="a7a88-125">The `String` variable then points to the new string.</span></span>  
  
 <span data-ttu-id="a7a88-126">콘텐츠를 조작할 수는 `String` 다양 한 문자열 함수를 사용 하 여 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="a7a88-126">You can manipulate the contents of a `String` variable by using a variety of string functions.</span></span> <span data-ttu-id="a7a88-127">다음 예제는 <xref:Microsoft.VisualBasic.Strings.Left%2A> 함수</span><span class="sxs-lookup"><span data-stu-id="a7a88-127">The following example illustrates the <xref:Microsoft.VisualBasic.Strings.Left%2A> function</span></span>  
  
```  
Dim S As String = "Database"  
' The following statement sets S to a new string containing "Data".  
S = Microsoft.VisualBasic.Left(S, 4)  
```  
  
 <span data-ttu-id="a7a88-128">다른 구성 요소에서 만든 문자열 선행 또는 후행 공백 채워질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7a88-128">A string created by another component might be padded with leading or trailing spaces.</span></span> <span data-ttu-id="a7a88-129">이러한 문자열을 수신 하는 경우 사용할 수 있습니다는 <xref:Microsoft.VisualBasic.Strings.Trim%2A>, <xref:Microsoft.VisualBasic.Strings.LTrim%2A>, 및 <xref:Microsoft.VisualBasic.Strings.RTrim%2A> 이러한 공백을 제거 하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="a7a88-129">If you receive such a string, you can use the <xref:Microsoft.VisualBasic.Strings.Trim%2A>, <xref:Microsoft.VisualBasic.Strings.LTrim%2A>, and <xref:Microsoft.VisualBasic.Strings.RTrim%2A> functions to remove these spaces.</span></span>  
  
 <span data-ttu-id="a7a88-130">문자열 조작에 대 한 자세한 내용은 참조 [문자열](../../../visual-basic/programming-guide/language-features/strings/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a7a88-130">For more information about string manipulations, see [Strings](../../../visual-basic/programming-guide/language-features/strings/index.md).</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="a7a88-131">프로그래밍 팁</span><span class="sxs-lookup"><span data-stu-id="a7a88-131">Programming Tips</span></span>  
  
-   <span data-ttu-id="a7a88-132">**음수입니다.**</span><span class="sxs-lookup"><span data-stu-id="a7a88-132">**Negative Numbers.**</span></span> <span data-ttu-id="a7a88-133">보유 하는 문자 기억 `String` 서명 되지 않으며 음수 값을 나타낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a7a88-133">Remember that the characters held by `String` are unsigned and cannot represent negative values.</span></span> <span data-ttu-id="a7a88-134">사용 하지 않아야 어떤 경우 든, `String` 숫자 값을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7a88-134">In any case, you should not use `String` to hold numeric values.</span></span>  
  
-   <span data-ttu-id="a7a88-135">**Interop 고려 사항입니다.**</span><span class="sxs-lookup"><span data-stu-id="a7a88-135">**Interop Considerations.**</span></span> <span data-ttu-id="a7a88-136">.NET Framework에 대해 작성 되지 않은 구성 요소와 상호 작용 하는 경우 예제 Automation 또는 COM 개체에 대 한 기억 문자열 문자 다른 데이터 너비 (8 비트)에 있는 다른 환경에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7a88-136">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, remember that string characters have a different data width (8 bits) in other environments.</span></span> <span data-ttu-id="a7a88-137">이러한 구성 요소를 8 비트 문자는 문자열 인수를 전달 하는 경우로 선언 `Byte()`, 배열을 `Byte` 요소 대신 `String` 새 Visual Basic 코드에서.</span><span class="sxs-lookup"><span data-stu-id="a7a88-137">If you are passing a string argument of 8-bit characters to such a component, declare it as `Byte()`, an array of `Byte` elements, instead of `String` in your new Visual Basic code.</span></span>  
  
-   <span data-ttu-id="a7a88-138">**형식 문자입니다.**</span><span class="sxs-lookup"><span data-stu-id="a7a88-138">**Type Characters.**</span></span> <span data-ttu-id="a7a88-139">식별자 형식 문자 추가 `$` 를 식별자에 리터럴에 `String` 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a7a88-139">Appending the identifier type character `$` to any identifier forces it to the `String` data type.</span></span> <span data-ttu-id="a7a88-140">`String`에 리터럴 형식 문자가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a7a88-140">`String` has no literal type character.</span></span> <span data-ttu-id="a7a88-141">그러나 컴파일러가 처리 따옴표로 묶인 리터럴을 (`" "`)으로 `String`합니다.</span><span class="sxs-lookup"><span data-stu-id="a7a88-141">However, the compiler treats literals enclosed in quotation marks (`" "`) as `String`.</span></span>  
  
-   <span data-ttu-id="a7a88-142">**Framework 형식입니다.**</span><span class="sxs-lookup"><span data-stu-id="a7a88-142">**Framework Type.**</span></span> <span data-ttu-id="a7a88-143">.NET Framework에 있는 해당 형식이 고 <xref:System.String?displayProperty=nameWithType> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="a7a88-143">The corresponding type in the .NET Framework is the <xref:System.String?displayProperty=nameWithType> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7a88-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a7a88-144">See Also</span></span>  
 <xref:System.String?displayProperty=nameWithType>  
 [<span data-ttu-id="a7a88-145">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="a7a88-145">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="a7a88-146">Char 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="a7a88-146">Char Data Type</span></span>](../../../visual-basic/language-reference/data-types/char-data-type.md)  
 [<span data-ttu-id="a7a88-147">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="a7a88-147">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="a7a88-148">변환 요약</span><span class="sxs-lookup"><span data-stu-id="a7a88-148">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="a7a88-149">방법: 부호 없는 형식을 사용하는 Windows 함수 호출</span><span class="sxs-lookup"><span data-stu-id="a7a88-149">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)  
 [<span data-ttu-id="a7a88-150">데이터 형식의 효율적 사용</span><span class="sxs-lookup"><span data-stu-id="a7a88-150">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
