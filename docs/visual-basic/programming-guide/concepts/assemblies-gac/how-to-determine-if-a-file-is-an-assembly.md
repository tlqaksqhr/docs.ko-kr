---
title: '방법: 파일 어셈블리 (Visual Basic) 인지 확인 합니다.'
ms.date: 07/20/2015
ms.assetid: de26f410-9bd1-4b55-a343-cc82f81684be
ms.openlocfilehash: 84d45cea4a2557350edacd5f05b12c8ffcac4df8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33643244"
---
# <a name="how-to-determine-if-a-file-is-an-assembly-visual-basic"></a><span data-ttu-id="e979d-102">방법: 파일 어셈블리 (Visual Basic) 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e979d-102">How to: Determine If a File Is an Assembly (Visual Basic)</span></span>
<span data-ttu-id="e979d-103">파일은 관리되고 해당 메타데이터에 어셈블리 항목을 포함하는 경우에만 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="e979d-103">A file is an assembly if and only if it is managed, and contains an assembly entry in its metadata.</span></span> <span data-ttu-id="e979d-104">어셈블리 및 메타데이터에 대한 자세한 내용은 [어셈블리 매니페스트](../../../../framework/app-domains/assembly-manifest.md) 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e979d-104">For more information on assemblies and metadata, see the topic [Assembly Manifest](../../../../framework/app-domains/assembly-manifest.md).</span></span>  
  
## <a name="how-to-manually-determine-if-a-file-is-an-assembly"></a><span data-ttu-id="e979d-105">파일이 어셈블리인지 수동으로 확인하는 방법</span><span class="sxs-lookup"><span data-stu-id="e979d-105">How to manually determine if a file is an assembly</span></span>  
  
1.  <span data-ttu-id="e979d-106">[Ildasm.exe(IL 디스어셈블러)](https://msdn.microsoft.com/library/f7dy01k1)를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="e979d-106">Start the [Ildasm.exe (IL Disassembler)](https://msdn.microsoft.com/library/f7dy01k1).</span></span>  
  
2.  <span data-ttu-id="e979d-107">테스트하려는 파일을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="e979d-107">Load the file you wish to test.</span></span>  
  
3.  <span data-ttu-id="e979d-108">**ILDASM**에서 파일이 PE(이식 가능) 파일이 아니라고 보고하는 경우에는 어셈블리가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="e979d-108">If **ILDASM** reports that the file is not a portable executable (PE) file, then it is not an assembly.</span></span> <span data-ttu-id="e979d-109">자세한 내용은 [방법: 어셈블리 내용 보기](../../../../framework/app-domains/how-to-view-assembly-contents.md) 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e979d-109">For more information, see the topic [How to: View Assembly Contents](../../../../framework/app-domains/how-to-view-assembly-contents.md).</span></span>  
  
## <a name="how-to-programmatically-determine-if-a-file-is-an-assembly"></a><span data-ttu-id="e979d-110">파일이 어셈블리인지 프로그래밍 방식으로 확인하는 방법</span><span class="sxs-lookup"><span data-stu-id="e979d-110">How to programmatically determine if a file is an assembly</span></span>  
  
1.  <span data-ttu-id="e979d-111">테스트하는 파일의 전체 파일 경로와 이름을 전달하여 <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="e979d-111">Call the <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> method, passing the full file path and name of the file you are testing.</span></span>  
  
2.  <span data-ttu-id="e979d-112"><xref:System.BadImageFormatException> 예외가 throw되는 경우 파일이 어셈블리가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="e979d-112">If a <xref:System.BadImageFormatException> exception is thrown, the file is not an assembly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e979d-113">예제</span><span class="sxs-lookup"><span data-stu-id="e979d-113">Example</span></span>  
 <span data-ttu-id="e979d-114">이 예제에서는 DLL을 테스트하여 어셈블리인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e979d-114">This example tests a DLL to see if it is an assembly.</span></span>  
  
```vb  
Module Module1  
    Sub Main()  
        Try  
            Dim testAssembly As Reflection.AssemblyName =  
                                Reflection.AssemblyName.GetAssemblyName("C:\Windows\Microsoft.NET\Framework\v3.5\System.Net.dll")  
            Console.WriteLine("Yes, the file is an Assembly.")  
        Catch ex As System.IO.FileNotFoundException  
            Console.WriteLine("The file cannot be found.")  
        Catch ex As System.BadImageFormatException  
            Console.WriteLine("The file is not an Assembly.")  
        Catch ex As System.IO.FileLoadException  
            Console.WriteLine("The Assembly has already been loaded.")  
        End Try  
        Console.ReadLine()  
    End Sub  
End Module  
' Output (with .NET Framework 3.5 installed):  
'        Yes, the file is an Assembly.  
```
  
 <span data-ttu-id="e979d-115"><xref:System.Reflection.AssemblyName.GetAssemblyName%2A> 메서드는 테스트 파일을 로드한 다음 정보를 읽고 나면 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="e979d-115">The <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> method loads the test file, and then releases it once the information is read.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e979d-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e979d-116">See Also</span></span>  
 <xref:System.Reflection.AssemblyName>  
 [<span data-ttu-id="e979d-117">프로그래밍 개념</span><span class="sxs-lookup"><span data-stu-id="e979d-117">Programming Concepts</span></span>](../../../../visual-basic/programming-guide/concepts/index.md)  
 [<span data-ttu-id="e979d-118">어셈블리와 전역 어셈블리 캐시(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e979d-118">Assemblies and the Global Assembly Cache (Visual Basic)</span></span>](index.md)
