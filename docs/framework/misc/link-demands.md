---
title: 링크 요청
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [.NET Framework], demands
- demanded permissions
- permissions [.NET Framework], demands
- granting permissions, demands
- code access security, demands
- user demands for permission
- caller security checks
- link demands
ms.assetid: a33fd5f9-2de9-4653-a4f0-d9df25082c4d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 29a3254bb5ccfe422a1c2d7d156975c0887d9273
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33390665"
---
# <a name="link-demands"></a><span data-ttu-id="91b9d-102">링크 요청</span><span class="sxs-lookup"><span data-stu-id="91b9d-102">Link Demands</span></span>
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 <span data-ttu-id="91b9d-103">링크 요청으로 인해 Just-In-Time 컴파일 동안 보안 검사를 수행하며 코드의 직접 호출 어셈블리만 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="91b9d-103">A link demand causes a security check during just-in-time compilation and checks only the immediate calling assembly of your code.</span></span> <span data-ttu-id="91b9d-104">연결은 함수 포인터 참조 및 메서드 호출을 포함하여 코드가 형식 참조에 바인딩된 경우에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="91b9d-104">Linking occurs when your code is bound to a type reference, including function pointer references and method calls.</span></span> <span data-ttu-id="91b9d-105">호출 어셈블리에 코드에 연결할 권한이 없는 경우 링크가 허용되지 않으며 코드가 로드 및 실행될 때 런타임 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="91b9d-105">If the calling assembly does not have sufficient permission to link to your code, the link is not allowed and a runtime exception is thrown when the code is loaded and run.</span></span> <span data-ttu-id="91b9d-106">코드에서 상속하는 클래스에서 링크 요청을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91b9d-106">Link demands can be overridden in classes that inherit from your code.</span></span>  
  
 <span data-ttu-id="91b9d-107">이 형식의 요청에서는 전체 스택 워크가 수행되지 않으며 코드가 여전히 보안 공격에 취약합니다.</span><span class="sxs-lookup"><span data-stu-id="91b9d-107">Note that a full stack walk is not performed with this type of demand and that your code is still susceptible to luring attacks.</span></span> <span data-ttu-id="91b9d-108">예를 들어 어셈블리 A에에서 메서드가 링크 요청으로 보호 되 면 어셈블리 B에에서 있는 직접 호출자는 기반으로 계산 Assembly B의 사용 권한  그러나 링크 요청이 평가 하지 않습니다 어셈블리 C에에서는 메서드를 간접적으로 호출 메서드는 메서드를 사용 하는 2. 어셈블리에 어셈블리의 경우 링크 요청은 지정 권한만 직접 코드에 연결 하는 직접 호출 어셈블리의 호출자가 가져야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91b9d-108">For example, if a method in assembly A is protected by a link demand, a direct caller in assembly B is evaluated based on the permissions of Assembly B.  However, the link demand will not evaluate a method in assembly C if it indirectly calls the method in assembly A using the method in assembly B. The link demand specifies only the permissions direct callers in the immediate calling assembly must have to link to your code.</span></span> <span data-ttu-id="91b9d-109">모든 호출자가 코드를 실행하는 데 필요한 권한은 지정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="91b9d-109">It does not specify the permissions all callers must have to run your code.</span></span>  
  
 <span data-ttu-id="91b9d-110"><xref:System.Security.CodeAccessPermission.Assert%2A>, <xref:System.Security.CodeAccessPermission.Deny%2A> 및 <xref:System.Security.CodeAccessPermission.PermitOnly%2A> 스택 워크 한정자는 링크 요청의 평가에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="91b9d-110">The <xref:System.Security.CodeAccessPermission.Assert%2A>, <xref:System.Security.CodeAccessPermission.Deny%2A>, and <xref:System.Security.CodeAccessPermission.PermitOnly%2A> stack walk modifiers do not affect the evaluation of link demands.</span></span>  <span data-ttu-id="91b9d-111">링크 요청은 스택 워크를 수행하지 않으므로 스택 워크 한정자가 링크 요청에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="91b9d-111">Because link demands do not perform a stack walk, the stack walk modifiers have no effect on link demands.</span></span>  
  
 <span data-ttu-id="91b9d-112">링크 요청으로 보호 되는 메서드를 통해 액세스 하는 경우는 [리플렉션](../../../docs/framework/reflection-and-codedom/reflection.md), 리플렉션을 통해 액세스 하는 코드의 직접 실행 호출자를 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="91b9d-112">If a method protected by a link demand is accessed through [Reflection](../../../docs/framework/reflection-and-codedom/reflection.md), then a link demand checks the immediate caller of the code accessed through reflection.</span></span> <span data-ttu-id="91b9d-113">이는 리플렉션을 사용하여 수행된 메서드 호출 및 메서드 검색 둘 다에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="91b9d-113">This is true both for method discovery and for method invocation performed using reflection.</span></span> <span data-ttu-id="91b9d-114">예를 들어, 코드를 반환 하기 위해는 <xref:System.Reflection.MethodInfo> 링크 요청으로 보호 되 고 전달 하는 메서드를 나타내는 개체 **MethodInfo** 개체는 개체를 사용 하 여 원래 메서드를 호출 하는 다른 일부 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="91b9d-114">For example, suppose code uses reflection to return a <xref:System.Reflection.MethodInfo> object representing a method protected by a link demand and then passes that **MethodInfo** object to some other code that uses the object to invoke the original method.</span></span> <span data-ttu-id="91b9d-115">이 경우 링크 요청 검사가 수행 두 번: 반환 하는 코드에 대해 한 번씩은 **MethodInfo** 개체와 호출 하는 코드에 대해 한 번씩 합니다.</span><span class="sxs-lookup"><span data-stu-id="91b9d-115">In this case the link demand check occurs twice: once for the code that returns the **MethodInfo** object and once for the code that invokes it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="91b9d-116">정적 생성자는 응용 프로그램 코드 실행 경로 외부의 시스템에서 호출되므로 정적 클래스 생성자에서 수행되는 링크 요청은 생성자를 보호하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="91b9d-116">A link demand performed on a static class constructor does not protect the constructor because static constructors are called by the system, outside the application's code execution path.</span></span> <span data-ttu-id="91b9d-117">따라서 링크 요청이 전체 클래스에 적용되는 경우 클래스의 나머지 부분은 보호하지만 정적 생성자에 대한 액세스를 보호할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="91b9d-117">As a result, when a link demand is applied to an entire class, it cannot protect access to a static constructor, although it does protect the rest of the class.</span></span>  
  
 <span data-ttu-id="91b9d-118">다음 코드 조각에서는 `ReadData` 메서드에 연결하는 코드에 `CustomPermission` 권한이 있어야 함을 선언적으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="91b9d-118">The following code fragment declaratively specifies that any code linking to the `ReadData` method must have the `CustomPermission` permission.</span></span> <span data-ttu-id="91b9d-119">이 권한은 가상의 사용자 지정 권한이며 .NET Framework에 존재하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="91b9d-119">This permission is a hypothetical custom permission and does not exist in the .NET Framework.</span></span> <span data-ttu-id="91b9d-120">전달 하 여 요청 됩니다는 **SecurityAction.LinkDemand** 하는 플래그는 `CustomPermissionAttribute`합니다.</span><span class="sxs-lookup"><span data-stu-id="91b9d-120">The demand is made by passing a **SecurityAction.LinkDemand** flag to the `CustomPermissionAttribute`.</span></span>  
  
```vb  
<CustomPermissionAttribute(SecurityAction.LinkDemand)> _  
Public Shared Function ReadData() As String  
    ' Access a custom resource.  
End Function    
```  
  
```csharp  
[CustomPermissionAttribute(SecurityAction.LinkDemand)]  
public static string ReadData()  
{  
    // Access a custom resource.  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="91b9d-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="91b9d-121">See Also</span></span>  
 [<span data-ttu-id="91b9d-122">특성</span><span class="sxs-lookup"><span data-stu-id="91b9d-122">Attributes</span></span>](../../../docs/standard/attributes/index.md)  
 [<span data-ttu-id="91b9d-123">코드 액세스 보안</span><span class="sxs-lookup"><span data-stu-id="91b9d-123">Code Access Security</span></span>](../../../docs/framework/misc/code-access-security.md)
