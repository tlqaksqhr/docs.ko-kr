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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 2e58363369ae4420879310bf09ed89cdd4f5b5cc
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-determine-if-a-file-is-an-assembly-visual-basic"></a>방법: 파일이 어셈블리 (Visual Basic) 인지 확인 합니다.
파일을 어셈블리인 경우에이 관리 하 고 해당 메타 데이터에서 어셈블리 항목을 포함 합니다. 어셈블리 및 메타 데이터에 대 한 자세한 내용은 항목을 참조 하십시오. [어셈블리 매니페스트](https://msdn.microsoft.com/library/1w45z383)합니다.  
  
## <a name="how-to-manually-determine-if-a-file-is-an-assembly"></a>수동으로 파일이 어셈블리 인지를 확인 하는 방법  
  
1.  시작 된 [Ildasm.exe (IL 디스어셈블러)](https://msdn.microsoft.com/library/f7dy01k1)합니다.  
  
2.  테스트 하려는 파일을 로드 합니다.  
  
3.  경우 **ILDASM** 보고서는 파일을 pe (이식 가능) 파일이 아닙니다. 다음은 어셈블리가 아닙니다. 자세한 내용은 항목을 참조 하십시오. [하는 방법: 어셈블리 내용 보기](http://msdn.microsoft.com/library/fb7baaab-4c0d-47ad-8fd3-4591cf834709)합니다.  
  
## <a name="how-to-programmatically-determine-if-a-file-is-an-assembly"></a>프로그래밍 방식으로 파일이 어셈블리 인지를 확인 하는 방법  
  
1.  호출의 <xref:System.Reflection.AssemblyName.GetAssemblyName%2A>메서드를 테스트 하는 파일의 이름과 전체 파일 경로 전달 합니다.</xref:System.Reflection.AssemblyName.GetAssemblyName%2A>  
  
2.  경우에 <xref:System.BadImageFormatException>예외가, 파일은 어셈블리가 아닙니다.</xref:System.BadImageFormatException>  
  
## <a name="example"></a>예제  
 이 예제에서는 DLL 어셈블리 인지를 테스트 합니다.  
  
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
  
 <xref:System.Reflection.AssemblyName.GetAssemblyName%2A>메서드 테스트 파일을 로드 하 고 다음 정보는 읽기 되 면 해제.</xref:System.Reflection.AssemblyName.GetAssemblyName%2A>  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Reflection.AssemblyName></xref:System.Reflection.AssemblyName>   
 [프로그래밍 개념](../../../../visual-basic/programming-guide/concepts/index.md)   
 [어셈블리 및 전역 어셈블리 캐시 (Visual Basic)](index.md)
