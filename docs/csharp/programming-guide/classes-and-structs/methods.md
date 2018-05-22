---
title: 메서드(C# 프로그래밍 가이드)
ms.date: 07/20/2015
helpviewer_keywords:
- methods [C#]
- C# language, methods
ms.assetid: cc738f07-e8cd-4683-9585-9f40c0667c37
ms.openlocfilehash: d3fc4107c10d098d40e4021bef9f6acd06311fab
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="methods-c-programming-guide"></a><span data-ttu-id="7bec0-102">메서드(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="7bec0-102">Methods (C# Programming Guide)</span></span>
<span data-ttu-id="7bec0-103">메서드는 일련의 문을 포함하는 코드 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-103">A method is a code block that contains a series of statements.</span></span> <span data-ttu-id="7bec0-104">프로그램을 통해 메서드를 호출하고 필요한 메서드 인수를 지정하여 문을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-104">A program causes the statements to be executed by calling the method and specifying any required method arguments.</span></span> <span data-ttu-id="7bec0-105">C#에서는 실행된 모든 명령이 메서드의 컨텍스트에서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-105">In C#, every executed instruction is performed in the context of a method.</span></span> <span data-ttu-id="7bec0-106">Main 메서드는 모든 C# 응용 프로그램의 진입점이고 프로그램이 시작될 때 CLR(공용 언어 런타임)에서 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-106">The Main method is the entry point for every C# application and it is called by the common language runtime (CLR) when the program is started.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7bec0-107">이 항목에서는 명명된 메서드에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-107">This topic discusses named methods.</span></span> <span data-ttu-id="7bec0-108">익명 함수에 대한 자세한 내용은 [익명 함수](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7bec0-108">For information about anonymous functions, see [Anonymous Functions](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).</span></span>  
  
## <a name="method-signatures"></a><span data-ttu-id="7bec0-109">메서드 서명</span><span class="sxs-lookup"><span data-stu-id="7bec0-109">Method Signatures</span></span>  
 <span data-ttu-id="7bec0-110">메서드는 [클래스](../../../csharp/language-reference/keywords/class.md) 또는 [구조체](../../../csharp/language-reference/keywords/struct.md) 에서 `public` 또는 `private`등의 액세스 수준, `abstract` 또는 `sealed`등의 선택적 한정자, 반환 값, 메서드 이름 및 메서드 매개 변수를 지정하여 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-110">Methods are declared in a [class](../../../csharp/language-reference/keywords/class.md) or [struct](../../../csharp/language-reference/keywords/struct.md) by specifying the access level such as `public` or `private`, optional modifiers such as `abstract` or `sealed`, the return value, the name of the method, and any method parameters.</span></span> <span data-ttu-id="7bec0-111">이들 파트는 함께 메서드 서명을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-111">These parts together are the signature of the method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7bec0-112">메서드의 반환 값은 메서드 오버로드를 위한 메서드 서명의 파트가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-112">A return type of a method is not part of the signature of the method for the purposes of method overloading.</span></span> <span data-ttu-id="7bec0-113">그러나 대리자와 대리자가 가리키는 메서드 간의 호환성을 결정할 경우에는 메서드 서명의 파트입니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-113">However, it is part of the signature of the method when determining the compatibility between a delegate and the method that it points to.</span></span>  
  
 <span data-ttu-id="7bec0-114">메서드 매개 변수는 괄호로 묶고 쉼표로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-114">Method parameters are enclosed in parentheses and are separated by commas.</span></span> <span data-ttu-id="7bec0-115">빈 괄호는 메서드에 매개 변수가 필요하지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-115">Empty parentheses indicate that the method requires no parameters.</span></span> <span data-ttu-id="7bec0-116">이 클래스에는 다음 세 가지 메서드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-116">This class contains three methods:</span></span>  
  
 [!code-csharp[csProgGuideObjects#40](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/methods_1.cs)]  
  
## <a name="method-access"></a><span data-ttu-id="7bec0-117">메서드 액세스</span><span class="sxs-lookup"><span data-stu-id="7bec0-117">Method Access</span></span>  
 <span data-ttu-id="7bec0-118">개체에 대한 메서드 호출은 필드 액세스와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-118">Calling a method on an object is like accessing a field.</span></span> <span data-ttu-id="7bec0-119">개체 이름 뒤에 마침표, 메서드 이름 및 괄호를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-119">After the object name, add a period, the name of the method, and parentheses.</span></span> <span data-ttu-id="7bec0-120">인수는 괄호 안에 나열되고 쉼표로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-120">Arguments are listed within the parentheses, and are separated by commas.</span></span> <span data-ttu-id="7bec0-121">`Motorcycle` 클래스의 메서드는 다음 예제와 같이 호출될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-121">The methods of the `Motorcycle` class can therefore be called as in the following example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#41](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/methods_2.cs)]  
  
## <a name="method-parameters-vs-arguments"></a><span data-ttu-id="7bec0-122">메서드 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="7bec0-122">Method Parameters vs. Arguments</span></span>  
 <span data-ttu-id="7bec0-123">메서드 정의는 필요한 모든 매개 변수의 이름 및 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-123">The method definition specifies the names and types of any parameters that are required.</span></span> <span data-ttu-id="7bec0-124">호출하는 코드에서 메서드를 호출할 때 해당 코드는 각 매개 변수에 대한 인수라는 구체적인 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-124">When calling code calls the method, it provides concrete values called arguments for each parameter.</span></span> <span data-ttu-id="7bec0-125">인수는 매개 변수 형식과 호환되어야 하지만 호출하는 코드에 사용된 인수 이름(있는 경우)은 메서드에 정의된 명명된 매개 변수와 동일할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-125">The arguments must be compatible with the parameter type but the argument name (if any) used in the calling code does not have to be the same as the parameter named defined in the method.</span></span> <span data-ttu-id="7bec0-126">예:</span><span class="sxs-lookup"><span data-stu-id="7bec0-126">For example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#74](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/methods_3.cs)]  
  
## <a name="passing-by-reference-vs-passing-by-value"></a><span data-ttu-id="7bec0-127">참조로 전달 및 값으로 전달</span><span class="sxs-lookup"><span data-stu-id="7bec0-127">Passing by Reference vs. Passing by Value</span></span>  
 <span data-ttu-id="7bec0-128">기본적으로 값 형식이 메서드에 전달될 때 개체 자체가 아닌 복사본이 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-128">By default, when a value type is passed to a method, a copy is passed instead of the object itself.</span></span> <span data-ttu-id="7bec0-129">따라서 인수에 대한 변경 내용은 호출하는 메서드의 원래 복사본에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-129">Therefore, changes to the argument have no effect on the original copy in the calling method.</span></span> <span data-ttu-id="7bec0-130">ref 키워드를 사용하여 값 형식을 참조로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-130">You can pass a value-type by reference by using the ref keyword.</span></span> <span data-ttu-id="7bec0-131">자세한 내용은 [값 형식 매개 변수 전달](../../../csharp/programming-guide/classes-and-structs/passing-value-type-parameters.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7bec0-131">For more information, see [Passing Value-Type Parameters](../../../csharp/programming-guide/classes-and-structs/passing-value-type-parameters.md).</span></span> <span data-ttu-id="7bec0-132">기본 제공 값 형식 목록을 보려면 [값 형식 표](../../../csharp/language-reference/keywords/value-types-table.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7bec0-132">For a list of built-in value types, see [Value Types Table](../../../csharp/language-reference/keywords/value-types-table.md).</span></span>  
  
 <span data-ttu-id="7bec0-133">참조 형식의 개체가 메서드에 전달될 때 개체에 대한 참조가 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-133">When an object of a reference type is passed to a method, a reference to the object is passed.</span></span> <span data-ttu-id="7bec0-134">즉, 메서드는 개체 자체가 아니라 개체의 위치를 나타내는 인수를 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-134">That is, the method receives not the object itself but an argument that indicates the location of the object.</span></span> <span data-ttu-id="7bec0-135">이 참조를 사용하여 개체의 멤버를 변경하면 개체를 값으로 전달하더라도 변경 내용은 호출하는 메서드의 인수에 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-135">If you change a member of the object by using this reference, the change is reflected in the argument in the calling method, even if you pass the object by value.</span></span>  
  
 <span data-ttu-id="7bec0-136">다음 예제와 같이 `class` 키워드를 사용하여 참조 형식을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-136">You create a reference type by using the `class` keyword, as the following example shows.</span></span>  
  
 [!code-csharp[csProgGuideObjects#42](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/methods_4.cs)]  
  
 <span data-ttu-id="7bec0-137">이제 이 형식에 기반을 둔 개체를 메서드에 전달하면 개체에 대한 참조가 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-137">Now, if you pass an object that is based on this type to a method, a reference to the object is passed.</span></span> <span data-ttu-id="7bec0-138">다음 예제에서는 `SampleRefType` 형식의 개체를 `ModifyObject`메서드에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-138">The following example passes an object of type `SampleRefType` to method `ModifyObject`.</span></span>  
  
 [!code-csharp[csProgGuideObjects#75](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/methods_5.cs)]  
  
 <span data-ttu-id="7bec0-139">이 예제는 인수를 값으로 메서드에 전달한다는 점에서 기본적으로 이전 예제와 같은 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-139">The example does essentially the same thing as the previous example in that it passes an argument by value to a method.</span></span> <span data-ttu-id="7bec0-140">그러나 참조 형식이 사용되므로 결과가 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-140">But, because a reference type is used, the result is different.</span></span> <span data-ttu-id="7bec0-141">`ModifyObject` 에서 매개 변수 `value` 의 `obj`필드에 대해 수정한 내용으로 인해 `value` 메서드에서 `rt`인수의 `TestRefType` 필드도 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-141">The modification that is made in `ModifyObject` to the `value` field of the parameter, `obj`, also changes the `value` field of the argument, `rt`, in the `TestRefType` method.</span></span> <span data-ttu-id="7bec0-142">`TestRefType` 메서드는 출력으로 33을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-142">The `TestRefType` method displays 33 as the output.</span></span>  
  
 <span data-ttu-id="7bec0-143">참조 형식을 참조 및 값으로 전달하는 방법에 대한 자세한 내용은 [참조-형식 매개 변수 전달](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md) 및 [참조 형식](../../../csharp/language-reference/keywords/reference-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7bec0-143">For more information about how to pass reference types by reference and by value, see [Passing Reference-Type Parameters](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md) and [Reference Types](../../../csharp/language-reference/keywords/reference-types.md).</span></span>  
  
## <a name="return-values"></a><span data-ttu-id="7bec0-144">반환 값</span><span class="sxs-lookup"><span data-stu-id="7bec0-144">Return Values</span></span>  
<span data-ttu-id="7bec0-145">메서드는 호출자에 값을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-145">Methods can return a value to the caller.</span></span> <span data-ttu-id="7bec0-146">메서드 이름 앞에 나열된 반환 형식이 `void`가 아니면 메서드는 `return` 키워드를 사용하여 값을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-146">If the return type, the type listed before the method name, is not `void`, the method can return the value by using the `return` keyword.</span></span> <span data-ttu-id="7bec0-147">`return` 키워드에 이어 반환 형식과 일치하는 값을 포함하는 문은 메서드 호출자에 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-147">A statement with the `return` keyword followed by a value that matches the return type will return that value to the method caller.</span></span> 

<span data-ttu-id="7bec0-148">호출자에게 값으로 또는 C# 7.0부터 [참조로](ref-returns.md) 값을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-148">The value can be returned to the caller by value or, starting with C# 7.0, [by reference](ref-returns.md).</span></span> <span data-ttu-id="7bec0-149">`ref` 키워드가 메서드 시그니처에 사용되고 각 `return` 키워드 뒤에 오면 값이 호출자에게 참조로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-149">Values are returned to the caller by reference if the `ref` keyword is used in the method signature and it follows each `return` keyword.</span></span> <span data-ttu-id="7bec0-150">예를 들어 다음 메서드 시그니처 및 반환 문은 메서드가 변수 이름 `estDistance`를 호출자에게 참조로 반환함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-150">For example, the following method signature and return statement indicate that the method returns a variable names `estDistance` by reference to the caller.</span></span>

```csharp
public ref double GetEstimatedDistance()
{
   return ref estDistance;
}
```

<span data-ttu-id="7bec0-151">`return` 키워드는 메서드 실행을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-151">The `return` keyword also stops the execution of the method.</span></span> <span data-ttu-id="7bec0-152">반환 형식이 `void`이면 값이 없는 `return` 문을 사용하여 메서드 실행을 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-152">If the return type is `void`, a `return` statement without a value is still useful to stop the execution of the method.</span></span> <span data-ttu-id="7bec0-153">`return` 키워드를 사용하지 않으면 메서드는 코드 블록 끝에 도달할 때 실행을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-153">Without the `return` keyword, the method will stop executing when it reaches the end of the code block.</span></span> <span data-ttu-id="7bec0-154">`return` 키워드를 사용하여 값을 반환하려면 void가 아닌 반환 값을 포함한 메서드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-154">Methods with a non-void return type are required to use the `return` keyword to return a value.</span></span> <span data-ttu-id="7bec0-155">예를 들어 이들 두 메서드에서는 `return` 키워드를 사용하여 정수를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-155">For example, these two methods use the `return` keyword to return integers:</span></span>  
  
 [!code-csharp[csProgGuideObjects#44](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/methods_6.cs)]  
  
 <span data-ttu-id="7bec0-156">메서드에서 반환된 값을 사용하려면 호출하는 메서드에서 같은 형식의 값으로 충분한 모든 경우에 메서드 호출 자체를 사용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-156">To use a value returned from a method, the calling method can use the method call itself anywhere a value of the same type would be sufficient.</span></span> <span data-ttu-id="7bec0-157">반환 값을 변수에 할당할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-157">You can also assign the return value to a variable.</span></span> <span data-ttu-id="7bec0-158">예를 들어 다음 두 코드 예제에서는 같은 목표를 달성합니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-158">For example, the following two code examples accomplish the same goal:</span></span>  
  
 [!code-csharp[csProgGuideObjects#45](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/methods_7.cs)]  
  
 [!code-csharp[csProgGuideObjects#46](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/methods_8.cs)]  
  
 <span data-ttu-id="7bec0-159">지역 변수(이 경우 `result`)를 사용하여 값을 저장하는 것은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-159">Using a local variable, in this case, `result`, to store a value is optional.</span></span> <span data-ttu-id="7bec0-160">코드의 가독성에 도움이 될 수 있고 전체 메서드 범위에 대해 인수의 원래 값을 저장해야 할 경우 필요할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-160">It may help the readability of the code, or it may be necessary if you need to store the original value of the argument for the entire scope of the method.</span></span>  

<span data-ttu-id="7bec0-161">메서드에서 참조로 반환된 값을 사용하려면 해당 값을 수정하려는 경우 [참조 지역](ref-returns.md#ref-locals) 변수를 선언해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-161">To use a value returned by reference from a method, you must declare a [ref local](ref-returns.md#ref-locals) variable if you intend to modify its value.</span></span> <span data-ttu-id="7bec0-162">예를 들어 `Planet.GetEstimatedDistance` 메서드가 <xref:System.Double> 값을 참조로 반환하는 경우 다음과 같은 코드를 사용하여 참조 지역 변수로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-162">For example, if the `Planet.GetEstimatedDistance` method returns a <xref:System.Double> value by reference, you can define it as a ref local variable with code like the following:</span></span>

```csharp
ref int distance = plant 
```

<span data-ttu-id="7bec0-163">호출하는 함수가 배열을 `M`에 전달한 경우에는 배열 내용을 수정하는 `M` 메서드에서 다차원 배열을 반환할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-163">Returning a multi-dimensional array from a method, `M`, that modifies the array's contents is not necessary if the calling function passed the array into `M`.</span></span>  <span data-ttu-id="7bec0-164">좋은 스타일이나 값의 기능 흐름을 위해 `M`의 결과 배열을 반환할 수 있지만, C#에서는 모든 참조 형식을 값으로 전달하고 배열 참조의 값이 배열에 대한 포인터이기 때문에 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-164">You may return the resulting array from `M` for good style or functional flow of values, but it is not necessary because C# passes all reference types by value, and the value of an array reference is the pointer to the array.</span></span> <span data-ttu-id="7bec0-165">다음 예제와 같이 `M` 메서드의 배열 내용에 대한 변경 사항은 배열에 대한 참조가 있는 모든 코드에서 관찰할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-165">In the method `M`, any changes to the array's contents are observable by any code that has a reference to the array, as shown in the following example.</span></span>  
  
```csharp  
static void Main(string[] args)  
        {  
            int[,] matrix = new int[2, 2];  
            FillMatrix(matrix);  
            // matrix is now full of -1  
        }  
  
        public static void FillMatrix(int[,] matrix)  
        {  
            for (int i = 0; i < matrix.GetLength(0); i++)  
            {  
                for (int j = 0; j < matrix.GetLength(1); j++)  
                {  
                    matrix[i, j] = -1;  
                }  
            }  
        }  
```  
  
 <span data-ttu-id="7bec0-166">자세한 내용은 [return](../../../csharp/language-reference/keywords/return.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7bec0-166">For more information, see [return](../../../csharp/language-reference/keywords/return.md).</span></span>  
  
## <a name="async-methods"></a><span data-ttu-id="7bec0-167">비동기 메서드</span><span class="sxs-lookup"><span data-stu-id="7bec0-167">Async Methods</span></span>  
 <span data-ttu-id="7bec0-168">비동기 기능을 사용하면 명시적 콜백을 사용하거나 수동으로 여러 메서드 또는 람다 식에 코드를 분할하지 않고도 비동기 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-168">By using the async feature, you can invoke asynchronous methods without using explicit callbacks or manually splitting your code across multiple methods or lambda expressions.</span></span> 
  
 <span data-ttu-id="7bec0-169">메서드에 [async](../../../csharp/language-reference/keywords/async.md) 한정자를 표시하면 메서드에서 [await](../../../csharp/language-reference/keywords/await.md) 연산자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-169">If you mark a method with the [async](../../../csharp/language-reference/keywords/async.md) modifier, you can use the [await](../../../csharp/language-reference/keywords/await.md) operator in the method.</span></span> <span data-ttu-id="7bec0-170">컨트롤이 비동기 메서드의 await 식에 도달하면 컨트롤이 호출자로 돌아가고 대기 중인 작업이 완료될 때까지 메서드의 진행이 일시 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-170">When control reaches an await expression in the async method, control returns to the caller, and progress in the method is suspended until the awaited task completes.</span></span> <span data-ttu-id="7bec0-171">작업이 완료되면 메서드가 실행이 다시 시작될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-171">When the task is complete, execution can resume in the method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7bec0-172">비동기 메서드는 아직 완료되지 않은 첫 번째 대기된 개체를 검색할 때나 비동기 메서드의 끝에 도달할 때 중에서 먼저 발생하는 시점에 호출자에게 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-172">An async method returns to the caller when either it encounters the first awaited object that’s not yet complete or it gets to the end of the async method, whichever occurs first.</span></span>  
  
 <span data-ttu-id="7bec0-173">비동기 메서드의 반환 형식은 <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.Task>또는 void일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-173">An async method can have a return type of <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.Task>, or void.</span></span> <span data-ttu-id="7bec0-174">void 반환 형식은 기본적으로 void 반환 형식이 필요할 때 이벤트 처리기를 정의하는 데 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-174">The void return type is used primarily to define event handlers, where a void return type is required.</span></span> <span data-ttu-id="7bec0-175">void를 반환하는 비동기 메서드는 대기할 수 없고 void를 반환하는 메서드의 호출자는 메서드가 throw하는 예외를 catch할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-175">An async method that returns void can't be awaited, and the caller of a void-returning method can't catch exceptions that the method throws.</span></span>  
  
 <span data-ttu-id="7bec0-176">다음 예제에서 `DelayAsync` 는 반환 형식이 <xref:System.Threading.Tasks.Task%601>인 비동기 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-176">In the following example, `DelayAsync` is an async method that has a return type of <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="7bec0-177">`DelayAsync` 에는 정수를 반환하는 `return` 문이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-177">`DelayAsync` has a `return` statement that returns an integer.</span></span> <span data-ttu-id="7bec0-178">따라서 `DelayAsync` 의 메서드 선언의 반환 형식은 `Task<int>`여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-178">Therefore the method declaration of `DelayAsync` must have a return type of `Task<int>`.</span></span> <span data-ttu-id="7bec0-179">반환 형식이 `Task<int>`이므로 `await` 의 `DoSomethingAsync` 식 계산에서 다음 문과 같이 정수가 생성됩니다. `int result = await delayTask`.</span><span class="sxs-lookup"><span data-stu-id="7bec0-179">Because the return type is `Task<int>`, the evaluation of the `await` expression in `DoSomethingAsync` produces an integer as the following statement demonstrates: `int result = await delayTask`.</span></span>  
  
 <span data-ttu-id="7bec0-180">`startButton_Click` 메서드는 반환 형식이 void인 비동기 메서드의 한 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-180">The `startButton_Click` method is an example of an async method that has a return type of void.</span></span> <span data-ttu-id="7bec0-181">`DoSomethingAsync` 는 비동기 메서드이므로 다음 문과 같이 `DoSomethingAsync` 호출에 대한 작업을 기다려야 합니다. `await DoSomethingAsync();`.</span><span class="sxs-lookup"><span data-stu-id="7bec0-181">Because `DoSomethingAsync` is an async method, the task for the call to `DoSomethingAsync` must be awaited, as the following statement shows: `await DoSomethingAsync();`.</span></span> <span data-ttu-id="7bec0-182">`startButton_Click` 메서드에 `async` 식이 포함되므로 `await` 한정자를 사용하여 해당 메서드를 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-182">The `startButton_Click` method must be defined with the `async` modifier because the method has an `await` expression.</span></span>  
  
 [!code-csharp[csAsyncMethod#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/methods_9.cs)]  
  
 <span data-ttu-id="7bec0-183">비동기 메서드는 [ref](../../../csharp/language-reference/keywords/ref.md) 또는 [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) 매개 변수를 선언할 수 없지만, 이러한 매개 변수가 있는 메서드를 호출할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-183">An async method can't declare any [ref](../../../csharp/language-reference/keywords/ref.md) or [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) parameters, but it can call methods that have such parameters.</span></span>  
  
 <span data-ttu-id="7bec0-184">비동기 메서드에 대한 자세한 내용은 [async 및 await를 사용한 비동기 프로그래밍](../../../csharp/programming-guide/concepts/async/index.md), [비동기 프로그램의 제어 흐름](../../../csharp/programming-guide/concepts/async/control-flow-in-async-programs.md) 및 [비동기 반환 형식](../../../csharp/programming-guide/concepts/async/async-return-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7bec0-184">For more information about async methods, see [Asynchronous Programming with async and await](../../../csharp/programming-guide/concepts/async/index.md), [Control Flow in Async Programs](../../../csharp/programming-guide/concepts/async/control-flow-in-async-programs.md), and [Async Return Types](../../../csharp/programming-guide/concepts/async/async-return-types.md).</span></span>  
  
## <a name="expression-body-definitions"></a><span data-ttu-id="7bec0-185">식 본문 정의</span><span class="sxs-lookup"><span data-stu-id="7bec0-185">Expression Body Definitions</span></span>  
 <span data-ttu-id="7bec0-186">일반적으로 식의 결과와 함께 바로 반환되거나 단일 문이 메서드 본문으로 포함된 메서드 정의가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-186">It is common to have method definitions that simply return immediately with the result of an expression, or that have a single statement as the body of the method.</span></span>  <span data-ttu-id="7bec0-187">`=>`를 사용하여 해당 메서드를 속성을 정의하기 위한 구문 바로 가기는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-187">There is a syntax shortcut for defining such methods using `=>`:</span></span>  
  
```csharp  
public Point Move(int dx, int dy) => new Point(x + dx, y + dy);   
public void Print() => Console.WriteLine(First + " " + Last);  
// Works with operators, properties, and indexers too.  
public static Complex operator +(Complex a, Complex b) => a.Add(b);  
public string Name => First + " " + Last;   
public Customer this[long id] => store.LookupCustomer(id);  
```  
  
 <span data-ttu-id="7bec0-188">메서드가 `void` 를 반환하거나 비동기 메서드이면 메서드 본문은 문 식이어야 합니다(람다에서와 같음).</span><span class="sxs-lookup"><span data-stu-id="7bec0-188">If the method returns `void` or is an async method, then the body of the method must be a statement expression (same as with lambdas).</span></span>  <span data-ttu-id="7bec0-189">속성 및 인덱서의 경우 읽기 전용이어야 하며, `get` 접근자 키워드를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-189">For properties and indexers, they must be read only, and you don't use the `get` accessor keyword.</span></span>  
  
## <a name="iterators"></a><span data-ttu-id="7bec0-190">Iterators</span><span class="sxs-lookup"><span data-stu-id="7bec0-190">Iterators</span></span>  
 <span data-ttu-id="7bec0-191">반복기는 배열 목록과 같은 컬렉션에 대해 사용자 지정 반복을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-191">An iterator performs a custom iteration over a collection, such as a list or an array.</span></span> <span data-ttu-id="7bec0-192">반복기는 [yield return](../../../csharp/language-reference/keywords/yield.md) 문을 사용하여 각 요소를 따로따로 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-192">An iterator uses the [yield return](../../../csharp/language-reference/keywords/yield.md) statement to return each element one at a time.</span></span> <span data-ttu-id="7bec0-193">[yield return](../../../csharp/language-reference/keywords/yield.md) 문에 도달하면 코드의 현재 위치가 기억됩니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-193">When a [yield return](../../../csharp/language-reference/keywords/yield.md) statement is reached, the current location in code is remembered.</span></span> <span data-ttu-id="7bec0-194">다음에 반복기가 호출되면 해당 위치에서 실행이 다시 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-194">Execution is restarted from that location when the iterator is called the next time.</span></span>  
  
 <span data-ttu-id="7bec0-195">[foreach](../../../csharp/language-reference/keywords/foreach-in.md) 문을 사용하여 클라이언트 코드에서 반복기를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-195">You call an iterator from client code by using a [foreach](../../../csharp/language-reference/keywords/foreach-in.md) statement.</span></span>  
  
 <span data-ttu-id="7bec0-196">반복기의 반환 형식은 <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>또는 <xref:System.Collections.Generic.IEnumerator%601>일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bec0-196">The return type of an iterator can be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>  
  
 <span data-ttu-id="7bec0-197">자세한 내용은 [반복기](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7bec0-197">For more information, see [Iterators](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="7bec0-198">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="7bec0-198">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7bec0-199">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7bec0-199">See Also</span></span>  
 [<span data-ttu-id="7bec0-200">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="7bec0-200">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="7bec0-201">클래스 및 구조체</span><span class="sxs-lookup"><span data-stu-id="7bec0-201">Classes and Structs</span></span>](index.md)  
 [<span data-ttu-id="7bec0-202">액세스 한정자</span><span class="sxs-lookup"><span data-stu-id="7bec0-202">Access Modifiers</span></span>](access-modifiers.md)  
 [<span data-ttu-id="7bec0-203">정적 클래스 및 정적 클래스 멤버</span><span class="sxs-lookup"><span data-stu-id="7bec0-203">Static Classes and Static Class Members</span></span>](static-classes-and-static-class-members.md)  
 [<span data-ttu-id="7bec0-204">상속</span><span class="sxs-lookup"><span data-stu-id="7bec0-204">Inheritance</span></span>](inheritance.md)  
 [<span data-ttu-id="7bec0-205">추상/봉인된 클래스 및 클래스 멤버</span><span class="sxs-lookup"><span data-stu-id="7bec0-205">Abstract and Sealed Classes and Class Members</span></span>](abstract-and-sealed-classes-and-class-members.md)  
 [<span data-ttu-id="7bec0-206">params</span><span class="sxs-lookup"><span data-stu-id="7bec0-206">params</span></span>](../../../csharp/language-reference/keywords/params.md)  
 [<span data-ttu-id="7bec0-207">return</span><span class="sxs-lookup"><span data-stu-id="7bec0-207">return</span></span>](../../../csharp/language-reference/keywords/return.md)  
 [<span data-ttu-id="7bec0-208">out</span><span class="sxs-lookup"><span data-stu-id="7bec0-208">out</span></span>](../../../csharp/language-reference/keywords/out.md)  
 [<span data-ttu-id="7bec0-209">ref</span><span class="sxs-lookup"><span data-stu-id="7bec0-209">ref</span></span>](../../../csharp/language-reference/keywords/ref.md)  
 [<span data-ttu-id="7bec0-210">매개 변수 전달</span><span class="sxs-lookup"><span data-stu-id="7bec0-210">Passing Parameters</span></span>](passing-parameters.md)
