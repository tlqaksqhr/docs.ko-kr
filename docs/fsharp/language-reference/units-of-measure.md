---
title: 측정 단위(F#)
description: '자세한 방법을 부동 소수점 및 F #의 부호 있는 정수 값은 측정 단위를, 길이, 볼륨 및 mass 나타내기 위해 일반적으로 사용 되는 연결 될 수 있습니다.'
ms.date: 05/16/2016
ms.openlocfilehash: 3e47c92100c1dd99161be709a065913f501854f2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33564953"
---
# <a name="units-of-measure"></a><span data-ttu-id="2ac63-103">측정 단위</span><span class="sxs-lookup"><span data-stu-id="2ac63-103">Units of Measure</span></span>

<span data-ttu-id="2ac63-104">F #에서 부동 소수점 및 부호 있는 정수 값 일반적으로 대량, 길이, 볼륨을 나타내는 데 사용 되는 측정 단위가 연결 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ac63-104">Floating point and signed integer values in F# can have associated units of measure, which are typically used to indicate length, volume, mass, and so on.</span></span> <span data-ttu-id="2ac63-105">수량 단위를 사용 하 여 사용 하도록 설정 하면 컴파일러 권한이 있는지 확인 하려면 산술 관계 올바른 단위를 사용 하면 방지할 수 있는 프로그래밍 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="2ac63-105">By using quantities with units, you enable the compiler to verify that arithmetic relationships have the correct units, which helps prevent programming errors.</span></span>


## <a name="syntax"></a><span data-ttu-id="2ac63-106">구문</span><span class="sxs-lookup"><span data-stu-id="2ac63-106">Syntax</span></span>

```fsharp
[<Measure>] type unit-name [ = measure ]
```

## <a name="remarks"></a><span data-ttu-id="2ac63-107">설명</span><span class="sxs-lookup"><span data-stu-id="2ac63-107">Remarks</span></span>
<span data-ttu-id="2ac63-108">위 구문 정의 *단위 이름* 으로 측정 단위입니다.</span><span class="sxs-lookup"><span data-stu-id="2ac63-108">The previous syntax defines *unit-name* as a unit of measure.</span></span> <span data-ttu-id="2ac63-109">선택적 요소는 이전에 정의 된 단위를 기준으로 새 측정값을 정의 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ac63-109">The optional part is used to define a new measure in terms of previously defined units.</span></span> <span data-ttu-id="2ac63-110">다음 줄에서는 측정값을 정의 하는 예를 들어 `cm` (센티미터).</span><span class="sxs-lookup"><span data-stu-id="2ac63-110">For example, the following line defines the measure `cm` (centimeter).</span></span>

```fsharp
[<Measure>] type cm
```

<span data-ttu-id="2ac63-111">다음 줄에서는 측정값을 정의 `ml` (밀리 리터) 입방 센티미터도 (`cm^3`).</span><span class="sxs-lookup"><span data-stu-id="2ac63-111">The following line defines the measure `ml` (milliliter) as a cubic centimeter (`cm^3`).</span></span>

```fsharp
[<Measure>] type ml = cm^3
```

<span data-ttu-id="2ac63-112">위 구문에서 *측정값* 은 단위와 관련 된 수식입니다.</span><span class="sxs-lookup"><span data-stu-id="2ac63-112">In the previous syntax, *measure* is a formula that involves units.</span></span> <span data-ttu-id="2ac63-113">단위와 관련 된 수식에 정수 거듭제곱에 (양수 및 음수) 지원 되는 경우 단위 사이의 공백을 나타내는 제품 두 명의 단위입니다. `*` 나타내기도 단위, 제품 및 `/` 단위의 몫을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2ac63-113">In formulas that involve units, integral powers are supported (positive and negative), spaces between units indicate a product of the two units, `*` also indicates a product of units, and `/` indicates a quotient of units.</span></span> <span data-ttu-id="2ac63-114">역 단위에 대 한 음의 정수 power를 사용 하거나 또는 `/` 분자와 분모 단위 수식의 구분을 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="2ac63-114">For a reciprocal unit, you can either use a negative integer power or a `/` that indicates a separation between the numerator and denominator of a unit formula.</span></span> <span data-ttu-id="2ac63-115">분모에 여러 단위 괄호로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ac63-115">Multiple units in the denominator should be surrounded by parentheses.</span></span> <span data-ttu-id="2ac63-116">후 공백으로 분리 되어 단위는 `/` 의 일부는 분모 이지만 오는 모든 단위 것으로 해석 한 `*` 분자의 일부로 해석 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ac63-116">Units separated by spaces after a `/` are interpreted as being part of the denominator, but any units following a `*` are interpreted as being part of the numerator.</span></span>

<span data-ttu-id="2ac63-117">분자와 같이 다른 단위와 함께 또는 단독으로 수량을 나타내거나 단위 식에 1을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ac63-117">You can use 1 in unit expressions, either alone to indicate a dimensionless quantity, or together with other units, such as in the numerator.</span></span> <span data-ttu-id="2ac63-118">으로 속도 대 한 단위를 작성 하는 예를 들어 `1/s`여기서 `s` 초를 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ac63-118">For example, the units for a rate would be written as `1/s`, where `s` indicates seconds.</span></span> <span data-ttu-id="2ac63-119">괄호 단위 수식에 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2ac63-119">Parentheses are not used in unit formulas.</span></span> <span data-ttu-id="2ac63-120">숫자 변환 상수 단위 수식;에 지정 하지 않으면 그러나 별도로 단위와 변환 상수를 정의 하 고 단위 검사 계산에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ac63-120">You do not specify numeric conversion constants in the unit formulas; however, you can define conversion constants with units separately and use them in unit-checked computations.</span></span>

<span data-ttu-id="2ac63-121">해당 하는 다양 한 방법으로 동일한 것을 의미할 단위 수식은 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ac63-121">Unit formulas that mean the same thing can be written in various equivalent ways.</span></span> <span data-ttu-id="2ac63-122">따라서 컴파일러 단위 수식 음수 거듭제곱 단일 분자와 분모의 경우 평균은, 그룹 단위를 변환 하 고 분자와 분모에서 단위를 사전순으로 정렬 되는 일관 된 형식에 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ac63-122">Therefore, the compiler converts unit formulas into a consistent form, which converts negative powers to reciprocals, groups units into a single numerator and a denominator, and alphabetizes the units in the numerator and denominator.</span></span>

<span data-ttu-id="2ac63-123">예를 들어 단위 수식 `kg m s^-2` 및 `m /s s * kg` 둘 다로 변환할지 `kg m/s^2`합니다.</span><span class="sxs-lookup"><span data-stu-id="2ac63-123">For example, the unit formulas `kg m s^-2` and `m /s s * kg` are both converted to `kg m/s^2`.</span></span>

<span data-ttu-id="2ac63-124">부동 소수점 식을 측정 단위를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2ac63-124">You use units of measure in floating point expressions.</span></span> <span data-ttu-id="2ac63-125">측정값의 연결 된 단위와 함께 부동 소수점 숫자를 사용 하 여 다른 수준의 형식 안전성 더하고 약한 형식의 부동 소수점 숫자를 사용 하는 경우 수식에서 발생할 수 있는 단위 불일치 오류를 방지할 수 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ac63-125">Using floating point numbers together with associated units of measure adds another level of type safety and helps avoid the unit mismatch errors that can occur in formulas when you use weakly typed floating point numbers.</span></span> <span data-ttu-id="2ac63-126">부동을 작성 하는 경우 단위를 사용 하는 소수점 식을 식의 단위가 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ac63-126">If you write a floating point expression that uses units, the units in the expression must match.</span></span>

<span data-ttu-id="2ac63-127">다음 예제에 나와 있는 것 처럼 꺾쇠 괄호에 단위 수식 사용 하 여 리터럴 주석을 달 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ac63-127">You can annotate literals with a unit formula in angle brackets, as shown in the following examples.</span></span>

```fsharp
1.0<cm>
55.0<miles/hour>
```

<span data-ttu-id="2ac63-128">꺾쇠 괄호; 수 사이 공백을 삽입 하지 마십시오 그러나와 같은 리터럴 접미사를 포함할 수는 `f`다음 예제와 같이, 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ac63-128">You do not put a space between the number and the angle bracket; however, you can include a literal suffix such as `f`, as in the following example.</span></span>

```fsharp
// The f indicates single-precision floating point.
55.0f<miles/hour>
```

<span data-ttu-id="2ac63-129">해당 기본 형식에서 리터럴 형식을 변경 하는 그러한 주석을 (같은 `float`) 크기가 지정 된 형식으로와 같은 `float<cm>` 또는,이 경우 `float<miles/hour>`합니다.</span><span class="sxs-lookup"><span data-stu-id="2ac63-129">Such an annotation changes the type of the literal from its primitive type (such as `float`) to a dimensioned type, such as `float<cm>` or, in this case, `float<miles/hour>`.</span></span> <span data-ttu-id="2ac63-130">단위 주석 `<1>` 하다 고 수량을 나타내거나 및 해당 형식이 단위 매개 변수 없이 기본 형식과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ac63-130">A unit annotation of `<1>` indicates a dimensionless quantity, and its type is equivalent to the primitive type without a unit parameter.</span></span>

<span data-ttu-id="2ac63-131">측정 단위는 부동 소수점 형식 또는 부호 있는 정수 계열 형식 대괄호로 표시 된 추가 단위 주석 함께 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ac63-131">The type of a unit of measure is a floating point or signed integral type together with an extra unit annotation, indicated in brackets.</span></span> <span data-ttu-id="2ac63-132">따라서 작성 하는 경우에서 변환 형식을 `g` (그램)를 `kg` 다음과 같이 형식을 설명 (킬로그램).</span><span class="sxs-lookup"><span data-stu-id="2ac63-132">Thus, when you write the type of a conversion from `g` (grams) to `kg` (kilograms), you describe the types as follows.</span></span>

```fsharp
let convertg2kg (x : float<g>) = x / 1000.0<g/kg>
```

<span data-ttu-id="2ac63-133">측정 단위를 확인 하는 컴파일 시간 단위에 대해 사용 되지만 런타임 환경에서 유지 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2ac63-133">Units of measure are used for compile-time unit checking but are not persisted in the run-time environment.</span></span> <span data-ttu-id="2ac63-134">따라서 성능을 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2ac63-134">Therefore, they do not affect performance.</span></span>

<span data-ttu-id="2ac63-135">측정 단위를 뿐 아니라 부동 소수점 형식; 모든 형식에 적용할 수 있습니다. 그러나만 부동 소수점 형식 정수 계열 형식 및 소수 형식 지원 차원이 구분 된 수량에 서명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ac63-135">Units of measure can be applied to any type, not just floating point types; however, only floating point types, signed integral types, and decimal types support dimensioned quantities.</span></span> <span data-ttu-id="2ac63-136">따라서 하면 이러한 기본 형식을 포함 하는 집계 및 기본 형식에서 측정 단위를 사용 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ac63-136">Therefore, it only makes sense to use units of measure on the primitive types and on aggregates that contain these primitive types.</span></span>

<span data-ttu-id="2ac63-137">다음 예제에는 측정 단위를 사용 하 여를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2ac63-137">The following example illustrates the use of units of measure.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6901.fs)]
    
<span data-ttu-id="2ac63-138">다음 코드 예제에는 값을 가지는 부동 소수점 숫자에서 크기가 지정 된 부동 소수점 값으로 변환 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2ac63-138">The following code example illustrates how to convert from a dimensionless floating point number to a dimensioned floating point value.</span></span> <span data-ttu-id="2ac63-139">곱하기만 1.0에서 크기를 1.0에 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ac63-139">You just multiply by 1.0, applying the dimensions to the 1.0.</span></span> <span data-ttu-id="2ac63-140">와 같은 함수에이 추상화할 수 `degreesFahrenheit`합니다.</span><span class="sxs-lookup"><span data-stu-id="2ac63-140">You can abstract this into a function like `degreesFahrenheit`.</span></span>

<span data-ttu-id="2ac63-141">또한 부동 소수점 숫자 값을 가지는 함수에 크기가 지정 된 값을 전달할 때의 단위를 취소 하거나 해야 캐스팅 `float` 를 사용 하 여는 `float` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="2ac63-141">Also, when you pass dimensioned values to functions that expect dimensionless floating point numbers, you must cancel out the units or cast to `float` by using the `float` operator.</span></span> <span data-ttu-id="2ac63-142">이 예제에서는로 나누면 `1.0<degC>` 에 대 한 인수에 대 한 `printf` 때문에 `printf` 차원이 수량을 예상 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ac63-142">In this example, you divide by `1.0<degC>` for the arguments to `printf` because `printf` expects dimensionless quantities.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6902.fs)]

<span data-ttu-id="2ac63-143">다음 예제에서는 세션에는이 코드에 입력과 출력에서 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2ac63-143">The following example session shows the outputs from and inputs to this code.</span></span>

```
Enter a temperature in degrees Fahrenheit.
90
That temperature in degrees Celsius is    32.22.
```

## <a name="using-generic-units"></a><span data-ttu-id="2ac63-144">제네릭 단위를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="2ac63-144">Using Generic Units</span></span>
<span data-ttu-id="2ac63-145">데이터에서 연결 된 단위에 대해 실행 되는 제네릭 함수를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ac63-145">You can write generic functions that operate on data that has an associated unit of measure.</span></span> <span data-ttu-id="2ac63-146">이렇게 하면 제네릭 단위 삼아 형식을 형식 매개 변수로 지정 하 여 다음 코드 예제와 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ac63-146">You do this by specifying a type together with a generic unit as a type parameter, as shown in the following code example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6903.fs)]
    
