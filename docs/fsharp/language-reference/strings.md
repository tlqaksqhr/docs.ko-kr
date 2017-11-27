---
title: "문자열(F#)"
description: "F # 'string' 유형의 변경할 수 없는 텍스트의 유니코드 문자 시퀀스로 나타내는 하는 방법에 대해 알아봅니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: df7624e5-ca6c-4e77-9e2b-87ca7e5e6f52
ms.openlocfilehash: 96a398ebcd53681481b10d1a2bee5f1e5442a5cd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="strings"></a><span data-ttu-id="c9109-104">문자열</span><span class="sxs-lookup"><span data-stu-id="c9109-104">Strings</span></span>

> [!NOTE]
<span data-ttu-id="c9109-105">이 문서의 API 참조 링크를 통해 MSDN으로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9109-105">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="c9109-106">docs.microsoft.com API 참조가 완전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c9109-106">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="c9109-107">`string` 형식은 변경할 수 없는 텍스트를 일련의 유니코드 문자로 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c9109-107">The `string` type represents immutable text as a sequence of Unicode characters.</span></span> <span data-ttu-id="c9109-108">`string`은 .NET Framework에서 `System.String`의 별칭입니다.</span><span class="sxs-lookup"><span data-stu-id="c9109-108">`string` is an alias for `System.String` in the .NET Framework.</span></span>

