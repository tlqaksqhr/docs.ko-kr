---
title: 보안 및 레지스트리(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- security [Visual Basic], registry
- registry [Visual Basic], security issues
ms.assetid: 9980aff7-2f69-492b-8f66-29a9a76d3df5
ms.openlocfilehash: ddfe8f88763ee2db78d25d72e6c9cb3456ccd13f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="security-and-the-registry-visual-basic"></a><span data-ttu-id="bcd77-102">보안 및 레지스트리(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bcd77-102">Security and the Registry (Visual Basic)</span></span>
<span data-ttu-id="bcd77-103">이 페이지에서는 레지스트리에 데이터를 저장할 경우 보안에 미치는 영향을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bcd77-103">This page discusses the security implications of storing data in the registry.</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="bcd77-104">사용 권한</span><span class="sxs-lookup"><span data-stu-id="bcd77-104">Permissions</span></span>  
 <span data-ttu-id="bcd77-105">레지스트리 키가 ACL(액세스 제어 목록)로 보호된 경우에도 비밀(예: 암호)을 레지스트리에 일반 텍스트로 저장하는 것은 안전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bcd77-105">It is not secure to store secrets, such as passwords, in the registry as plain text, even if the registry key is protected by ACLs (access control lists).</span></span>  
  
 <span data-ttu-id="bcd77-106">레지스트리로 작업하면 시스템 리소스나 보호된 정보에 부적절하게 액세스하여 보안이 손상될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bcd77-106">Working with the registry may compromise security by allowing inappropriate access to system resources or protected information.</span></span> <span data-ttu-id="bcd77-107">이러한 속성을 사용하려면 레지스트리 변수에 대한 액세스를 제어하는 <xref:System.Security.Permissions.RegistryPermissionAccess> 열거형의 읽기 및 쓰기 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcd77-107">To use these properties, you must have read and write permissions from the <xref:System.Security.Permissions.RegistryPermissionAccess> enumeration, which controls access to registry variables.</span></span> <span data-ttu-id="bcd77-108">완전 신뢰로 실행되는 코드(기본 보안 정책에서 사용자의 로컬 하드 디스크에 설치된 모든 코드)에는 레지스트리에 액세스하는 데 필요한 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bcd77-108">Any code running with full trust (under the default security policy, this is any code installed on the user's local hard disk) has the necessary permissions to access the registry.</span></span> <span data-ttu-id="bcd77-109">자세한 내용은 <xref:System.Security.Permissions.RegistryPermission> 클래스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bcd77-109">For more information, see <xref:System.Security.Permissions.RegistryPermission> class.</span></span>  
  
 <span data-ttu-id="bcd77-110"><xref:System.Security.Permissions.RegistryPermission> 없이 코드에서 액세스할 수 있는 메모리 위치에 레지스트리 변수를 저장하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bcd77-110">Registry variables should not be stored in memory locations where code without <xref:System.Security.Permissions.RegistryPermission> can access them.</span></span> <span data-ttu-id="bcd77-111">마찬가지로, 사용 권한을 부여하는 경우 작업을 완료하는 데 필요한 최소 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="bcd77-111">Similarly, when granting permissions, grant the minimum privileges necessary to get the job done.</span></span>  
  
 <span data-ttu-id="bcd77-112">레지스트리 권한 액세스 값은 <xref:System.Security.Permissions.RegistryPermissionAccess> 열거형에 의해 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="bcd77-112">Registry permission access values are defined by the <xref:System.Security.Permissions.RegistryPermissionAccess> enumeration.</span></span> <span data-ttu-id="bcd77-113">다음 표에서는 해당 멤버를 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bcd77-113">The following table details its members.</span></span>  
  
|<span data-ttu-id="bcd77-114">값</span><span class="sxs-lookup"><span data-stu-id="bcd77-114">Value</span></span>|<span data-ttu-id="bcd77-115">레지스트리 변수에 대한 액세스 권한</span><span class="sxs-lookup"><span data-stu-id="bcd77-115">Access to Registry Variables</span></span>|  
|-----------|----------------------------------|  
|`AllAccess`|<span data-ttu-id="bcd77-116">만들기, 읽기, 쓰기</span><span class="sxs-lookup"><span data-stu-id="bcd77-116">Create, read, and write</span></span>|  
|`Create`|<span data-ttu-id="bcd77-117">만들기</span><span class="sxs-lookup"><span data-stu-id="bcd77-117">Create</span></span>|  
|`NoAccess`|<span data-ttu-id="bcd77-118">액세스 권한 없음</span><span class="sxs-lookup"><span data-stu-id="bcd77-118">No access</span></span>|  
|`Read`|<span data-ttu-id="bcd77-119">읽기</span><span class="sxs-lookup"><span data-stu-id="bcd77-119">Read</span></span>|  
|`Write`|<span data-ttu-id="bcd77-120">Write</span><span class="sxs-lookup"><span data-stu-id="bcd77-120">Write</span></span>|  
  
## <a name="checking-values-in-registry-keys"></a><span data-ttu-id="bcd77-121">레지스트리 키의 값 검사</span><span class="sxs-lookup"><span data-stu-id="bcd77-121">Checking Values in Registry Keys</span></span>  
 <span data-ttu-id="bcd77-122">레지스트리 값을 만들 때 해당 값이 이미 있는 경우 수행할 작업을 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcd77-122">When you create a registry value, you need to decide what to do if that value already exists.</span></span> <span data-ttu-id="bcd77-123">다른 악성 프로세스에서 값을 이미 만들고 액세스했을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bcd77-123">Another process, perhaps a malicious one, may have already created the value and have access to it.</span></span> <span data-ttu-id="bcd77-124">레지스트리 값에 데이터를 넣으면 다른 프로세스에서 해당 데이터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bcd77-124">When you put data in the registry value, the data is available to the other process.</span></span> <span data-ttu-id="bcd77-125">이를 방지하려면 `GetValue` 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bcd77-125">To prevent this, use the `GetValue` method.</span></span> <span data-ttu-id="bcd77-126">키가 아직 없는 경우 `Nothing`이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="bcd77-126">It returns `Nothing` if the key does not already exist.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="bcd77-127">웹 응용 프로그램에서 레지스트리를 읽는 경우 현재 사용자의 ID는 웹 응용 프로그램에 구현된 인증 및 가장에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="bcd77-127">When reading the registry from a Web application, the identity of current user depends on the authentication and impersonation implemented in the Web application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcd77-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bcd77-128">See Also</span></span>  
 <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>  
 [<span data-ttu-id="bcd77-129">레지스트리 읽기 및 쓰기</span><span class="sxs-lookup"><span data-stu-id="bcd77-129">Reading from and Writing to the Registry</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md)
