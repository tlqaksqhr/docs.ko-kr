---
title: '방법: LINQ () (Visual Basic) 문자열 컬렉션 결합 및 비교'
ms.date: 07/20/2015
ms.assetid: 243cfafc-9eaa-4354-a9df-d329f1d39913
ms.openlocfilehash: 0e8df8e6e324b2a575fb6232c54a223cb35a4ef2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33644448"
---
# <a name="how-to-combine-and-compare-string-collections-linq-visual-basic"></a><span data-ttu-id="d587c-102">방법: LINQ () (Visual Basic) 문자열 컬렉션 결합 및 비교</span><span class="sxs-lookup"><span data-stu-id="d587c-102">How to: Combine and Compare String Collections (LINQ) (Visual Basic)</span></span>
<span data-ttu-id="d587c-103">이 예제에서는 텍스트 줄이 포함된 파일을 병합하고 결과를 정렬하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d587c-103">This example shows how to merge files that contain lines of text and then sort the results.</span></span> <span data-ttu-id="d587c-104">특히, 두 개의 텍스트 줄 집합에 대한 단순 연결, 합집합 및 교집합을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d587c-104">Specifically, it shows how to perform a simple concatenation, a union, and an intersection on the two sets of text lines.</span></span>  
  
### <a name="to-set-up-the-project-and-the-text-files"></a><span data-ttu-id="d587c-105">프로젝트 및 텍스트 파일을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="d587c-105">To set up the project and the text files</span></span>  
  
1.  <span data-ttu-id="d587c-106">이러한 이름을 names1.txt 텍스트 파일에 복사하고 파일을 프로젝트 폴더에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="d587c-106">Copy these names into a text file that is named names1.txt and save it in your project folder:</span></span>  
  
    ```  
    Bankov, Peter  
    Holm, Michael  
    Garcia, Hugo  
    Potra, Cristina  
    Noriega, Fabricio  
    Aw, Kam Foo  
    Beebe, Ann  
    Toyoshima, Tim  
    Guy, Wey Yuan  
    Garcia, Debra  
    ```  
  
2.  <span data-ttu-id="d587c-107">이러한 이름을 names2.txt 텍스트 파일에 복사하고 파일을 프로젝트 폴더에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="d587c-107">Copy these names into a text file that is named names2.txt and save it in your project folder.</span></span> <span data-ttu-id="d587c-108">두 파일의 일부 이름에는 공통점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d587c-108">Note that the two files have some names in common.</span></span>  
  
    ```  
    Liu, Jinghao  
    Bankov, Peter  
    Holm, Michael  
    Garcia, Hugo  
    Beebe, Ann  
    Gilchrist, Beth  
    Myrcha, Jacek  
    Giakoumakis, Leo  
    McLin, Nkenge  
    El Yassir, Mehdi  
    ```  
  
## <a name="example"></a><span data-ttu-id="d587c-109">예제</span><span class="sxs-lookup"><span data-stu-id="d587c-109">Example</span></span>  
  
