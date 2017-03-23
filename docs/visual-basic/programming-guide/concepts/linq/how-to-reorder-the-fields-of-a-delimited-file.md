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
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 9abb0510ed3944cd80d6658238ef79d64dc0ca27
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-reorder-the-fields-of-a-delimited-file-linq-visual-basic"></a>방법: 구분된 된 파일 (Visual Basic) (LINQ)의 필드 다시 정렬
쉼표로 구분 된 값 (CSV) 파일은은 행과 열으로 표현 되는 다른 테이블 형식 데이터 나 스프레드시트 데이터를 저장 하는 데 자주 사용 하는 텍스트 파일입니다. 사용 하 여는 <xref:System.String.Split%2A>필드를 구분 하는 메서드를 쿼리하고 LINQ를 사용 하 여 CSV 파일 조작 매우 쉽습니다.</xref:System.String.Split%2A> 실제로 동일한 기법 데 사용할 수는 텍스트의 구조화 된 줄의 일부를 다시 정렬 CSV 파일에 제한 되지 않습니다.  
  
 다음 예제에서는 세 열에서는 학생의 "last name," 나타낸다고 가정해 봅시다 "first name" 및 "id"입니다. 필드는 학생의 성을 기준으로 알파벳 순서에 있습니다. 쿼리 표시 되는 ID 열, 첫 번째 학생의 첫 번째 이름과 마지막 이름을 결합 하는 두 번째 열 뒤에 새 시퀀스를 생성 합니다. 줄 ID 필드에 따라 다시 정렬 됩니다. 결과 새 파일에 저장 되며 및 원래 데이터가 수정 되지 않습니다.  
  
### <a name="to-create-the-data-file"></a>데이터 파일을 만들려면  
  
1.  Spreadsheet1.csv 라는 일반 텍스트 파일에 다음 줄을 복사 합니다. 프로젝트 폴더에 파일을 저장 합니다.  
  
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
  
## <a name="example"></a>예제  
  
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
  
## <a name="compiling-the-code"></a>코드 컴파일  
  
## <a name="see-also"></a>참고 항목  
 [LINQ 및 문자열 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)   
 [LINQ 및 파일 디렉터리 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)   
 [방법: CSV 파일에서 XML 생성](http://msdn.microsoft.com/library/dd7bab8c-96fa-4343-94d0-9739dd6a74fd)
