---
title: "SQL Server Compact 및 LINQ to SQL"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 59022359-a5a2-4c42-9a6a-5c0259c3ad17
caps.latest.revision: "5"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 9409c17065b0421ec32a61352f9c0b975095ab44
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="sql-server-compact-and-linq-to-sql"></a><span data-ttu-id="4603a-102">SQL Server Compact 및 LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="4603a-102">SQL Server Compact and LINQ to SQL</span></span>
<span data-ttu-id="4603a-103">SQL Server Compact는 Visual Studio와 함께 설치 된 기본 데이터베이스입니다.</span><span class="sxs-lookup"><span data-stu-id="4603a-103">SQL Server Compact is the default database installed with Visual Studio.</span></span> <span data-ttu-id="4603a-104">자세한 내용은 참조 [PAVE 조치를 사용 하 여 SQL Server Compact (Visual Studio)](http://msdn.microsoft.com/en-us/13320dd1-94e5-4077-bf76-8df253695ccc)합니다.</span><span class="sxs-lookup"><span data-stu-id="4603a-104">For more information, see [PAVE OVER Using SQL Server Compact (Visual Studio)](http://msdn.microsoft.com/en-us/13320dd1-94e5-4077-bf76-8df253695ccc).</span></span>  
  
 <span data-ttu-id="4603a-105">이 항목에서는 사용법, 구성, 기능 집합 및 범위의 주요 차이점에 설명 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="4603a-105">This topic outlines the key differences in usage, configuration, feature sets, and scope of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] support.</span></span>  
  
## <a name="characteristics-of-sql-server-compact-in-relation-to-linq-to-sql"></a><span data-ttu-id="4603a-106">LINQ to SQL과 관련된 SQL Server Compact의 특성</span><span class="sxs-lookup"><span data-stu-id="4603a-106">Characteristics of SQL Server Compact in Relation to LINQ to SQL</span></span>  
 <span data-ttu-id="4603a-107">기본적으로 SQL Server Compact는 모든에 대해 설치 [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] 버전의 경우와 함께 사용할 개발 컴퓨터에서 사용할 수 있는 되므로 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="4603a-107">By default, SQL Server Compact is installed for all [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] editions, and is therefore available on the development computer for use with [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="4603a-108">하지만 SQL Server Compact를 사용 하 여 응용 프로그램의 배포 및 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 의 다른 한 [!INCLUDE[ssNoVersion](../../../../../../includes/ssnoversion-md.md)] 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="4603a-108">But deployment of an application that uses SQL Server Compact and [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] differs from that for a [!INCLUDE[ssNoVersion](../../../../../../includes/ssnoversion-md.md)] application.</span></span> <span data-ttu-id="4603a-109">SQL Server Compact는 .NET Framework의 일부가 아니므로 응용 프로그램과 함께 패키지하거나 Microsoft 사이트에서 별도로 다운로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4603a-109">SQL Server Compact is not a part of the .NET Framework, and therefore must be packaged with the application or downloaded separately from the Microsoft site.</span></span>  
  
 <span data-ttu-id="4603a-110">다음 특성에 주의합니다.</span><span class="sxs-lookup"><span data-stu-id="4603a-110">Note the following characteristics:</span></span>  
  
-   <span data-ttu-id="4603a-111">SQL Server Compact는 데이터베이스 파일(.sdf 확장명)에 대해 직접 사용할 수 있는 DLL로 패키지됩니다.</span><span class="sxs-lookup"><span data-stu-id="4603a-111">SQL Server Compact is packaged as a DLL that can be used against database files (.sdf extension) directly.</span></span>  
  
-   <span data-ttu-id="4603a-112">SQL Server Compact는 클라이언트 응용 프로그램과 동일한 프로세스에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4603a-112">SQL Server Compact runs in the same process as the client application.</span></span> <span data-ttu-id="4603a-113">SQL Server Compact와 통신 효율성와의 통신 보다 훨씬 더 클 수 따라서 있습니다 [!INCLUDE[ssNoVersion](../../../../../../includes/ssnoversion-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="4603a-113">The efficiency of communication with SQL Server Compact can therefore be significantly higher than communicating with [!INCLUDE[ssNoVersion](../../../../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="4603a-114">반면에 SQL Server Compact에서는 요구 해당 비용을 사용 하 여 관리 및 비관리 코드 간에 상호 운용이 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="4603a-114">On the other hand, SQL Server Compact does require interoperability between managed and unmanaged code with its attendant costs.</span></span>  
  
-   <span data-ttu-id="4603a-115">SQL Server Compact DLL의 크기가 작습니다.</span><span class="sxs-lookup"><span data-stu-id="4603a-115">The size of the SQL Server Compact DLL is small.</span></span> <span data-ttu-id="4603a-116">이로 인해 전체 응용 프로그램 크기가 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="4603a-116">This feature reduces the overall application size.</span></span>  
  
-   <span data-ttu-id="4603a-117">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 런타임 및 SQLMetal 명령줄 도구에서 SQL Server Compact를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="4603a-117">The [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] runtime and the SQLMetal command-line tool support SQL Server Compact.</span></span>  
  
-   <span data-ttu-id="4603a-118">[!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]에서는 SQL Server Compact를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4603a-118">The [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] does not support SQL Server Compact.</span></span>  
  
## <a name="feature-set"></a><span data-ttu-id="4603a-119">기능 집합</span><span class="sxs-lookup"><span data-stu-id="4603a-119">Feature Set</span></span>  
 <span data-ttu-id="4603a-120">SQL Server Compact 기능 집합은 기능 집합 보다 훨씬 간단 [!INCLUDE[ssNoVersion](../../../../../../includes/ssnoversion-md.md)] 영향을 줄 수 있는 다음과 같은 방법으로 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 응용 프로그램:</span><span class="sxs-lookup"><span data-stu-id="4603a-120">The SQL Server Compact feature set is much simpler than the feature set of [!INCLUDE[ssNoVersion](../../../../../../includes/ssnoversion-md.md)] in the following ways that can affect [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications :</span></span>  
  
-   <span data-ttu-id="4603a-121">SQL Server Compact에서는 저장 프로시저나 뷰를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4603a-121">SQL Server Compact does not support stored procedures or views.</span></span>  
  
-   <span data-ttu-id="4603a-122">SQL Server Compact에서는 데이터 형식 및 SQL 함수의 하위 집합만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="4603a-122">SQL Server Compact supports only a subset of data types and SQL functions.</span></span>  
  
-   <span data-ttu-id="4603a-123">SQL Server Compact에서는 SQL 구문의 하위 집합만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="4603a-123">SQL Server Compact supports only a subset of SQL constructs.</span></span>  
  
-   <span data-ttu-id="4603a-124">SQL Server Compact에서는 최소한의 최적화 프로그램을 제공하므로</span><span class="sxs-lookup"><span data-stu-id="4603a-124">SQL Server Compact provides only a minimal optimizer.</span></span> <span data-ttu-id="4603a-125">일부 쿼리의 시간이 초과될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4603a-125">It is possible that some queries might time out.</span></span>  
  
-   <span data-ttu-id="4603a-126">SQL Server Compact는 부분 신뢰를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4603a-126">SQL Server Compact does not support partial trust.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4603a-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4603a-127">See Also</span></span>  
 [<span data-ttu-id="4603a-128">참조</span><span class="sxs-lookup"><span data-stu-id="4603a-128">Reference</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)
