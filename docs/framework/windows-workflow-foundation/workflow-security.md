---
title: 워크플로 보안
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- programming [WF], workflow security
ms.assetid: d712a566-f435-44c0-b8c0-49298e84b114
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: bfd7c3e36bf28c364adf3cd230522cfc40a9503b
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="workflow-security"></a><span data-ttu-id="09c79-102">워크플로 보안</span><span class="sxs-lookup"><span data-stu-id="09c79-102">Workflow Security</span></span>
<span data-ttu-id="09c79-103">Windows WF (Workflow Foundation) 통합 된 Microsoft SQL Server와 같은 여러 가지 서로 다른 기술 및 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="09c79-103">Windows Workflow Foundation (WF) is integrated with several different technologies, such as Microsoft SQL Server and [!INCLUDE[indigo1](../../../includes/indigo1-md.md)].</span></span> <span data-ttu-id="09c79-104">이러한 기술과 잘못 상호 작용하면 워크플로에 보안 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09c79-104">Interacting with these technologies may introduce security issues into your workflow if done improperly.</span></span>  
  
## <a name="persistence-security-concerns"></a><span data-ttu-id="09c79-105">지속성 보안 고려 사항</span><span class="sxs-lookup"><span data-stu-id="09c79-105">Persistence Security Concerns</span></span>  
  
1.  <span data-ttu-id="09c79-106"><xref:System.Activities.Statements.Delay> 활동 및 지속성을 사용하는 워크플로는 서비스로 다시 활성화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09c79-106">Workflows that use a <xref:System.Activities.Statements.Delay> activity and persistence need to be reactivated by a service.</span></span> <span data-ttu-id="09c79-107">Windows AppFabric은 WMS(워크플로 관리 서비스)를 사용하여 만료된 타이머로 워크플로를 다시 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="09c79-107">Windows AppFabric uses the Workflow Management Service (WMS) to reactivate workflows with expired timers.</span></span> <span data-ttu-id="09c79-108">WMS는 <xref:System.ServiceModel.WorkflowServiceHost>를 만들어 다시 활성화된 워크플로를 호스트합니다.</span><span class="sxs-lookup"><span data-stu-id="09c79-108">WMS creates a <xref:System.ServiceModel.WorkflowServiceHost> to host the reactivated workflow.</span></span> <span data-ttu-id="09c79-109">WMS 서비스가 중지된 경우 타이머가 만료되면 지속된 워크플로는 다시 활성화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09c79-109">If the WMS service is stopped, persisted workflows will not be reactivated when their timers expire.</span></span>  
  
2.  <span data-ttu-id="09c79-110">지속적인 인스턴스에 대한 액세스는 응용 프로그램 도메인 외부의 악의적인 엔터티로부터 보호되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09c79-110">Access to durable instancing should be protected against malicious entities external to the application domain.</span></span> <span data-ttu-id="09c79-111">또한 지속적인 인스턴스 코드와 같은 응용 프로그램 도메인에서 개발자는 악의적인 코드를 실행할 수 없는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09c79-111">In addition, developers should ensure that malicious code can't be executed in the same application domain as the durable instancing code.</span></span>  
  
3.  <span data-ttu-id="09c79-112">지속적인 인스턴스는 높은(관리자) 권한으로 실행해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="09c79-112">Durable instancing should not be run with elevated (Administrator) permissions.</span></span>  
  
4.  <span data-ttu-id="09c79-113">응용 프로그램 도메인 외부에서 처리되는 데이터는 보호해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09c79-113">Data being processed outside the application domain should be protected.</span></span>  
  
5.  <span data-ttu-id="09c79-114">보안 격리가 필요한 응용 프로그램은 스키마 추상화의 같은 인스턴스를 공유해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="09c79-114">Applications that require security isolation should not share the same instance of the schema abstraction.</span></span> <span data-ttu-id="09c79-115">이런 응용 프로그램은 다른 저장소 공급자 또는 다른 저장소 인스턴스를 사용하도록 구성된 저장소 공급자를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09c79-115">Such applications should use different store providers, or store providers configured to use different store instantiations.</span></span>  
  
## <a name="sql-server-security-concerns"></a><span data-ttu-id="09c79-116">SQL Server 보안 고려 사항</span><span class="sxs-lookup"><span data-stu-id="09c79-116">SQL Server Security Concerns</span></span>  
  
