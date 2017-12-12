---
title: "방법: 서명된 Friend 어셈블리 만들기(C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: bab62063-61e6-453f-905f-77673df9534e
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d3d9d4c549654341c0739cc8132d953623482d62
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/09/2017
---
# <a name="how-to-create-signed-friend-assemblies-c"></a><span data-ttu-id="5104a-102">방법: 서명된 Friend 어셈블리 만들기(C#)</span><span class="sxs-lookup"><span data-stu-id="5104a-102">How to: Create Signed Friend Assemblies (C#)</span></span>
<span data-ttu-id="5104a-103">이 예제에서는 강력한 이름을 가진 어셈블리와 함께 friend 어셈블리를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5104a-103">This example shows how to use friend assemblies with assemblies that have strong names.</span></span> <span data-ttu-id="5104a-104">두 어셈블리에 모두 강력한 이름을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5104a-104">Both assemblies must be strong named.</span></span> <span data-ttu-id="5104a-105">이 예제의 두 어셈블리는 모두 동일한 키를 사용하지만 두 어셈블리에 서로 다른 키를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5104a-105">Although both assemblies in this example use the same keys, you could use different keys for two assemblies.</span></span>  
  
### <a name="to-create-a-signed-assembly-and-a-friend-assembly"></a><span data-ttu-id="5104a-106">서명된 어셈블리 및 friend 어셈블리를 만들려면</span><span class="sxs-lookup"><span data-stu-id="5104a-106">To create a signed assembly and a friend assembly</span></span>  
  
