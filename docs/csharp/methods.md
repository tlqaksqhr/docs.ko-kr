---
title: 메서드 - C# 가이드
description: 메서드, 메서드 매개 변수 및 메서드 반환 값의 개요
keywords: .NET, .NET Core, C#
author: rpetrusha
ms.author: ronpet
ms.date: 10/26/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 577a8527-1081-4b36-9b9e-0685b6553c6e
ms.openlocfilehash: 526cd6d269c7c089f6547fcf243b43e411037d13
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="methods"></a><span data-ttu-id="1e356-104">메서드</span><span class="sxs-lookup"><span data-stu-id="1e356-104">Methods</span></span> #

<span data-ttu-id="1e356-105">메서드는 일련의 문을 포함하는 코드 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-105">A method is a code block that contains a series of statements.</span></span> <span data-ttu-id="1e356-106">프로그램을 통해 메서드를 호출하고 필요한 메서드 인수를 지정하여 문을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-106">A program causes the statements to be executed by calling the method and specifying any required method arguments.</span></span> <span data-ttu-id="1e356-107">C#에서는 실행된 모든 명령이 메서드의 컨텍스트에서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-107">In C#, every executed instruction is performed in the context of a method.</span></span> <span data-ttu-id="1e356-108">`Main` 메서드는 모든 C# 응용 프로그램의 진입점이고 프로그램이 시작될 때 CLR(공용 언어 런타임)에서 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-108">The `Main` method is the entry point for every C# application and it is called by the common language runtime (CLR) when the program is started.</span></span>

> [!NOTE]
> <span data-ttu-id="1e356-109">이 항목에서는 명명된 메서드에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-109">This topic discusses named methods.</span></span> <span data-ttu-id="1e356-110">익명 함수에 대한 자세한 내용은 [익명 함수](programming-guide/statements-expressions-operators/anonymous-functions.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1e356-110">For information about anonymous functions, see [Anonymous Functions](programming-guide/statements-expressions-operators/anonymous-functions.md).</span></span>

<span data-ttu-id="1e356-111">이 항목에는 다음과 같은 단원이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-111">This topic contains the following sections:</span></span>

