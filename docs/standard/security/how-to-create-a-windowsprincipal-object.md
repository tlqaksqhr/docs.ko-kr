---
title: "방법: WindowsPrincipal 개체 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WindowsPrincipal objects, creating
- security [.NET Framework], creating a WindowsPrincipal object
- security [.NET Framework], principals
- principal objects, creating
ms.assetid: 56eb10ca-e61d-4ed2-af7a-555fc4c25a25
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: c4eb890696162af61f1355bfca50ce5dd2a615ad
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-create-a-windowsprincipal-object"></a><span data-ttu-id="4a61a-102">방법: WindowsPrincipal 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="4a61a-102">How to: Create a WindowsPrincipal Object</span></span>
<span data-ttu-id="4a61a-103">코드에서 역할 기반 유효성 검사를 반복적으로 수행해야 하는지 또는 한 번만 수행해야 하는지에 따라 <xref:System.Security.Principal.WindowsPrincipal> 개체를 만드는 두 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a61a-103">There are two ways to create a <xref:System.Security.Principal.WindowsPrincipal> object, depending on whether code must repeatedly perform role-based validation or must perform it only once.</span></span>  
  
 <span data-ttu-id="4a61a-104">코드에서 역할 기반 유효성 검사를 반복적으로 수행해야 하는 경우 다음 절차 중 첫 번째 절차가 더 적은 오버헤드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="4a61a-104">If code must repeatedly perform role-based validation, the first of the following procedures produces less overhead.</span></span> <span data-ttu-id="4a61a-105">코드에서 역할 기반 유효성 검사를 한 번만 수행해야 하는 경우 다음 절차 중 두 번째 절차를 사용하여 <xref:System.Security.Principal.WindowsPrincipal> 개체를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a61a-105">When code needs to make role-based validations only once, you can create a <xref:System.Security.Principal.WindowsPrincipal> object by using the second of the following procedures.</span></span>  
  
### <a name="to-create-a-windowsprincipal-object-for-repeated-validation"></a><span data-ttu-id="4a61a-106">반복된 유효성 검사를 위한 WindowsPrincipal 개체를 만들려면</span><span class="sxs-lookup"><span data-stu-id="4a61a-106">To create a WindowsPrincipal object for repeated validation</span></span>  
  
1.  <span data-ttu-id="4a61a-107">새 정책에 대한 요구 사항을 나타내는 <xref:System.Security.Principal.PrincipalPolicy> 열거형 값을 메서드에 전달하여 정적 <xref:System.AppDomain.CurrentDomain%2A?displayProperty=nameWithType> 속성에 의해서 반환된 <xref:System.AppDomain> 개체에서 <xref:System.AppDomain.SetPrincipalPolicy%2A> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="4a61a-107">Call the <xref:System.AppDomain.SetPrincipalPolicy%2A> method on the <xref:System.AppDomain> object that is returned by the static <xref:System.AppDomain.CurrentDomain%2A?displayProperty=nameWithType> property, passing the method a <xref:System.Security.Principal.PrincipalPolicy> enumeration value that indicates what the new policy should be.</span></span> <span data-ttu-id="4a61a-108">지원되는 값은 <xref:System.Security.Principal.PrincipalPolicy.NoPrincipal>, <xref:System.Security.Principal.PrincipalPolicy.UnauthenticatedPrincipal> 및 <xref:System.Security.Principal.PrincipalPolicy.WindowsPrincipal>입니다.</span><span class="sxs-lookup"><span data-stu-id="4a61a-108">Supported values are <xref:System.Security.Principal.PrincipalPolicy.NoPrincipal>, <xref:System.Security.Principal.PrincipalPolicy.UnauthenticatedPrincipal>, and <xref:System.Security.Principal.PrincipalPolicy.WindowsPrincipal>.</span></span> <span data-ttu-id="4a61a-109">다음 코드에서는 이 메서드 호출을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4a61a-109">The following code demonstrates this method call.</span></span>  
  
    ```csharp  
    AppDomain.CurrentDomain.SetPrincipalPolicy(  
        PrincipalPolicy.WindowsPrincipal);  
    ```  
  
    ```vb  
    AppDomain.CurrentDomain.SetPrincipalPolicy( _  
        PrincipalPolicy.WindowsPrincipal)  
    ```  
  