## <a name="creating-aggregate-types-with-generic-units"></a><span data-ttu-id="2ac63-147">집합체 형식은 제네릭 단위를 사용 하 여 만들기</span><span class="sxs-lookup"><span data-stu-id="2ac63-147">Creating Aggregate Types with Generic Units</span></span>
<span data-ttu-id="2ac63-148">다음 코드에는 일반적인 단위가 포함 된 개별 부동 소수점 값으로 구성 된 집계 형식을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2ac63-148">The following code shows how to create an aggregate type that consists of individual floating point values that have units that are generic.</span></span> <span data-ttu-id="2ac63-149">이렇게 하면 다양 한 단위를 사용 하는 단일 형식을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ac63-149">This enables a single type to be created that works with a variety of units.</span></span> <span data-ttu-id="2ac63-150">또한 제네릭 단위를 단위 집합이 하나를 가진 제네릭 형식을 같은 제네릭 형식 다른 집합의 단위는 다른 형식 인지 확인 하 여 형식 안전성을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ac63-150">Also, generic units preserve type safety by ensuring that a generic type that has one set of units is a different type than the same generic type with a different set of units.</span></span> <span data-ttu-id="2ac63-151">이 기술의 기반은 하는 `Measure` 특성에 형식 매개 변수에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ac63-151">The basis of this technique is that the `Measure` attribute can be applied to the type parameter.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6904.fs)]
    
