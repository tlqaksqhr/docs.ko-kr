---
title: 제네릭 인터페이스 (Visual Basic)의 가변성
ms.date: 07/20/2015
ms.assetid: cf4096d0-4bb3-45a9-9a6b-f01e29a60333
ms.openlocfilehash: c18f014897ace71e437bd733ff6fcd1d4d8810dd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33643460"
---
# <a name="variance-in-generic-interfaces-visual-basic"></a><span data-ttu-id="ab829-102">제네릭 인터페이스 (Visual Basic)의 가변성</span><span class="sxs-lookup"><span data-stu-id="ab829-102">Variance in Generic Interfaces (Visual Basic)</span></span>
<span data-ttu-id="ab829-103">.NET Framework 4에서는 기존의 몇몇 제네릭 인터페이스에 대한 가변성 지원이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ab829-103">.NET Framework 4 introduced variance support for several existing generic interfaces.</span></span> <span data-ttu-id="ab829-104">가변성 지원은 이러한 인터페이스를 구현하는 클래스의 암시적 변환을 가능하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab829-104">Variance support enables implicit conversion of classes that implement these interfaces.</span></span> <span data-ttu-id="ab829-105">다음 인터페이스는 현재 variant입니다.</span><span class="sxs-lookup"><span data-stu-id="ab829-105">The following interfaces are now variant:</span></span>  
  
-   <span data-ttu-id="ab829-106"><xref:System.Collections.Generic.IEnumerable%601>(T는 공변(covariant)임)</span><span class="sxs-lookup"><span data-stu-id="ab829-106"><xref:System.Collections.Generic.IEnumerable%601> (T is covariant)</span></span>  
  
-   <span data-ttu-id="ab829-107"><xref:System.Collections.Generic.IEnumerator%601>(T는 공변(covariant)임)</span><span class="sxs-lookup"><span data-stu-id="ab829-107"><xref:System.Collections.Generic.IEnumerator%601> (T is covariant)</span></span>  
  
-   <span data-ttu-id="ab829-108"><xref:System.Linq.IQueryable%601>(T는 공변(covariant)임)</span><span class="sxs-lookup"><span data-stu-id="ab829-108"><xref:System.Linq.IQueryable%601> (T is covariant)</span></span>  
  
-   <span data-ttu-id="ab829-109"><xref:System.Linq.IGrouping%602>(`TKey` 및 `TElement`는 공변(covariant)임)</span><span class="sxs-lookup"><span data-stu-id="ab829-109"><xref:System.Linq.IGrouping%602> (`TKey` and `TElement` are covariant)</span></span>  
  
-   <span data-ttu-id="ab829-110"><xref:System.Collections.Generic.IComparer%601>(T는 반공변(contravariant)임)</span><span class="sxs-lookup"><span data-stu-id="ab829-110"><xref:System.Collections.Generic.IComparer%601> (T is contravariant)</span></span>  
  
-   <span data-ttu-id="ab829-111"><xref:System.Collections.Generic.IEqualityComparer%601>(T는 반공변(contravariant)임)</span><span class="sxs-lookup"><span data-stu-id="ab829-111"><xref:System.Collections.Generic.IEqualityComparer%601> (T is contravariant)</span></span>  
  
