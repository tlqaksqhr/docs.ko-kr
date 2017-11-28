---
title: "리터럴(F#)"
description: "F # 프로그래밍 언어의 리터럴 형식에 알아봅니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 4b1d6e9d-f933-4cd4-966d-d643152c27e4
ms.openlocfilehash: 6bb1f233b6846e226c4e73aee00b8cf77735fe2d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="literals"></a><span data-ttu-id="c761d-104">리터럴</span><span class="sxs-lookup"><span data-stu-id="c761d-104">Literals</span></span>

> [!NOTE]
<span data-ttu-id="c761d-105">이 문서에서 API 참조 링크 이동 합니다 msdn (당분간).</span><span class="sxs-lookup"><span data-stu-id="c761d-105">The API reference links in this article will take you to MSDN (for now).</span></span>

<span data-ttu-id="c761d-106">이 항목에서는 F # 리터럴 형식을 지정 하는 방법을 보여 주는 표를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c761d-106">This topic provides a table that shows how to specify the type of a literal in F#.</span></span>

## <a name="literal-types"></a><span data-ttu-id="c761d-107">리터럴 형식</span><span class="sxs-lookup"><span data-stu-id="c761d-107">Literal Types</span></span>
<span data-ttu-id="c761d-108">다음 표에서 F #에서 리터럴 형식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c761d-108">The following table shows the literal types in F#.</span></span> <span data-ttu-id="c761d-109">16 진수 표기법으로 숫자를 나타내는 문자는 대/소문자 구분; 됩니다. 문자 형식을 식별 하는 대/소문자를 구분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c761d-109">Characters that represent digits in hexadecimal notation are not case-sensitive; characters that identify the type are case-sensitive.</span></span>

