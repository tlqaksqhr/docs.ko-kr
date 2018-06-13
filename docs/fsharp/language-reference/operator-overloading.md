---
title: 연산자 오버로드(F#)
description: 'F #에서 전역 수준에서 클래스 또는 레코드 종류에 산술 연산자를 오버 로드 하는 방법에 알아봅니다.'
ms.date: 05/16/2016
ms.openlocfilehash: fc9b7311aa746fd758930365972a187ffdfff0d5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33564367"
---
# <a name="operator-overloading"></a><span data-ttu-id="f6fd9-103">연산자 오버로드</span><span class="sxs-lookup"><span data-stu-id="f6fd9-103">Operator Overloading</span></span>

<span data-ttu-id="f6fd9-104">이 항목의 전역 수준에서 클래스 또는 레코드 종류에 산술 연산자를 오버 로드 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6fd9-104">This topic describes how to overload arithmetic operators in a class or record type, and at the global level.</span></span>


## <a name="syntax"></a><span data-ttu-id="f6fd9-105">구문</span><span class="sxs-lookup"><span data-stu-id="f6fd9-105">Syntax</span></span>

```fsharp
// Overloading an operator as a class or record member.
static member (operator-symbols) (parameter-list) =
    method-body
// Overloading an operator at the global level
let [inline] (operator-symbols) parameter-list = function-body
```

## <a name="remarks"></a><span data-ttu-id="f6fd9-106">설명</span><span class="sxs-lookup"><span data-stu-id="f6fd9-106">Remarks</span></span>
<span data-ttu-id="f6fd9-107">위 구문에는 *연산자 기호* 중 하나인 `+`, `-`, `*`, `/`, `=`등입니다.</span><span class="sxs-lookup"><span data-stu-id="f6fd9-107">In the previous syntax, the *operator-symbol* is one of `+`, `-`, `*`, `/`, `=`, and so on.</span></span> <span data-ttu-id="f6fd9-108">*매개 변수 목록* 해당 연산자는 일반적인 구문을에 나타나는 순서에 따라 피연산자를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6fd9-108">The *parameter-list* specifies the operands in the order they appear in the usual syntax for that operator.</span></span> <span data-ttu-id="f6fd9-109">*메서드 본문* 결과 값을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6fd9-109">The *method-body* constructs the resulting value.</span></span>

<span data-ttu-id="f6fd9-110">연산자에 대 한 연산자 오버 로드는 정적 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6fd9-110">Operator overloads for operators must be static.</span></span> <span data-ttu-id="f6fd9-111">같은 단항 연산자에 대 한 연산자 오버 로드 `+` 및 `-`, 물결표를 사용 해야 합니다 (`~`)에 *연산자 기호* 에서처럼 연산자는 단항 연산자, 이항 연산자가 아니라,을 나타내기 위해는 다음 선언입니다.</span><span class="sxs-lookup"><span data-stu-id="f6fd9-111">Operator overloads for unary operators, such as `+` and `-`, must use a tilde (`~`) in the *operator-symbol* to indicate that the operator is a unary operator and not a binary operator, as shown in the following declaration.</span></span>

```fsharp
static member (~-) (v : Vector)
```

<span data-ttu-id="f6fd9-112">다음 코드에서는 연산자가 두 개뿐인 벡터 클래스를 보여 줍니다. 그 중 하나는 단항 빼기 연산자이고 다른 하나는 스칼라 값을 곱하기 위한 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="f6fd9-112">The following code illustrates a vector class that has just two operators, one for unary minus and one for multiplication by a scalar.</span></span> <span data-ttu-id="f6fd9-113">예제에서는 스칼라 곱하기 위한 두 개의 오버 로드 연산자 벡터와 스칼라 나타나는 순서에 관계 없이 작동 해야 되므로 세 키워드가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6fd9-113">In the example, two overloads for scalar multiplication are needed because the operator must work regardless of the order in which the vector and scalar appear.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4001.fs)]

## <a name="creating-new-operators"></a><span data-ttu-id="f6fd9-114">새 운영자를 만드는</span><span class="sxs-lookup"><span data-stu-id="f6fd9-114">Creating New Operators</span></span>
<span data-ttu-id="f6fd9-115">모든 표준 연산자를 오버 로드할 수 있지만 새 연산자 특정 문자의 시퀀스를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6fd9-115">You can overload all the standard operators, but you can also create new operators out of sequences of certain characters.</span></span> <span data-ttu-id="f6fd9-116">허용 되는 연산자 문자는 `!`, `%`, `&`, `*`, `+`, `-`, `.`, `/`, `<`, `=`, `>`, `?`, `@`, `^`, `|`, 및 `~`합니다.</span><span class="sxs-lookup"><span data-stu-id="f6fd9-116">Allowed operator characters are `!`, `%`, `&`, `*`, `+`, `-`, `.`, `/`, `<`, `=`, `>`, `?`, `@`, `^`, `|`, and `~`.</span></span> <span data-ttu-id="f6fd9-117">`~` 문자 연산자 단항으로 만드는 특별 한 의미가 있으며 연산자 문자 시퀀스의 일부가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="f6fd9-117">The `~` character has the special meaning of making an operator unary, and is not part of the operator character sequence.</span></span> <span data-ttu-id="f6fd9-118">일부 연산자는 단항을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6fd9-118">Not all operators can be made unary.</span></span>

<span data-ttu-id="f6fd9-119">정확한 문자 시퀀스를 사용에 따라 특정 우선 순위 및 결합성 귀하가 운영자가 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="f6fd9-119">Depending on the exact character sequence you use, your operator will have a certain precedence and associativity.</span></span> <span data-ttu-id="f6fd9-120">결합성에서 오른쪽으로 또는 오른쪽에서 왼쪽 하거나 유지할 수 있습니다 및 연산자의 우선 순위가 동일한의 괄호 없이 시퀀스에 나타날 때마다 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6fd9-120">Associativity can be either left to right or right to left and is used whenever operators of the same level of precedence appear in sequence without parentheses.</span></span>

<span data-ttu-id="f6fd9-121">연산자 문자 `.` 예를 들어 동일한 우선 순위 및 결합성 순위도 된 곱하기의 고유한 버전을 정의 하려는 경우 등의연산자만들수있도록우선순위,영향을주지않습니다`.*`.</span><span class="sxs-lookup"><span data-stu-id="f6fd9-121">The operator character `.` does not affect precedence, so that, for example, if you want to define your own version of multiplication that has the same precedence and associativity as ordinary multiplication, you could create operators such as `.*`.</span></span>

<span data-ttu-id="f6fd9-122">연산자만 `?` 및 `?<-` 로 시작할 수 `?`합니다.</span><span class="sxs-lookup"><span data-stu-id="f6fd9-122">Only the operators `?` and `?<-` may start with `?`.</span></span>

<span data-ttu-id="f6fd9-123">F #에서 모든 연산자의 우선 순위를 표시 하는 테이블에서 찾을 수 있습니다 [기호 및 연산자 참조](symbol-and-operator-reference/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f6fd9-123">A table that shows the precedence of all operators in F# can be found in [Symbol and Operator Reference](symbol-and-operator-reference/index.md).</span></span>


## <a name="overloaded-operator-names"></a><span data-ttu-id="f6fd9-124">오버 로드 된 연산자 이름</span><span class="sxs-lookup"><span data-stu-id="f6fd9-124">Overloaded Operator Names</span></span>
<span data-ttu-id="f6fd9-125">F # 컴파일러 연산자 식 컴파일되면 해당 연산자에 대 한 컴파일러에서 생성 된 이름을 갖는 메서드를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6fd9-125">When the F# compiler compiles an operator expression, it generates a method that has a compiler-generated name for that operator.</span></span> <span data-ttu-id="f6fd9-126">메서드에 대 한 Microsoft intermediate language (MSIL) 뿐 아니라 리플렉션 및 IntelliSense에 표시 되는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f6fd9-126">This is the name that appears in the Microsoft intermediate language (MSIL) for the method, and also in reflection and IntelliSense.</span></span> <span data-ttu-id="f6fd9-127">일반적으로 F # 코드에서 이러한 이름을 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f6fd9-127">You do not normally need to use these names in F# code.</span></span>

<span data-ttu-id="f6fd9-128">다음 표에서 표준 연산자를 보여주며,의 해당 이름을 생성 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f6fd9-128">The following table shows the standard operators and their corresponding generated names.</span></span>



|<span data-ttu-id="f6fd9-129">연산자</span><span class="sxs-lookup"><span data-stu-id="f6fd9-129">Operator</span></span>|<span data-ttu-id="f6fd9-130">생성 된 이름</span><span class="sxs-lookup"><span data-stu-id="f6fd9-130">Generated name</span></span>|
|--------|--------------|
|`[]`|`op_Nil`|
|`::`|`op_Cons`|
|`+`|`op_Addition`|
|`-`|`op_Subtraction`|
|`*`|`op_Multiply`|
|`/`|`op_Division`|
|`@`|`op_Append`|
|`^`|`op_Concatenate`|
|`%`|`op_Modulus`|
|`&&&`|`op_BitwiseAnd`|
|<code>&#124;&#124;&#124;</code>|`op_BitwiseOr`|
|`^^^`|`op_ExclusiveOr`|
|`<<<`|`op_LeftShift`|
|`~~~`|`op_LogicalNot`|
|`>>>`|`op_RightShift`|
|`~+`|`op_UnaryPlus`|
|`~-`|`op_UnaryNegation`|
|`=`|`op_Equality`|
|`<=`|`op_LessThanOrEqual`|
|`>=`|`op_GreaterThanOrEqual`|
|`<`|`op_LessThan`|
|`>`|`op_GreaterThan`|
|`?`|`op_Dynamic`|
|`?<-`|`op_DynamicAssignment`|
|<code>&#124;></code>|`op_PipeRight`|
|<code><&#124;</code>|`op_PipeLeft`|
|`!`|`op_Dereference`|
|`>>`|`op_ComposeRight`|
|`<<`|`op_ComposeLeft`|
|`<@ @>`|`op_Quotation`|
|`<@@ @@>`|`op_QuotationUntyped`|
|`+=`|`op_AdditionAssignment`|
|`-=`|`op_SubtractionAssignment`|
|`*=`|`op_MultiplyAssignment`|
|`/=`|`op_DivisionAssignment`|
|`..`|`op_Range`|
|`.. ..`|`op_RangeStep`|
<span data-ttu-id="f6fd9-131">여기에 나열 되지 않은 연산자 문자의 다른 조합 연산자로 사용할 수 있으며 다음 테이블의 개별 문자에 대 한 이름을 연결 하 여 구성 하는 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6fd9-131">Other combinations of operator characters that are not listed here can be used as operators and have names that are made up by concatenating names for the individual characters from the following table.</span></span> <span data-ttu-id="f6fd9-132">예를 들어 +!</span><span class="sxs-lookup"><span data-stu-id="f6fd9-132">For example, +!</span></span> <span data-ttu-id="f6fd9-133">됩니다 `op_PlusBang`합니다.</span><span class="sxs-lookup"><span data-stu-id="f6fd9-133">becomes `op_PlusBang`.</span></span>



|<span data-ttu-id="f6fd9-134">연산자 문자</span><span class="sxs-lookup"><span data-stu-id="f6fd9-134">Operator character</span></span>|<span data-ttu-id="f6fd9-135">이름</span><span class="sxs-lookup"><span data-stu-id="f6fd9-135">Name</span></span>|
|------------------|----|
|`>`|`Greater`|
|`<`|`Less`|
|`+`|`Plus`|
|`-`|`Minus`|
|`*`|`Multiply`|
|`/`|`Divide`|
|`=`|`Equals`|
|`~`|`Twiddle`|
|`%`|`Percent`|
|`.`|`Dot`|
|`&`|`Amp`|
|<code>&#124;</code>|`Bar`|
|`@`|`At`|
|`^`|`Hat`|
|`!`|`Bang`|
|`?`|`Qmark`|
|`(`|`LParen`|
|`,`|`Comma`|
|`)`|`RParen`|
|`[`|`LBrack`|
|`]`|`RBrack`|

## <a name="prefix-and-infix-operators"></a><span data-ttu-id="f6fd9-136">접두사와 중 위 연산자</span><span class="sxs-lookup"><span data-stu-id="f6fd9-136">Prefix and Infix Operators</span></span>
<span data-ttu-id="f6fd9-137">*접두사* 연산자는 하나 이상의 함수 처럼 훨씬 피연산자 앞에 배치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6fd9-137">*Prefix* operators are expected to be placed in front of an operand or operands, much like a function.</span></span> <span data-ttu-id="f6fd9-138">*중 위* 연산자는 연산자는 두 피연산자 사이 배치할 수입니다.</span><span class="sxs-lookup"><span data-stu-id="f6fd9-138">*Infix* operators are expected to be placed between the two operands.</span></span>

<span data-ttu-id="f6fd9-139">전위 연산자도 특정 연산자만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6fd9-139">Only certain operators can be used as prefix operators.</span></span> <span data-ttu-id="f6fd9-140">일부 연산자는 항상 전위 연산자, 및 중 위 또는 접두사 수 다른 나머지는 언제나 연산자 중 위 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6fd9-140">Some operators are always prefix operators, others can be infix or prefix, and the rest are always infix operators.</span></span> <span data-ttu-id="f6fd9-141">`!`를 제외한 `!=`로 시작하는 연산자와 `~` 연산자 또는 `~` 연산자의 반복적인 시퀀스는 항상 전위 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="f6fd9-141">Operators that begin with `!`, except `!=`, and the operator `~`, or repeated sequences of`~`, are always prefix operators.</span></span> <span data-ttu-id="f6fd9-142">연산자 `+`, `-`, `+.`, `-.`, `&`, `&&`, `%`, 및 `%%` 전위 연산자 또는 중 위 연산자 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6fd9-142">The operators `+`, `-`, `+.`, `-.`, `&`, `&&`, `%`, and `%%` can be prefix operators or infix operators.</span></span> <span data-ttu-id="f6fd9-143">추가 하 여 이러한 연산자의 전위 버전 중 위에서 구분 하기는 `~` 전위 연산자 정의 될 때의 시작 부분에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6fd9-143">You distinguish the prefix version of these operators from the infix version by adding a `~` at the beginning of a prefix operator when it is defined.</span></span> <span data-ttu-id="f6fd9-144">`~` 는 연산자를 사용 하 여 정의 된 경우에 때는 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f6fd9-144">The `~` is not used when you use the operator, only when it is defined.</span></span>

## <a name="example"></a><span data-ttu-id="f6fd9-145">예제</span><span class="sxs-lookup"><span data-stu-id="f6fd9-145">Example</span></span>

<span data-ttu-id="f6fd9-146">다음 코드에서는 연산자 분수 유형을 구현 하도록 오버 로드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6fd9-146">The following code illustrates the use of operator overloading to implement a fraction type.</span></span> <span data-ttu-id="f6fd9-147">분수는 분자와 분모도 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6fd9-147">A fraction is represented by a numerator and a denominator.</span></span> <span data-ttu-id="f6fd9-148">함수 `hcf` 분수를 줄이기 위해 사용 되는 가장 큰 공통 인수를 확인 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6fd9-148">The function `hcf` is used to determine the highest common factor, which is used to reduce fractions.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4002.fs)]

<span data-ttu-id="f6fd9-149">**출력:**</span><span class="sxs-lookup"><span data-stu-id="f6fd9-149">**Output:**</span></span>

```
3/4 + 1/2 = 5/4
3/4 - 1/2 = 1/4
3/4 * 1/2 = 3/8
3/4 / 1/2 = 3/2
3/4 + 1 = 7/4
```

## <a name="operators-at-the-global-level"></a><span data-ttu-id="f6fd9-150">연산자의 전역 수준에서</span><span class="sxs-lookup"><span data-stu-id="f6fd9-150">Operators at the Global Level</span></span>
<span data-ttu-id="f6fd9-151">전역 수준에서 연산자를 정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6fd9-151">You can also define operators at the global level.</span></span> <span data-ttu-id="f6fd9-152">다음 코드는 연산자 정의 `+?`합니다.</span><span class="sxs-lookup"><span data-stu-id="f6fd9-152">The following code defines an operator `+?`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4003.fs)]

<span data-ttu-id="f6fd9-153">위 코드의 출력은 `12`합니다.</span><span class="sxs-lookup"><span data-stu-id="f6fd9-153">The output of the above code is `12`.</span></span>

<span data-ttu-id="f6fd9-154">F #에 대 한 범위 지정 규칙 새로 정의 된 연산자의 기본 제공 연산자 보다 우선 적용을 지정 하기 때문에 이런이 방식으로 일반적인 산술 연산자를 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6fd9-154">You can redefine the regular arithmetic operators in this manner because the scoping rules for F# dictate that newly defined operators take precedence over the built-in operators.</span></span>

<span data-ttu-id="f6fd9-155">키워드 `inline` 는 종종 호출 코드에 가장 잘 통합 되는 작은 함수가 전역 연산자와 함께 자주 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6fd9-155">The keyword `inline` is often used with global operators, which are often small functions that are best integrated into the calling code.</span></span> <span data-ttu-id="f6fd9-156">연산자 함수를 인라인으로 만들기를 사용 하면 제네릭 정적으로 확인 된 코드를 생성 하는 정적으로 확인 된 형식 매개 변수와 함께 작동 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6fd9-156">Making operator functions inline also enables them to work with statically resolved type parameters to produce statically resolved generic code.</span></span> <span data-ttu-id="f6fd9-157">자세한 내용은 참조 [인라인 함수](functions/inline-functions.md) 및 [정적으로 확인할 형식 매개 변수](generics/statically-resolved-type-parameters.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f6fd9-157">For more information, see [Inline Functions](functions/inline-functions.md) and [Statically Resolved Type Parameters](generics/statically-resolved-type-parameters.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f6fd9-158">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f6fd9-158">See Also</span></span>
[<span data-ttu-id="f6fd9-159">멤버</span><span class="sxs-lookup"><span data-stu-id="f6fd9-159">Members</span></span>](members/index.md)
