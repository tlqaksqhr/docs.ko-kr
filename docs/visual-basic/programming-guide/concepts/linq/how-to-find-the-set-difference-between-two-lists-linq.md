---
title: "방법: 두 목록 (Visual Basic) (LINQ) 간의 차집합 구하기 | Microsoft 문서"
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
ms.assetid: b5b25474-10a8-4df6-aab5-75621bb6b68e
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 9c00a66c79e080211c92457c0194462698fee98f
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-find-the-set-difference-between-two-lists-linq-visual-basic"></a><span data-ttu-id="ed727-102">방법: 두 목록 (Visual Basic) (LINQ) 간의 차집합 구하기</span><span class="sxs-lookup"><span data-stu-id="ed727-102">How to: Find the Set Difference Between Two Lists (LINQ) (Visual Basic)</span></span>
<span data-ttu-id="ed727-103">이 예제에서는 LINQ를 문자열의 두 목록을 비교 하 고 names2.txt에 없지만 names1.txt에 있는 해당 줄을 출력을 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ed727-103">This example shows how to use LINQ to compare two lists of strings and output those lines that are in names1.txt but not in names2.txt.</span></span>  
  
### <a name="to-create-the-data-files"></a><span data-ttu-id="ed727-104">데이터 파일을 만들려면</span><span class="sxs-lookup"><span data-stu-id="ed727-104">To create the data files</span></span>  
  
1.  <span data-ttu-id="ed727-105">에 표시 된 대로 names1.txt 및 names2.txt 솔루션 폴더에 복사 [하는 방법: 결합 및 비교 문자열 컬렉션 (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-combine-and-compare-string-collections-linq.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ed727-105">Copy names1.txt and names2.txt to your solution folder as shown in [How to: Combine and Compare String Collections (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-combine-and-compare-string-collections-linq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ed727-106">예제</span><span class="sxs-lookup"><span data-stu-id="ed727-106">Example</span></span>  
  
```vb  
Class CompareLists  
  
    Shared Sub Main()  
  
        ' Create the IEnumerable data sources.  
        Dim names1 As String() = System.IO.File.ReadAllLines("../../../names1.txt")  
        Dim names2 As String() = System.IO.File.ReadAllLines("../../../names2.txt")  
  
        ' Create the query. Note that method syntax must be used here.  
        Dim differenceQuery = names1.Except(names2)  
        Console.WriteLine("The following lines are in names1.txt but not names2.txt")  
  
        ' Execute the query.  
        For Each name As String In differenceQuery  
            Console.WriteLine(name)  
        Next  
  
        ' Keep console window open in debug mode.  
        Console.WriteLine("Press any key to exit.")  
        Console.ReadKey()  
    End Sub  
End Class  
' Output:  
' The following lines are in names1.txt but not names2.txt  
' Potra, Cristina  
' Noriega, Fabricio  
' Aw, Kam Foo  
' Toyoshima, Tim  
' Guy, Wey Yuan  
' Garcia, Debra  
```  
  
 <span data-ttu-id="ed727-107">와 같은 일부 유형의 쿼리 Visual Basic에서 작업 <xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Union%2A>, 및 <xref:System.Linq.Enumerable.Concat%2A>, 메서드 기반 구문을 으로만 표시 될 수 있습니다.</xref:System.Linq.Enumerable.Concat%2A> </xref:System.Linq.Enumerable.Union%2A> </xref:System.Linq.Enumerable.Distinct%2A> </xref:System.Linq.Enumerable.Except%2A></span><span class="sxs-lookup"><span data-stu-id="ed727-107">Some types of query operations in Visual Basic, such as <xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Union%2A>, and <xref:System.Linq.Enumerable.Concat%2A>, can only be expressed in method-based syntax.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ed727-108">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="ed727-108">Compiling the Code</span></span>  
 <span data-ttu-id="ed727-109">.NET Framework 버전 3.5 이상 System.Core.dll에 대 한 참조를 대상으로 하는 프로젝트 만들기 및 `Imports` System.Linq 네임 스페이스에 대 한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="ed727-109">Create a project that targets the .NET Framework version 3.5 or higher with a reference to System.Core.dll and a `Imports` statement for the System.Linq namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed727-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ed727-110">See Also</span></span>  
 [<span data-ttu-id="ed727-111">LINQ 및 문자열 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ed727-111">LINQ and Strings (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)
