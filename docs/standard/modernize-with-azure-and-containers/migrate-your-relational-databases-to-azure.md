---
title: "관계형 데이터베이스를 azure로 마이그레이션"
description: "기존.NET 응용 프로그램을 Azure 클라우드 및 Windows 컨테이너를 최신식 | 관계형 데이터베이스를 azure로 마이그레이션"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.prod: .net
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 9189de8d083c8f9dea8c53b428e6cd34ae6dad15
ms.sourcegitcommit: d3cfda0943364aaf6ccd574f55f584576c8a4fee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/08/2018
---
# <a name="migrate-your-relational-databases-to-azure"></a><span data-ttu-id="25aab-103">관계형 데이터베이스를 azure로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="25aab-103">Migrate your relational databases to azure</span></span>

<span data-ttu-id="25aab-104">비전: Azure는 가장 포괄적인 데이터베이스 마이그레이션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="25aab-104">Vision: Azure offers the most comprehensive database migration.</span></span>

<span data-ttu-id="25aab-105">Azure에서 데이터베이스 서버 (순수 리프트 및 shift) IaaS Vm에 직접 마이그레이션할 수 있습니다 또는 추가 혜택에 대 한 Azure SQL 데이터베이스로 마이그레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25aab-105">In Azure, you can migrate your database servers directly to IaaS VMs (pure lift and shift), or you can migrate to Azure SQL Database, for additional benefits.</span></span> <span data-ttu-id="25aab-106">Azure SQL 데이터베이스 관리 되는 인스턴스 및 전체 데이터베이스-as a service (DBaaS) 옵션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="25aab-106">Azure SQL Database offers managed instance and full database-as-a-service (DBaaS) options.</span></span> <span data-ttu-id="25aab-107">그림 3-1 여러 관계형 데이터베이스는 Azure에서 사용할 수 있는 마이그레이션 경로 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="25aab-107">Figure 3-1 shows the multiple relational database migration paths available in Azure.</span></span>

![Azure에서 데이터베이스 마이그레이션 경로](./media/image3-1.png)

> <span data-ttu-id="25aab-109">**그림 3-1.**</span><span class="sxs-lookup"><span data-stu-id="25aab-109">**Figure 3-1.**</span></span> <span data-ttu-id="25aab-110">Azure에서 데이터베이스 마이그레이션 경로</span><span class="sxs-lookup"><span data-stu-id="25aab-110">Database migration paths in Azure</span></span>

## <a name="when-to-migrate-to-azure-sql-database-managed-instance"></a><span data-ttu-id="25aab-111">Azure SQL 데이터베이스 관리 되는 인스턴스를 마이그레이션 시기</span><span class="sxs-lookup"><span data-stu-id="25aab-111">When to migrate to Azure SQL Database Managed Instance</span></span>

<span data-ttu-id="25aab-112">대부분의 경우 Azure SQL 데이터베이스 관리 되는 인스턴스를 Azure로 데이터를 마이그레이션할 때 고려할 최선의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25aab-112">In most cases, Azure SQL Database Managed Instance will be your best option to consider when you migrate your data to Azure.</span></span> <span data-ttu-id="25aab-113">SQL Server 데이터베이스를 마이그레이션하는 거의 100% 하는지 다시 응용 프로그램을 설계 하거나 데이터 또는 데이터 액세스 코드를 변경할 필요가 없습니다 해야 하는 경우 Azure SQL 데이터베이스의 관리 되는 인스턴스 기능을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="25aab-113">If you are migrating SQL Server databases and need nearly 100% assurance that you won't need to re-architect your application or make changes to your data or data access code, choose the Managed Instance feature of Azure SQL Database.</span></span>

<span data-ttu-id="25aab-114">Azure SQL 데이터베이스 관리 되는 인스턴스는 표준 Azure SQL 데이터베이스 (단일 데이터베이스 모델)에서 제공 하는 기능 외의 격리 요구 사항 또는 SQL Server 인스턴스 수준 기능에 대 한 추가 요구 사항이 있는 경우 최상의 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="25aab-114">Azure SQL Database Managed Instance is the best option if you have additional requirements for SQL Server instance-level functionality, or isolation requirements beyond the features provided in a standard Azure SQL Database (single database model).</span></span> <span data-ttu-id="25aab-115">마지막 하나는 가장 PaaS 지향 선택 하지만 기존의 SQL server의 같은 기능을 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="25aab-115">This last one is the most PaaS-oriented choice, but it doesn't offer the same features as that of a traditional SQL server.</span></span> <span data-ttu-id="25aab-116">마이그레이션 frictions 노출 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25aab-116">Migration might surface frictions.</span></span>

