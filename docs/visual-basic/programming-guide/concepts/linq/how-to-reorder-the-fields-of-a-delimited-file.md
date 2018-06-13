---
title: '방법: 구분 기호로 분리 된 파일 (LINQ) (Visual Basic)의 필드 순서'
ms.date: 07/20/2015
ms.assetid: c451c7db-663b-4daf-b8ba-a2093095d672
ms.openlocfilehash: 4bef55c35311672ab3f28c2ce04a64e1cd21c170
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33642043"
---
# <a name="how-to-reorder-the-fields-of-a-delimited-file-linq-visual-basic"></a><span data-ttu-id="bdb5b-102">방법: 구분 기호로 분리 된 파일 (LINQ) (Visual Basic)의 필드 순서</span><span class="sxs-lookup"><span data-stu-id="bdb5b-102">How to: Reorder the Fields of a Delimited File (LINQ) (Visual Basic)</span></span>
<span data-ttu-id="bdb5b-103">쉼표로 구분된 값(CSV) 파일은 스프레드시트 데이터 또는 행과 열로 표현되는 다른 테이블 형식 데이터를 저장하는 데 자주 사용되는 텍스트 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="bdb5b-103">A comma-separated value (CSV) file is a text file that is often used to store spreadsheet data or other tabular data that is represented by rows and columns.</span></span> <span data-ttu-id="bdb5b-104"><xref:System.String.Split%2A> 메서드를 사용하여 필드를 구분하면 LINQ를 사용하여 쉽게 CSV 파일을 쿼리하고 조작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdb5b-104">By using the <xref:System.String.Split%2A> method to separate the fields, it is very easy to query and manipulate CSV files by using LINQ.</span></span> <span data-ttu-id="bdb5b-105">실제로 동일한 방법을 사용하여 모든 구조적 텍스트 줄의 일부를 다시 정렬할 수 있습니다. CSV 파일로 제한되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bdb5b-105">In fact, the same technique can be used to reorder the parts of any structured line of text; it is not limited to CSV files.</span></span>  
  
 <span data-ttu-id="bdb5b-106">다음 예제에서는 세 개의 열이 학생의 "last name", "first name" 및 "ID"를 나타낸다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="bdb5b-106">In the following example, assume that the three columns represent students' "last name," "first name", and "ID."</span></span> <span data-ttu-id="bdb5b-107">필드는 학생의 성을 기준으로 알파벳 순서로 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdb5b-107">The fields are in alphabetical order based on the students' last names.</span></span> <span data-ttu-id="bdb5b-108">쿼리는 ID 열이 첫 번째로 표시되고, 학생의 이름과 성을 결합하는 두 번째 열이 뒤에 오는 새 시퀀스를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="bdb5b-108">The query produces a new sequence in which the ID column appears first, followed by a second column that combines the student's first name and last name.</span></span> <span data-ttu-id="bdb5b-109">ID 필드에 따라 줄이 다시 정렬됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdb5b-109">The lines are reordered according to the ID field.</span></span> <span data-ttu-id="bdb5b-110">결과는 새 파일에 저장되고 원래 데이터가 수정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bdb5b-110">The results are saved into a new file and the original data is not modified.</span></span>  
  
### <a name="to-create-the-data-file"></a><span data-ttu-id="bdb5b-111">데이터 파일을 만들려면</span><span class="sxs-lookup"><span data-stu-id="bdb5b-111">To create the data file</span></span>  
  
1.  <span data-ttu-id="bdb5b-112">spreadsheet1.csv라는 일반 텍스트 파일에 다음 줄을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="bdb5b-112">Copy the following lines into a plain text file that is named spreadsheet1.csv.</span></span> <span data-ttu-id="bdb5b-113">프로젝트 폴더에 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="bdb5b-113">Save the file in your project folder.</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="bdb5b-114">예제</span><span class="sxs-lookup"><span data-stu-id="bdb5b-114">Example</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="bdb5b-115">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="bdb5b-115">Compiling the Code</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdb5b-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bdb5b-116">See Also</span></span>  
 [<span data-ttu-id="bdb5b-117">LINQ 및 문자열 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bdb5b-117">LINQ and Strings (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)  
 [<span data-ttu-id="bdb5b-118">LINQ 및 파일 디렉터리(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bdb5b-118">LINQ and File Directories (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)  
 [<span data-ttu-id="bdb5b-119">방법: CSV 파일에서 XML 생성</span><span class="sxs-lookup"><span data-stu-id="bdb5b-119">How to: Generate XML from CSV Files</span></span>](http://msdn.microsoft.com/library/dd7bab8c-96fa-4343-94d0-9739dd6a74fd)
