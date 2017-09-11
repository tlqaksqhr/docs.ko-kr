---
title: "(Visual Basic) 제네릭 컬렉션 용 인터페이스의 가변성 사용 | Microsoft 문서"
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
ms.assetid: c867fcea-7462-4995-b9c5-542feec74036
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
ms.openlocfilehash: 86184c7de3fe16148bf954b16d703ca682216337
ms.contentlocale: ko-kr
ms.lasthandoff: 03/13/2017

---
# <a name="using-variance-in-interfaces-for-generic-collections-visual-basic"></a><span data-ttu-id="6bc55-102">(Visual Basic) 제네릭 컬렉션 용 인터페이스의 가변성 사용</span><span class="sxs-lookup"><span data-stu-id="6bc55-102">Using Variance in Interfaces for Generic Collections (Visual Basic)</span></span>
<span data-ttu-id="6bc55-103">공변 (covariant) 인터페이스의 메서드를 인터페이스에 지정 된 것 보다 더 많은 파생된 형식을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bc55-103">A covariant interface allows its methods to return more derived types than those specified in the interface.</span></span> <span data-ttu-id="6bc55-104">반공 변 인터페이스의 메서드를 인터페이스에 지정 된 것 보다 더 적은 파생 형식의 매개 변수를 사용할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="6bc55-104">A contravariant interface allows its methods to accept parameters of less derived types than those specified in the interface.</span></span>  
  
 <span data-ttu-id="6bc55-105">.NET Framework 4에서는 몇 가지 기존 인터페이스가 공변 (covariant) 및 반공 변입니다.</span><span class="sxs-lookup"><span data-stu-id="6bc55-105">In .NET Framework 4, several existing interfaces became covariant and contravariant.</span></span> <span data-ttu-id="6bc55-106">여기에 <xref:System.Collections.Generic.IEnumerable%601>및 <xref:System.IComparable%601>.</xref:System.IComparable%601> </xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="6bc55-106">These include <xref:System.Collections.Generic.IEnumerable%601> and <xref:System.IComparable%601>.</span></span> <span data-ttu-id="6bc55-107">이 파생 형식의 컬렉션에 대 한 기본 형식의 제네릭 컬렉션과 함께 작동 하는 메서드를 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bc55-107">This enables you to reuse methods that operate with generic collections of base types for collections of derived types.</span></span>  
  
 <span data-ttu-id="6bc55-108">.NET Framework의 variant 인터페이스 목록은 참조 하십시오. [제네릭 인터페이스 (Visual Basic)에 대 한 분산](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6bc55-108">For a list of variant interfaces in the .NET Framework, see [Variance in Generic Interfaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md).</span></span>  
  
## <a name="converting-generic-collections"></a><span data-ttu-id="6bc55-109">제네릭 컬렉션 변환</span><span class="sxs-lookup"><span data-stu-id="6bc55-109">Converting Generic Collections</span></span>  
 <span data-ttu-id="6bc55-110">다음은 예제 공변성 (covariance) 지원의 혜택은 <xref:System.Collections.Generic.IEnumerable%601>인터페이스.</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="6bc55-110">The following example illustrates the benefits of covariance support in the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="6bc55-111">`PrintFullName` 메서드 컬렉션을 받아들여는 `IEnumerable(Of Person)` 형식을 매개 변수로 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bc55-111">The `PrintFullName` method accepts a collection of the `IEnumerable(Of Person)` type as a parameter.</span></span> <span data-ttu-id="6bc55-112">그러나 다시 사용할 컬렉션의는 `IEnumerable(Of Person)` 하기 때문에 입력 `Employee` 상속 `Person`합니다.</span><span class="sxs-lookup"><span data-stu-id="6bc55-112">However, you can reuse it for a collection of the `IEnumerable(Of Person)` type because `Employee` inherits `Person`.</span></span>  
  
<span data-ttu-id="6bc55-113"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="6bc55-113"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span></span>  
## <a name="comparing-generic-collections"></a><span data-ttu-id="6bc55-114">제네릭 컬렉션 비교</span><span class="sxs-lookup"><span data-stu-id="6bc55-114">Comparing Generic Collections</span></span>  
 <span data-ttu-id="6bc55-115">다음 예제에서는 반공 분산 지원의 혜택은 <xref:System.Collections.Generic.IComparer%601>인터페이스.</xref:System.Collections.Generic.IComparer%601></span><span class="sxs-lookup"><span data-stu-id="6bc55-115">The following example illustrates the benefits of contravariance support in the <xref:System.Collections.Generic.IComparer%601> interface.</span></span> <span data-ttu-id="6bc55-116">`PersonComparer` 클래스는 `IComparer(Of Person)` 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="6bc55-116">The `PersonComparer` class implements the `IComparer(Of Person)` interface.</span></span> <span data-ttu-id="6bc55-117">그러나 다시 사용할 수 있습니다 개체의 시퀀스를 비교 하려면이 클래스는 `Employee` 하기 때문에 입력 `Employee` 상속 `Person`합니다.</span><span class="sxs-lookup"><span data-stu-id="6bc55-117">However, you can reuse this class to compare a sequence of objects of the `Employee` type because `Employee` inherits `Person`.</span></span>  
  
```vb  
' Simple hierarhcy of classes.  
Public Class Person  
    Public Property FirstName As String  
    Public Property LastName As String  
End Class  
  
Public Class Employee  
    Inherits Person  
End Class  
' The custom comparer for the Person type  
' with standard implementations of Equals()  
' and GetHashCode() methods.  
Class PersonComparer  
    Implements IEqualityComparer(Of Person)  
  
    Public Function Equals1(  
        ByVal x As Person,  
        ByVal y As Person) As Boolean _  
        Implements IEqualityComparer(Of Person).Equals  
  
        If x Is y Then Return True  
        If x Is Nothing OrElse y Is Nothing Then Return False  
        Return (x.FirstName = y.FirstName) AndAlso  
            (x.LastName = y.LastName)  
    End Function  
    Public Function GetHashCode1(  
        ByVal person As Person) As Integer _  
        Implements IEqualityComparer(Of Person).GetHashCode  
  
        If person Is Nothing Then Return 0  
        Dim hashFirstName =  
            If(person.FirstName Is Nothing,  
            0, person.FirstName.GetHashCode())  
        Dim hashLastName = person.LastName.GetHashCode()  
        Return hashFirstName Xor hashLastName  
    End Function  
End Class  
  
Sub Main()  
    Dim employees = New List(Of Employee) From {  
        New Employee With {.FirstName = "Michael", .LastName = "Alexander"},  
        New Employee With {.FirstName = "Jeff", .LastName = "Price"}  
    }  
  
    ' You can pass PersonComparer,   
    ' which implements IEqualityComparer(Of Person),  
    ' although the method expects IEqualityComparer(Of Employee)  
  
    Dim noduplicates As IEnumerable(Of Employee) = employees.Distinct(New PersonComparer())  
  
    For Each employee In noduplicates  
        Console.WriteLine(employee.FirstName & " " & employee.LastName)  
    Next  
End Sub  
```  
  
## <a name="see-also"></a><span data-ttu-id="6bc55-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6bc55-118">See Also</span></span>  
 [<span data-ttu-id="6bc55-119">(Visual Basic) 제네릭 인터페이스의 가변성</span><span class="sxs-lookup"><span data-stu-id="6bc55-119">Variance in Generic Interfaces (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)
