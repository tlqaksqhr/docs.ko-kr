---
title: "ref(C# 참조)"
ms.date: 2017-05-30
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ref_CSharpKeyword
- ref
dev_langs:
- CSharp
helpviewer_keywords:
- parameters [C#], ref
- ref keyword [C#]
ms.assetid: b8a5e59c-907d-4065-b41d-95bf4273c0bd
caps.latest.revision: 32
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 003125ca6218d42a919d8bb592b5454a7cb387c7
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="ref-c-reference"></a><span data-ttu-id="74dfa-102">ref(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="74dfa-102">ref (C# Reference)</span></span>

<span data-ttu-id="74dfa-103">`ref` 키워드는 참조로 전달되는 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="74dfa-103">The `ref` keyword indicates a value that is passed by reference.</span></span> <span data-ttu-id="74dfa-104">다음 세 가지 컨텍스트에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="74dfa-104">It is used in three different contexts:</span></span> 

- <span data-ttu-id="74dfa-105">메서드 시그니처 및 메서드 호출에서 인수를 메서드에 참조로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="74dfa-105">In a method signature and in a method call, to pass an argument to a method by reference.</span></span> <span data-ttu-id="74dfa-106">자세한 내용은 [참조로 인수 전달](#passing-an-argument-by-reference)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="74dfa-106">See [Passing an argument by reference](#passing-an-argument-by-reference) for more information.</span></span>

- <span data-ttu-id="74dfa-107">메서드 시그니처에서 값을 호출자에게 참조로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="74dfa-107">In a method signature, to return a value to the caller by reference.</span></span> <span data-ttu-id="74dfa-108">자세한 내용은 [참조 반환 값](#reference-return-values)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="74dfa-108">See [Reference return values](#reference-return-values) for more information.</span></span>

- <span data-ttu-id="74dfa-109">멤버 본문에서 참조 반환 값이 호출자가 수정하려는 참조로 로컬에 저장됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="74dfa-109">In a member body, to indicate that a reference return value is stored locally as a reference that the caller intends to modify.</span></span> <span data-ttu-id="74dfa-110">자세한 내용은 [참조 로컬](#ref-locals)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="74dfa-110">See [Ref locals](#ref-locals) for more information.</span></span>

## <a name="passing-an-argument-by-reference"></a><span data-ttu-id="74dfa-111">참조로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="74dfa-111">Passing an argument by reference</span></span>

<span data-ttu-id="74dfa-112">메서드의 매개 변수 목록에 사용되는 경우 `ref` 키워드는 인수가 값이 아니라 참조로 전달됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="74dfa-112">When used in a method's parameter list, the `ref` keyword indicates that an argument is passed by reference, not by value.</span></span> <span data-ttu-id="74dfa-113">인수를 참조로 전달하는 경우 호출된 메서드의 인수 변경 내용이 호출 메서드에 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="74dfa-113">The effect of passing by reference is that any change to the argument in the called method is reflected in the calling method.</span></span> <span data-ttu-id="74dfa-114">예를 들어 호출자가 지역 변수 식 또는 배열 요소 액세스 식을 전달하는 경우 호출된 메서드에서 ref 매개 변수가 참조하는 개체를 바꾸면 메서드 반환 시 호출자의 지역 변수 또는 배열 요소가 새 개체를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="74dfa-114">For example, if the caller passes a local variable expression or an array element access expression, and the called method replaces the object to which the ref parameter refers, then the caller’s local variable or the array element now refers to the new object when the method returns.</span></span>

> [!NOTE]
>  <span data-ttu-id="74dfa-115">참조로 전달의 개념과 참조 형식의 개념을 혼동해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="74dfa-115">Do not confuse the concept of passing by reference with the concept of reference types.</span></span> <span data-ttu-id="74dfa-116">이 두 개념은 서로 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="74dfa-116">The two concepts are not the same.</span></span> <span data-ttu-id="74dfa-117">메서드 매개 변수는 값 형식이든 참조 형식이든 관계없이 `ref`를 통해 수정할 수 있으며,</span><span class="sxs-lookup"><span data-stu-id="74dfa-117">A method parameter can be modified by `ref` regardless of whether it is a value type or a reference type.</span></span> <span data-ttu-id="74dfa-118">참조로 전달되는 경우 값 형식은 boxing되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="74dfa-118">There is no boxing of a value type when it is passed by reference.</span></span>  

<span data-ttu-id="74dfa-119">`ref` 매개 변수를 사용하려면 다음 예제에 나와 있는 것처럼 메서드 정의와 호출 메서드가 모두 `ref` 키워드를 명시적으로 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74dfa-119">To use a `ref` parameter, both the method definition and the calling method must explicitly use the `ref` keyword, as shown in the following example.</span></span>  

<span data-ttu-id="74dfa-120">[!code-cs[csrefKeywordsMethodParams#6](../../../../samples/snippets/csharp/language-reference/keywords/ref/ref-1.cs)]</span><span class="sxs-lookup"><span data-stu-id="74dfa-120">[!code-cs[csrefKeywordsMethodParams#6](../../../../samples/snippets/csharp/language-reference/keywords/ref/ref-1.cs)]</span></span>

<span data-ttu-id="74dfa-121">`ref` 매개 변수로 전달하는 인수는 전달 전에 초기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74dfa-121">An argument that is passed to a `ref` parameter must be initialized before it is passed.</span></span> <span data-ttu-id="74dfa-122">이러한 방식은 인수를 전달하기 전에 명시적으로 초기화할 필요가 없는 [out](out.md) 매개 변수와는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="74dfa-122">This differs from [out](out.md) parameters, whose arguments do not have to be explicitly initialized before they are passed.</span></span>

<span data-ttu-id="74dfa-123">클래스의 멤버는 `ref` 및 `out`만 다른 서명을 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="74dfa-123">Members of a class can't have signatures that differ only by `ref` and `out`.</span></span> <span data-ttu-id="74dfa-124">특정 형식의 두 멤버가 하나는 `ref` 매개 변수를 포함하고 다른 하나는 `out` 매개 변수를 포함한다는 것 외에는 차이가 없으면 컴파일러 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="74dfa-124">A compiler error occurs if the only difference between two members of a type is that one of them has a `ref` parameter and the other has an `out` parameter.</span></span> <span data-ttu-id="74dfa-125">예를 들어 다음 코드는 컴파일되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="74dfa-125">The following code, for example, doesn't compile.</span></span>  
  
 <span data-ttu-id="74dfa-126">[!code-cs[csrefKeywordsMethodParams#2](../../../../samples/snippets/csharp/language-reference/keywords/ref/ref-2.cs)]</span><span class="sxs-lookup"><span data-stu-id="74dfa-126">[!code-cs[csrefKeywordsMethodParams#2](../../../../samples/snippets/csharp/language-reference/keywords/ref/ref-2.cs)]</span></span>
  
 <span data-ttu-id="74dfa-127">그러나 다음 예제에 나와 있는 것처럼 메서드 하나에는 `ref` 또는 `out` 매개 변수가 포함되어 있고 다른 하나에는 값 매개 변수가 포함되어 있으면 메서드를 오버로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74dfa-127">However, methods can be overloaded when one method has a `ref` or `out` parameter and the other has a value parameter, as shown in the following example.</span></span>
  
 <span data-ttu-id="74dfa-128">[!code-cs[ref-and-overloads](../../../../samples/snippets/csharp/language-reference/keywords/ref/ref-3.cs)]</span><span class="sxs-lookup"><span data-stu-id="74dfa-128">[!code-cs[ref-and-overloads](../../../../samples/snippets/csharp/language-reference/keywords/ref/ref-3.cs)]</span></span>
  
 <span data-ttu-id="74dfa-129">숨기기나 재정의와 같이 서명이 일치해야 하는 다른 상황에서는 `ref` 및 `out`이 서명의 일부가 되며 서로 일치하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="74dfa-129">In other situations that require signature matching, such as hiding or overriding, `ref` and `out` are part of the signature and don't match each other.</span></span>  
  
 <span data-ttu-id="74dfa-130">속성은 변수가 아니라</span><span class="sxs-lookup"><span data-stu-id="74dfa-130">Properties are not variables.</span></span> <span data-ttu-id="74dfa-131">메서드이며 `ref` 매개 변수로 전달할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="74dfa-131">They are methods, and cannot be passed to `ref` parameters.</span></span>  
  
 <span data-ttu-id="74dfa-132">배열 전달 방법에 대한 자세한 내용은 [ref 및 out을 사용하여 배열 전달](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="74dfa-132">For information about how to pass arrays, see [Passing Arrays Using ref and out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).</span></span>  
  
 <span data-ttu-id="74dfa-133">다음과 같은 종류의 메서드에는 `ref` 및 `out` 키워드를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="74dfa-133">You can't use the `ref` and `out` keywords for the following kinds of methods:</span></span>  
  
-   <span data-ttu-id="74dfa-134">[async](../../../csharp/language-reference/keywords/async.md) 한정자를 사용하여 정의하는 비동기 메서드</span><span class="sxs-lookup"><span data-stu-id="74dfa-134">Async methods, which you define by using the [async](../../../csharp/language-reference/keywords/async.md) modifier.</span></span>  
  
-   <span data-ttu-id="74dfa-135">[yield return](../../../csharp/language-reference/keywords/yield.md) 또는 `yield break` 문을 포함하는 반복기 메서드</span><span class="sxs-lookup"><span data-stu-id="74dfa-135">Iterator methods, which include a [yield return](../../../csharp/language-reference/keywords/yield.md) or `yield break` statement.</span></span>  
  
## <a name="passing-an-argument-by-reference-an-example"></a><span data-ttu-id="74dfa-136">참조로 인수 전달: 예제</span><span class="sxs-lookup"><span data-stu-id="74dfa-136">Passing an argument by reference: An example</span></span>

<span data-ttu-id="74dfa-137">앞의 예제에서는 값 형식을 참조로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="74dfa-137">The previous examples pass value types by reference.</span></span> <span data-ttu-id="74dfa-138">`ref` 키워드를 사용하여 참조 형식을 참조로 전달할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74dfa-138">You can also use the `ref` keyword to pass reference types by reference.</span></span> <span data-ttu-id="74dfa-139">참조 형식을 참조로 전달하는 경우 호출된 메서드는 참조 매개 변수가 호출자에서 참조하는 개체를 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74dfa-139">Passing a reference type by reference enables the called method to replace the object to which the reference parameter refers in the caller.</span></span> <span data-ttu-id="74dfa-140">개체의 저장 위치는 참조 매개 변수의 값으로 메서드에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="74dfa-140">The storage location of the object is passed to the method as the value of the reference parameter.</span></span> <span data-ttu-id="74dfa-141">매개 변수의 저장 위치에서 값을 변경하여 새 개체를 가리키도록 하면 호출자가 참조하는 저장 위치도 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="74dfa-141">If you change the value in the storage location of the parameter (to point to a new object), you also change the storage location to which the caller refers.</span></span> <span data-ttu-id="74dfa-142">다음 예제에서는 참조 형식 인스턴스를 `ref` 매개 변수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="74dfa-142">The following example passes an instance of a reference type as a `ref` parameter.</span></span>   
  
 <span data-ttu-id="74dfa-143">[!code-cs[ReferencesByRef](../../../../samples/snippets/csharp/language-reference/keywords/ref/ref-4.cs)]</span><span class="sxs-lookup"><span data-stu-id="74dfa-143">[!code-cs[ReferencesByRef](../../../../samples/snippets/csharp/language-reference/keywords/ref/ref-4.cs)]</span></span>  

<span data-ttu-id="74dfa-144">참조 형식을 참조 및 값으로 전달하는 방법에 대한 자세한 내용은 [참조-형식 매개 변수 전달](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="74dfa-144">For more information about how to pass reference types by value and by reference, see [Passing Reference-Type Parameters](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md).</span></span>
  
## <a name="reference-return-values"></a><span data-ttu-id="74dfa-145">참조 반환 값</span><span class="sxs-lookup"><span data-stu-id="74dfa-145">Reference return values</span></span>

<span data-ttu-id="74dfa-146">참조 반환 값(또는 ref return)은 메서드가 호출자에게 참조로 반환하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="74dfa-146">Reference return values (or ref returns) are values that a method returns by reference to the caller.</span></span> <span data-ttu-id="74dfa-147">즉, 호출자가 메서드에서 반환된 값을 수정할 수 있으며 해당 변경 내용이 메서드를 포함하는 개체의 상태에 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="74dfa-147">That is, the caller can modify the value returned by a method, and that change is reflected in the state of the object that contains the method.</span></span> 

<span data-ttu-id="74dfa-148">참조 반환 값은 `ref` 키워드를 사용하여 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="74dfa-148">A reference return value is defined by using the `ref` keyword:</span></span>

- <span data-ttu-id="74dfa-149">메서드 시그니처에서.</span><span class="sxs-lookup"><span data-stu-id="74dfa-149">In the method signature.</span></span> <span data-ttu-id="74dfa-150">예를 들어 다음 메서드 시그니처는 `GetCurrentPrice` 메서드가 <xref:System.Decimal> 값을 참조로 반환함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="74dfa-150">For example, the following method signature inidicates that the `GetCurrentPrice` method returns a <xref:System.Decimal> value by reference.</span></span>

   ```csharp
   public ref decimal GetCurrentValue()
   ``` 
- <span data-ttu-id="74dfa-151">메서드의 각 `return` 문 앞에서.</span><span class="sxs-lookup"><span data-stu-id="74dfa-151">Before each `return` statement in the method.</span></span> <span data-ttu-id="74dfa-152">예:</span><span class="sxs-lookup"><span data-stu-id="74dfa-152">For example:</span></span>
 
   ```csharp
   ref return Decimal.Zero;
   ``` 

<span data-ttu-id="74dfa-153">호출자가 개체 상태를 수정하려면 참조 반환 값을 [참조 로컬](#ref-locals)로 명시적으로 정의된 변수에 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74dfa-153">In order for the caller to modify the an object's state, the reference return value must be stored to a variable that is explicitly defined as a [ref local](#ref-locals).</span></span> 

<span data-ttu-id="74dfa-154">예를 들어 [참조 반환 및 참조 로컬 예제](#a-ref-returns-and-ref-locals-example)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="74dfa-154">For an example, see [A ref returns and ref locals example](#a-ref-returns-and-ref-locals-example)</span></span>

## <a name="ref-locals"></a><span data-ttu-id="74dfa-155">참조 로컬</span><span class="sxs-lookup"><span data-stu-id="74dfa-155">Ref locals</span></span>

<span data-ttu-id="74dfa-156">참조 지역 변수는 `ref return`을 사용하여 반환된 값을 참조하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="74dfa-156">A ref local variable is used to refer to values returned using `ref return`.</span></span>  <span data-ttu-id="74dfa-157">참조 지역 변수를 초기화하고 참조 반환 값에 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74dfa-157">A ref local variable must be initialized and assigned to a ref return value.</span></span> <span data-ttu-id="74dfa-158">참조 로컬 값의 수정 내용은 메서드가 값을 참조로 반환하는 개체 상태에 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="74dfa-158">Any modifications to the value of the ref local are reflected in the state of the object whose method returned the value by reference.</span></span>

<span data-ttu-id="74dfa-159">변수 선언 앞, 값을 참조로 반환하는 메서드 호출 직전에 `ref` 키워드를 사용하여 참조 로컬을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="74dfa-159">You define a ref local by using the `ref` keyword before the variable declaration, as well as immediately before the call to the method that returns the value by reference.</span></span> 

<span data-ttu-id="74dfa-160">예를 들어 다음 문은 `GetEstimatedValue` 메서드에서 반환되는 참조 로컬 값을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="74dfa-160">For example, the following statement defines a ref local value that is returned by a method named `GetEstimatedValue`:</span></span>

```csharp
ref decimal estValue = ref Building.GetEstimatedValue();
```

<span data-ttu-id="74dfa-161">`ref` 키워드를 두 위치에 모두 사용해야 합니다. 그러지 않으면 컴파일러 오류 CS8172, “값을 사용하여 참조 형식 변수를 초기화할 수 없습니다.”가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="74dfa-161">Note that the `ref` keyword must be used in both places, or the compiler generates error CS8172, "Cannot initialize a by-reference variable with a value."</span></span> 
 
## <a name="a-ref-returns-and-ref-locals-example"></a><span data-ttu-id="74dfa-162">참조 반환 및 참조 로컬 예제</span><span class="sxs-lookup"><span data-stu-id="74dfa-162">A ref returns and ref locals example</span></span>

<span data-ttu-id="74dfa-163">다음 예제에서는 두 개의 <xref:System.String> 필드 `Title` 및 `Author`가 있는 `Book` 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="74dfa-163">The following example defines a `Book` class that has two <xref:System.String> fields, `Title` and `Author`.</span></span> <span data-ttu-id="74dfa-164">또한 `Book` 개체의 private 배열을 포함하는 `BookCollection` 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="74dfa-164">It also defines a `BookCollection` class that includes a private array of `Book` objects.</span></span> <span data-ttu-id="74dfa-165">개별 책 개체는 해당 `GetBookByTitle` 메서드를 호출하여 참조로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="74dfa-165">Individual book objects are returned by reference by calling its `GetBookByTitle` method.</span></span>

<span data-ttu-id="74dfa-166">[!code-cs[csrefreturns](../../../../samples/snippets/csharp/language-reference/keywords/ref/ref-5.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="74dfa-166">[!code-cs[csrefreturns](../../../../samples/snippets/csharp/language-reference/keywords/ref/ref-5.cs#1)]</span></span>  

<span data-ttu-id="74dfa-167">호출자가 `GetBookByTitle` 메서드에서 참조 로컬로 반환된 값을 저장하는 경우 호출자가 반환 값을 변경하면 다음 예제와 같이 `BookCollection` 개체에 변경 내용이 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="74dfa-167">When the caller stores the value returned by the `GetBookByTitle` method as a ref local, changes that the caller makes to the return value are reflected in the `BookCollection` object, as the following example shows.</span></span>

<span data-ttu-id="74dfa-168">[!code-cs[csrefreturns](../../../../samples/snippets/csharp/language-reference/keywords/ref/ref-5.cs#2)]</span><span class="sxs-lookup"><span data-stu-id="74dfa-168">[!code-cs[csrefreturns](../../../../samples/snippets/csharp/language-reference/keywords/ref/ref-5.cs#2)]</span></span>  

## <a name="c-language-specification"></a><span data-ttu-id="74dfa-169">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="74dfa-169">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="74dfa-170">참고 항목</span><span class="sxs-lookup"><span data-stu-id="74dfa-170">See Also</span></span>  
 <span data-ttu-id="74dfa-171">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="74dfa-171">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="74dfa-172">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="74dfa-172">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="74dfa-173">[매개 변수 전달](../../../csharp/programming-guide/classes-and-structs/passing-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="74dfa-173">[Passing Parameters](../../../csharp/programming-guide/classes-and-structs/passing-parameters.md) </span></span>  
 <span data-ttu-id="74dfa-174">[메서드 매개 변수](../../../csharp/language-reference/keywords/method-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="74dfa-174">[Method Parameters](../../../csharp/language-reference/keywords/method-parameters.md) </span></span>  
 [<span data-ttu-id="74dfa-175">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="74dfa-175">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)

