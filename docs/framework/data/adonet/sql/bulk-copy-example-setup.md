---
title: 대량 복사 예제 설정
ms.date: 03/30/2017
ms.assetid: d4dde6ac-b8b6-4593-965a-635c8fb2dadb
ms.openlocfilehash: cb4e92529c8e68bd7e47e5943f7e79dcc97603e0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33362441"
---
# <a name="bulk-copy-example-setup"></a><span data-ttu-id="c257a-102">대량 복사 예제 설정</span><span class="sxs-lookup"><span data-stu-id="c257a-102">Bulk Copy Example Setup</span></span>
<span data-ttu-id="c257a-103"><xref:System.Data.SqlClient.SqlBulkCopy> 클래스를 사용하면 SQL Server 테이블에만 데이터를 쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c257a-103">The <xref:System.Data.SqlClient.SqlBulkCopy> class can be used to write data only to SQL Server tables.</span></span> <span data-ttu-id="c257a-104">이 항목에 표시 된 코드 예제는 SQL Server 예제 데이터베이스를 사용 하 여 **AdventureWorks**합니다.</span><span class="sxs-lookup"><span data-stu-id="c257a-104">The code samples shown in this topic use the SQL Server sample database, **AdventureWorks**.</span></span> <span data-ttu-id="c257a-105">코드 샘플에서는 기존 테이블을 변경하지 않도록 사용자가 먼저 만드는 테이블에 데이터를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="c257a-105">To avoid altering the existing tables code samples write data to tables that you must create first.</span></span>  
  
 <span data-ttu-id="c257a-106">**BulkCopyDemoMatchingColumns** 및 **BulkCopyDemoDifferentColumns** 테이블은 둘 다 기반는 **AdventureWorks** **Production.Products**  테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="c257a-106">The **BulkCopyDemoMatchingColumns** and **BulkCopyDemoDifferentColumns** tables are both based on the **AdventureWorks** **Production.Products** table.</span></span> <span data-ttu-id="c257a-107">이러한 테이블을 사용 하는 코드 샘플 데이터에서 추가 되 고 **Production.Products** 이러한 샘플 테이블 중 하나에 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="c257a-107">In code samples that use these tables, data is added from the **Production.Products** table to one of these sample tables.</span></span> <span data-ttu-id="c257a-108">**BulkCopyDemoDifferentColumns** 샘플 원본 데이터에서 열을 대상 테이블로 매핑하는 방법을 설명 하는 경우 테이블을 사용 합니다. **BulkCopyDemoMatchingColumns** 대부분의 다른 샘플에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c257a-108">The **BulkCopyDemoDifferentColumns** table is used when the sample illustrates how to map columns from the source data to the destination table; **BulkCopyDemoMatchingColumns** is used for most other samples.</span></span>  
  
 <span data-ttu-id="c257a-109">일부 코드 샘플에서는 <xref:System.Data.SqlClient.SqlBulkCopy> 클래스 하나로 여러 테이블에 쓰는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c257a-109">A few of the code samples demonstrate how to use one <xref:System.Data.SqlClient.SqlBulkCopy> class to write to multiple tables.</span></span> <span data-ttu-id="c257a-110">이러한 예제는 **BulkCopyDemoOrderHeader** 및 **BulkCopyDemoOrderDetail** 테이블 대상 테이블로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c257a-110">For these samples, the **BulkCopyDemoOrderHeader** and **BulkCopyDemoOrderDetail** tables are used as the destination tables.</span></span> <span data-ttu-id="c257a-111">이러한 테이블은 기반는 **Sales.SalesOrderHeader** 및 **Sales.SalesOrderDetail** 테이블에 **AdventureWorks**합니다.</span><span class="sxs-lookup"><span data-stu-id="c257a-111">These tables are based on the **Sales.SalesOrderHeader** and **Sales.SalesOrderDetail** tables in **AdventureWorks**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c257a-112">**SqlBulkCopy** 사용에 대 한 구문을 보여 주는 코드 샘플은 제공 **SqlBulkCopy** 만 합니다.</span><span class="sxs-lookup"><span data-stu-id="c257a-112">The **SqlBulkCopy** code samples are provided to demonstrate the syntax for using **SqlBulkCopy** only.</span></span> <span data-ttu-id="c257a-113">소스 테이블과 대상 테이블이 동일한 SQL Server 인스턴스에 있으면 Transact-SQL `INSERT … SELECT` 문을 사용하여 데이터를 더 쉽고 빠르게 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c257a-113">If the source and destination tables are located in the same SQL Server instance, it is easier and faster to use a Transact-SQL `INSERT … SELECT` statement to copy the data.</span></span>  
  