|<span data-ttu-id="c761d-110">형식</span><span class="sxs-lookup"><span data-stu-id="c761d-110">Type</span></span>|<span data-ttu-id="c761d-111">설명</span><span class="sxs-lookup"><span data-stu-id="c761d-111">Description</span></span>|<span data-ttu-id="c761d-112">접두사 또는 접미사</span><span class="sxs-lookup"><span data-stu-id="c761d-112">Suffix or prefix</span></span>|<span data-ttu-id="c761d-113">예제</span><span class="sxs-lookup"><span data-stu-id="c761d-113">Examples</span></span>|
|----|-----------|----------------|--------|
|<span data-ttu-id="c761d-114">sbyte</span><span class="sxs-lookup"><span data-stu-id="c761d-114">sbyte</span></span>|<span data-ttu-id="c761d-115">부호 있는 8 비트 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="c761d-115">signed 8-bit integer</span></span>|<span data-ttu-id="c761d-116">y</span><span class="sxs-lookup"><span data-stu-id="c761d-116">y</span></span>|`86y`<br /><br />`0b00000101y`|
|<span data-ttu-id="c761d-117">byte</span><span class="sxs-lookup"><span data-stu-id="c761d-117">byte</span></span>|<span data-ttu-id="c761d-118">부호 없는 8 비트 자연 수</span><span class="sxs-lookup"><span data-stu-id="c761d-118">unsigned 8-bit natural number</span></span>|<span data-ttu-id="c761d-119">uy</span><span class="sxs-lookup"><span data-stu-id="c761d-119">uy</span></span>|`86uy`<br /><br />`0b00000101uy`|
|<span data-ttu-id="c761d-120">int16</span><span class="sxs-lookup"><span data-stu-id="c761d-120">int16</span></span>|<span data-ttu-id="c761d-121">부호 있는 16 비트 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="c761d-121">signed 16-bit integer</span></span>|<span data-ttu-id="c761d-122">s</span><span class="sxs-lookup"><span data-stu-id="c761d-122">s</span></span>|`86s`|
|<span data-ttu-id="c761d-123">uint16</span><span class="sxs-lookup"><span data-stu-id="c761d-123">uint16</span></span>|<span data-ttu-id="c761d-124">부호 없는 16 비트 자연 수</span><span class="sxs-lookup"><span data-stu-id="c761d-124">unsigned 16-bit natural number</span></span>|<span data-ttu-id="c761d-125">us</span><span class="sxs-lookup"><span data-stu-id="c761d-125">us</span></span>|`86us`|
|<span data-ttu-id="c761d-126">int</span><span class="sxs-lookup"><span data-stu-id="c761d-126">int</span></span><br /><br /><span data-ttu-id="c761d-127">int32</span><span class="sxs-lookup"><span data-stu-id="c761d-127">int32</span></span>|<span data-ttu-id="c761d-128">부호 있는 32 비트 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="c761d-128">signed 32-bit integer</span></span>|<span data-ttu-id="c761d-129">l 또는 없음</span><span class="sxs-lookup"><span data-stu-id="c761d-129">l or none</span></span>|`86`<br /><br />`86l`|
|<span data-ttu-id="c761d-130">uint</span><span class="sxs-lookup"><span data-stu-id="c761d-130">uint</span></span><br /><br /><span data-ttu-id="c761d-131">uint32</span><span class="sxs-lookup"><span data-stu-id="c761d-131">uint32</span></span>|<span data-ttu-id="c761d-132">부호 없는 32 비트 자연 수</span><span class="sxs-lookup"><span data-stu-id="c761d-132">unsigned 32-bit natural number</span></span>|<span data-ttu-id="c761d-133">u 또는 u l</span><span class="sxs-lookup"><span data-stu-id="c761d-133">u or ul</span></span>|`86u`<br /><br />`86ul`|
|<span data-ttu-id="c761d-134">unativeint</span><span class="sxs-lookup"><span data-stu-id="c761d-134">unativeint</span></span>|<span data-ttu-id="c761d-135">부호 없는 자연 숫자로 네이티브 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c761d-135">native pointer as an unsigned natural number</span></span>|<span data-ttu-id="c761d-136">취소</span><span class="sxs-lookup"><span data-stu-id="c761d-136">un</span></span>|`0x00002D3Fun`|
|<span data-ttu-id="c761d-137">int64</span><span class="sxs-lookup"><span data-stu-id="c761d-137">int64</span></span>|<span data-ttu-id="c761d-138">부호 있는 64 비트 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="c761d-138">signed 64-bit integer</span></span>|<span data-ttu-id="c761d-139">L</span><span class="sxs-lookup"><span data-stu-id="c761d-139">L</span></span>|`86L`|
|<span data-ttu-id="c761d-140">uint64</span><span class="sxs-lookup"><span data-stu-id="c761d-140">uint64</span></span>|<span data-ttu-id="c761d-141">부호 없는 64 비트 자연 수</span><span class="sxs-lookup"><span data-stu-id="c761d-141">unsigned 64-bit natural number</span></span>|<span data-ttu-id="c761d-142">UL</span><span class="sxs-lookup"><span data-stu-id="c761d-142">UL</span></span>|`86UL`|
|<span data-ttu-id="c761d-143">단일, float32</span><span class="sxs-lookup"><span data-stu-id="c761d-143">single, float32</span></span>|<span data-ttu-id="c761d-144">32 비트 부동 소수점 숫자</span><span class="sxs-lookup"><span data-stu-id="c761d-144">32-bit floating point number</span></span>|<span data-ttu-id="c761d-145">F 또는 f</span><span class="sxs-lookup"><span data-stu-id="c761d-145">F or f</span></span>|<span data-ttu-id="c761d-146">`4.14F` 또는 `4.14f`</span><span class="sxs-lookup"><span data-stu-id="c761d-146">`4.14F` or `4.14f`</span></span>|
|||<span data-ttu-id="c761d-147">lf</span><span class="sxs-lookup"><span data-stu-id="c761d-147">lf</span></span>|`0x00000000lf`|
|<span data-ttu-id="c761d-148">float이 고 double</span><span class="sxs-lookup"><span data-stu-id="c761d-148">float; double</span></span>|<span data-ttu-id="c761d-149">64 비트 부동 소수점 숫자</span><span class="sxs-lookup"><span data-stu-id="c761d-149">64-bit floating point number</span></span>|<span data-ttu-id="c761d-150">없음</span><span class="sxs-lookup"><span data-stu-id="c761d-150">none</span></span>|<span data-ttu-id="c761d-151">`4.14`, `2.3E+32` 또는 `2.3e+32`</span><span class="sxs-lookup"><span data-stu-id="c761d-151">`4.14` or `2.3E+32` or `2.3e+32`</span></span>|
|||<span data-ttu-id="c761d-152">LF</span><span class="sxs-lookup"><span data-stu-id="c761d-152">LF</span></span>|`0x0000000000000000LF`|
|<span data-ttu-id="c761d-153">bigint</span><span class="sxs-lookup"><span data-stu-id="c761d-153">bigint</span></span>|<span data-ttu-id="c761d-154">64 비트 표현에 제한 되지 않는 정수</span><span class="sxs-lookup"><span data-stu-id="c761d-154">integer not limited to 64-bit representation</span></span>|<span data-ttu-id="c761d-155">I</span><span class="sxs-lookup"><span data-stu-id="c761d-155">I</span></span>|`9999999999999999999999999999I`|
|<span data-ttu-id="c761d-156">decimal</span><span class="sxs-lookup"><span data-stu-id="c761d-156">decimal</span></span>|<span data-ttu-id="c761d-157">고정된 소수점 또는 유리수도 표현 되는 소수</span><span class="sxs-lookup"><span data-stu-id="c761d-157">fractional number represented as a fixed point or rational number</span></span>|<span data-ttu-id="c761d-158">M 또는 m</span><span class="sxs-lookup"><span data-stu-id="c761d-158">M or m</span></span>|<span data-ttu-id="c761d-159">`0.7833M` 또는 `0.7833m`</span><span class="sxs-lookup"><span data-stu-id="c761d-159">`0.7833M` or `0.7833m`</span></span>|
|<span data-ttu-id="c761d-160">Char</span><span class="sxs-lookup"><span data-stu-id="c761d-160">Char</span></span>|<span data-ttu-id="c761d-161">유니코드 문자</span><span class="sxs-lookup"><span data-stu-id="c761d-161">Unicode character</span></span>|<span data-ttu-id="c761d-162">없음</span><span class="sxs-lookup"><span data-stu-id="c761d-162">none</span></span>|`'a'`|
|<span data-ttu-id="c761d-163">문자열</span><span class="sxs-lookup"><span data-stu-id="c761d-163">String</span></span>|<span data-ttu-id="c761d-164">유니코드 문자열</span><span class="sxs-lookup"><span data-stu-id="c761d-164">Unicode string</span></span>|<span data-ttu-id="c761d-165">없음</span><span class="sxs-lookup"><span data-stu-id="c761d-165">none</span></span>|`"text\n"`<br /><br /><span data-ttu-id="c761d-166">또는</span><span class="sxs-lookup"><span data-stu-id="c761d-166">or</span></span><br /><br />`@"c:\filename"`<br /><br /><span data-ttu-id="c761d-167">또는</span><span class="sxs-lookup"><span data-stu-id="c761d-167">or</span></span><br /><br />`"""<book title="Paradise Lost">"""`<br /><br /><span data-ttu-id="c761d-168">또는</span><span class="sxs-lookup"><span data-stu-id="c761d-168">or</span></span><br /><br />`"string1" + "string2"`<br /><br /><span data-ttu-id="c761d-169">참고 항목 [문자열](Strings.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c761d-169">See also [Strings](Strings.md).</span></span>|
|<span data-ttu-id="c761d-170">byte</span><span class="sxs-lookup"><span data-stu-id="c761d-170">byte</span></span>|<span data-ttu-id="c761d-171">ASCII 문자</span><span class="sxs-lookup"><span data-stu-id="c761d-171">ASCII character</span></span>|<span data-ttu-id="c761d-172">B</span><span class="sxs-lookup"><span data-stu-id="c761d-172">B</span></span>|`'a'B`|
|<span data-ttu-id="c761d-173">byte[]</span><span class="sxs-lookup"><span data-stu-id="c761d-173">byte[]</span></span>|<span data-ttu-id="c761d-174">ASCII 문자열</span><span class="sxs-lookup"><span data-stu-id="c761d-174">ASCII string</span></span>|<span data-ttu-id="c761d-175">B</span><span class="sxs-lookup"><span data-stu-id="c761d-175">B</span></span>|`"text"B`|
|<span data-ttu-id="c761d-176">String 또는 byte]</span><span class="sxs-lookup"><span data-stu-id="c761d-176">String or byte[]</span></span>|<span data-ttu-id="c761d-177">축 자 문자열</span><span class="sxs-lookup"><span data-stu-id="c761d-177">verbatim string</span></span>|<span data-ttu-id="c761d-178">@ 접두사</span><span class="sxs-lookup"><span data-stu-id="c761d-178">@ prefix</span></span>|<span data-ttu-id="c761d-179">`@"\\server\share"`(유니코드)</span><span class="sxs-lookup"><span data-stu-id="c761d-179">`@"\\server\share"` (Unicode)</span></span><br /><br /><span data-ttu-id="c761d-180">`@"\\server\share"B`(ASCII)</span><span class="sxs-lookup"><span data-stu-id="c761d-180">`@"\\server\share"B` (ASCII)</span></span>|

