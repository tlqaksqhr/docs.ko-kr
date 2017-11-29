---
title: "제네릭(F#)"
description: "F # 제네릭 함수 및 코드를 반복 하지 않고 다양 한 형식 사용 하는 코드를 작성할 수 있도록 하는 형식을 사용 하는 방법에 알아봅니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: a9f2e2ee-bcb1-4ce3-8531-850aa183040f
ms.openlocfilehash: e7a5712fddf4d372d1ada86927f50e394a59a410
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="generics"></a><span data-ttu-id="33ada-104">제네릭</span><span class="sxs-lookup"><span data-stu-id="33ada-104">Generics</span></span>

<span data-ttu-id="33ada-105">F# 함수 값, 메서드, 속성 및 집계 형식(예: 클래스, 레코드 및 구분된 공용 구조체)은 *제네릭*일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33ada-105">F# function values, methods, properties, and aggregate types such as classes, records, and discriminated unions can be *generic*.</span></span> <span data-ttu-id="33ada-106">제네릭 구문에는 형식 매개 변수가 하나 이상 포함됩니다. 형식 매개 변수는 제네릭 구문의 사용자가 일반적으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="33ada-106">Generic constructs contain at least one type parameter, which is usually supplied by the user of the generic construct.</span></span> <span data-ttu-id="33ada-107">제네릭 함수 및 형식을 통해 각 형식에 대한 코드를 반복하지 않고 다양한 형식을 사용하는 코드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33ada-107">Generic functions and types enable you to write code that works with a variety of types without repeating the code for each type.</span></span> <span data-ttu-id="33ada-108">컴파일러의 형식 유추 및 자동 일반화 메커니즘에서는 대개 코드를 암시적으로 제네릭으로 유추하므로 F#에서 코드를 제네릭 형식으로 지정하는 것은 간단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33ada-108">Making your code generic can be simple in F#, because often your code is implicitly inferred to be generic by the compiler's type inference and automatic generalization mechanisms.</span></span>


## <a name="syntax"></a><span data-ttu-id="33ada-109">구문</span><span class="sxs-lookup"><span data-stu-id="33ada-109">Syntax</span></span>

```fsharp
// Explicitly generic function.
let function-name<type-parameters> parameter-list =
function-body

// Explicitly generic method.
[ static ] member object-identifer.method-name<type-parameters> parameter-list [ return-type ] =
method-body

// Explicitly generic class, record, interface, structure,
// or discriminated union.
type type-name<type-parameters> type-definition
```

## <a name="remarks"></a><span data-ttu-id="33ada-110">설명</span><span class="sxs-lookup"><span data-stu-id="33ada-110">Remarks</span></span>
<span data-ttu-id="33ada-111">명시적으로 제네릭 함수 또는 형식을 선언하는 작업은 제네릭이 아닌 함수 또는 형식을 선언하는 작업과 매우 비슷합니다. 단, 함수 또는 형식 이름 뒤에 형식 매개 변수를 꺾쇠 괄호로 묶어 지정(및 사용)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="33ada-111">The declaration of an explicitly generic function or type is much like that of a non-generic function or type, except for the specification (and use) of the type parameters, in angle brackets after the function or type name.</span></span>

