---
title: '방법: 문자열 (LINQ) (Visual Basic)에 있는 문자에 대 한 쿼리'
ms.date: 07/20/2015
ms.assetid: 499ebbe0-746c-4235-9dba-ce722c12b50e
ms.openlocfilehash: 0953ff9152a4af1aa40379e15b2279d23ad0aac1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33642118"
---
# <a name="how-to-query-for-characters-in-a-string-linq-visual-basic"></a><span data-ttu-id="94968-102">방법: 문자열 (LINQ) (Visual Basic)에 있는 문자에 대 한 쿼리</span><span class="sxs-lookup"><span data-stu-id="94968-102">How to: Query for Characters in a String (LINQ) (Visual Basic)</span></span>
<span data-ttu-id="94968-103"><xref:System.String> 클래스는 제네릭 <xref:System.Collections.Generic.IEnumerable%601> 인터페이스를 구현하기 때문에 모든 문자열을 문자 시퀀스로 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94968-103">Because the <xref:System.String> class implements the generic <xref:System.Collections.Generic.IEnumerable%601> interface, any string can be queried as a sequence of characters.</span></span> <span data-ttu-id="94968-104">그러나 LINQ는 일반적으로 이 용도로 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="94968-104">However, this is not a common use of LINQ.</span></span> <span data-ttu-id="94968-105">복잡한 패턴 일치 작업의 경우 <xref:System.Text.RegularExpressions.Regex> 클래스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="94968-105">For complex pattern matching operations, use the <xref:System.Text.RegularExpressions.Regex> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="94968-106">예제</span><span class="sxs-lookup"><span data-stu-id="94968-106">Example</span></span>  
 <span data-ttu-id="94968-107">다음 예제에서는 문자열을 쿼리하여 문자열에 포함된 숫자 자릿수를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="94968-107">The following example queries a string to determine the number of numeric digits it contains.</span></span> <span data-ttu-id="94968-108">쿼리가 처음 실행된 후 "다시 사용"됩니다.</span><span class="sxs-lookup"><span data-stu-id="94968-108">Note that the query is "reused" after it is executed the first time.</span></span> <span data-ttu-id="94968-109">이 작업은 쿼리 자체가 실제 결과를 저장하지 않기 때문에 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="94968-109">This is possible because the query itself does not store any actual results.</span></span>  
  
```vb  
Class QueryAString  
  
    Shared Sub Main()  
  
        ' A string is an IEnumerable data source.  
        Dim aString As String = "ABCDE99F-J74-12-89A"  
  
        ' Select only those characters that are numbers  
        Dim stringQuery = From ch In aString   
                          Where Char.IsDigit(ch)   
                          Select ch  
        ' Execute the query  
        For Each c As Char In stringQuery  
            Console.Write(c & " ")  
        Next  
  
        ' Call the Count method on the existing query.  
        Dim count As Integer = stringQuery.Count()  
        Console.WriteLine(System.Environment.NewLine & "Count = " & count)  
  
        ' Select all characters before the first '-'  
        Dim stringQuery2 = aString.TakeWhile(Function(c) c <> "-")  
  
        ' Execute the second query  
        For Each ch In stringQuery2  
            Console.Write(ch)  
        Next  
  
        Console.WriteLine(System.Environment.NewLine & "Press any key to exit")  
        Console.ReadKey()  
    End Sub  
End Class  
' Output:  
' 9 9 7 4 1 2 8 9   
' Count = 8  
' ABCDE99F  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="94968-110">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="94968-110">Compiling the Code</span></span>  
 <span data-ttu-id="94968-111">System.Core.dll에 대한 참조와 System.Linq 네임스페이스에 대한 `Imports` 문을 사용하여 .NET Framework 버전 3.5 이상을 대상으로 하는 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="94968-111">Create a project that targets the .NET Framework version 3.5 or higher with a reference to System.Core.dll and a `Imports` statement for the System.Linq namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94968-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="94968-112">See Also</span></span>  
 [<span data-ttu-id="94968-113">LINQ 및 문자열 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="94968-113">LINQ and Strings (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)  
 [<span data-ttu-id="94968-114">방법: LINQ 쿼리와 정규식 (Visual Basic)를 결합 합니다.</span><span class="sxs-lookup"><span data-stu-id="94968-114">How to: Combine LINQ Queries with Regular Expressions (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-combine-linq-queries-with-regular-expressions.md)
