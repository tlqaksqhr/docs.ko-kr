---
title: 리터럴(F#)
description: 'F # 프로그래밍 언어의 리터럴 형식에 알아봅니다.'
ms.date: 05/16/2016
ms.openlocfilehash: f28ca0ae7a0b092bbc039d23625b883faffd241c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33564341"
---
# <a name="literals"></a><span data-ttu-id="d23b9-103">리터럴</span><span class="sxs-lookup"><span data-stu-id="d23b9-103">Literals</span></span>

> [!NOTE]
<span data-ttu-id="d23b9-104">이 문서에서 API 참조 링크 이동 합니다 msdn (당분간).</span><span class="sxs-lookup"><span data-stu-id="d23b9-104">The API reference links in this article will take you to MSDN (for now).</span></span>

<span data-ttu-id="d23b9-105">이 항목에서는 F # 리터럴 형식을 지정 하는 방법을 보여 주는 표를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d23b9-105">This topic provides a table that shows how to specify the type of a literal in F#.</span></span>

## <a name="literal-types"></a><span data-ttu-id="d23b9-106">리터럴 형식</span><span class="sxs-lookup"><span data-stu-id="d23b9-106">Literal Types</span></span>
<span data-ttu-id="d23b9-107">다음 표에서 F #에서 리터럴 형식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d23b9-107">The following table shows the literal types in F#.</span></span> <span data-ttu-id="d23b9-108">16 진수 표기법으로 숫자를 나타내는 문자는 대/소문자 구분; 됩니다. 문자 형식을 식별 하는 대/소문자를 구분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d23b9-108">Characters that represent digits in hexadecimal notation are not case-sensitive; characters that identify the type are case-sensitive.</span></span>

|<span data-ttu-id="d23b9-109">형식</span><span class="sxs-lookup"><span data-stu-id="d23b9-109">Type</span></span>|<span data-ttu-id="d23b9-110">설명</span><span class="sxs-lookup"><span data-stu-id="d23b9-110">Description</span></span>|<span data-ttu-id="d23b9-111">접두사 또는 접미사</span><span class="sxs-lookup"><span data-stu-id="d23b9-111">Suffix or prefix</span></span>|<span data-ttu-id="d23b9-112">예제</span><span class="sxs-lookup"><span data-stu-id="d23b9-112">Examples</span></span>|
|----|-----------|----------------|--------|
|<span data-ttu-id="d23b9-113">sbyte</span><span class="sxs-lookup"><span data-stu-id="d23b9-113">sbyte</span></span>|<span data-ttu-id="d23b9-114">부호 있는 8 비트 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="d23b9-114">signed 8-bit integer</span></span>|<span data-ttu-id="d23b9-115">y</span><span class="sxs-lookup"><span data-stu-id="d23b9-115">y</span></span>|`86y`<br /><br />`0b00000101y`|
|<span data-ttu-id="d23b9-116">byte</span><span class="sxs-lookup"><span data-stu-id="d23b9-116">byte</span></span>|<span data-ttu-id="d23b9-117">부호 없는 8 비트 자연 수</span><span class="sxs-lookup"><span data-stu-id="d23b9-117">unsigned 8-bit natural number</span></span>|<span data-ttu-id="d23b9-118">uy</span><span class="sxs-lookup"><span data-stu-id="d23b9-118">uy</span></span>|`86uy`<br /><br />`0b00000101uy`|
|<span data-ttu-id="d23b9-119">int16</span><span class="sxs-lookup"><span data-stu-id="d23b9-119">int16</span></span>|<span data-ttu-id="d23b9-120">부호 있는 16 비트 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="d23b9-120">signed 16-bit integer</span></span>|<span data-ttu-id="d23b9-121">s</span><span class="sxs-lookup"><span data-stu-id="d23b9-121">s</span></span>|`86s`|
|<span data-ttu-id="d23b9-122">uint16</span><span class="sxs-lookup"><span data-stu-id="d23b9-122">uint16</span></span>|<span data-ttu-id="d23b9-123">부호 없는 16 비트 자연 수</span><span class="sxs-lookup"><span data-stu-id="d23b9-123">unsigned 16-bit natural number</span></span>|<span data-ttu-id="d23b9-124">us</span><span class="sxs-lookup"><span data-stu-id="d23b9-124">us</span></span>|`86us`|
|<span data-ttu-id="d23b9-125">int</span><span class="sxs-lookup"><span data-stu-id="d23b9-125">int</span></span><br /><br /><span data-ttu-id="d23b9-126">int32</span><span class="sxs-lookup"><span data-stu-id="d23b9-126">int32</span></span>|<span data-ttu-id="d23b9-127">부호 있는 32 비트 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="d23b9-127">signed 32-bit integer</span></span>|<span data-ttu-id="d23b9-128">l 또는 없음</span><span class="sxs-lookup"><span data-stu-id="d23b9-128">l or none</span></span>|`86`<br /><br />`86l`|
|<span data-ttu-id="d23b9-129">uint</span><span class="sxs-lookup"><span data-stu-id="d23b9-129">uint</span></span><br /><br /><span data-ttu-id="d23b9-130">uint32</span><span class="sxs-lookup"><span data-stu-id="d23b9-130">uint32</span></span>|<span data-ttu-id="d23b9-131">부호 없는 32 비트 자연 수</span><span class="sxs-lookup"><span data-stu-id="d23b9-131">unsigned 32-bit natural number</span></span>|<span data-ttu-id="d23b9-132">u 또는 u l</span><span class="sxs-lookup"><span data-stu-id="d23b9-132">u or ul</span></span>|`86u`<br /><br />`86ul`|
|<span data-ttu-id="d23b9-133">unativeint</span><span class="sxs-lookup"><span data-stu-id="d23b9-133">unativeint</span></span>|<span data-ttu-id="d23b9-134">부호 없는 자연 숫자로 네이티브 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d23b9-134">native pointer as an unsigned natural number</span></span>|<span data-ttu-id="d23b9-135">취소</span><span class="sxs-lookup"><span data-stu-id="d23b9-135">un</span></span>|`0x00002D3Fun`|
|<span data-ttu-id="d23b9-136">int64</span><span class="sxs-lookup"><span data-stu-id="d23b9-136">int64</span></span>|<span data-ttu-id="d23b9-137">부호 있는 64 비트 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="d23b9-137">signed 64-bit integer</span></span>|<span data-ttu-id="d23b9-138">L</span><span class="sxs-lookup"><span data-stu-id="d23b9-138">L</span></span>|`86L`|
|<span data-ttu-id="d23b9-139">uint64</span><span class="sxs-lookup"><span data-stu-id="d23b9-139">uint64</span></span>|<span data-ttu-id="d23b9-140">부호 없는 64 비트 자연 수</span><span class="sxs-lookup"><span data-stu-id="d23b9-140">unsigned 64-bit natural number</span></span>|<span data-ttu-id="d23b9-141">UL</span><span class="sxs-lookup"><span data-stu-id="d23b9-141">UL</span></span>|`86UL`|
|<span data-ttu-id="d23b9-142">단일, float32</span><span class="sxs-lookup"><span data-stu-id="d23b9-142">single, float32</span></span>|<span data-ttu-id="d23b9-143">32 비트 부동 소수점 숫자</span><span class="sxs-lookup"><span data-stu-id="d23b9-143">32-bit floating point number</span></span>|<span data-ttu-id="d23b9-144">F 또는 f</span><span class="sxs-lookup"><span data-stu-id="d23b9-144">F or f</span></span>|<span data-ttu-id="d23b9-145">`4.14F` 또는 `4.14f`</span><span class="sxs-lookup"><span data-stu-id="d23b9-145">`4.14F` or `4.14f`</span></span>|
|||<span data-ttu-id="d23b9-146">lf</span><span class="sxs-lookup"><span data-stu-id="d23b9-146">lf</span></span>|`0x00000000lf`|
|<span data-ttu-id="d23b9-147">float이 고 double</span><span class="sxs-lookup"><span data-stu-id="d23b9-147">float; double</span></span>|<span data-ttu-id="d23b9-148">64 비트 부동 소수점 숫자</span><span class="sxs-lookup"><span data-stu-id="d23b9-148">64-bit floating point number</span></span>|<span data-ttu-id="d23b9-149">없음</span><span class="sxs-lookup"><span data-stu-id="d23b9-149">none</span></span>|<span data-ttu-id="d23b9-150">`4.14`, `2.3E+32` 또는 `2.3e+32`</span><span class="sxs-lookup"><span data-stu-id="d23b9-150">`4.14` or `2.3E+32` or `2.3e+32`</span></span>|
|||<span data-ttu-id="d23b9-151">LF</span><span class="sxs-lookup"><span data-stu-id="d23b9-151">LF</span></span>|`0x0000000000000000LF`|
|<span data-ttu-id="d23b9-152">bigint</span><span class="sxs-lookup"><span data-stu-id="d23b9-152">bigint</span></span>|<span data-ttu-id="d23b9-153">64 비트 표현에 제한 되지 않는 정수</span><span class="sxs-lookup"><span data-stu-id="d23b9-153">integer not limited to 64-bit representation</span></span>|<span data-ttu-id="d23b9-154">I</span><span class="sxs-lookup"><span data-stu-id="d23b9-154">I</span></span>|`9999999999999999999999999999I`|
|<span data-ttu-id="d23b9-155">decimal</span><span class="sxs-lookup"><span data-stu-id="d23b9-155">decimal</span></span>|<span data-ttu-id="d23b9-156">고정된 소수점 또는 유리수도 표현 되는 소수</span><span class="sxs-lookup"><span data-stu-id="d23b9-156">fractional number represented as a fixed point or rational number</span></span>|<span data-ttu-id="d23b9-157">M 또는 m</span><span class="sxs-lookup"><span data-stu-id="d23b9-157">M or m</span></span>|<span data-ttu-id="d23b9-158">`0.7833M` 또는 `0.7833m`</span><span class="sxs-lookup"><span data-stu-id="d23b9-158">`0.7833M` or `0.7833m`</span></span>|
|<span data-ttu-id="d23b9-159">Char</span><span class="sxs-lookup"><span data-stu-id="d23b9-159">Char</span></span>|<span data-ttu-id="d23b9-160">유니코드 문자</span><span class="sxs-lookup"><span data-stu-id="d23b9-160">Unicode character</span></span>|<span data-ttu-id="d23b9-161">없음</span><span class="sxs-lookup"><span data-stu-id="d23b9-161">none</span></span>|`'a'`|
|<span data-ttu-id="d23b9-162">문자열</span><span class="sxs-lookup"><span data-stu-id="d23b9-162">String</span></span>|<span data-ttu-id="d23b9-163">유니코드 문자열</span><span class="sxs-lookup"><span data-stu-id="d23b9-163">Unicode string</span></span>|<span data-ttu-id="d23b9-164">없음</span><span class="sxs-lookup"><span data-stu-id="d23b9-164">none</span></span>|`"text\n"`<br /><br /><span data-ttu-id="d23b9-165">또는</span><span class="sxs-lookup"><span data-stu-id="d23b9-165">or</span></span><br /><br />`@"c:\filename"`<br /><br /><span data-ttu-id="d23b9-166">또는</span><span class="sxs-lookup"><span data-stu-id="d23b9-166">or</span></span><br /><br />`"""<book title="Paradise Lost">"""`<br /><br /><span data-ttu-id="d23b9-167">또는</span><span class="sxs-lookup"><span data-stu-id="d23b9-167">or</span></span><br /><br />`"string1" + "string2"`<br /><br /><span data-ttu-id="d23b9-168">참고 항목 [문자열](Strings.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d23b9-168">See also [Strings](Strings.md).</span></span>|
|<span data-ttu-id="d23b9-169">byte</span><span class="sxs-lookup"><span data-stu-id="d23b9-169">byte</span></span>|<span data-ttu-id="d23b9-170">ASCII 문자</span><span class="sxs-lookup"><span data-stu-id="d23b9-170">ASCII character</span></span>|<span data-ttu-id="d23b9-171">B</span><span class="sxs-lookup"><span data-stu-id="d23b9-171">B</span></span>|`'a'B`|
|<span data-ttu-id="d23b9-172">byte[]</span><span class="sxs-lookup"><span data-stu-id="d23b9-172">byte[]</span></span>|<span data-ttu-id="d23b9-173">ASCII 문자열</span><span class="sxs-lookup"><span data-stu-id="d23b9-173">ASCII string</span></span>|<span data-ttu-id="d23b9-174">B</span><span class="sxs-lookup"><span data-stu-id="d23b9-174">B</span></span>|`"text"B`|
|<span data-ttu-id="d23b9-175">String 또는 byte]</span><span class="sxs-lookup"><span data-stu-id="d23b9-175">String or byte[]</span></span>|<span data-ttu-id="d23b9-176">축 자 문자열</span><span class="sxs-lookup"><span data-stu-id="d23b9-176">verbatim string</span></span>|<span data-ttu-id="d23b9-177">@ 접두사</span><span class="sxs-lookup"><span data-stu-id="d23b9-177">@ prefix</span></span>|<span data-ttu-id="d23b9-178">`@"\\server\share"` (유니코드)</span><span class="sxs-lookup"><span data-stu-id="d23b9-178">`@"\\server\share"` (Unicode)</span></span><br /><br /><span data-ttu-id="d23b9-179">`@"\\server\share"B` (ASCII)</span><span class="sxs-lookup"><span data-stu-id="d23b9-179">`@"\\server\share"B` (ASCII)</span></span>|

## <a name="remarks"></a><span data-ttu-id="d23b9-180">설명</span><span class="sxs-lookup"><span data-stu-id="d23b9-180">Remarks</span></span>
<span data-ttu-id="d23b9-181">유니코드 문자열에 명시적 인코딩을 사용 하 여 지정할 수 있는 포함 될 수 있습니다 `\u` 뒤에 16 비트 16 진수 코드 또는 utf-32 인코딩을 사용 하 여 지정할 수 있는 `\U` 뒤에 유니코드를 나타내는 32 비트 16 진수 코드 서로게이트 쌍입니다.</span><span class="sxs-lookup"><span data-stu-id="d23b9-181">Unicode strings can contain explicit encodings that you can specify by using `\u` followed by a 16-bit hexadecimal code or UTF-32 encodings that you can specify by using `\U` followed by a 32-bit hexadecimal code that represents a Unicode surrogate pair.</span></span>

<span data-ttu-id="d23b9-182">F # 3.1을 기준으로 사용할 수 있습니다는 `+` 문자열 리터럴을 결합 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d23b9-182">As of F# 3.1, you can use the `+` sign to combine string literals.</span></span> <span data-ttu-id="d23b9-183">비트 사용할 수 또는 (`|||`) 열거형 플래그를 결합 하는 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="d23b9-183">You can also use the bitwise or (`|||`) operator to combine enum flags.</span></span> <span data-ttu-id="d23b9-184">예를 들어 다음 코드는 올바른 F # 3.1에서:</span><span class="sxs-lookup"><span data-stu-id="d23b9-184">For example, the following code is legal in F# 3.1:</span></span>

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

<span data-ttu-id="d23b9-185">다른 비트 연산자의 사용이 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d23b9-185">The use of other bitwise operators isn't allowed.</span></span>


## <a name="named-literals"></a><span data-ttu-id="d23b9-186">명명 된 리터럴</span><span class="sxs-lookup"><span data-stu-id="d23b9-186">Named Literals</span></span>
<span data-ttu-id="d23b9-187">로 상수 있어야 하는 값을 표시할 수 있습니다는 [리터럴](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d23b9-187">Values that are intended to be constants can be marked with the [Literal](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) attribute.</span></span> <span data-ttu-id="d23b9-188">이 특성을 상수로 컴파일할 사용 하면 값의 효과 가집니다.</span><span class="sxs-lookup"><span data-stu-id="d23b9-188">This attribute has the effect of causing a value to be compiled as a constant.</span></span>

<span data-ttu-id="d23b9-189">패턴 일치 식에서 소문자로 시작 하는 식별자는 항상 변수를 바인딩할 수으로 처리 하지 않고 리터럴로 하므로 일반적으로 사용 해야 문자가 대문자 리터럴을 정의할 때.</span><span class="sxs-lookup"><span data-stu-id="d23b9-189">In pattern matching expressions, identifiers that begin with lowercase characters are always treated as variables to be bound, rather than as literals, so you should generally use initial capitals when you define literals.</span></span>

## <a name="integers-in-other-bases"></a><span data-ttu-id="d23b9-190">다른 밑에 있는 정수</span><span class="sxs-lookup"><span data-stu-id="d23b9-190">Integers In Other Bases</span></span>

<span data-ttu-id="d23b9-191">사용 하 여 16 진수, 8 진수 또는 이진에서 부호 있는 32 비트 정수로 지정 될 수도 있습니다는 `0x`, `0o` 또는 `0b` 각각 접두사입니다.</span><span class="sxs-lookup"><span data-stu-id="d23b9-191">Signed 32-bit integers can also be specified in hexadecimal, octal, or binary using a `0x`, `0o` or `0b` prefix respectively.</span></span>

```fsharp
let Numbers = (0x9F, 0o77, 0b1010)
// Result: Numbers : int * int * int = (159, 63, 10)
```

## <a name="underscores-in-numeric-literals"></a><span data-ttu-id="d23b9-192">숫자 리터럴에 밑줄이</span><span class="sxs-lookup"><span data-stu-id="d23b9-192">Underscores in Numeric Literals</span></span>

<span data-ttu-id="d23b9-193">F # 4.1 부터는 구분할 수 있습니다 자리는 밑줄 문자 (`_`).</span><span class="sxs-lookup"><span data-stu-id="d23b9-193">Starting with F# 4.1, you can separate digits with the underscore character (`_`).</span></span>

```fsharp
let DeadBeef = 0xDEAD_BEEF

let DeadBeefAsBits = 0b1101_1110_1010_1101_1011_1110_1110_1111

let ExampleSSN = 123_456_7890
```

## <a name="see-also"></a><span data-ttu-id="d23b9-194">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d23b9-194">See Also</span></span>

[<span data-ttu-id="d23b9-195">Core.LiteralAttribute 클래스</span><span class="sxs-lookup"><span data-stu-id="d23b9-195">Core.LiteralAttribute Class</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.literalattribute-class-%5bfsharp%5d)
