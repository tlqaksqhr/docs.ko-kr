---
title: "방법: 서명 되지 않은 Friend 어셈블리 (Visual Basic) 만들기 | Microsoft 문서"
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
ms.assetid: 5735eb79-9729-4c46-ac1f-537ada3acaa7
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: ceddb35c306f72c8927deda326d9fcca6c75d786
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-create-unsigned-friend-assemblies-visual-basic"></a>방법: 서명 되지 않은 Friend 어셈블리 (Visual Basic) 만들기
이 예제에는 어셈블리에 서명 되지 않은 friend 어셈블리를 사용 하는 방법을 보여 줍니다.  
  
### <a name="to-create-an-assembly-and-a-friend-assembly"></a>어셈블리 및 friend 어셈블리를 만들려면  
  
1.  명령 프롬프트를 엽니다.  
  
2.  라는 Visual Basic 파일을 만듭니다 `friend_signed_A.` 하는 다음 코드를 포함 합니다. 코드를 사용 하는 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>friend_signed_B friend 어셈블리 선언 하는 특성입니다.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>  
  
    ```vb  
    ' friend_unsigned_A.vb  
    ' Compile with:   
    ' Vbc /target:library friend_unsigned_A.vb  
    Imports System.Runtime.CompilerServices  
    Imports System  
  
    <Assembly: InternalsVisibleTo("friend_unsigned_B")>   
  
    ' Friend type.  
    Friend Class Class1  
        Public Sub Test()  
            Console.WriteLine("Class1.Test")  
        End Sub  
    End Class  
  
    ' Public type with Friend member.  
    Public Class Class2  
        Friend Sub Test()  
            Console.WriteLine("Class2.Test")  
        End Sub  
    End Class  
    ```  
  
3.  컴파일 및 friend_signed_A 다음 명령을 사용 하 여 로그인 합니다.  
  
    ```vb  
    Vbc /target:library friend_unsigned_A.vb  
    ```  
  
4.  라는 Visual Basic 파일을 만듭니다 `friend_unsigned_B` 하는 다음 코드를 포함 합니다. Friend_unsigned_B의 코드에 액세스할 수 friend_unsigned_A friend_unsigned_B friend 어셈블리를 지정 하므로 `Friend` 형식과 friend_unsigned_A에서 멤버입니다.  
  
    ```vb  
    ' friend_unsigned_B.vb  
    ' Compile with:   
    ' Vbc /r:friend_unsigned_A.dll friend_unsigned_B.vb  
    Module Module1  
        Sub Main()  
            ' Access a Friend type.  
            Dim inst1 As New Class1()  
            inst1.Test()  
  
            Dim inst2 As New Class2()  
            ' Access a Friend member of a public type.  
            inst2.Test()  
  
            System.Console.ReadLine()  
        End Sub  
    End Module  
    ```  
  
5.  다음 명령을 사용 하 여 friend_signed_B를 컴파일하십시오.  
  
    ```vb  
    Vbc /r:friend_unsigned_A.dll friend_unsigned_B.vb  
    ```  
  
     컴파일러에서 생성 되는 어셈블리의 이름에 전달 되는 friend 어셈블리 이름과 같아야 합니다.는 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>특성.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 사용 하 여 어셈블리를 명시적으로 설정할 수는 `/out` 컴파일러 옵션입니다.  
  
6.  Friend_signed_B.exe 파일을 실행 합니다.  
  
     두 문자열을 인쇄 하는 프로그램: "Class1.Test" 및 "Class2.Test"입니다.  
  
## <a name="net-framework-security"></a>.NET Framework 보안  
 가 유사성 사이는 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>특성 및 <xref:System.Security.Permissions.StrongNameIdentityPermission>클래스가 있습니다.</xref:System.Security.Permissions.StrongNameIdentityPermission> </xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 주요 차이점은 <xref:System.Security.Permissions.StrongNameIdentityPermission>반면 코드의 특정 섹션을 실행 하는 보안 권한을 요구할 수 있습니다는 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>특성의 표시 유형을 제어 `Friend` 형식 및 멤버.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> </xref:System.Security.Permissions.StrongNameIdentityPermission>  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>   
 [어셈블리 및 전역 어셈블리 캐시 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)   
 [Friend 어셈블리 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/friend-assemblies.md)   
 [방법: 서명 된 Friend 어셈블리 (Visual Basic) 만들기](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md)   
 [프로그래밍 가이드 개념](../../../../visual-basic/programming-guide/concepts/index.md)
