---
title: "SQL Server 보안 개요"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ae66dd75-5c16-4cc0-9e12-774dd26d3fb9
caps.latest.revision: "5"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: a8f44b69f177584bb3680f68c50ff054c6b805ed
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="overview-of-sql-server-security"></a><span data-ttu-id="4d031-102">SQL Server 보안 개요</span><span class="sxs-lookup"><span data-stu-id="4d031-102">Overview of SQL Server Security</span></span>
<span data-ttu-id="4d031-103">보안 위협에 대처하는 가장 좋은 방법은 여러 보안 계층으로 구성된 심층적인 방어 전략을 구현하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4d031-103">A defense-in-depth strategy, with overlapping layers of security, is the best way to counter security threats.</span></span> <span data-ttu-id="4d031-104">SQL Server는 데이터베이스 관리자와 개발자가 안전한 데이터베이스 응용 프로그램과 위협 대처 방안을 만들 수 있도록 디자인된 보안 아키텍처를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4d031-104">SQL Server provides a security architecture that is designed to allow database administrators and developers to create secure database applications and counter threats.</span></span> <span data-ttu-id="4d031-105">SQL Server의 각 버전은 새로운 기능이 추가되어 이전 버전의 SQL Server에 비해 향상되었지만</span><span class="sxs-lookup"><span data-stu-id="4d031-105">Each version of SQL Server has improved on previous versions of SQL Server with the introduction of new features and functionality.</span></span> <span data-ttu-id="4d031-106">사용자 환경에 맞게 직접 보안을 구성하고 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d031-106">However, security does not ship in the box.</span></span> <span data-ttu-id="4d031-107">보안 요구 사항은 응용 프로그램마다 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="4d031-107">Each application is unique in its security requirements.</span></span> <span data-ttu-id="4d031-108">따라서 개발자는 알려진 위협에 대응하는 데 가장 적합한 기능의 조합이 무엇인지 파악하고 향후 발생할 수 있는 위협에 대비할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d031-108">Developers need to understand which combination of features and functionality are most appropriate to counter known threats, and to anticipate threats that may arise in the future.</span></span>  
  
 <span data-ttu-id="4d031-109">SQL Server 인스턴스에는 서버를 비롯한 여러 엔터티의 계층 구조적 컬렉션이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d031-109">A SQL Server instance contains a hierarchical collection of entities, starting with the server.</span></span> <span data-ttu-id="4d031-110">각 서버에는 여러 개의 데이터베이스가 있고, 각 데이터베이스에는 보안 개체의 컬렉션이 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d031-110">Each server contains multiple databases, and each database contains a collection of securable objects.</span></span> <span data-ttu-id="4d031-111">모든 SQL Server 보안 개체에 연결 된 *권한을* 에 부여할 수 있습니다는 *주*, 되는 개인 사용자, 그룹 또는 SQL Server에 액세스 권한을 부여한 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="4d031-111">Every SQL Server securable has associated *permissions* that can be granted to a *principal*, which is an individual, group or process granted access to SQL Server.</span></span> <span data-ttu-id="4d031-112">SQL Server 보안 프레임 워크를 통해 보안 엔터티에 대 한 액세스를 관리 *인증* 및 *권한 부여*합니다.</span><span class="sxs-lookup"><span data-stu-id="4d031-112">The SQL Server security framework manages access to securable entities through *authentication* and *authorization*.</span></span>  
  
-   <span data-ttu-id="4d031-113">인증은 보안 주체가 서버에서 확인하는 자격 증명을 제출하여 액세스를 요청함으로써 SQL Server에 로그온하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="4d031-113">Authentication is the process of logging on to SQL Server by which a principal requests access by submitting credentials that the server evaluates.</span></span> <span data-ttu-id="4d031-114">인증을 통해 사용자 또는 프로세스의 ID가 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d031-114">Authentication establishes the identity of the user or process being authenticated.</span></span>  
  
