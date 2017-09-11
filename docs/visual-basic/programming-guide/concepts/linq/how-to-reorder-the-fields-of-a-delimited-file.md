---
title: "방법: 구분된 된 파일 (Visual Basic) (LINQ)의 필드 다시 정렬 | Microsoft 문서"
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
ms.assetid: c451c7db-663b-4daf-b8ba-a2093095d672
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
ms.openlocfilehash: 8540dff06e146a1846063e11e3382e9457f9e412
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-reorder-the-fields-of-a-delimited-file-linq-visual-basic"></a><span data-ttu-id="e2d40-102">방법: 구분된 된 파일 (Visual Basic) (LINQ)의 필드 다시 정렬</span><span class="sxs-lookup"><span data-stu-id="e2d40-102">How to: Reorder the Fields of a Delimited File (LINQ) (Visual Basic)</span></span>
<span data-ttu-id="e2d40-103">쉼표로 구분 된 값 (CSV) 파일은은 행과 열으로 표현 되는 다른 테이블 형식 데이터 나 스프레드시트 데이터를 저장 하는 데 자주 사용 하는 텍스트 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="e2d40-103">A comma-separated value (CSV) file is a text file that is often used to store spreadsheet data or other tabular data that is represented by rows and columns.</span></span> <span data-ttu-id="e2d40-104">사용 하 여는 <xref:System.String.Split%2A>필드를 구분 하는 메서드를 쿼리하고 LINQ를 사용 하 여 CSV 파일 조작 매우 쉽습니다.</xref:System.String.Split%2A></span><span class="sxs-lookup"><span data-stu-id="e2d40-104">By using the <xref:System.String.Split%2A> method to separate the fields, it is very easy to query and manipulate CSV files by using LINQ.</span></span> <span data-ttu-id="e2d40-105">실제로 동일한 기법 데 사용할 수는 텍스트의 구조화 된 줄의 일부를 다시 정렬 CSV 파일에 제한 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e2d40-105">In fact, the same technique can be used to reorder the parts of any structured line of text; it is not limited to CSV files.</span></span>  
  
 <span data-ttu-id="e2d40-106">다음 예제에서는 세 열에서는 학생의 "last name," 나타낸다고 가정해 봅시다 "first name" 및 "id"입니다.</span><span class="sxs-lookup"><span data-stu-id="e2d40-106">In the following example, assume that the three columns represent students' "last name," "first name", and "ID."</span></span> <span data-ttu-id="e2d40-107">필드는 학생의 성을 기준으로 알파벳 순서에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2d40-107">The fields are in alphabetical order based on the students' last names.</span></span> <span data-ttu-id="e2d40-108">쿼리 표시 되는 ID 열, 첫 번째 학생의 첫 번째 이름과 마지막 이름을 결합 하는 두 번째 열 뒤에 새 시퀀스를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2d40-108">The query produces a new sequence in which the ID column appears first, followed by a second column that combines the student's first name and last name.</span></span> <span data-ttu-id="e2d40-109">줄 ID 필드에 따라 다시 정렬 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2d40-109">The lines are reordered according to the ID field.</span></span> <span data-ttu-id="e2d40-110">결과 새 파일에 저장 되며 및 원래 데이터가 수정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e2d40-110">The results are saved into a new file and the original data is not modified.</span></span>  
  
### <a name="to-create-the-data-file"></a><span data-ttu-id="e2d40-111">데이터 파일을 만들려면</span><span class="sxs-lookup"><span data-stu-id="e2d40-111">To create the data file</span></span>  
  
1.  <span data-ttu-id="e2d40-112">Spreadsheet1.csv 라는 일반 텍스트 파일에 다음 줄을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2d40-112">Copy the following lines into a plain text file that is named spreadsheet1.csv.</span></span> <span data-ttu-id="e2d40-113">프로젝트 폴더에 파일을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2d40-113">Save the file in your project folder.</span></span>  
  
    ```  
    Adams,Terry,120  
    Fakhouri,Fadi,116  
    Feng,Hanying,117  
    Garcia,Cesar,114  
    Garcia,Debra,115  
    Garcia,Hugo,118  
    Mortensen,Sven,113  
    O'Donnell,Claire,112  
    Omelchenko,Svetlana,111  
    Tucker,Lance,119  
    Tucker,Michael,122  
    Zabokritski,Eugene,121  
    ```  
  
## <a name="example"></a><span data-ttu-id="e2d40-114">예제</span><span class="sxs-lookup"><span data-stu-id="e2d40-114">Example</span></span>  
  
```vb  
Class CSVFiles  
  
    Shared Sub Main()  
  
        ' Create the IEnumerable data source.  
        Dim lines As String() = System.IO.File.ReadAllLines("../../../spreadsheet1.csv")  
  
        ' Execute the query. Put field 2 first, then  
        ' reverse and combine fields 0 and 1 from the old field  
        Dim lineQuery = From line In lines   
                        Let x = line.Split(New Char() {","})   
                        Order By x(2)   
                        Select x(2) & ", " & (x(1) & " " & x(0))  
  
        ' Execute the query and write out the new file. Note that WriteAllLines  
        ' takes a string array, so ToArray is called on the query.  
        System.IO.File.WriteAllLines("../../../spreadsheet2.csv", lineQuery.ToArray())  
  
        ' Keep console window open in debug mode.  
        Console.WriteLine("Spreadsheet2.csv written to disk. Press any key to exit")  
        Console.ReadKey()  
    End Sub  
End Class  
' Output to spreadsheet2.csv:  
' 111, Svetlana Omelchenko  
' 112, Claire O'Donnell  
' 113, Sven Mortensen  
' 114, Cesar Garcia  
' 115, Debra Garcia  
' 116, Fadi Fakhouri  
' 117, Hanying Feng  
' 118, Hugo Garcia  
' 119, Lance Tucker  
' 120, Terry Adams  
' 121, Eugene Zabokritski  
' 122, Michael Tucker  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e2d40-115">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="e2d40-115">Compiling the Code</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2d40-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e2d40-116">See Also</span></span>  
 <span data-ttu-id="e2d40-117">[LINQ 및 문자열 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md) </span><span class="sxs-lookup"><span data-stu-id="e2d40-117">[LINQ and Strings (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md) </span></span>  
<span data-ttu-id="e2d40-118"> [LINQ 및 파일 디렉터리 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md) </span><span class="sxs-lookup"><span data-stu-id="e2d40-118"> [LINQ and File Directories (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md) </span></span>  
<span data-ttu-id="e2d40-119"> [방법: CSV 파일에서 XML 생성](http://msdn.microsoft.com/library/dd7bab8c-96fa-4343-94d0-9739dd6a74fd)</span><span class="sxs-lookup"><span data-stu-id="e2d40-119"> [How to: Generate XML from CSV Files](http://msdn.microsoft.com/library/dd7bab8c-96fa-4343-94d0-9739dd6a74fd)</span></span>