## <a name="remarks"></a><span data-ttu-id="c9109-109">설명</span><span class="sxs-lookup"><span data-stu-id="c9109-109">Remarks</span></span>
<span data-ttu-id="c9109-110">문자열 리터럴은 따옴표 (") 문자로 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9109-110">String literals are delimited by the quotation mark (") character.</span></span> <span data-ttu-id="c9109-111">백슬래시 문자 (\) 특수 문자를 인코딩하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9109-111">The backslash character (\) is used to encode certain special characters.</span></span> <span data-ttu-id="c9109-112">백슬래시와 함께 다음 문자 라고는 *이스케이프 시퀀스*합니다.</span><span class="sxs-lookup"><span data-stu-id="c9109-112">The backslash and the next character together are known as an *escape sequence*.</span></span> <span data-ttu-id="c9109-113">이스케이프 시퀀스가 지원 F # 문자열 리터럴은 다음 표에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9109-113">Escape sequences supported in F# string literals are shown in the following table.</span></span>

|<span data-ttu-id="c9109-114">문자</span><span class="sxs-lookup"><span data-stu-id="c9109-114">Character</span></span>|<span data-ttu-id="c9109-115">이스케이프 시퀀스</span><span class="sxs-lookup"><span data-stu-id="c9109-115">Escape sequence</span></span>|
|---------|---------------|
|<span data-ttu-id="c9109-116">백스페이스</span><span class="sxs-lookup"><span data-stu-id="c9109-116">Backspace</span></span>|<span data-ttu-id="c9109-117">\b</span><span class="sxs-lookup"><span data-stu-id="c9109-117">\b</span></span>|
|<span data-ttu-id="c9109-118">줄 바꿈</span><span class="sxs-lookup"><span data-stu-id="c9109-118">Newline</span></span>|\n|
|<span data-ttu-id="c9109-119">캐리지 리턴</span><span class="sxs-lookup"><span data-stu-id="c9109-119">Carriage return</span></span>|<span data-ttu-id="c9109-120">\r</span><span class="sxs-lookup"><span data-stu-id="c9109-120">\r</span></span>|
|<span data-ttu-id="c9109-121">탭</span><span class="sxs-lookup"><span data-stu-id="c9109-121">Tab</span></span>|<span data-ttu-id="c9109-122">\t</span><span class="sxs-lookup"><span data-stu-id="c9109-122">\t</span></span>|
|<span data-ttu-id="c9109-123">백슬래시</span><span class="sxs-lookup"><span data-stu-id="c9109-123">Backslash</span></span>|\\|
|<span data-ttu-id="c9109-124">따옴표</span><span class="sxs-lookup"><span data-stu-id="c9109-124">Quotation mark</span></span>|\"|
|<span data-ttu-id="c9109-125">아포스트로피</span><span class="sxs-lookup"><span data-stu-id="c9109-125">Apostrophe</span></span>|\'|
|<span data-ttu-id="c9109-126">유니코드 문자</span><span class="sxs-lookup"><span data-stu-id="c9109-126">Unicode character</span></span>|<span data-ttu-id="c9109-127">\u*XXXX* 또는 \U*XXXXXXXX* (여기서 *X* 16 진수 숫자 나타냅니다)</span><span class="sxs-lookup"><span data-stu-id="c9109-127">\u*XXXX* or \U*XXXXXXXX* (where *X* indicates a hexadecimal digit)</span></span>|

<span data-ttu-id="c9109-128">앞에 @ 기호를 리터럴 축 자 문자열 (가) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9109-128">If preceded by the @ symbol, the literal is a verbatim string.</span></span> <span data-ttu-id="c9109-129">즉, 모든 이스케이프 시퀀스는 무시 제외 하 고 두 인용 부호 문자는 하나의 따옴표 문자로 해석 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9109-129">This means that any escape sequences are ignored, except that two quotation mark characters are interpreted as one quotation mark character.</span></span>

<span data-ttu-id="c9109-130">또한 문자열 삼중 따옴표로 묶을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9109-130">Additionally, a string may be enclosed by triple quotes.</span></span> <span data-ttu-id="c9109-131">이 경우 모든 이스케이프 시퀀스는 무시 큰따옴표 문자를 포함 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9109-131">In this case, all escape sequences are ignored, including double quotation mark characters.</span></span> <span data-ttu-id="c9109-132">포함 된 따옴표 붙은 문자열 포함 하는 문자열을 지정 하려면 축 자 문자열 또는 삼중 따옴표가 붙은 문자열 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9109-132">To specify a string that contains an embedded quoted string, you can either use a verbatim string or a triple-quoted string.</span></span> <span data-ttu-id="c9109-133">축 자 문자열을 사용 하면 단일 따옴표 문자를 나타내기 위해 두 개의 따옴표 문자를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9109-133">If you use a verbatim string, you  must specify two quotation mark characters to indicate a single quotation mark character.</span></span> <span data-ttu-id="c9109-134">삼중 따옴표가 붙은 문자열을 사용 하면 문자열의 끝으로 구문 분석 중인 없이도 단일 따옴표 문자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9109-134">If you use a triple-quoted string, you can use the single quotation mark characters without them being parsed as the end of the string.</span></span> <span data-ttu-id="c9109-135">XML 또는 포함 된 따옴표를 포함 하는 다른 구조를 사용 하 여 작업할 때이 방법이 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9109-135">This technique can be useful when you work with XML or other structures that include embedded quotation marks.</span></span>

```fsharp
// Using a verbatim string
let xmlFragment1 = @"<book author=""Milton, John"" title=""Paradise Lost"">"

// Using a triple-quoted string
let xmlFragment2 = """<book author="Milton, John" title="Paradise Lost">"""
```

<span data-ttu-id="c9109-136">코드에서 줄 바꿈이 포함 문자열이 허용 되는 고 줄 바꿈으로 해석 됩니다 문자 그대로 줄 바꿈 백슬래시 문자는 줄 바꿈 앞 마지막 문자가 하지 않는 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9109-136">In code, strings that have line breaks are accepted and the line breaks are interpreted literally as newlines, unless a backslash character is the last character before the line break.</span></span> <span data-ttu-id="c9109-137">백슬래시 문자를 사용할 때 다음 줄에서 선행 공백 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9109-137">Leading whitespace on the next line is ignored when the backslash character is used.</span></span> <span data-ttu-id="c9109-138">다음 코드에서는 문자열 `str1` 에 값을 갖는 `"abc\n     def"` 및 문자열 `str2` 에 값을 갖는 `"abcdef"`합니다.</span><span class="sxs-lookup"><span data-stu-id="c9109-138">The following code produces a string `str1` that has value `"abc\n     def"` and a string `str2` that has value `"abcdef"`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1001.fs)]

<span data-ttu-id="c9109-139">다음과 같이 배열 유사 구문을 사용 하 여 문자열의 문자들을 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9109-139">You can access individual characters in a string by using array-like syntax, as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1002.fs)]

<span data-ttu-id="c9109-140">출력은 `b`입니다.</span><span class="sxs-lookup"><span data-stu-id="c9109-140">The output is `b`.</span></span>

