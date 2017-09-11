---
title: "방법: 파일이 어셈블리 (Visual Basic) 인지 확인 합니다. | Microsoft 문서"
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
ms.assetid: de26f410-9bd1-4b55-a343-cc82f81684be
caps.latest.revision: 6
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 4bd3404cbdc3b79ff92290a53574080bf197fe9d
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-determine-if-a-file-is-an-assembly-visual-basic"></a><span data-ttu-id="21bb5-102">방법: 파일이 어셈블리 (Visual Basic) 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="21bb5-102">How to: Determine If a File Is an Assembly (Visual Basic)</span></span>
<span data-ttu-id="21bb5-103">파일을 어셈블리인 경우에이 관리 하 고 해당 메타 데이터에서 어셈블리 항목을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="21bb5-103">A file is an assembly if and only if it is managed, and contains an assembly entry in its metadata.</span></span> <span data-ttu-id="21bb5-104">어셈블리 및 메타 데이터에 대 한 자세한 내용은 항목을 참조 하십시오. [어셈블리 매니페스트](https://msdn.microsoft.com/library/1w45z383)합니다.</span><span class="sxs-lookup"><span data-stu-id="21bb5-104">For more information on assemblies and metadata, see the topic [Assembly Manifest](https://msdn.microsoft.com/library/1w45z383).</span></span>  
  
## <a name="how-to-manually-determine-if-a-file-is-an-assembly"></a><span data-ttu-id="21bb5-105">수동으로 파일이 어셈블리 인지를 확인 하는 방법</span><span class="sxs-lookup"><span data-stu-id="21bb5-105">How to manually determine if a file is an assembly</span></span>  
  
1.  <span data-ttu-id="21bb5-106">시작 된 [Ildasm.exe (IL 디스어셈블러)](https://msdn.microsoft.com/library/f7dy01k1)합니다.</span><span class="sxs-lookup"><span data-stu-id="21bb5-106">Start the [Ildasm.exe (IL Disassembler)](https://msdn.microsoft.com/library/f7dy01k1).</span></span>  
  
2.  <span data-ttu-id="21bb5-107">테스트 하려는 파일을 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="21bb5-107">Load the file you wish to test.</span></span>  
  
3.  <span data-ttu-id="21bb5-108">경우 **ILDASM** 보고서는 파일을 pe (이식 가능) 파일이 아닙니다. 다음은 어셈블리가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="21bb5-108">If **ILDASM** reports that the file is not a portable executable (PE) file, then it is not an assembly.</span></span> <span data-ttu-id="21bb5-109">자세한 내용은 항목을 참조 하십시오. [하는 방법: 어셈블리 내용 보기](http://msdn.microsoft.com/library/fb7baaab-4c0d-47ad-8fd3-4591cf834709)합니다.</span><span class="sxs-lookup"><span data-stu-id="21bb5-109">For more information, see the topic [How to: View Assembly Contents](http://msdn.microsoft.com/library/fb7baaab-4c0d-47ad-8fd3-4591cf834709).</span></span>  
  
## <a name="how-to-programmatically-determine-if-a-file-is-an-assembly"></a><span data-ttu-id="21bb5-110">프로그래밍 방식으로 파일이 어셈블리 인지를 확인 하는 방법</span><span class="sxs-lookup"><span data-stu-id="21bb5-110">How to programmatically determine if a file is an assembly</span></span>  
  
1.  <span data-ttu-id="21bb5-111">호출의 <xref:System.Reflection.AssemblyName.GetAssemblyName%2A>메서드를 테스트 하는 파일의 이름과 전체 파일 경로 전달 합니다.</xref:System.Reflection.AssemblyName.GetAssemblyName%2A></span><span class="sxs-lookup"><span data-stu-id="21bb5-111">Call the <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> method, passing the full file path and name of the file you are testing.</span></span>  
  
2.  <span data-ttu-id="21bb5-112">경우에 <xref:System.BadImageFormatException>예외가, 파일은 어셈블리가 아닙니다.</xref:System.BadImageFormatException></span><span class="sxs-lookup"><span data-stu-id="21bb5-112">If a <xref:System.BadImageFormatException> exception is thrown, the file is not an assembly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="21bb5-113">예제</span><span class="sxs-lookup"><span data-stu-id="21bb5-113">Example</span></span>  
 <span data-ttu-id="21bb5-114">이 예제에서는 DLL 어셈블리 인지를 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="21bb5-114">This example tests a DLL to see if it is an assembly.</span></span>  
  
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
  
 <span data-ttu-id="21bb5-115"><xref:System.Reflection.AssemblyName.GetAssemblyName%2A>메서드 테스트 파일을 로드 하 고 다음 정보는 읽기 되 면 해제.</xref:System.Reflection.AssemblyName.GetAssemblyName%2A></span><span class="sxs-lookup"><span data-stu-id="21bb5-115">The <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> method loads the test file, and then releases it once the information is read.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21bb5-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="21bb5-116">See Also</span></span>  
 <span data-ttu-id="21bb5-117"><xref:System.Reflection.AssemblyName></xref:System.Reflection.AssemblyName></span><span class="sxs-lookup"><span data-stu-id="21bb5-117"><xref:System.Reflection.AssemblyName></span></span>   
<span data-ttu-id="21bb5-118"> [프로그래밍 개념](../../../../visual-basic/programming-guide/concepts/index.md) </span><span class="sxs-lookup"><span data-stu-id="21bb5-118"> [Programming Concepts](../../../../visual-basic/programming-guide/concepts/index.md) </span></span>  
<span data-ttu-id="21bb5-119"> [어셈블리 및 전역 어셈블리 캐시 (Visual Basic)](index.md)</span><span class="sxs-lookup"><span data-stu-id="21bb5-119"> [Assemblies and the Global Assembly Cache (Visual Basic)](index.md)</span></span>