## <a name="units-at-runtime"></a><span data-ttu-id="2ac63-152">런타임 시 단위</span><span class="sxs-lookup"><span data-stu-id="2ac63-152">Units at Runtime</span></span>
<span data-ttu-id="2ac63-153">측정 단위는 정적 형식 확인에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ac63-153">Units of measure are used for static type checking.</span></span> <span data-ttu-id="2ac63-154">부동 소수점 값을 컴파일하면 측정 단위를 제거 실행 시 단위는 손실 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ac63-154">When floating point values are compiled, the units of measure are eliminated, so the units are lost at run time.</span></span> <span data-ttu-id="2ac63-155">따라서 실행 시의 단위를 확인 하는 중에 의존 하는 기능을 구현 하려고 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2ac63-155">Therefore, any attempt to implement functionality that depends on checking the units at run time is not possible.</span></span> <span data-ttu-id="2ac63-156">예를 들어, 구현 하는 `ToString` 단위를 출력 하는 함수 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2ac63-156">For example, implementing a `ToString` function to print out the units is not possible.</span></span>


## <a name="conversions"></a><span data-ttu-id="2ac63-157">변환</span><span class="sxs-lookup"><span data-stu-id="2ac63-157">Conversions</span></span>
<span data-ttu-id="2ac63-158">단위는 형식을 변환 하려면 (예를 들어 `float<'u>`) 단위 하지 않은 형식으로 표준 변환 함수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ac63-158">To convert a type that has units (for example, `float<'u>`) to a type that does not have units, you can use the standard conversion function.</span></span> <span data-ttu-id="2ac63-159">사용할 수는 예를 들어 `float` 변환할는 `float` 하지 않은 단위, 다음 코드에 나와 있는 것 처럼 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2ac63-159">For example, you can use `float` to convert to a `float` value that does not have units, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6905.fs)]

