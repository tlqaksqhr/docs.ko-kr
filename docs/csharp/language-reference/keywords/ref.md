---
title: ref(C# 참조)
ms.date: 03/06/2018
f1_keywords:
- ref_CSharpKeyword
- ref
helpviewer_keywords:
- parameters [C#], ref
- ref keyword [C#]
ms.openlocfilehash: a72624d5702ec12bfda98d49a16474cc84205ff0
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/25/2018
ms.locfileid: "39245754"
---
# <a name="ref-c-reference"></a><span data-ttu-id="1bce7-102">ref(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="1bce7-102">ref (C# Reference)</span></span>

<span data-ttu-id="1bce7-103">`ref` 키워드는 참조로 전달되는 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1bce7-103">The `ref` keyword indicates a value that is passed by reference.</span></span> <span data-ttu-id="1bce7-104">다음 네 가지 컨텍스트에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bce7-104">It is used in four different contexts:</span></span>

- <span data-ttu-id="1bce7-105">메서드 시그니처 및 메서드 호출에서 인수를 메서드에 참조로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="1bce7-105">In a method signature and in a method call, to pass an argument to a method by reference.</span></span> <span data-ttu-id="1bce7-106">자세한 내용은 [참조로 인수 전달](#passing-an-argument-by-reference)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1bce7-106">See [Passing an argument by reference](#passing-an-argument-by-reference) for more information.</span></span>
- <span data-ttu-id="1bce7-107">메서드 시그니처에서 값을 호출자에게 참조로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="1bce7-107">In a method signature, to return a value to the caller by reference.</span></span> <span data-ttu-id="1bce7-108">자세한 내용은 [참조 반환 값](#reference-return-values)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1bce7-108">See [Reference return values](#reference-return-values) for more information.</span></span>
- <span data-ttu-id="1bce7-109">멤버 본문에서 참조 반환 값이 호출자가 수정하려는 참조로 로컬에 저장되거나 일반적으로 로컬 변수가 참조를 기준으로 다른 값에 액세스 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1bce7-109">In a member body, to indicate that a reference return value is stored locally as a reference that the caller intends to modify or, in general, a local variable accesses another value by reference.</span></span> <span data-ttu-id="1bce7-110">자세한 내용은 [참조 로컬](#ref-locals)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1bce7-110">See [Ref locals](#ref-locals) for more information.</span></span>
- <span data-ttu-id="1bce7-111">`ref struct` 또는 `ref readonly struct`을 선언하기 위한 `struct` 선언서.</span><span class="sxs-lookup"><span data-stu-id="1bce7-111">In a `struct` declaration to declare a `ref struct` or a `ref readonly struct`.</span></span> <span data-ttu-id="1bce7-112">자세한 내용은 [참조 구조체 선언](#ref-struct-declarations)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1bce7-112">See [ref struct declarations](#ref-struct-declarations) for more information.</span></span>

## <a name="passing-an-argument-by-reference"></a><span data-ttu-id="1bce7-113">참조로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="1bce7-113">Passing an argument by reference</span></span>

<span data-ttu-id="1bce7-114">메서드의 매개 변수 목록에 사용되는 경우 `ref` 키워드는 인수가 값이 아니라 참조로 전달됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1bce7-114">When used in a method's parameter list, the `ref` keyword indicates that an argument is passed by reference, not by value.</span></span> <span data-ttu-id="1bce7-115">인수를 참조로 전달하는 경우 호출된 메서드의 인수 변경 내용이 호출 메서드에 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bce7-115">The effect of passing by reference is that any change to the argument in the called method is reflected in the calling method.</span></span> <span data-ttu-id="1bce7-116">예를 들어 호출자가 지역 변수 식 또는 배열 요소 액세스 식을 전달하는 경우 호출된 메서드에서 ref 매개 변수가 참조하는 개체를 바꾸면 메서드 반환 시 호출자의 지역 변수 또는 배열 요소가 새 개체를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="1bce7-116">For example, if the caller passes a local variable expression or an array element access expression, and the called method replaces the object to which the ref parameter refers, then the caller’s local variable or the array element now refers to the new object when the method returns.</span></span>

> [!NOTE]
> <span data-ttu-id="1bce7-117">참조로 전달의 개념과 참조 형식의 개념을 혼동해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bce7-117">Do not confuse the concept of passing by reference with the concept of reference types.</span></span> <span data-ttu-id="1bce7-118">이 두 개념은 서로 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="1bce7-118">The two concepts are not the same.</span></span> <span data-ttu-id="1bce7-119">메서드 매개 변수는 값 형식이든 참조 형식이든 관계없이 `ref`를 통해 수정할 수 있으며,</span><span class="sxs-lookup"><span data-stu-id="1bce7-119">A method parameter can be modified by `ref` regardless of whether it is a value type or a reference type.</span></span> <span data-ttu-id="1bce7-120">참조로 전달되는 경우 값 형식은 boxing되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1bce7-120">There is no boxing of a value type when it is passed by reference.</span></span>  

<span data-ttu-id="1bce7-121">`ref` 매개 변수를 사용하려면 다음 예제에 나와 있는 것처럼 메서드 정의와 호출 메서드가 모두 `ref` 키워드를 명시적으로 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1bce7-121">To use a `ref` parameter, both the method definition and the calling method must explicitly use the `ref` keyword, as shown in the following example.</span></span>  

[!code-csharp-interactive[csrefKeywordsMethodParams#6](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#1)]

<span data-ttu-id="1bce7-122">`ref` 또는 `in` 매개 변수로 전달하는 인수는 전달 전에 초기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1bce7-122">An argument that is passed to a `ref` or `in` parameter must be initialized before it is passed.</span></span> <span data-ttu-id="1bce7-123">이러한 방식은 인수를 전달하기 전에 명시적으로 초기화할 필요가 없는 [out](out-parameter-modifier.md) 매개 변수와는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="1bce7-123">This differs from [out](out-parameter-modifier.md) parameters, whose arguments do not have to be explicitly initialized before they are passed.</span></span>

<span data-ttu-id="1bce7-124">클래스의 멤버는 `ref`, `in` 또는 `out`만 다른 서명을 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1bce7-124">Members of a class can't have signatures that differ only by `ref`, `in`, or `out`.</span></span> <span data-ttu-id="1bce7-125">특정 형식의 두 멤버가 하나는 `ref` 매개 변수를 포함하고 다른 하나는 `out` 또는 `in` 매개 변수를 포함한다는 것 외에는 차이가 없으면 컴파일러 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="1bce7-125">A compiler error occurs if the only difference between two members of a type is that one of them has a `ref` parameter and the other has an `out`, or `in` parameter.</span></span> <span data-ttu-id="1bce7-126">예를 들어 다음 코드는 컴파일되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1bce7-126">The following code, for example, doesn't compile.</span></span>  

```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded 
    // methods that differ only on ref and out".
    public void SampleMethod(out int i) { }
    public void SampleMethod(ref int i) { }
}
```

<span data-ttu-id="1bce7-127">그러나 다음 예제에 나와 있는 것처럼 메서드 하나에는 `ref`, `in` 또는 `out` 매개 변수가 포함되어 있고 다른 하나에는 값 매개 변수가 포함되어 있으면 메서드를 오버로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bce7-127">However, methods can be overloaded when one method has a `ref`, `in`, or `out` parameter and the other has a value parameter, as shown in the following example.</span></span>
  
[!code-csharp[csrefKeywordsMethodParams#6](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#2)]
  
 <span data-ttu-id="1bce7-128">숨기기나 재정의와 같이 서명이 일치해야 하는 다른 상황에서는 `in`, `ref` 및 `out`이 서명의 일부가 되며 서로 일치하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1bce7-128">In other situations that require signature matching, such as hiding or overriding, `in`, `ref`, and `out` are part of the signature and don't match each other.</span></span>  
  
 <span data-ttu-id="1bce7-129">속성은 변수가 아니라</span><span class="sxs-lookup"><span data-stu-id="1bce7-129">Properties are not variables.</span></span> <span data-ttu-id="1bce7-130">메서드이며 `ref` 매개 변수로 전달할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1bce7-130">They are methods, and cannot be passed to `ref` parameters.</span></span>  
  
 <span data-ttu-id="1bce7-131">배열 전달 방법에 대한 자세한 내용은 [ref 및 out을 사용하여 배열 전달](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1bce7-131">For information about how to pass arrays, see [Passing Arrays Using ref and out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).</span></span>  
  
 <span data-ttu-id="1bce7-132">다음과 같은 종류의 메서드에는 `ref`, `in` 및 `out` 키워드를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1bce7-132">You can't use the `ref`, `in`, and `out` keywords for the following kinds of methods:</span></span>  
  
- <span data-ttu-id="1bce7-133">[async](../../../csharp/language-reference/keywords/async.md) 한정자를 사용하여 정의하는 비동기 메서드</span><span class="sxs-lookup"><span data-stu-id="1bce7-133">Async methods, which you define by using the [async](../../../csharp/language-reference/keywords/async.md) modifier.</span></span>  
- <span data-ttu-id="1bce7-134">[yield return](../../../csharp/language-reference/keywords/yield.md) 또는 `yield break` 문을 포함하는 반복기 메서드</span><span class="sxs-lookup"><span data-stu-id="1bce7-134">Iterator methods, which include a [yield return](../../../csharp/language-reference/keywords/yield.md) or `yield break` statement.</span></span>  

## <a name="passing-an-argument-by-reference-an-example"></a><span data-ttu-id="1bce7-135">참조로 인수 전달: 예제</span><span class="sxs-lookup"><span data-stu-id="1bce7-135">Passing an argument by reference: An example</span></span>

<span data-ttu-id="1bce7-136">앞의 예제에서는 값 형식을 참조로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="1bce7-136">The previous examples pass value types by reference.</span></span> <span data-ttu-id="1bce7-137">`ref` 키워드를 사용하여 참조 형식을 참조로 전달할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bce7-137">You can also use the `ref` keyword to pass reference types by reference.</span></span> <span data-ttu-id="1bce7-138">참조 형식을 참조로 전달하는 경우 호출된 메서드는 참조 매개 변수가 호출자에서 참조하는 개체를 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bce7-138">Passing a reference type by reference enables the called method to replace the object to which the reference parameter refers in the caller.</span></span> <span data-ttu-id="1bce7-139">개체의 저장 위치는 참조 매개 변수의 값으로 메서드에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bce7-139">The storage location of the object is passed to the method as the value of the reference parameter.</span></span> <span data-ttu-id="1bce7-140">매개 변수의 저장 위치에서 값을 변경하여 새 개체를 가리키도록 하면 호출자가 참조하는 저장 위치도 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bce7-140">If you change the value in the storage location of the parameter (to point to a new object), you also change the storage location to which the caller refers.</span></span> <span data-ttu-id="1bce7-141">다음 예제에서는 참조 형식 인스턴스를 `ref` 매개 변수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="1bce7-141">The following example passes an instance of a reference type as a `ref` parameter.</span></span>
  
[!code-csharp[csrefKeywordsMethodParams#6](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#3)]

<span data-ttu-id="1bce7-142">참조 형식을 참조 및 값으로 전달하는 방법에 대한 자세한 내용은 [참조-형식 매개 변수 전달](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1bce7-142">For more information about how to pass reference types by value and by reference, see [Passing Reference-Type Parameters](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md).</span></span>
  
## <a name="reference-return-values"></a><span data-ttu-id="1bce7-143">참조 반환 값</span><span class="sxs-lookup"><span data-stu-id="1bce7-143">Reference return values</span></span>

<span data-ttu-id="1bce7-144">참조 반환 값(또는 ref return)은 메서드가 호출자에게 참조로 반환하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1bce7-144">Reference return values (or ref returns) are values that a method returns by reference to the caller.</span></span> <span data-ttu-id="1bce7-145">즉, 호출자가 메서드에서 반환된 값을 수정할 수 있으며 해당 변경 내용이 메서드를 포함하는 개체의 상태에 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bce7-145">That is, the caller can modify the value returned by a method, and that change is reflected in the state of the object that contains the method.</span></span>

<span data-ttu-id="1bce7-146">참조 반환 값은 `ref` 키워드를 사용하여 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bce7-146">A reference return value is defined by using the `ref` keyword:</span></span>

- <span data-ttu-id="1bce7-147">메서드 시그니처에서.</span><span class="sxs-lookup"><span data-stu-id="1bce7-147">In the method signature.</span></span> <span data-ttu-id="1bce7-148">예를 들어 다음 메서드 시그니처는 `GetCurrentPrice` 메서드가 <xref:System.Decimal> 값을 참조로 반환함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1bce7-148">For example, the following method signature indicates that the `GetCurrentPrice` method returns a <xref:System.Decimal> value by reference.</span></span>

```csharp
public ref decimal GetCurrentValue()
```

- <span data-ttu-id="1bce7-149">메서드의 `return` 문에서 반환된 `return` 토큰과 변수 간에.</span><span class="sxs-lookup"><span data-stu-id="1bce7-149">Between the `return` token and the variable returned in a `return` statement in the method.</span></span> <span data-ttu-id="1bce7-150">예:</span><span class="sxs-lookup"><span data-stu-id="1bce7-150">For example:</span></span>

```csharp
return ref DecimalArray[0];
```

<span data-ttu-id="1bce7-151">호출자가 개체 상태를 수정하려면 참조 반환 값을 [참조 로컬](#ref-locals)로 명시적으로 정의된 변수에 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1bce7-151">In order for the caller to modify the object's state, the reference return value must be stored to a variable that is explicitly defined as a [ref local](#ref-locals).</span></span>

<span data-ttu-id="1bce7-152">예를 들어 [참조 반환 및 참조 로컬 예제](#a-ref-returns-and-ref-locals-example)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1bce7-152">For an example, see [A ref returns and ref locals example](#a-ref-returns-and-ref-locals-example)</span></span>

## <a name="ref-locals"></a><span data-ttu-id="1bce7-153">참조 로컬</span><span class="sxs-lookup"><span data-stu-id="1bce7-153">Ref locals</span></span>

<span data-ttu-id="1bce7-154">참조 지역 변수는 `return ref`을 사용하여 반환된 값을 참조하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bce7-154">A ref local variable is used to refer to values returned using `return ref`.</span></span>  <span data-ttu-id="1bce7-155">참조 지역 변수를 초기화하고 참조 반환 값에 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1bce7-155">A ref local variable must be initialized and assigned to a ref return value.</span></span> <span data-ttu-id="1bce7-156">참조 로컬 값의 수정 내용은 메서드가 값을 참조로 반환하는 개체 상태에 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bce7-156">Any modifications to the value of the ref local are reflected in the state of the object whose method returned the value by reference.</span></span>

<span data-ttu-id="1bce7-157">변수 선언 앞, 값을 참조로 반환하는 메서드 호출 직전에 `ref` 키워드를 사용하여 참조 로컬을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1bce7-157">You define a ref local by using the `ref` keyword before the variable declaration, as well as immediately before the call to the method that returns the value by reference.</span></span>

<span data-ttu-id="1bce7-158">예를 들어 다음 문은 `GetEstimatedValue` 메서드에서 반환되는 참조 로컬 값을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1bce7-158">For example, the following statement defines a ref local value that is returned by a method named `GetEstimatedValue`:</span></span>

```csharp
ref decimal estValue = ref Building.GetEstimatedValue();
```

<span data-ttu-id="1bce7-159">동일한 방법으로 참조로 값에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bce7-159">You can access a value by reference in the same way.</span></span> <span data-ttu-id="1bce7-160">경우에 따라 참조로 값에 액세스하면 비용이 많이 들 수 있는 복사 작업을 피함으로써 성능이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bce7-160">In some cases, accessing a value by reference increases performance by avoiding a potentially expensive copy operation.</span></span> <span data-ttu-id="1bce7-161">예를 들어, 다음 명령문은 값을 참조하는 데 사용되는 참조 로컬 값을 정의하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="1bce7-161">For example, the following statement shows how one can define a ref local value that is used to reference a value.</span></span>

```csharp
ref VeryLargeStruct reflocal = ref veryLargeStruct;
```

<span data-ttu-id="1bce7-162">두 예에서 `ref` 키워드는 두 위치에 모두 사용해야 합니다. 그렇지 않으면 컴파일러 오류 CS8172, "값을 사용하여 참조 형식 변수를 초기화할 수 없습니다."가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bce7-162">Note that in both examples the `ref` keyword must be used in both places, or the compiler generates error CS8172, "Cannot initialize a by-reference variable with a value."</span></span>

## <a name="a-ref-returns-and-ref-locals-example"></a><span data-ttu-id="1bce7-163">참조 반환 및 참조 로컬 예제</span><span class="sxs-lookup"><span data-stu-id="1bce7-163">A ref returns and ref locals example</span></span>

<span data-ttu-id="1bce7-164">다음 예제에서는 두 개의 <xref:System.String> 필드 `Title` 및 `Author`가 있는 `Book` 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1bce7-164">The following example defines a `Book` class that has two <xref:System.String> fields, `Title` and `Author`.</span></span> <span data-ttu-id="1bce7-165">또한 `Book` 개체의 private 배열을 포함하는 `BookCollection` 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1bce7-165">It also defines a `BookCollection` class that includes a private array of `Book` objects.</span></span> <span data-ttu-id="1bce7-166">개별 책 개체는 해당 `GetBookByTitle` 메서드를 호출하여 참조로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bce7-166">Individual book objects are returned by reference by calling its `GetBookByTitle` method.</span></span>

[!code-csharp[csrefKeywordsMethodParams#6](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#4)]

<span data-ttu-id="1bce7-167">호출자가 `GetBookByTitle` 메서드에서 참조 로컬로 반환된 값을 저장하는 경우 호출자가 반환 값을 변경하면 다음 예제와 같이 `BookCollection` 개체에 변경 내용이 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bce7-167">When the caller stores the value returned by the `GetBookByTitle` method as a ref local, changes that the caller makes to the return value are reflected in the `BookCollection` object, as the following example shows.</span></span>

[!code-csharp[csrefKeywordsMethodParams#6](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#5)]

## <a name="ref-struct-declarations"></a><span data-ttu-id="1bce7-168">참조 구조체 선언</span><span class="sxs-lookup"><span data-stu-id="1bce7-168">Ref struct declarations</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="1bce7-169">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="1bce7-169">C# Language Specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1bce7-170">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1bce7-170">See also</span></span>

 [<span data-ttu-id="1bce7-171">값 형식과 참조 의미 체계</span><span class="sxs-lookup"><span data-stu-id="1bce7-171">Reference semantics with value types</span></span>](../../reference-semantics-with-value-types.md)  
 [<span data-ttu-id="1bce7-172">매개 변수 전달</span><span class="sxs-lookup"><span data-stu-id="1bce7-172">Passing Parameters</span></span>](../../programming-guide/classes-and-structs/passing-parameters.md)  
 [<span data-ttu-id="1bce7-173">메서드 매개 변수</span><span class="sxs-lookup"><span data-stu-id="1bce7-173">Method Parameters</span></span>](method-parameters.md)  
 [<span data-ttu-id="1bce7-174">C# 참조</span><span class="sxs-lookup"><span data-stu-id="1bce7-174">C# Reference</span></span>](../index.md)  
 [<span data-ttu-id="1bce7-175">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="1bce7-175">C# Programming Guide</span></span>](../../programming-guide/index.md)  
 [<span data-ttu-id="1bce7-176">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="1bce7-176">C# Keywords</span></span>](index.md)
