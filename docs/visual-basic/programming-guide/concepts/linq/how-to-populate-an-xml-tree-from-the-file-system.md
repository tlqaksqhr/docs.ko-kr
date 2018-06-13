---
title: '방법: 파일 시스템 (Visual Basic)에서 XML 트리 채우기'
ms.date: 07/20/2015
ms.assetid: 34eec79e-7945-4ba8-9f74-d05bb8ec67f6
ms.openlocfilehash: 158a6c5c6734f0aa11e22b5cbea35c960c7a1c40
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33642562"
---
# <a name="how-to-populate-an-xml-tree-from-the-file-system-visual-basic"></a><span data-ttu-id="0b32e-102">방법: 파일 시스템 (Visual Basic)에서 XML 트리 채우기</span><span class="sxs-lookup"><span data-stu-id="0b32e-102">How to: Populate an XML Tree from the File System (Visual Basic)</span></span>
<span data-ttu-id="0b32e-103">일반적으로 XML 트리는 계층적인 이름/값 데이터 저장소로 유용하게 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b32e-103">A common and useful application of XML trees is as a hierarchical name/value data store.</span></span> <span data-ttu-id="0b32e-104">계층적 데이터로 XML 트리를 채운 다음 쿼리 및 변환하고 필요한 경우 serialize할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b32e-104">You can populate an XML tree with hierarchical data, and then query it, transform it, and if necessary, serialize it.</span></span> <span data-ttu-id="0b32e-105">이 사용 시나리오에서 네임스페이스 및 공백 동작과 같은 많은 XML 관련 의미는 중요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0b32e-105">In this usage scenario, many of the XML specific semantics, such as namespaces and white space behavior, are not important.</span></span> <span data-ttu-id="0b32e-106">대신 XML 트리를 한 사용자가 사용하는 작고 계층적인 메모리 내 데이터베이스로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0b32e-106">Instead, you are using the XML tree as a small, in memory, single user hierarchical database.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b32e-107">예제</span><span class="sxs-lookup"><span data-stu-id="0b32e-107">Example</span></span>  
 <span data-ttu-id="0b32e-108">다음 예제에서는 재귀를 사용하여 로컬 파일 시스템에서 XML 트리를 채운 다음</span><span class="sxs-lookup"><span data-stu-id="0b32e-108">The following example populates an XML tree from the local file system using recursion.</span></span> <span data-ttu-id="0b32e-109">트리를 쿼리하고 트리에 있는 모든 파일의 총 크기를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="0b32e-109">It then queries the tree, calculating the total of the sizes of all files in the tree.</span></span>  
  
```vb  
Module Module1  
    Function CreateFileSystemXmlTree(ByVal source As String) As XElement  
        Dim di As DirectoryInfo = New DirectoryInfo(source)  
        Return <Dir Name=<%= di.Name %>>  
                   <%= From d In Directory.GetDirectories(source) _  
                       Select CreateFileSystemXmlTree(d) %>  
                   <%= From fi In di.GetFiles() _  
                       Select <File>  
                                  <Name><%= fi.Name %></Name>  
                                  <Length><%= fi.Length %></Length>  
                              </File> %>  
               </Dir>  
    End Function  
  
    Sub Main()  
        Dim fileSystemTree As XElement = CreateFileSystemXmlTree("C:/Tmp")  
        Console.WriteLine(fileSystemTree)  
        Console.WriteLine("------")  
        Dim totalFileSize As Long = _  
            ( _  
                From f In fileSystemTree...<File> _  
                Select CLng(f.<Length>(0)) _  
            ).Sum()  
        Console.WriteLine("Total File Size:{0}", totalFileSize)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="0b32e-110">이 예제의 결과는 다음과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="0b32e-110">This example produces output similar to the following:</span></span>  
  
```xml  
<Dir Name="Tmp">  
  <Dir Name="ConsoleApplication1">  
    <Dir Name="bin">  
      <Dir Name="Debug">  
        <File>  
          <Name>ConsoleApplication1.exe</Name>  
          <Length>4608</Length>  
        </File>  
        <File>  
          <Name>ConsoleApplication1.pdb</Name>  
          <Length>11776</Length>  
        </File>  
        <File>  
          <Name>ConsoleApplication1.vshost.exe</Name>  
          <Length>9568</Length>  
        </File>  
        <File>  
          <Name>ConsoleApplication1.vshost.exe.manifest</Name>  
          <Length>473</Length>  
        </File>  
      </Dir>  
    </Dir>  
    <Dir Name="obj">  
      <Dir Name="Debug">  
        <Dir Name="TempPE" />  
        <File>  
          <Name>ConsoleApplication1.csproj.FileListAbsolute.txt</Name>  
          <Length>322</Length>  
        </File>  
        <File>  
          <Name>ConsoleApplication1.exe</Name>  
          <Length>4608</Length>  
        </File>  
        <File>  
          <Name>ConsoleApplication1.pdb</Name>  
          <Length>11776</Length>  
        </File>  
      </Dir>  
    </Dir>  
    <Dir Name="Properties">  
      <File>  
        <Name>AssemblyInfo.cs</Name>  
        <Length>1454</Length>  
      </File>  
    </Dir>  
    <File>  
      <Name>ConsoleApplication1.csproj</Name>  
      <Length>2546</Length>  
    </File>  
    <File>  
      <Name>ConsoleApplication1.sln</Name>  
      <Length>937</Length>  
    </File>  
    <File>  
      <Name>ConsoleApplication1.suo</Name>  
      <Length>10752</Length>  
    </File>  
    <File>  
      <Name>Program.cs</Name>  
      <Length>269</Length>  
    </File>  
  </Dir>  
</Dir>  
------  
Total File Size:59089  
```  
  
## <a name="see-also"></a><span data-ttu-id="0b32e-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0b32e-111">See Also</span></span>  
 [<span data-ttu-id="0b32e-112">고급 쿼리 기술 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0b32e-112">Advanced Query Techniques (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/advanced-query-techniques-linq-to-xml.md)