<span data-ttu-id="25aab-117">예를 들어 SQL Server 기능을 인스턴스 수준에 심층 투자 했습니다 하는 조직에서 관리 되는 인스턴스 SQL로 마이그레이션 도움이 되는 경우</span><span class="sxs-lookup"><span data-stu-id="25aab-117">For example, an organization that has made deep investments in instance-level SQL Server capabilities would benefit from migrating to SQL Managed Instance.</span></span> <span data-ttu-id="25aab-118">인스턴스 수준 SQL Server 기능의 예 SQL 공용 언어 런타임 (CLR) 통합, SQL Server 에이전트, 포함 및 데이터베이스 간 쿼리 합니다.</span><span class="sxs-lookup"><span data-stu-id="25aab-118">Examples of instance-level SQL Server capabilities include SQL common language runtime (CLR) integration, SQL Server Agent, and cross-database querying.</span></span> <span data-ttu-id="25aab-119">이러한 기능에 대 한 지원 표준 Azure SQL 데이터베이스 (단일 데이터베이스 모델)에서 제공 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="25aab-119">Support for these features are not available in standard Azure SQL Database (a single-database model).</span></span>

<span data-ttu-id="25aab-120">조직은 되는 산업에서 작동 하 고 보안을 위해 격리를 유지 해야 하는 SQL 관리 되는 인스턴스 모델 선택에서 향상 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25aab-120">An organization that operates in a highly regulated industry, and which needs to maintain isolation for security purposes, also might benefit from choosing the SQL Managed Instance model.</span></span>

<span data-ttu-id="25aab-121">Azure SQL 데이터베이스에서 관리 되는 인스턴스는 다음과 같은 특징이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25aab-121">Managed Instance in Azure SQL Database has the following characteristics:</span></span>

- <span data-ttu-id="25aab-122">Azure 가상 네트워크를 통해 보안 격리</span><span class="sxs-lookup"><span data-stu-id="25aab-122">Security isolation through Azure Virtual Network</span></span>

- <span data-ttu-id="25aab-123">응용 프로그램 표면 호환성, 이러한 기능:</span><span class="sxs-lookup"><span data-stu-id="25aab-123">Application surface compatibility, with these features:</span></span>

  - <span data-ttu-id="25aab-124">SQL Server 에이전트 및 SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="25aab-124">SQL Server Agent and SQL Server Profiler</span></span>

  - <span data-ttu-id="25aab-125">데이터베이스 간 참조와 쿼리를 SQL CLR 복제, 변경 데이터 캡처 (CDC) 및 Service Broker</span><span class="sxs-lookup"><span data-stu-id="25aab-125">Cross-database references and queries, SQL CLR, replication, change data capture (CDC), and Service Broker</span></span>

- <span data-ttu-id="25aab-126">데이터베이스 크기를 최대 35 확장성</span><span class="sxs-lookup"><span data-stu-id="25aab-126">Database sizes up to 35 TB</span></span>

- <span data-ttu-id="25aab-127">이러한 기능을 사용 하 여 최소 가동 중지 시간 마이그레이션:</span><span class="sxs-lookup"><span data-stu-id="25aab-127">Minimum-downtime migration, with these features:</span></span>

  - <span data-ttu-id="25aab-128">Azure 데이터베이스 마이그레이션 서비스</span><span class="sxs-lookup"><span data-stu-id="25aab-128">Azure Database Migration Service</span></span>

  - <span data-ttu-id="25aab-129">기본 백업 및 복원 및 로그 전달</span><span class="sxs-lookup"><span data-stu-id="25aab-129">Native backup and restore, and log shipping</span></span>

