---
title: "Friend 어셈블리 (Visual Basic) | Microsoft 문서"
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
ms.assetid: 9b3d5716-e6e4-47a7-a3e9-084d7fba5c28
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
ms.openlocfilehash: 23c9167bf6a632b53202bdc56aebb2248065e967
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="friend-assemblies-visual-basic"></a><span data-ttu-id="a3e7b-102">Friend 어셈블리 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a3e7b-102">Friend Assemblies (Visual Basic)</span></span>
<span data-ttu-id="a3e7b-103">A *friend 어셈블리* 어셈블리가 다른 어셈블리에 액세스할 수 있는 [친구](../../../../visual-basic/language-reference/modifiers/friend.md) 형식 및 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="a3e7b-103">A *friend assembly* is an assembly that can access another assembly's [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) types and members.</span></span> <span data-ttu-id="a3e7b-104">Friend 어셈블리와 어셈블리를 식별 하는 경우에 더 이상 형식 및 멤버를 표시 하려면 해당에서 공용으로 다른 어셈블리에서 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a3e7b-104">If you identify an assembly as a friend assembly, you no longer have to mark types and members as public in order for them to be accessed by other assemblies.</span></span> <span data-ttu-id="a3e7b-105">다음과 같은 시나리오에서 특히 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e7b-105">This is especially convenient in the following scenarios:</span></span>  
  
-   <span data-ttu-id="a3e7b-106">단위 테스트 동안 테스트 코드에서 실행 하는 경우 별도 어셈블리를 사용할 수 있지만 필요으로 표시 되는 테스트 중인 어셈블리의 멤버에 대 `Friend`합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e7b-106">During unit testing, when test code runs in a separate assembly but requires access to members in the assembly being tested that are marked as `Friend`.</span></span>  
  
-   <span data-ttu-id="a3e7b-107">클래스 라이브러리를 개발 하는 시점과 라이브러리에 추가 된 별도 어셈블리에 포함 되어 있지만로 표시 된 기존 어셈블리의 멤버에 대 한 액세스 권한이 필요한 `Friend`합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e7b-107">When you are developing a class library and additions to the library are contained in separate assemblies but require access to members in existing assemblies that are marked as `Friend`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a3e7b-108">주의</span><span class="sxs-lookup"><span data-stu-id="a3e7b-108">Remarks</span></span>  
 <span data-ttu-id="a3e7b-109">사용할 수는 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>지정된 된 어셈블리에 대 한 하나 이상의 friend 어셈블리를 식별 하는 특성입니다.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span><span class="sxs-lookup"><span data-stu-id="a3e7b-109">You can use the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute to identify one or more friend assemblies for a given assembly.</span></span> <span data-ttu-id="a3e7b-110">다음 예제에서는 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>어셈블리 A에에서 특성을 어셈블리를 지정 `AssemblyB` friend 어셈블리로.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span><span class="sxs-lookup"><span data-stu-id="a3e7b-110">The following example uses the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute in assembly A and specifies assembly `AssemblyB` as a friend assembly.</span></span> <span data-ttu-id="a3e7b-111">이렇게 하면 어셈블리 `AssemblyB` 모든 형식과 멤버 변수로 표시 되는 어셈블리에 대 한 액세스 `Friend`합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e7b-111">This gives assembly `AssemblyB` access to all types and members in assembly A that are marked as `Friend`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a3e7b-112">어셈블리를 컴파일할 때 (어셈블리 `AssemblyB`) 액세스 하는 어셈블리 내부 형식이 나 다른 어셈블리의 내부 멤버 (어셈블리 *A*)를 사용 하 여 출력 파일 (.exe 또는.dll)의 이름을 명시적으로 지정 해야는 **/출력** 컴파일러 옵션.</span><span class="sxs-lookup"><span data-stu-id="a3e7b-112">When you compile an assembly (assembly `AssemblyB`) that will access internal types or internal members of another assembly (assembly *A*), you must explicitly specify the name of the output file (.exe or .dll) by using the **/out** compiler option.</span></span> <span data-ttu-id="a3e7b-113">컴파일러가 외부 참조에서 바인딩할 때 구성 하는 어셈블리의 이름을 아직 생성 되지 않은 때문에 이것이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e7b-113">This is required because the compiler has not yet generated the name for the assembly it is building at the time it is binding to external references.</span></span> <span data-ttu-id="a3e7b-114">자세한 내용은 참조 [/out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e7b-114">For more information, see [/out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md).</span></span>  
  
