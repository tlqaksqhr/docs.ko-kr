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
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: a8a7df331c8cd93de45d902cb9b6c67460952c6d
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-create-signed-friend-assemblies-visual-basic"></a><span data-ttu-id="47297-102">방법: 서명 된 Friend 어셈블리 (Visual Basic) 만들기</span><span class="sxs-lookup"><span data-stu-id="47297-102">How to: Create Signed Friend Assemblies (Visual Basic)</span></span>
<span data-ttu-id="47297-103">이 예제에는 어셈블리에 강력한 이름을 갖고 friend 어셈블리를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="47297-103">This example shows how to use friend assemblies with assemblies that have strong names.</span></span> <span data-ttu-id="47297-104">두 어셈블리는 강력한 이름을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47297-104">Both assemblies must be strong named.</span></span> <span data-ttu-id="47297-105">이 예에서 두 어셈블리가 모두 동일한 키를 사용 하지만 두 어셈블리에 대 한 서로 다른 키를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47297-105">Although both assemblies in this example use the same keys, you could use different keys for two assemblies.</span></span>  
  
### <a name="to-create-a-signed-assembly-and-a-friend-assembly"></a><span data-ttu-id="47297-106">서명된 된 어셈블리 및 friend 어셈블리를 만들려면</span><span class="sxs-lookup"><span data-stu-id="47297-106">To create a signed assembly and a friend assembly</span></span>  
  