<span data-ttu-id="25aab-130">이러한 기능을 사용 Azure SQL 데이터베이스를 기존 응용 프로그램 데이터베이스를 마이그레이션할 때의 관리 되는 인스턴스 모델 제공 거의 100 %Paas 이점에 SQL Server에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="25aab-130">With these capabilities, when you migrate existing application databases to Azure SQL Database, the Managed Instance model offers nearly 100% of the benefits of Paas for SQL Server.</span></span> <span data-ttu-id="25aab-131">관리 되는 인스턴스는 인스턴스 수준 기능을 사용 하 여 응용 프로그램 디자인을 변경 하지 않고 계속 하면 SQL Server 환경입니다.</span><span class="sxs-lookup"><span data-stu-id="25aab-131">Managed Instance is a SQL Server environment where you continue using instance-level capabilities without changing your application design.</span></span>

<span data-ttu-id="25aab-132">관리 되는 인스턴스는 현재 SQL Server를 사용 하 고 클라우드에서 네트워크 보안에는 유연성 필요 엔터프라이즈의 경우 가장 적합 한 때문일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25aab-132">Managed Instance is probably the best fit for enterprises that currently are using SQL Server, and which require flexibility in their network security in the cloud.</span></span> <span data-ttu-id="25aab-133">SQL 데이터베이스에 대 한 개인 가상 네트워크를 것 같습니다.</span><span class="sxs-lookup"><span data-stu-id="25aab-133">It's like having a private virtual network for your SQL databases.</span></span>

## <a name="when-to-migrate-to-azure-sql-database"></a><span data-ttu-id="25aab-134">Azure SQL 데이터베이스로 마이그레이션 시기</span><span class="sxs-lookup"><span data-stu-id="25aab-134">When to migrate to Azure SQL Database</span></span>

<span data-ttu-id="25aab-135">앞서 언급 했 듯이 표준 Azure SQL 데이터베이스는 완전히 관리 되는, 관계형 DBaaS 합니다.</span><span class="sxs-lookup"><span data-stu-id="25aab-135">As mentioned, the standard Azure SQL Database is a fully managed, relational DBaaS.</span></span> <span data-ttu-id="25aab-136">SQL 데이터베이스는 전 세계 38 데이터 센터 간에 수백만 프로덕션 데이터베이스의 현재 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="25aab-136">SQL Database currently manages millions of production databases, across 38 datacenters, around the world.</span></span> <span data-ttu-id="25aab-137">광범위 한 응용 프로그램 및 구동 세계적인 규모에 고급 데이터 처리를 필요로 하는 데이터를 가장 많이 사용, 중요 한 응용 프로그램을 간단 하 게 트랜잭션 데이터를 관리 하에서 작업을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="25aab-137">It supports a broad range of applications and workloads, from managing straightforward transactional data, to driving the most data-intensive, mission-critical applications that require advanced data processing at a global scale.</span></span>

<span data-ttu-id="25aab-138">PaaS의 완전 한 기능으로 인해 및 더 나은 가격-궁극적으로 비용을 절감 하 고-없습니다 추가 인스턴스 기능과 그 사용 하 여 기본, 표준 SQL 데이터베이스 응용 프로그램이 있는 경우 프로그램 "기본적으로 선택"으로 표준 Azure SQL 데이터베이스를 이동 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="25aab-138">Because of its full PaaS features and better pricing-and ultimately lower cost-you should move to the standard Azure SQL Database as your "by-default choice" if you have an application that uses basic, standard SQL databases, and no additional instance features.</span></span> <span data-ttu-id="25aab-139">SQL CLR 통합, SQL Server 에이전트 및 데이터베이스 간 쿼리 같은 SQL Server 기능 표준 Azure SQL 데이터베이스에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="25aab-139">SQL Server features like SQL CLR integration, SQL Server Agent, and cross-database querying are not supported in the standard Azure SQL Database.</span></span> <span data-ttu-id="25aab-140">이러한 기능은 Azure SQL 데이터베이스 관리 되는 인스턴스 모델에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25aab-140">Those features are available only in the Azure SQL Database Managed Instance model.</span></span>