```vb  
Class ConcatenateStrings  
    Shared Sub Main()  
  
        ' Create the IEnumerable data sources.  
        Dim fileA As String() = System.IO.File.ReadAllLines("../../../names1.txt")  
        Dim fileB As String() = System.IO.File.ReadAllLines("../../../names2.txt")  
  
        ' Simple concatenation and sort.  
        Dim concatQuery = fileA.Concat(fileB).OrderBy(Function(name) name)  
  
        ' Pass the query variable to another function for execution  
        OutputQueryResults(concatQuery, "Simple concatenation and sort. Duplicates are preserved:")  
  
        ' New query. Concatenate files and remove duplicates  
        Dim uniqueNamesQuery = fileA.Union(fileB).OrderBy(Function(name) name)  
        OutputQueryResults(uniqueNamesQuery, "Union removes duplicate names:")  
  
        ' New query. Find the names that occur in both files.  
        Dim commonNamesQuery = fileA.Intersect(fileB)  
        OutputQueryResults(commonNamesQuery, "Merge based on intersect: ")  
  
        ' New query in three steps for better readability   
        ' First filter each list separately  
  
        Dim nameToSearch As String = "Garcia"  
        Dim mergeQueryA As IEnumerable(Of String) = From name In fileA   
                          Let n = name.Split(New Char() {","})   
                          Where n(0) = nameToSearch   
                          Select name  
  
        Dim mergeQueryB = From name In fileB   
                          Let n = name.Split(New Char() {","})   
                          Where n(0) = nameToSearch   
                          Select name  
  
        ' Create a new query to concatenate and sort results. Duplicates are removed in Union.  
        ' Note that none of the queries actually executed until the call to OutputQueryResults.  
        Dim mergeSortQuery = mergeQueryA.Union(mergeQueryB).OrderBy(Function(str) str)  
  
        ' Now execute mergeSortQuery  
        OutputQueryResults(mergeSortQuery, "Concat based on partial name match """ & nameToSearch & """ from each list:")  
  
        ' Keep console window open in debug mode.  
        Console.WriteLine("Press any key to exit.")  
        Console.ReadKey()  
  
    End Sub  
  
    Shared Sub OutputQueryResults(ByVal query As IEnumerable(Of String), ByVal message As String)  
  
        Console.WriteLine(System.Environment.NewLine & message)  
        For Each item As String In query  
            Console.WriteLine(item)  
        Next  
        Console.WriteLine(query.Count & " total names in list")  
  
    End Sub  
End Class  
' Output:  
  
' Simple concatenation and sort. Duplicates are preserved:  
' Aw, Kam Foo  
' Bankov, Peter  
' Bankov, Peter  
' Beebe, Ann  
' Beebe, Ann  
' El Yassir, Mehdi  
' Garcia, Debra  
' Garcia, Hugo  
' Garcia, Hugo  
' Giakoumakis, Leo  
' Gilchrist, Beth  
' Guy, Wey Yuan  
' Holm, Michael  
' Holm, Michael  
' Liu, Jinghao  
' McLin, Nkenge  
' Myrcha, Jacek  
' Noriega, Fabricio  
' Potra, Cristina  
' Toyoshima, Tim  
' 20 total names in list  
  
' Union removes duplicate names:  
' Aw, Kam Foo  
' Bankov, Peter  
' Beebe, Ann  
' El Yassir, Mehdi  
' Garcia, Debra  
' Garcia, Hugo  
' Giakoumakis, Leo  
' Gilchrist, Beth  
' Guy, Wey Yuan  
' Holm, Michael  
' Liu, Jinghao  
' McLin, Nkenge  
' Myrcha, Jacek  
' Noriega, Fabricio  
' Potra, Cristina  
' Toyoshima, Tim  
' 16 total names in list  
  
' Merge based on intersect:  
' Bankov, Peter  
' Holm, Michael  
' Garcia, Hugo  
' Beebe, Ann  
' 4 total names in list  
  
' Concat based on partial name match "Garcia" from each list:  
' Garcia, Debra  
' Garcia, Hugo  
' 2 total names in list  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d587c-110">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="d587c-110">Compiling the Code</span></span>  
 <span data-ttu-id="d587c-111">System.Core.dll에 대한 참조와 System.Linq 네임스페이스에 대한 `Imports` 문을 사용하여 .NET Framework 버전 3.5 이상을 대상으로 하는 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d587c-111">Create a project that targets the .NET Framework version 3.5 or higher with a reference to System.Core.dll and a `Imports` statement for the System.Linq namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d587c-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d587c-112">See Also</span></span>  
 [<span data-ttu-id="d587c-113">LINQ 및 문자열 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d587c-113">LINQ and Strings (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)  
 [<span data-ttu-id="d587c-114">LINQ 및 파일 디렉터리(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d587c-114">LINQ and File Directories (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)
