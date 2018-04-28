---
title: 코드 인용(F#)
description: '생성 하 고 프로그래밍 방식으로 F # 코드 식을 사용할 수 있는 언어 기능 F # 코드 인용에 알아봅니다.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: cfa2e4b9a4ad1776315dfa8ea82fb8fc3f13a552
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="code-quotations"></a><span data-ttu-id="d2bc1-103">코드 인용</span><span class="sxs-lookup"><span data-stu-id="d2bc1-103">Code Quotations</span></span>

> [!NOTE]
<span data-ttu-id="d2bc1-104">API 참조 링크를 통해 MSDN으로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2bc1-104">The API reference link will take you to MSDN.</span></span>  <span data-ttu-id="d2bc1-105">docs.microsoft.com API 참조가 완전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2bc1-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="d2bc1-106">이 항목에서는 설명 *코드 인용*를 생성 하 고 프로그래밍 방식으로 F # 코드 식을 사용할 수 있는 언어 기능.</span><span class="sxs-lookup"><span data-stu-id="d2bc1-106">This topic describes *code quotations*, a language feature that enables you to generate and work with F# code expressions programmatically.</span></span> <span data-ttu-id="d2bc1-107">이 기능을 사용 하는 추상 구문 트리 F # 코드를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2bc1-107">This feature lets you generate an abstract syntax tree that represents F# code.</span></span> <span data-ttu-id="d2bc1-108">추상 구문 트리 트래버스 고 그런 다음 응용 프로그램의 필요에 따라 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2bc1-108">The abstract syntax tree can then be traversed and processed according to the needs of your application.</span></span> <span data-ttu-id="d2bc1-109">예를 들어 F # 코드를 생성 하거나 다른 언어의 코드를 생성 하 여 트리를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2bc1-109">For example, you can use the tree to generate F# code or generate code in some other language.</span></span>


## <a name="quoted-expressions"></a><span data-ttu-id="d2bc1-110">따옴표 붙은 식</span><span class="sxs-lookup"><span data-stu-id="d2bc1-110">Quoted Expressions</span></span>
<span data-ttu-id="d2bc1-111">A *인용 된 식* 식인지 F # 코드 프로그램의 일부분으로 컴파일되지 않은 방식으로 구분 되지만 대신 컴파일 결과 F # 식을 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="d2bc1-111">A *quoted expression* is an F# expression in your code that is delimited in such a way that it is not compiled as part of your program, but instead is compiled into an object that represents an F# expression.</span></span> <span data-ttu-id="d2bc1-112">두 가지 방법 중 하나에 따옴표 붙은 식에 표시할 수 있습니다: 형식 정보를 사용 하거나 형식 정보 없이 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2bc1-112">You can mark a quoted expression in one of two ways: either with type information or without type information.</span></span> <span data-ttu-id="d2bc1-113">기호를 사용 하는 형식 정보를 포함 하려는 경우 `<@` 및 `@>` 에 인용된 된 식을 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2bc1-113">If you want to include type information, you use the symbols `<@` and `@>` to delimit the quoted expression.</span></span> <span data-ttu-id="d2bc1-114">기호를 사용 하는 형식 정보를 필요 하지 않은 경우 `<@@` 및 `@@>`합니다.</span><span class="sxs-lookup"><span data-stu-id="d2bc1-114">If you do not need type information, you use the symbols `<@@` and `@@>`.</span></span> <span data-ttu-id="d2bc1-115">다음 코드는 형식화 및 형식화 되지 않은 인용구를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d2bc1-115">The following code shows typed and untyped quotations.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet501.fs)]

<span data-ttu-id="d2bc1-116">식 트리를 트래버스하는 형식 정보를 포함 하지 않는 경우 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2bc1-116">Traversing a large expression tree is faster if you do not include type information.</span></span> <span data-ttu-id="d2bc1-117">형식화 된 기호가 포함 된 따옴표 붙은 식의 결과 형식이 `Expr<'T>`, 여기서 형식 매개 변수는 F # 컴파일러는 형식 유추 알고리즘을 기준으로 식의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d2bc1-117">The resulting type of an expression quoted with the typed symbols is `Expr<'T>`, where the type parameter has the type of the expression as determined by the F# compiler's type inference algorithm.</span></span> <span data-ttu-id="d2bc1-118">따옴표 붙은 식의 형식이 제네릭이 아닌 형식 형식 정보 없이 코드 인용을 사용 하면 [Expr](https://msdn.microsoft.com/library/ed6a2caf-69d4-45c2-ab97-e9b3be9bce65)합니다.</span><span class="sxs-lookup"><span data-stu-id="d2bc1-118">When you use code quotations without type information, the type of the quoted expression is the non-generic type [Expr](https://msdn.microsoft.com/library/ed6a2caf-69d4-45c2-ab97-e9b3be9bce65).</span></span> <span data-ttu-id="d2bc1-119">호출할 수 있습니다는 [Raw](https://msdn.microsoft.com/library/47fb94f1-e77f-4c68-aabc-2b0ba40d59c2) 속성에는 형식화 된 `Expr` 클래스는 형식화 되지 않은 얻으려고 `Expr` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="d2bc1-119">You can call the [Raw](https://msdn.microsoft.com/library/47fb94f1-e77f-4c68-aabc-2b0ba40d59c2) property on the typed `Expr` class to obtain the untyped `Expr` object.</span></span>

<span data-ttu-id="d2bc1-120">다양 한 개체를 생성 하 F # 식을 프로그래밍 방식으로 사용할 수 있는 정적 메서드는 `Expr` 클래스를 사용 하지 않고 따옴표 붙은 식입니다.</span><span class="sxs-lookup"><span data-stu-id="d2bc1-120">There are a variety of static methods that allow you to generate F# expression objects programmatically in the `Expr` class without using quoted expressions.</span></span>

<span data-ttu-id="d2bc1-121">참고 코드 인용에는 전체 식이 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2bc1-121">Note that a code quotation must include a complete expression.</span></span> <span data-ttu-id="d2bc1-122">에 대 한는 `let` 바인딩, 예를 들어 필요한 바인딩된 이름 및 바인딩을 사용 하는 추가 식을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2bc1-122">For a `let` binding, for example, you need both the definition of the bound name and an additional expression that uses the binding.</span></span> <span data-ttu-id="d2bc1-123">자세한 구문에서이 다음에 나오는 식의 `in` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="d2bc1-123">In verbose syntax, this is an expression that follows the `in` keyword.</span></span> <span data-ttu-id="d2bc1-124">모듈의 최상위 수준에서이 모듈에서 다음 식을 방금 이지만 인용에 명시적으로 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2bc1-124">At the top-level in a module, this is just the next expression in the module, but in a quotation, it is explicitly required.</span></span>

<span data-ttu-id="d2bc1-125">따라서 다음 식은 올바르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2bc1-125">Therefore, the following expression is not valid.</span></span>

```fsharp
// Not valid:
// <@ let f x = x + 1 @>
```

<span data-ttu-id="d2bc1-126">하지만 다음 식은 올바릅니다.</span><span class="sxs-lookup"><span data-stu-id="d2bc1-126">But the following expressions are valid.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet502.fs)]

