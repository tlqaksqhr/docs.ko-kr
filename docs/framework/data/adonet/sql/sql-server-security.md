---
title: "SQL Server 보안"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9053724d-a1fb-4f0f-b9dc-7f6dd893e8ff
caps.latest.revision: 
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: c186b25aeaa42b7285316d7bc9de913dd7b89af7
ms.sourcegitcommit: ba765893e3efcece67d99fd6d5ce0074b050d1d9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/02/2018
---
# <a name="sql-server-security"></a><span data-ttu-id="ccf48-102">SQL Server 보안</span><span class="sxs-lookup"><span data-stu-id="ccf48-102">SQL Server Security</span></span>
[!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] <span data-ttu-id="ccf48-103">에 보안 데이터베이스 응용 프로그램 만들기를 지 원하는 많은 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ccf48-103">has many features that support creating secure database applications.</span></span>  
  
 <span data-ttu-id="ccf48-104">데이터 절도나 손상 같이 일반적으로 발생하는 보안 문제는 사용 중인 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 버전에 관계없이 항상 고려해야 할 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="ccf48-104">Common security considerations, such as data theft or vandalism, apply regardless of the version of [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] you are using.</span></span> <span data-ttu-id="ccf48-105">데이터 무결성도 보안 문제로 간주해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf48-105">Data integrity should also be considered as a security issue.</span></span> <span data-ttu-id="ccf48-106">데이터를 보호하지 않으면 특수한 데이터 조작이 허용되어 실수나 악의적으로 데이터가 잘못된 값으로 수정되거나 완전히 삭제될 수 있으므로 데이터가 쓸모없게 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ccf48-106">If data is not protected, it is possible that it could become worthless if ad hoc data manipulation is permitted and the data is inadvertently or maliciously modified with incorrect values or deleted entirely.</span></span> <span data-ttu-id="ccf48-107">또한 기밀 정보의 올바른 저장과 같이 반드시 지켜야 할 법적 요구 사항도 많습니다.</span><span class="sxs-lookup"><span data-stu-id="ccf48-107">In addition, there are often legal requirements that must be adhered to, such as the correct storage of confidential information.</span></span> <span data-ttu-id="ccf48-108">특정 관할권에서는 해당 법률에 따라 몇 가지 개인 데이터를 저장하는 것이 완전히 금지될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ccf48-108">Storing some kinds of personal data is proscribed entirely, depending on the laws that apply in a particular jurisdiction.</span></span>  
  
 <span data-ttu-id="ccf48-109">Windows가 버전마다 다른 것처럼 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]도 버전마다 보안 기능이 다르며 최신 버전이 이전 버전보다 향상된 보안 기능을 가지고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ccf48-109">Each version of [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] has different security features, as does each version of Windows, with later versions having enhanced functionality over earlier ones.</span></span> <span data-ttu-id="ccf48-110">하지만 보안 기능만으로는 데이터베이스 응용 프로그램의 보안을 보장할 수 없다는 점을 숙지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf48-110">It is important to understand that security features alone cannot guarantee a secure database application.</span></span> <span data-ttu-id="ccf48-111">데이터베이스 응용 프로그램은 각각 고유한 요구 사항, 실행 환경, 배포 모델, 실제 위치, 사용자 집단을 가집니다.</span><span class="sxs-lookup"><span data-stu-id="ccf48-111">Each database application is unique in its requirements, execution environment, deployment model, physical location, and user population.</span></span> <span data-ttu-id="ccf48-112">로컬에서만 실행되는 일부 응용 프로그램에는 최소한의 보안 기능만 있어도 되지만 대부분의 로컬 응용 프로그램이나 인터넷을 통해 배포되는 응용 프로그램에는 엄격한 보안 수단과 지속적인 모니터링 및 평가가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf48-112">Some applications that are local in scope may need only minimal security whereas other local applications or applications deployed over the Internet may require stringent security measures and ongoing monitoring and evaluation.</span></span>  
  
 <span data-ttu-id="ccf48-113">[!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 데이터베이스 응용 프로그램의 보안 요구 사항은 디자인 타임부터 고려해야 하며 뒤늦게 생각해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ccf48-113">The security requirements of a [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] database application should be considered at design time, not as an afterthought.</span></span> <span data-ttu-id="ccf48-114">개발 주기의 초기 단계에서 위협 요소를 평가하면 취약점이 발견되는 모든 부분의 손상 위험을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ccf48-114">Evaluating threats early in the development cycle gives you the opportunity to mitigate potential damage wherever a vulnerability is detected.</span></span>  
  
 <span data-ttu-id="ccf48-115">응용 프로그램의 초기 디자인이 뛰어나다고 해도 시스템이 발전함에 따라 새로운 위협 요소가 등장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ccf48-115">Even if the initial design of an application is sound, new threats may emerge as the system evolves.</span></span> <span data-ttu-id="ccf48-116">데이터베이스를 보호하는 여러 방어선을 만들면 보안 위반이 발생함으로써 입을 수 있는 손상을 최소화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ccf48-116">By creating multiple lines of defense around your database, you can minimize the damage inflicted by a security breach.</span></span> <span data-ttu-id="ccf48-117">이중 가장 먼저 구축해야 할 방어선은 필요한 권한 이상의 권한이 부여되지 않게 하여 공격에 노출되는 영역을 줄이는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ccf48-117">Your first line of defense is to reduce the attack surface area by never to granting more permissions than are absolutely necessary.</span></span>  
  
 <span data-ttu-id="ccf48-118">이 단원의 항목에서는 개발자와 관련이 있는 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]의 보안 기능에 대해 간략히 설명하며, 이러한 항목에 대해 자세히 다루고 있는 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 온라인 설명서와 기타 리소스의 관련 항목으로 연결되는 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf48-118">The topics in this section briefly describe the security features in [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] that are relevant for developers, with links to relevant topics in [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] Books Online and other resources that provide more detailed coverage.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ccf48-119">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="ccf48-119">In This Section</span></span>  
 [<span data-ttu-id="ccf48-120">SQL Server 보안 개요</span><span class="sxs-lookup"><span data-stu-id="ccf48-120">Overview of SQL Server Security</span></span>](../../../../../docs/framework/data/adonet/sql/overview-of-sql-server-security.md)  
 <span data-ttu-id="ccf48-121">[!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]의 아키텍처와 보안 기능에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf48-121">Describes the architecture and security features of [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="ccf48-122">SQL Server의 응용 프로그램 보안 시나리오</span><span class="sxs-lookup"><span data-stu-id="ccf48-122">Application Security Scenarios in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 <span data-ttu-id="ccf48-123">ADO.NET 및 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 응용 프로그램에 대한 다양한 응용 프로그램 보안 시나리오를 설명하는 항목을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf48-123">Contains topics discussing various application security scenarios for ADO.NET and [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] applications.</span></span>  
  
 [<span data-ttu-id="ccf48-124">SQL Server Express 보안</span><span class="sxs-lookup"><span data-stu-id="ccf48-124">SQL Server Express Security</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-express-security.md)  
 <span data-ttu-id="ccf48-125">[!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] Express의 보안 고려 사항에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf48-125">Describes security considerations for [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] Express.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ccf48-126">관련 단원</span><span class="sxs-lookup"><span data-stu-id="ccf48-126">Related Sections</span></span>  
