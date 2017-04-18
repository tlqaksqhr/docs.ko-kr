---
title: "대량 복사 예제 설정 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d4dde6ac-b8b6-4593-965a-635c8fb2dadb
caps.latest.revision: 5
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 5
---
# 대량 복사 예제 설정
<xref:System.Data.SqlClient.SqlBulkCopy> 클래스를 사용하면 SQL Server 테이블에만 데이터를 쓸 수 있습니다.  이 항목의 코드 샘플에서는 SQL Server 샘플 데이터베이스인 **AdventureWorks**를 사용합니다.  코드 샘플에서는 기존 테이블을 변경하지 않도록 사용자가 먼저 만드는 테이블에 데이터를 씁니다.  
  
 **BulkCopyDemoMatchingColumns** 및 **BulkCopyDemoDifferentColumns** 테이블은 모두 **AdventureWorks** **Production.Products** 테이블을 기반으로 합니다.  이러한 테이블을 사용하는 코드 샘플에서는 데이터가 **Production.Products** 테이블에서 이러한 샘플 테이블 중 하나로 추가됩니다.  **BulkCopyDemoDifferentColumns** 테이블은 샘플에서 원본 데이터의 열을 대상 테이블로 매핑하는 방법을 설명하는 경우에 사용하며 **BulkCopyDemoMatchingColumns**는 대부분의 다른 샘플에 사용됩니다.  
  
 일부 코드 샘플에서는 <xref:System.Data.SqlClient.SqlBulkCopy> 클래스 하나로 여러 테이블에 쓰는 방법을 보여 줍니다.  이러한 샘플에서는 **BulkCopyDemoOrderHeader** 및 **BulkCopyDemoOrderDetail** 테이블을 대상 테이블로 사용합니다.  이러한 테이블은 **AdventureWorks**의 **Sales.SalesOrderHeader** 및 **Sales.SalesOrderDetail** 테이블을 기반으로 합니다.  
  
> [!NOTE]
>  **SqlBulkCopy** 코드 샘플은 **SqlBulkCopy**를 사용하는 구문을 보여 주기 위한 용도로만 제공됩니다.  소스 테이블과 대상 테이블이 동일한 SQL Server 인스턴스에 있으면 Transact\-SQL `INSERT   SELECT` 문을 사용하여 데이터를 더 쉽고 빠르게 복사할 수 있습니다.  
  
## 테이블 설정  
 코드 샘플을 올바르게 실행하는 데 필요한 테이블을 만들려면 SQL Server 데이터베이스에서 다음 Transact\-SQL 문을 실행해야 합니다.  
  
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
  
## 참고 항목  
 [SQL Server에서의 대량 복사 작업](../../../../../docs/framework/data/adonet/sql/bulk-copy-operations-in-sql-server.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)