<span data-ttu-id="33ada-112">선언은 보통 암시적으로 제네릭인 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="33ada-112">Declarations are often implicitly generic.</span></span> <span data-ttu-id="33ada-113">함수 또는 형식을 작성하는 데 사용되는 모든 매개 변수의 형식을 완전하게 지정하지 않으면 컴파일러가 작성되는 코드에서 각 매개 변수, 값 및 변수의 형식을 유추하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="33ada-113">If you do not fully specify the type of every parameter that is used to compose a function or type, the compiler attempts to infer the type of each parameter, value, and variable from the code you write.</span></span> <span data-ttu-id="33ada-114">자세한 내용은 [형식 유추](../type-inference.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="33ada-114">For more information, see [Type Inference](../type-inference.md).</span></span> <span data-ttu-id="33ada-115">형식 또는 함수에 대한 코드에 매개 변수의 형식이 없으면 함수 또는 형식은 암시적으로 제네릭인 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="33ada-115">If the code for your type or function does not otherwise constrain the types of parameters, the function or type is implicitly generic.</span></span> <span data-ttu-id="33ada-116">이 프로세스를 *자동 일반화*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="33ada-116">This process is named *automatic generalization*.</span></span> <span data-ttu-id="33ada-117">자동 일반화에는 몇 가지 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33ada-117">There are some limits on automatic generalization.</span></span> <span data-ttu-id="33ada-118">예를 들어 F# 컴파일러가 제네릭 구문에 대한 형식을 유추할 수 없는 경우 컴파일러에서 *값 제한*이라는 제한을 나타내는 오류를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="33ada-118">For example, if the F# compiler is unable to infer the types for a generic construct, the compiler reports an error that refers to a restriction called the *value restriction*.</span></span> <span data-ttu-id="33ada-119">이 경우 몇 가지 형식의 주석을 추가해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33ada-119">In that case, you may have to add some type annotations.</span></span> <span data-ttu-id="33ada-120">자동 일반화 및 값 제한과 문제를 해결하도록 코드를 변경하는 방법에 대한 자세한 내용은 [자동 일반화](automatic-generalization.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="33ada-120">For more information about automatic generalization and the value restriction, and how to change your code to address the problem, see [Automatic Generalization](automatic-generalization.md).</span></span>

<span data-ttu-id="33ada-121">이전 구문에서 *type-parameters*는 알 수 없는 형식을 나타내는 매개 변수의 쉼표로 구분 된 목록입니다. 각 매개 변수는 작은따옴표로 시작하고, 선택적으로 해당 형식 매개 변수에 사용되는 형식을 추가로 제한하는 제약 조건 절을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33ada-121">In the previous syntax, *type-parameters* is a comma-separated list of parameters that represent unknown types, each of which starts with a single quotation mark, optionally with a constraint clause that further limits what types may be used for that type parameter.</span></span> <span data-ttu-id="33ada-122">다양한 종류의 제약 조건 절 구문 및 제약 조건에 대한 기타 정보는 [제약 조건](constraints.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="33ada-122">For the syntax for constraint clauses of various kinds and other information about constraints, see [Constraints](constraints.md).</span></span>

<span data-ttu-id="33ada-123">구문의 *type-definition*은 제네릭이 아닌 형식에 대한 형식 정의와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="33ada-123">The *type-definition* in the syntax is the same as the type definition for a non-generic type.</span></span> <span data-ttu-id="33ada-124">여기에는 클래스 형식에 대한 생성자 매개 변수, 선택적 `as` 절, 등호, 레코드 필드, `inherit` 절, 구분된 공용 구조체에 대한 선택 항목, `let` 및 `do` 바인딩, 멤버 정의 및 제네릭이 아닌 형식 정의에서 허용되는 기타 항목이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="33ada-124">It includes the constructor parameters for a class type, an optional `as` clause, the equal symbol, the record fields, the `inherit` clause, the choices for a discriminated union, `let` and `do` bindings, member definitions, and anything else permitted in a non-generic type definition.</span></span>

<span data-ttu-id="33ada-125">기타 구문 요소는 제네릭이 아닌 함수 및 형식에 대한 요소와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="33ada-125">The other syntax elements are the same as those for non-generic functions and types.</span></span> <span data-ttu-id="33ada-126">예를 들어 *object-identifier*는 포함하는 개체 자체를 나타내는 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="33ada-126">For example, *object-identifier* is an identifier that represents the containing object itself.</span></span>

<span data-ttu-id="33ada-127">속성, 필드 및 생성자는 바깥쪽 형식보다 더 제네릭일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="33ada-127">Properties, fields, and constructors cannot be more generic than the enclosing type.</span></span> <span data-ttu-id="33ada-128">또한 모듈의 값은 제네릭이 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="33ada-128">Also, values in a module cannot be generic.</span></span>


## <a name="implicitly-generic-constructs"></a><span data-ttu-id="33ada-129">암시적인 제네릭 구문</span><span class="sxs-lookup"><span data-stu-id="33ada-129">Implicitly Generic Constructs</span></span>
<span data-ttu-id="33ada-130">F# 컴파일러가 코드에서 형식을 유추할 경우 제네릭일 수 있는 모든 함수를 제네릭으로 자동으로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="33ada-130">When the F# compiler infers the types in your code, it automatically treats any function that can be generic as generic.</span></span> <span data-ttu-id="33ada-131">매개 변수 형식과 같은 형식을 명시적으로 지정하는 경우 자동 일반화가 방지됩니다.</span><span class="sxs-lookup"><span data-stu-id="33ada-131">If you specify a type explicitly, such as a parameter type, you prevent automatic generalization.</span></span>

<span data-ttu-id="33ada-132">다음 코드 예제에서 `makeList`는 해당 함수와 그 매개 변수가 명시적으로 제네릭으로 선언되지 않더라도 제네릭입니다.</span><span class="sxs-lookup"><span data-stu-id="33ada-132">In the following code example, `makeList` is generic, even though neither it nor its parameters are explicitly declared as generic.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1700.fs)]

<span data-ttu-id="33ada-133">함수의 시그니처는 `'a -> 'a -> 'a list`로 유추됩니다.</span><span class="sxs-lookup"><span data-stu-id="33ada-133">The signature of the function is inferred to be `'a -> 'a -> 'a list`.</span></span> <span data-ttu-id="33ada-134">이 예제의 `a` 및 `b`는 동일한 형식을 가지는 것으로 유추됩니다.</span><span class="sxs-lookup"><span data-stu-id="33ada-134">Note that `a` and `b` in this example are inferred to have the same type.</span></span> <span data-ttu-id="33ada-135">모두 이 목록에 함께 포함되며, 목록의 모든 요소가 동일한 형식이어야 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="33ada-135">This is because they are included in a list together, and all elements of a list must be of the same type.</span></span>

