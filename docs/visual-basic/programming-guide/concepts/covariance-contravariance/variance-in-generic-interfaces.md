---
title: "제네릭 인터페이스 (Visual Basic)에 대 한 분산 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: cf4096d0-4bb3-45a9-9a6b-f01e29a60333
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: c53c27bdb085213046553fc4b08f11336880a7c2
ms.contentlocale: ko-kr
ms.lasthandoff: 03/13/2017

---
# <a name="variance-in-generic-interfaces-visual-basic"></a><span data-ttu-id="f28fc-102">(Visual Basic) 제네릭 인터페이스의 가변성</span><span class="sxs-lookup"><span data-stu-id="f28fc-102">Variance in Generic Interfaces (Visual Basic)</span></span>
<span data-ttu-id="f28fc-103">.NET framework 4에는 여러 기존 제네릭 인터페이스에 대 한 분산 지원이 추가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f28fc-103">.NET Framework 4 introduced variance support for several existing generic interfaces.</span></span> <span data-ttu-id="f28fc-104">분산 지원을 통해 이러한 인터페이스를 구현 하는 클래스를 암시적으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f28fc-104">Variance support enables implicit conversion of classes that implement these interfaces.</span></span> <span data-ttu-id="f28fc-105">다음 인터페이스는 현재 variant:</span><span class="sxs-lookup"><span data-stu-id="f28fc-105">The following interfaces are now variant:</span></span>  
  
-   <span data-ttu-id="f28fc-106"><xref:System.Collections.Generic.IEnumerable%601>(T는 공변 (covariant))</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="f28fc-106"><xref:System.Collections.Generic.IEnumerable%601> (T is covariant)</span></span>  
  
-   <span data-ttu-id="f28fc-107"><xref:System.Collections.Generic.IEnumerator%601>(T는 공변 (covariant))</xref:System.Collections.Generic.IEnumerator%601></span><span class="sxs-lookup"><span data-stu-id="f28fc-107"><xref:System.Collections.Generic.IEnumerator%601> (T is covariant)</span></span>  
  
-   <span data-ttu-id="f28fc-108"><xref:System.Linq.IQueryable%601>(T는 공변 (covariant))</xref:System.Linq.IQueryable%601></span><span class="sxs-lookup"><span data-stu-id="f28fc-108"><xref:System.Linq.IQueryable%601> (T is covariant)</span></span>  
  
-   <span data-ttu-id="f28fc-109"><xref:System.Linq.IGrouping%602>(`TKey` 및 `TElement` 는 공변 (covariant))</xref:System.Linq.IGrouping%602></span><span class="sxs-lookup"><span data-stu-id="f28fc-109"><xref:System.Linq.IGrouping%602> (`TKey` and `TElement` are covariant)</span></span>  
  
-   <span data-ttu-id="f28fc-110"><xref:System.Collections.Generic.IComparer%601>(T는 반공 변)</xref:System.Collections.Generic.IComparer%601></span><span class="sxs-lookup"><span data-stu-id="f28fc-110"><xref:System.Collections.Generic.IComparer%601> (T is contravariant)</span></span>  
  
-   <span data-ttu-id="f28fc-111"><xref:System.Collections.Generic.IEqualityComparer%601>(T는 반공 변)</xref:System.Collections.Generic.IEqualityComparer%601></span><span class="sxs-lookup"><span data-stu-id="f28fc-111"><xref:System.Collections.Generic.IEqualityComparer%601> (T is contravariant)</span></span>  
  
