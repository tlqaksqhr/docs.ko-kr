---
title: "WCF에서 권한 부여"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- authorization [WCF]
- security [WCF], authorization
ms.assetid: 8ea0b552-af65-45b0-a157-c6c111b8ce5e
caps.latest.revision: "15"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a0c2afafa1d645ec0e95b7b41ff8389873969c89
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="authorization-in-wcf"></a><span data-ttu-id="4ba87-102">WCF에서 권한 부여</span><span class="sxs-lookup"><span data-stu-id="4ba87-102">Authorization in WCF</span></span>
<span data-ttu-id="4ba87-103">권한 부여는 서비스나 파일과 같은 리소스에 대한 액세스 및 권한을 제어하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="4ba87-103">Authorization is the process of controlling access and rights to resources, such as services or files.</span></span> <span data-ttu-id="4ba87-104">이 단원의 항목에서는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]에서 여러 가지 방법으로 기본 작업을 수행하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4ba87-104">The topics in this section show you how to perform this basic task in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] in a variety of ways.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4ba87-105">단원 내용</span><span class="sxs-lookup"><span data-stu-id="4ba87-105">In This Section</span></span>  
 [<span data-ttu-id="4ba87-106">액세스 제어 메커니즘</span><span class="sxs-lookup"><span data-stu-id="4ba87-106">Access Control Mechanisms</span></span>](../../../../docs/framework/wcf/feature-details/access-control-mechanisms.md)  
 <span data-ttu-id="4ba87-107">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]의 권한 부여 메커니즘 및 제안된 사용에 대해 간략히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4ba87-107">Provides a brief outline of the authorization mechanisms in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], and suggested uses.</span></span>  
  
 [<span data-ttu-id="4ba87-108">방법: PrincipalPermissionAttribute 클래스를 사용하여 액세스 제한</span><span class="sxs-lookup"><span data-stu-id="4ba87-108">How to: Restrict Access with the PrincipalPermissionAttribute Class</span></span>](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)  
 <span data-ttu-id="4ba87-109"><xref:System.Security.Permissions.PrincipalPermissionAttribute>를 사용하여 서비스에 대한 액세스를 제한하는 프로세스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4ba87-109">Shows the process of restricting access to a service with the <xref:System.Security.Permissions.PrincipalPermissionAttribute>.</span></span>  
  
 [<span data-ttu-id="4ba87-110">방법: 서비스에서 ASP.NET 역할 공급자 사용</span><span class="sxs-lookup"><span data-stu-id="4ba87-110">How to: Use the ASP.NET Role Provider with a Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)  
 <span data-ttu-id="4ba87-111">[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]의 역할 공급자 기능을 사용할 수 있도록 설정하는 서비스 구성에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4ba87-111">Walks through the configuration of a service to enable it to use the role provider feature of [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].</span></span>  
  
 [<span data-ttu-id="4ba87-112">방법: 서비스에서 ASP.NET 권한 부여 관리자 역할 공급자 사용</span><span class="sxs-lookup"><span data-stu-id="4ba87-112">How to: Use the ASP.NET Authorization Manager Role Provider with a Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service.md)  
 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]<span data-ttu-id="4ba87-113">은 권한 부여 관리자를 사용하여 웹 사이트의 권한을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ba87-113"> can use the Authorization Manager to manage authorization for a Web site.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="4ba87-114">도 이와 유사하게 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]/권한 부여 관리자를 결합 사용하여 클라이언트 권한을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ba87-114"> can similarly leverage the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]/Authorization Manager combination for authorization of clients.</span></span>  
  
 [<span data-ttu-id="4ba87-115">클레임 및 권한 부여 Id 모델 관리</span><span class="sxs-lookup"><span data-stu-id="4ba87-115">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)  
 <span data-ttu-id="4ba87-116">클레임 기반 권한 부여에 ID 모델 인프라를 사용하는 기본적인 사용법에 대해 설명합니다 .</span><span class="sxs-lookup"><span data-stu-id="4ba87-116">Explains the basics of using the Identity Model infrastructure for claims-based authorization.</span></span>  
  
 [<span data-ttu-id="4ba87-117">위임 및 가장</span><span class="sxs-lookup"><span data-stu-id="4ba87-117">Delegation and Impersonation</span></span>](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)  
 <span data-ttu-id="4ba87-118">위임과 가장의 차이점을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4ba87-118">Explains the difference between delegation and impersonation.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="4ba87-119">참조</span><span class="sxs-lookup"><span data-stu-id="4ba87-119">Reference</span></span>  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.ServiceModel.Description.PrincipalPermissionMode>  
  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>  
  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
  
## <a name="related-sections"></a><span data-ttu-id="4ba87-120">관련 단원</span><span class="sxs-lookup"><span data-stu-id="4ba87-120">Related Sections</span></span>  
 [<span data-ttu-id="4ba87-121">인증</span><span class="sxs-lookup"><span data-stu-id="4ba87-121">Authentication</span></span>](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
  
## <a name="see-also"></a><span data-ttu-id="4ba87-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4ba87-122">See Also</span></span>  
 [<span data-ttu-id="4ba87-123">보안 개요</span><span class="sxs-lookup"><span data-stu-id="4ba87-123">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="4ba87-124">Windows Server App Fabric에 대 한 보안 모델</span><span class="sxs-lookup"><span data-stu-id="4ba87-124">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
