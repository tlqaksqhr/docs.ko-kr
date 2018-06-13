---
title: '방법: GenericPrincipal 및 GenericIdentity 개체 만들기'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Creating Generic Identity Objects
- GenericPrincipal Objects
- Creating GenericPrincipal Objects
- GenericIdentity Objects
ms.assetid: 465694cf-258b-4747-9dae-35b01a5bcdbb
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 65fd078b6be9dbcdfc03e34285d70a6bfe42d87b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33581780"
---
# <a name="how-to-create-genericprincipal-and-genericidentity-objects"></a><span data-ttu-id="d775a-102">방법: GenericPrincipal 및 GenericIdentity 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="d775a-102">How to: Create GenericPrincipal and GenericIdentity Objects</span></span>
<span data-ttu-id="d775a-103">사용할 수는 <xref:System.Security.Principal.GenericIdentity> 클래스와 함께 <xref:System.Security.Principal.GenericPrincipal> 를 Windows 도메인의 독립적인 존재 하는 권한 부여 체계를 만드는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="d775a-103">You can use the <xref:System.Security.Principal.GenericIdentity> class in conjunction with the <xref:System.Security.Principal.GenericPrincipal> class to create an authorization scheme that exists independent of a Windows domain.</span></span>  
  
### <a name="to-create-a-genericprincipal-object"></a><span data-ttu-id="d775a-104">GenericPrincipal 개체를 만들려면</span><span class="sxs-lookup"><span data-stu-id="d775a-104">To create a GenericPrincipal object</span></span>  
  
1.  <span data-ttu-id="d775a-105">identity 클래스의 새 인스턴스를 만들고, 유지하고 싶은 이름으로 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="d775a-105">Create a new instance of the identity class and initialize it with the name you want it to hold.</span></span> <span data-ttu-id="d775a-106">다음 코드에서는 새 **GenericIdentity** 개체를 만들고 이를 `MyUser`라는 이름으로 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="d775a-106">The following code creates a new **GenericIdentity** object and initializes it with the name `MyUser`.</span></span>  
  
    ```vb  
    Dim MyIdentity As New GenericIdentity("MyUser")  
    ```  
  
    ```csharp  
    GenericIdentity MyIdentity = new GenericIdentity("MyUser");  
    ```  
  
2.  <span data-ttu-id="d775a-107">**GenericPrincipal** 클래스의 새 인스턴스를 만들고 이를 이전에 만든 **GenericIdentity** 개체 및 해당 Principal에 연결할 역할을 나타내는 문자열 배열로 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="d775a-107">Create a new instance of the **GenericPrincipal** class and initialize it with the previously created **GenericIdentity** object and an array of strings that represent the roles that you want associated with this principal.</span></span> <span data-ttu-id="d775a-108">다음의 코드 예제에서는 관리자 역할 및 사용자 역할을 나타내는 문자열 배열을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d775a-108">The following code example specifies an array of strings that represent an administrator role and a user role.</span></span> <span data-ttu-id="d775a-109">이렇게 하면 앞의 **GenericIdentity** 및 문자열 배열을 사용하여 **GenericPrincipal**이 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="d775a-109">The **GenericPrincipal** is then initialized with the previous **GenericIdentity** and the string array.</span></span>  
  
    ```vb  
    Dim MyStringArray As String() = {"Manager", "Teller"}  
    DIm MyPrincipal As New GenericPrincipal(MyIdentity, MyStringArray)  
    ```  
  
    ```csharp  
    String[] MyStringArray = {"Manager", "Teller"};  
    GenericPrincipal MyPrincipal = new GenericPrincipal(MyIdentity, MyStringArray);  
    ```  
  