<span data-ttu-id="d2bc1-127">코드 인용을 사용 하려면 가져오기 선언 추가 해야 합니다 (사용 하 여는 `open` 키워드)가 열립니다는 [Microsoft.FSharp.Quotations](https://msdn.microsoft.com/library/e9ce8a3a-e00c-4190-bad5-cce52ee089b2) 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="d2bc1-127">To use code quotations, you must add an import declaration (by using the `open` keyword) that opens the [Microsoft.FSharp.Quotations](https://msdn.microsoft.com/library/e9ce8a3a-e00c-4190-bad5-cce52ee089b2) namespace.</span></span>

<span data-ttu-id="d2bc1-128">F # PowerPack 평가 하 고 실행 하는 F # 식을 개체에 대 한 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2bc1-128">The F# PowerPack provides support for evaluating and executing F# expression objects.</span></span>


## <a name="expr-type"></a><span data-ttu-id="d2bc1-129">Expr 형식</span><span class="sxs-lookup"><span data-stu-id="d2bc1-129">Expr Type</span></span>
<span data-ttu-id="d2bc1-130">인스턴스는 `Expr` 유형은 F # 식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d2bc1-130">An instance of the `Expr` type represents an F# expression.</span></span> <span data-ttu-id="d2bc1-131">제네릭과 제네릭이 아닌 `Expr` 유형은 F # 라이브러리 설명서에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2bc1-131">Both the generic and the non-generic `Expr` types are documented in the F# library documentation.</span></span> <span data-ttu-id="d2bc1-132">자세한 내용은 참조 [Microsoft.FSharp.Quotations Namespace](https://msdn.microsoft.com/visualfsharpdocs/conceptual/microsoft.fsharp.quotations-namespace-%5bfsharp%5d) 및 [Quotations.Expr 클래스](https://msdn.microsoft.com/visualfsharpdocs/conceptual/quotations.expr-class-%5bfsharp%5d)합니다.</span><span class="sxs-lookup"><span data-stu-id="d2bc1-132">For more information, see [Microsoft.FSharp.Quotations Namespace](https://msdn.microsoft.com/visualfsharpdocs/conceptual/microsoft.fsharp.quotations-namespace-%5bfsharp%5d) and [Quotations.Expr Class](https://msdn.microsoft.com/visualfsharpdocs/conceptual/quotations.expr-class-%5bfsharp%5d).</span></span>


## <a name="splicing-operators"></a><span data-ttu-id="d2bc1-133">결합 연산자</span><span class="sxs-lookup"><span data-stu-id="d2bc1-133">Splicing Operators</span></span>
<span data-ttu-id="d2bc1-134">스플라이스 리터럴 코드 인용을 프로그래밍 방식으로 또는 다른 코드 인용에서 만든 식과 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2bc1-134">Splicing enables you to combine literal code quotations with expressions that you have created programmatically or from another code quotation.</span></span> <span data-ttu-id="d2bc1-135">`%` 및 `%%` 연산자를 사용 하는 코드 인용에 F # 식을 개체를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2bc1-135">The `%` and `%%` operators enable you to add an F# expression object into a code quotation.</span></span> <span data-ttu-id="d2bc1-136">사용 된 `%` 형식화 된 인용에 식을 형식화 된 개체를 삽입 하는 연산자를 사용 하 여는 `%%` 연산자를 형식화 되지 않은 인용에 식을 형식화 되지 않은 개체를 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2bc1-136">You use the `%` operator to insert a typed expression object into a typed quotation; you use the `%%` operator to insert an untyped expression object into an untyped quotation.</span></span> <span data-ttu-id="d2bc1-137">두 연산자는 단항 전위 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="d2bc1-137">Both operators are unary prefix operators.</span></span> <span data-ttu-id="d2bc1-138">따라서 경우 `expr` 형식의 식이 형식화 되지 않은 `Expr`, 다음 코드는 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2bc1-138">Thus if `expr` is an untyped expression of type `Expr`, the following code is valid.</span></span>

```fsharp
<@@ 1 + %%expr @@>
```

<span data-ttu-id="d2bc1-139">쓰고 `expr` 형식의 형식화 된 견적 `Expr<int>`, 다음 코드는 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2bc1-139">And if `expr` is a typed quotation of type `Expr<int>`, the following code is valid.</span></span>

```fsharp
<@ 1 + %expr @>
```

## <a name="example"></a><span data-ttu-id="d2bc1-140">예제</span><span class="sxs-lookup"><span data-stu-id="d2bc1-140">Example</span></span>

### <a name="description"></a><span data-ttu-id="d2bc1-141">설명</span><span class="sxs-lookup"><span data-stu-id="d2bc1-141">Description</span></span>
<span data-ttu-id="d2bc1-142">다음 예제에서는 식 개체에 F # 코드를 저장 한 다음 식의 F # 코드를 인쇄 코드 인용의 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d2bc1-142">The following example illustrates the use of code quotations to put F# code into an expression object and then print the F# code that represents the expression.</span></span> <span data-ttu-id="d2bc1-143">함수 `println` 정의 된 재귀 함수를 포함 하 `print` F # 식을 개체를 표시 하는 (형식의 `Expr`)는 친숙 한 형태로 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2bc1-143">A function `println` is defined that contains a recursive function `print` that displays an F# expression object (of type `Expr`) in a friendly format.</span></span> <span data-ttu-id="d2bc1-144">여러 활성 패턴은는 [Microsoft.FSharp.Quotations.Patterns](https://msdn.microsoft.com/library/093944a9-c752-403a-8983-5fcd5dbf92a4) 및 [Microsoft.FSharp.Quotations.DerivedPatterns](https://msdn.microsoft.com/library/d2434a6e-ae7b-4f3d-b567-c162938bc9cd) 식 개체를 분석에 사용할 수 있는 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="d2bc1-144">There are several active patterns in the [Microsoft.FSharp.Quotations.Patterns](https://msdn.microsoft.com/library/093944a9-c752-403a-8983-5fcd5dbf92a4) and [Microsoft.FSharp.Quotations.DerivedPatterns](https://msdn.microsoft.com/library/d2434a6e-ae7b-4f3d-b567-c162938bc9cd) modules that can be used to analyze expression objects.</span></span> <span data-ttu-id="d2bc1-145">이 예에서는 F # 식을에 표시 될 수 있는 모든 패턴을 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2bc1-145">This example does not include all the possible patterns that might appear in an F# expression.</span></span> <span data-ttu-id="d2bc1-146">패턴에 와일드 카드 패턴에 일치 하는 트리거 인식 되지 않은 (`_`) 하 고 사용 하 여 렌더링 되는 `ToString` 메서드 이며에 `Expr` 입력에 일치 하는 식에 추가할 활성 패턴을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2bc1-146">Any unrecognized pattern triggers a match to the wildcard pattern (`_`) and is rendered by using the `ToString` method, which, on the `Expr` type, lets you know the active pattern to add to your match expression.</span></span>


### <a name="code"></a><span data-ttu-id="d2bc1-147">코드</span><span class="sxs-lookup"><span data-stu-id="d2bc1-147">Code</span></span>
[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet601.fs)]
    