- [<span data-ttu-id="1e356-112">메서드 시그니처</span><span class="sxs-lookup"><span data-stu-id="1e356-112">Method signatures</span></span>](#signatures)
- [<span data-ttu-id="1e356-113">메서드 호출</span><span class="sxs-lookup"><span data-stu-id="1e356-113">Method invocation</span></span>](#invocation)
- [<span data-ttu-id="1e356-114">상속 및 재정의된 메서드</span><span class="sxs-lookup"><span data-stu-id="1e356-114">Inherited and overridden methods</span></span>](#inherited)
- [<span data-ttu-id="1e356-115">매개 변수 전달</span><span class="sxs-lookup"><span data-stu-id="1e356-115">Passing parameters</span></span>](#passing)
  - [<span data-ttu-id="1e356-116">값으로 매개 변수 전달</span><span class="sxs-lookup"><span data-stu-id="1e356-116">Passing parameters by value</span></span>](#byval)
  - [<span data-ttu-id="1e356-117">참조로 매개 변수 전달</span><span class="sxs-lookup"><span data-stu-id="1e356-117">Passing parameters by reference</span></span>](#byref)
  - [<span data-ttu-id="1e356-118">매개 변수 배열</span><span class="sxs-lookup"><span data-stu-id="1e356-118">Parameter arrays</span></span>](#paramarray)
- [<span data-ttu-id="1e356-119">선택적 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="1e356-119">Optional parameters and arguments</span></span>](#optional)
- [<span data-ttu-id="1e356-120">반환 값</span><span class="sxs-lookup"><span data-stu-id="1e356-120">Return values</span></span>](#return)
- [<span data-ttu-id="1e356-121">확장 메서드</span><span class="sxs-lookup"><span data-stu-id="1e356-121">Extension methods</span></span>](#extension)
- [<span data-ttu-id="1e356-122">비동기 메서드</span><span class="sxs-lookup"><span data-stu-id="1e356-122">Async Methods</span></span>](#async)
- [<span data-ttu-id="1e356-123">식 본문 멤버</span><span class="sxs-lookup"><span data-stu-id="1e356-123">Expression-bodied members</span></span>](#expr)
- [<span data-ttu-id="1e356-124">반복기</span><span class="sxs-lookup"><span data-stu-id="1e356-124">Iterators</span></span>](#iterators)

<a name="signatures"></a>
## <a name="method-signatures"></a><span data-ttu-id="1e356-125">메서드 시그니처</span><span class="sxs-lookup"><span data-stu-id="1e356-125">Method signatures</span></span> ##

<span data-ttu-id="1e356-126">메서드는 다음을 지정하여 `class` 또는 `struct`에서 선언됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-126">Methods are declared in a `class` or `struct` by specifying:</span></span>

- <span data-ttu-id="1e356-127">`public` 또는 `private`와 같은 선택적 액세스 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-127">An optional access level, such as `public` or `private`.</span></span> <span data-ttu-id="1e356-128">기본값은 `private`입니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-128">The default is `private`.</span></span>
- <span data-ttu-id="1e356-129">`abstract` 또는 `sealed`와 같은 선택적 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-129">Optional modifiers such as `abstract` or `sealed`.</span></span>
- <span data-ttu-id="1e356-130">반환 값 또는 메서드에 반환 값이 없는 경우 `void`입니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-130">The return value, or `void` if the method has none.</span></span>
- <span data-ttu-id="1e356-131">메서드 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-131">The method name.</span></span>
- <span data-ttu-id="1e356-132">메서드 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-132">Any method parameters.</span></span> <span data-ttu-id="1e356-133">메서드 매개 변수는 괄호로 묶고 쉼표로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-133">Method parameters are enclosed in parentheses and are separated by commas.</span></span> <span data-ttu-id="1e356-134">빈 괄호는 메서드에 매개 변수가 필요하지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-134">Empty parentheses indicate that the method requires no parameters.</span></span>

<span data-ttu-id="1e356-135">이러한 부분이 결합되어 메서드 시그니처를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-135">These parts together form the method signature.</span></span>

> [!NOTE]
> <span data-ttu-id="1e356-136">메서드의 반환 값은 메서드 오버로드를 위한 메서드 서명의 부분이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-136">A return type of a method is not part of the signature of the method for the purposes of method overloading.</span></span> <span data-ttu-id="1e356-137">그러나 대리자와 대리자가 가리키는 메서드 간의 호환성을 결정할 경우에는 메서드 서명의 부분입니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-137">However, it is part of the signature of the method when determining the compatibility between a delegate and the method that it points to.</span></span>

<span data-ttu-id="1e356-138">다음 예제에서는 다섯 개의 메서드를 포함하는 `Motorcycle`이라는 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-138">The following example defines a class named `Motorcycle` that contains five methods:</span></span>

[!code-csharp[csSnippets.Methods#40](../../samples/snippets/csharp/concepts/methods/methods40.cs#40)]

<span data-ttu-id="1e356-139">`Motorcycle` 클래스에는 오버로드된 메서드 `Drive`가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-139">Note that the `Motorcycle` class includes an overloaded method, `Drive`.</span></span> <span data-ttu-id="1e356-140">두 메서드는 이름이 같지만 해당 매개 변수 형식으로 구별되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-140">Two methods have the same name, but must be differentiated by their parameter types.</span></span>

<a name="invocation"></a>
## <a name="method-invocation"></a><span data-ttu-id="1e356-141">메서드 호출</span><span class="sxs-lookup"><span data-stu-id="1e356-141">Method invocation</span></span> ##

<span data-ttu-id="1e356-142">메서드는 *인스턴스* 또는 *정적*일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-142">Methods can be either *instance* or *static*.</span></span> <span data-ttu-id="1e356-143">인스턴스 메서드를 호출하려면 개체를 인스턴스화하고 해당 개체에서 메서드를 호출해야 합니다. 인스턴스 메서드는 인스턴스 및 해당 데이터에 대해 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-143">Invoking an instance method requires that you instantiate an object and call the method on that object; an instance method operates on that instance and its data.</span></span> <span data-ttu-id="1e356-144">메서드가 속하는 형식의 이름을 참조하여 정적 메서드를 호출합니다. 정적 메서드는 인스턴스 데이터에 대해 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-144">You invoke a static method by referencing the name of the type to which the method belongs; static methods operate do not operate on instance data.</span></span> <span data-ttu-id="1e356-145">개체 인스턴스를 통해 정적 메서드를 호출하려고 하면 컴파일러 오류가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-145">Attempting to call a static method through an object instance generates a compiler error.</span></span>

<span data-ttu-id="1e356-146">메서드 호출은 필드 액세스와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-146">Calling a method is like accessing a field.</span></span> <span data-ttu-id="1e356-147">개체 이름(인스턴스 메서드를 호출하는 경우) 또는 형식 이름(`static` 메서드를 호출하는 경우) 뒤에 마침표, 메서드 이름 및 괄호를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-147">After the object name (if you are calling an instance method) or the type name (if you are calling a `static` method), add a period, the name of the method, and parentheses.</span></span> <span data-ttu-id="1e356-148">인수는 괄호 안에 나열되고 쉼표로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-148">Arguments are listed within the parentheses, and are separated by commas.</span></span>

<span data-ttu-id="1e356-149">메서드 정의는 필요한 모든 매개 변수의 이름 및 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-149">The method definition specifies the names and types of any parameters that are required.</span></span> <span data-ttu-id="1e356-150">호출자는 메서드를 호출할 때 각 매개 변수에 대해 인수라는 구체적인 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-150">When a caller invokes the method, it provides concrete values, called arguments, for each parameter.</span></span> <span data-ttu-id="1e356-151">인수는 매개 변수 형식과 호환되어야 하지만 인수 이름(호출하는 코드에 사용된 경우)은 메서드에 정의된 명명된 매개 변수와 동일할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-151">The arguments must be compatible with the parameter type, but the argument name, if one is used in the calling code, does not have to be the same as the parameter named defined in the method.</span></span> <span data-ttu-id="1e356-152">다음 예제에서는 `Square` 메서드에 *i*라는 `int` 형식의 단일 매개 변수가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-152">In the following example, the `Square` method includes a single parameter of type `int` named *i*.</span></span> <span data-ttu-id="1e356-153">첫 번째 메서드 호출은 `Square` 메서드에 *num*이라는 `int` 형식의 변수를 전달합니다. 두 번째 호출은 숫자 상수, 세 번째 호출은 식을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-153">The first method call passes the `Square` method a variable of type `int` named *num*; the second, a numeric constant; and the third, an expression.</span></span>

[!code-csharp[csSnippets.Methods#74](../../samples/snippets/csharp/concepts/methods/params74.cs#74)]

<span data-ttu-id="1e356-154">가장 일반적인 형태의 메서드 호출은 위치 인수를 사용하며, 메서드 매개 변수와 동일한 순서로 인수를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-154">The most common form of method invocation used positional arguments; it supplies arguments in the same order as method parameters.</span></span> <span data-ttu-id="1e356-155">`Motorcycle` 클래스의 메서드는 다음 예제와 같이 호출될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-155">The methods of the `Motorcycle` class can therefore be called as in the following example.</span></span> <span data-ttu-id="1e356-156">예를 들어 `Drive` 메서드 호출에는 메서드 구문의 두 매개 변수에 해당하는 두 개의 인수가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-156">The call to the `Drive` method, for example, includes two arguments that correspond to the two parameters in the method's syntax.</span></span> <span data-ttu-id="1e356-157">첫 번째 인수는 `miles` 매개 변수의 값이 되고, 두 번째 인수는 `speed` 매개 변수의 값이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-157">The first becomes the value of the `miles` parameter, the second the value of the `speed` parameter.</span></span>

[!code-csharp[csSnippets.Methods#41](../../samples/snippets/csharp/concepts/methods/methods40.cs#41)]

<span data-ttu-id="1e356-158">메서드를 호출할 때 위치 인수 대신 *명명된 인수*를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-158">You can also used *named arguments* instead of positional arguments when invoking a method.</span></span> <span data-ttu-id="1e356-159">명명된 인수를 사용하는 경우 매개 변수 이름 뒤에 콜론(":")과 인수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-159">When using named arguments, you specify the parameter name followed by a colon (":") and the argument.</span></span> <span data-ttu-id="1e356-160">모든 필수 인수가 있기만 하면 메서드의 인수 순서는 중요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-160">Arguments to the method can appear in any order, as long as all required arguments are present.</span></span> <span data-ttu-id="1e356-161">다음 예제에서는 명명된 인수를 사용하여 `TestMotorcycle.Drive` 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-161">The following example uses named arguments to invoke the `TestMotorcycle.Drive` method.</span></span> <span data-ttu-id="1e356-162">이 예제에서는 명명된 인수가 메서드의 매개 변수 목록과 반대 순서로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-162">In this example, the named arguments are passed in the opposite order from the method's parameter list.</span></span>

[!code-csharp[csSnippets.Methods#45](../../samples/snippets/csharp/concepts/methods/named1.cs#45)]

<span data-ttu-id="1e356-163">위치 인수와 명명된 인수 둘 다를 사용하여 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-163">You can invoke a method using both positional arguments and named arguments.</span></span> <span data-ttu-id="1e356-164">그러나 위치 인수는 명명된 인수 다음에 올 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-164">However, a positional argument cannot follow a named argument.</span></span> <span data-ttu-id="1e356-165">다음 예제에서는 위치 인수 하나와 명명된 인수 하나를 사용하여 이전 예제의 `TestMotorcycle.Drive` 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-165">The following example invokes the `TestMotorcycle.Drive` method from the previous example using one positional argument and one named argument.</span></span>

[!code-csharp[csSnippets.Methods#46](../../samples/snippets/csharp/concepts/methods/named2.cs#46)]

 <a name="inherited"></a>
 ##<a name="inherited-and-overridden-methods"></a><span data-ttu-id="1e356-166">상속 및 재정의된 메서드</span><span class="sxs-lookup"><span data-stu-id="1e356-166">Inherited and overridden methods</span></span> ##

<span data-ttu-id="1e356-167">형식은 해당 형식에서 명시적으로 정의된 멤버 외에도 기본 클래스에서 정의된 멤버를 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-167">In addition to the members that are explicitly defined in a type, a type inherits members defined in its base classes.</span></span> <span data-ttu-id="1e356-168">관리되는 형식 시스템의 모든 형식이 직접 또는 간접적으로 <xref:System.Object> 클래스에서 상속하므로 모든 형식은 <xref:System.Object.Equals(System.Object)>, <xref:System.Object.GetType> 및 <xref:System.Object.ToString>과 같은 해당 멤버를 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-168">Since all types in the managed type system inherit directly or indirectly from the <xref:System.Object> class, all types inherit its members, such as <xref:System.Object.Equals(System.Object)>, <xref:System.Object.GetType>, and <xref:System.Object.ToString>.</span></span> <span data-ttu-id="1e356-169">다음 예제에서는 `Person` 클래스를 정의하고, 두 개의 `Person` 개체를 인스턴스화하고, `Person.Equals` 메서드를 호출하여 두 개체가 같은지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-169">The following example defines a `Person` class, instantiates two `Person` objects, and calls the `Person.Equals` method to determine whether the two objects are equal.</span></span> <span data-ttu-id="1e356-170">그러나 `Equals` 메서드는 `Person` 클래스에서 정의되지 않고 <xref:System.Object>에서 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-170">The `Equals` method, however, is not defined in the `Person` class; it is inherited from <xref:System.Object>.</span></span>

[!code-csharp[csSnippets.Methods#104](../../samples/snippets/csharp/concepts/methods/inherited1.cs#104)]

<span data-ttu-id="1e356-171">형식은 `override` 키워드를 사용하고 재정의된 메서드에 대한 구현을 제공하여 상속된 멤버를 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-171">Types can override inherited members by using the `override` keyword and providing an implementation for the overridden method.</span></span> <span data-ttu-id="1e356-172">메서드 시그니처는 재정의된 메서드의 시그니처와 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-172">The method signature must be the same as that of the overridden method.</span></span> <span data-ttu-id="1e356-173">다음 예제는 <xref:System.Object.Equals(System.Object)> 메서드를 재정의한다는 점을 제외하고 이전 예제와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-173">The following example is like the previous one, except that it overrides the <xref:System.Object.Equals(System.Object)> method.</span></span> <span data-ttu-id="1e356-174">또한 두 메서드가 일치하는 결과를 제공하기 때문에 <xref:System.Object.GetHashCode> 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-174">(It also overrides the <xref:System.Object.GetHashCode> method, since the two methods are intended to provide consistent results.)</span></span>

[!code-csharp[csSnippets.Methods#105](../../samples/snippets/csharp/concepts/methods/overridden1.cs#105)]

<a name="passing"></a>
## <a name="passing-parameters"></a><span data-ttu-id="1e356-175">매개 변수 전달</span><span class="sxs-lookup"><span data-stu-id="1e356-175">Passing parameters</span></span> ##

<span data-ttu-id="1e356-176">C#의 형식은 *값 형식* 또는 *참조 형식*입니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-176">Types in C# are either *value types* or *reference types*.</span></span> <span data-ttu-id="1e356-177">기본 제공 값 형식 목록을 보려면 [형식 및 변수](./tour-of-csharp/types-and-variables.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1e356-177">For a list of built-in value types, see [Types and variables](./tour-of-csharp/types-and-variables.md).</span></span> <span data-ttu-id="1e356-178">기본적으로, 값 형식과 참조 형식은 둘 다 값으로 메서드에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-178">By default, both value types and reference types are passed to a method by value.</span></span>

<a name="byval"></a>
### <a name="passing-parameters-by-value"></a><span data-ttu-id="1e356-179">값으로 매개 변수 전달</span><span class="sxs-lookup"><span data-stu-id="1e356-179">Passing parameters by value</span></span> ###

<span data-ttu-id="1e356-180">값 형식이 값으로 메서드에 전달되는 경우 개체 자체가 아니라 개체의 복사본이 메서드에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-180">When a value type is passed to a method by value, a copy of the object instead of the object itself is passed to the method.</span></span> <span data-ttu-id="1e356-181">따라서 제어가 호출자로 반환될 때 호출된 메서드의 개체 변경 내용은 원래 개체에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-181">Therefore, changes to the object in the called method have no effect on the original object when control returns to the caller.</span></span>

<span data-ttu-id="1e356-182">다음 예제에서는 값 형식을 값으로 메서드에 전달하며, 호출된 메서드는 값 형식의 값을 변경하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-182">The following example passes a value type to a method by value, and the called method attempts to change the value type's value.</span></span> <span data-ttu-id="1e356-183">값 형식인 `int` 형식의 변수를 정의하고, 해당 값을 20으로 초기화한 다음 `ModifyValue`라는 메서드에 전달하면 이 메서드가 변수의 값을 30으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-183">It defines a variable of type `int`, which is a value type, initializes its value to 20, and passes it to a method named `ModifyValue` that changes the variable's value to 30.</span></span> <span data-ttu-id="1e356-184">그러나 메서드가 반환될 때는 변수의 값이 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-184">When the method returns, however, the variable's value remains unchanged.</span></span>

[!code-csharp[csSnippets.Methods#10](../../samples/snippets/csharp/concepts/methods/byvalue10.cs#10)]

<span data-ttu-id="1e356-185">참조 형식의 개체가 메서드에 값으로 전달되는 경우 개체에 대한 참조가 값으로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-185">When an object of a reference type is passed to a method by value, a reference to the object is passed by value.</span></span> <span data-ttu-id="1e356-186">즉, 메서드는 개체 자체가 아니라 개체의 위치를 나타내는 인수를 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-186">That is, the method receives not the object itself, but an argument that indicates the location of the object.</span></span> <span data-ttu-id="1e356-187">이 참조를 사용하여 개체의 멤버를 변경하는 경우 제어가 호출하는 메서드로 반환될 때 변경 내용이 개체에 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-187">If you change a member of the object by using this reference, the change is reflected in the object when control returns to the calling method.</span></span> <span data-ttu-id="1e356-188">그러나 메서드에 전달되는 개체를 바꾸면 제어가 호출자로 반환될 때 원래 개체에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-188">However, replacing the object passed to the method has no effect on the original object when control returns to the caller.</span></span>

<span data-ttu-id="1e356-189">다음 예제에서는 `SampleRefType`이라는 클래스(참조 형식)를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-189">The following example defines a class (which is a reference type) named `SampleRefType`.</span></span> <span data-ttu-id="1e356-190">`SampleRefType` 개체를 인스턴스화하고, 해당 `value` 필드에 44를 할당한 다음 개체를 `ModifyObject` 메서드에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-190">It instantiates a `SampleRefType` object, assigns 44 to its `value` field, and passes the object to the `ModifyObject` method.</span></span> <span data-ttu-id="1e356-191">이 예제는 인수를 값으로 메서드에 전달한다는 점에서 기본적으로 이전 예제와 같은 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-191">This example does essentially the same thing as the previous example -- it passes an argument by value to a method.</span></span> <span data-ttu-id="1e356-192">그러나 참조 형식이 사용되므로 결과가 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-192">But because a reference type is used, the result is different.</span></span> <span data-ttu-id="1e356-193">예제의 출력과 같이 `ModifyObject`에서 `obj.value` 필드에 대해 수정한 내용으로 인해 `Main` 메서드에서 `rt` 인수의 `value` 필드도 33으로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-193">The modification that is made in `ModifyObject` to the `obj.value` field also changes the `value` field of the argument, `rt`, in the `Main` method to 33, as the output from the example shows.</span></span>

[!code-csharp[csSnippets.Methods#42](../../samples/snippets/csharp/concepts/methods/byvalue42.cs#42)]

<a name="byref"></a>
### <a name="passing-parameters-by-reference"></a><span data-ttu-id="1e356-194">참조로 매개 변수 전달</span><span class="sxs-lookup"><span data-stu-id="1e356-194">Passing parameters by reference</span></span> ###

<span data-ttu-id="1e356-195">메서드의 인수 값을 변경하고 제어가 호출하는 메서드로 반환될 때 해당 변경 내용을 반영하려는 경우 참조로 매개 변수를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-195">You pass a parameter by reference when you want to change the value of an argument in a method and want to refect that change when control returns to the calling method.</span></span> <span data-ttu-id="1e356-196">참조로 매개 변수를 전달하려면 [`ref`](language-reference/keywords/ref.md) 또는 [`out`](language-reference/keywords/out-parameter-modifier.md) 키워드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-196">To pass a parameter by reference, you use the [`ref`](language-reference/keywords/ref.md) or [`out`](language-reference/keywords/out-parameter-modifier.md) keyword.</span></span> <span data-ttu-id="1e356-197">복사를 방지하지만 여전히 [`in`](language-reference/keywords/in-parameter-modifier.md) 키워드를 사용하여 수정을 방지하도록 참조로 값을 전달할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-197">You can also pass a value by reference to avoid copying but still prevent modifications using the [`in`](language-reference/keywords/in-parameter-modifier.md) keyword.</span></span>

<span data-ttu-id="1e356-198">다음 예제는 값이 참조로 `ModifyValue` 메서드에 전달된다는 점을 제외하고 이전 예제와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-198">The following example is identical to the previous one, except the value is passed by reference to the `ModifyValue` method.</span></span> <span data-ttu-id="1e356-199">`ModifyValue` 메서드에서 매개 변수의 값을 수정하면 제어가 호출자로 반환될 때 값의 변경 내용이 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-199">When the value of the parameter is modified in the `ModifyValue` method, the change in value is reflected when control returns to the caller.</span></span>

[!code-csharp[csSnippets.Methods#106](../../samples/snippets/csharp/concepts/methods/byref106.cs#106)]

<span data-ttu-id="1e356-200">by ref 매개 변수를 사용하는 일반적인 패턴은 변수 값의 교환을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-200">A common pattern that uses by ref parameters involves swapping the values of variables.</span></span> <span data-ttu-id="1e356-201">두 개의 변수를 참조로 메서드에 전달하고 메서드가 해당 내용을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-201">You pass two variables to a method by reference, and the method swaps their contents.</span></span> <span data-ttu-id="1e356-202">다음 예제에서는 정수 값을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-202">The following example swaps integer values.</span></span>

[!code-csharp[csSnippets.Methods#106](../../samples/snippets/csharp/concepts/methods/swap107.cs#107)]

<span data-ttu-id="1e356-203">참조 형식 매개 변수를 전달하면 해당 개별 요소 또는 필드의 값이 아니라 참조 자체의 값을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-203">Passing a reference-type parameter allows you to change the value of the reference itself, rather than the value of its individual elements or fields.</span></span>

<a name="paramarray"></a>
### <a name="parameter-arrays"></a><span data-ttu-id="1e356-204">매개 변수 배열</span><span class="sxs-lookup"><span data-stu-id="1e356-204">Parameter arrays</span></span> ###

<span data-ttu-id="1e356-205">경우에 따라 메서드의 인수 개수를 정확하게 지정하라는 요구 사항은 제한적입니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-205">Sometimes, the requirement that you specify the exact number of arguments to your method is restrictive.</span></span> <span data-ttu-id="1e356-206">`params` 키워드를 사용하여 매개 변수를 매개 변수 배열로 지정하면 가변 개수의 인수로 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-206">By using the `params` keyword to indicate that a parameter is a parameter array, you allow your method to be called with a variable number of arguments.</span></span> <span data-ttu-id="1e356-207">`params` 키워드로 태그가 지정된 매개 변수는 배열 형식이어야 하며, 메서드의 매개 변수 목록에서 마지막 매개 변수여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-207">The parameter tagged with the `params` keyword must must be an array type, and it must be the last parameter in the method's parameter list.</span></span>

<span data-ttu-id="1e356-208">그러면 호출자가 다음 세 가지 방법 중 하나로 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-208">A caller can then invoke the method in either of three ways:</span></span>

- <span data-ttu-id="1e356-209">원하는 개수의 요소를 포함하는 적절한 형식의 배열 전달</span><span class="sxs-lookup"><span data-stu-id="1e356-209">By passing an array of the appropriate type that contains the desired number of elements.</span></span>
- <span data-ttu-id="1e356-210">적절한 형식의 개별 인수가 포함된 쉼표로 구분된 목록을 메서드에 전달</span><span class="sxs-lookup"><span data-stu-id="1e356-210">By passing a comma-separated list of individual arguments of the appropriate type to the method.</span></span>
- <span data-ttu-id="1e356-211">매개 변수 배열에 인수 제공 안 함</span><span class="sxs-lookup"><span data-stu-id="1e356-211">By not providing an argument to the parameter array.</span></span>

<span data-ttu-id="1e356-212">다음 예제에서는 첫 번째 매개 변수인 `StringOperation` 열거형 멤버에 지정된 문자열 작업을 수행하는 `DoStringOperation` 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-212">The following example defines a method named `DoStringOperation` that performs the string operation specified by its first parameter, a `StringOperation` enumeration member.</span></span> <span data-ttu-id="1e356-213">작업을 수행하는 대상 문자열은 매개 변수 배열에 의해 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-213">The strings upon which it is to perform the operation are defined by a parameter array.</span></span> <span data-ttu-id="1e356-214">`Main` 메서드는 해당 메서드를 호출하는 세 가지 방법을 모두 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-214">The `Main` method illustrates all three ways of invoking the method.</span></span> <span data-ttu-id="1e356-215">`params` 키워드로 태그가 지정된 메서드는 매개 변수 배열에 대한 인수가 제공되지 않은 경우 해당 값을 `null`로 처리하도록 준비해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-215">Note that the method tagged with the `params` keyword must be prepared to handle the case in which no argument is supplied for the parameter array, so that its value is `null`.</span></span>

[!code-csharp[csSnippets.Methods#106](../../samples/snippets/csharp/concepts/methods/byref108.cs#108)]

<a name="optional"></a>
## <a name="optional-parameters-and-arguments"></a><span data-ttu-id="1e356-216">선택적 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="1e356-216">Optional parameters and arguments</span></span> ##

<span data-ttu-id="1e356-217">메서드 정의에서 해당 매개 변수를 필수 또는 선택 사항으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-217">A method definition can specify that its parameters are required or that they are optional.</span></span> <span data-ttu-id="1e356-218">기본적으로 매개 변수는 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-218">By default, parameters are required.</span></span> <span data-ttu-id="1e356-219">선택적 매개 변수는 메서드 정의에 매개 변수의 기본값을 포함하여 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-219">Optional parameters are specified by including the parameter's default value in the method definition.</span></span> <span data-ttu-id="1e356-220">메서드를 호출할 때 선택적 매개 변수에 대한 인수가 제공되지 않은 경우 기본값이 대신 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-220">When the method is called, if no argument is supplied for an optional parameter, the default value is used instead.</span></span>

<span data-ttu-id="1e356-221">다음 종류의 식 중 하나로 매개 변수의 기본값을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-221">The parameter's default value must be assigned by one of the following kinds of expressions:</span></span>

- <span data-ttu-id="1e356-222">리터럴 문자열이나 숫자와 같은 상수</span><span class="sxs-lookup"><span data-stu-id="1e356-222">A constant, such as a literal string or number.</span></span>
- <span data-ttu-id="1e356-223">`new ValType` 형태의 식. 여기서 `ValType`은 값 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-223">An expression of the form `new ValType`, where `ValType` is a value type.</span></span> <span data-ttu-id="1e356-224">이 경우 형식의 실제 멤버가 아닌 값 형식의 암시적 기본 생성자가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-224">Note that this invokes the value type's implicit default constructor, which is not an actual member of the type.</span></span>
- <span data-ttu-id="1e356-225">`default(ValType)` 형태의 식. 여기서 `ValType`은 값 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-225">An expression of the form `default(ValType)`, where `ValType` is a value type.</span></span>

<span data-ttu-id="1e356-226">메서드에 필수 및 선택적 매개 변수가 둘 다 포함된 경우 선택적 매개 변수는 매개 변수 목록의 끝에서 모든 필수 매개 변수 다음에 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-226">If a method includes both required and optional parameters, optional parameters are defined at the end of the parameter list, after all required parameters.</span></span>

<span data-ttu-id="1e356-227">다음 예제에서는 필수 매개 변수 하나와 선택적 매개 변수 두 개가 있는 `ExampleMethod` 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-227">The following example defines a method, `ExampleMethod`, that has one required and two optional parameters.</span></span>

[!code-csharp[csSnippets.Methods#21](../../samples/snippets/csharp/concepts/methods/optional1.cs#21)]

<span data-ttu-id="1e356-228">여러 선택적 인수가 있는 메서드를 위치 인수로 호출하는 경우 호출자가 첫 번째 매개 변수부터 인수가 제공되는 마지막 매개 변수까지 모든 선택적 매개 변수에 대한 인수를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-228">If a method with multiple optional arguments is invoked using positional arguments, the caller must supply an argument for all optional parameters from the first one to the last one for which an argument is supplied.</span></span> <span data-ttu-id="1e356-229">예를 들어 `ExampleMethod` 메서드에서 호출자가 `description` 매개 변수에 대한 인수를 제공하는 경우 `optionalInt` 매개 변수에 대한 인수도 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-229">In the case of the  `ExampleMethod` method, for example, if the caller supplies an argument for the `description` parameter, it must also supply one for the `optionalInt` parameter.</span></span> <span data-ttu-id="1e356-230">`opt.ExampleMethod(2, 2, "Addition of 2 and 2");`는 유효한 메서드 호출이고, `opt.ExampleMethod(2, , "Addition of 2 and 0);`은 "인수가 없습니다." 컴파일러 오류를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-230">`opt.ExampleMethod(2, 2, "Addition of 2 and 2");` is a valid method call; `opt.ExampleMethod(2, , "Addition of 2 and 0);` generates an "Argument missing" compiler error.</span></span>

<span data-ttu-id="1e356-231">명명된 인수 또는 위치 인수와 명명된 인수의 조합을 사용하여 메서드를 호출하는 경우 호출자는 메서드 호출에서 마지막 위치 인수 뒤에 오는 모든 인수를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-231">If a method is called using named arguments or a combination of positional and named arguments, the caller can omit any arguments that follow the last positional argument in the method call.</span></span>

<span data-ttu-id="1e356-232">다음 예제에서는 `ExampleMethod` 메서드를 세 번 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-232">The following example calls the `ExampleMethod` method three times.</span></span>  <span data-ttu-id="1e356-233">처음 두 메서드 호출은 위치 인수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-233">The first two method calls use positional arguments.</span></span> <span data-ttu-id="1e356-234">첫 번째 호출은 선택적 인수를 둘 다 생략하고, 두 번째 호출은 마지막 인수를 생략합니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-234">The first omits both optional arguments, while the second omits the last argument.</span></span> <span data-ttu-id="1e356-235">세 번째 메서드 호출은 필수 매개 변수에 대한 위치 인수를 제공하지만 `optionalInt` 인수를 생략하고 명명된 인수를 사용하여 `description` 매개 변수에 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-235">The third method call supplies a positional argument for the required parameter, but uses a named argument to supply a value to the `description` parameter while omitting the `optionalInt` argument.</span></span>

[!code-csharp[csSnippets.Methods#22](../../samples/snippets/csharp/concepts/methods/optional1.cs#22)]

<span data-ttu-id="1e356-236">선택적 매개 변수를 사용하면 *오버로드 확인* 또는 C# 컴파일러가 메서드 호출에서 호출해야 하는 특정 오버로드를 확인하는 방법이 다음과 같이 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-236">The use of optional parameters affects *overload resolution*, or the way in which the C# compiler determines which particular overload should be invoked by a method call, as follows:</span></span>

- <span data-ttu-id="1e356-237">메서드, 인덱서 또는 생성자는 해당 매개 변수가 각각 선택 사항이거나 이름 또는 위치로 호출하는 문의 단일 인수에 해당하고 이 인수를 매개 변수의 형식으로 변환할 수 있는 경우 실행 후보가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-237">A method, indexer, or constructor is a candidate for execution if each of its parameters either is optional or corresponds, by name or by position, to a single argument in the calling statement, and that argument can be converted to the type of the parameter.</span></span>
- <span data-ttu-id="1e356-238">둘 이상의 인증서가 있으면 기본 설정 변환에 대한 오버로드 확인 규칙이 명시적으로 지정된 인수에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-238">If more than one candidate is found, overload resolution rules for preferred conversions are applied to the arguments that are explicitly specified.</span></span> <span data-ttu-id="1e356-239">선택적 매개 변수에 대해 생략된 인수는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-239">Omitted arguments for optional parameters are ignored.</span></span>
- <span data-ttu-id="1e356-240">두 후보가 똑같이 정상이라고 판단되는 경우 기본적으로 호출에서 인수가 생략된 선택적 매개 변수가 없는 후보가 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-240">If two candidates are judged to be equally good, preference goes to a candidate that does not have optional parameters for which arguments were omitted in the call.</span></span> <span data-ttu-id="1e356-241">이는 매개 변수가 적은 후보에 대한 오버로드 확인에서 일반적인 기본 설정의 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-241">This is a consequence of a general preference in overload resolution for candidates that have fewer parameters.</span></span>

 <a name="return"></a>
 ## <a name="return-values"></a><span data-ttu-id="1e356-242">반환 값</span><span class="sxs-lookup"><span data-stu-id="1e356-242">Return values</span></span> ##

<span data-ttu-id="1e356-243">메서드는 호출자에 값을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-243">Methods can return a value to the caller.</span></span> <span data-ttu-id="1e356-244">메서드 이름 앞에 나열된 반환 형식이 `void`가 아니면 메서드는 `return` 키워드를 사용하여 값을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-244">If the return type (the type listed before the method name) is not `void`, the method can return the value by using the `return` keyword.</span></span> <span data-ttu-id="1e356-245">`return` 키워드에 이어 반환 형식과 일치하는 변수, 상수 또는 식을 포함하는 문은 메서드 호출자에 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-245">A statement with the `return` keyword followed by a variable, constant, or expression that matches the return type will return that value to the method caller.</span></span> <span data-ttu-id="1e356-246">`return` 키워드를 사용하여 값을 반환하려면 void가 아닌 반환 값을 포함한 메서드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-246">Methods with a non-void return type are required to use the `return` keyword to return a value.</span></span> <span data-ttu-id="1e356-247">`return` 키워드는 메서드 실행을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-247">The `return` keyword also stops the execution of the method.</span></span>

<span data-ttu-id="1e356-248">반환 형식이 `void`이면 값이 없는 `return` 문을 사용하여 메서드 실행을 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-248">If the return type is `void`, a `return` statement without a value is still useful to stop the execution of the method.</span></span> <span data-ttu-id="1e356-249">`return` 키워드를 사용하지 않으면 메서드는 코드 블록 끝에 도달할 때 실행을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-249">Without the `return` keyword, the method will stop executing when it reaches the end of the code block.</span></span>

<span data-ttu-id="1e356-250">예를 들어 이들 두 메서드에서는 `return` 키워드를 사용하여 정수를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-250">For example, these two methods use the `return` keyword to return integers:</span></span>

[!code-csharp[csSnippets.Methods#44](../../samples/snippets/csharp/concepts/methods/return44.cs#44)]

<span data-ttu-id="1e356-251">메서드에서 반환된 값을 사용하려면 호출하는 메서드에서 같은 형식의 값으로 충분한 모든 경우에 메서드 호출 자체를 사용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-251">To use a value returned from a method, the calling method can use the method call itself anywhere a value of the same type would be sufficient.</span></span> <span data-ttu-id="1e356-252">반환 값을 변수에 할당할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-252">You can also assign the return value to a variable.</span></span> <span data-ttu-id="1e356-253">예를 들어 다음 두 코드 예제에서는 같은 목표를 달성합니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-253">For example, the following two code examples accomplish the same goal:</span></span>

[!code-csharp[csSnippets.Methods#45](../../samples/snippets/csharp/concepts/methods/return44.cs#45)]

[!code-csharp[csSnippets.Methods#46](../../samples/snippets/csharp/concepts/methods/return44.cs#46)]

<span data-ttu-id="1e356-254">지역 변수(이 경우 `result`)를 사용하여 값을 저장하는 것은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-254">Using a local variable, in this case, `result`, to store a value is optional.</span></span> <span data-ttu-id="1e356-255">코드의 가독성에 도움이 될 수 있고 전체 메서드 범위에 대해 인수의 원래 값을 저장해야 할 경우 필요할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-255">It may help the readability of the code, or it may be necessary if you need to store the original value of the argument for the entire scope of the method.</span></span>

<span data-ttu-id="1e356-256">메서드에서 둘 이상의 값을 반환하려는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-256">Sometimes, you want your method to return more than a single value.</span></span> <span data-ttu-id="1e356-257">C# 7.0부터 *튜플 형식* 및 *튜플 리터럴*을 사용하면 이 작업을 쉽게 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-257">Starting with C# 7.0, you can do this easily by using *tuple types* and *tuple literals*.</span></span> <span data-ttu-id="1e356-258">튜플 형식은 튜플 요소의 데이터 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-258">The tuple type defines the data types of the tuple's elements.</span></span> <span data-ttu-id="1e356-259">튜플 리터럴은 반환된 튜플의 실제 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-259">Tuple literals provide the actual values of the returned tuple.</span></span> <span data-ttu-id="1e356-260">다음 예제에서 `(string, string, string, int)`는 `GetPersonalInfo` 메서드에서 반환되는 튜플 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-260">In the following example, `(string, string, string, int)` defines the tuple type that is returned by the `GetPersonalInfo` method.</span></span> <span data-ttu-id="1e356-261">`(per.FirstName, per.MiddleName, per.LastName, per.Age)` 식은 튜플 리터럴입니다. 메서드는 `PersonInfo` 개체와 함께 이름, 중간 이름 및 성을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-261">The expression `(per.FirstName, per.MiddleName, per.LastName, per.Age)` is the tuple literal; the method returns the first, middle, and last name, along with the age, of a `PersonInfo` object.</span></span>

```csharp
public (string, string, string, int) GetPersonalInfo(string id)
{
    PersonInfo per = PersonInfo.RetrieveInfoById(id);
    if (per != null)
       return (per.FirstName, per.MiddleName, per.LastName, per.Age);
    else
       return null;
}
```

<span data-ttu-id="1e356-262">호출자는 반환된 튜플을 코드에서 다음과 같이 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-262">The caller can then consume the returned tuple with code like the following:</span></span>

```csharp
var person = GetPersonalInfo("111111111")
if (person != null)
   Console.WriteLine("{person.Item1} {person.Item3}: age = {person.Item4}");
```

<span data-ttu-id="1e356-263">튜플 형식 정의의 튜플 요소에 이름을 할당할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-263">Names can also be assigned to the tuple elements in the tuple type definition.</span></span> <span data-ttu-id="1e356-264">다음 예제에서는 명명된 요소를 사용하는 `GetPersonalInfo` 메서드의 대체 버전을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-264">The following example shows an alternate version of the `GetPersonalInfo` method that uses named elements:</span></span>

```csharp
public (string FName, string MName, string LName, int Age) GetPersonalInfo(string id)
{
    PersonInfo per = PersonInfo.RetrieveInfoById(id);
    if (per != null)
       return (per.FirstName, per.MiddleName, per.LastName, per.Age);
    else
       return null;
}
```

<span data-ttu-id="1e356-265">`GetPersonInfo` 메서드에 대한 이전 호출을 다음과 같이 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-265">The previous call to the `GetPersonInfo` method can then be modified as follows:</span></span>

```csharp
var person = GetPersonalInfo("111111111");
if (person != null)
   Console.WriteLine("{person.FName} {person.LName}: age = {person.Age}");
```

<span data-ttu-id="1e356-266">메서드에 배열이 인수로 전달되고 메서드가 개별 요소의 값을 수정하는 경우 값의 스타일 또는 기능 흐름 개선을 위해 메서드에서 배열을 반환하도록 선택할 수도 있지만 필수는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-266">If a method is passed an array as an argument and modifies the value of individual elements, it is not necessary for the method to return the array, although you may choose to do so for good style or functional flow of values.</span></span>  <span data-ttu-id="1e356-267">이는 C#에서 모든 참조 형식을 값으로 전달하고 배열 참조의 값이 배열에 대한 포인터이기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-267">This is because C# passes all reference types by value, and the value of an array reference is the pointer to the array.</span></span> <span data-ttu-id="1e356-268">다음 예제에서는 `DoubleValues` 메서드에서 수행한 `values` 배열 내용의 변경 사항을 배열에 대한 참조가 있는 모든 코드에서 관찰할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-268">In the following example, changes to the contents of the `values` array that are made in the `DoubleValues` method are observable by any code that has a reference to the array.</span></span>

[!code-csharp[csSnippets.Methods#101](../../samples/snippets/csharp/concepts/methods/returnarray1.cs#101)]

 <a name="exten"></a>
 ## <a name="extension-methods"></a><span data-ttu-id="1e356-269">확장 메서드</span><span class="sxs-lookup"><span data-stu-id="1e356-269">Extension methods</span></span> ##

<span data-ttu-id="1e356-270">일반적으로 기존 형식에 메서드를 추가하는 방법에는 다음 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-270">Ordinarily, there are two ways to add a method to an existing type:</span></span>

- <span data-ttu-id="1e356-271">해당 형식에 대한 소스 코드를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-271">Modify the source code for that type.</span></span> <span data-ttu-id="1e356-272">물론, 형식의 소스 코드를 소유하지 않은 경우에는 이 작업을 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-272">You cannot do this, of course, if you do not own the type's source code.</span></span> <span data-ttu-id="1e356-273">이는 메서드를 지원하기 위해 전용 데이터 필드를 추가하는 경우에도 주요 변경 내용이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-273">And this becomes a breaking change if you also add any private data fields to support the method.</span></span>
- <span data-ttu-id="1e356-274">파생 클래스에서 새 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-274">Define the new method in a derived class.</span></span> <span data-ttu-id="1e356-275">구조체, 열거형 등의 다른 형식에 대해 상속을 사용하여 이러한 방식으로 메서드를 추가할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-275">A method cannot be added in this way using inheritance for other types, such as structures and enumerations.</span></span> <span data-ttu-id="1e356-276">봉인 클래스에 메서드를 "추가"하는 데 사용할 수도 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-276">Nor can it be used to "add" a method to a sealed class.</span></span>

<span data-ttu-id="1e356-277">확장 메서드를 사용하면 형식 자체를 수정하거나 상속된 형식에서 새 메서드를 구현하지 않고 기존 형식에 메서드를 "추가"할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-277">Extension methods let you "add" a method to an existing type without modifying the type itself or implementing the new method in an inherited type.</span></span> <span data-ttu-id="1e356-278">또한 확장 메서드는 확장하는 형식과 동일한 어셈블리에 있지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-278">The extension method also does not have to reside in the same assembly as the type it extends.</span></span> <span data-ttu-id="1e356-279">형식의 정의된 멤버인 것처럼 확장 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-279">You call an extension method as if it were a defined member of a type.</span></span>

<span data-ttu-id="1e356-280">자세한 내용은 [확장 메서드](programming-guide/classes-and-structs/extension-methods.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1e356-280">For more information, see [Extension Methods](programming-guide/classes-and-structs/extension-methods.md).</span></span>

<a name="async"></a>
## <a name="async-methods"></a><span data-ttu-id="1e356-281">비동기 메서드</span><span class="sxs-lookup"><span data-stu-id="1e356-281">Async Methods</span></span> ##

<span data-ttu-id="1e356-282">비동기 기능을 사용하면 명시적 콜백을 사용하거나 수동으로 여러 메서드 또는 람다 식에 코드를 분할하지 않고도 비동기 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-282">By using the async feature, you can invoke asynchronous methods without using explicit callbacks or manually splitting your code across multiple methods or lambda expressions.</span></span>

<span data-ttu-id="1e356-283">메서드에 [async](language-reference/keywords/async.md) 한정자를 표시하면 메서드에서 [await](language-reference/keywords/await.md) 연산자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-283">If you mark a method with the [async](language-reference/keywords/async.md) modifier, you can use the [await](language-reference/keywords/await.md) operator in the method.</span></span> <span data-ttu-id="1e356-284">제어가 비동기 메서드의 `await` 식에 도달하면 대기된 작업이 완료되지 않은 경우 제어가 호출자로 반환되고, 대기된 작업이 완료될 때까지 `await` 키워드가 있는 메서드의 진행이 일시 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-284">When control reaches an `await` expression in the async method, control returns to the caller if the awaited task is not completed, and progress in the method with the `await` keyword is suspended until the awaited task completes.</span></span> <span data-ttu-id="1e356-285">작업이 완료되면 메서드가 실행이 다시 시작될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-285">When the task is complete, execution can resume in the method.</span></span>

> [!NOTE]
> <span data-ttu-id="1e356-286">비동기 메서드는 아직 완료되지 않은 첫 번째 대기된 개체를 검색할 때나 비동기 메서드의 끝에 도달할 때 중에서 먼저 발생하는 시점에 호출자에게 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-286">An async method returns to the caller when either it encounters the first awaited object that’s not yet complete or it gets to the end of the async method, whichever occurs first.</span></span>

<span data-ttu-id="1e356-287">비동기 메서드의 반환 형식은 <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.Task> 또는 `void`일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-287">An async method can have a return type of <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.Task>, or `void`.</span></span> <span data-ttu-id="1e356-288">`void` 반환 형식은 기본적으로 `void` 반환 형식이 필요할 때 이벤트 처리기를 정의하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-288">The `void` return type is used primarily to define event handlers, where a `void` return type is required.</span></span> <span data-ttu-id="1e356-289">`void`를 반환하는 비동기 메서드는 대기할 수 없고 void를 반환하는 메서드의 호출자는 메서드가 throw하는 예외를 catch할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-289">An async method that returns `void` can't be awaited, and the caller of a void-returning method can't catch exceptions that the method throws.</span></span> <span data-ttu-id="1e356-290">C# 7.0이 릴리스되면 비동기 메서드가 [작업과 유사한 형식을 반환](https://github.com/ljw1004/roslyn/blob/features/async-return/docs/specs/feature%20-%20arbitrary%20async%20returns.md)할 수 있도록 이 제한이 완화됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-290">C# 7.0, when it is released, will ease this restriction to allow an async method [to return any task-like type](https://github.com/ljw1004/roslyn/blob/features/async-return/docs/specs/feature%20-%20arbitrary%20async%20returns.md).</span></span>

<span data-ttu-id="1e356-291">다음 예제에서 `DelayAsync`는 정수를 반환하는 return 문을 포함하는 비동기 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-291">In the following example, `DelayAsync` is an async method that has a return statement that returns an integer.</span></span> <span data-ttu-id="1e356-292">비동기 메서드이기 때문에 해당 메서드 선언의 반환 형식은 `Task<int>`여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-292">Because it is an async method, its method declaration must have a return type of `Task<int>`.</span></span> <span data-ttu-id="1e356-293">반환 형식이 `Task<int>`이므로 `DoSomethingAsync`의 `await` 식 계산에서 다음 `int result = await delayTask` 문과 같이 정수가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-293">Because the return type is `Task<int>`, the evaluation of the `await` expression in `DoSomethingAsync` produces an integer, as the following `int result = await delayTask` statement demonstrates.</span></span>

[!code-csharp[csSnippets.Methods#102](../../samples/snippets/csharp/concepts/methods/async1.cs#102)]

<span data-ttu-id="1e356-294">비동기 메서드는 모든 [in](language-reference/keywords/in-parameter-modifier.md), [ref](language-reference/keywords/ref.md) 또는 [out](language-reference/keywords/out-parameter-modifier.md) 매개 변수를 선언할 수 없지만, 이러한 매개 변수가 있는 메서드를 호출할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-294">An async method can't declare any [in](language-reference/keywords/in-parameter-modifier.md), [ref](language-reference/keywords/ref.md), or [out](language-reference/keywords/out-parameter-modifier.md) parameters, but it can call methods that have such parameters.</span></span>

 <span data-ttu-id="1e356-295">비동기 메서드에 대한 자세한 내용은 [Async 및 Await를 사용한 비동기 프로그래밍](async.md), [비동기 프로그램의 제어 흐름](programming-guide/concepts/async/control-flow-in-async-programs.md) 및 [비동기 반환 형식](programming-guide/concepts/async/async-return-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1e356-295">For more information about async methods, see [Asynchronous Programming with Async and Await](async.md), [Control Flow in Async Programs](programming-guide/concepts/async/control-flow-in-async-programs.md), and [Async Return Types](programming-guide/concepts/async/async-return-types.md).</span></span>

<a name="expr"></a>
## <a name="expression-bodied-members"></a><span data-ttu-id="1e356-296">식 본문 멤버</span><span class="sxs-lookup"><span data-stu-id="1e356-296">Expression-bodied members</span></span> ##

<span data-ttu-id="1e356-297">일반적으로 식의 결과와 함께 바로 반환되거나 단일 문이 메서드 본문으로 포함된 메서드 정의가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-297">It is common to have method definitions that simply return immediately with the result of an expression, or that have a single statement as the body of the method.</span></span>  <span data-ttu-id="1e356-298">`=>`를 사용하여 해당 메서드를 속성을 정의하기 위한 구문 바로 가기는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-298">There is a syntax shortcut for defining such methods using `=>`:</span></span>

```csharp
public Point Move(int dx, int dy) => new Point(x + dx, y + dy);
public void Print() => Console.WriteLine(First + " " + Last);
// Works with operators, properties, and indexers too.
public static Complex operator +(Complex a, Complex b) => a.Add(b);
public string Name => First + " " + Last;
public Customer this[long id] => store.LookupCustomer(id);
```

<span data-ttu-id="1e356-299">메서드가 `void`를 반환하거나 비동기 메서드이면 메서드 본문은 문 식이어야 합니다(람다에서와 같음).</span><span class="sxs-lookup"><span data-stu-id="1e356-299">If the method returns `void` or is an async method, the body of the method must be a statement expression (same as with lambdas).</span></span>  <span data-ttu-id="1e356-300">속성 및 인덱서의 경우 읽기 전용이어야 하며, `get` 접근자 키워드를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-300">For properties and indexers, they must be read-only, and you do not use the `get` accessor keyword.</span></span>

<a name="iterators"></a>
## <a name="iterators"></a><span data-ttu-id="1e356-301">반복기</span><span class="sxs-lookup"><span data-stu-id="1e356-301">Iterators</span></span> ##

<span data-ttu-id="1e356-302">반복기는 배열 목록과 같은 컬렉션에 대해 사용자 지정 반복을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-302">An iterator performs a custom iteration over a collection, such as a list or an array.</span></span> <span data-ttu-id="1e356-303">반복기는 [yield return](language-reference/keywords/yield.md) 문을 사용하여 각 요소를 한 번에 하나씩 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-303">An iterator uses the [yield return](language-reference/keywords/yield.md) statement to return each element one at a time.</span></span> <span data-ttu-id="1e356-304">`yield return` 문에 도달하면 호출자가 시퀀스의 다음 요소를 요청할 수 있도록 현재 위치가 기억됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-304">When a `yield return` statement is reached, the current location is remembered so that the caller can request the next element in the sequence.</span></span>

<span data-ttu-id="1e356-305">반복기의 반환 형식은 <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>또는 <xref:System.Collections.Generic.IEnumerator%601>일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e356-305">The return type of an iterator can be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>

<span data-ttu-id="1e356-306">자세한 내용은 [반복기](programming-guide/concepts/iterators.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1e356-306">For more information, see [Iterators](programming-guide/concepts/iterators.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1e356-307">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1e356-307">See also</span></span> ##

<span data-ttu-id="1e356-308">[액세스 한정자](language-reference/keywords/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="1e356-308">[Access Modifiers](language-reference/keywords/access-modifiers.md) </span></span>  
<span data-ttu-id="1e356-309">[정적 클래스 및 정적 클래스 멤버](programming-guide/classes-and-structs/static-classes-and-static-class-members.md) </span><span class="sxs-lookup"><span data-stu-id="1e356-309">[Static Classes and Static Class Members](programming-guide/classes-and-structs/static-classes-and-static-class-members.md) </span></span>  
<span data-ttu-id="1e356-310">[상속](programming-guide/classes-and-structs/inheritance.md) </span><span class="sxs-lookup"><span data-stu-id="1e356-310">[Inheritance](programming-guide/classes-and-structs/inheritance.md) </span></span>  
<span data-ttu-id="1e356-311">[추상 및 봉인 클래스와 클래스 멤버](programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md) </span><span class="sxs-lookup"><span data-stu-id="1e356-311">[Abstract and Sealed Classes and Class Members](programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md) </span></span>  
<span data-ttu-id="1e356-312">[params](language-reference/keywords/params.md) </span><span class="sxs-lookup"><span data-stu-id="1e356-312">[params](language-reference/keywords/params.md) </span></span>  
<span data-ttu-id="1e356-313">[out](language-reference/keywords/out-parameter-modifier.md) </span><span class="sxs-lookup"><span data-stu-id="1e356-313">[out](language-reference/keywords/out-parameter-modifier.md) </span></span>  
<span data-ttu-id="1e356-314">[ref](language-reference/keywords/ref.md) </span><span class="sxs-lookup"><span data-stu-id="1e356-314">[ref](language-reference/keywords/ref.md) </span></span>  
<span data-ttu-id="1e356-315">[in](language-reference/keywords/in-parameter-modifier.md) </span><span class="sxs-lookup"><span data-stu-id="1e356-315">[in](language-reference/keywords/in-parameter-modifier.md) </span></span>  
[<span data-ttu-id="1e356-316">매개 변수 전달</span><span class="sxs-lookup"><span data-stu-id="1e356-316">Passing Parameters</span></span>](programming-guide/classes-and-structs/passing-parameters.md)