<span data-ttu-id="25aab-141">Azure SQL 데이터베이스는 응용 프로그램 개발자에 만들어지는 지능형 클라우드 데이터베이스 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="25aab-141">Azure SQL Database is the only intelligent cloud database service that's built for app developers.</span></span> <span data-ttu-id="25aab-142">즉시, 다중 테 넌 트 앱을 효율적으로 제공할 수 있도록 가동 중지 시간 없이 크기가 조정 되는 유일한 클라우드 데이터베이스 서비스 이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="25aab-142">It's also the only cloud database service that scales on-the-fly, without downtime, to help you efficiently deliver multitenant apps.</span></span> <span data-ttu-id="25aab-143">궁극적으로, Azure SQL 데이터베이스 혁신을 하는 데 시간이 더 오래 유지 및 시장 출시 시간을 가속화 합니다.</span><span class="sxs-lookup"><span data-stu-id="25aab-143">Ultimately, Azure SQL Database leaves you more time to innovate, and it accelerates your time to market.</span></span> <span data-ttu-id="25aab-144">안전한 앱을 빌드할 수 있으며 언어와 선호 하는 플랫폼을 사용 하 여 SQL 데이터베이스에 연결.</span><span class="sxs-lookup"><span data-stu-id="25aab-144">You can build secure apps, and connect to your SQL database by using the languages and platforms that you prefer.</span></span>

<span data-ttu-id="25aab-145">Azure SQL 데이터베이스는 다음과 같은 이점을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="25aab-145">Azure SQL Database offers the following benefits:</span></span>

- <span data-ttu-id="25aab-146">학습 및 응용 프로그램에 맞게 조정 하는 기본 제공 지능 (기계 학습)</span><span class="sxs-lookup"><span data-stu-id="25aab-146">Built-in intelligence (machine learning) that learns and adapts to your app</span></span>

- <span data-ttu-id="25aab-147">요청 시 데이터베이스 프로 비전</span><span class="sxs-lookup"><span data-stu-id="25aab-147">On-demand database provisioning</span></span>

- <span data-ttu-id="25aab-148">모든 작업에 대 한 제품의 범위</span><span class="sxs-lookup"><span data-stu-id="25aab-148">A range of offers, for all workloads</span></span>

- <span data-ttu-id="25aab-149">99.99% 가용성 SLA, 0 개 유지 관리</span><span class="sxs-lookup"><span data-stu-id="25aab-149">99.99% availability SLA, zero maintenance</span></span>

- <span data-ttu-id="25aab-150">데이터 보호를 위한 지리적 복제 및 복원 서비스</span><span class="sxs-lookup"><span data-stu-id="25aab-150">Geo-replication and restore services for data protection</span></span>

- <span data-ttu-id="25aab-151">Azure SQL 데이터베이스 지정 시간 복원 기능</span><span class="sxs-lookup"><span data-stu-id="25aab-151">Azure SQL Database Point in Time Restore feature</span></span>

- <span data-ttu-id="25aab-152">SQL Server 2016에서는 하이브리드 및 마이그레이션을 포함 하 여 호환성</span><span class="sxs-lookup"><span data-stu-id="25aab-152">Compatibility with SQL Server 2016, including hybrid and migration</span></span>

<span data-ttu-id="25aab-153">표준 Azure SQL 데이터베이스 보다에 더 가까운 PaaS Azure SQL 데이터베이스 관리 되는 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="25aab-153">The standard Azure SQL Database is closer to PaaS than Azure SQL Database Managed Instance.</span></span> <span data-ttu-id="25aab-154">해야 사용 하려고 하면, 가능한 경우 하므로 관리 되는 클라우드에서 많은 혜택을 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25aab-154">You should try to use it, if possible, because you'll get more benefits from a managed cloud.</span></span> <span data-ttu-id="25aab-155">그러나 Azure SQL 데이터베이스 일반에서 몇 가지 주요 차이점이 있으며 온-프레미스 SQL Server 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="25aab-155">However, Azure SQL Database has some key differences from regular and on-premises SQL Server instances.</span></span> <span data-ttu-id="25aab-156">기존 응용 프로그램의 데이터베이스 요구 사항 및 enterprise 요구 사항 및 정책에 따라 아닐 적합 하 고 클라우드로 마이그레이션을 계획할 때.</span><span class="sxs-lookup"><span data-stu-id="25aab-156">Depending on your existing application's database requirements, and your enterprise requirements and policies, it might not be the best choice when you are planning your migration to the cloud.</span></span>