-   <span data-ttu-id="ab829-112"><xref:System.IComparable%601>(T는 반공변(contravariant)임)</span><span class="sxs-lookup"><span data-stu-id="ab829-112"><xref:System.IComparable%601> (T is contravariant)</span></span>  
  
 <span data-ttu-id="ab829-113">공변성(covariance)은 메서드가 인터페이스의 제네릭 형식 매개 변수에 정의된 것보다 더 많은 수의 파생된 반환 형식을 갖도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="ab829-113">Covariance permits a method to have a more derived return type than that defined by the generic type parameter of the interface.</span></span> <span data-ttu-id="ab829-114">공변성(covariance) 기능을 설명하려면 `IEnumerable(Of Object)` 및 `IEnumerable(Of String)`이라는 제네릭 인터페이스를 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="ab829-114">To illustrate the covariance feature, consider these generic interfaces: `IEnumerable(Of Object)` and `IEnumerable(Of String)`.</span></span> <span data-ttu-id="ab829-115">`IEnumerable(Of String)` 인터페이스는 `IEnumerable(Of Object)` 인터페이스를 상속하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ab829-115">The `IEnumerable(Of String)` interface does not inherit the `IEnumerable(Of Object)` interface.</span></span> <span data-ttu-id="ab829-116">그러나 `String` 형식은 `Object` 형식을 상속하며, 경우에 따라 이러한 인터페이스의 개체를 서로 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab829-116">However, the `String` type does inherit the `Object` type, and in some cases you may want to assign objects of these interfaces to each other.</span></span> <span data-ttu-id="ab829-117">다음 코드 예제에서 이를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab829-117">This is shown in the following code example.</span></span>  
  
```vb  
Dim strings As IEnumerable(Of String) = New List(Of String)  
Dim objects As IEnumerable(Of Object) = strings  
```  
  
 <span data-ttu-id="ab829-118">.NET Framework의 이전 버전에서는이 코드는 Visual basic으로 컴파일 오류가 발생 `Option Strict On`합니다.</span><span class="sxs-lookup"><span data-stu-id="ab829-118">In earlier versions of the .NET Framework, this code causes a compilation error in Visual Basic with `Option Strict On`.</span></span> <span data-ttu-id="ab829-119">그러나 <xref:System.Collections.Generic.IEnumerable%601> 인터페이스는 공변(covariant) 이므로 이제 다음 예제와 같이 `objects` 대신 `strings`를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab829-119">But now you can use `strings` instead of `objects`, as shown in the previous example, because the <xref:System.Collections.Generic.IEnumerable%601> interface is covariant.</span></span>  
  
 <span data-ttu-id="ab829-120">반공변성(Contravariance)은 메서드가 인터페이스의 제네릭 매개 변수에 지정된 것보다 더 적은 수의 파생된 형식의 인수 형식을 갖도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="ab829-120">Contravariance permits a method to have argument types that are less derived than that specified by the generic parameter of the interface.</span></span> <span data-ttu-id="ab829-121">반공변성(contravariance)을 설명하기 위해, 사용자가 `BaseComparer` 클래스를 만들어 `BaseClass` 클래스의 인스턴스를 비교한다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="ab829-121">To illustrate contravariance, assume that you have created a `BaseComparer` class to compare instances of the `BaseClass` class.</span></span> <span data-ttu-id="ab829-122">`BaseComparer` 클래스는 `IEqualityComparer(Of BaseClass)` 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="ab829-122">The `BaseComparer` class implements the `IEqualityComparer(Of BaseClass)` interface.</span></span> <span data-ttu-id="ab829-123"><xref:System.Collections.Generic.IEqualityComparer%601> 인터페이스는 이제 반공변(contravariant)이므로 `BaseClass` 클래스를 상속하는 클래스의 인스턴스를 비교하는 데 `BaseComparer`를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab829-123">Because the <xref:System.Collections.Generic.IEqualityComparer%601> interface is now contravariant, you can use `BaseComparer` to compare instances of classes that inherit the `BaseClass` class.</span></span> <span data-ttu-id="ab829-124">다음 코드 예제에서 이를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab829-124">This is shown in the following code example.</span></span>  
  
