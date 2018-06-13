---
title: 제네릭 인터페이스의 가변성(C#)
ms.date: 07/20/2015
ms.assetid: 4828a8f9-48c0-4128-9749-7fcd6bf19a06
ms.openlocfilehash: fdcfd13a645ffc9b596beed65b74f8e593c642f7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33326760"
---
# <a name="variance-in-generic-interfaces-c"></a><span data-ttu-id="ab418-102">제네릭 인터페이스의 가변성(C#)</span><span class="sxs-lookup"><span data-stu-id="ab418-102">Variance in Generic Interfaces (C#)</span></span>
<span data-ttu-id="ab418-103">.NET Framework 4에서는 기존의 몇몇 제네릭 인터페이스에 대한 가변성 지원이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ab418-103">.NET Framework 4 introduced variance support for several existing generic interfaces.</span></span> <span data-ttu-id="ab418-104">가변성 지원은 이러한 인터페이스를 구현하는 클래스의 암시적 변환을 가능하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab418-104">Variance support enables implicit conversion of classes that implement these interfaces.</span></span> <span data-ttu-id="ab418-105">다음 인터페이스는 현재 variant입니다.</span><span class="sxs-lookup"><span data-stu-id="ab418-105">The following interfaces are now variant:</span></span>  
  
-   <span data-ttu-id="ab418-106"><xref:System.Collections.Generic.IEnumerable%601>(T는 공변(covariant)임)</span><span class="sxs-lookup"><span data-stu-id="ab418-106"><xref:System.Collections.Generic.IEnumerable%601> (T is covariant)</span></span>  
  
-   <span data-ttu-id="ab418-107"><xref:System.Collections.Generic.IEnumerator%601>(T는 공변(covariant)임)</span><span class="sxs-lookup"><span data-stu-id="ab418-107"><xref:System.Collections.Generic.IEnumerator%601> (T is covariant)</span></span>  
  
-   <span data-ttu-id="ab418-108"><xref:System.Linq.IQueryable%601>(T는 공변(covariant)임)</span><span class="sxs-lookup"><span data-stu-id="ab418-108"><xref:System.Linq.IQueryable%601> (T is covariant)</span></span>  
  
-   <span data-ttu-id="ab418-109"><xref:System.Linq.IGrouping%602>(`TKey` 및 `TElement`는 공변(covariant)임)</span><span class="sxs-lookup"><span data-stu-id="ab418-109"><xref:System.Linq.IGrouping%602> (`TKey` and `TElement` are covariant)</span></span>  
  
-   <span data-ttu-id="ab418-110"><xref:System.Collections.Generic.IComparer%601>(T는 반공변(contravariant)임)</span><span class="sxs-lookup"><span data-stu-id="ab418-110"><xref:System.Collections.Generic.IComparer%601> (T is contravariant)</span></span>  
  
-   <span data-ttu-id="ab418-111"><xref:System.Collections.Generic.IEqualityComparer%601>(T는 반공변(contravariant)임)</span><span class="sxs-lookup"><span data-stu-id="ab418-111"><xref:System.Collections.Generic.IEqualityComparer%601> (T is contravariant)</span></span>  
  
-   <span data-ttu-id="ab418-112"><xref:System.IComparable%601>(T는 반공변(contravariant)임)</span><span class="sxs-lookup"><span data-stu-id="ab418-112"><xref:System.IComparable%601> (T is contravariant)</span></span>  
  
 <span data-ttu-id="ab418-113">공변성(covariance)은 메서드가 인터페이스의 제네릭 형식 매개 변수에 정의된 것보다 더 많은 수의 파생된 반환 형식을 갖도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="ab418-113">Covariance permits a method to have a more derived return type than that defined by the generic type parameter of the interface.</span></span> <span data-ttu-id="ab418-114">공변성(covariance) 기능을 설명하려면 `IEnumerable<Object>` 및 `IEnumerable<String>`이라는 제네릭 인터페이스를 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="ab418-114">To illustrate the covariance feature, consider these generic interfaces: `IEnumerable<Object>` and `IEnumerable<String>`.</span></span> <span data-ttu-id="ab418-115">`IEnumerable<String>` 인터페이스는 `IEnumerable<Object>` 인터페이스를 상속하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ab418-115">The `IEnumerable<String>` interface does not inherit the `IEnumerable<Object>` interface.</span></span> <span data-ttu-id="ab418-116">그러나 `String` 형식은 `Object` 형식을 상속하며, 경우에 따라 이러한 인터페이스의 개체를 서로 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab418-116">However, the `String` type does inherit the `Object` type, and in some cases you may want to assign objects of these interfaces to each other.</span></span> <span data-ttu-id="ab418-117">다음 코드 예제에서 이를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab418-117">This is shown in the following code example.</span></span>  
  
```csharp  
IEnumerable<String> strings = new List<String>();  
IEnumerable<Object> objects = strings;  
```  
  
 <span data-ttu-id="ab418-118">.NET Framework의 이전 버전에서는 이 코드가 `Option Strict On` 상태의 C#에서 컴파일 오류를 일으킵니다.</span><span class="sxs-lookup"><span data-stu-id="ab418-118">In earlier versions of the .NET Framework, this code causes a compilation error in C# with `Option Strict On`.</span></span> <span data-ttu-id="ab418-119">그러나 <xref:System.Collections.Generic.IEnumerable%601> 인터페이스는 공변(covariant) 이므로 이제 다음 예제와 같이 `objects` 대신 `strings`를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab418-119">But now you can use `strings` instead of `objects`, as shown in the previous example, because the <xref:System.Collections.Generic.IEnumerable%601> interface is covariant.</span></span>  
  
 <span data-ttu-id="ab418-120">반공변성(Contravariance)은 메서드가 인터페이스의 제네릭 매개 변수에 지정된 것보다 더 적은 수의 파생된 형식의 인수 형식을 갖도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="ab418-120">Contravariance permits a method to have argument types that are less derived than that specified by the generic parameter of the interface.</span></span> <span data-ttu-id="ab418-121">반공변성(contravariance)을 설명하기 위해, 사용자가 `BaseComparer` 클래스를 만들어 `BaseClass` 클래스의 인스턴스를 비교한다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="ab418-121">To illustrate contravariance, assume that you have created a `BaseComparer` class to compare instances of the `BaseClass` class.</span></span> <span data-ttu-id="ab418-122">`BaseComparer` 클래스는 `IEqualityComparer<BaseClass>` 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="ab418-122">The `BaseComparer` class implements the `IEqualityComparer<BaseClass>` interface.</span></span> <span data-ttu-id="ab418-123"><xref:System.Collections.Generic.IEqualityComparer%601> 인터페이스는 이제 반공변(contravariant)이므로 `BaseClass` 클래스를 상속하는 클래스의 인스턴스를 비교하는 데 `BaseComparer`를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab418-123">Because the <xref:System.Collections.Generic.IEqualityComparer%601> interface is now contravariant, you can use `BaseComparer` to compare instances of classes that inherit the `BaseClass` class.</span></span> <span data-ttu-id="ab418-124">다음 코드 예제에서 이를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab418-124">This is shown in the following code example.</span></span>  
  
```csharp  
// Simple hierarchy of classes.  
class BaseClass { }  
class DerivedClass : BaseClass { }  
  
// Comparer class.  
class BaseComparer : IEqualityComparer<BaseClass>   
{  
    public int GetHashCode(BaseClass baseInstance)  
    {  
        return baseInstance.GetHashCode();  
    }  
    public bool Equals(BaseClass x, BaseClass y)  
    {  
        return x == y;  
    }  
}  
class Program  
{  
    static void Test()  
    {  
        IEqualityComparer<BaseClass> baseComparer = new BaseComparer();  
  
        // Implicit conversion of IEqualityComparer<BaseClass> to   
        // IEqualityComparer<DerivedClass>.  
        IEqualityComparer<DerivedClass> childComparer = baseComparer;  
    }  
}  
```  
  
 <span data-ttu-id="ab418-125">추가 예제는 [제네릭 컬렉션용 인터페이스의 가변성 사용(C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ab418-125">For more examples, see [Using Variance in Interfaces for Generic Collections (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md).</span></span>  
  
 <span data-ttu-id="ab418-126">제네릭 인터페이스의 가변성은 참조 형식에 대해서만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab418-126">Variance in generic interfaces is supported for reference types only.</span></span> <span data-ttu-id="ab418-127">값 형식은 가변성을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ab418-127">Value types do not support variance.</span></span> <span data-ttu-id="ab418-128">정수는 값 형식으로 표시되므로 예를 들어 `IEnumerable<int>`를 `IEnumerable<object>`로 암시적으로 변환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ab418-128">For example, `IEnumerable<int>` cannot be implicitly converted to `IEnumerable<object>`, because integers are represented by a value type.</span></span>  
  
```csharp  
IEnumerable<int> integers = new List<int>();  
// The following statement generates a compiler errror,  
// because int is a value type.  
// IEnumerable<Object> objects = integers;  
```  
  
 <span data-ttu-id="ab418-129">Variant 인터페이스를 구현하는 클래스는 여전히 비 variant라는 점에 유의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab418-129">It is also important to remember that classes that implement variant interfaces are still invariant.</span></span> <span data-ttu-id="ab418-130">예를 들어 <xref:System.Collections.Generic.List%601>는 공변(covariant) 인터페이스 <xref:System.Collections.Generic.IEnumerable%601>을 구현하지만 암시적으로 `List<Object>`를 `List<String>`으로 변환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ab418-130">For example, although <xref:System.Collections.Generic.List%601> implements the covariant interface <xref:System.Collections.Generic.IEnumerable%601>, you cannot implicitly convert `List<Object>` to `List<String>`.</span></span> <span data-ttu-id="ab418-131">다음 코드 예제에서 이 내용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab418-131">This is illustrated in the following code example.</span></span>  
  
```csharp  
// The following line generates a compiler error  
// because classes are invariant.  
// List<Object> list = new List<String>();  
  
// You can use the interface object instead.  
IEnumerable<Object> listObjects = new List<String>();  
```  
  
## <a name="see-also"></a><span data-ttu-id="ab418-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ab418-132">See Also</span></span>  
 [<span data-ttu-id="ab418-133">제네릭 컬렉션용 인터페이스의 가변성 사용(C#)</span><span class="sxs-lookup"><span data-stu-id="ab418-133">Using Variance in Interfaces for Generic Collections (C#)</span></span>](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md)  
 [<span data-ttu-id="ab418-134">Variant 제네릭 인터페이스 만들기(C#)</span><span class="sxs-lookup"><span data-stu-id="ab418-134">Creating Variant Generic Interfaces (C#)</span></span>](../../../../csharp/programming-guide/concepts/covariance-contravariance/creating-variant-generic-interfaces.md)  
 [<span data-ttu-id="ab418-135">제네릭 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ab418-135">Generic Interfaces</span></span>](../../../../standard/generics/interfaces.md)  
 [<span data-ttu-id="ab418-136">대리자의 가변성(C#)</span><span class="sxs-lookup"><span data-stu-id="ab418-136">Variance in Delegates (C#)</span></span>](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)
