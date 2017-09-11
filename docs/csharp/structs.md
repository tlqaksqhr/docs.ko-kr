---
title: "구조체 - C# 가이드"
description: "구조체 형식 및 만드는 방법을 알아봅니다."
keywords: .NET, .NET Core, C#
author: BillWagner
ms.author: wiwagn
ms.date: 10/12/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: a7094b8c-7229-4b6f-82fc-824d0ea0ec40
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: e2a4bfdb46a69113d5eb8949df4ccf902acf9dee
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---

# <a name="structs"></a><span data-ttu-id="186a6-104">구조체</span><span class="sxs-lookup"><span data-stu-id="186a6-104">Structs</span></span>
<span data-ttu-id="186a6-105">*struct*가 값 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="186a6-105">A *struct* is a value type.</span></span> <span data-ttu-id="186a6-106">구조체를 만드는 경우 구조체가 할당된 변수에 구조체의 실제 데이터가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="186a6-106">When a struct is created, the variable to which the struct is assigned holds the struct's actual data.</span></span> <span data-ttu-id="186a6-107">구조체를 새 변수에 할당하면 구조체가 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="186a6-107">When the struct is assigned to a new variable, it is copied.</span></span> <span data-ttu-id="186a6-108">따라서 새 변수와 원래 변수에 동일한 데이터의 두 가지 별도 복사본이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="186a6-108">The new variable and the original variable therefore contain two separate copies of the same data.</span></span> <span data-ttu-id="186a6-109">한 복사본의 변경 내용은 다른 복사본에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="186a6-109">Changes made to one copy do not affect the other copy.</span></span>

<span data-ttu-id="186a6-110">값 형식 변수에는 해당 값이 직접 포함되므로, 변수가 선언된 컨텍스트에 관계없이 메모리가 인라인으로 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="186a6-110">Value type variables directly contain their values, which means that the memory is allocated inline in whatever context the variable is declared.</span></span> <span data-ttu-id="186a6-111">값 형식 변수에 대한 별도 힙 할당이나 가비지 수집 오버헤드는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="186a6-111">There is no separate heap allocation or garbage collection overhead for value-type variables.</span></span>  
  
<span data-ttu-id="186a6-112">값 형식에는 [struct](./language-reference/keywords/struct.md) 및 [enum](./language-reference/keywords/enum.md)의 두 가지 범주가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="186a6-112">There are two categories of value types: [struct](./language-reference/keywords/struct.md) and [enum](./language-reference/keywords/enum.md).</span></span>  
  
<span data-ttu-id="186a6-113">기본 제공 숫자 형식은 구조체이며, 액세스할 수 있는 속성과 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="186a6-113">The built-in numeric types are structs, and they have properties and methods that you can access:</span></span>  
  
<span data-ttu-id="186a6-114">[!code-csharp[정적 메서드](../../samples/snippets/csharp/concepts/structs/static-method.cs)]</span><span class="sxs-lookup"><span data-stu-id="186a6-114">[!code-csharp[Static Method](../../samples/snippets/csharp/concepts/structs/static-method.cs)]</span></span>
  
<span data-ttu-id="186a6-115">하지만 단순 비집계 형식처럼 값을 선언하고 변수에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="186a6-115">But you declare and assign values to them as if they were simple non-aggregate types:</span></span>  
  
<span data-ttu-id="186a6-116">[!code-csharp[값 할당](../../samples/snippets/csharp/concepts/structs/assign-value.cs)]</span><span class="sxs-lookup"><span data-stu-id="186a6-116">[!code-csharp[Assign Values](../../samples/snippets/csharp/concepts/structs/assign-value.cs)]</span></span> 
  
<span data-ttu-id="186a6-117">값 형식은 *sealed*이므로, 예를 들어 @System.Int32에서 형식을 파생시킬 수 없으며 구조체는 @System.ValueType에서만 상속할 수 있기 때문에 사용자 정의 클래스 또는 구조체에서 상속하는 구조체를 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="186a6-117">Value types are *sealed*, which means, for example, that you cannot derive a type from @System.Int32, and you cannot define a struct to inherit from any user-defined class or struct because a struct can only inherit from @System.ValueType.</span></span> <span data-ttu-id="186a6-118">그러나 구조체는 하나 이상의 인터페이스를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="186a6-118">However, a struct can implement one or more interfaces.</span></span> <span data-ttu-id="186a6-119">구조체 형식을 인터페이스 형식으로 캐스팅할 수 있습니다. 이 경우 *boxing* 작업은 관리되는 힙의 참조 형식 개체 내에 구조체를 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="186a6-119">You can cast a struct type to an interface type; this causes a *boxing* operation to wrap the struct inside a reference type object on the managed heap.</span></span> <span data-ttu-id="186a6-120">boxing 작업은 @System.Object를 입력 매개 변수로 사용하는 메서드에 값 형식을 전달할 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="186a6-120">Boxing operations occur when you pass a value type to a method that takes an @System.Object as an input parameter.</span></span> <span data-ttu-id="186a6-121">자세한 내용은 [boxing 및 unboxing](./programming-guide/types/boxing-and-unboxing.md )을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="186a6-121">For more information, see [Boxing and Unboxing](./programming-guide/types/boxing-and-unboxing.md ).</span></span>  
  
