---
title: "제네릭 메서드(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- generics [C#], methods
ms.assetid: 673eeea2-4b48-4faa-9c4e-2e89449221b9
caps.latest.revision: 27
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
ms.openlocfilehash: 14461773303bafc098f79c3686b1f76827f11005
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="generic-methods-c-programming-guide"></a><span data-ttu-id="e85f3-102">제네릭 메서드(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="e85f3-102">Generic Methods (C# Programming Guide)</span></span>
<span data-ttu-id="e85f3-103">제네릭 메서드는 다음과 같은 형식 매개 변수를 사용하여 선언된 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-103">A generic method is a method that is declared with type parameters, as follows:</span></span>  
  
 <span data-ttu-id="e85f3-104">[!code-cs[csProgGuideGenerics#22](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="e85f3-104">[!code-cs[csProgGuideGenerics#22](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_1.cs)]</span></span>  
  
 <span data-ttu-id="e85f3-105">다음 코드 예제는 형식 인수에 `int`를 사용하여 메서드를 호출하는 한 가지 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-105">The following code example shows one way to call the method by using `int` for the type argument:</span></span>  
  
 <span data-ttu-id="e85f3-106">[!code-cs[csProgGuideGenerics#23](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="e85f3-106">[!code-cs[csProgGuideGenerics#23](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_2.cs)]</span></span>  
  
 <span data-ttu-id="e85f3-107">형식 인수를 생략하고 컴파일러에서 이를 자동으로 유추하도록 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-107">You can also omit the type argument and the compiler will infer it.</span></span> <span data-ttu-id="e85f3-108">`Swap`에 대한 다음 호출은 위 예제의 호출과 동일한 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-108">The following call to `Swap` is equivalent to the previous call:</span></span>  
  
 <span data-ttu-id="e85f3-109">[!code-cs[csProgGuideGenerics#24](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="e85f3-109">[!code-cs[csProgGuideGenerics#24](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_3.cs)]</span></span>  
  
 <span data-ttu-id="e85f3-110">정적 메서드와 인스턴스 메서드에는 형식 유추와 동일한 규칙이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-110">The same rules for type inference apply to static methods and instance methods.</span></span> <span data-ttu-id="e85f3-111">컴파일러는 전달한 메서드 인수에 따라 형식 매개 변수를 유추할 수 있지만, 제약 조건이나 반환 값만으로는 형식 매개 변수를 유추할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-111">The compiler can infer the type parameters based on the method arguments you pass in; it cannot infer the type parameters only from a constraint or return value.</span></span> <span data-ttu-id="e85f3-112">따라서 매개 변수가 없는 메서드에 대해서는 형식 유추가 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-112">Therefore type inference does not work with methods that have no parameters.</span></span> <span data-ttu-id="e85f3-113">형식 유추는 컴파일러에서 오버로드된 메서드 시그니처를 확인하려고 하기 전에 컴파일 시간에 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-113">Type inference occurs at compile time before the compiler tries to resolve overloaded method signatures.</span></span> <span data-ttu-id="e85f3-114">컴파일러는 동일한 이름을 공유하는 모든 제네릭 메서드에 형식 유추 논리를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-114">The compiler applies type inference logic to all generic methods that share the same name.</span></span> <span data-ttu-id="e85f3-115">오버로드 확인 단계에서 컴파일러는 형식 유추에 성공한 제네릭 메서드만 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-115">In the overload resolution step, the compiler includes only those generic methods on which type inference succeeded.</span></span>  
  
 <span data-ttu-id="e85f3-116">제네릭 클래스 내에서 제네릭이 아닌 메서드는 다음과 같은 클래스 수준의 형식 매개 변수에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-116">Within a generic class, non-generic methods can access the class-level type parameters, as follows:</span></span>  
  
 <span data-ttu-id="e85f3-117">[!code-cs[csProgGuideGenerics#25](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="e85f3-117">[!code-cs[csProgGuideGenerics#25](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_4.cs)]</span></span>  
  
 <span data-ttu-id="e85f3-118">포함하는 클래스와 동일한 형식 매개 변수를 사용하는 제네릭 메서드를 정의하면 컴파일러에서 CS0693 경고가 발생합니다. 이는 메서드 범위 내에서 내부 `T`에 제공된 인수가 외부 `T`에 제공된 인수를 숨기기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-118">If you define a generic method that takes the same type parameters as the containing class, the compiler generates warning CS0693 because within the method scope, the argument supplied for the inner `T` hides the argument supplied for the outer `T`.</span></span> <span data-ttu-id="e85f3-119">클래스를 인스턴스화할 때 제공한 형식 인수가 아닌 다른 형식 인수를 사용하여 제네릭 클래스 메서드를 호출할 수 있으려면 다음 예제의 `GenericList2<T>`에서와 같이 메서드의 형식 매개 변수에 다른 식별자를 제공해 보세요.</span><span class="sxs-lookup"><span data-stu-id="e85f3-119">If you require the flexibility of calling a generic class method with type arguments other than the ones provided when the class was instantiated, consider providing another identifier for the type parameter of the method, as shown in `GenericList2<T>` in the following example.</span></span>  
  
 <span data-ttu-id="e85f3-120">[!code-cs[csProgGuideGenerics#26](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="e85f3-120">[!code-cs[csProgGuideGenerics#26](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_5.cs)]</span></span>  
  
 <span data-ttu-id="e85f3-121">메서드에서 형식 매개 변수에 대한 더 구체적인 작업을 수행하려면 제약 조건을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-121">Use constraints to enable more specialized operations on type parameters in methods.</span></span> <span data-ttu-id="e85f3-122">`SwapIfGreater<T>`라는 이 버전의 `Swap<T>`은 <xref:System.IComparable%601>을 구현하는 형식 인수와만 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-122">This version of `Swap<T>`, now named `SwapIfGreater<T>`, can only be used with type arguments that implement <xref:System.IComparable%601>.</span></span>  
  
 <span data-ttu-id="e85f3-123">[!code-cs[csProgGuideGenerics#27](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="e85f3-123">[!code-cs[csProgGuideGenerics#27](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_6.cs)]</span></span>  
  
 <span data-ttu-id="e85f3-124">제네릭 메서드는 몇몇 형식 매개 변수에 오버로드될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-124">Generic methods can be overloaded on several type parameters.</span></span> <span data-ttu-id="e85f3-125">예를 들어 다음 메서드는 모두 동일한 클래스에 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e85f3-125">For example, the following methods can all be located in the same class:</span></span>  
  
 <span data-ttu-id="e85f3-126">[!code-cs[csProgGuideGenerics#28](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="e85f3-126">[!code-cs[csProgGuideGenerics#28](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-methods_7.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="e85f3-127">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="e85f3-127">C# Language Specification</span></span>  
 <span data-ttu-id="e85f3-128">자세한 내용은 [C# 언어 사양](../../../csharp/language-reference/language-specification/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e85f3-128">For more information, see the [C# Language Specification](../../../csharp/language-reference/language-specification/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e85f3-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e85f3-129">See Also</span></span>  
 <span data-ttu-id="e85f3-130"><xref:System.Collections.Generic></span><span class="sxs-lookup"><span data-stu-id="e85f3-130"><xref:System.Collections.Generic></span></span>   
 <span data-ttu-id="e85f3-131">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="e85f3-131">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="e85f3-132">[제네릭 소개](../../../csharp/programming-guide/generics/introduction-to-generics.md) </span><span class="sxs-lookup"><span data-stu-id="e85f3-132">[Introduction to Generics](../../../csharp/programming-guide/generics/introduction-to-generics.md) </span></span>  
 [<span data-ttu-id="e85f3-133">메서드</span><span class="sxs-lookup"><span data-stu-id="e85f3-133">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)