```vb  
Imports System.Runtime.CompilerServices  
Imports System  
<Assembly: InternalsVisibleTo("AssemblyB")>   
  
' Friend class.  
Friend Class FriendClass  
    Public Sub Test()  
        Console.WriteLine("Sample Class")  
    End Sub  
End Class  
  
' Public class with a Friend method.  
Public Class ClassWithFriendMethod  
    Friend Sub Test()  
        Console.WriteLine("Sample Method")  
    End Sub  
End Class  
  
```  
  
 <span data-ttu-id="a3e7b-115">친구에 액세스할 수 대로 명시적으로 지정 하는 어셈블리만 `Friend` 형식 및 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="a3e7b-115">Only assemblies that you explicitly specify as friends can access `Friend` types and members.</span></span> <span data-ttu-id="a3e7b-116">예를 들어, 어셈블리 B가 어셈블리 A 및 어셈블리 C 참조 어셈블리 B의 친구, C 없는 경우에 대 한 액세스 `Friend` A에는 형식</span><span class="sxs-lookup"><span data-stu-id="a3e7b-116">For example, if assembly B is a friend of assembly A and assembly C references assembly B, C does not have access to `Friend` types in A.</span></span>  
  
 <span data-ttu-id="a3e7b-117">컴파일러에 전달 된 friend 어셈블리 이름의 몇 가지 기본 유효성 검사는 수행 된 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>특성.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span><span class="sxs-lookup"><span data-stu-id="a3e7b-117">The compiler performs some basic validation of the friend assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute.</span></span> <span data-ttu-id="a3e7b-118">하는 경우 어셈블리 *A* 선언 *B* friend 어셈블리와 유효성 검사 규칙은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a3e7b-118">If assembly *A* declares *B* as a friend assembly, the validation rules are as follows:</span></span>  
  
-   <span data-ttu-id="a3e7b-119">하는 경우 어셈블리 *A* 은 강력한 이름, 어셈블리 *B* 또한 강력한 이름을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e7b-119">If assembly *A* is strong named, assembly *B* must also be strong named.</span></span> <span data-ttu-id="a3e7b-120">특성에 전달 되는 friend 어셈블리 이름은 어셈블리 이름 및 어셈블리에 서명 하는 데 사용 되는 강력한 이름 키의 공개 키의 이루어져야 *B*합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e7b-120">The friend assembly name that is passed to the attribute must consist of the assembly name and the public key of the strong-name key that is used to sign assembly *B*.</span></span>  
  
     <span data-ttu-id="a3e7b-121">에 전달 되는 friend 어셈블리 이름은 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>특성에는 어셈블리의 강력한 이름 수 없습니다 *B*: 어셈블리 버전, 문화권, 아키텍처 또는 공개 키 토큰을 포함 하지 마십시오.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span><span class="sxs-lookup"><span data-stu-id="a3e7b-121">The friend assembly name that is passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute cannot be the strong name of assembly *B*: do not include the assembly version, culture, architecture, or public key token.</span></span>  
  
