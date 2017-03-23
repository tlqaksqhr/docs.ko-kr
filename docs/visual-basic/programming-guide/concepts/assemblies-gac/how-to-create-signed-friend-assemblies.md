---
title: "방법: 서명 된 Friend 어셈블리 (Visual Basic) 만들기 | Microsoft 문서"
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
ms.assetid: f2afd83d-b044-484b-a56d-56d0a8a40647
caps.latest.revision: 4
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 1a69f7e833800ec7417bc35fad763f1001b3e7f9
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-create-signed-friend-assemblies-visual-basic"></a>방법: 서명 된 Friend 어셈블리 (Visual Basic) 만들기
이 예제에는 어셈블리에 강력한 이름을 갖고 friend 어셈블리를 사용 하는 방법을 보여 줍니다. 두 어셈블리는 강력한 이름을 지정 해야 합니다. 이 예에서 두 어셈블리가 모두 동일한 키를 사용 하지만 두 어셈블리에 대 한 서로 다른 키를 사용할 수 있습니다.  
  
### <a name="to-create-a-signed-assembly-and-a-friend-assembly"></a>서명된 된 어셈블리 및 friend 어셈블리를 만들려면  
  
1.  명령 프롬프트를 엽니다.  
  
2.  키 파일을 생성 하 고 해당 공개 키를 표시 하려면 다음 명령 시퀀스를 사용 하 여 강력한 이름 도구. 자세한 내용은 [Sn.exe(강력한 이름 도구)](https://msdn.microsoft.com/library/k5b5tt23)를 참조하세요.  
  
    1.  이 예제에 대 한 강력한 이름 키를 생성 하 고 FriendAssemblies.snk 파일에 저장 합니다.  
  
         `sn -k FriendAssemblies.snk`  
  
    2.  FriendAssemblies.snk에서 공개 키를 추출 하 고 FriendAssemblies.publickey에 넣습니다.  
  
         `sn -p FriendAssemblies.snk FriendAssemblies.publickey`  
  
    3.  FriendAssemblies.publickey 파일에 저장 된 공개 키를 표시 합니다.  
  
         `sn -tp FriendAssemblies.publickey`  
  
3.  라는 Visual Basic 파일을 만듭니다 `friend_signed_A` 하는 다음 코드를 포함 합니다. 코드를 사용 하는 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>friend_signed_B friend 어셈블리 선언 하는 특성입니다.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>  
  
     강력한 이름 도구를 실행할 때마다 새 공개 키를 생성 합니다. 따라서 다음 예제와 같이 방금 생성 한 공개 키도 다음 코드에 공개 키를 대체 해야 있습니다.  
  
    ```vb  
    ' friend_signed_A.vb  
    ' Compile with:   
    ' Vbc /target:library /keyfile:FriendAssemblies.snk friend_signed_A.vb  
    Imports System.Runtime.CompilerServices  
  
    <Assembly: InternalsVisibleTo("friend_signed_B, PublicKey=0024000004800000940000000602000000240000525341310004000001000100e3aedce99b7e10823920206f8e46cd5558b4ec7345bd1a5b201ffe71660625dcb8f9a08687d881c8f65a0dcf042f81475d2e88f3e3e273c8311ee40f952db306c02fbfc5d8bc6ee1e924e6ec8fe8c01932e0648a0d3e5695134af3bb7fab370d3012d083fa6b83179dd3d031053f72fc1f7da8459140b0af5afc4d2804deccb6")>   
    Public Class Class1  
        Public Sub Test()  
            System.Console.WriteLine("Class1.Test")  
            System.Console.ReadLine()  
        End Sub  
    End Class  
    ```  
  
4.  컴파일 및 friend_signed_A 다음 명령을 사용 하 여 로그인 합니다.  
  
    ```vb  
    Vbc /target:library /keyfile:FriendAssemblies.snk friend_signed_A.vb  
    ```  
  
5.  라는 Visual Basic 파일 만들기 `friend_signed_B` 다음 코드를 포함 합니다. Friend_signed_B의 코드에 액세스할 수 friend_signed_A friend_signed_B friend 어셈블리를 지정 하므로 `Friend` 형식과 friend_signed_A에서 멤버입니다. 다음 코드를 포함 하는 파일.  
  
    ```vb  
    ' friend_signed_B.vb  
    ' Compile with:   
    ' Vbc /keyfile:FriendAssemblies.snk /r:friend_signed_A.dll friend_signed_B.vb  
    Module Sample  
        Public Sub Main()  
            Dim inst As New Class1  
            inst.Test()  
        End Sub  
    End Module  
    ```  
  
6.  컴파일 및 friend_signed_B 다음 명령을 사용 하 여 로그인 합니다.  
  
    ```vb  
    Vbc /keyfile:FriendAssemblies.snk /r:friend_signed_A.dll friend_signed_B.vb  
    ```  
  
     컴파일러에서 생성 된 어셈블리의 이름에 전달 된 friend 어셈블리 이름과 같아야 합니다.는 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>특성.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 사용 하 여 어셈블리를 명시적으로 설정할 수는 `/out` 컴파일러 옵션입니다. 자세한 내용은 참조 [/out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md)합니다.  
  
7.  Friend_signed_B.exe 파일을 실행 합니다.  
  
     프로그램은 문자열 "Class1.Test"를 인쇄합니다.  
  
## <a name="net-framework-security"></a>.NET Framework 보안  
 가 유사성 사이는 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>특성 및 <xref:System.Security.Permissions.StrongNameIdentityPermission>클래스가 있습니다.</xref:System.Security.Permissions.StrongNameIdentityPermission> </xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 주요 차이점은 <xref:System.Security.Permissions.StrongNameIdentityPermission>반면 코드의 특정 섹션을 실행 하는 보안 권한을 요구할 수 있습니다는 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>특성의 표시 유형을 제어 `Friend` 형식 및 멤버.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> </xref:System.Security.Permissions.StrongNameIdentityPermission>  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>   
 [어셈블리 및 전역 어셈블리 캐시 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)   
 [Friend 어셈블리 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/friend-assemblies.md)   
 [방법: 서명 되지 않은 Friend 어셈블리 (Visual Basic) 만들기](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md)   
 [/keyfile](../../../../visual-basic/reference/command-line-compiler/keyfile.md)   
 [Sn.exe (강력한 이름 도구)](https://msdn.microsoft.com/library/k5b5tt23)   
 [강력한 이름의 어셈블리 만들기 및 사용](https://msdn.microsoft.com/library/xwb8f617)   
 [프로그래밍 개념](../../../../visual-basic/programming-guide/concepts/index.md)