1.  <span data-ttu-id="5104a-107">명령 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5104a-107">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="5104a-108">강력한 이름 도구와 함께 다음 명령 시퀀스를 사용하여 키 파일을 생성하고 해당 공개 키를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5104a-108">Use the following sequence of commands with the Strong Name tool to generate a keyfile and to display its public key.</span></span> <span data-ttu-id="5104a-109">자세한 내용은 [Sn.exe(강력한 이름 도구)](https://msdn.microsoft.com/library/k5b5tt23)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5104a-109">For more information, see [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23).</span></span>  
  
    1.  <span data-ttu-id="5104a-110">이 예제에 대한 강력한 이름 키를 생성하고 FriendAssemblies.snk 파일에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="5104a-110">Generate a strong-name key for this example and store it in the file FriendAssemblies.snk:</span></span>  
  
         `sn -k FriendAssemblies.snk`  
  
    2.  <span data-ttu-id="5104a-111">FriendAssemblies.snk에서 공개 키를 추출하고 FriendAssemblies.publickey에 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="5104a-111">Extract the public key from FriendAssemblies.snk and put it into FriendAssemblies.publickey:</span></span>  
  
         `sn -p FriendAssemblies.snk FriendAssemblies.publickey`  
  
    3.  <span data-ttu-id="5104a-112">FriendAssemblies.publickey 파일에 저장된 공개 키를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5104a-112">Display the public key stored in the file FriendAssemblies.publickey:</span></span>  
  
         `sn -tp FriendAssemblies.publickey`  
  
3.  <span data-ttu-id="5104a-113">다음 코드가 포함된 `friend_signed_A`라는 C# 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5104a-113">Create a C# file named `friend_signed_A` that contains the following code.</span></span> <span data-ttu-id="5104a-114">코드에서는 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 특성을 사용하여 friend_signed_B를 friend 어셈블리로 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="5104a-114">The code uses the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute to declare friend_signed_B as a friend assembly.</span></span>  
  
     <span data-ttu-id="5104a-115">강력한 이름 도구는 실행할 때마다 새 공개 키를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="5104a-115">The Strong Name tool generates a new public key every time it runs.</span></span> <span data-ttu-id="5104a-116">따라서 다음 예제와 같이 다음 코드의 공개 키를 방금 생성한 공개 키로 대체해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5104a-116">Therefore, you must replace the public key in the following code with the public key you just generated, as shown in the following example.</span></span>  
  
    ```csharp  
    // friend_signed_A.cs  
    // Compile with:   
    // csc /target:library /keyfile:FriendAssemblies.snk friend_signed_A.cs  
    using System.Runtime.CompilerServices;  
  
    [assembly: InternalsVisibleTo("friend_signed_B, PublicKey=0024000004800000940000000602000000240000525341310004000001000100e3aedce99b7e10823920206f8e46cd5558b4ec7345bd1a5b201ffe71660625dcb8f9a08687d881c8f65a0dcf042f81475d2e88f3e3e273c8311ee40f952db306c02fbfc5d8bc6ee1e924e6ec8fe8c01932e0648a0d3e5695134af3bb7fab370d3012d083fa6b83179dd3d031053f72fc1f7da8459140b0af5afc4d2804deccb6")]  
    class Class1  
    {  
        public void Test()  
        {  
            System.Console.WriteLine("Class1.Test");  
            System.Console.ReadLine();  
        }  
    }  
    ```  
  
4.  <span data-ttu-id="5104a-117">다음 명령을 사용하여 friend_signed_A를 컴파일하고 서명합니다.</span><span class="sxs-lookup"><span data-stu-id="5104a-117">Compile and sign friend_signed_A by using the following command.</span></span>  
  
    ```csharp  
    csc /target:library /keyfile:FriendAssemblies.snk friend_signed_A.cs  
    ```  
  
5.  <span data-ttu-id="5104a-118">다음 코드가 포함된 `friend_signed_B`라는 C# 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5104a-118">Create a C# file that is named `friend_signed_B` and contains the following code.</span></span> <span data-ttu-id="5104a-119">friend_signed_A는 friend_signed_B를 friend 어셈블리로 지정하기 때문에 friend_signed_B의 코드는 friend_signed_A의 `internal` 형식과 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5104a-119">Because friend_signed_A specifies friend_signed_B as a friend assembly, the code in friend_signed_B can access `internal` types and members from friend_signed_A.</span></span> <span data-ttu-id="5104a-120">파일에는 다음 코드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5104a-120">The file contains the following code.</span></span>  
  
    ```csharp  
    // friend_signed_B.cs  
    // Compile with:   
    // csc /keyfile:FriendAssemblies.snk /r:friend_signed_A.dll /out:friend_signed_B.exe friend_signed_B.cs  
    public class Program  
    {  
        static void Main()  
        {  
            Class1 inst = new Class1();  
            inst.Test();  
        }  
    }  
    ```  
  
6.  <span data-ttu-id="5104a-121">다음 명령을 사용하여 friend_signed_B를 컴파일하고 서명합니다.</span><span class="sxs-lookup"><span data-stu-id="5104a-121">Compile and sign friend_signed_B by using the following command.</span></span>  
  
    ```csharp  
    csc /keyfile:FriendAssemblies.snk /r:friend_signed_A.dll /out:friend_signed_B.exe friend_signed_B.cs  
    ```  
  
     <span data-ttu-id="5104a-122">컴파일러에서 생성된 어셈블리 이름은 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 특성에 전달된 friend 어셈블리 이름과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5104a-122">The name of the assembly generated by the compiler must match the friend assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute.</span></span> <span data-ttu-id="5104a-123">`/out` 컴파일러 옵션을 사용하여 출력 어셈블리(.exe 또는 .dll)의 이름을 명시적으로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5104a-123">You must explicitly specify the name of the output assembly (.exe or .dll) by using the `/out` compiler option.</span></span>  <span data-ttu-id="5104a-124">자세한 내용은 [/out(C# 컴파일러 옵션)](../../../../csharp/language-reference/compiler-options/out-compiler-option.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5104a-124">For more information, see [/out (C# Compiler Options)](../../../../csharp/language-reference/compiler-options/out-compiler-option.md).</span></span>  
  
7.  <span data-ttu-id="5104a-125">friend_signed_B.exe 파일을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="5104a-125">Run the friend_signed_B.exe file.</span></span>  
  
     <span data-ttu-id="5104a-126">프로그램에서 "Class1.Test" 문자열을 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="5104a-126">The program prints the string "Class1.Test".</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="5104a-127">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="5104a-127">.NET Framework Security</span></span>  
 <span data-ttu-id="5104a-128"><xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 특성과 <xref:System.Security.Permissions.StrongNameIdentityPermission> 클래스 간에는 유사점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5104a-128">There are similarities between the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute and the <xref:System.Security.Permissions.StrongNameIdentityPermission> class.</span></span> <span data-ttu-id="5104a-129">주요 차이점은 <xref:System.Security.Permissions.StrongNameIdentityPermission>은 코드의 특정 섹션을 실행하는 보안 권한을 요구할 수 있는 반면, <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 특성은 `internal` 형식 및 멤버의 표시 유형을 제어한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5104a-129">The main difference is that <xref:System.Security.Permissions.StrongNameIdentityPermission> can demand security permissions to run a particular section of code, whereas the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute controls the visibility of `internal` types and members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5104a-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5104a-130">See Also</span></span>  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>  
 [<span data-ttu-id="5104a-131">어셈블리 및 전역 어셈블리 캐시(C#)</span><span class="sxs-lookup"><span data-stu-id="5104a-131">Assemblies and the Global Assembly Cache (C#)</span></span>](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md)  
 [<span data-ttu-id="5104a-132">Friend 어셈블리(C#)</span><span class="sxs-lookup"><span data-stu-id="5104a-132">Friend Assemblies (C#)</span></span>](../../../../csharp/programming-guide/concepts/assemblies-gac/friend-assemblies.md)  
 [<span data-ttu-id="5104a-133">방법: 서명되지 않은 Friend 어셈블리 만들기(C#)</span><span class="sxs-lookup"><span data-stu-id="5104a-133">How to: Create Unsigned Friend Assemblies (C#)</span></span>](../../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md)  
 [<span data-ttu-id="5104a-134">/keyfile</span><span class="sxs-lookup"><span data-stu-id="5104a-134">/keyfile</span></span>](../../../../visual-basic/reference/command-line-compiler/keyfile.md)  
 [<span data-ttu-id="5104a-135">Sn.exe(강력한 이름 도구)</span><span class="sxs-lookup"><span data-stu-id="5104a-135">Sn.exe (Strong Name Tool)</span></span>](https://msdn.microsoft.com/library/k5b5tt23)  
 [<span data-ttu-id="5104a-136">강력한 이름의 어셈블리 만들기 및 사용</span><span class="sxs-lookup"><span data-stu-id="5104a-136">Creating and Using Strong-Named Assemblies</span></span>](../../../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)  
 [<span data-ttu-id="5104a-137">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="5104a-137">C# Programming Guide</span></span>](../../../../csharp/programming-guide/index.md)