<span data-ttu-id="c9109-141">또는 다음 코드와 같이 배열 조각 구문을 사용 하 여 부분 문자열을 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9109-141">Or you can extract substrings by using array slice syntax, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1003.fs)]

<span data-ttu-id="c9109-142">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c9109-142">The output is as follows.</span></span>

```
abc
def
```

<span data-ttu-id="c9109-143">유형, 부호 없는 바이트의 배열에서 ASCII 문자열을 표현할 수 `byte[]`합니다.</span><span class="sxs-lookup"><span data-stu-id="c9109-143">You can represent ASCII strings by arrays of unsigned bytes, type `byte[]`.</span></span> <span data-ttu-id="c9109-144">접미사를 추가 `B` 문자열 리터럴로 ASCII 문자열 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c9109-144">You add the suffix `B` to a string literal to indicate that it is an ASCII string.</span></span> <span data-ttu-id="c9109-145">바이트 배열에서 사용 된 ASCII 문자열 리터럴은 유니코드 이스케이프 시퀀스를 제외한 유니코드 문자열로 같은 이스케이프 시퀀스를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9109-145">ASCII string literals used with byte arrays support the same escape sequences as Unicode strings, except for the Unicode escape sequences.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1004.fs)]
    
## <a name="string-operators"></a><span data-ttu-id="c9109-146">문자열 연산자</span><span class="sxs-lookup"><span data-stu-id="c9109-146">String Operators</span></span>
<span data-ttu-id="c9109-147">문자열을 연결 하는 방법은 두 가지가:를 사용 하 여는 `+` 연산자를 사용 하 여 또는 `^` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="c9109-147">There are two ways to concatenate strings: by using the `+` operator or by using the `^` operator.</span></span> <span data-ttu-id="c9109-148">`+` 연산자 기능을 처리 하는.NET Framework 문자열과 호환성이 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9109-148">The `+` operator maintains compatibility with the .NET Framework string handling features.</span></span>

<span data-ttu-id="c9109-149">다음 예제에서는 문자열을 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9109-149">The following example illustrates string concatenation.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1006.fs)]
    
## <a name="string-class"></a><span data-ttu-id="c9109-150">String 클래스</span><span class="sxs-lookup"><span data-stu-id="c9109-150">String Class</span></span>
<span data-ttu-id="c9109-151">F #에서 문자열 형식이.NET Framework 실제로 `System.String` 모든 입력은 `System.String` 멤버는 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9109-151">Because the string type in F# is actually a .NET Framework `System.String` type, all the `System.String` members are available.</span></span> <span data-ttu-id="c9109-152">여기에는 `+` 연산자를 사용 되는 문자열을 연결 하는 `Length` 속성 및 `Chars` 유니코드 문자 배열 문자열을 반환 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="c9109-152">This includes the `+` operator, which is used to concatenate strings, the `Length` property, and the `Chars` property, which returns the string as an array of Unicode characters.</span></span> <span data-ttu-id="c9109-153">문자열에 대 한 자세한 내용은 참조 `System.String`합니다.</span><span class="sxs-lookup"><span data-stu-id="c9109-153">For more information about strings, see `System.String`.</span></span>

<span data-ttu-id="c9109-154">사용 하 여는 `Chars` 속성 `System.String`, 다음 코드 에서처럼는 인덱스를 지정 하 여 문자열의 개별 문자를 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9109-154">By using the `Chars` property of `System.String`, you can access the individual characters in a string by specifying an index, as is shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1005.fs)]
    
## <a name="string-module"></a><span data-ttu-id="c9109-155">String 모듈</span><span class="sxs-lookup"><span data-stu-id="c9109-155">String Module</span></span>
<span data-ttu-id="c9109-156">문자열 처리에 대 한 추가 기능에 포함 되어는 `String` 모듈에는 `FSharp.Core` 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="c9109-156">Additional functionality for string handling is included in the `String` module in the `FSharp.Core` namespace.</span></span> <span data-ttu-id="c9109-157">자세한 내용은 참조 [Core.String 모듈](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d)합니다.</span><span class="sxs-lookup"><span data-stu-id="c9109-157">For more information, see [Core.String Module](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).</span></span>

## <a name="see-also"></a><span data-ttu-id="c9109-158">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c9109-158">See Also</span></span>
[<span data-ttu-id="c9109-159">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="c9109-159">F# Language Reference</span></span>](index.md)