1.  <span data-ttu-id="47297-107">명령 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="47297-107">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="47297-108">키 파일을 생성 하 고 해당 공개 키를 표시 하려면 다음 명령 시퀀스를 사용 하 여 강력한 이름 도구.</span><span class="sxs-lookup"><span data-stu-id="47297-108">Use the following sequence of commands with the Strong Name tool to generate a keyfile and to display its public key.</span></span> <span data-ttu-id="47297-109">자세한 내용은 [Sn.exe(강력한 이름 도구)](https://msdn.microsoft.com/library/k5b5tt23)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="47297-109">For more information, see [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23).</span></span>  
  
    1.  <span data-ttu-id="47297-110">이 예제에 대 한 강력한 이름 키를 생성 하 고 FriendAssemblies.snk 파일에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="47297-110">Generate a strong-name key for this example and store it in the file FriendAssemblies.snk:</span></span>  
  
         `sn -k FriendAssemblies.snk`  
  
    2.  <span data-ttu-id="47297-111">FriendAssemblies.snk에서 공개 키를 추출 하 고 FriendAssemblies.publickey에 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="47297-111">Extract the public key from FriendAssemblies.snk and put it into FriendAssemblies.publickey:</span></span>  
  
         `sn -p FriendAssemblies.snk FriendAssemblies.publickey`  
  
    3.  <span data-ttu-id="47297-112">FriendAssemblies.publickey 파일에 저장 된 공개 키를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="47297-112">Display the public key stored in the file FriendAssemblies.publickey:</span></span>  
  
         `sn -tp FriendAssemblies.publickey`  
  
3.  <span data-ttu-id="47297-113">라는 Visual Basic 파일을 만듭니다 `friend_signed_A` 하는 다음 코드를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="47297-113">Create a Visual Basic file named `friend_signed_A` that contains the following code.</span></span> <span data-ttu-id="47297-114">코드를 사용 하는 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>friend_signed_B friend 어셈블리 선언 하는 특성입니다.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span><span class="sxs-lookup"><span data-stu-id="47297-114">The code uses the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute to declare friend_signed_B as a friend assembly.</span></span>  
  
     <span data-ttu-id="47297-115">강력한 이름 도구를 실행할 때마다 새 공개 키를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="47297-115">The Strong Name tool generates a new public key every time it runs.</span></span> <span data-ttu-id="47297-116">따라서 다음 예제와 같이 방금 생성 한 공개 키도 다음 코드에 공개 키를 대체 해야 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47297-116">Therefore, you must replace the public key in the following code with the public key you just generated, as shown in the following example.</span></span>  
  
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
  
4.  <span data-ttu-id="47297-117">컴파일 및 friend_signed_A 다음 명령을 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="47297-117">Compile and sign friend_signed_A by using the following command.</span></span>  
  
    ```vb  
    Vbc /target:library /keyfile:FriendAssemblies.snk friend_signed_A.vb  
    ```  
  
5.  <span data-ttu-id="47297-118">라는 Visual Basic 파일 만들기 `friend_signed_B` 다음 코드를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="47297-118">Create a Visual Basic file that is named `friend_signed_B` and contains the following code.</span></span> <span data-ttu-id="47297-119">Friend_signed_B의 코드에 액세스할 수 friend_signed_A friend_signed_B friend 어셈블리를 지정 하므로 `Friend` 형식과 friend_signed_A에서 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="47297-119">Because friend_signed_A specifies friend_signed_B as a friend assembly, the code in friend_signed_B can access `Friend` types and members from friend_signed_A.</span></span> <span data-ttu-id="47297-120">다음 코드를 포함 하는 파일.</span><span class="sxs-lookup"><span data-stu-id="47297-120">The file contains the following code.</span></span>  
  
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
  
6.  <span data-ttu-id="47297-121">컴파일 및 friend_signed_B 다음 명령을 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="47297-121">Compile and sign friend_signed_B by using the following command.</span></span>  
  
    ```vb  
    Vbc /keyfile:FriendAssemblies.snk /r:friend_signed_A.dll friend_signed_B.vb  
    ```  
  
     <span data-ttu-id="47297-122">컴파일러에서 생성 된 어셈블리의 이름에 전달 된 friend 어셈블리 이름과 같아야 합니다.는 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>특성.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span><span class="sxs-lookup"><span data-stu-id="47297-122">The name of the assembly generated by the compiler must match the friend assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute.</span></span> <span data-ttu-id="47297-123">사용 하 여 어셈블리를 명시적으로 설정할 수는 `/out` 컴파일러 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="47297-123">You can explicitly set the assembly by using the `/out` compiler option.</span></span> <span data-ttu-id="47297-124">자세한 내용은 참조 [/out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="47297-124">For more information, see [/out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md).</span></span>  
  
7.  <span data-ttu-id="47297-125">Friend_signed_B.exe 파일을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="47297-125">Run the friend_signed_B.exe file.</span></span>  
  
     <span data-ttu-id="47297-126">프로그램은 문자열 "Class1.Test"를 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="47297-126">The program prints the string "Class1.Test".</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="47297-127">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="47297-127">.NET Framework Security</span></span>  
 <span data-ttu-id="47297-128">가 유사성 사이는 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>특성 및 <xref:System.Security.Permissions.StrongNameIdentityPermission>클래스가 있습니다.</xref:System.Security.Permissions.StrongNameIdentityPermission> </xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span><span class="sxs-lookup"><span data-stu-id="47297-128">There are similarities between the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute and the <xref:System.Security.Permissions.StrongNameIdentityPermission> class.</span></span> <span data-ttu-id="47297-129">주요 차이점은 <xref:System.Security.Permissions.StrongNameIdentityPermission>반면 코드의 특정 섹션을 실행 하는 보안 권한을 요구할 수 있습니다는 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>특성의 표시 유형을 제어 `Friend` 형식 및 멤버.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> </xref:System.Security.Permissions.StrongNameIdentityPermission></span><span class="sxs-lookup"><span data-stu-id="47297-129">The main difference is that <xref:System.Security.Permissions.StrongNameIdentityPermission> can demand security permissions to run a particular section of code, whereas the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute controls the visibility of `Friend` types and members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47297-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="47297-130">See Also</span></span>  
 <span data-ttu-id="47297-131"><xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span><span class="sxs-lookup"><span data-stu-id="47297-131"><xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span></span>   
<span data-ttu-id="47297-132"> [어셈블리 및 전역 어셈블리 캐시 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span><span class="sxs-lookup"><span data-stu-id="47297-132"> [Assemblies and the Global Assembly Cache (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span></span>  
<span data-ttu-id="47297-133"> [Friend 어셈블리 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/friend-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="47297-133"> [Friend Assemblies (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/friend-assemblies.md) </span></span>  
<span data-ttu-id="47297-134"> [방법: 서명 되지 않은 Friend 어셈블리 (Visual Basic) 만들기](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="47297-134"> [How to: Create Unsigned Friend Assemblies (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md) </span></span>  
<span data-ttu-id="47297-135"> [/keyfile](../../../../visual-basic/reference/command-line-compiler/keyfile.md) </span><span class="sxs-lookup"><span data-stu-id="47297-135"> [/keyfile](../../../../visual-basic/reference/command-line-compiler/keyfile.md) </span></span>  
<span data-ttu-id="47297-136"> [Sn.exe (강력한 이름 도구)](https://msdn.microsoft.com/library/k5b5tt23) </span><span class="sxs-lookup"><span data-stu-id="47297-136"> [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23) </span></span>  
<span data-ttu-id="47297-137"> [강력한 이름의 어셈블리 만들기 및 사용](https://msdn.microsoft.com/library/xwb8f617) </span><span class="sxs-lookup"><span data-stu-id="47297-137"> [Creating and Using Strong-Named Assemblies](https://msdn.microsoft.com/library/xwb8f617) </span></span>  
<span data-ttu-id="47297-138"> [프로그래밍 개념](../../../../visual-basic/programming-guide/concepts/index.md)</span><span class="sxs-lookup"><span data-stu-id="47297-138"> [Programming Concepts](../../../../visual-basic/programming-guide/concepts/index.md)</span></span>