-   <span data-ttu-id="f28fc-112"><xref:System.IComparable%601>(T는 반공 변)</xref:System.IComparable%601></span><span class="sxs-lookup"><span data-stu-id="f28fc-112"><xref:System.IComparable%601> (T is contravariant)</span></span>  
  
 <span data-ttu-id="f28fc-113">공변성 (covariance) 인터페이스의 제네릭 형식 매개 변수에 의해 정의 된 것 보다 더 많이 파생 된 반환 형식을 갖는 메서드를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f28fc-113">Covariance permits a method to have a more derived return type than that defined by the generic type parameter of the interface.</span></span> <span data-ttu-id="f28fc-114">공변성 (covariance) 기능을 설명 하기 위해 이러한 제네릭 인터페이스를 고려: `IEnumerable(Of Object)` 및 `IEnumerable(Of String)`합니다.</span><span class="sxs-lookup"><span data-stu-id="f28fc-114">To illustrate the covariance feature, consider these generic interfaces: `IEnumerable(Of Object)` and `IEnumerable(Of String)`.</span></span> <span data-ttu-id="f28fc-115">`IEnumerable(Of String)` 인터페이스를 상속 하지 않는 `IEnumerable(Of Object)` 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="f28fc-115">The `IEnumerable(Of String)` interface does not inherit the `IEnumerable(Of Object)` interface.</span></span> <span data-ttu-id="f28fc-116">그러나는 `String` 형식 상속지 않습니다는 `Object` 형식의 경우에 따라 서로 이러한 인터페이스의 개체를 할당 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f28fc-116">However, the `String` type does inherit the `Object` type, and in some cases you may want to assign objects of these interfaces to each other.</span></span> <span data-ttu-id="f28fc-117">이 다음 코드 예제에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f28fc-117">This is shown in the following code example.</span></span>  
  
<span data-ttu-id="f28fc-118"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="f28fc-118"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="f28fc-119">.NET Framework의 이전 버전에서는이 코드는 Visual basic에서 컴파일 오류가 발생 `Option Strict On`합니다.</span><span class="sxs-lookup"><span data-stu-id="f28fc-119">In earlier versions of the .NET Framework, this code causes a compilation error in Visual Basic with `Option Strict On`.</span></span> <span data-ttu-id="f28fc-120">이제 사용할 수 있지만 `strings` 대신 `objects`때문에 앞의 예제에 표시 된 것 처럼는 <xref:System.Collections.Generic.IEnumerable%601>인터페이스는 공변 (covariant).</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="f28fc-120">But now you can use `strings` instead of `objects`, as shown in the previous example, because the <xref:System.Collections.Generic.IEnumerable%601> interface is covariant.</span></span>  
  
 <span data-ttu-id="f28fc-121">반 공변성 인터페이스의 제네릭 매개 변수로 지정 된 것 보다 더 적게 파생 된 인수 형식을 갖는 메서드를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f28fc-121">Contravariance permits a method to have argument types that are less derived than that specified by the generic parameter of the interface.</span></span> <span data-ttu-id="f28fc-122">를 설명 하기 위해 반 공변성을 만들었다고 가정는 `BaseComparer` 클래스의 인스턴스를 비교 하는 `BaseClass` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="f28fc-122">To illustrate contravariance, assume that you have created a `BaseComparer` class to compare instances of the `BaseClass` class.</span></span> <span data-ttu-id="f28fc-123">`BaseComparer` 클래스는 `IEqualityComparer(Of BaseClass)` 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="f28fc-123">The `BaseComparer` class implements the `IEqualityComparer(Of BaseClass)` interface.</span></span> <span data-ttu-id="f28fc-124">때문에 <xref:System.Collections.Generic.IEqualityComparer%601>인터페이스는 이제 반공 변을 사용할 수 있습니다 `BaseComparer` 상속 하는 클래스의 인스턴스를 비교 하는 `BaseClass` 클래스</xref:System.Collections.Generic.IEqualityComparer%601></span><span class="sxs-lookup"><span data-stu-id="f28fc-124">Because the <xref:System.Collections.Generic.IEqualityComparer%601> interface is now contravariant, you can use `BaseComparer` to compare instances of classes that inherit the `BaseClass` class.</span></span> <span data-ttu-id="f28fc-125">이 다음 코드 예제에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f28fc-125">This is shown in the following code example.</span></span>  
  