-   <span data-ttu-id="a3e7b-122">하는 경우 어셈블리 *A* 강력한 이름이 지정 되지 않은, friend 어셈블리 이름은 어셈블리 이름만으로 구성 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e7b-122">If assembly *A* is not strong named, the friend assembly name should consist of only the assembly name.</span></span> <span data-ttu-id="a3e7b-123">자세한 내용은 참조 [하는 방법: 만들 서명 되지 않은 Friend 어셈블리 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e7b-123">For more information, see [How to: Create Unsigned Friend Assemblies (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md).</span></span>  
  
-   <span data-ttu-id="a3e7b-124">하는 경우 어셈블리 *B* 강하고 라는 어셈블리에 대 한 강력한 이름 키를 지정 해야 *B* 프로젝트 설정이 나 명령줄을 사용 하 여 `/keyfile` 컴파일러 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="a3e7b-124">If assembly *B* is strong named, you must specify the strong-name key for assembly *B* by using the project setting or the command-line `/keyfile` compiler option.</span></span> <span data-ttu-id="a3e7b-125">자세한 내용은 참조 [하는 방법: 서명 된 Friend 어셈블리 만들기 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e7b-125">For more information, see [How to: Create Signed Friend Assemblies (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md).</span></span>  
  
 <span data-ttu-id="a3e7b-126"><xref:System.Security.Permissions.StrongNameIdentityPermission>클래스는 다음과 같은 차이점이와 형식을 공유 하는 기능도 제공:</xref:System.Security.Permissions.StrongNameIdentityPermission></span><span class="sxs-lookup"><span data-stu-id="a3e7b-126">The <xref:System.Security.Permissions.StrongNameIdentityPermission> class also provides the ability to share types, with the following differences:</span></span>  
  
-   <span data-ttu-id="a3e7b-127"><xref:System.Security.Permissions.StrongNameIdentityPermission>friend 어셈블리는 전체 어셈블리에 적용 하는 동안은 개별 형식에 적용 됩니다.</xref:System.Security.Permissions.StrongNameIdentityPermission></span><span class="sxs-lookup"><span data-stu-id="a3e7b-127"><xref:System.Security.Permissions.StrongNameIdentityPermission> applies to an individual type, while a friend assembly applies to the whole assembly.</span></span>  
  
-   <span data-ttu-id="a3e7b-128">어셈블리에서 형식의 수백 경우 *A* 어셈블리와 공유 하려는 *B*을 추가 해야 <xref:System.Security.Permissions.StrongNameIdentityPermission>모든 사람이.</xref:System.Security.Permissions.StrongNameIdentityPermission></span><span class="sxs-lookup"><span data-stu-id="a3e7b-128">If there are hundreds of types in assembly *A* that you want to share with assembly *B*, you have to add <xref:System.Security.Permissions.StrongNameIdentityPermission> to all of them.</span></span> <span data-ttu-id="a3e7b-129">Friend 어셈블리를 사용 하는 경우 친구 관계를 한 번 선언 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e7b-129">If you use a friend assembly, you only need to declare the friend relationship once.</span></span>  
  
-   <span data-ttu-id="a3e7b-130">사용 하는 경우 <xref:System.Security.Permissions.StrongNameIdentityPermission>를 공유 하려는 형식 public으로 선언 해야 합니다.</xref:System.Security.Permissions.StrongNameIdentityPermission></span><span class="sxs-lookup"><span data-stu-id="a3e7b-130">If you use <xref:System.Security.Permissions.StrongNameIdentityPermission>, the types you want to share have to be declared as public.</span></span> <span data-ttu-id="a3e7b-131">공유 형식으로 선언 된 friend 어셈블리를 사용 하는 경우 `Friend`합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e7b-131">If you use a friend assembly, the shared types are declared as `Friend`.</span></span>  
  
 <span data-ttu-id="a3e7b-132">어셈블리의 액세스 하는 방법에 대 한 내용은 `Friend` 형식 및 메서드는 모듈 파일 (.netmodule 확장 파일)에서 참조 [/moduleassemblyname (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/moduleassemblyname.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a3e7b-132">For information about how to access an assembly's `Friend` types and methods from a module file (a file with the .netmodule extension), see [/moduleassemblyname (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/moduleassemblyname.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3e7b-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a3e7b-133">See Also</span></span>  
 <span data-ttu-id="a3e7b-134"><xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span><span class="sxs-lookup"><span data-stu-id="a3e7b-134"><xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span></span>   
 <span data-ttu-id="a3e7b-135"><xref:System.Security.Permissions.StrongNameIdentityPermission></xref:System.Security.Permissions.StrongNameIdentityPermission></span><span class="sxs-lookup"><span data-stu-id="a3e7b-135"><xref:System.Security.Permissions.StrongNameIdentityPermission></span></span>   
<span data-ttu-id="a3e7b-136"> [방법: 서명 되지 않은 Friend 어셈블리 (Visual Basic) 만들기](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="a3e7b-136"> [How to: Create Unsigned Friend Assemblies (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md) </span></span>  
<span data-ttu-id="a3e7b-137"> [방법: 서명 된 Friend 어셈블리 (Visual Basic) 만들기](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="a3e7b-137"> [How to: Create Signed Friend Assemblies (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md) </span></span>  
<span data-ttu-id="a3e7b-138"> [어셈블리 및 전역 어셈블리 캐시 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span><span class="sxs-lookup"><span data-stu-id="a3e7b-138"> [Assemblies and the Global Assembly Cache (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span></span>  
<span data-ttu-id="a3e7b-139"> [프로그래밍 개념](../../../../visual-basic/programming-guide/concepts/index.md)</span><span class="sxs-lookup"><span data-stu-id="a3e7b-139"> [Programming Concepts](../../../../visual-basic/programming-guide/concepts/index.md)</span></span>