-   <span data-ttu-id="4d031-115">권한 부여는 특정 보안 주체가 액세스할 수 있는 보안 리소스 및 해당 리소스에 대해 허용되는 작업을 결정하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="4d031-115">Authorization is the process of determining which securable resources a principal can access, and which operations are allowed for those resources.</span></span>  
  
 <span data-ttu-id="4d031-116">이 단원의 항목에서는 SQL Server 보안 기본 사항에 대해 설명하며 보다 자세한 설명을 볼 수 있는 SQL Server 온라인 설명서의 해당 항목에 대한 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4d031-116">The topics in this section cover SQL Server security fundamentals, providing links to the complete documentation in the relevant version of SQL Server Books Online.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4d031-117">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="4d031-117">In This Section</span></span>  
 [<span data-ttu-id="4d031-118">SQL Server에서 인증</span><span class="sxs-lookup"><span data-stu-id="4d031-118">Authentication in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/authentication-in-sql-server.md)  
 <span data-ttu-id="4d031-119">SQL Server의 로그인 및 인증에 대해 설명하고 추가 리소스에 대한 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4d031-119">Describes logins and authentication in SQL Server and provides links to additional resources.</span></span>  
  
 [<span data-ttu-id="4d031-120">SQL Server의 서버 및 데이터베이스 역할</span><span class="sxs-lookup"><span data-stu-id="4d031-120">Server and Database Roles in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/server-and-database-roles-in-sql-server.md)  
 <span data-ttu-id="4d031-121">고정 서버 역할과 데이터베이스 역할, 사용자 지정 데이터베이스 역할 및 기본 제공 계정에 대해 설명하고 추가 리소스에 대한 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4d031-121">Describes fixed server and database roles, custom database roles, and built-in accounts and provides links to additional resources.</span></span>  
  
 [<span data-ttu-id="4d031-122">SQL Server에서 소유권 및 사용자 스키마 분리</span><span class="sxs-lookup"><span data-stu-id="4d031-122">Ownership and User-Schema Separation in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/ownership-and-user-schema-separation-in-sql-server.md)  
 <span data-ttu-id="4d031-123">개체 소유권과 사용자 스키마 분리에 대해 설명하고 추가 리소스에 대한 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4d031-123">Describes object ownership and  user-schema separation and provides links to additional resources.</span></span>  
  
 [<span data-ttu-id="4d031-124">SQL Server에서 권한 부여 및 권한</span><span class="sxs-lookup"><span data-stu-id="4d031-124">Authorization and Permissions in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/authorization-and-permissions-in-sql-server.md)  
 <span data-ttu-id="4d031-125">최소 권한 원칙을 사용하여 권한을 부여하는 방법에 대해 설명하고 추가 리소스에 대한 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4d031-125">Describes granting permissions using the principle of least privilege and provides links to additional resources.</span></span>  
  
 [<span data-ttu-id="4d031-126">SQL Server에서 데이터 암호화</span><span class="sxs-lookup"><span data-stu-id="4d031-126">Data Encryption in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/data-encryption-in-sql-server.md)  
 <span data-ttu-id="4d031-127">SQL Server의 데이터 암호화 옵션에 대해 설명하고 추가 리소스에 대한 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4d031-127">Describes data encryption options in SQL Server and provides links to additional resources.</span></span>  
  
 [<span data-ttu-id="4d031-128">SQL Server의 CLR 통합 보안</span><span class="sxs-lookup"><span data-stu-id="4d031-128">CLR Integration Security in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/clr-integration-security-in-sql-server.md)  
 <span data-ttu-id="4d031-129">CLR 통합 보안 리소스에 대한 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4d031-129">Provides links to CLR integration security resources.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d031-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4d031-130">See Also</span></span>  
 [<span data-ttu-id="4d031-131">ADO.NET 응용 프로그램 보안</span><span class="sxs-lookup"><span data-stu-id="4d031-131">Securing ADO.NET Applications</span></span>](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [<span data-ttu-id="4d031-132">SQL Server 보안</span><span class="sxs-lookup"><span data-stu-id="4d031-132">SQL Server Security</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-security.md)  
 [<span data-ttu-id="4d031-133">SQL Server의 응용 프로그램 보안 시나리오</span><span class="sxs-lookup"><span data-stu-id="4d031-133">Application Security Scenarios in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 [<span data-ttu-id="4d031-134">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="4d031-134">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