-   <span data-ttu-id="09c79-117">많은 수의 자식 활동, 위치, 책갈피, 호스트 확장 또는 범위를 사용하거나 매우 큰 페이로드가 있는 책갈피를 사용할 때는 메모리가 부족하거나 유지 중에 과도한 양의 데이터베이스 공간이 할당될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09c79-117">When large numbers of child activities, locations, bookmarks, host extensions, or scopes are used, or when bookmarks with very large payloads are used, memory can be exhausted, or undue amounts of database space can be allocated during persistence.</span></span> <span data-ttu-id="09c79-118">개체 수준 및 데이터베이스 수준 보안을 사용하여 이 문제를 완화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09c79-118">This can be mitigated by using object-level and database-level security.</span></span>  
  
-   <span data-ttu-id="09c79-119"><xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>를 사용할 때는 인스턴스 저장소를 보호해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09c79-119">When using <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>, the instance store must be secured.</span></span> <span data-ttu-id="09c79-120">자세한 내용은 참조 [SQL Server에 대 한 유용한 정보](http://go.microsoft.com/fwlink/?LinkId=164972)합니다.</span><span class="sxs-lookup"><span data-stu-id="09c79-120">For more information, see [SQL Server Best Practices](http://go.microsoft.com/fwlink/?LinkId=164972).</span></span>  
  
-   <span data-ttu-id="09c79-121">인스턴스 저장소의 중요 데이터를 암호화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09c79-121">Sensitive data in the instance store should be encrypted.</span></span> <span data-ttu-id="09c79-122">자세한 내용은 참조 [SQL 보안 암호화](http://go.microsoft.com/fwlink/?LinkId=164976)합니다.</span><span class="sxs-lookup"><span data-stu-id="09c79-122">For more information, see [SQL Security Encryption](http://go.microsoft.com/fwlink/?LinkId=164976).</span></span>  
  
-   <span data-ttu-id="09c79-123">데이터베이스 연결 문자열은 종종 구성 파일에 포함되기 때문에 Windows 수준 보안(ACL)을 사용하여 구성 파일(대개 Web.Config)이 안전한지, 로그인과 암호 정보가 연결 문자열에 포함되어 있지 않은지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09c79-123">Since the database connection string is often included in a configuration file, windows-level security (ACL) should be used to ensure that the configuration file (Web.Config usually) is secure, and that login and password information are not included in the connection string.</span></span> <span data-ttu-id="09c79-124">대신 데이터베이스와 웹 서버 사이에는 Windows 인증을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09c79-124">Windows authentication should be used between the database and the web server instead.</span></span>  
  
## <a name="considerations-for-workflowservicehost"></a><span data-ttu-id="09c79-125">WorkflowServiceHost에 대한 고려 사항</span><span class="sxs-lookup"><span data-stu-id="09c79-125">Considerations for WorkflowServiceHost</span></span>  
  
-   <span data-ttu-id="09c79-126">워크플로에 사용되는 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 끝점을 보호해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09c79-126">[!INCLUDE[indigo1](../../../includes/indigo1-md.md)] endpoints used in workflows should be secured.</span></span> <span data-ttu-id="09c79-127">자세한 내용은 참조 [WCF 보안 개요](http://go.microsoft.com/fwlink/?LinkID=164975)합니다.</span><span class="sxs-lookup"><span data-stu-id="09c79-127">For more information, see [WCF Security Overview](http://go.microsoft.com/fwlink/?LinkID=164975).</span></span>  
  
-   <span data-ttu-id="09c79-128"><xref:System.ServiceModel.ServiceAuthorizationManager>를 사용하여 호스트 수준 권한 부여를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09c79-128">Host-level authorization can be implemented by using <xref:System.ServiceModel.ServiceAuthorizationManager>.</span></span> <span data-ttu-id="09c79-129">참조 [방법: 서비스에 대 한 사용자 지정 권한 부여 관리자 만들기](http://go.microsoft.com/fwlink/?LinkId=192228) 대 한 자세한 내용은 합니다.</span><span class="sxs-lookup"><span data-stu-id="09c79-129">See [How To: Create a Custom Authorization Manager for a Service](http://go.microsoft.com/fwlink/?LinkId=192228) for details.</span></span> <span data-ttu-id="09c79-130">다음 샘플에도 설명 되어: [워크플로 서비스 보안](../../../docs/framework/windows-workflow-foundation/samples/securing-workflow-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="09c79-130">This is also demonstrated in the following sample: [Securing Workflow Services](../../../docs/framework/windows-workflow-foundation/samples/securing-workflow-services.md).</span></span>  
  
