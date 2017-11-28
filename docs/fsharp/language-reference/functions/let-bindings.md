---
title: "let 바인딩(F#)"
description: "F # 식별자 값 또는 함수를 연결 하는 바인딩 ' let'를 사용 하는 방법에 알아봅니다."
keywords: "visual f#, f#, 함수형 프로그래밍"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: bee69edc-d5ae-46bd-8b56-f02d97725d0d
ms.openlocfilehash: a57c5572e4bb5a3777c928dd572b7a84d4f0a334
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="let-bindings"></a><span data-ttu-id="a1cbc-104">let 바인딩</span><span class="sxs-lookup"><span data-stu-id="a1cbc-104">let Bindings</span></span>

<span data-ttu-id="a1cbc-105">A *바인딩* 식별자는 값 또는 함수를 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1cbc-105">A *binding* associates an identifier with a value or function.</span></span> <span data-ttu-id="a1cbc-106">사용 하면는 `let` 값 또는 함수에는 이름을 바인딩하는 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="a1cbc-106">You use the `let` keyword to bind a name to a value or function.</span></span>

## <a name="syntax"></a><span data-ttu-id="a1cbc-107">구문</span><span class="sxs-lookup"><span data-stu-id="a1cbc-107">Syntax</span></span>

```fsharp
// Binding a value:
let identifier-or-pattern [: type] =expressionbody-expression
// Binding a function value:
let identifier parameter-list [: return-type ] =expressionbody-expression
```

## <a name="remarks"></a><span data-ttu-id="a1cbc-108">설명</span><span class="sxs-lookup"><span data-stu-id="a1cbc-108">Remarks</span></span>

<span data-ttu-id="a1cbc-109">`let` 키워드 또는 하나 이상의 이름에 대 한 함수 값을 정의 하는 바인딩 식에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1cbc-109">The `let` keyword is used in binding expressions to define values or function values for one or more names.</span></span> <span data-ttu-id="a1cbc-110">가장 간단한 형태는 `let` 식은 간단한 값에 다음과 같이 이름의 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="a1cbc-110">The simplest form of the `let` expression binds a name to a simple value, as follows.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1101.fs)]

<span data-ttu-id="a1cbc-111">새 줄을 사용 하 여 식에서 식별자를 구분 하면 각 줄에 다음 코드 처럼 식에 써야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1cbc-111">If you separate the expression from the identifier by using a new line, you must indent each line of the expression, as in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1102.fs)]

<span data-ttu-id="a1cbc-112">단순한 이름 대신 이름을 포함 하는 패턴을 지정할 수 있습니다, 예를 들어, 튜플, 다음 코드에 나와 있는 것 처럼 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1cbc-112">Instead of just a name, a pattern that contains names can be specified, for example, a tuple, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1103.fs)]

<span data-ttu-id="a1cbc-113">*본문 식* 이름이 사용 되는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="a1cbc-113">The *body-expression* is the expression in which the names are used.</span></span> <span data-ttu-id="a1cbc-114">본문 식의 첫 번째 문자로 정확히 위로 줄 들여쓰기 자체 줄에 표시 되는 `let` 키워드:</span><span class="sxs-lookup"><span data-stu-id="a1cbc-114">The body expression appears on its own line, indented to line up exactly with the first character in the `let` keyword:</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1104.fs)]

<span data-ttu-id="a1cbc-115">A `let` 바인딩은 될 수 있습니다는 클래스 형식의 정의에서 나 로컬 범위에서 모듈 수준 등에 함수 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1cbc-115">A `let` binding can appear at the module level, in the definition of a class type, or in local scopes, such as in a function definition.</span></span> <span data-ttu-id="a1cbc-116">A `let` 최상위에는 모듈 또는 클래스 형식에 바인딩 본문 식이 필요 하지는 않지만 다른 범위 수준에서 본문 식이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1cbc-116">A `let` binding at the top level in a module or in a class type does not need to have a body expression, but at other scope levels, the body expression is required.</span></span> <span data-ttu-id="a1cbc-117">하지만 먼저에 없는 정의의 지점 이후에 바인딩된 이름은 사용할 수는 `let` 다음 코드 에서처럼 바인딩 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="a1cbc-117">The bound names are usable after the point of definition, but not at any point before the `let` binding appears, as is illustrated in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1105.fs)]
    