<span data-ttu-id="f28fc-126"><CodeContentPlaceHolder>1</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="f28fc-126"><CodeContentPlaceHolder>1</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="f28fc-127">더 많은 예제를 참조 하십시오. [(Visual Basic) 제네릭 컬렉션 용 인터페이스의 가변성 사용 하 여](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f28fc-127">For more examples, see [Using Variance in Interfaces for Generic Collections (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md).</span></span>  
  
 <span data-ttu-id="f28fc-128">제네릭 인터페이스의 가변성은 참조 형식 에서만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f28fc-128">Variance in generic interfaces is supported for reference types only.</span></span> <span data-ttu-id="f28fc-129">값 형식 차이 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f28fc-129">Value types do not support variance.</span></span> <span data-ttu-id="f28fc-130">예를 들어 `IEnumerable(Of Integer)` 로 암시적으로 변환할 수 없는 `IEnumerable(Of Object)`이므로 정수 값 형식으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f28fc-130">For example, `IEnumerable(Of Integer)` cannot be implicitly converted to `IEnumerable(Of Object)`, because integers are represented by a value type.</span></span>  
  
<span data-ttu-id="f28fc-131"><CodeContentPlaceHolder>2</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="f28fc-131"><CodeContentPlaceHolder>2</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="f28fc-132">Variant 인터페이스를 구현 하는 클래스는 여전히 고정 하는 것이 중요 이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="f28fc-132">It is also important to remember that classes that implement variant interfaces are still invariant.</span></span> <span data-ttu-id="f28fc-133">예를 들어 있지만 <xref:System.Collections.Generic.List%601>공변 (covariant) 인터페이스를 구현 <xref:System.Collections.Generic.IEnumerable%601>, 암시적으로 변환할 수 없습니다 `List(Of Object)` 를 `List(Of String)`.</xref:System.Collections.Generic.IEnumerable%601> </xref:System.Collections.Generic.List%601></span><span class="sxs-lookup"><span data-stu-id="f28fc-133">For example, although <xref:System.Collections.Generic.List%601> implements the covariant interface <xref:System.Collections.Generic.IEnumerable%601>, you cannot implicitly convert `List(Of Object)` to `List(Of String)`.</span></span> <span data-ttu-id="f28fc-134">다음 코드 예제에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f28fc-134">This is illustrated in the following code example.</span></span>  
  
```vb  
' The following statement generates a compiler error  
' because classes are invariant.  
' Dim list As List(Of Object) = New List(Of String)  
  
' You can use the interface object instead.  
Dim listObjects As IEnumerable(Of Object) = New List(Of String)  
```  
  
## <a name="see-also"></a><span data-ttu-id="f28fc-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f28fc-135">See Also</span></span>  
 <span data-ttu-id="f28fc-136">[(Visual Basic) 제네릭 컬렉션 용 인터페이스의 가변성 사용](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md) </span><span class="sxs-lookup"><span data-stu-id="f28fc-136">[Using Variance in Interfaces for Generic Collections (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md) </span></span>  
<span data-ttu-id="f28fc-137"> [Variant 제네릭 인터페이스 만들기 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/creating-variant-generic-interfaces.md) </span><span class="sxs-lookup"><span data-stu-id="f28fc-137"> [Creating Variant Generic Interfaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/creating-variant-generic-interfaces.md) </span></span>  
<span data-ttu-id="f28fc-138"> [제네릭 인터페이스](http://msdn.microsoft.com/library/88bf5b04-d371-4edb-ba38-01ec7cabaacf) </span><span class="sxs-lookup"><span data-stu-id="f28fc-138"> [Generic Interfaces](http://msdn.microsoft.com/library/88bf5b04-d371-4edb-ba38-01ec7cabaacf) </span></span>  
<span data-ttu-id="f28fc-139"> [(Visual Basic) 대리자의 가변성](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)</span><span class="sxs-lookup"><span data-stu-id="f28fc-139"> [Variance in Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)</span></span>