[<span data-ttu-id="ccf48-127">SQL Server 데이터베이스 엔진 및 Azure SQL 데이터베이스에 대 한 보안 센터</span><span class="sxs-lookup"><span data-stu-id="ccf48-127">Security Center for SQL Server Database Engine and Azure SQL Database</span></span>](/sql/relational-databases/security/security-center-for-sql-server-database-engine-and-azure-sql-database)  
<span data-ttu-id="ccf48-128">SQL Server 및 Azure SQL 데이터베이스에 대 한 보안 고려 사항에 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf48-128">Describes security considerations for SQL Server and Azure SQL Database.</span></span>

[<span data-ttu-id="ccf48-129">SQL Server 설치에 대 한 보안 고려 사항</span><span class="sxs-lookup"><span data-stu-id="ccf48-129">Security Considerations for a SQL Server Installation</span></span>](/sql/sql-server/install/security-considerations-for-a-sql-server-installation)  
<span data-ttu-id="ccf48-130">SQL Server를 설치 하기 전에 고려해 야 할 보안 문제를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ccf48-130">Describes security concerns to consider before installing SQL Server.</span></span>

## <a name="see-also"></a><span data-ttu-id="ccf48-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ccf48-131">See Also</span></span>  
 [<span data-ttu-id="ccf48-132">ADO.NET 응용 프로그램 보안</span><span class="sxs-lookup"><span data-stu-id="ccf48-132">Securing ADO.NET Applications</span></span>](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [<span data-ttu-id="ccf48-133">SQL Server 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ccf48-133">SQL Server and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/index.md)  