2.  <span data-ttu-id="4a61a-110">정책을 설정한 후 정적 <xref:System.Threading.Thread.CurrentPrincipal%2A?displayProperty=nameWithType> 속성을 사용하여 현재 Windows 사용자를 캡슐화하는 보안 주체를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="4a61a-110">With the policy set, use the static <xref:System.Threading.Thread.CurrentPrincipal%2A?displayProperty=nameWithType> property to retrieve the principal that encapsulates the current Windows user.</span></span> <span data-ttu-id="4a61a-111">속성 반환 형식이 <xref:System.Security.Principal.IPrincipal>이므로 결과를 <xref:System.Security.Principal.WindowsPrincipal> 형식으로 캐스팅해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a61a-111">Because the property return type is <xref:System.Security.Principal.IPrincipal>, you must cast the result to a <xref:System.Security.Principal.WindowsPrincipal> type.</span></span> <span data-ttu-id="4a61a-112">다음 코드에서는 새 <xref:System.Security.Principal.WindowsPrincipal> 개체를 현재 스레드와 연결된 보안 주체의 값으로 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="4a61a-112">The following code initializes a new <xref:System.Security.Principal.WindowsPrincipal> object to the value of the principal associated with the current thread.</span></span>  
  
    ```csharp  
    WindowsPrincipal MyPrincipal =   
        (WindowsPrincipal) Thread.CurrentPrincipal;  
    ```  
  
    ```vb  
    Dim MyPrincipal As WindowsPrincipal = _  
        CType(Thread.CurrentPrincipal, WindowsPrincipal)   
    ```  
  
3.  <span data-ttu-id="4a61a-113">보안 주체 개체가 생성되면 여러 메서드 중 하나를 사용하여 유효성을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a61a-113">When the principal object has been created, you can use one of several methods to validate it.</span></span>  
  
### <a name="to-create-a-windowsprincipal-object-for-a-single-validation"></a><span data-ttu-id="4a61a-114">단일 유효성 검사를 위한 WindowsPrincipal 개체를 만들려면</span><span class="sxs-lookup"><span data-stu-id="4a61a-114">To create a WindowsPrincipal object for a single validation</span></span>  
  
1.  <span data-ttu-id="4a61a-115">현재 Windows 계정을 쿼리하고 해당 계정에 대한 정보를 새로 만든 ID 개체에 배치하는 정적 <xref:System.Security.Principal.WindowsIdentity.GetCurrent%2A?displayProperty=nameWithType> 메서드를 호출하여 새 <xref:System.Security.Principal.WindowsIdentity> 개체를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="4a61a-115">Initialize a new <xref:System.Security.Principal.WindowsIdentity> object by calling the static <xref:System.Security.Principal.WindowsIdentity.GetCurrent%2A?displayProperty=nameWithType> method, which queries the current Windows account and places information about that account into the newly created identity object.</span></span> <span data-ttu-id="4a61a-116">다음 코드에서는 새 <xref:System.Security.Principal.WindowsIdentity> 개체를 만들고 현재 인증된 사용자로 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="4a61a-116">The following code creates a new <xref:System.Security.Principal.WindowsIdentity> object and initializes it to the current authenticated user.</span></span>  
  
    ```csharp  
    WindowsIdentity MyIdentity = WindowsIdentity.GetCurrent();  
    ```  
  
    ```vb  
    Dim MyIdentity As WindowsIdentity = WindowsIdentity.GetCurrent()  
    ```  
  
2.  <span data-ttu-id="4a61a-117">새 <xref:System.Security.Principal.WindowsPrincipal> 개체를 만들고 이전 단계에서 만든 <xref:System.Security.Principal.WindowsIdentity> 개체의 값을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="4a61a-117">Create a new <xref:System.Security.Principal.WindowsPrincipal> object and pass it the value of the <xref:System.Security.Principal.WindowsIdentity> object created in the preceding step.</span></span>  
  
    ```csharp  
    WindowsPrincipal MyPrincipal = new WindowsPrincipal(MyIdentity);  
    ```  
  
    ```vb  
    Dim MyPrincipal As New WindowsPrincipal(MyIdentity)  
    ```  
  
3.  <span data-ttu-id="4a61a-118">보안 주체 개체가 생성되면 여러 메서드 중 하나를 사용하여 유효성을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a61a-118">When the principal object has been created, you can use one of several methods to validate it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a61a-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4a61a-119">See Also</span></span>  
 [<span data-ttu-id="4a61a-120">Principal 개체 및 Identity 개체</span><span class="sxs-lookup"><span data-stu-id="4a61a-120">Principal and Identity Objects</span></span>](../../../docs/standard/security/principal-and-identity-objects.md)
