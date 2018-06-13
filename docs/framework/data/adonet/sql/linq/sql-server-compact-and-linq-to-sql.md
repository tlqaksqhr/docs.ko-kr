---
title: SQL Server Compact 및 LINQ to SQL
ms.date: 03/30/2017
ms.assetid: 59022359-a5a2-4c42-9a6a-5c0259c3ad17
ms.openlocfilehash: 74b8a7a6dfc9a4050dbba9a8c2f6969dba42656c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33355788"
---
# <a name="sql-server-compact-and-linq-to-sql"></a><span data-ttu-id="a45ef-102">SQL Server Compact 및 LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="a45ef-102">SQL Server Compact and LINQ to SQL</span></span>
<span data-ttu-id="a45ef-103">SQL Server Compact는 Visual Studio와 함께 설치 된 기본 데이터베이스입니다.</span><span class="sxs-lookup"><span data-stu-id="a45ef-103">SQL Server Compact is the default database installed with Visual Studio.</span></span> <span data-ttu-id="a45ef-104">자세한 내용은 참조 [PAVE 조치를 사용 하 여 SQL Server Compact (Visual Studio)](http://msdn.microsoft.com/library/13320dd1-94e5-4077-bf76-8df253695ccc)합니다.</span><span class="sxs-lookup"><span data-stu-id="a45ef-104">For more information, see [PAVE OVER Using SQL Server Compact (Visual Studio)](http://msdn.microsoft.com/library/13320dd1-94e5-4077-bf76-8df253695ccc).</span></span>  
  
 <span data-ttu-id="a45ef-105">이 항목에서는 사용법, 구성, 기능 집합 및 범위의 주요 차이점에 설명 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="a45ef-105">This topic outlines the key differences in usage, configuration, feature sets, and scope of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] support.</span></span>  
  
## <a name="characteristics-of-sql-server-compact-in-relation-to-linq-to-sql"></a><span data-ttu-id="a45ef-106">LINQ to SQL과 관련된 SQL Server Compact의 특성</span><span class="sxs-lookup"><span data-stu-id="a45ef-106">Characteristics of SQL Server Compact in Relation to LINQ to SQL</span></span>  
 <span data-ttu-id="a45ef-107">기본적으로 SQL Server Compact 모든 Visual Studio 버전에 대 한 설치 이므로 함께 사용할 개발 컴퓨터에서 사용할 수 있는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="a45ef-107">By default, SQL Server Compact is installed for all Visual Studio editions, and is therefore available on the development computer for use with [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="a45ef-108">하지만 SQL Server Compact를 사용 하 여 응용 프로그램의 배포 및 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] SQL Server 응용 프로그램에 대 한는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="a45ef-108">But deployment of an application that uses SQL Server Compact and [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] differs from that for a SQL Server application.</span></span> <span data-ttu-id="a45ef-109">SQL Server Compact는 .NET Framework의 일부가 아니므로 응용 프로그램과 함께 패키지하거나 Microsoft 사이트에서 별도로 다운로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a45ef-109">SQL Server Compact is not a part of the .NET Framework, and therefore must be packaged with the application or downloaded separately from the Microsoft site.</span></span>  
  
 <span data-ttu-id="a45ef-110">다음 특성에 주의합니다.</span><span class="sxs-lookup"><span data-stu-id="a45ef-110">Note the following characteristics:</span></span>  
  
-   <span data-ttu-id="a45ef-111">SQL Server Compact는 데이터베이스 파일(.sdf 확장명)에 대해 직접 사용할 수 있는 DLL로 패키지됩니다.</span><span class="sxs-lookup"><span data-stu-id="a45ef-111">SQL Server Compact is packaged as a DLL that can be used against database files (.sdf extension) directly.</span></span>  
  
-   <span data-ttu-id="a45ef-112">SQL Server Compact는 클라이언트 응용 프로그램과 동일한 프로세스에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a45ef-112">SQL Server Compact runs in the same process as the client application.</span></span> <span data-ttu-id="a45ef-113">따라서 SQL Server Compact와 통신 효율성 SQL Server와의 통신 보다 훨씬 더 높은 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a45ef-113">The efficiency of communication with SQL Server Compact can therefore be significantly higher than communicating with SQL Server.</span></span> <span data-ttu-id="a45ef-114">반면에 SQL Server Compact에서는 요구 해당 비용을 사용 하 여 관리 및 비관리 코드 간에 상호 운용이 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="a45ef-114">On the other hand, SQL Server Compact does require interoperability between managed and unmanaged code with its attendant costs.</span></span>  
  
-   <span data-ttu-id="a45ef-115">SQL Server Compact DLL의 크기가 작습니다.</span><span class="sxs-lookup"><span data-stu-id="a45ef-115">The size of the SQL Server Compact DLL is small.</span></span> <span data-ttu-id="a45ef-116">이로 인해 전체 응용 프로그램 크기가 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="a45ef-116">This feature reduces the overall application size.</span></span>  
  
-   <span data-ttu-id="a45ef-117">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 런타임 및 SQLMetal 명령줄 도구에서 SQL Server Compact를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="a45ef-117">The [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] runtime and the SQLMetal command-line tool support SQL Server Compact.</span></span>  
  
-   <span data-ttu-id="a45ef-118">[!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]에서는 SQL Server Compact를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a45ef-118">The [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] does not support SQL Server Compact.</span></span>  
  
## <a name="feature-set"></a><span data-ttu-id="a45ef-119">기능 집합</span><span class="sxs-lookup"><span data-stu-id="a45ef-119">Feature Set</span></span>  
 <span data-ttu-id="a45ef-120">영향을 줄 수 있는 다음과 같은 방법으로 SQL Server Compact 기능 집합은 SQL server 기능 집합 보다 훨씬 더 간단 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 응용 프로그램:</span><span class="sxs-lookup"><span data-stu-id="a45ef-120">The SQL Server Compact feature set is much simpler than the feature set of SQL Server in the following ways that can affect [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications :</span></span>  
  
-   <span data-ttu-id="a45ef-121">SQL Server Compact에서는 저장 프로시저나 뷰를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a45ef-121">SQL Server Compact does not support stored procedures or views.</span></span>  
  
-   <span data-ttu-id="a45ef-122">SQL Server Compact에서는 데이터 형식 및 SQL 함수의 하위 집합만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="a45ef-122">SQL Server Compact supports only a subset of data types and SQL functions.</span></span>  
  
-   <span data-ttu-id="a45ef-123">SQL Server Compact에서는 SQL 구문의 하위 집합만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="a45ef-123">SQL Server Compact supports only a subset of SQL constructs.</span></span>  
  
-   <span data-ttu-id="a45ef-124">SQL Server Compact에서는 최소한의 최적화 프로그램을 제공하므로</span><span class="sxs-lookup"><span data-stu-id="a45ef-124">SQL Server Compact provides only a minimal optimizer.</span></span> <span data-ttu-id="a45ef-125">일부 쿼리의 시간이 초과될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a45ef-125">It is possible that some queries might time out.</span></span>  
  
-   <span data-ttu-id="a45ef-126">SQL Server Compact는 부분 신뢰를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a45ef-126">SQL Server Compact does not support partial trust.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a45ef-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a45ef-127">See Also</span></span>  
 [<span data-ttu-id="a45ef-128">참조</span><span class="sxs-lookup"><span data-stu-id="a45ef-128">Reference</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)