3.  <span data-ttu-id="d775a-110">해당 Principal을 현재 스레드에 연결하려면 다음 코드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d775a-110">Use the following code to attach the principal to the current thread.</span></span> <span data-ttu-id="d775a-111">이 중요 한 주 서버에서 여러 번 유효성이 검사 합니다, 응용 프로그램에서 실행 되는 다른 코드에서 확인할 수 있어야 하거나 것을 확인 해야 합니다는 <xref:System.Security.Permissions.PrincipalPermission> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="d775a-111">This is valuable in situations where the principal must be validated several times, it must be validated by other code running in your application, or it must be validated by a <xref:System.Security.Permissions.PrincipalPermission> object.</span></span> <span data-ttu-id="d775a-112">Principal 개체를 스레드에 연결하지 않고도 이 개체에 대해 역할 기반 확인을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d775a-112">You can still perform role-based validation on the principal object without attaching it to the thread.</span></span> <span data-ttu-id="d775a-113">자세한 내용은 [Principal 개체 바꾸기](../../../docs/standard/security/replacing-a-principal-object.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d775a-113">For more information, see [Replacing a Principal Object](../../../docs/standard/security/replacing-a-principal-object.md).</span></span>  
  
    ```vb  
    Thread.CurrentPrincipal = MyPrincipal  
    ```  
  
    ```csharp  
    Thread.CurrentPrincipal = MyPrincipal;  
    ```  
  
## <a name="example"></a><span data-ttu-id="d775a-114">예제</span><span class="sxs-lookup"><span data-stu-id="d775a-114">Example</span></span>  
 <span data-ttu-id="d775a-115">다음 코드 예제에서는 **GenericPrincipal** 및 **GenericIdentity**의 인스턴스를 만드는 방법을 보여 줍니다</span><span class="sxs-lookup"><span data-stu-id="d775a-115">The following code example demonstrates how to create an instance of a **GenericPrincipal** and a **GenericIdentity**.</span></span> <span data-ttu-id="d775a-116">이 코드에서는 해당 개체의 값을 콘솔에 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d775a-116">This code displays the values of these objects to the console.</span></span>  
  
```vb  
Imports System  
Imports System.Security.Principal  
Imports System.Threading  
  
Public Class Class1  
  
    Public Shared Sub Main()  
        ' Create generic identity.  
        Dim MyIdentity As New GenericIdentity("MyIdentity")  
  
        ' Create generic principal.  
        Dim MyStringArray As String() =  {"Manager", "Teller"}  
        Dim MyPrincipal As New GenericPrincipal(MyIdentity, MyStringArray)  
  
        ' Attach the principal to the current thread.  
        ' This is not required unless repeated validation must occur,  
        ' other code in your application must validate, or the   
        ' PrincipalPermisson object is used.   
        Thread.CurrentPrincipal = MyPrincipal  
  
        ' Print values to the console.  
        Dim Name As String = MyPrincipal.Identity.Name  
        Dim Auth As Boolean = MyPrincipal.Identity.IsAuthenticated  
        Dim IsInRole As Boolean = MyPrincipal.IsInRole("Manager")  
  
        Console.WriteLine("The Name is: {0}", Name)  
        Console.WriteLine("The IsAuthenticated is: {0}", Auth)  
        Console.WriteLine("Is this a Manager? {0}", IsInRole)  
  
    End Sub  
  
End Class  
```  
  
```csharp  
using System;  
using System.Security.Principal;  
using System.Threading;  
  
public class Class1  
{  
    public static int Main(string[] args)  
    {  
    // Create generic identity.  
    GenericIdentity MyIdentity = new GenericIdentity("MyIdentity");  
  
    // Create generic principal.  
    String[] MyStringArray = {"Manager", "Teller"};  
    GenericPrincipal MyPrincipal =   
        new GenericPrincipal(MyIdentity, MyStringArray);  
  
    // Attach the principal to the current thread.  
    // This is not required unless repeated validation must occur,  
    // other code in your application must validate, or the   
    // PrincipalPermisson object is used.   
    Thread.CurrentPrincipal = MyPrincipal;  
  
    // Print values to the console.  
    String Name =  MyPrincipal.Identity.Name;  
    bool Auth =  MyPrincipal.Identity.IsAuthenticated;   
    bool IsInRole =  MyPrincipal.IsInRole("Manager");  
  
    Console.WriteLine("The Name is: {0}", Name);  
    Console.WriteLine("The IsAuthenticated is: {0}", Auth);  
    Console.WriteLine("Is this a Manager? {0}", IsInRole);  
  
    return 0;  
    }  
}  
```  
  
 <span data-ttu-id="d775a-117">응용 프로그램을 실행하면 다음과 같은 결과가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d775a-117">When executed, the application displays output similar to the following.</span></span>  
  
```  
The Name is: MyIdentity  
The IsAuthenticated is: True  
Is this a Manager? True  
```  
  
## <a name="see-also"></a><span data-ttu-id="d775a-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d775a-118">See Also</span></span>  
 <xref:System.Security.Principal.GenericIdentity>  
 <xref:System.Security.Principal.GenericPrincipal>  
 <xref:System.Security.Permissions.PrincipalPermission>  
 [<span data-ttu-id="d775a-119">Principal 개체 바꾸기</span><span class="sxs-lookup"><span data-stu-id="d775a-119">Replacing a Principal Object</span></span>](../../../docs/standard/security/replacing-a-principal-object.md)  
 [<span data-ttu-id="d775a-120">Principal 개체 및 Identity 개체</span><span class="sxs-lookup"><span data-stu-id="d775a-120">Principal and Identity Objects</span></span>](../../../docs/standard/security/principal-and-identity-objects.md)
