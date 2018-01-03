---
title: "위험한 권한 및 정책 관리"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- permissions [.NET Framework], policy administration
- security [.NET Framework], dangerous permissions
- code security, dangerous permissions
- secure coding, dangerous permissions
- permissions [.NET Framework], dangerous
ms.assetid: 1929e854-23a0-4bb1-94be-e8aa3b609e32
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 471570aec43398b05b8678bdcf74a3ef2494e289
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="dangerous-permissions-and-policy-administration"></a><span data-ttu-id="08b34-102">위험한 권한 및 정책 관리</span><span class="sxs-lookup"><span data-stu-id="08b34-102">Dangerous Permissions and Policy Administration</span></span>
<span data-ttu-id="08b34-103">.NET Framework가 권한을 제공하는 보호되는 몇몇 작업은 보안 시스템의 보안을 손상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b34-103">Several of the protected operations for which the .NET Framework provides permissions can potentially allow the security system to be circumvented.</span></span> <span data-ttu-id="08b34-104">이렇게 위험한 권한은 필요한 경우에만, 그리고 신뢰할 수 있는 코드에만 제공되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08b34-104">These dangerous permissions should be given only to trustworthy code, and then only as necessary.</span></span> <span data-ttu-id="08b34-105">일반적으로 이러한 권한이 부여되면 악성 코드를 방어할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="08b34-105">There is usually no defense against malicious code if it is granted these permissions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="08b34-106">[!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]에서는 .NET Framework 보안 모델 및 용어 대한 중요한 변경 내용이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b34-106">In the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], there have been important changes to the .NET Framework security model and terminology.</span></span> <span data-ttu-id="08b34-107">이러한 변경에 대 한 자세한 내용은 참조 [보안 변경 내용](../../../docs/framework/security/security-changes.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="08b34-107">For more information about these changes, see [Security Changes](../../../docs/framework/security/security-changes.md).</span></span>  
  
 <span data-ttu-id="08b34-108">위험한 권한은 다음 표에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b34-108">The dangerous permissions are explained in the following table.</span></span>  
  
|<span data-ttu-id="08b34-109">사용 권한</span><span class="sxs-lookup"><span data-stu-id="08b34-109">Permission</span></span>|<span data-ttu-id="08b34-110">잠재적 위험</span><span class="sxs-lookup"><span data-stu-id="08b34-110">Potential risk</span></span>|  
|----------------|--------------------|  
|<xref:System.Security.Permissions.SecurityPermission>||  
|<xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode>|<span data-ttu-id="08b34-111">관리 코드에서 비관리 코드를 호출하도록 허용하므로 위험할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b34-111">Allows managed code to call into unmanaged code, which is often dangerous.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.SkipVerification>|<span data-ttu-id="08b34-112">이 코드는 유효성 검사가 없어도 모든 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b34-112">Without verification, the code can do anything.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlEvidence>|<span data-ttu-id="08b34-113">잘못된 증명 정보로 보안 정책을 속일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b34-113">Invalidated evidence can fool security policy.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlPolicy>|<span data-ttu-id="08b34-114">보안 정책을 수정하는 기능으로 보안을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b34-114">The ability to modify security policy can disable security.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.SerializationFormatter>|<span data-ttu-id="08b34-115">직렬화를 사용하면 접근성 메커니즘을 피할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b34-115">The use of serialization can circumvent accessibility mechanisms.</span></span> <span data-ttu-id="08b34-116">자세한 내용은 [보안 및 직렬화](../../../docs/framework/misc/security-and-serialization.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="08b34-116">For details, see [Security and Serialization](../../../docs/framework/misc/security-and-serialization.md).</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlPrincipal>|<span data-ttu-id="08b34-117">현재 보안 주체를 설정하는 기능은 역할 기반 보안을 속일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b34-117">The ability to set the current principal can trick role-based security.</span></span>|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlThread>|<span data-ttu-id="08b34-118">스레드 조작은 스레드와 관련된 보안 상태로 인해 위험합니다.</span><span class="sxs-lookup"><span data-stu-id="08b34-118">Manipulation of threads is dangerous because of the security state associated with threads.</span></span>|  
|<xref:System.Security.Permissions.ReflectionPermission>||  
|<xref:System.MemberAccessException>|<span data-ttu-id="08b34-119">접근성 메커니즘을 무력화하는 데 전용 멤버를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08b34-119">Can use private members to defeat accessibility mechanisms.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="08b34-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="08b34-120">See Also</span></span>  
 [<span data-ttu-id="08b34-121">보안 코딩 지침</span><span class="sxs-lookup"><span data-stu-id="08b34-121">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)
