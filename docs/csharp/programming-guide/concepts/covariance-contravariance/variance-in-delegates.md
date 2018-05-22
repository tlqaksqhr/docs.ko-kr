---
title: 대리자의 가변성(C#)
ms.date: 07/20/2015
ms.assetid: 19de89d2-8224-4406-8964-2965b732b890
ms.openlocfilehash: 8b74c29d8d94a31d30408131009d92e2b2a4281c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="variance-in-delegates-c"></a><span data-ttu-id="9af01-102">대리자의 가변성(C#)</span><span class="sxs-lookup"><span data-stu-id="9af01-102">Variance in Delegates (C#)</span></span>
<span data-ttu-id="9af01-103">.NET Framework 3.5에는 메서드 시그니처를 C#에 있는 모든 대리자의 대리자 형식과 일치시키는 가변성 지원이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9af01-103">.NET Framework 3.5 introduced variance support for matching method signatures with delegate types in all delegates in C#.</span></span> <span data-ttu-id="9af01-104">즉, 일치하는 시그니처가 있는 메서드만이 아니라 더 많은 파생된 형식(공변성(covariance))을 반환하는 메서드 또는 대리자 형식에 지정된 것보다 더 적은 수의 파생된 형식(반공변성(contravariance))을 가지고 있는 매개 변수를 수락하는 메서드도 대리자에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9af01-104">This means that you can assign to delegates not only methods that have matching signatures, but also methods that return more derived types (covariance) or that accept parameters that have less derived types (contravariance) than that specified by the delegate type.</span></span> <span data-ttu-id="9af01-105">여기에는 제네릭 및 비 제네릭 대리자가 모두 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9af01-105">This includes both generic and non-generic delegates.</span></span>  
  
 <span data-ttu-id="9af01-106">다음과 같이 두 개의 클래스 및 두 개의 대리자(제네릭 및 비 제네릭)를 가지고 있는 코드를 예로 들어보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="9af01-106">For example, consider the following code, which has two classes and two delegates: generic and non-generic.</span></span>  
  
```csharp  
public class First { }  
public class Second : First { }  
public delegate First SampleDelegate(Second a);  
public delegate R SampleGenericDelegate<A, R>(A a);  
```  
  
 <span data-ttu-id="9af01-107">`SampleDelegate` 또는 `SampleGenericDelegate<A, R>` 형식의 대리자를 만들 때 다음 메서드 중 하나를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9af01-107">When you create delegates of the `SampleDelegate` or `SampleGenericDelegate<A, R>` types, you can assign any one of the following methods to those delegates.</span></span>  
  
```csharp  
// Matching signature.  
public static First ASecondRFirst(Second first)  
{ return new First(); }  
  
// The return type is more derived.  
public static Second ASecondRSecond(Second second)  
{ return new Second(); }  
  
// The argument type is less derived.  
public static First AFirstRFirst(First first)  
{ return new First(); }  
  
// The return type is more derived   
// and the argument type is less derived.  
public static Second AFirstRSecond(First first)  
{ return new Second(); }  
```  
  
 <span data-ttu-id="9af01-108">다음 코드 예제에서는 메서드 시그니처 및 대리자 형식 사이의 암시적 변환을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9af01-108">The following code example illustrates the implicit conversion between the method signature and the delegate type.</span></span>  
  
```csharp  
// Assigning a method with a matching signature   
// to a non-generic delegate. No conversion is necessary.  
SampleDelegate dNonGeneric = ASecondRFirst;  
// Assigning a method with a more derived return type   
// and less derived argument type to a non-generic delegate.  
// The implicit conversion is used.  
SampleDelegate dNonGenericConversion = AFirstRSecond;  
  
// Assigning a method with a matching signature to a generic delegate.  
// No conversion is necessary.  
SampleGenericDelegate<Second, First> dGeneric = ASecondRFirst;  
// Assigning a method with a more derived return type   
// and less derived argument type to a generic delegate.  
// The implicit conversion is used.  
SampleGenericDelegate<Second, First> dGenericConversion = AFirstRSecond;  
```  
  
 <span data-ttu-id="9af01-109">더 많은 예제는 [대리자에서 가변성 사용(C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md) 및 [Func 및 Action 제네릭 대리자에 가변성 사용(C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9af01-109">For more examples, see [Using Variance in Delegates (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md) and [Using Variance for Func and Action Generic Delegates (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span></span>  
  
## <a name="variance-in-generic-type-parameters"></a><span data-ttu-id="9af01-110">제네릭 형식 매개 변수에서의 가변성</span><span class="sxs-lookup"><span data-stu-id="9af01-110">Variance in Generic Type Parameters</span></span>  
 <span data-ttu-id="9af01-111">.NET Framework 4 이상에서는 가변성에 필요한 대로 형식이 서로 간에 상속된 경우 제네릭 형식 매개 변수로 지정한 서로 다른 형식을 가지고 있는 제네릭 대리자를 상호 간에 할당할 수 있도록, 대리자 간 암시적 변환을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9af01-111">In .NET Framework 4 or later you can enable implicit conversion between delegates, so that generic delegates that have different types specified by generic type parameters can be assigned to each other, if the types are inherited from each other as required by variance.</span></span>  
  
 <span data-ttu-id="9af01-112">암시적 변환을 사용하도록 설정하려면 `in` 및 `out` 키워드를 사용하여 대리자에서 제네릭 매개 변수를 공변(covariant) 또는 반공변(contravariant)으로 선언해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9af01-112">To enable implicit conversion, you must explicitly declare generic parameters in a delegate as covariant or contravariant by using the `in` or `out` keyword.</span></span>  
  
 <span data-ttu-id="9af01-113">다음 코드 예제에서는 공변(covariant) 제네릭 형식 매개 변수가 있는 대리자를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9af01-113">The following code example shows how you can create a delegate that has a covariant generic type parameter.</span></span>  
  
```csharp  
// Type T is declared covariant by using the out keyword.  
public delegate T SampleGenericDelegate <out T>();  
  
public static void Test()  
{  
    SampleGenericDelegate <String> dString = () => " ";  
  
    // You can assign delegates to each other,  
    // because the type T is declared covariant.  
    SampleGenericDelegate <Object> dObject = dString;             
}  
```  
  
 <span data-ttu-id="9af01-114">메서드 시그니처를 대리자 형식과 일치시키는 용도로만 가변성 지원을 사용하고 `in` 및 `out` 키워드를 사용하지 않는 경우, 대리자를 동일한 람다 식 또는 메서드로 인스턴스화할 수는 있지만 한 대리자를 다른 대리자에 할당할 수는 없는 경우가 더러 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9af01-114">If you use only variance support to match method signatures with delegate types and do not use the `in` and `out` keywords, you may find that sometimes you can instantiate delegates with identical lambda expressions or methods, but you cannot assign one delegate to another.</span></span>  
  
 <span data-ttu-id="9af01-115">다음 코드 예제에서, `String`은 `Object`를 상속하지만 `SampleGenericDelegate<String>`을 `SampleGenericDelegate<Object>`로 명시적으로 변환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9af01-115">In the following code example, `SampleGenericDelegate<String>` cannot be explicitly converted to `SampleGenericDelegate<Object>`, although `String` inherits `Object`.</span></span> <span data-ttu-id="9af01-116">`T` 제네릭 매개 변수를 `out` 키워드로 표시하면 이 문제를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9af01-116">You can fix this problem by marking the generic parameter `T` with the `out` keyword.</span></span>  
  
```csharp  
public delegate T SampleGenericDelegate<T>();  
  
public static void Test()  
{  
    SampleGenericDelegate<String> dString = () => " ";  
  
    // You can assign the dObject delegate  
    // to the same lambda expression as dString delegate  
    // because of the variance support for   
    // matching method signatures with delegate types.  
    SampleGenericDelegate<Object> dObject = () => " ";  
  
    // The following statement generates a compiler error  
    // because the generic type T is not marked as covariant.  
    // SampleGenericDelegate <Object> dObject = dString;  
  
}  
```  
  
### <a name="generic-delegates-that-have-variant-type-parameters-in-the-net-framework"></a><span data-ttu-id="9af01-117">.NET Framework에 Variant 형식 매개 변수를 가지고 있는 제네릭 대리자</span><span class="sxs-lookup"><span data-stu-id="9af01-117">Generic Delegates That Have Variant Type Parameters in the .NET Framework</span></span>  
 <span data-ttu-id="9af01-118">.NET Framework 4에는 기존의 몇몇 제네릭 대리자에서 제네릭 형식 매개 변수에 대한 가변성 지원이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9af01-118">.NET Framework 4 introduced variance support for generic type parameters in several existing generic delegates:</span></span>  
  
-   <span data-ttu-id="9af01-119"><xref:System> 네임스페이스의 `Action` 대리자(예: <xref:System.Action%601> 및 <xref:System.Action%602>)</span><span class="sxs-lookup"><span data-stu-id="9af01-119">`Action` delegates from the <xref:System> namespace, for example, <xref:System.Action%601> and <xref:System.Action%602></span></span>  
  
-   <span data-ttu-id="9af01-120"><xref:System> 네임스페이스의 `Func` 대리자(예: <xref:System.Func%601> 및 <xref:System.Func%602>)</span><span class="sxs-lookup"><span data-stu-id="9af01-120">`Func` delegates from the <xref:System> namespace, for example, <xref:System.Func%601> and <xref:System.Func%602></span></span>  
  
-   <span data-ttu-id="9af01-121"><xref:System.Predicate%601> 대리자</span><span class="sxs-lookup"><span data-stu-id="9af01-121">The <xref:System.Predicate%601> delegate</span></span>  
  
-   <span data-ttu-id="9af01-122"><xref:System.Comparison%601> 대리자</span><span class="sxs-lookup"><span data-stu-id="9af01-122">The <xref:System.Comparison%601> delegate</span></span>  
  
-   <span data-ttu-id="9af01-123"><xref:System.Converter%602> 대리자</span><span class="sxs-lookup"><span data-stu-id="9af01-123">The <xref:System.Converter%602> delegate</span></span>  
  
 <span data-ttu-id="9af01-124">자세한 정보 및 예제는 [Func 및 Action 제네릭 대리자에 가변성 사용(C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9af01-124">For more information and examples, see [Using Variance for Func and Action Generic Delegates (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span></span>  
  
### <a name="declaring-variant-type-parameters-in-generic-delegates"></a><span data-ttu-id="9af01-125">제네릭 대리자에서 Variant 형식 매개 변수 선언</span><span class="sxs-lookup"><span data-stu-id="9af01-125">Declaring Variant Type Parameters in Generic Delegates</span></span>  
 <span data-ttu-id="9af01-126">제네릭 대리자가 공변(covariant) 또는 반공변(contravariant) 제네릭 형식 매개 변수를 가지고 있는 경우 이를 *variant 제네릭 대리자*라고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9af01-126">If a generic delegate has covariant or contravariant generic type parameters, it can be referred to as a *variant generic delegate*.</span></span>  
  
 <span data-ttu-id="9af01-127">`out` 키워드를 사용하여 제네릭 대리자에서 제네릭 형식 매개 변수를 공변(covariant)으로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9af01-127">You can declare a generic type parameter covariant in a generic delegate by using the `out` keyword.</span></span> <span data-ttu-id="9af01-128">공변(covariant) 형식은 메서드 반환 형식으로만 사용할 수 있으며 메서드 인수의 형식으로는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9af01-128">The covariant type can be used only as a method return type and not as a type of method arguments.</span></span> <span data-ttu-id="9af01-129">다음 코드 예제에서는 공변(covariant) 제네릭 대리자를 선언하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9af01-129">The following code example shows how to declare a covariant generic delegate.</span></span>  
  
```csharp  
public delegate R DCovariant<out R>();  
```  
  
 <span data-ttu-id="9af01-130">`in` 키워드를 사용하여 제네릭 대리자에서 제네릭 형식 매개 변수를 반공변(contravariant)으로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9af01-130">You can declare a generic type parameter contravariant in a generic delegate by using the `in` keyword.</span></span> <span data-ttu-id="9af01-131">반공변(contravariant) 형식은 메서드 인수의 형식으로서만 사용할 수 있으며 메서드 반환 형식으로는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9af01-131">The contravariant type can be used only as a type of method arguments and not as a method return type.</span></span> <span data-ttu-id="9af01-132">다음 코드 예제에서는 반공변(contravariant) 제네릭 대리자를 선언하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9af01-132">The following code example shows how to declare a contravariant generic delegate.</span></span>  
  
```csharp  
public delegate void DContravariant<in A>(A a);  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="9af01-133">C#의 `ref`, `in` 및 `out` 매개 변수는 variant로 표시할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9af01-133">`ref`, `in`, and `out` parameters in C# can't be marked as variant.</span></span>  
  
 <span data-ttu-id="9af01-134">동일한 대리자에서, 그러나 서로 다른 형식 매개 변수에 대해 분산 및 공변성(covariance)을 모두 지원하는 것도 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="9af01-134">It is also possible to support both variance and covariance in the same delegate, but for different type parameters.</span></span> <span data-ttu-id="9af01-135">다음 예제에서 이를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9af01-135">This is shown in the following example.</span></span>  
  
```csharp  
public delegate R DVariant<in A, out R>(A a);  
```  
  
### <a name="instantiating-and-invoking-variant-generic-delegates"></a><span data-ttu-id="9af01-136">Variant 제네릭 대리자 인스턴스화 및 호출</span><span class="sxs-lookup"><span data-stu-id="9af01-136">Instantiating and Invoking Variant Generic Delegates</span></span>  
 <span data-ttu-id="9af01-137">비 variant 대리자를 인스턴스화 및 호출하듯 variant 대리자를 인스턴스화 및 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9af01-137">You can instantiate and invoke variant delegates just as you instantiate and invoke invariant delegates.</span></span> <span data-ttu-id="9af01-138">다음 예제에서는 람다 식을 사용하여 대리자가 인스턴스화됩니다.</span><span class="sxs-lookup"><span data-stu-id="9af01-138">In the following example, the delegate is instantiated by a lambda expression.</span></span>  
  
```csharp  
DVariant<String, String> dvariant = (String str) => str + " ";  
dvariant("test");  
```  
  
### <a name="combining-variant-generic-delegates"></a><span data-ttu-id="9af01-139">Variant 제네릭 대리자 결합</span><span class="sxs-lookup"><span data-stu-id="9af01-139">Combining Variant Generic Delegates</span></span>  
 <span data-ttu-id="9af01-140">Variant 대리자는 결합할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9af01-140">You should not combine variant delegates.</span></span> <span data-ttu-id="9af01-141"><xref:System.Delegate.Combine%2A> 메서드는 variant 대리자 변환을 지원하지 않으며 대리자가 정확히 동일한 형식일 것으로 예상합니다.</span><span class="sxs-lookup"><span data-stu-id="9af01-141">The <xref:System.Delegate.Combine%2A> method does not support variant delegate conversion and expects delegates to be of exactly the same type.</span></span> <span data-ttu-id="9af01-142">따라서 다음 코드 예제와 같이 <xref:System.Delegate.Combine%2A> 메서드를 사용하거나 `+` 연산자를 사용하여 대리자를 결합하면 런타임 예외가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9af01-142">This can lead to a run-time exception when you combine delegates either by using the <xref:System.Delegate.Combine%2A> method or by using the `+` operator, as shown in the following code example.</span></span>  
  
```csharp  
Action<object> actObj = x => Console.WriteLine("object: {0}", x);  
Action<string> actStr = x => Console.WriteLine("string: {0}", x);  
// All of the following statements throw exceptions at run time.  
// Action<string> actCombine = actStr + actObj;  
// actStr += actObj;  
// Delegate.Combine(actStr, actObj);  
```  
  
## <a name="variance-in-generic-type-parameters-for-value-and-reference-types"></a><span data-ttu-id="9af01-143">값 및 참조 형식에 대한 제네릭 형식 매개 변수에서의 가변성</span><span class="sxs-lookup"><span data-stu-id="9af01-143">Variance in Generic Type Parameters for Value and Reference Types</span></span>  
 <span data-ttu-id="9af01-144">제네릭 형식 매개 변수에 대한 가변성은 참조 형식에 대해서만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="9af01-144">Variance for generic type parameters is supported for reference types only.</span></span> <span data-ttu-id="9af01-145">정수는 값 형식이므로, 예를 들어 `DVariant<int>`를 명시적으로 `DVariant<Object>` 또는 `DVariant<long>`으로 변환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9af01-145">For example, `DVariant<int>` can't be implicitly converted to `DVariant<Object>` or `DVariant<long>`, because integer is a value type.</span></span>  
  
 <span data-ttu-id="9af01-146">다음 예제에서는 제네릭 형식 매개 변수에서의 가변성이 값 형식에 대해 지원되지 않음을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9af01-146">The following example demonstrates that variance in generic type parameters is not supported for value types.</span></span>  
  
```csharp  
// The type T is covariant.  
public delegate T DVariant<out T>();  
  
// The type T is invariant.  
public delegate T DInvariant<T>();  
  
public static void Test()  
{  
    int i = 0;  
    DInvariant<int> dInt = () => i;  
    DVariant<int> dVariantInt = () => i;  
  
    // All of the following statements generate a compiler error  
    // because type variance in generic parameters is not supported  
    // for value types, even if generic type parameters are declared variant.  
    // DInvariant<Object> dObject = dInt;  
    // DInvariant<long> dLong = dInt;  
    // DVariant<Object> dVariantObject = dVariantInt;  
    // DVariant<long> dVariantLong = dVariantInt;              
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="9af01-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9af01-147">See Also</span></span>  
 [<span data-ttu-id="9af01-148">제네릭</span><span class="sxs-lookup"><span data-stu-id="9af01-148">Generics</span></span>](~/docs/standard/generics/index.md)  
 [<span data-ttu-id="9af01-149">Func 및 Action 제네릭 대리자에 가변성 사용(C#)</span><span class="sxs-lookup"><span data-stu-id="9af01-149">Using Variance for Func and Action Generic Delegates (C#)</span></span>](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)  
 [<span data-ttu-id="9af01-150">방법: 대리자 조합(멀티캐스트 대리자)</span><span class="sxs-lookup"><span data-stu-id="9af01-150">How to: Combine Delegates (Multicast Delegates)</span></span>](../../../../csharp/programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md)