## <a name="when-to-move-your-original-rdbms-to-a-vm-iaas"></a><span data-ttu-id="25aab-157">VM (IaaS)에 원래 RDBMS 프로그램을 이동 하는 경우</span><span class="sxs-lookup"><span data-stu-id="25aab-157">When to move your original RDBMS to a VM (IaaS)</span></span>

<span data-ttu-id="25aab-158">마이그레이션 옵션 중 하나 원래 관계형 데이터베이스 관리 시스템 RDBMS (), Oracle, IBM DB2, MySQL, PostgreSQL 또는 SQL Server를 포함 하 여 Azure VM에서 실행 중인 유사한 서버를 이동 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="25aab-158">One of your migration options is to move your original relational database management system (RDBMS), including Oracle, IBM DB2, MySQL, PostgreSQL, or SQL Server, to a similar server that's running on an Azure VM.</span></span> <span data-ttu-id="25aab-159">마이그레이션해야 하는 가장 빠른 클라우드 최소한의 변경 또는 전혀 변경으로 전혀 기존 응용 프로그램의 경우 IaaS 클라우드에서로 직접 마이그레이션을 상당히 많은 옵션을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25aab-159">If you have existing applications that require the fastest migration to the cloud with minimal changes, or no changes at all, a direct migration to IaaS in the cloud might be a fair option.</span></span> <span data-ttu-id="25aab-160">클라우드의 모든 이점을 활용 하는 가장 좋은 방법은 하지 않을 수 있지만 가장 빠른 초기 경로 때문일 합니다.</span><span class="sxs-lookup"><span data-stu-id="25aab-160">It might not be the best way to take advantage of all the cloud's benefits, but it's probably the fastest initial path.</span></span>