## <a name="remarks"></a><span data-ttu-id="c761d-181">설명</span><span class="sxs-lookup"><span data-stu-id="c761d-181">Remarks</span></span>
<span data-ttu-id="c761d-182">유니코드 문자열에 명시적 인코딩을 사용 하 여 지정할 수 있는 포함 될 수 있습니다 `\u` 뒤에 16 비트 16 진수 코드 또는 utf-32 인코딩을 사용 하 여 지정할 수 있는 `\U` 뒤에 유니코드를 나타내는 32 비트 16 진수 코드 서로게이트 쌍입니다.</span><span class="sxs-lookup"><span data-stu-id="c761d-182">Unicode strings can contain explicit encodings that you can specify by using `\u` followed by a 16-bit hexadecimal code or UTF-32 encodings that you can specify by using `\U` followed by a 32-bit hexadecimal code that represents a Unicode surrogate pair.</span></span>

<span data-ttu-id="c761d-183">F # 3.1을 기준으로 사용할 수 있습니다는 `+` 문자열 리터럴을 결합 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c761d-183">As of F# 3.1, you can use the `+` sign to combine string literals.</span></span> <span data-ttu-id="c761d-184">비트 사용할 수 또는 (`|||`) 열거형 플래그를 결합 하는 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="c761d-184">You can also use the bitwise or (`|||`) operator to combine enum flags.</span></span> <span data-ttu-id="c761d-185">예를 들어 다음 코드는 올바른 F # 3.1에서:</span><span class="sxs-lookup"><span data-stu-id="c761d-185">For example, the following code is legal in F# 3.1:</span></span>

