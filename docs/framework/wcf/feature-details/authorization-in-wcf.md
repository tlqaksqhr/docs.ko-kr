---
title: WCF에서 권한 부여
ms.date: 03/30/2017
helpviewer_keywords:
- authorization [WCF]
- security [WCF], authorization
ms.assetid: 8ea0b552-af65-45b0-a157-c6c111b8ce5e
ms.openlocfilehash: c6bf779c7baeea1f9a253ad0bde966cea67b57aa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33488574"
---
# <a name="authorization-in-wcf"></a><span data-ttu-id="44f7e-102">WCF에서 권한 부여</span><span class="sxs-lookup"><span data-stu-id="44f7e-102">Authorization in WCF</span></span>
<span data-ttu-id="44f7e-103">권한 부여는 서비스나 파일과 같은 리소스에 대한 액세스 및 권한을 제어하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="44f7e-103">Authorization is the process of controlling access and rights to resources, such as services or files.</span></span> <span data-ttu-id="44f7e-104">이 섹션의 항목에서는 WCF Windows Communication Foundation ()는 여러 가지 방법으로 기본 작업을 수행 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="44f7e-104">The topics in this section show you how to perform this basic task in Windows Communication Foundation (WCF) in a variety of ways.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="44f7e-105">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="44f7e-105">In This Section</span></span>  
 [<span data-ttu-id="44f7e-106">Access Control 메커니즘</span><span class="sxs-lookup"><span data-stu-id="44f7e-106">Access Control Mechanisms</span></span>](../../../../docs/framework/wcf/feature-details/access-control-mechanisms.md)  
 <span data-ttu-id="44f7e-107">WCF 및 적절된 한 사용 권한 부여 메커니즘의 간략 한 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="44f7e-107">Provides a brief outline of the authorization mechanisms in WCF, and suggested uses.</span></span>  
  
 [<span data-ttu-id="44f7e-108">방법: PrincipalPermissionAttribute 클래스를 사용하여 액세스 제한</span><span class="sxs-lookup"><span data-stu-id="44f7e-108">How to: Restrict Access with the PrincipalPermissionAttribute Class</span></span>](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)  
 <span data-ttu-id="44f7e-109"><xref:System.Security.Permissions.PrincipalPermissionAttribute>를 사용하여 서비스에 대한 액세스를 제한하는 프로세스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="44f7e-109">Shows the process of restricting access to a service with the <xref:System.Security.Permissions.PrincipalPermissionAttribute>.</span></span>  
  
 [<span data-ttu-id="44f7e-110">방법: 서비스에서 ASP.NET 역할 공급자 사용</span><span class="sxs-lookup"><span data-stu-id="44f7e-110">How to: Use the ASP.NET Role Provider with a Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)  
 <span data-ttu-id="44f7e-111">[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]의 역할 공급자 기능을 사용할 수 있도록 설정하는 서비스 구성에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="44f7e-111">Walks through the configuration of a service to enable it to use the role provider feature of [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].</span></span>  
  
 [<span data-ttu-id="44f7e-112">방법: 서비스에서 ASP.NET 권한 부여 관리자 역할 공급자 사용</span><span class="sxs-lookup"><span data-stu-id="44f7e-112">How to: Use the ASP.NET Authorization Manager Role Provider with a Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service.md)  
 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]<span data-ttu-id="44f7e-113">은 권한 부여 관리자를 사용하여 웹 사이트의 권한을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44f7e-113"> can use the Authorization Manager to manage authorization for a Web site.</span></span> <span data-ttu-id="44f7e-114">WCF 마찬가지로 활용할 수 있습니다는 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]/Authorization 관리자 클라이언트의 권한 부여를 결합 합니다.</span><span class="sxs-lookup"><span data-stu-id="44f7e-114">WCF can similarly leverage the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]/Authorization Manager combination for authorization of clients.</span></span>  
  
 [<span data-ttu-id="44f7e-115">ID 모델을 사용하여 클레임 및 권한 부여 관리</span><span class="sxs-lookup"><span data-stu-id="44f7e-115">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)  
 <span data-ttu-id="44f7e-116">클레임 기반 권한 부여에 ID 모델 인프라를 사용하는 기본적인 사용법에 대해 설명합니다 .</span><span class="sxs-lookup"><span data-stu-id="44f7e-116">Explains the basics of using the Identity Model infrastructure for claims-based authorization.</span></span>  
  
 [<span data-ttu-id="44f7e-117">위임 및 가장</span><span class="sxs-lookup"><span data-stu-id="44f7e-117">Delegation and Impersonation</span></span>](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)  
 <span data-ttu-id="44f7e-118">위임과 가장의 차이점을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="44f7e-118">Explains the difference between delegation and impersonation.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="44f7e-119">참조</span><span class="sxs-lookup"><span data-stu-id="44f7e-119">Reference</span></span>  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.ServiceModel.Description.PrincipalPermissionMode>  
  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>  
  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
  
## <a name="related-sections"></a><span data-ttu-id="44f7e-120">관련 단원</span><span class="sxs-lookup"><span data-stu-id="44f7e-120">Related Sections</span></span>  
 [<span data-ttu-id="44f7e-121">인증</span><span class="sxs-lookup"><span data-stu-id="44f7e-121">Authentication</span></span>](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
  
## <a name="see-also"></a><span data-ttu-id="44f7e-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="44f7e-122">See Also</span></span>  
 [<span data-ttu-id="44f7e-123">보안 개요</span><span class="sxs-lookup"><span data-stu-id="44f7e-123">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="44f7e-124">Windows Server App Fabric에 대 한 보안 모델</span><span class="sxs-lookup"><span data-stu-id="44f7e-124">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