### <a name="output"></a><span data-ttu-id="d2bc1-148">출력</span><span class="sxs-lookup"><span data-stu-id="d2bc1-148">Output</span></span>

```fsharp
fun (x:System.Int32) -> x + 1
a + 1
let f = fun (x:System.Int32) -> x + 10 in f 10
```

## <a name="example"></a><span data-ttu-id="d2bc1-149">예제</span><span class="sxs-lookup"><span data-stu-id="d2bc1-149">Example</span></span>

### <a name="description"></a><span data-ttu-id="d2bc1-150">설명</span><span class="sxs-lookup"><span data-stu-id="d2bc1-150">Description</span></span>
<span data-ttu-id="d2bc1-151">세 가지 활성 패턴을 사용할 수도 있습니다는 [ExprShape 모듈](https://msdn.microsoft.com/library/7685150e-2432-4d39-9338-57292eff18de) 적은 활성 패턴으로 식 트리를 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2bc1-151">You can also use the three active patterns in the [ExprShape module](https://msdn.microsoft.com/library/7685150e-2432-4d39-9338-57292eff18de) to traverse expression trees with fewer active patterns.</span></span> <span data-ttu-id="d2bc1-152">이러한 활성 패턴 트리 이동 하지만 대부분의 노드에서 있는 모든 정보를 불필요 하는 경우 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2bc1-152">These active patterns can be useful when you want to traverse a tree but you do not need all the information in most of the nodes.</span></span> <span data-ttu-id="d2bc1-153">F # 식이 다음 세 가지 패턴 중 하 나와 일치 하는 이러한 패턴을 사용 하는 경우: `ShapeVar` 식이 변수에 `ShapeLambda` 식 람다 식의 값 또는 `ShapeCombination` 식이 80 이외 인 경우.</span><span class="sxs-lookup"><span data-stu-id="d2bc1-153">When you use these patterns, any F# expression matches one of the following three patterns: `ShapeVar` if the expression is a variable, `ShapeLambda` if the expression is a lambda expression, or `ShapeCombination` if the expression is anything else.</span></span> <span data-ttu-id="d2bc1-154">이전 코드 예제와 같이 활성 패턴을 사용 하 여 식 트리를 이동 하는 경우 모든 가능한 F # 식은 형식에 처리 하기 위해 더 많은 패턴을 사용 해야 하 고 코드를 더 복잡 해질 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2bc1-154">If you traverse an expression tree by using the active patterns as in the previous code example, you have to use many more patterns to handle all possible F# expression types, and your code will be more complex.</span></span> <span data-ttu-id="d2bc1-155">자세한 내용은 참조 [ExprShape.ShapeVar&#124;ShapeLambda&#124;ShapeCombination 활성 패턴](https://msdn.microsoft.com/visualfsharpdocs/conceptual/exprshape.shapevarhshapelambdahshapecombination-active-pattern-%5bfsharp%5d)합니다.</span><span class="sxs-lookup"><span data-stu-id="d2bc1-155">For more information, see [ExprShape.ShapeVar&#124;ShapeLambda&#124;ShapeCombination Active Pattern](https://msdn.microsoft.com/visualfsharpdocs/conceptual/exprshape.shapevarhshapelambdahshapecombination-active-pattern-%5bfsharp%5d).</span></span>

<span data-ttu-id="d2bc1-156">다음 코드 예제에서는 보다 복잡 한 순회에 대 한 기준으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2bc1-156">The following code example can be used as a basis for more complex traversals.</span></span> <span data-ttu-id="d2bc1-157">이 코드에서는 함수 호출을 포함 하는 식에 대 한 식 트리 만들어집니다 `add`합니다.</span><span class="sxs-lookup"><span data-stu-id="d2bc1-157">In this code, an expression tree is created for an expression that involves a function call, `add`.</span></span> <span data-ttu-id="d2bc1-158">[SpecificCall](https://msdn.microsoft.com/library/05a77b21-20fe-4b9a-8e07-aa999538198d) 활성 패턴은 한 모든 호출을 검색 하는 데 사용 `add` 식 트리에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2bc1-158">The [SpecificCall](https://msdn.microsoft.com/library/05a77b21-20fe-4b9a-8e07-aa999538198d) active pattern is used to detect any call to `add` in the expression tree.</span></span> <span data-ttu-id="d2bc1-159">이 활성 패턴 할당에 대 한 호출의 인수는 `exprList` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d2bc1-159">This active pattern assigns the arguments of the call to the `exprList` value.</span></span> <span data-ttu-id="d2bc1-160">이 경우 많습니다 두 개만 개뿐이므로 이들 및 함수는 인수에 재귀적으로 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2bc1-160">In this case, there are only two, so these are pulled out and the function is called recursively on the arguments.</span></span> <span data-ttu-id="d2bc1-161">결과에 대 한 호출을 나타내는 코드 인용에 삽입 됩니다 `mul` 스플라이스 연산자를 사용 하 여 (`%%`).</span><span class="sxs-lookup"><span data-stu-id="d2bc1-161">The results are inserted into a code quotation that represents a call to `mul` by using the splice operator (`%%`).</span></span> <span data-ttu-id="d2bc1-162">`println` 이전 예제에서 함수는 결과 표시 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2bc1-162">The `println` function from the previous example is used to display the results.</span></span>

<span data-ttu-id="d2bc1-163">다른 활성 패턴 분기의 코드를 다시 생성 하기만 동일한 식 트리를 되므로 결과 식은 작업만에서 변경 `add` 를 `mul`합니다.</span><span class="sxs-lookup"><span data-stu-id="d2bc1-163">The code in the other active pattern branches just regenerates the same expression tree, so the only change in the resulting expression is the change from `add` to `mul`.</span></span>


### <a name="code"></a><span data-ttu-id="d2bc1-164">코드</span><span class="sxs-lookup"><span data-stu-id="d2bc1-164">Code</span></span>
[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet701.fs)]
    
### <a name="output"></a><span data-ttu-id="d2bc1-165">출력</span><span class="sxs-lookup"><span data-stu-id="d2bc1-165">Output</span></span>

```fsharp
1 + Module1.add(2,Module1.add(3,4))
1 + Module1.mul(2,Module1.mul(3,4))
```

## <a name="see-also"></a><span data-ttu-id="d2bc1-166">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d2bc1-166">See Also</span></span>
[<span data-ttu-id="d2bc1-167">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="d2bc1-167">F# Language Reference</span></span>](index.md)

