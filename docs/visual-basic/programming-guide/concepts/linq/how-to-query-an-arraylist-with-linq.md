---
title: '방법: LINQ (Visual Basic)를 사용 하 여 ArrayList 쿼리'
ms.date: 07/20/2015
ms.assetid: 176358a9-d765-4b57-9557-7feb4428138d
ms.openlocfilehash: 24865842d073dbd4cbb60fe4a228520e98010f4d
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36207248"
---
# <a name="how-to-query-an-arraylist-with-linq-visual-basic"></a><span data-ttu-id="313fc-102">방법: LINQ (Visual Basic)를 사용 하 여 ArrayList 쿼리</span><span class="sxs-lookup"><span data-stu-id="313fc-102">How to: Query an ArrayList with LINQ (Visual Basic)</span></span>
<span data-ttu-id="313fc-103">LINQ를 사용하여 <xref:System.Collections.ArrayList> 등의 제네릭이 아닌 <xref:System.Collections.IEnumerable> 컬렉션을 쿼리하는 경우 컬렉션에 있는 개체의 특정 형식을 반영하도록 범위 변수의 형식을 명시적으로 선언해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="313fc-103">When using LINQ to query non-generic <xref:System.Collections.IEnumerable> collections such as <xref:System.Collections.ArrayList>, you must explicitly declare the type of the range variable to reflect the specific type of the objects in the collection.</span></span> <span data-ttu-id="313fc-104">예를 들어, 있는 경우는 <xref:System.Collections.ArrayList> 의 `Student` 개체 프로그램 [From 절이](../../../../visual-basic/language-reference/queries/from-clause.md) 다음과 같이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="313fc-104">For example, if you have an <xref:System.Collections.ArrayList> of `Student` objects, your [From Clause](../../../../visual-basic/language-reference/queries/from-clause.md) should look like this:</span></span>  
  
```  
Dim query = From student As Student In arrList   
...  
```  
  
 <span data-ttu-id="313fc-105">범위 변수의 형식을 지정하여 <xref:System.Collections.ArrayList>의 각 항목을 `Student`로 캐스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="313fc-105">By specifying the type of the range variable, you are casting each item in the <xref:System.Collections.ArrayList> to a `Student`.</span></span>  
  
 <span data-ttu-id="313fc-106">명시적 형식 범위 변수를 쿼리 식에 사용하는 것은 <xref:System.Linq.Enumerable.Cast%2A> 메서드 호출과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="313fc-106">The use of an explicitly typed range variable in a query expression is equivalent to calling the <xref:System.Linq.Enumerable.Cast%2A> method.</span></span> <span data-ttu-id="313fc-107">지정된 캐스트를 수행할 수 없는 경우 <xref:System.Linq.Enumerable.Cast%2A>에서 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="313fc-107"><xref:System.Linq.Enumerable.Cast%2A> throws an exception if the specified cast cannot be performed.</span></span> <span data-ttu-id="313fc-108"><xref:System.Linq.Enumerable.Cast%2A> 및 <xref:System.Linq.Enumerable.OfType%2A>은 제네릭이 아닌 <xref:System.Collections.IEnumerable> 형식에서 작동하는 두 가지 표준 쿼리 연산자 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="313fc-108"><xref:System.Linq.Enumerable.Cast%2A> and <xref:System.Linq.Enumerable.OfType%2A> are the two Standard Query Operator methods that operate on non-generic <xref:System.Collections.IEnumerable> types.</span></span> <span data-ttu-id="313fc-109">Visual Basic의 경우 명시적으로 호출 해야는 <xref:System.Linq.Enumerable.Cast%2A> 특정 범위 변수 유형 되도록 데이터 원본에 대해 메서드.</span><span class="sxs-lookup"><span data-stu-id="313fc-109">In Visual Basic, you must explicitly call the <xref:System.Linq.Enumerable.Cast%2A> method on the data source to ensure a specific range variable type.</span></span> <span data-ttu-id="313fc-110">자세한 내용은 참조 [쿼리 작업 (Visual Basic)의 형식 관계](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="313fc-110">For more information, see [Type Relationships in Query Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="313fc-111">예</span><span class="sxs-lookup"><span data-stu-id="313fc-111">Example</span></span>  
 <span data-ttu-id="313fc-112">다음 예제에서는 <xref:System.Collections.ArrayList>에 대한 단순 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="313fc-112">The following example shows a simple query over an <xref:System.Collections.ArrayList>.</span></span> <span data-ttu-id="313fc-113">이 예제에서는 코드가 <xref:System.Collections.ArrayList.Add%2A> 메서드를 호출할 때 개체 이니셜라이저를 사용하지만 요구 사항은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="313fc-113">Note that this example uses object initializers when the code calls the <xref:System.Collections.ArrayList.Add%2A> method, but this is not a requirement.</span></span>  
  
```vb  
Imports System.Collections  
Imports System.Linq  
  
Module Module1  
  
    Public Class Student  
        Public Property FirstName As String  
        Public Property LastName As String  
        Public Property Scores As Integer()  
    End Class  
  
    Sub Main()  
  
        Dim student1 As New Student With {.FirstName = "Svetlana",   
                                     .LastName = "Omelchenko",   
                                     .Scores = New Integer() {98, 92, 81, 60}}  
        Dim student2 As New Student With {.FirstName = "Claire",   
                                    .LastName = "O'Donnell",   
                                    .Scores = New Integer() {75, 84, 91, 39}}  
        Dim student3 As New Student With {.FirstName = "Cesar",   
                                    .LastName = "Garcia",   
                                    .Scores = New Integer() {97, 89, 85, 82}}  
        Dim student4 As New Student With {.FirstName = "Sven",   
                                    .LastName = "Mortensen",   
                                    .Scores = New Integer() {88, 94, 65, 91}}  
  
        Dim arrList As New ArrayList()  
        arrList.Add(student1)  
        arrList.Add(student2)  
        arrList.Add(student3)  
        arrList.Add(student4)  
  
        ' Use an explicit type for non-generic collections  
        Dim query = From student As Student In arrList   
                    Where student.Scores(0) > 95   
                    Select student  
  
        For Each student As Student In query  
            Console.WriteLine(student.LastName & ": " & student.Scores(0))  
        Next  
        ' Keep the console window open in debug mode.  
        Console.WriteLine("Press any key to exit.")  
        Console.ReadKey()  
    End Sub  
  
End Module  
' Output:  
'   Omelchenko: 98  
'   Garcia: 97  
```  
  
## <a name="see-also"></a><span data-ttu-id="313fc-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="313fc-114">See Also</span></span>  
 [<span data-ttu-id="313fc-115">LINQ to Objects(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="313fc-115">LINQ to Objects (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)