-   <span data-ttu-id="09c79-131">들어오는 메시지에 대한 ServiceSecurityContext는 OperationContext에 액세스하여 워크플로 내에서도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09c79-131">The ServiceSecurityContext for the incoming message is also available from within workflow by accessing OperationContext.</span></span>  <span data-ttu-id="09c79-132">참조 [워크플로 서비스에서 OperationContext 액세스](../../../docs/framework/wcf/feature-details/accessing-operationcontext-from-a-workflow-service.md) 대 한 자세한 내용은 합니다.</span><span class="sxs-lookup"><span data-stu-id="09c79-132">See [Accessing OperationContext from a Workflow Service](../../../docs/framework/wcf/feature-details/accessing-operationcontext-from-a-workflow-service.md) for details.</span></span>  
  
## <a name="wf-security-pack-ctp"></a><span data-ttu-id="09c79-133">WF Security Pack CTP</span><span class="sxs-lookup"><span data-stu-id="09c79-133">WF Security Pack CTP</span></span>  
 <span data-ttu-id="09c79-134">Microsoft WF Security Pack CTP 1은 활동 및 해당 구현에 따라 집합의 첫 번째 community technology preview (CTP) 릴리스 [Windows Workflow Foundation](http://msdn.microsoft.com/netframework/aa663328.aspx)에 [.NET Framework 4](http://msdn.microsoft.com/netframework/default.aspx) (WF 4) 인데 [Windows Identity Foundation (WIF)](http://msdn.microsoft.com/security/aa570351.aspx)합니다.</span><span class="sxs-lookup"><span data-stu-id="09c79-134">The Microsoft WF Security Pack CTP 1 is the first community technology preview (CTP) release of a set of activities and their implementation based on [Windows Workflow Foundation](http://msdn.microsoft.com/netframework/aa663328.aspx)in [.NET Framework 4](http://msdn.microsoft.com/netframework/default.aspx) (WF 4) and the [Windows Identity Foundation (WIF)](http://msdn.microsoft.com/security/aa570351.aspx).</span></span>  <span data-ttu-id="09c79-135">Microsoft WF Security Pack CTP 1에는 다음과 같은 워크플로를 사용하여 다양한 보안 관련 시나리오를 손쉽게 사용하는 방법을 보여 주는 활동과 디자이너가 모두 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09c79-135">The Microsoft WF Security Pack CTP 1 contains both activities and their designers which illustrate how to easily enable various security-related scenarios using workflow, including:</span></span>  
  
1.  <span data-ttu-id="09c79-136">워크플로에서 클라이언트 ID 가장</span><span class="sxs-lookup"><span data-stu-id="09c79-136">Impersonating a client identity in the workflow</span></span>  
  
2.  <span data-ttu-id="09c79-137">PrincipalPermission 및 클레임의 유효성 검사 같은 워크플로 내 인증</span><span class="sxs-lookup"><span data-stu-id="09c79-137">In-workflow authorization, such as PrincipalPermission and validation of Claims</span></span>  
  
3.  <span data-ttu-id="09c79-138">사용자 이름/암호 또는 STS(보안 토큰 서비스)에서 검색한 토큰 같은 워크플로에 지정된 ClientCredentials을 사용하여 인증된 메시징</span><span class="sxs-lookup"><span data-stu-id="09c79-138">Authenticated messaging using ClientCredentials specified in the workflow, such as username/password or a token retrieved from a Security Token Service (STS)</span></span>  
  
4.  <span data-ttu-id="09c79-139">WS-Trust ActAs를 사용하여 클라이언트 보안 토큰이 백엔드 서비스로 이동(클레임 기반 위임)</span><span class="sxs-lookup"><span data-stu-id="09c79-139">Flowing a client security token to a back-end service (claims-based delegation) using WS-Trust ActAs</span></span>  
  
<span data-ttu-id="09c79-140">자세한 내용 및 WF Security Pack CTP 다운로드 하려면 참조: [WF Security Pack CTP](http://wf.codeplex.com/releases/view/48114)</span><span class="sxs-lookup"><span data-stu-id="09c79-140">For more information and to download the WF Security Pack CTP, see: [WF Security Pack CTP](http://wf.codeplex.com/releases/view/48114)</span></span>