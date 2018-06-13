---
title: 동작 보안
ms.date: 03/30/2017
ms.assetid: 19710ae3-f197-4d28-ba9d-52e465006819
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: c1360a5b9e4b96c66b4bb7809fc139d1306730dd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33499521"
---
# <a name="behavior-security"></a><span data-ttu-id="92d52-102">동작 보안</span><span class="sxs-lookup"><span data-stu-id="92d52-102">Behavior Security</span></span>
<span data-ttu-id="92d52-103">이 단원에는 서비스 동작에 대한 보안을 구성하는 방법을 보여 주는 샘플이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92d52-103">This section includes samples that demonstrate configuring security for service behaviors.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="92d52-104">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="92d52-104">In This Section</span></span>  
 [<span data-ttu-id="92d52-105">서비스 감사 동작</span><span class="sxs-lookup"><span data-stu-id="92d52-105">Service Auditing Behavior</span></span>](../../../../docs/framework/wcf/samples/service-auditing-behavior.md)  
 <span data-ttu-id="92d52-106">이 샘플에서는 서비스 작업 중에 서비스 이벤트 감사를 활성화하기 위해 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="92d52-106">This sample demonstrates how to use the <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> to enable auditing of security events during service operations.</span></span>  
  
 [<span data-ttu-id="92d52-107">멤버 자격 및 역할 공급자</span><span class="sxs-lookup"><span data-stu-id="92d52-107">Membership and Role Provider</span></span>](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)  
 <span data-ttu-id="92d52-108">이 샘플에서는 서비스에서 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 멤버 자격 및 역할 공급자를 사용하여 클라이언트를 인증하고 권한을 부여하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="92d52-108">This sample demonstrates how a service can use the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] membership and role providers to authenticate and authorize clients.</span></span>  
  
 [<span data-ttu-id="92d52-109">서비스 작업에 대한 액세스 승인</span><span class="sxs-lookup"><span data-stu-id="92d52-109">Authorizing Access to Service Operations</span></span>](../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md)  
 <span data-ttu-id="92d52-110">이 샘플에 사용 하는 방법을 보여 줍니다는 [ \<serviceAuthorization >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) 사용할 수 있도록는 <xref:System.Security.Permissions.PrincipalPermissionAttribute> 특성을 서비스 작업에 대 한 액세스 권한을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="92d52-110">This sample demonstrates how to use the [\<serviceAuthorization>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) to enable use of the <xref:System.Security.Permissions.PrincipalPermissionAttribute> attribute to authorize access to service operations.</span></span>  
  
 [<span data-ttu-id="92d52-111">클라이언트 가장</span><span class="sxs-lookup"><span data-stu-id="92d52-111">Impersonating the Client</span></span>](../../../../docs/framework/wcf/samples/impersonating-the-client.md)  
 <span data-ttu-id="92d52-112">이 샘플에서는 서비스가 호출자를 대신하여 시스템 리소스에 액세스할 수 있도록 서비스에서 호출자 응용 프로그램을 가장하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="92d52-112">This sample demonstrates how to impersonate the caller application at the service so that the service can access system resources on behalf of the caller.</span></span>
