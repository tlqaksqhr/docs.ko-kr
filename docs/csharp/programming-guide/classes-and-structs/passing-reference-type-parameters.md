---
title: "참조 형식 매개 변수 전달(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- method parameters [C#], reference types
- parameters [C#], reference
ms.assetid: 9e6eb65c-942e-48ab-920a-b7ba9df4ea20
caps.latest.revision: 14
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
ms.openlocfilehash: 3f57dc9f0de6fae6da3ec8e6e6cfdc3a21baeaea
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="passing-reference-type-parameters-c-programming-guide"></a><span data-ttu-id="76679-102">참조 형식 매개 변수 전달(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="76679-102">Passing Reference-Type Parameters (C# Programming Guide)</span></span>
<span data-ttu-id="76679-103">[참조 형식](../../../csharp/language-reference/keywords/reference-types.md)의 변수에는 해당 데이터가 직접 포함되지 않고 데이터에 대한 참조가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="76679-103">A variable of a [reference type](../../../csharp/language-reference/keywords/reference-types.md) does not contain its data directly; it contains a reference to its data.</span></span> <span data-ttu-id="76679-104">참조 형식 매개 변수를 값으로 전달하는 경우 클래스 멤버 값 등 참조에서 가리키는 데이터를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76679-104">When you pass a reference-type parameter by value, it is possible to change the data pointed to by the reference, such as the value of a class member.</span></span> <span data-ttu-id="76679-105">하지만 참조 자체의 값은 변경할 수 없습니다. 즉, 동일한 참조를 사용하여 새 클래스에 대한 메모리를 할당하고 블록 외부에 유지되도록 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="76679-105">However, you cannot change the value of the reference itself; that is, you cannot use the same reference to allocate memory for a new class and have it persist outside the block.</span></span> <span data-ttu-id="76679-106">이렇게 하려면 [ref](../../../csharp/language-reference/keywords/ref.md) 또는 [out](../../../csharp/language-reference/keywords/out.md) 키워드를 사용하여 매개 변수를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="76679-106">To do that, pass the parameter using the [ref](../../../csharp/language-reference/keywords/ref.md) or [out](../../../csharp/language-reference/keywords/out.md) keyword.</span></span> <span data-ttu-id="76679-107">간단한 설명을 위해 다음 예제에서는 `ref`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="76679-107">For simplicity, the following examples use `ref`.</span></span>  
  
## <a name="passing-reference-types-by-value"></a><span data-ttu-id="76679-108">값으로 참조 형식 전달</span><span class="sxs-lookup"><span data-stu-id="76679-108">Passing Reference Types by Value</span></span>  
 <span data-ttu-id="76679-109">다음 예제에서는 참조 형식 매개 변수 `arr`을 `Change` 메서드에 값으로 전달하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="76679-109">The following example demonstrates passing a reference-type parameter, `arr`, by value, to a method, `Change`.</span></span> <span data-ttu-id="76679-110">매개 변수가 `arr`에 대한 참조이므로 배열 요소의 값을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76679-110">Because the parameter is a reference to `arr`, it is possible to change the values of the array elements.</span></span> <span data-ttu-id="76679-111">그러나 다른 메모리 위치에 매개 변수를 다시 할당하려는 시도는 메서드 내부에서만 작동하고 원래 변수 `arr`에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="76679-111">However, the attempt to reassign the parameter to a different memory location only works inside the method and does not affect the original variable, `arr`.</span></span>  
  
 <span data-ttu-id="76679-112">[!code-cs[csProgGuideParameters#7](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-reference-type-parameters_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="76679-112">[!code-cs[csProgGuideParameters#7](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-reference-type-parameters_1.cs)]</span></span>  
  
 <span data-ttu-id="76679-113">앞의 예제에서 참조 형식인 `arr` 배열은 `ref` 매개 변수 없이 메서드에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="76679-113">In the preceding example, the array, `arr`, which is a reference type, is passed to the method without the `ref` parameter.</span></span> <span data-ttu-id="76679-114">이 경우 `arr`을 가리키는 참조의 복사본이 메서드에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="76679-114">In such a case, a copy of the reference, which points to `arr`, is passed to the method.</span></span> <span data-ttu-id="76679-115">출력에서는 이 경우 메서드가 배열 요소의 내용을 `1`에서 `888`로 변경할 수 있음을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="76679-115">The output shows that it is possible for the method to change the contents of an array element, in this case from `1` to `888`.</span></span> <span data-ttu-id="76679-116">그러나 `Change` 메서드 내에서 [new](../../../csharp/language-reference/keywords/new.md) 연산자를 사용하여 새 메모리 부분을 할당하면 `pArray` 변수가 새 배열을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="76679-116">However, allocating a new portion of memory by using the [new](../../../csharp/language-reference/keywords/new.md) operator inside the `Change` method makes the variable `pArray` reference a new array.</span></span> <span data-ttu-id="76679-117">따라서 그 후의 변경 내용은 `Main` 내에서 생성된 원래 배열 `arr`에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="76679-117">Thus, any changes after that will not affect the original array, `arr`, which is created inside `Main`.</span></span> <span data-ttu-id="76679-118">실제로 이 예제에서는 `Main` 내부와 `Change` 메서드 내부에 각각 하나씩, 두 개의 배열이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="76679-118">In fact, two arrays are created in this example, one inside `Main` and one inside the `Change` method.</span></span>  
  
## <a name="passing-reference-types-by-reference"></a><span data-ttu-id="76679-119">참조로 참조 형식 전달</span><span class="sxs-lookup"><span data-stu-id="76679-119">Passing Reference Types by Reference</span></span>  
 <span data-ttu-id="76679-120">다음 예제는 `ref` 키워드가 메서드 헤더 및 호출에 추가된다는 점을 제외하고 앞의 예제와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="76679-120">The following example is the same as the previous example, except that the `ref` keyword is added to the method header and call.</span></span> <span data-ttu-id="76679-121">메서드에서 발생하는 모든 변경 내용이 호출하는 프로그램의 원래 변수에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="76679-121">Any changes that take place in the method affect the original variable in the calling program.</span></span>  
  
 <span data-ttu-id="76679-122">[!code-cs[csProgGuideParameters#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-reference-type-parameters_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="76679-122">[!code-cs[csProgGuideParameters#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-reference-type-parameters_2.cs)]</span></span>  
  
 <span data-ttu-id="76679-123">메서드 내에서 발생하는 모든 변경 내용은 `Main`의 원래 배열에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="76679-123">All of the changes that take place inside the method affect the original array in `Main`.</span></span> <span data-ttu-id="76679-124">실제로 원래 배열은 `new` 연산자를 사용하여 다시 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="76679-124">In fact, the original array is reallocated using the `new` operator.</span></span> <span data-ttu-id="76679-125">따라서 `Change` 메서드를 호출한 후 `arr`에 대한 모든 참조는 `Change` 메서드에서 생성된 5개 요소의 배열을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="76679-125">Thus, after calling the `Change` method, any reference to `arr` points to the five-element array, which is created in the `Change` method.</span></span>  
  
## <a name="swapping-two-strings"></a><span data-ttu-id="76679-126">두 문자열 교환</span><span class="sxs-lookup"><span data-stu-id="76679-126">Swapping Two Strings</span></span>  
 <span data-ttu-id="76679-127">문자열 교환은 참조 형식 매개 변수를 참조로 전달하는 좋은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="76679-127">Swapping strings is a good example of passing reference-type parameters by reference.</span></span> <span data-ttu-id="76679-128">예제에서는 두 개의 문자열 `str1` 및 `str2`가 `Main`에서 초기화되고 `ref` 키워드로 수정되는 매개 변수로 `SwapStrings` 메서드에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="76679-128">In the example, two strings, `str1` and `str2`, are initialized in `Main` and passed to the `SwapStrings` method as parameters modified by the `ref` keyword.</span></span> <span data-ttu-id="76679-129">두 문자열이 메서드 및 `Main` 내에서 교환됩니다.</span><span class="sxs-lookup"><span data-stu-id="76679-129">The two strings are swapped inside the method and inside `Main` as well.</span></span>  
  
 <span data-ttu-id="76679-130">[!code-cs[csProgGuideParameters#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-reference-type-parameters_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="76679-130">[!code-cs[csProgGuideParameters#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-reference-type-parameters_3.cs)]</span></span>  
  
 <span data-ttu-id="76679-131">이 예제에서는 호출하는 프로그램의 변수에 영향을 주기 위해 매개 변수를 참조로 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="76679-131">In this example, the parameters need to be passed by reference to affect the variables in the calling program.</span></span> <span data-ttu-id="76679-132">메서드 헤더와 메서드 호출 모두에서 `ref` 키워드를 제거하는 경우 호출하는 프로그램에서는 아무것도 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="76679-132">If you remove the `ref` keyword from both the method header and the method call, no changes will take place in the calling program.</span></span>  
  
 <span data-ttu-id="76679-133">문자열에 대한 자세한 내용은 [문자열](../../../csharp/language-reference/keywords/string.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="76679-133">For more information about strings, see [string](../../../csharp/language-reference/keywords/string.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76679-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="76679-134">See Also</span></span>  
 <span data-ttu-id="76679-135">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="76679-135">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="76679-136">[매개 변수 전달](../../../csharp/programming-guide/classes-and-structs/passing-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="76679-136">[Passing Parameters](../../../csharp/programming-guide/classes-and-structs/passing-parameters.md) </span></span>  
 <span data-ttu-id="76679-137">[ref 및 out을 사용하여 배열 전달](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md) </span><span class="sxs-lookup"><span data-stu-id="76679-137">[Passing Arrays Using ref and out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md) </span></span>  
 <span data-ttu-id="76679-138">[ref](../../../csharp/language-reference/keywords/ref.md) </span><span class="sxs-lookup"><span data-stu-id="76679-138">[ref](../../../csharp/language-reference/keywords/ref.md) </span></span>  
 [<span data-ttu-id="76679-139">참조 형식</span><span class="sxs-lookup"><span data-stu-id="76679-139">Reference Types</span></span>](../../../csharp/language-reference/keywords/reference-types.md)

