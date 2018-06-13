---
title: ServiceAuthorizationBehavior
ms.date: 03/30/2017
ms.assetid: 77dad8e8-fea4-4d1c-b366-2f01a2a87f78
ms.openlocfilehash: e03f83927ec5aef7f916b2262c9c8cff1db68ac9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33486475"
---
# <a name="serviceauthorizationbehavior"></a><span data-ttu-id="bc01c-102">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="bc01c-102">ServiceAuthorizationBehavior</span></span>
<span data-ttu-id="bc01c-103">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="bc01c-103">ServiceAuthorizationBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc01c-104">구문</span><span class="sxs-lookup"><span data-stu-id="bc01c-104">Syntax</span></span>  
  
```  
class ServiceAuthorizationBehavior : Behavior  
{  
  boolean ImpersonateCallerForAllOperations;  
  string PrincipalPermissionMode;  
  string RoleProvider;  
  string ServiceAuthorizationManager;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="bc01c-105">메서드</span><span class="sxs-lookup"><span data-stu-id="bc01c-105">Methods</span></span>  
 <span data-ttu-id="bc01c-106">ServiceAuthorizationBehavior 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bc01c-106">The ServiceAuthorizationBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="bc01c-107">속성</span><span class="sxs-lookup"><span data-stu-id="bc01c-107">Properties</span></span>  
 <span data-ttu-id="bc01c-108">ServiceAuthorizationBehavior 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc01c-108">The ServiceAuthorizationBehavior class has the following properties:</span></span>  
  
### <a name="impersonatecallerforalloperations"></a><span data-ttu-id="bc01c-109">ImpersonateCallerForAllOperations</span><span class="sxs-lookup"><span data-stu-id="bc01c-109">ImpersonateCallerForAllOperations</span></span>  
 <span data-ttu-id="bc01c-110">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="bc01c-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="bc01c-111">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="bc01c-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bc01c-112">들어오는 메시지가 제공하는 자격 증명을 사용하여 서비스가 가장을 시도하는지 여부를 제어하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="bc01c-112">A value that controls whether the service attempts to impersonate using the credentials provided by the incoming message.</span></span>  
  
### <a name="principalpermissionmode"></a><span data-ttu-id="bc01c-113">PrincipalPermissionMode</span><span class="sxs-lookup"><span data-stu-id="bc01c-113">PrincipalPermissionMode</span></span>  
 <span data-ttu-id="bc01c-114">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="bc01c-114">Data type: string</span></span>  
  
 <span data-ttu-id="bc01c-115">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="bc01c-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bc01c-116">서버에서 작업을 수행할 때 사용되는 주체입니다.</span><span class="sxs-lookup"><span data-stu-id="bc01c-116">The principal used to carry out operations on the server.</span></span>  
  
### <a name="roleprovider"></a><span data-ttu-id="bc01c-117">RoleProvider</span><span class="sxs-lookup"><span data-stu-id="bc01c-117">RoleProvider</span></span>  
 <span data-ttu-id="bc01c-118">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="bc01c-118">Data type: string</span></span>  
  
 <span data-ttu-id="bc01c-119">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="bc01c-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bc01c-120">ASP.NET 역할 공급자의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="bc01c-120">The name of the ASP.NET role provider.</span></span>  
  
### <a name="serviceauthorizationmanager"></a><span data-ttu-id="bc01c-121">ServiceAuthorizationManager</span><span class="sxs-lookup"><span data-stu-id="bc01c-121">ServiceAuthorizationManager</span></span>  
 <span data-ttu-id="bc01c-122">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="bc01c-122">Data type: string</span></span>  
  
 <span data-ttu-id="bc01c-123">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="bc01c-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bc01c-124">사용자 지정 인증에 사용되는 권한 부여 관리자입니다.</span><span class="sxs-lookup"><span data-stu-id="bc01c-124">The authorization manager used for custom authorization.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc01c-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bc01c-125">Requirements</span></span>  
  
|<span data-ttu-id="bc01c-126">MOF</span><span class="sxs-lookup"><span data-stu-id="bc01c-126">MOF</span></span>|<span data-ttu-id="bc01c-127">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc01c-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="bc01c-128">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="bc01c-128">Namespace</span></span>|<span data-ttu-id="bc01c-129">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc01c-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bc01c-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bc01c-130">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
