---
title: "방법: 폴더 (Visual Basic) (LINQ) 집합을 바이트의 총 수에 대 한 쿼리 | Microsoft 문서"
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
ms.assetid: bfe85ed2-44dc-4ef1-aac7-241622b80a69
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
ms.openlocfilehash: 668a8a4d89f7b81c3aef9b4e1a46ad749c4a8341
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-query-for-the-total-number-of-bytes-in-a-set-of-folders-linq-visual-basic"></a>방법: 폴더 (Visual Basic) (LINQ) 집합을 바이트의 총 수에 대 한 쿼리
이 예제에서는 지정된 된 폴더에 있는 모든 파일 및 모든 하위 폴더에 사용 된 바이트의 총 수를 검색 하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 <xref:System.Linq.Enumerable.Sum%2A>에서 선택한 모든 항목의 값을 추가 하는 메서드는 `select` 절.</xref:System.Linq.Enumerable.Sum%2A> <xref:System.Linq.Enumerable.Min%2A>또는 <xref:System.Linq.Enumerable.Max%2A> <xref:System.Linq.Enumerable.Sum%2A>.</xref:System.Linq.Enumerable.Sum%2A> 대신 메서드</xref:System.Linq.Enumerable.Max%2A> </xref:System.Linq.Enumerable.Min%2A> 를 호출 하 여 지정 된 디렉터리 트리에서 가장 큰 크거나 작은 파일을 검색 하려면 다음이 쿼리를 쉽게 수정할 수 있습니다.  
  
```vb  
Module QueryTotalBytes  
    Sub Main()  
  
        ' Change the drive\path if necessary.  
        Dim root As String = "C:\Program Files\Microsoft Visual Studio 9.0\VB"  
  
        'Take a snapshot of the folder contents.  
        ' This method assumes that the application has discovery permissions  
        ' for all folders under the specified path.  
        Dim fileList = My.Computer.FileSystem.GetFiles _  
                  (root, FileIO.SearchOption.SearchAllSubDirectories, "*.*")  
  
        Dim fileQuery = From file In fileList _  
                        Select GetFileLength(file)  
  
        ' Force execution and cache the results to avoid multiple trips to the file system.  
        Dim fileLengths = fileQuery.ToArray()  
  
        ' Find the largest file  
        Dim maxSize = Aggregate aFile In fileLengths Into Max()  
  
        ' Find the total number of bytes  
        Dim totalBytes = Aggregate aFile In fileLengths Into Sum()  
  
        Console.WriteLine("The largest file is " & maxSize & " bytes")  
        Console.WriteLine("There are " & totalBytes & " total bytes in " & _  
                          fileList.Count & " files under " & root)  
  
        ' Keep the console window open in debug mode  
        Console.WriteLine("Press any key to exit.")  
        Console.ReadKey()  
    End Sub  
  
    ' This method is used to catch the possible exception  
    ' that can be raised when accessing the FileInfo.Length property.  
    Function GetFileLength(ByVal filename As String) As Long  
        Dim retval As Long  
        Try  
            Dim fi As New System.IO.FileInfo(filename)  
            retval = fi.Length  
        Catch ex As System.IO.FileNotFoundException  
            ' If a file is no longer present,  
            ' just return zero bytes.   
            retval = 0  
        End Try  
  
        Return retval  
    End Function  
End Module  
```  
  
 지정된 된 디렉터리 트리에서의 바이트 수를 계산 해야 하는 경우 이렇게 하려면 보다 효율적으로 데이터 원본으로 목록 컬렉션을 만드는 오버 헤드를 유발 하는 LINQ 쿼리를 만들지 않고 있습니다. LINQ 사용 하는 조건의 유용성에는 쿼리가 더 복잡 하거나 동일한 데이터 원본에 대해 여러 쿼리를 실행 해야 할 때 증가 합니다.  
  
 쿼리 파일 길이를 가져오는 별도 메서드를 호출 합니다. 이후 다른 스레드에서 파일이 삭제 된 경우 발생할 수 있는 예외를 처리 하기 위해이 위해는 <xref:System.IO.FileInfo>개체에 대 한 호출에서 만든 `GetFiles`.</xref:System.IO.FileInfo> 경우에는 <xref:System.IO.FileInfo>개체에 이미 생성 되어 예외가 발생할 수 있으므로 한 <xref:System.IO.FileInfo>개체는 새로 고침 하려고 해당 <xref:System.IO.FileInfo.Length%2A>최신 길이 처음으로 속성에 액세스를 사용 하 여 속성.</xref:System.IO.FileInfo.Length%2A> </xref:System.IO.FileInfo> </xref:System.IO.FileInfo> 쿼리 외부에 try catch 블록에서이 작업을 배치 하 여 코드의 의도 일으킬 수 있는 쿼리에서 연산을 회피 규칙을 따릅니다. 일반적으로 매우 주의 해야 응용 프로그램 하지 알 수 없는 상태에 남아 있는 있는지 확인 하는 예외를 사용 하는 경우.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 .NET Framework 버전 3.5 이상 System.Core.dll에 대 한 참조를 대상으로 하는 프로젝트 만들기 및 `Imports` System.Linq 네임 스페이스에 대 한 정보입니다.  
  
## <a name="see-also"></a>참고 항목  
 [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)   
 [LINQ 및 파일 디렉터리 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)
