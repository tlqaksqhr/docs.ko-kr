---
title: "값 형식 매개 변수 전달(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- method parameters [C#], value types
- parameters [C#], value
ms.assetid: 193ab86f-5f9b-4359-ac29-7cdf8afad3a6
caps.latest.revision: 17
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
ms.openlocfilehash: a3377630fc4294831f6b9d66a69377aa42d973f1
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="passing-value-type-parameters-c-programming-guide"></a><span data-ttu-id="dea31-102">값 형식 매개 변수 전달(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="dea31-102">Passing Value-Type Parameters (C# Programming Guide)</span></span>
<span data-ttu-id="dea31-103">데이터에 대한 참조가 포함되어 있는 [참조 형식](../../../csharp/language-reference/keywords/reference-types.md) 변수와는 달리, [값 형식](../../../csharp/language-reference/keywords/value-types.md) 변수에는 해당 데이터가 직접 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="dea31-103">A [value-type](../../../csharp/language-reference/keywords/value-types.md) variable contains its data directly as opposed to a [reference-type](../../../csharp/language-reference/keywords/reference-types.md) variable, which contains a reference to its data.</span></span> <span data-ttu-id="dea31-104">값 형식 변수를 메서드에 값으로 전달하는 것은 변수의 복사본을 메서드에 전달하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="dea31-104">Passing a value-type variable to a method by value means passing a copy of the variable to the method.</span></span> <span data-ttu-id="dea31-105">메서드 내에서 수행되는 매개 변수 변경 작업은 인수 변수에 저장된 원래 데이터에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dea31-105">Any changes to the parameter that take place inside the method have no affect on the original data stored in the argument variable.</span></span> <span data-ttu-id="dea31-106">호출한 메서드가 매개 변수의 값을 변경하도록 하려면 [ref](../../../csharp/language-reference/keywords/ref.md) 또는 [아웃](../../../csharp/language-reference/keywords/out.md) 키워드를 사용하여 해당 메서드를 참조로 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dea31-106">If you want the called method to change the value of the parameter, you must pass it by reference, using the [ref](../../../csharp/language-reference/keywords/ref.md) or [out](../../../csharp/language-reference/keywords/out.md) keyword.</span></span> <span data-ttu-id="dea31-107">간단한 설명을 위해 다음 예제에서는 `ref`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="dea31-107">For simplicity, the following examples use `ref`.</span></span>  
  
## <a name="passing-value-types-by-value"></a><span data-ttu-id="dea31-108">값으로 값 형식 전달</span><span class="sxs-lookup"><span data-stu-id="dea31-108">Passing Value Types by Value</span></span>  
 <span data-ttu-id="dea31-109">다음 예제에서는 값 형식 매개 변수를 값으로 전달하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dea31-109">The following example demonstrates passing value-type parameters by value.</span></span> <span data-ttu-id="dea31-110">`n` 변수가 `SquareIt` 메서드에 값으로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="dea31-110">The variable `n` is passed by value to the method `SquareIt`.</span></span> <span data-ttu-id="dea31-111">메서드 내에서 수행되는 변경 작업은 변수의 원래 값에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dea31-111">Any changes that take place inside the method have no affect on the original value of the variable.</span></span>  
  
 <span data-ttu-id="dea31-112">[!code-cs[csProgGuideParameters#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="dea31-112">[!code-cs[csProgGuideParameters#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_1.cs)]</span></span>  
  
 <span data-ttu-id="dea31-113">`n` 변수는 값 형식이며</span><span class="sxs-lookup"><span data-stu-id="dea31-113">The variable `n` is a value type.</span></span> <span data-ttu-id="dea31-114">값 `5` 5를 데이터로 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="dea31-114">It contains its data, the value `5`.</span></span> <span data-ttu-id="dea31-115">`SquareIt`을 호출하면 `n`의 내용이 `x` 매개 변수로 복사됩니다. 그러면 메서드 내에서 이 매개 변수의 값을 제곱합니다.</span><span class="sxs-lookup"><span data-stu-id="dea31-115">When `SquareIt` is invoked, the contents of `n` are copied into the parameter `x`, which is squared inside the method.</span></span> <span data-ttu-id="dea31-116">그러나 `Main`에서는 `n`의 값이 `SquareIt` 메서드를 호출한 후에도 호출 전과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="dea31-116">In `Main`, however, the value of `n` is the same after calling the `SquareIt` method as it was before.</span></span> <span data-ttu-id="dea31-117">즉, 메서드 내에서 수행되는 변경은 지역 변수 `x`에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="dea31-117">The change that takes place inside the method only affects the local variable `x`.</span></span>  
  
## <a name="passing-value-types-by-reference"></a><span data-ttu-id="dea31-118">참조로 값 형식 전달</span><span class="sxs-lookup"><span data-stu-id="dea31-118">Passing Value Types by Reference</span></span>  
 <span data-ttu-id="dea31-119">다음 예제는 인수가 `ref` 매개 변수로 전달된다는 점을 제외하면 이전 예제와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="dea31-119">The following example is the same as the previous example, except that the argument is passed as a `ref` parameter.</span></span> <span data-ttu-id="dea31-120">메서드에서 `x`가 변경되면 기본 인수 `n`의 값도 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="dea31-120">The value of the underlying argument, `n`, is changed when `x` is changed in the method.</span></span>  
  
 <span data-ttu-id="dea31-121">[!code-cs[csProgGuideParameters#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="dea31-121">[!code-cs[csProgGuideParameters#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_2.cs)]</span></span>  
  
 <span data-ttu-id="dea31-122">이 예제에서는 `n`의 값이 아니라 `n`에 대한 참조가 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="dea31-122">In this example, it is not the value of `n` that is passed; rather, a reference to `n` is passed.</span></span> <span data-ttu-id="dea31-123">`x` 매개 변수는 [int](../../../csharp/language-reference/keywords/int.md)가 아니며 `int`에 대한 참조(이 예제에서는 `n`에 대한 참조)입니다.</span><span class="sxs-lookup"><span data-stu-id="dea31-123">The parameter `x` is not an [int](../../../csharp/language-reference/keywords/int.md); it is a reference to an `int`, in this case, a reference to `n`.</span></span> <span data-ttu-id="dea31-124">그러므로 메서드 내에서 `x`를 제곱할 때 실제로는 `x`가 참조하는 `n`을 제곱하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dea31-124">Therefore, when `x` is squared inside the method, what actually is squared is what `x` refers to, `n`.</span></span>  
  
## <a name="swapping-value-types"></a><span data-ttu-id="dea31-125">값 형식 교환</span><span class="sxs-lookup"><span data-stu-id="dea31-125">Swapping Value Types</span></span>  
 <span data-ttu-id="dea31-126">인수의 값을 변경하는 일반적인 예로는 두 변수를 메서드에 전달하면 메서드가 변수의 내용을 교환하는 swap 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dea31-126">A common example of changing the values of arguments is a swap method, where you pass two variables to the method, and the method swaps their contents.</span></span> <span data-ttu-id="dea31-127">이때 인수는 swap 메서드에 참조로 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dea31-127">You must pass the arguments to the swap method by reference.</span></span> <span data-ttu-id="dea31-128">이렇게 하지 않으면 메서드 내에서 매개 변수의 로컬 복사본이 교환되므로 호출하는 메서드에서는 변경이 수행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dea31-128">Otherwise, you swap local copies of the parameters inside the method, and no change occurs in the calling method.</span></span> <span data-ttu-id="dea31-129">다음 예제에서는 정수 값을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="dea31-129">The following example swaps integer values.</span></span>  
  
 <span data-ttu-id="dea31-130">[!code-cs[csProgGuideParameters#5](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="dea31-130">[!code-cs[csProgGuideParameters#5](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_3.cs)]</span></span>  
  
 <span data-ttu-id="dea31-131">`SwapByRef` 메서드를 호출할 때는 다음 예제와 같이 호출에 `ref` 키워드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="dea31-131">When you call the `SwapByRef` method, use the `ref` keyword in the call, as shown in the following example.</span></span>  
  
 <span data-ttu-id="dea31-132">[!code-cs[csProgGuideParameters#6](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="dea31-132">[!code-cs[csProgGuideParameters#6](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_4.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dea31-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dea31-133">See Also</span></span>  
 <span data-ttu-id="dea31-134">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="dea31-134">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="dea31-135">[매개 변수 전달](../../../csharp/programming-guide/classes-and-structs/passing-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="dea31-135">[Passing Parameters](../../../csharp/programming-guide/classes-and-structs/passing-parameters.md) </span></span>  
 [<span data-ttu-id="dea31-136">참조 형식 매개 변수 전달</span><span class="sxs-lookup"><span data-stu-id="dea31-136">Passing Reference-Type Parameters</span></span>](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md)

