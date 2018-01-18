---
title: "밀접하게 결합된 클라이언트-서버 응용 프로그램을 사용한 LINQ to SQL"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e083d805-dcf6-459d-b9af-9ef0563f2dd7
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 6ff0ee9019f8c61ad2fc18c5d22240abb2dc6b9b
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="linq-to-sql-with-tightly-coupled-client-server-applications"></a><span data-ttu-id="d7e60-102">밀접하게 결합된 클라이언트-서버 응용 프로그램을 사용한 LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="d7e60-102">LINQ to SQL with Tightly-Coupled Client-Server Applications</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="d7e60-103">프레젠테이션 계층에 있는 밀접 하 게 결합 된 스마트 클라이언트와 중간 계층에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7e60-103"> can be used on the middle tier with tightly-coupled Smart Clients on the presentation layer.</span></span> <span data-ttu-id="d7e60-104">읽기 전용 데이터 액세스를 사용하고 낙관적 동시성 검사 또는 타임스탬프를 사용하는 낙관적 동시성 검사가 필요하지 않은 시나리오에서는 로컬 시나리오에 비해 작업이 크게 복잡하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d7e60-104">In scenarios that involve read-only data access, no optimistic concurrency checks, or optimistic concurrency with timestamps, there is not much more complexity than with non-remote scenarios.</span></span> <span data-ttu-id="d7e60-105">그러나 데이터베이스에서 원래 값을 사용하여 낙관적 동시성 검사를 수행해야 할 경우 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]은 데이터 집합을 사용할 때와는 달리 데이터 라운드트립을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d7e60-105">However, when a database requires optimistic concurrency checks with original values, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] does not provide the level of support for round-tripping of data that you find in DataSets.</span></span> <span data-ttu-id="d7e60-106">하지만 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 중간 계층은 모든 종류의 플랫폼에 있는 클라이언트와 데이터를 교환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7e60-106">However, a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] middle tier can exchange data with clients on any platform.</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="d7e60-107">[!INCLUDE[vs_orcas_long](../../../../../../includes/vs-orcas-long-md.md)] 클라이언트에 serialize 된 후 엔터티 상태를 추적 하는 인프라가 없는 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7e60-107"> in [!INCLUDE[vs_orcas_long](../../../../../../includes/vs-orcas-long-md.md)] provides no infrastructure for tracking entity state after they have been serialized to a client.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="d7e60-108">데이터와 프레젠테이션 계층 간의 상호 작용은 작고 비교적 원자적 인 서비스 지향 아키텍처를 사용 하도록 설정 하지만 원래 값의 라운드트립은 수행 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d7e60-108"> enables service-oriented architectures where interactions between the data and presentation layers are small and relatively atomic, but does not perform any round-tripping of original values.</span></span> <span data-ttu-id="d7e60-109">따라서 밀접하게 결합된 스마트 클라이언트와 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]을 사용하려는 경우 데이터베이스에서 원래 값을 사용하여 낙관적 동시성 검사를 사용한다면 프레젠테이션 계층과 중간 계층 사이에 변경 내용을 통신하는 메커니즘을 직접 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7e60-109">Therefore, if you want to use a tightly-coupled Smart Client with [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], and a database uses optimistic concurrency with original values, you will have to implement your own mechanism for communicating changes between the presentation tier and middle tier.</span></span> <span data-ttu-id="d7e60-110">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]이 중간 계층에서 제공하는 이점을 활용할 수 있도록 이와 같은 추가 작업을 수행할지 여부는 시스템 디자이너가 결정할 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="d7e60-110">It is up to the system designer to decide whether it makes sense to do this bit of extra work in exchange for the benefits that [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides on the middle tier.</span></span> <span data-ttu-id="d7e60-111">그러나 데이터베이스에서 타임스탬프를 사용하는 경우에는 변경 내용 추적 논리를 사용자 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d7e60-111">On the other hand, if the database has timestamps, then there is no need for custom change-tracking logic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7e60-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d7e60-112">See Also</span></span>  
 [<span data-ttu-id="d7e60-113">LINQ to SQL을 사용한 N 계층 및 원격 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="d7e60-113">N-Tier and Remote Applications with LINQ to SQL</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/n-tier-and-remote-applications-with-linq-to-sql.md)  
 [<span data-ttu-id="d7e60-114">웹 서비스를 사용하는 LINQ to SQL N 계층</span><span class="sxs-lookup"><span data-stu-id="d7e60-114">LINQ to SQL N-Tier with Web Services</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/linq-to-sql-n-tier-with-web-services.md)  
 [<span data-ttu-id="d7e60-115">n 계층 응용 프로그램에서 데이터 집합 작업</span><span class="sxs-lookup"><span data-stu-id="d7e60-115">Work with datasets in n-tier applications</span></span>](http://msdn.microsoft.com/library/f6ae2ee0-ea5f-4a79-8f4b-e21c115afb20)