```vb  
' Simple hierarchy of classes.  
Class BaseClass  
End Class  
  
Class DerivedClass  
    Inherits BaseClass  
End Class  
  
' Comparer class.  
Class BaseComparer  
    Implements IEqualityComparer(Of BaseClass)  
  
    Public Function Equals1(ByVal x As BaseClass,  
                            ByVal y As BaseClass) As Boolean _  
                            Implements IEqualityComparer(Of BaseClass).Equals  
        Return (x.Equals(y))  
    End Function  
  
    Public Function GetHashCode1(ByVal obj As BaseClass) As Integer _  
        Implements IEqualityComparer(Of BaseClass).GetHashCode  
        Return obj.GetHashCode  
    End Function  
End Class  
Sub Test()  
    Dim baseComparer As IEqualityComparer(Of BaseClass) = New BaseComparer  
    ' Implicit conversion of IEqualityComparer(Of BaseClass) to   
    ' IEqualityComparer(Of DerivedClass).  
    Dim childComparer As IEqualityComparer(Of DerivedClass) = baseComparer  
End Sub  
```  
  
 <span data-ttu-id="ab829-125">더 많은 예제를 참조 하십시오. [(Visual Basic) 제네릭 컬렉션 용 인터페이스의 가변성 사용 하 여](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ab829-125">For more examples, see [Using Variance in Interfaces for Generic Collections (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md).</span></span>  
  
 <span data-ttu-id="ab829-126">제네릭 인터페이스의 가변성은 참조 형식에 대해서만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab829-126">Variance in generic interfaces is supported for reference types only.</span></span> <span data-ttu-id="ab829-127">값 형식은 가변성을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ab829-127">Value types do not support variance.</span></span> <span data-ttu-id="ab829-128">정수는 값 형식으로 표시되므로 예를 들어 `IEnumerable(Of Integer)`를 `IEnumerable(Of Object)`로 암시적으로 변환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ab829-128">For example, `IEnumerable(Of Integer)` cannot be implicitly converted to `IEnumerable(Of Object)`, because integers are represented by a value type.</span></span>  
  
```vb  
Dim integers As IEnumerable(Of Integer) = New List(Of Integer)  
' The following statement generates a compiler error  
' with Option Strict On, because Integer is a value type.  
' Dim objects As IEnumerable(Of Object) = integers  
```  
  
 <span data-ttu-id="ab829-129">Variant 인터페이스를 구현하는 클래스는 여전히 비 variant라는 점에 유의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab829-129">It is also important to remember that classes that implement variant interfaces are still invariant.</span></span> <span data-ttu-id="ab829-130">예를 들어 <xref:System.Collections.Generic.List%601>는 공변(covariant) 인터페이스 <xref:System.Collections.Generic.IEnumerable%601>을 구현하지만 암시적으로 `List(Of Object)`를 `List(Of String)`으로 변환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ab829-130">For example, although <xref:System.Collections.Generic.List%601> implements the covariant interface <xref:System.Collections.Generic.IEnumerable%601>, you cannot implicitly convert `List(Of Object)` to `List(Of String)`.</span></span> <span data-ttu-id="ab829-131">다음 코드 예제에서 이 내용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab829-131">This is illustrated in the following code example.</span></span>  
  
```vb  
' The following statement generates a compiler error  
' because classes are invariant.  
' Dim list As List(Of Object) = New List(Of String)  
  
' You can use the interface object instead.  
Dim listObjects As IEnumerable(Of Object) = New List(Of String)  
```  
  
## <a name="see-also"></a><span data-ttu-id="ab829-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ab829-132">See Also</span></span>  
 [<span data-ttu-id="ab829-133">제네릭 컬렉션용 인터페이스의 가변성 사용(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ab829-133">Using Variance in Interfaces for Generic Collections (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md)  
 [<span data-ttu-id="ab829-134">Variant 제네릭 인터페이스 만들기(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ab829-134">Creating Variant Generic Interfaces (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/creating-variant-generic-interfaces.md)  
 [<span data-ttu-id="ab829-135">제네릭 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ab829-135">Generic Interfaces</span></span>](../../../../standard/generics/interfaces.md)  
 [<span data-ttu-id="ab829-136">대리자의 가변성(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ab829-136">Variance in Delegates (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)