<span data-ttu-id="33ada-136">형식 주석에 작은따옴표 구문을 사용하여 매개 변수 형식이 제네릭 형식 매개 변수임을 나타냄으로써 함수를 제네릭으로 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33ada-136">You can also make a function generic by using the single quotation mark syntax in a type annotation to indicate that a parameter type is a generic type parameter.</span></span> <span data-ttu-id="33ada-137">다음 코드에서 `function1`은 해당 매개 변수가 이 방식으로 형식 매개 변수로 선언되므로 제네릭입니다.</span><span class="sxs-lookup"><span data-stu-id="33ada-137">In the following code, `function1` is generic because its parameters are declared in this manner, as type parameters.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1701.fs)]
    
## <a name="explicitly-generic-constructs"></a><span data-ttu-id="33ada-138">명시적인 제네릭 구문</span><span class="sxs-lookup"><span data-stu-id="33ada-138">Explicitly Generic Constructs</span></span>
<span data-ttu-id="33ada-139">또한 꺾쇠 괄호에 형식 매개 변수를 명시적으로 선언하여(`<type-parameter>`) 함수를 제네릭으로 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33ada-139">You can also make a function generic by explicitly declaring its type parameters in angle brackets (`<type-parameter>`).</span></span> <span data-ttu-id="33ada-140">다음 코드에서는 이를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="33ada-140">The following code illustrates this.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1703.fs)]
    
## <a name="using-generic-constructs"></a><span data-ttu-id="33ada-141">제네릭 구문 사용</span><span class="sxs-lookup"><span data-stu-id="33ada-141">Using Generic Constructs</span></span>
<span data-ttu-id="33ada-142">제네릭 함수 또는 메서드를 사용하면 형식 인수를 지정해야 할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="33ada-142">When you use generic functions or methods, you might not have to specify the type arguments.</span></span> <span data-ttu-id="33ada-143">컴파일러는 형식 유추를 사용하여 적절한 형식 인수를 유추합니다.</span><span class="sxs-lookup"><span data-stu-id="33ada-143">The compiler uses type inference to infer the appropriate type arguments.</span></span> <span data-ttu-id="33ada-144">여전히 모호한 경우 여러 개의 형식 인수를 쉼표로 구분하면서 꺾쇠 괄호에 형식 인수를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33ada-144">If there is still an ambiguity, you can supply type arguments in angle brackets, separating multiple type arguments with commas.</span></span>

<span data-ttu-id="33ada-145">다음 코드는 이전 섹션에 정의된 함수의 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="33ada-145">The following code shows the use of the functions that are defined in the previous sections.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1702.fs)]
    
>[!NOTE]
<span data-ttu-id="33ada-146">제네릭 형식을 이름으로 참조하는 방법에는 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33ada-146">There are two ways to refer to a generic type by name.</span></span> <span data-ttu-id="33ada-147">예를 들어 `list<int>` 및 `int list`는 단일 형식 인수 `int`를 포함하는 제네릭 형식 `list`를 참조하는 두 가지 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="33ada-147">For example, `list<int>` and `int list` are two ways to refer to a generic type `list` that has a single type argument `int`.</span></span> <span data-ttu-id="33ada-148">두 번째 형식은 일반적으로 기본 제공된 F# 형식(예: `list` 및 `option`)에서만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="33ada-148">The latter form is conventionally used only with built-in F# types such as `list` and `option`.</span></span> <span data-ttu-id="33ada-149">형식 인수가 여러 개 있으면 일반적으로 `Dictionary<int, string>` 구문을 사용할 수 있지만 `(int, string) Dictionary` 구문을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33ada-149">If there are multiple type arguments, you normally use the syntax `Dictionary<int, string>` but you can also use the syntax `(int, string) Dictionary`.</span></span>

## <a name="wildcards-as-type-arguments"></a><span data-ttu-id="33ada-150">형식 인수로 와일드카드 사용</span><span class="sxs-lookup"><span data-stu-id="33ada-150">Wildcards as Type Arguments</span></span>
<span data-ttu-id="33ada-151">컴파일러에서 형식 인수를 유추하도록 지정하기 위해 명명된 형식 인수 대신 밑줄 또는 와일드카드 기호(`_`)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33ada-151">To specify that a type argument should be inferred by the compiler, you can use the underscore, or wildcard symbol (`_`), instead of a named type argument.</span></span> <span data-ttu-id="33ada-152">다음 코드에서 이를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33ada-152">This is shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1704.fs)]
    
