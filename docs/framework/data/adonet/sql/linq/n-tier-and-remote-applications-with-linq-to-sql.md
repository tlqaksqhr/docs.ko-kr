---
title: "LINQ to SQL을 사용한 N 계층 및 원격 응용 프로그램"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 854a1cdd-53cb-45f5-83ca-63962a9b3598
caps.latest.revision: "5"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 293ebf52b6179ec02f65c81112ee24c9b6322eae
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="n-tier-and-remote-applications-with-linq-to-sql"></a><span data-ttu-id="07f15-102">LINQ to SQL을 사용한 N 계층 및 원격 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="07f15-102">N-Tier and Remote Applications with LINQ to SQL</span></span>
<span data-ttu-id="07f15-103">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]을 사용하는 n 계층 또는 다계층 응용 프로그램을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07f15-103">You can create n-tier or multitier applications that use [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="07f15-104">일반적으로 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 데이터 컨텍스트, 엔터티 클래스 및 쿼리 생성 논리는 데이터 액세스 계층 (DAL)와 중간 계층에 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="07f15-104">Typically, the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] data context, entity classes, and query construction logic are located on the middle tier as the data access layer (DAL).</span></span> <span data-ttu-id="07f15-105">비즈니스 논리와 모든 비지속적 데이터는 엔터티와 데이터 컨텍스트의 부분 클래스와 메서드에 완전하게 구현되거나 별도의 클래스에 구현될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07f15-105">Business logic and any non-persistent data can be implemented completely in partial classes and methods of entities and the data context, or it can be implemented in separate classes.</span></span>  
  
 <span data-ttu-id="07f15-106">클라이언트 또는 프레젠테이션 계층에서 중간 계층의 원격 인터페이스에 있는 메서드를 호출하면 중간 계층의 DAL에서는 <xref:System.Data.Linq.DataContext> 메서드에 매핑된 쿼리나 저장 프로시저를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="07f15-106">The client or presentation layer calls methods on the middle-tier's remote interface, and the DAL on that tier will execute queries or stored procedures that are mapped to <xref:System.Data.Linq.DataContext> methods.</span></span> <span data-ttu-id="07f15-107">중간 계층에서는 일반적으로 프록시 개체 또는 엔터티의 XML 표현으로 클라이언트에 데이터를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="07f15-107">The middle tier returns the data to clients typically as XML representations of entities or proxy objects.</span></span>  
  
 <span data-ttu-id="07f15-108">중간 계층에서 엔터티는 엔터티의 상태를 추적하는 데이터 컨텍스트에 의해 만들어지며, 데이터베이스로부터의 지연된 로드 및 데이터베이스로의 변경 내용 전송을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="07f15-108">On the middle tier, entities are created by the data context, which tracks their state, and manages deferred loading from and submission of changes to the database.</span></span> <span data-ttu-id="07f15-109">이러한 엔터티는 `DataContext`에 "연결"됩니다.</span><span class="sxs-lookup"><span data-stu-id="07f15-109">These entities are "attached" to the `DataContext`.</span></span> <span data-ttu-id="07f15-110">그러나 serialization을 통해 엔터티를 다른 계층으로 보내면 엔터티가 분리되어 `DataContext`에서 해당 엔터티의 상태를 더 이상 추적하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="07f15-110">However, after the entities are sent to another tier through serialization, they become detached, which means the `DataContext` is no longer tracking their state.</span></span> <span data-ttu-id="07f15-111">업데이트를 위해 클라이언트에서 다시 보내는 엔터티는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 변경 내용을 데이터베이스에 전송하기 전에 데이터 컨텍스트에 다시 연결되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07f15-111">Entities that the client sends back for updates must be reattached to the data context before [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] can submit the changes to the database.</span></span> <span data-ttu-id="07f15-112">낙관적 동시성 검사에 원래 값 및/또는 타임스탬프가 필요한 경우 클라이언트에서는 이러한 정보를 중간 계층에 다시 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="07f15-112">The client is responsible for providing original values and/or timestamps back to the middle tier if those are required for optimistic concurrency checks.</span></span>  
  
 <span data-ttu-id="07f15-113">ASP.NET 응용 프로그램에서는 이러한 복잡한 작업을 <xref:System.Web.UI.WebControls.LinqDataSource>에서 대부분 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="07f15-113">In ASP.NET applications, the <xref:System.Web.UI.WebControls.LinqDataSource> manages most of this complexity.</span></span> <span data-ttu-id="07f15-114">자세한 내용은 참조 [NIB: LinqDataSource 웹 서버 컨트롤 개요](http://msdn.microsoft.com/en-us/104cfc3f-7385-47d3-8a51-830dfa791136)합니다.</span><span class="sxs-lookup"><span data-stu-id="07f15-114">For more information, see [NIB: LinqDataSource Web Server Control Overview](http://msdn.microsoft.com/en-us/104cfc3f-7385-47d3-8a51-830dfa791136).</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="07f15-115">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="07f15-115">Additional Resources</span></span>  
 <span data-ttu-id="07f15-116">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]을 사용하는 n 계층 응용 프로그램을 구현하는 방법에 대한 자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="07f15-116">For more information about how to implement n-tier applications that use [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], see the following topics:</span></span>  
  
-   [<span data-ttu-id="07f15-117">ASP.NET을 사용하는 LINQ to SQL N 계층</span><span class="sxs-lookup"><span data-stu-id="07f15-117">LINQ to SQL N-Tier with ASP.NET</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/linq-to-sql-n-tier-with-aspnet.md)  
  
-   [<span data-ttu-id="07f15-118">웹 서비스를 사용하는 LINQ to SQL N 계층</span><span class="sxs-lookup"><span data-stu-id="07f15-118">LINQ to SQL N-Tier with Web Services</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/linq-to-sql-n-tier-with-web-services.md)  
  
-   [<span data-ttu-id="07f15-119">밀접하게 결합된 클라이언트-서버 응용 프로그램을 사용한 LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="07f15-119">LINQ to SQL with Tightly-Coupled Client-Server Applications</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/linq-to-sql-with-tightly-coupled-client-server-applications.md)  
  
-   [<span data-ttu-id="07f15-120">N 계층 비즈니스 논리 구현</span><span class="sxs-lookup"><span data-stu-id="07f15-120">Implementing N-Tier Business Logic</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/implementing-business-logic-linq-to-sql.md)  
  
-   [<span data-ttu-id="07f15-121">N 계층 응용 프로그램에서 데이터 검색 및 CUD 작업(LINQ to SQL)</span><span class="sxs-lookup"><span data-stu-id="07f15-121">Data Retrieval and CUD Operations in N-Tier Applications (LINQ to SQL)</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-retrieval-and-cud-operations-in-n-tier-applications.md)  
  
 <span data-ttu-id="07f15-122">ADO.NET 데이터 집합을 사용 하는 n 계층 응용 프로그램에 대 한 자세한 내용은 참조 [n 계층 응용 프로그램에서 데이터 집합을 사용할](http://msdn.microsoft.com/library/f6ae2ee0-ea5f-4a79-8f4b-e21c115afb20)합니다.</span><span class="sxs-lookup"><span data-stu-id="07f15-122">For more information about n-tier applications that use ADO.NET DataSets, see [Work with datasets in n-tier applications](http://msdn.microsoft.com/library/f6ae2ee0-ea5f-4a79-8f4b-e21c115afb20).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07f15-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="07f15-123">See Also</span></span>  
 [<span data-ttu-id="07f15-124">배경 정보</span><span class="sxs-lookup"><span data-stu-id="07f15-124">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
