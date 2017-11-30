---
title: "샘플 공급자의 SQL 생성"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e70f553d-4622-4627-928e-1aa2ee605d8e
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 58a49f7bf5d385466810a3c59bda748ef66d5840
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="sql-generation-in-the-sample-provider"></a><span data-ttu-id="d724e-102">샘플 공급자의 SQL 생성</span><span class="sxs-lookup"><span data-stu-id="d724e-102">SQL Generation in the Sample Provider</span></span>
<span data-ttu-id="d724e-103">[Entity Framework 샘플 공급자](http://go.microsoft.com/fwlink/?LinkId=180616) 새 구성 요소가 지 원하는 ADO.NET 데이터 공급자는 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="d724e-103">The [Entity Framework Sample Provider](http://go.microsoft.com/fwlink/?LinkId=180616) demonstrates the new components of ADO.NET Data Providers that support the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span>  <span data-ttu-id="d724e-104">샘플 공급자는 SQL Server 2005 데이터베이스와 작동하며 System.Data.SqlClient ADO.NET 2.0 데이터 공급자에 대한 래퍼로 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="d724e-104">It works with a SQL Server 2005 database and is implemented as a wrapper for the System.Data.SqlClient ADO.NET 2.0 Data Provider.</span></span>  
  
 <span data-ttu-id="d724e-105">샘플 공급자의 SQL 생성 모듈(DmlSqlGenerator.cs 파일을 제외하고 SQL Generation 폴더에 있음)은 DbQueryCommandTree 입력을 사용하고 단일 SQL SELECT 문을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d724e-105">The SQL Generation module of the Sample Provider (located under the SQL Generation folder, except for the file DmlSqlGenerator.cs) takes an input DbQueryCommandTree and produces a single SQL SELECT statement.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d724e-106">단원 내용</span><span class="sxs-lookup"><span data-stu-id="d724e-106">In This Section</span></span>  
 <span data-ttu-id="d724e-107">이 단원에 포함된 항목은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d724e-107">This section includes the following topics:</span></span>  
  
 [<span data-ttu-id="d724e-108">아키텍처 및 디자인</span><span class="sxs-lookup"><span data-stu-id="d724e-108">Architecture and Design</span></span>](../../../../../docs/framework/data/adonet/ef/architecture-and-design.md)  
  
 [<span data-ttu-id="d724e-109">연습: SQL 생성</span><span class="sxs-lookup"><span data-stu-id="d724e-109">Walkthrough: SQL Generation</span></span>](../../../../../docs/framework/data/adonet/ef/walkthrough-sql-generation.md)  
  
## <a name="see-also"></a><span data-ttu-id="d724e-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d724e-110">See Also</span></span>  
 [<span data-ttu-id="d724e-111">SQL 생성</span><span class="sxs-lookup"><span data-stu-id="d724e-111">SQL Generation</span></span>](../../../../../docs/framework/data/adonet/ef/sql-generation.md)
