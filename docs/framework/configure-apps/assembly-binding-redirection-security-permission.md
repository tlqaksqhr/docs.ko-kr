---
title: "어셈블리 바인딩 리디렉션 보안 권한"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: 24a5cdff-7ed9-4195-93f3-edf6899019fc
caps.latest.revision: "9"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 1bd25dd0444c428e000371abe494e62b258eaa63
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="assembly-binding-redirection-security-permission"></a><span data-ttu-id="d5c51-102">어셈블리 바인딩 리디렉션 보안 권한</span><span class="sxs-lookup"><span data-stu-id="d5c51-102">Assembly Binding Redirection Security Permission</span></span>
<span data-ttu-id="d5c51-103">응용 프로그램 구성 파일에서 어셈블리 바인딩을 명시적으로 리디렉션하려면 보안 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d5c51-103">Explicit assembly binding redirection in an application configuration file requires a security permission.</span></span> <span data-ttu-id="d5c51-104">이는 .NET Framework 어셈블리와 타사 어셈블리의 리디렉션 모두에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5c51-104">This applies to redirection of .NET Framework assemblies and assemblies from third parties.</span></span> <span data-ttu-id="d5c51-105">설정 하 여 권한 부여는 <xref:System.Security.Permissions.SecurityPermissionFlag> 에 플래그는 <xref:System.Security.Permissions.SecurityPermission>합니다.</span><span class="sxs-lookup"><span data-stu-id="d5c51-105">The permission is granted by setting the <xref:System.Security.Permissions.SecurityPermissionFlag> flag on the <xref:System.Security.Permissions.SecurityPermission>.</span></span> <span data-ttu-id="d5c51-106">관리 되는 어셈블리 기본적으로 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d5c51-106">Managed assemblies have no permissions by default.</span></span>  
  
 <span data-ttu-id="d5c51-107">신뢰할 수 있는 영역 (로컬 컴퓨터) 및 인트라넷 영역에서 실행 중인 응용 프로그램에는 보안 권한이 부여 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5c51-107">The security permission is granted to applications running in the Trusted Zone (local machine) and Intranet Zone.</span></span> <span data-ttu-id="d5c51-108">인터넷 영역에서 실행 중인 응용 프로그램에서 어셈블리 바인딩 리디렉션을 수행할 금지 엄격 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5c51-108">Applications running in the Internet Zone are strictly prohibited from performing assembly binding redirection.</span></span>  
  
 <span data-ttu-id="d5c51-109">관리자에 의해 제어 되는 컴퓨터 구성 파일 또는 구성 요소 게시자에 의해 제어 되는 게시자 정책 파일에 어셈블리 리디렉션을 수행 되는 경우에 권한이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d5c51-109">The permission is not required if assembly redirection is performed in a publisher policy file that is controlled by the component publisher, or in the machine configuration file that is controlled by the administrator.</span></span> <span data-ttu-id="d5c51-110">그러나 사용 권한을 명시적으로 사용 하 여 게시자 정책을 무시 하려면 응용 프로그램에 필요한는 [ \<예 = "no" / >](../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md) 응용 프로그램 구성 파일의 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d5c51-110">However, the permission is required for an application to explicitly ignore publisher policy using the [\<publisherPolicy apply="no"/>](../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md) element in the application configuration file.</span></span>  
  
 <span data-ttu-id="d5c51-111">다음 표에서 기본 보안 설정에 대 한는 **이러한** 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="d5c51-111">The following table shows the default security settings for the **BindingRedirects** flag.</span></span>  
  
|<span data-ttu-id="d5c51-112">영역</span><span class="sxs-lookup"><span data-stu-id="d5c51-112">Zone</span></span>|<span data-ttu-id="d5c51-113">이러한 플래그 설정</span><span class="sxs-lookup"><span data-stu-id="d5c51-113">BindingRedirects flag setting</span></span>|  
|----------|-----------------------------------|  
|<span data-ttu-id="d5c51-114">신뢰할 수 있는 영역 (로컬 컴퓨터)</span><span class="sxs-lookup"><span data-stu-id="d5c51-114">Trusted Zone (local machine)</span></span>|<span data-ttu-id="d5c51-115">**ON**</span><span class="sxs-lookup"><span data-stu-id="d5c51-115">**ON**</span></span>|  
|<span data-ttu-id="d5c51-116">인트라넷 영역</span><span class="sxs-lookup"><span data-stu-id="d5c51-116">Intranet Zone</span></span>|<span data-ttu-id="d5c51-117">**ON**</span><span class="sxs-lookup"><span data-stu-id="d5c51-117">**ON**</span></span>|  
|<span data-ttu-id="d5c51-118">인터넷 영역</span><span class="sxs-lookup"><span data-stu-id="d5c51-118">Internet Zone</span></span>|<span data-ttu-id="d5c51-119">**해제**</span><span class="sxs-lookup"><span data-stu-id="d5c51-119">**OFF**</span></span>|  
|<span data-ttu-id="d5c51-120">신뢰할 수 없는 영역</span><span class="sxs-lookup"><span data-stu-id="d5c51-120">Untrusted zones</span></span>|<span data-ttu-id="d5c51-121">**해제**</span><span class="sxs-lookup"><span data-stu-id="d5c51-121">**OFF**</span></span>|  
  
 <span data-ttu-id="d5c51-122">관리자 또는 제한 지정된 된 컴퓨터의 특정 시나리오를 지원 하도록 이러한 보안 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5c51-122">An administrator can change these security settings to support or restrict specific scenarios on a given computer.</span></span> <span data-ttu-id="d5c51-123">변경 하기 위한 도구도 **이러한** 플래그 설정을 기본;에서 관리자가 수동으로 편집 해야 Security.config 파일 사용자의 컴퓨터에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5c51-123">There are no tools for changing the **BindingRedirects** flag setting from the default; an administrator must manually edit the Security.config file on a user's computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5c51-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d5c51-124">See Also</span></span>  
 [<span data-ttu-id="d5c51-125">게시자 정책 파일 및-병렬 실행</span><span class="sxs-lookup"><span data-stu-id="d5c51-125">Publisher Policy Files and Side-by-Side Execution</span></span>](http://msdn.microsoft.com/en-us/97a042be-4d72-40c3-91c0-76fd36bdf133)  
 [<span data-ttu-id="d5c51-126">방법: 자동 바인딩 리디렉션 사용 설정 및 해제</span><span class="sxs-lookup"><span data-stu-id="d5c51-126">How to: Enable and Disable Automatic Binding Redirection</span></span>](../../../docs/framework/configure-apps/how-to-enable-and-disable-automatic-binding-redirection.md)  
 [<span data-ttu-id="d5c51-127">Side-by-Side 실행</span><span class="sxs-lookup"><span data-stu-id="d5c51-127">Side-by-Side Execution</span></span>](../../../docs/framework/deployment/side-by-side-execution.md)