```fsharp
[<Literal>]
let Literal1 = "a" + "b"

[<Literal>]
let FileLocation =   __SOURCE_DIRECTORY__ + "/" + __SOURCE_FILE__

[<Literal>]
let Literal2 = 1 ||| 64

[<Literal>]
let Literal3 = System.IO.FileAccess.Read ||| System.IO.FileAccess.Write
```

<span data-ttu-id="c761d-186">다른 비트 연산자의 사용이 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c761d-186">The use of other bitwise operators isn't allowed.</span></span>


## <a name="named-literals"></a><span data-ttu-id="c761d-187">명명 된 리터럴</span><span class="sxs-lookup"><span data-stu-id="c761d-187">Named Literals</span></span>
<span data-ttu-id="c761d-188">로 상수 있어야 하는 값을 표시할 수 있습니다는 [리터럴](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="c761d-188">Values that are intended to be constants can be marked with the [Literal](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) attribute.</span></span> <span data-ttu-id="c761d-189">이 특성을 상수로 컴파일할 사용 하면 값의 효과 가집니다.</span><span class="sxs-lookup"><span data-stu-id="c761d-189">This attribute has the effect of causing a value to be compiled as a constant.</span></span>

<span data-ttu-id="c761d-190">패턴 일치 식에서 소문자로 시작 하는 식별자는 항상 변수를 바인딩할 수으로 처리 하지 않고 리터럴로 하므로 일반적으로 사용 해야 문자가 대문자 리터럴을 정의할 때.</span><span class="sxs-lookup"><span data-stu-id="c761d-190">In pattern matching expressions, identifiers that begin with lowercase characters are always treated as variables to be bound, rather than as literals, so you should generally use initial capitals when you define literals.</span></span>

## <a name="integers-in-other-bases"></a><span data-ttu-id="c761d-191">다른 밑에 있는 정수</span><span class="sxs-lookup"><span data-stu-id="c761d-191">Integers In Other Bases</span></span>

<span data-ttu-id="c761d-192">사용 하 여 16 진수, 8 진수 또는 이진에서 부호 있는 32 비트 정수로 지정 될 수도 있습니다는 `0x`, `0o` 또는 `0b` 각각 접두사입니다.</span><span class="sxs-lookup"><span data-stu-id="c761d-192">Signed 32-bit integers can also be specified in hexadecimal, octal, or binary using a `0x`, `0o` or `0b` prefix respectively.</span></span>

```fsharp
let Numbers = (0x9F, 0o77, 0b1010)
// Result: Numbers : int * int * int = (159, 63, 10)
```

## <a name="underscores-in-numeric-literals"></a><span data-ttu-id="c761d-193">숫자 리터럴에 밑줄이</span><span class="sxs-lookup"><span data-stu-id="c761d-193">Underscores in Numeric Literals</span></span>

<span data-ttu-id="c761d-194">F # 4.1 부터는 구분할 수 있습니다 자리는 밑줄 문자 (`_`).</span><span class="sxs-lookup"><span data-stu-id="c761d-194">Starting with F# 4.1, you can separate digits with the underscore character (`_`).</span></span>

```fsharp
let DeadBeef = 0xDEAD_BEEF

let DeadBeefAsBits = 0b1101_1110_1010_1101_1011_1110_1110_1111

let ExampleSSN = 123_456_7890
```

## <a name="see-also"></a><span data-ttu-id="c761d-195">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c761d-195">See Also</span></span>

[<span data-ttu-id="c761d-196">Core.LiteralAttribute 클래스</span><span class="sxs-lookup"><span data-stu-id="c761d-196">Core.LiteralAttribute Class</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.literalattribute-class-%5bfsharp%5d)