<span data-ttu-id="25aab-161">현재 Microsoft Azure 지원 최대 [331 다른 데이터베이스 서버의](https://azuremarketplace.microsoft.com/en-us/marketplace/apps/category/databases?page=1&subcategories=databases-all) IaaS Vm으로 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="25aab-161">Currently, Microsoft Azure supports up to [331 different database servers](https://azuremarketplace.microsoft.com/en-us/marketplace/apps/category/databases?page=1&subcategories=databases-all) deployed as IaaS VMs.</span></span> <span data-ttu-id="25aab-162">여기에 SQL Server, Oracle, MySQL, PostgreSQL, 및 IBM DB2와 같은 인기 있는 RDBMSes MongoDB, Cassandra, DataStax, MariaDB, 및 Cloudera와 같은 다른 많은 NoSQL 데이터베이스 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25aab-162">These include popular RDBMSes like SQL Server, Oracle, MySQL, PostgreSQL, and IBM DB2, and many other NoSQL databases like MongoDB, Cassandra, DataStax, MariaDB, and Cloudera.</span></span>

> [!NOTE]
> <span data-ttu-id="25aab-163">이동 되지만 Azure VM에 프로그램 RDBMS에는 (있기 때문에 IaaS)에서 클라우드로 데이터를 마이그레이션할 수는 가장 빠른 방법은 있을 수 있으며,이 방법은 (데이터베이스 관리자 및 IT 전문가) IT 팀에 많은 투자를 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="25aab-163">Although moving your RDBMS to an Azure VM might be the fastest way to migrate your data to the cloud (because it is IaaS), this approach requires a significant investment in your IT teams (database administrators and IT pros).</span></span> <span data-ttu-id="25aab-164">엔터프라이즈 팀을 설정 하 고 고가용성, 재해 복구 및 SQL Server에 대 한 패치를 관리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="25aab-164">Enterprise teams need to be able to set up and manage high availability, disaster recovery, and patching for SQL Server.</span></span> <span data-ttu-id="25aab-165">이 컨텍스트에 모든 관리 권한 사용 하 여 사용자 지정 된 환경도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="25aab-165">This context also needs a customized environment, with full administrative rights.</span></span>

## <a name="when-to-migrate-to-sql-server-as-a-vm-iaas"></a><span data-ttu-id="25aab-166">VM (IaaS)으로 SQL Server로 마이그레이션 시기</span><span class="sxs-lookup"><span data-stu-id="25aab-166">When to migrate to SQL Server as a VM (IaaS)</span></span>

<span data-ttu-id="25aab-167">몇 가지 계속 해야 하는 경우 SQL server 일반 VM으로 마이그레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25aab-167">There might be a few cases where you still need to migrate to SQL Server as a regular VM.</span></span> <span data-ttu-id="25aab-168">예제 시나리오는 SQL Server Reporting Services를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="25aab-168">An example scenario is if you need to use SQL Server Reporting Services.</span></span> <span data-ttu-id="25aab-169">대부분의 경우에서 하지만 Azure SQL 데이터베이스 관리 되는 인스턴스 제공할 수 있습니다는 SQL Server VM로의 마이그레이션을 시도 하면 마지막 수단 이어야 합니다. 온-프레미스 SQL server에서 마이그레이션하는 데 필요한 모든 것입니다.</span><span class="sxs-lookup"><span data-stu-id="25aab-169">In most cases, though, Azure SQL Database Managed Instance can provide everything you need to migrate from on-premises SQL servers, so migration to a SQL Server VM should be your last resort to try.</span></span>

## <a name="use-azure-database-migration-service-to-migrate-your-relational-databases-to-azure"></a><span data-ttu-id="25aab-170">관계형 데이터베이스를 Azure로 데이터베이스 마이그레이션 Azure 서비스를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="25aab-170">Use Azure Database Migration Service to migrate your relational databases to Azure</span></span> 

<span data-ttu-id="25aab-171">Azure SQL 데이터베이스, Azure SQL 데이터베이스 관리 되는 인스턴스 또는 Azure VM에서 SQL Server 대상 데이터베이스 인지를 Azure에 SQL Server, Oracle, MySQL 등 관계형 데이터베이스를 마이그레이션하려면 Azure 데이터베이스 마이그레이션 서비스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25aab-171">You can use Azure Database Migration Service to migrate relational databases like SQL Server, Oracle, and MySQL to Azure, whether your target database is Azure SQL Database, Azure SQL Database Managed Instance, or SQL Server on an Azure VM.</span></span>

<span data-ttu-id="25aab-172">자동화 된 워크플로 평가 보고를 사용 하면 데이터베이스를 마이그레이션하기 전에 확인 하는 데 필요한 변경을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="25aab-172">The automated workflow, with assessment reporting, guides you through the changes you need to make before you migrate the database.</span></span> <span data-ttu-id="25aab-173">준비 되 면 서비스 Azure를 원본 데이터베이스를 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="25aab-173">When you are ready, the service migrates the source database to Azure.</span></span>

<span data-ttu-id="25aab-174">원래 RDBMS를 변경할 때마다 다시 테스트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="25aab-174">Whenever you change an original RDBMS, you might need to retest.</span></span> <span data-ttu-id="25aab-175">SQL 한 문장이 나 테스트 결과 따라 응용 프로그램의 개체-관계형 매핑 (ORM) 코드를 변경 하려면 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25aab-175">You also might need to change the SQL sentences or Object-Relational Mapping (ORM) code in your application, depending on testing results.</span></span>

<span data-ttu-id="25aab-176">다른 데이터베이스 (예를 들어 IBM DB2) 있고 리프트 및 shift 방법을 선택할 수 있습니다 계속 하 시겠습니까 해당 데이터베이스를 사용 하 여 azure에서 IaaS Vm으로 더 복잡 한 데이터 마이그레이션을 수행 하려는 경우가 아니면 합니다.</span><span class="sxs-lookup"><span data-stu-id="25aab-176">If you have any other database (for example, IBM DB2) and you opt for a lift and shift approach, you might want to continue using those databases as IaaS VMs in Azure, unless you are willing to perform a more complex data migration.</span></span> <span data-ttu-id="25aab-177">더 복잡 한 데이터 마이그레이션 새 스키마 및 다른 프로그래밍 라이브러리와 다른 데이터베이스 형식으로 마이그레이션하는 것 이므로 추가 작업이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="25aab-177">A more complex data migration will require additional effort, because you'd be migrating to a different database type with new schema and different programming libraries.</span></span>

<span data-ttu-id="25aab-178">Azure 데이터베이스 마이그레이션 서비스를 사용 하 여 데이터베이스를 마이그레이션하는 방법에 자세한 내용은 [Azure SQL 데이터베이스 관리 되는 인스턴스 및 Azure 데이터베이스 마이그레이션 서비스 빠르게 클라우드로 가져올](https://channel9.msdn.com/Events/Build/2017/P4008)합니다.</span><span class="sxs-lookup"><span data-stu-id="25aab-178">To learn how to migrate databases by using Azure Database Migration Service, see [Get to the cloud faster with Azure SQL Database Managed Instance and Azure Database Migration Service](https://channel9.msdn.com/Events/Build/2017/P4008).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="25aab-179">추가 자료</span><span class="sxs-lookup"><span data-stu-id="25aab-179">Additional resources</span></span>

- <span data-ttu-id="25aab-180">**클라우드 SQL Server 옵션 선택: Azure SQL 데이터베이스 (PaaS) 또는 Azure VM (IaaS)에서 SQL Server**</span><span class="sxs-lookup"><span data-stu-id="25aab-180">**Choose a cloud SQL Server option: Azure SQL Database (PaaS) or SQL Server on Azure VM (IaaS)**</span></span>

    [<span data-ttu-id="25aab-181">https://docs.microsoft.com/azure/sql-database/sql-database-paas-vs-sql-server-iaas</span><span class="sxs-lookup"><span data-stu-id="25aab-181">https://docs.microsoft.com/azure/sql-database/sql-database-paas-vs-sql-server-iaas</span></span>](https://docs.microsoft.com/azure/sql-database/sql-database-paas-vs-sql-server-iaas)

- <span data-ttu-id="25aab-182">**Azure SQL DB 관리 되는 인스턴스 및 데이터베이스 마이그레이션 서비스 빠르게 클라우드로 가져오기**</span><span class="sxs-lookup"><span data-stu-id="25aab-182">**Get to the cloud faster with Azure SQL DB Managed Instance and Database Migration Service**</span></span>

    [<span data-ttu-id="25aab-183">https://channel9.msdn.com/Events/Build/2017/P4008</span><span class="sxs-lookup"><span data-stu-id="25aab-183">https://channel9.msdn.com/Events/Build/2017/P4008</span></span>](https://channel9.msdn.com/Events/Build/2017/P4008)

- <span data-ttu-id="25aab-184">**클라우드의 SQL 데이터베이스에 SQL Server 데이터베이스 마이그레이션**</span><span class="sxs-lookup"><span data-stu-id="25aab-184">**SQL Server database migration to SQL Database in the cloud**</span></span>

    [<span data-ttu-id="25aab-185">https://docs.microsoft.com/azure/sql-database/sql-database-cloud-migrate</span><span class="sxs-lookup"><span data-stu-id="25aab-185">https://docs.microsoft.com/azure/sql-database/sql-database-cloud-migrate</span></span>](https://docs.microsoft.com/azure/sql-database/sql-database-cloud-migrate)

- <span data-ttu-id="25aab-186">**Azure SQL Database**</span><span class="sxs-lookup"><span data-stu-id="25aab-186">**Azure SQL Database**</span></span>

    [<span data-ttu-id="25aab-187">https://azure.microsoft.com/services/sql-database/?v=16.50</span><span class="sxs-lookup"><span data-stu-id="25aab-187">https://azure.microsoft.com/services/sql-database/?v=16.50</span></span>](https://azure.microsoft.com/services/sql-database/?v=16.50)

- <span data-ttu-id="25aab-188">**가상 컴퓨터에서 SQL Server**</span><span class="sxs-lookup"><span data-stu-id="25aab-188">**SQL Server on virtual machines**</span></span>

    [<span data-ttu-id="25aab-189">https://azure.microsoft.com/services/virtual-machines/sql-server/</span><span class="sxs-lookup"><span data-stu-id="25aab-189">https://azure.microsoft.com/services/virtual-machines/sql-server/</span></span>](https://azure.microsoft.com/services/virtual-machines/sql-server/)

>[!div class="step-by-step"]
<span data-ttu-id="25aab-190">[이전](lift-and-shift-existing-apps-azure-iaas.md)
[다음](lift-and-shift-existing-apps-devops/index.md)</span><span class="sxs-lookup"><span data-stu-id="25aab-190">[Previous](lift-and-shift-existing-apps-azure-iaas.md)
[Next](lift-and-shift-existing-apps-devops/index.md)</span></span>