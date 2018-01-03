---
title: LINQ to SQL
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 73d13345-eece-471a-af40-4cc7a2f11655
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 78fbd1bde6727490e789ba22232af3f17af20d75
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="linq-to-sql"></a><span data-ttu-id="251ac-102">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="251ac-102">LINQ to SQL</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="251ac-103">은 관계형 데이터를 개체로 관리하는 데 필요한 런타임 인프라를 제공하는 [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] 버전 3.5의 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="251ac-103"> is a component of [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] version 3.5 that provides a run-time infrastructure for managing relational data as objects.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="251ac-104">관계형 데이터는 테이블 간에 서로 관계된 공통 열이 있는 이차원 테이블(*관계* 또는 *플랫 파일*)의 컬렉션으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="251ac-104">Relational data appears as a collection of two-dimensional tables (*relations* or *flat files*), where common columns relate tables to each other.</span></span> <span data-ttu-id="251ac-105">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]을 효율적으로 사용하려면 관계형 데이터베이스의 기본 원리에 대해 조금은 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="251ac-105">To use [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] effectively, you must have some familiarity with the underlying principles of relational databases.</span></span>  
  
 <span data-ttu-id="251ac-106">
          [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 관계형 데이터베이스의 데이터 모델은 개발자의 프로그래밍 언어로 표현되는 개체 모델에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="251ac-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the data model of a relational database is mapped to an object model expressed in the programming language of the developer.</span></span> <span data-ttu-id="251ac-107">응용 프로그램을 실행하면 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 개체 모델의 SQL 언어 통합 쿼리를 변환하여 실행을 위해 데이터베이스로 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="251ac-107">When the application runs, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translates into SQL the language-integrated queries in the object model and sends them to the database for execution.</span></span> <span data-ttu-id="251ac-108">데이터베이스에서 결과를 반환하면 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 해당 결과를 사용자의 프로그래밍 언어로 작업할 수 있는 개체로 다시 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="251ac-108">When the database returns the results, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translates them back to objects that you can work with in your own programming language.</span></span>  
  
 <span data-ttu-id="251ac-109">일반적으로 [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)]를 사용하는 개발자는 [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]의 많은 기능을 구현하는 데 필요한 사용자 인터페이스를 제공하는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="251ac-109">Developers using [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] typically use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)], which provides a user interface for implementing many of the features of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 <span data-ttu-id="251ac-110">이 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 릴리스에 포함된 설명서에서는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 응용 프로그램을 빌드하는 데 필요한 기본 빌드 블록, 프로세스 및 기술에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="251ac-110">The documentation that is included with this release of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] describes the basic building blocks, processes, and techniques you need for building [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications.</span></span> <span data-ttu-id="251ac-111">특정 문제에 대 한 Microsoft Docs를 검색할 수도 및에 참여할 수 있습니다는 [LINQ 포럼](http://go.microsoft.com/fwlink/?LinkId=76488)전문가 함께 보다 복잡 한 주제를 자세히 논의할 수 있는, 합니다.</span><span class="sxs-lookup"><span data-stu-id="251ac-111">You can also search Microsoft Docs for specific issues, and you can participate in the [LINQ Forum](http://go.microsoft.com/fwlink/?LinkId=76488), where you can discuss more complex topics in detail with experts.</span></span> <span data-ttu-id="251ac-112">마지막으로 [LINQ to SQL: .NET Language-Integrated Query for Relational Data](http://go.microsoft.com/fwlink/?LinkId=93205)(LINQ to SQL: 관계형 데이터에 대한 .NET Language-Integrated Query) 백서에서는 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] 및 C# 코드 예제를 통해 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 기술에 대해 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="251ac-112">Finally, the [LINQ to SQL: .NET Language-Integrated Query for Relational Data](http://go.microsoft.com/fwlink/?LinkId=93205) white paper details [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] technology, complete with [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] and C# code examples.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="251ac-113">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="251ac-113">In This Section</span></span>  
 [<span data-ttu-id="251ac-114">시작</span><span class="sxs-lookup"><span data-stu-id="251ac-114">Getting Started</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/getting-started.md)  
 <span data-ttu-id="251ac-115">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]을 사용하는 방법에 대한 정보와 함께 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에 대한 간략한 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="251ac-115">Provides a condensed overview of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] along with information about how to get started using [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 [<span data-ttu-id="251ac-116">프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="251ac-116">Programming Guide</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)  
 <span data-ttu-id="251ac-117">매핑, 쿼리, 업데이트, 디버깅 및 유사한 작업에 대한 단계를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="251ac-117">Provides steps for mapping, querying, updating, debugging, and similar tasks.</span></span>  
  
 [<span data-ttu-id="251ac-118">참조</span><span class="sxs-lookup"><span data-stu-id="251ac-118">Reference</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)  
 <span data-ttu-id="251ac-119">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]의 일부 측면에 대한 참조 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="251ac-119">Provides reference information about several aspects of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="251ac-120">항목에는 SQL-CLR 형식 매핑, 표준 쿼리 연산자 변환 등이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="251ac-120">Topics include SQL-CLR Type Mapping, Standard Query Operator Translation, and more.</span></span>  
  
 [<span data-ttu-id="251ac-121">샘플</span><span class="sxs-lookup"><span data-stu-id="251ac-121">Samples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/samples.md)  
 <span data-ttu-id="251ac-122">[!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] 및 C# 샘플에 대한 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="251ac-122">Provides links to [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] and C# samples.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="251ac-123">관련 단원</span><span class="sxs-lookup"><span data-stu-id="251ac-123">Related Sections</span></span>  
 [<span data-ttu-id="251ac-124">LINQ(Language-Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="251ac-124">LINQ (Language-Integrated Query)</span></span>](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)  
 <span data-ttu-id="251ac-125">[!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] 기술에 대한 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="251ac-125">Provides an overview of [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] technologies.</span></span>  
  
 [<span data-ttu-id="251ac-126">LINQ</span><span class="sxs-lookup"><span data-stu-id="251ac-126">LINQ</span></span>](../../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 <span data-ttu-id="251ac-127">[!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] 사용자를 위해 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] 기술에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="251ac-127">Describes [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] technologies for [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] users.</span></span>  
  
 [<span data-ttu-id="251ac-128">LINQ to ADO.NET</span><span class="sxs-lookup"><span data-stu-id="251ac-128">LINQ to ADO.NET</span></span>](http://msdn.microsoft.com/en-us/be3297b9-1b54-4d4c-82a8-add0d79c2006)  
 <span data-ttu-id="251ac-129">[!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] 포털에 대한 링크입니다.</span><span class="sxs-lookup"><span data-stu-id="251ac-129">Links to the [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] portal.</span></span>  
  
 [<span data-ttu-id="251ac-130">LINQ to SQL 연습</span><span class="sxs-lookup"><span data-stu-id="251ac-130">LINQ to SQL Walkthroughs</span></span>](http://msdn.microsoft.com/en-us/308e66ac-f704-4e00-9b4e-7af0045a2374)  
 <span data-ttu-id="251ac-131">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에 대한 연습을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="251ac-131">Lists walkthroughs available for [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 [<span data-ttu-id="251ac-132">샘플 데이터베이스 다운로드</span><span class="sxs-lookup"><span data-stu-id="251ac-132">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)  
 <span data-ttu-id="251ac-133">설명서에 사용되는 샘플 데이터베이스를 다운로드하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="251ac-133">Describes how to download sample databases used in the documentation.</span></span>  
  
 [<span data-ttu-id="251ac-134">LinqDataSource 기술 개요</span><span class="sxs-lookup"><span data-stu-id="251ac-134">LinqDataSource Technology Overview</span></span>](http://msdn.microsoft.com/en-us/104cfc3f-7385-47d3-8a51-830dfa791136)  
 <span data-ttu-id="251ac-135"><xref:System.Web.UI.WebControls.LinqDataSource> 컨트롤에서 [!INCLUDE[vbteclinqext](../../../../../../includes/vbteclinqext-md.md)] 데이터 소스 컨트롤 아키텍처를 통해 [!INCLUDE[vstecasp](../../../../../../includes/vstecasp-md.md)]를 웹 개발자에게 노출시키는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="251ac-135">Describes how the <xref:System.Web.UI.WebControls.LinqDataSource> control exposes [!INCLUDE[vbteclinqext](../../../../../../includes/vbteclinqext-md.md)] to Web developers through the [!INCLUDE[vstecasp](../../../../../../includes/vstecasp-md.md)] data-source control architecture.</span></span>
