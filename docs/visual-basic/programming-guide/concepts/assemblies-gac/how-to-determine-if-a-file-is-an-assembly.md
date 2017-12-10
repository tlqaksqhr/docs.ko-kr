---
title: "방법: 파일 어셈블리 (Visual Basic) 인지 확인 합니다."
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: de26f410-9bd1-4b55-a343-cc82f81684be
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 314c65ebfbb2aaf1acc9fad4cefa13c5f4f17cec
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/09/2017
---
# <a name="how-to-determine-if-a-file-is-an-assembly-visual-basic"></a>방법: 파일 어셈블리 (Visual Basic) 인지 확인 합니다.
파일은 관리되고 해당 메타데이터에 어셈블리 항목을 포함하는 경우에만 어셈블리입니다. 어셈블리 및 메타데이터에 대한 자세한 내용은 [어셈블리 매니페스트](../../../../../docs/framework/app-domains/assembly-manifest.md) 항목을 참조하세요.  
  
## <a name="how-to-manually-determine-if-a-file-is-an-assembly"></a>파일이 어셈블리인지 수동으로 확인하는 방법  
  
1.  [Ildasm.exe(IL 디스어셈블러)](https://msdn.microsoft.com/library/f7dy01k1)를 시작합니다.  
  
2.  테스트하려는 파일을 로드합니다.  
  
3.  **ILDASM**에서 파일이 PE(이식 가능) 파일이 아니라고 보고하는 경우에는 어셈블리가 아닙니다. 자세한 내용은 [방법: 어셈블리 내용 보기](../../../../framework/app-domains/how-to-view-assembly-contents.md) 항목을 참조하세요.  
  
## <a name="how-to-programmatically-determine-if-a-file-is-an-assembly"></a>파일이 어셈블리인지 프로그래밍 방식으로 확인하는 방법  
  
1.  테스트하는 파일의 전체 파일 경로와 이름을 전달하여 <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> 메서드를 호출합니다.  
  
2.  <xref:System.BadImageFormatException> 예외가 throw되는 경우 파일이 어셈블리가 아닙니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 DLL을 테스트하여 어셈블리인지 확인합니다.  
  
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
  
 <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> 메서드는 테스트 파일을 로드한 다음 정보를 읽고 나면 해제합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Reflection.AssemblyName>  
 [프로그래밍 개념](../../../../visual-basic/programming-guide/concepts/index.md)  
 [어셈블리와 전역 어셈블리 캐시(Visual Basic)](index.md)