## <a name="function-bindings"></a><span data-ttu-id="a1cbc-118">함수 바인딩이</span><span class="sxs-lookup"><span data-stu-id="a1cbc-118">Function Bindings</span></span>

<span data-ttu-id="a1cbc-119">다음 코드에 표시 된 함수 이름과 매개 변수를 함수 바인딩을 포함 하는 점을 제외 하 고 함수 바인딩이 값 바인딩에 대 한 규칙을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="a1cbc-119">Function bindings follow the rules for value bindings, except that function bindings include the function name and the parameters, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1106.fs)]

<span data-ttu-id="a1cbc-120">일반적으로 매개 변수는 튜플 패턴 같은 패턴.</span><span class="sxs-lookup"><span data-stu-id="a1cbc-120">In general, parameters are patterns, such as a tuple pattern:</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1107.fs)]

<span data-ttu-id="a1cbc-121">A `let` 마지막 식의 값으로 계산 바인딩 식입니다.</span><span class="sxs-lookup"><span data-stu-id="a1cbc-121">A `let` binding expression evaluates to the value of the last expression.</span></span> <span data-ttu-id="a1cbc-122">따라서 다음 코드 예제에서는 값에서에서 `result` 에서 계산 `100 * function3 (1, 2)`를 반환 하 `300`합니다.</span><span class="sxs-lookup"><span data-stu-id="a1cbc-122">Therefore, in the following code example, the value of `result` is computed from `100 * function3 (1, 2)`, which evaluates to `300`.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1109.fs)]

<span data-ttu-id="a1cbc-123">자세한 내용은 [함수](index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a1cbc-123">For more information, see [Functions](index.md).</span></span>

## <a name="type-annotations"></a><span data-ttu-id="a1cbc-124">형식 주석</span><span class="sxs-lookup"><span data-stu-id="a1cbc-124">Type Annotations</span></span>

<span data-ttu-id="a1cbc-125">괄호 안에 포함 된 모든 형식 이름 뒤에 오는 콜론 (:)를 포함 하 여 매개 변수를 형식에 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1cbc-125">You can specify types for parameters by including a colon (:) followed by a type name, all enclosed in parentheses.</span></span> <span data-ttu-id="a1cbc-126">또한 마지막 매개 변수 뒤에 콜론과 형식을 추가 하 여 반환 값의 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1cbc-126">You can also specify the type of the return value by appending the colon and type after the last parameter.</span></span> <span data-ttu-id="a1cbc-127">에 대 한 전체 형식 주석을 `function1`, 매개 변수 형식으로 정수를 사용할 때 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a1cbc-127">The full type annotations for `function1`, with integers as the parameter types, would be as follows.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1108.fs)]

<span data-ttu-id="a1cbc-128">명시적 형식 매개 변수가 없는 경우 형식 유추를 함수 매개 변수의 형식을 결정 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1cbc-128">When there are no explicit type parameters, type inference is used to determine the types of parameters of functions.</span></span> <span data-ttu-id="a1cbc-129">이 형식의 제네릭 매개 변수를 자동으로 일반화 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1cbc-129">This can include automatically generalizing the type of a parameter to be generic.</span></span>

<span data-ttu-id="a1cbc-130">자세한 내용은 참조 [자동 일반화](../generics/automatic-generalization.md) 및 [형식 유추](../type-inference.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a1cbc-130">For more information, see [Automatic Generalization](../generics/automatic-generalization.md) and [Type Inference](../type-inference.md).</span></span>

## <a name="let-bindings-in-classes"></a><span data-ttu-id="a1cbc-131">클래스의 let 바인딩</span><span class="sxs-lookup"><span data-stu-id="a1cbc-131">let Bindings in Classes</span></span>

<span data-ttu-id="a1cbc-132">A `let` 바인딩 구조 또는 레코드 종류는 있지만 클래스 형식에 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1cbc-132">A `let` binding can appear in a class type but not in a structure or record type.</span></span> <span data-ttu-id="a1cbc-133">클래스 형식에 바인딩 수를 사용 하려면 기본 생성자를 클래스에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1cbc-133">To use a let binding in a class type, the class must have a primary constructor.</span></span> <span data-ttu-id="a1cbc-134">생성자 매개 변수는 클래스 정의에 형식 이름 뒤에 나타나야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1cbc-134">Constructor parameters must appear after the type name in the class definition.</span></span> <span data-ttu-id="a1cbc-135">A `let` 전용 필드 및 멤버 해당 클래스 형식에 대 한와 함께 클래스 형식에 바인딩 정의 `do` 형식에서 바인딩 유형에 대 한 기본 생성자에 대 한 코드를 형성 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1cbc-135">A `let` binding in a class type defines private fields and members for that class type and, together with `do` bindings in the type, forms the code for the primary constructor for the type.</span></span> <span data-ttu-id="a1cbc-136">다음 코드 예제에서는 클래스를 보여 줍니다 `MyClass` 전용 필드와 `field1` 및 `field2`합니다.</span><span class="sxs-lookup"><span data-stu-id="a1cbc-136">The following code examples show a class `MyClass` with private fields `field1` and `field2`.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1110.fs)]