## <a name="table-setup"></a><span data-ttu-id="c257a-114">테이블 설정</span><span class="sxs-lookup"><span data-stu-id="c257a-114">Table Setup</span></span>  
 <span data-ttu-id="c257a-115">코드 샘플을 올바르게 실행하는 데 필요한 테이블을 만들려면 SQL Server 데이터베이스에서 다음 Transact-SQL 문을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c257a-115">To create the tables necessary for the code samples to run correctly, you must run the following Transact-SQL statements in a SQL Server database.</span></span>  
  
```  
USE AdventureWorks  
  
IF EXISTS (SELECT * FROM dbo.sysobjects   
 WHERE id = object_id(N'[dbo].[BulkCopyDemoMatchingColumns]')  
 AND OBJECTPROPERTY(id, N'IsUserTable') = 1)  
    DROP TABLE [dbo].[BulkCopyDemoMatchingColumns]  
  
CREATE TABLE [dbo].[BulkCopyDemoMatchingColumns]([ProductID] [int] IDENTITY(1,1) NOT NULL,  
    [Name] [nvarchar](50) NOT NULL,  
    [ProductNumber] [nvarchar](25) NOT NULL,  
 CONSTRAINT [PK_ProductID] PRIMARY KEY CLUSTERED  
(  
    [ProductID] ASC  
) ON [PRIMARY]) ON [PRIMARY]  
  
IF EXISTS (SELECT * FROM dbo.sysobjects   
 WHERE id = object_id(N'[dbo].[BulkCopyDemoDifferentColumns]')  
 AND OBJECTPROPERTY(id, N'IsUserTable') = 1)  
    DROP TABLE [dbo].[BulkCopyDemoDifferentColumns]  
  
CREATE TABLE [dbo].[BulkCopyDemoDifferentColumns]([ProdID] [int] IDENTITY(1,1) NOT NULL,  
    [ProdNum] [nvarchar](25) NOT NULL,  
    [ProdName] [nvarchar](50) NOT NULL,  
 CONSTRAINT [PK_ProdID] PRIMARY KEY CLUSTERED  
(  
    [ProdID] ASC  
) ON [PRIMARY]) ON [PRIMARY]  
  
IF EXISTS (SELECT * FROM dbo.sysobjects   
 WHERE id = object_id(N'[dbo].[BulkCopyDemoOrderHeader]')  
 AND OBJECTPROPERTY(id, N'IsUserTable') = 1)  
    DROP TABLE [dbo].[BulkCopyDemoOrderHeader]  
  
CREATE TABLE [dbo].[BulkCopyDemoOrderHeader]([SalesOrderID] [int] IDENTITY(1,1) NOT NULL,  
    [OrderDate] [datetime] NOT NULL,  
    [AccountNumber] [nvarchar](15) NULL,  
 CONSTRAINT [PK_SalesOrderID] PRIMARY KEY CLUSTERED  
(  
    [SalesOrderID] ASC  
) ON [PRIMARY]) ON [PRIMARY]  
  
IF EXISTS (SELECT * FROM dbo.sysobjects   
 WHERE id = object_id(N'[dbo].[BulkCopyDemoOrderDetail]')  
 AND OBJECTPROPERTY(id, N'IsUserTable') = 1)  
    DROP TABLE [dbo].[BulkCopyDemoOrderDetail]  
  
CREATE TABLE [dbo].[BulkCopyDemoOrderDetail]([SalesOrderID] [int] NOT NULL,  
    [SalesOrderDetailID] [int] NOT NULL,  
    [OrderQty] [smallint] NOT NULL,  
    [ProductID] [int] NOT NULL,  
    [UnitPrice] [money] NOT NULL,  
 CONSTRAINT [PK_LineNumber] PRIMARY KEY CLUSTERED  
(  
    [SalesOrderID] ASC,  
    [SalesOrderDetailID] ASC  
) ON [PRIMARY]) ON [PRIMARY]  
```  
  
## <a name="see-also"></a><span data-ttu-id="c257a-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c257a-116">See Also</span></span>  
 [<span data-ttu-id="c257a-117">SQL Server에서 대량 복사 작업</span><span class="sxs-lookup"><span data-stu-id="c257a-117">Bulk Copy Operations in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/bulk-copy-operations-in-sql-server.md)  
 [<span data-ttu-id="c257a-118">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="c257a-118">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
