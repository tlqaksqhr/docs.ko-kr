---
title: "out 매개 변수 한정자(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- parameters [C#], out
- out parameters [C#]
ms.assetid: 3fce0dc5-03f4-4faa-bd61-36c41bc6baf1
caps.latest.revision: 9
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
ms.sourcegitcommit: 59e445ac27f07c85d9e98c5f595cf5f935f75443
ms.openlocfilehash: 9a0a488c6f444608a335cd990847774fb6fe9e3f
ms.contentlocale: ko-kr
ms.lasthandoff: 08/31/2017

---
# <a name="out-parameter-modifier-c-reference"></a><span data-ttu-id="2546e-102">out 매개 변수 한정자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="2546e-102">out parameter modifier (C# Reference)</span></span>
<span data-ttu-id="2546e-103">`out` 키워드를 사용하면 참조를 통해 인수를 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2546e-103">The `out` keyword causes arguments to be passed by reference.</span></span> <span data-ttu-id="2546e-104">이러한 방식은 [ref](../../../csharp/language-reference/keywords/ref.md) 키워드와 비슷합니다. 단, `ref`의 경우에는 변수를 전달하기 전에 초기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2546e-104">It is like the [ref](../../../csharp/language-reference/keywords/ref.md) keyword, except that `ref` requires that the variable be initialized before it is passed.</span></span> <span data-ttu-id="2546e-105">`out` 매개 변수를 사용하려면 메서드 정의와 호출 메서드가 모두 명시적으로 `out` 키워드를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2546e-105">To use an `out` parameter, both the method definition and the calling method must explicitly use the `out` keyword.</span></span> <span data-ttu-id="2546e-106">예:</span><span class="sxs-lookup"><span data-stu-id="2546e-106">For example:</span></span>  
  
 <span data-ttu-id="2546e-107">[!code-cs[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/out/out-1.cs)]</span><span class="sxs-lookup"><span data-stu-id="2546e-107">[!code-cs[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/out/out-1.cs)]</span></span>  

> [!NOTE] 
> <span data-ttu-id="2546e-108">`out` 키워드를 제네릭 형식 매개 변수와 함께 사용하여 형식 매개 변수를 공변(covariant)으로 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2546e-108">The `out` keyword can also be used with a generic type parameter to specify that the type parameter is covariant.</span></span> <span data-ttu-id="2546e-109">이 컨텍스트에서 `out` 키워드를 사용하는 방법에 대한 자세한 내용은 [out(제네릭 한정자)](../../../csharp/language-reference/keywords/out-generic-modifier.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2546e-109">For more information on the use of the `out` keyword in this context, see [out (Generic Modifier)](../../../csharp/language-reference/keywords/out-generic-modifier.md).</span></span>
  
 <span data-ttu-id="2546e-110">`out` 인수로 전달되는 변수는 메서드 호출에서 전달되기 전에 초기화할 필요가 없지만</span><span class="sxs-lookup"><span data-stu-id="2546e-110">Variables passed as `out` arguments do not have to be initialized before being passed in a method call.</span></span> <span data-ttu-id="2546e-111">호출된 메서드는 메서드가 반환되기 전에 값을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2546e-111">However, the called method is required to assign a value before the method returns.</span></span>  
  
 <span data-ttu-id="2546e-112">`ref` 및 `out` 키워드는 서로 다른 런타임 동작을 수행하지만 컴파일 시간에 메서드 시그니처의 일부로 간주되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2546e-112">Although the `ref` and `out` keywords cause different run-time behavior, they are not considered part of the method signature at compile time.</span></span> <span data-ttu-id="2546e-113">따라서 메서드 하나는 `ref` 인수를 사용하고 다른 하나는 `out` 인수를 사용한다는 것 외에는 차이점이 없으면 메서드를 오버로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2546e-113">Therefore, methods cannot be overloaded if the only difference is that one method takes a `ref` argument and the other takes an `out` argument.</span></span> <span data-ttu-id="2546e-114">예를 들어 다음 코드는 컴파일되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2546e-114">The following code, for example, will not compile:</span></span>  
  
```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded 
    // methods that differ only on ref and out".
    public void SampleMethod(out int i) { }
    public void SampleMethod(ref int i) { }
}
```
  
<span data-ttu-id="2546e-115">그러나 다음과 같이 메서드 하나는 `ref` 또는 `out` 인수를 사용하고 다른 하나는 인수를 사용하지 않는 경우에는 오버로드를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2546e-115">Overloading is legal, however, if one method takes a `ref` or `out` argument and the other uses neither, like this:</span></span>  
  
 <span data-ttu-id="2546e-116">[!code-cs[csrefKeywordsMethodParams#3](../../../../samples/snippets/csharp/language-reference/keywords/out/out-3.cs)]</span><span class="sxs-lookup"><span data-stu-id="2546e-116">[!code-cs[csrefKeywordsMethodParams#3](../../../../samples/snippets/csharp/language-reference/keywords/out/out-3.cs)]</span></span>  
  
 <span data-ttu-id="2546e-117">속성은 변수가 아니므로 `out` 매개 변수로 전달할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2546e-117">Properties are not variables and therefore cannot be passed as `out` parameters.</span></span>  
  
 <span data-ttu-id="2546e-118">배열 전달에 대한 자세한 내용은 [ref 및 out을 사용하여 배열 전달](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2546e-118">For information about passing arrays, see [Passing Arrays Using ref and out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).</span></span>  
  
 <span data-ttu-id="2546e-119">다음과 같은 종류의 메서드에는 `ref` 및 `out` 키워드를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2546e-119">You can't use the `ref` and `out` keywords for the following kinds of methods:</span></span>  
  
-   <span data-ttu-id="2546e-120">[async](../../../csharp/language-reference/keywords/async.md) 한정자를 사용하여 정의하는 비동기 메서드</span><span class="sxs-lookup"><span data-stu-id="2546e-120">Async methods, which you define by using the [async](../../../csharp/language-reference/keywords/async.md) modifier.</span></span>  
  
-   <span data-ttu-id="2546e-121">[yield return](../../../csharp/language-reference/keywords/yield.md) 또는 `yield break` 문을 포함하는 반복기 메서드</span><span class="sxs-lookup"><span data-stu-id="2546e-121">Iterator methods, which include a [yield return](../../../csharp/language-reference/keywords/yield.md) or `yield break` statement.</span></span>  

## <a name="declaring-out-arguments"></a><span data-ttu-id="2546e-122">`out` 인수 선언</span><span class="sxs-lookup"><span data-stu-id="2546e-122">Declaring `out` arguments</span></span>   

 <span data-ttu-id="2546e-123">메서드가 여러 값을 반환하도록 하려는 경우 `out` 인수를 사용하여 메서드를 선언하면 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="2546e-123">Declaring a method with `out` arguments is useful when you want a method to return multiple values.</span></span> <span data-ttu-id="2546e-124">다음 예제에서는 `out`을 사용하여 단일 메서드 호출로 3개 변수를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="2546e-124">The following example uses `out` to return three variables with a single method call.</span></span> <span data-ttu-id="2546e-125">세 번째 인수는 null에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="2546e-125">Note that the third argument is assigned to null.</span></span> <span data-ttu-id="2546e-126">따라서 메서드가 값을 선택적으로 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2546e-126">This enables methods to return values optionally.</span></span>  
  
 <span data-ttu-id="2546e-127">[!code-cs[csrefKeywordsMethodParams#4](../../../../samples/snippets/csharp/language-reference/keywords/out/out-4.cs)]</span><span class="sxs-lookup"><span data-stu-id="2546e-127">[!code-cs[csrefKeywordsMethodParams#4](../../../../samples/snippets/csharp/language-reference/keywords/out/out-4.cs)]</span></span>  

 <span data-ttu-id="2546e-128">[Try 패턴](/visualstudio/code-quality/ca1021-avoid-out-parameters#try-pattern-methods.md)은 `bool`을 반환하여 작업의 성공 및 실패를 나타내고 작업에서 생성된 값을 `out` 인수에 반환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2546e-128">The [Try pattern](/visualstudio/code-quality/ca1021-avoid-out-parameters#try-pattern-methods.md) involves returning a `bool` to indicate whether an operation succeeded and failed, and returning the value produced by the operation in an `out` argument.</span></span> <span data-ttu-id="2546e-129">[DateTime.TryParse](xref:System.DateTime.TryParse(System.String,System.DateTime@)) 메서드와 같은 다양한 구문 분석 메서드에서 이 패턴을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2546e-129">A number of parsing methods, such as the [DateTime.TryParse](xref:System.DateTime.TryParse(System.String,System.DateTime@)) method, use this pattern.</span></span>
   
## <a name="calling-a-method-with-an-out-argument"></a><span data-ttu-id="2546e-130">`out` 인수를 사용하여 메서드 호출</span><span class="sxs-lookup"><span data-stu-id="2546e-130">Calling a method with an `out` argument</span></span>

<span data-ttu-id="2546e-131">C# 6 및 이전 버전에서는 `out` 인수로 전달하기 전에 별도 문에서 변수를 선언해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2546e-131">In C# 6 and earlier, you must declare a variable in a separate statement before you pass it as an `out` argument.</span></span> <span data-ttu-id="2546e-132">다음 예제에서는 [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) 메서드에 전달되기 전에 `number`라는 변수를 선언합니다. 이 메서드는 문자열을 숫자로 변환하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="2546e-132">The following example declares a variable named `number` before it is passed to the [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) method, which attempts to convert a string to a number.</span></span>

 <span data-ttu-id="2546e-133">[!code-cs[csrefKeywordsMethodParams#5](../../../../samples/snippets/csharp/language-reference/keywords/out/out-5.cs)]</span><span class="sxs-lookup"><span data-stu-id="2546e-133">[!code-cs[csrefKeywordsMethodParams#5](../../../../samples/snippets/csharp/language-reference/keywords/out/out-5.cs)]</span></span>  

<span data-ttu-id="2546e-134">C# 7부터 별도 변수 선언이 아니라 메서드 호출의 인수 목록에서 `out` 변수를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2546e-134">Starting with C# 7, you can declare the `out` variable in the argument list of the method call, rather than in a separate variable declaration.</span></span> <span data-ttu-id="2546e-135">이렇게 하면 보다 간결하고 읽기 쉬운 코드가 생성되며 메서드 호출 전에 실수로 변수에 값이 할당되는 경우를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2546e-135">This produces more compact, readable code, and also prevents you from inadvertently assigning a value to the variable before the method call.</span></span> <span data-ttu-id="2546e-136">다음 예제는 [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) 메서드 호출에서 `number` 변수를 정의한다는 점을 제외하고 이전 예제와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="2546e-136">The following example is like the previous example, except that it defines the `number` variable in the call to the [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) method.</span></span>

 <span data-ttu-id="2546e-137">[!code-cs[csrefKeywordsMethodParams#6](../../../../samples/snippets/csharp/language-reference/keywords/out/out-6.cs)]</span><span class="sxs-lookup"><span data-stu-id="2546e-137">[!code-cs[csrefKeywordsMethodParams#6](../../../../samples/snippets/csharp/language-reference/keywords/out/out-6.cs)]</span></span>  
   
<span data-ttu-id="2546e-138">앞의 예제에서 `number` 변수는 `int`로 강력하게 형식화됩니다.</span><span class="sxs-lookup"><span data-stu-id="2546e-138">In the previous example, the `number` variable is strongly typed as an `int`.</span></span> <span data-ttu-id="2546e-139">다음 예제와 같이 암시적 형식 지역 변수를 선언할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2546e-139">You can also declare an implicitly typed local variable, as the following example does.</span></span>

 <span data-ttu-id="2546e-140">[!code-cs[csrefKeywordsMethodParams#7](../../../../samples/snippets/csharp/language-reference/keywords/out/out-7.cs)]</span><span class="sxs-lookup"><span data-stu-id="2546e-140">[!code-cs[csrefKeywordsMethodParams#7](../../../../samples/snippets/csharp/language-reference/keywords/out/out-7.cs)]</span></span>  
   
## <a name="c-language-specification"></a><span data-ttu-id="2546e-141">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="2546e-141">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2546e-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2546e-142">See Also</span></span>  
 <span data-ttu-id="2546e-143">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="2546e-143">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="2546e-144">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="2546e-144">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="2546e-145">[C# 키워드](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="2546e-145">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 [<span data-ttu-id="2546e-146">메서드 매개 변수</span><span class="sxs-lookup"><span data-stu-id="2546e-146">Method Parameters</span></span>](../../../csharp/language-reference/keywords/method-parameters.md)