<span data-ttu-id="a1cbc-137">범위 `field1` 및 `field2` 선언 된 형식으로 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1cbc-137">The scopes of `field1` and `field2` are limited to the type in which they are declared.</span></span> <span data-ttu-id="a1cbc-138">자세한 내용은 참조 [ `let` 클래스에서](../members/let-bindings-in-classes.md) 및 [클래스](../classes.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a1cbc-138">For more information, see [`let` Bindings in Classes](../members/let-bindings-in-classes.md) and [Classes](../classes.md).</span></span>

## <a name="type-parameters-in-let-bindings"></a><span data-ttu-id="a1cbc-139">형식 매개 변수에 let 바인딩</span><span class="sxs-lookup"><span data-stu-id="a1cbc-139">Type Parameters in let Bindings</span></span>

<span data-ttu-id="a1cbc-140">A `let` 형식에서 또는 계산 식에서 모듈 수준에서 바인딩 명시적 형식 매개 변수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1cbc-140">A `let` binding at the module level, in a type, or in a computation expression can have explicit type parameters.</span></span> <span data-ttu-id="a1cbc-141">Let 함수 정의 내에서 같은 식에서 바인딩을 형식 매개 변수를 가질 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a1cbc-141">A let binding in an expression, such as within a function definition, cannot have type parameters.</span></span> <span data-ttu-id="a1cbc-142">자세한 내용은 [제네릭](../generics/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a1cbc-142">For more information, see [Generics](../generics/index.md).</span></span>

## <a name="attributes-on-let-bindings"></a><span data-ttu-id="a1cbc-143">특성을 let 바인딩</span><span class="sxs-lookup"><span data-stu-id="a1cbc-143">Attributes on let Bindings</span></span>

<span data-ttu-id="a1cbc-144">특성은 최상위에 적용할 수 `let` 모듈에서는 다음 코드에 나와 있는 것 처럼 바인딩.</span><span class="sxs-lookup"><span data-stu-id="a1cbc-144">Attributes can be applied to top-level `let` bindings in a module, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1111.fs)]
    
## <a name="scope-and-accessibility-of-let-bindings"></a><span data-ttu-id="a1cbc-145">범위 및 액세스 가능성의 Let 바인딩</span><span class="sxs-lookup"><span data-stu-id="a1cbc-145">Scope and Accessibility of Let Bindings</span></span>

