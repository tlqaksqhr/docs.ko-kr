---
title: "방법: 파일 또는 디렉터리 트리 (LINQ) (Visual Basic)에서 파일에 대 한 가장 큰 쿼리 | Microsoft 문서"
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
ms.assetid: 8c1c9f0c-95dd-4222-9be2-9ec026a13e81
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 055cbdd5a5903417ab382d390e1215f0319c0b5a
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-query-for-the-largest-file-or-files-in-a-directory-tree-linq-visual-basic"></a>방법: 디렉터리 트리에서 가장 큰 파일을 하나 이상 쿼리(LINQ)(Visual Basic)
이 예제에서는 파일 크기 (바이트) 관련 된 다섯 개의 쿼리를 보여 줍니다.  
  
-   가장 큰 파일의 바이트 크기를 검색 하는 방법입니다.  
  
-   가장 작은 파일의 바이트 크기를 검색 하는 방법입니다.  
  
-   검색 하는 방법의 <xref:System.IO.FileInfo>개체 가장 높거나 파일에서 지정한 루트 폴더 아래에 있는 하나 이상의 폴더.</xref:System.IO.FileInfo>  
  
-   예: 10 개의 가장 큰 파일 시퀀스를 검색 하는 방법.  
  
-   지정된 된 크기 보다 작은 파일을 무시 하 고 해당 파일 크기 (바이트)에서에 따라 그룹으로 파일을 요청 하는 방법.  
  
## <a name="example"></a>예제  
 다음 예제에서는 파일 크기 (바이트)에서에 따라 그룹 파일을 쿼리 하는 방법을 보여 주는 별도&5; 개 쿼리에 포함 되어 있습니다. 다른 속성에는 쿼리를 기반으로 이러한 예제를 쉽게 수정할 수는 <xref:System.IO.FileInfo>개체.</xref:System.IO.FileInfo>  
  
```vb  
Module QueryBySize  
    Sub Main()  
  
        ' Change the drive\path if necessary  
        Dim root As String = "C:\Program Files\Microsoft Visual Studio 9.0"  
  
        'Take a snapshot of the folder contents  
        Dim dir As New System.IO.DirectoryInfo(root)  
        Dim fileList = dir.GetFiles("*.*", System.IO.SearchOption.AllDirectories)  
  
        ' Return the size of the largest file  
        Dim maxSize = Aggregate aFile In fileList Into Max(GetFileLength(aFile))  
  
        'Dim maxSize = fileLengths.Max  
        Console.WriteLine("The length of the largest file under {0} is {1}", _  
                          root, maxSize)  
  
        ' Return the FileInfo object of the largest file  
        ' by sorting and selecting from the beginning of the list  
        Dim filesByLengDesc = From file In fileList _  
                              Let filelength = GetFileLength(file) _  
                              Where filelength > 0 _  
                              Order By filelength Descending _  
                              Select file  
  
        Dim longestFile = filesByLengDesc.First  
  
        Console.WriteLine("The largest file under {0} is {1} with a length of {2} bytes", _  
                          root, longestFile.FullName, longestFile.Length)  
  
        Dim smallestFile = filesByLengDesc.Last  
  
        Console.WriteLine("The smallest file under {0} is {1} with a length of {2} bytes", _  
                                root, smallestFile.FullName, smallestFile.Length)  
  
        ' Return the FileInfos for the 10 largest files  
        ' Based on a previous query, but nothing is executed  
        ' until the For Each statement below.  
        Dim tenLargest = From file In filesByLengDesc Take 10  
  
        Console.WriteLine("The 10 largest files under {0} are:", root)  
  
        For Each fi As System.IO.FileInfo In tenLargest  
            Console.WriteLine("{0}: {1} bytes", fi.FullName, fi.Length)  
        Next  
  
        ' Group files according to their size,  
        ' leaving out the ones under 200K  
        Dim sizeGroups = From file As System.IO.FileInfo In fileList _  
                         Where file.Length > 0 _  
                         Let groupLength = file.Length / 100000 _  
                         Group file By groupLength Into fileGroup = Group _  
                         Where groupLength >= 2 _  
                         Order By groupLength Descending  
  
        For Each group In sizeGroups  
            Console.WriteLine(group.groupLength + "00000")  
  
            For Each item As System.IO.FileInfo In group.fileGroup  
                Console.WriteLine("   {0}: {1}", item.Name, item.Length)  
            Next  
        Next  
  
        ' Keep the console window open in debug mode  
        Console.WriteLine("Press any key to exit.")  
        Console.ReadKey()  
  
    End Sub  
  
    ' This method is used to catch the possible exception  
    ' that can be raised when accessing the FileInfo.Length property.  
    ' In this particular case, it is safe to ignore the exception.  
    Function GetFileLength(ByVal fi As System.IO.FileInfo) As Long  
        Dim retval As Long  
        Try  
            retval = fi.Length  
        Catch ex As FileNotFoundException  
            ' If a file is no longer present,  
            ' just return zero bytes.   
            retval = 0  
        End Try  
  
        Return retval  
    End Function  
End Module  
```  
  
 하나 이상의 전체 반환할 <xref:System.IO.FileInfo>개체, 쿼리 먼저 조사 해야 데이터에서 각각, 원본 및 해당 Length 속성의 값으로 정렬 합니다.</xref:System.IO.FileInfo> 그런 다음 단일 그래픽 인터페이스 또는 시퀀스의 최대 길이를 반환할 수 있습니다. 사용 하 여 <xref:System.Linq.Enumerable.First%2A>를 목록에서 첫 번째 요소를 반환 합니다.</xref:System.Linq.Enumerable.First%2A> 사용 하 여 <xref:System.Linq.Enumerable.Take%2A>요소의 첫 번째 n 개의 수를 반환 합니다.</xref:System.Linq.Enumerable.Take%2A> 목록의 시작 부분에 가장 작은 요소를 내림차순 정렬 순서를 지정 합니다.  
  
 쿼리를 파일 이후 기간 내에 다른 스레드에서 삭제 된 경우에 발생할 수 있는 예외를 처리 하기 위해 파일 크기 (바이트) 가져오는 별도 메서드 호출의 <xref:System.IO.FileInfo>개체에 대 한 호출에서 만든 `GetFiles`.</xref:System.IO.FileInfo> 었 더라도 <xref:System.IO.FileInfo>개체에 이미 생성 되어 예외가 발생할 수 있으므로 <xref:System.IO.FileInfo>개체는 새로 고침 하려고 해당 <xref:System.IO.FileInfo.Length%2A>속성에서에서 사용 하 여 최신 크기 (바이트) 처음으로 속성에 액세스 합니다.</xref:System.IO.FileInfo.Length%2A> </xref:System.IO.FileInfo> </xref:System.IO.FileInfo> 쿼리 외부에 try catch 블록에서이 작업을 배치 하 여 의도 일으킬 수 있는 쿼리에서 연산을 회피의 규칙을 따릅니다. 일반적으로 매우 주의 해야 예외를 사용할 때 응용 프로그램 하지 알 수 없는 상태에 남아 있는 되도록 합니다.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 .NET Framework 버전 3.5 이상 System.Core.dll에 대 한 참조를 대상으로 하는 프로젝트 만들기 및 `Imports` System.Linq 네임 스페이스에 대 한 정보입니다.  
  
## <a name="see-also"></a>참고 항목  
 [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)   
 [LINQ 및 파일 디렉터리 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)