## <a name="constraints-in-generic-types-and-functions"></a><span data-ttu-id="33ada-153">제네릭 형식 및 함수의 제약 조건</span><span class="sxs-lookup"><span data-stu-id="33ada-153">Constraints in Generic Types and Functions</span></span>
<span data-ttu-id="33ada-154">제네릭 형식 또는 함수 정의에서는, 제네릭 형식 매개 변수에 사용 가능할 수 있는 것으로 알려진 구문만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33ada-154">In a generic type or function definition, you can use only those constructs that are known to be available on the generic type parameter.</span></span> <span data-ttu-id="33ada-155">이는 컴파일 시간에 함수 및 메서드 호출의 확인을 지원하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="33ada-155">This is required to enable the verification of function and method calls at compile time.</span></span> <span data-ttu-id="33ada-156">형식 매개 변수를 명시적으로 선언하는 경우 특정 메서드 및 함수를 사용할 수 있다는 것을 컴파일러에 알리기 위해 명시적 제약 조건을 제네릭 형식 매개 변수에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33ada-156">If you declare your type parameters explicitly, you can apply an explicit constraint to a generic type parameter to notify the compiler that certain methods and functions are available.</span></span> <span data-ttu-id="33ada-157">그러나 F# 컴파일러에서 제네릭 매개 변수 형식을 유추하도록 허용하면 적절한 제약 조건이 자동으로 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="33ada-157">However, if you allow the F# compiler to infer your generic parameter types, it will determine the appropriate constraints for you.</span></span> <span data-ttu-id="33ada-158">자세한 내용은 [제약 조건](constraints.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="33ada-158">For more information, see [Constraints](constraints.md).</span></span>


## <a name="statically-resolved-type-parameters"></a><span data-ttu-id="33ada-159">정적으로 확인된 형식 매개 변수</span><span class="sxs-lookup"><span data-stu-id="33ada-159">Statically Resolved Type Parameters</span></span>
<span data-ttu-id="33ada-160">F# 프로그램에서 사용할 수 있는 두 가지 종류의 형식 매개 변수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33ada-160">There are two kinds of type parameters that can be used in F# programs.</span></span> <span data-ttu-id="33ada-161">첫 번째는 이전 섹션에 설명된 종류의 제네릭 형식 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="33ada-161">The first are generic type parameters of the kind described in the previous sections.</span></span> <span data-ttu-id="33ada-162">형식 매개 변수의 첫 번째 종류는 Visual Basic 및 C# 같은 언어에 사용되는 제네릭 형식 매개 변수와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="33ada-162">This first kind of type parameter is equivalent to the generic type parameters that are used in languages such as Visual Basic and C#.</span></span> <span data-ttu-id="33ada-163">형식 매개 변수의 다른 종류는 F#에만 관련되며 *정적으로 확인된 형식 매개 변수*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="33ada-163">Another kind of type parameter is specific to F# and is referred to as a *statically resolved type parameter*.</span></span> <span data-ttu-id="33ada-164">이러한 구문에 대한 내용은 [정적으로 확인된 형식 매개 변수](statically-resolved-type-parameters.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="33ada-164">For information about these constructs, see [Statically Resolved Type Parameters](statically-resolved-type-parameters.md).</span></span>


## <a name="examples"></a><span data-ttu-id="33ada-165">예제</span><span class="sxs-lookup"><span data-stu-id="33ada-165">Examples</span></span>
[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1705.fs)]
    
## <a name="see-also"></a><span data-ttu-id="33ada-166">참고 항목</span><span class="sxs-lookup"><span data-stu-id="33ada-166">See Also</span></span>
[<span data-ttu-id="33ada-167">언어 참조</span><span class="sxs-lookup"><span data-stu-id="33ada-167">Language Reference</span></span>](../index.md)

[<span data-ttu-id="33ada-168">유형</span><span class="sxs-lookup"><span data-stu-id="33ada-168">Types</span></span>](../fsharp-types.md)

[<span data-ttu-id="33ada-169">정적으로 확인된 형식 매개 변수</span><span class="sxs-lookup"><span data-stu-id="33ada-169">Statically Resolved Type Parameters</span></span>](statically-resolved-type-parameters.md)

[<span data-ttu-id="33ada-170">.NET Framework의 제네릭</span><span class="sxs-lookup"><span data-stu-id="33ada-170">Generics in the .NET Framework</span></span>](~/docs/standard/generics/index.md)

[<span data-ttu-id="33ada-171">자동 일반화</span><span class="sxs-lookup"><span data-stu-id="33ada-171">Automatic Generalization</span></span>](automatic-generalization.md)

[<span data-ttu-id="33ada-172">제약 조건</span><span class="sxs-lookup"><span data-stu-id="33ada-172">Constraints</span></span>](constraints.md)