<span data-ttu-id="a1cbc-146">Let 바인딩을 사용 하 여 선언 엔터티의 범위를 포함 하는 영역 제한 됩니다 바인딩에 표시 된 후 범위 (예: 함수, 모듈, 파일 또는 클래스).</span><span class="sxs-lookup"><span data-stu-id="a1cbc-146">The scope of an entity declared with a let binding is limited to the portion of the containing scope (such as a function, module, file or class) after the binding appears.</span></span> <span data-ttu-id="a1cbc-147">따라서이 방식이 적용 됩니다 let 바인딩 범위에는 이름을 새로 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1cbc-147">Therefore, it can be said that a let binding introduces a name into a scope.</span></span> <span data-ttu-id="a1cbc-148">모듈에서는 let 바인딩 값 또는 함수의 모듈의 클라이언트에서 액세스할 수 한 모듈은 모듈의 let 바인딩 모듈의 공용 함수로 컴파일되는 때문에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1cbc-148">In a module, a let-bound value or function is accessible to clients of a module as long as the module is accessible, since the let bindings in a module are compiled into public functions of the module.</span></span> <span data-ttu-id="a1cbc-149">반면, 클래스의 let 바인딩은 private 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="a1cbc-149">By contrast, let bindings in a class are private to the class.</span></span>

<span data-ttu-id="a1cbc-150">일반적으로 모듈의 함수는 클라이언트 코드에서 사용 하는 경우 모듈의 이름으로 한정 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1cbc-150">Normally, functions in modules must be qualified by the name of the module when used by client code.</span></span> <span data-ttu-id="a1cbc-151">예를 들어 모듈 `Module1` 함수 `function1`, 사용자 지정 `Module1.function1` 에 함수를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1cbc-151">For example, if a module `Module1` has a function `function1`, users would specify `Module1.function1` to refer to the function.</span></span>

<span data-ttu-id="a1cbc-152">사용자가 모듈의 모듈 이름으로 한정 되지 않고 해당 모듈 내에서 함수를 사용 하기 위해 사용할 수 있도록 하는 가져오기 선언을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1cbc-152">Users of a module may use an import declaration to make the functions within that module available for use without being qualified by the module name.</span></span> <span data-ttu-id="a1cbc-153">위에서 언급 한 예에서 사용자가 모듈의 경우 열 수 모듈 가져오기 선언 열기를 사용 하 여 `Module1` 이후에 참조할 `function1` 직접 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1cbc-153">In the example just mentioned, users of the module can in that case open the module by using the import declaration open `Module1` and thereafter refer to `function1` directly.</span></span>

```fsharp
module Module1 =
    let function1 x = x + 1.0

module Module2 =
    let function2 x =
        Module1.function1 x

open Module1

let function3 x =
    function1 x
```

<span data-ttu-id="a1cbc-154">일부 모듈 특성이 [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15), 즉, 제공 하는 함수 모듈의 이름으로 한정 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1cbc-154">Some modules have the attribute [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15), which means that the functions that they expose must be qualified with the name of the module.</span></span> <span data-ttu-id="a1cbc-155">예를 들어 F # List 모듈에는이 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1cbc-155">For example, the F# List module has this attribute.</span></span>

<span data-ttu-id="a1cbc-156">모듈 및 액세스 제어에 대 한 자세한 내용은 참조 하십시오. [모듈](../modules.md) 및 [액세스 제어](../access-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a1cbc-156">For more information on modules and access control, see [Modules](../modules.md) and [Access Control](../access-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a1cbc-157">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a1cbc-157">See Also</span></span>

[<span data-ttu-id="a1cbc-158">함수</span><span class="sxs-lookup"><span data-stu-id="a1cbc-158">Functions</span></span>](index.md)

[<span data-ttu-id="a1cbc-159">클래스의 `let` 바인딩</span><span class="sxs-lookup"><span data-stu-id="a1cbc-159">`let` Bindings in Classes</span></span>](../members/let-bindings-in-classes.md)