<span data-ttu-id="2ac63-160">단위 없는 값 단위를가지고 있는 값으로 변환 하려면 해당 단위로 주석을 처리 하는 1 또는 1.0 값을 곱합니다 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ac63-160">To convert a unitless value to a value that has units, you can multiply by a 1 or 1.0 value that is annotated with the appropriate units.</span></span> <span data-ttu-id="2ac63-161">그러나 상호 운용성 계층을 쓰기 위해 있습니다 값 단위와 단위 값으로 변환 하는 데 사용할 수 있는 일부 explicit 함수.</span><span class="sxs-lookup"><span data-stu-id="2ac63-161">However, for writing interoperability layers, there are also some explicit functions that you can use to convert unitless values to values with units.</span></span> <span data-ttu-id="2ac63-162">이러한 데이터베이스는 [Microsoft.FSharp.Core.LanguagePrimitives](https://msdn.microsoft.com/library/69d08ac5-5d51-4c20-bf1e-850fd312ece3) 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="2ac63-162">These are in the [Microsoft.FSharp.Core.LanguagePrimitives](https://msdn.microsoft.com/library/69d08ac5-5d51-4c20-bf1e-850fd312ece3) module.</span></span> <span data-ttu-id="2ac63-163">예를 들어, 단위는 변환할 `float` 에 `float<cm>`를 사용 하 여 [FloatWithMeasure](https://msdn.microsoft.com/library/69520bc7-d67b-46b8-9004-7cac9646b8d9)다음 코드에 나온 것 처럼 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ac63-163">For example, to convert from a unitless `float` to a `float<cm>`, use [FloatWithMeasure](https://msdn.microsoft.com/library/69520bc7-d67b-46b8-9004-7cac9646b8d9), as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6906.fs)]
    
## <a name="units-of-measure-in-the-f-power-pack"></a><span data-ttu-id="2ac63-164">F # Power Pack의 측정 단위</span><span class="sxs-lookup"><span data-stu-id="2ac63-164">Units of Measure in the F# Power Pack</span></span>
<span data-ttu-id="2ac63-165">단위 라이브러리에서 F # PowerPack ´ ù.</span><span class="sxs-lookup"><span data-stu-id="2ac63-165">A unit library is available in the F# PowerPack.</span></span> <span data-ttu-id="2ac63-166">단위 라이브러리 SI 단위 및 실제 상수를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="2ac63-166">The unit library includes SI units and physical constants.</span></span>


## <a name="see-also"></a><span data-ttu-id="2ac63-167">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2ac63-167">See Also</span></span>
[<span data-ttu-id="2ac63-168">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="2ac63-168">F# Language Reference</span></span>](index.md)
