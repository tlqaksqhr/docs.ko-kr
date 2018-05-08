---
title: '방법: 두 개의 폴더 (Visual Basic) (LINQ)의 내용 비교'
ms.date: 07/20/2015
ms.assetid: 903c7e9a-f48d-4a07-a8a8-5450d2646efa
ms.openlocfilehash: 02f05f540afb9dcb398cc63a16f0fbbb80a7f4cf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-compare-the-contents-of-two-folders-linq-visual-basic"></a>방법: 두 개의 폴더 (Visual Basic) (LINQ)의 내용 비교
이 예제에서는 두 파일 목록을 비교하는 세 가지 방법을 보여 줍니다.  
  
-   두 파일 목록이 똑같은지 여부를 지정하는 부울 값 쿼리.  
  
-   양쪽 폴더에 있는 파일을 검색하기 위해 교집합 쿼리.  
  
-   두 개 중 한 폴더에만 있는 파일을 검색하기 위해 차집합 쿼리.  
  
    > [!NOTE]
    >  여기 표시된 방법은 형식에 관계없이 개체의 시퀀스를 비교하도록 조정될 수 있습니다.  
  
 여기 표시된 `FileComparer` 클래스는 표준 쿼리 연산자와 함께 사용자 지정 비교자 클래스를 사용하는 방법을 보여 줍니다. 이 클래스는 실제 시나리오에서 사용되지 않습니다. 단지 각 파일의 이름 및 길이(바이트)를 사용하여 각 폴더의 내용이 똑같은지 여부를 확인합니다. 실제 시나리오에서는 더 엄격한 일치 검사를 수행하도록 이 비교자를 수정해야 합니다.  
  
## <a name="example"></a>예제  
  
```vb  
Module CompareDirs  
    Public Sub Main()  
  
        ' Create two identical or different temporary folders   
        ' on a local drive and add files to them.  
        ' Then set these file paths accordingly.  
        Dim pathA As String = "C:\TestDir"  
        Dim pathB As String = "C:\TestDir2"  
  
        ' Take a snapshot of the file system.   
        Dim dir1 As New System.IO.DirectoryInfo(pathA)  
        Dim dir2 As New System.IO.DirectoryInfo(pathB)  
  
        Dim list1 = dir1.GetFiles("*.*", System.IO.SearchOption.AllDirectories)  
        Dim list2 = dir2.GetFiles("*.*", System.IO.SearchOption.AllDirectories)  
  
        ' Create the FileCompare object we'll use in each query  
        Dim myFileCompare As New FileCompare  
  
        ' This query determines whether the two folders contain  
        ' identical file lists, based on the custom file comparer  
        ' that is defined in the FileCompare class.  
        ' The query executes immediately because it returns a bool.  
        Dim areIdentical As Boolean = list1.SequenceEqual(list2, myFileCompare)  
        If areIdentical = True Then  
            Console.WriteLine("The two folders are the same.")  
        Else  
            Console.WriteLine("The two folders are not the same.")  
        End If  
  
        ' Find common files in both folders. It produces a sequence and doesn't execute  
        ' until the foreach statement.  
        Dim queryCommonFiles = list1.Intersect(list2, myFileCompare)  
  
        If queryCommonFiles.Count() > 0 Then  
  
            Console.WriteLine("The following files are in both folders:")  
            For Each fi As System.IO.FileInfo In queryCommonFiles  
                Console.WriteLine(fi.FullName)  
            Next  
        Else  
            Console.WriteLine("There are no common files in the two folders.")  
        End If  
  
        ' Find the set difference between the two folders.  
        ' For this example we only check one way.  
        Dim queryDirAOnly = list1.Except(list2, myFileCompare)  
        Console.WriteLine("The following files are in dirA but not dirB:")  
        For Each fi As System.IO.FileInfo In queryDirAOnly  
            Console.WriteLine(fi.FullName)  
        Next  
  
        ' Keep the console window open in debug mode  
        Console.WriteLine("Press any key to exit.")  
        Console.ReadKey()  
    End Sub  
  
    ' This implementation defines a very simple comparison  
    ' between two FileInfo objects. It only compares the name  
    ' of the files being compared and their length in bytes.  
    Public Class FileCompare  
        Implements System.Collections.Generic.IEqualityComparer(Of System.IO.FileInfo)  
  
        Public Function Equals1(ByVal x As System.IO.FileInfo, ByVal y As System.IO.FileInfo) _  
            As Boolean Implements System.Collections.Generic.IEqualityComparer(Of System.IO.FileInfo).Equals  
  
            If (x.Name = y.Name) And (x.Length = y.Length) Then  
                Return True  
            Else  
                Return False  
            End If  
        End Function  
  
        ' Return a hash that reflects the comparison criteria. According to the   
        ' rules for IEqualityComparer(Of T), if Equals is true, then the hash codes must  
        ' also be equal. Because equality as defined here is a simple value equality, not  
        ' reference identity, it is possible that two or more objects will produce the same  
        ' hash code.  
        Public Function GetHashCode1(ByVal fi As System.IO.FileInfo) _  
            As Integer Implements System.Collections.Generic.IEqualityComparer(Of System.IO.FileInfo).GetHashCode  
            Dim s As String = fi.Name & fi.Length  
            Return s.GetHashCode()  
        End Function  
    End Class  
End Module  
```  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 System.Core.dll에 대한 참조와 System.Linq 네임스페이스에 대한 `Imports` 문을 사용하여 .NET Framework 버전 3.5 이상을 대상으로 하는 프로젝트를 만듭니다.  
  
## <a name="see-also"></a>참고 항목  
 [LINQ to Objects(Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)  
 [LINQ 및 파일 디렉터리(Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)