<span data-ttu-id="186a6-122">[struct](./language-reference/keywords/struct.md) 키워드를 사용하여 고유한 사용자 지정 값 형식을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="186a6-122">You use the [struct](./language-reference/keywords/struct.md) keyword to create your own custom value types.</span></span> <span data-ttu-id="186a6-123">일반적으로 구조체는 다음 예제와 같이 소규모 관련 변수 집합의 컨테이너로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="186a6-123">Typically, a struct is used as a container for a small set of related variables, as shown in the following example:</span></span>  
  
<span data-ttu-id="186a6-124">[!code-csharp[Struct 키워드](../../samples/snippets/csharp/concepts/structs/struct-keyword.cs)]</span><span class="sxs-lookup"><span data-stu-id="186a6-124">[!code-csharp[Struct Keyword](../../samples/snippets/csharp/concepts/structs/struct-keyword.cs)]</span></span>  
  
<span data-ttu-id="186a6-125">.NET Framework의 값 형식에 대한 자세한 내용은 [CTS(공용 형식 시스템)](../standard/common-type-system.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="186a6-125">For more information about value types in the .NET Framework, see [Common Type System](../standard/common-type-system.md).</span></span>  
    
<span data-ttu-id="186a6-126">구조체가 클래스보다 더 제한적이지만 구조체는 클래스와 동일한 구문을 대부분 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="186a6-126">Structs share most of the same syntax as classes, although structs are more limited than classes:</span></span>  
  
-   <span data-ttu-id="186a6-127">구조체 선언 내에서 필드가 `const` 또는 `static`으로 선언된 경우가 아니면 필드를 초기화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="186a6-127">Within a struct declaration, fields cannot be initialized unless they are declared as `const` or `static`.</span></span>  
  
-   <span data-ttu-id="186a6-128">구조체는 기본 생성자(매개 변수가 없는 생성자) 또는 종료자를 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="186a6-128">A struct cannot declare a default constructor (a constructor without parameters) or a finalizer.</span></span>  
  
-   <span data-ttu-id="186a6-129">할당 시 구조체가 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="186a6-129">Structs are copied on assignment.</span></span> <span data-ttu-id="186a6-130">구조체를 새 변수에 할당하면 모든 데이터가 복사되고, 새 복사본을 수정해도 원래 복사본의 데이터는 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="186a6-130">When a struct is assigned to a new variable, all the data is copied, and any modification to the new copy does not change the data for the original copy.</span></span> <span data-ttu-id="186a6-131">Dictionary<string, myStruct> 등의 값 형식 컬렉션으로 작업하는 경우 이 점을 명심해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="186a6-131">This is important to remember when working with collections of value types such as Dictionary<string, myStruct>.</span></span>  
  
-   <span data-ttu-id="186a6-132">구조체는 값 형식이고 클래스는 참조 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="186a6-132">Structs are value types and classes are reference types.</span></span>  
  
-   <span data-ttu-id="186a6-133">클래스와 달리 구조체는 `new` 연산자를 사용하지 않고 인스턴스화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="186a6-133">Unlike classes, structs can be instantiated without using a `new` operator.</span></span>  
  
-   <span data-ttu-id="186a6-134">구조체는 매개 변수가 있는 생성자를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="186a6-134">Structs can declare constructors that have parameters.</span></span>  
  
-   <span data-ttu-id="186a6-135">구조체는 다른 구조체 또는 클래스에서 상속될 수 없으며, 클래스의 기본 클래스가 될 수도 없습니다.</span><span class="sxs-lookup"><span data-stu-id="186a6-135">A struct cannot inherit from another struct or class, and it cannot be the base of a class.</span></span> <span data-ttu-id="186a6-136">모든 구조체는 @System.Object에서 상속하는 @System.ValueType에서 직접 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="186a6-136">All structs inherit directly from @System.ValueType, which inherits from @System.Object.</span></span>  
  
-   <span data-ttu-id="186a6-137">구조체는 인터페이스를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="186a6-137">A struct can implement interfaces.</span></span>

## <a name="literal-values"></a><span data-ttu-id="186a6-138">리터럴 값</span><span class="sxs-lookup"><span data-stu-id="186a6-138">Literal values</span></span>  
<span data-ttu-id="186a6-139">C#에서는 리터럴 값이 컴파일러에서 형식을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="186a6-139">In C#, literal values receive a type from the compiler.</span></span> <span data-ttu-id="186a6-140">숫자의 끝에 문자를 추가하여 숫자 리터럴의 입력 방법을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="186a6-140">You can specify how a numeric literal should be typed by appending a letter to the end of the number.</span></span> <span data-ttu-id="186a6-141">예를 들어 값 4.56이 float로 처리되도록 지정하려면 숫자 뒤에 "f" 또는 "F"를 추가합니다(`4.56f`).</span><span class="sxs-lookup"><span data-stu-id="186a6-141">For example, to specify that the value 4.56 should be treated as a float, append an "f" or "F" after the number: `4.56f`.</span></span> <span data-ttu-id="186a6-142">문자를 추가하지 않으면 컴파일러가 리터럴에 대해 `double` 형식을 유추합니다.</span><span class="sxs-lookup"><span data-stu-id="186a6-142">If no letter is appended, the compiler will infer the `double` type for the literal.</span></span> <span data-ttu-id="186a6-143">문자 접미사와 함께 지정할 수 있는 형식에 대한 자세한 내용은 [값 형식](./language-reference/keywords/value-types.md)에서 개별 형식의 참조 페이지를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="186a6-143">For more information about which types can be specified with letter suffixes, see the reference pages for individual types in [Value Types](./language-reference/keywords/value-types.md).</span></span>  
  
<span data-ttu-id="186a6-144">리터럴은 형식화되고 모든 형식이 궁극적으로 @System.Object에서 파생되기 때문에 다음과 같은 코드를 작성하고 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="186a6-144">Because literals are typed, and all types derive ultimately from @System.Object, you can write and compile code such as the following:</span></span>  
  
<span data-ttu-id="186a6-145">[!code-csharp[리터럴 값](../../samples/snippets/csharp/concepts/structs/literals.cs)]</span><span class="sxs-lookup"><span data-stu-id="186a6-145">[!code-csharp[Literal Values](../../samples/snippets/csharp/concepts/structs/literals.cs)]</span></span>

<span data-ttu-id="186a6-146">마지막 두 예제에서는 C# 7.0에서 도입된 언어 기능을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="186a6-146">The last two examples demonstrate language features introduced in C# 7.0.</span></span> <span data-ttu-id="186a6-147">첫 번째 예제에서는 밑줄 문자를 숫자 리터럴 내의 *숫자 구분 기호*로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="186a6-147">The first allows you to use an underscore character as a *digit separator* inside numeric literals.</span></span> <span data-ttu-id="186a6-148">가독성을 개선하기 위해 숫자 사이의 원하는 위치에 넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="186a6-148">You can put them wherever you want between digits to improve readability.</span></span> <span data-ttu-id="186a6-149">값에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="186a6-149">They have no effect on the value.</span></span>

<span data-ttu-id="186a6-150">두 번째 예제에서는 16진수 표기법을 사용하는 대신 비트 패턴을 직접 지정할 수 있는 *이진 리터럴*을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="186a6-150">The second demonstrates *binary literals*, which allow you to specify bit patterns directly instead of using hexadecimal notation.</span></span>

## <a name="nullable-types"></a><span data-ttu-id="186a6-151">Nullable 형식</span><span class="sxs-lookup"><span data-stu-id="186a6-151">Nullable types</span></span>  
<span data-ttu-id="186a6-152">일반적인 값 형식은 [null](./language-reference/keywords/null.md) 값을 가질 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="186a6-152">Ordinary value types cannot have a value of [null](./language-reference/keywords/null.md).</span></span> <span data-ttu-id="186a6-153">그러나 형식 뒤에 **?**를 추가하면 nullable 값 형식을</span><span class="sxs-lookup"><span data-stu-id="186a6-153">However, you can create nullable value types by affixing a **?**</span></span> <span data-ttu-id="186a6-154">만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="186a6-154">after the type.</span></span> <span data-ttu-id="186a6-155">예를 들어 **int?**는 [null](./language-reference/keywords/null.md) 값을 가질 수도 있는 **int** 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="186a6-155">For example, **int?** is an **int** type that can also have the value [null](./language-reference/keywords/null.md).</span></span> <span data-ttu-id="186a6-156">CTS에서 Nullable 형식은 제네릭 구조체 형식 @System.Nullable601%의 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="186a6-156">In the CTS, nullable types are instances of the generic struct type @System.Nullable%601.</span></span> <span data-ttu-id="186a6-157">Nullable 형식은 특히 숫자 값이 null일 수 있는 데이터베이스에 데이터를 전달하는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="186a6-157">Nullable types are especially useful when you are passing data to and from databases in which numeric values might be null.</span></span> <span data-ttu-id="186a6-158">자세한 내용은 [Nullable 형식(C# 프로그래밍 가이드)](./programming-guide/nullable-types/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="186a6-158">For more information, see [Nullable Types (C# Programming Guide)](./programming-guide/nullable-types/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="186a6-159">참고 항목</span><span class="sxs-lookup"><span data-stu-id="186a6-159">See also</span></span>
[<span data-ttu-id="186a6-160">클래스</span><span class="sxs-lookup"><span data-stu-id="186a6-160">Classes</span></span>](classes.md)

[<span data-ttu-id="186a6-161">기본 형식</span><span class="sxs-lookup"><span data-stu-id="186a6-161">Basic Types</span></span>](basic-types.md)

