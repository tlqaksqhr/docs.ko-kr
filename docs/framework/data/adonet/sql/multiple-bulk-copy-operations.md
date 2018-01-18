---
title: "여러 개의 대량 복사 작업"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 5ad12f94-7459-4a93-a421-4160d1a90715
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 8a753357719f451ce7acc2d7f42c0493ca2357ab
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="multiple-bulk-copy-operations"></a><span data-ttu-id="84559-102">여러 개의 대량 복사 작업</span><span class="sxs-lookup"><span data-stu-id="84559-102">Multiple Bulk Copy Operations</span></span>
<span data-ttu-id="84559-103"><xref:System.Data.SqlClient.SqlBulkCopy> 클래스의 단일 인스턴스를 사용하여 여러 대량 복사 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84559-103">You can perform multiple bulk copy operations using a single instance of a <xref:System.Data.SqlClient.SqlBulkCopy> class.</span></span> <span data-ttu-id="84559-104">작업 매개 변수 (예를 들어 대상 테이블의 이름) 복사본 간에 변경 하는 경우의 후속 호출 전에 업데이트 해야 하는 **WriteToServer** 메서드를 다음 예제와 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="84559-104">If the operation parameters change between copies (for example, the name of the destination table), you must update them prior to any subsequent calls to any of the **WriteToServer** methods, as demonstrated in the following example.</span></span> <span data-ttu-id="84559-105">명시적으로 변경하지 않는 한 모든 속성 값은 지정된 인스턴스에 대한 이전의 대량 복사 작업과 동일하게 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="84559-105">Unless explicitly changed, all property values remain the same as they were on the previous bulk copy operation for a given instance.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="84559-106"><xref:System.Data.SqlClient.SqlBulkCopy>의 단일 인스턴스를 사용하여 여러 대량 복사 작업을 수행하는 것은 작업마다 별도의 인스턴스를 사용하는 방법보다 대개 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="84559-106">Performing multiple bulk copy operations using the same instance of <xref:System.Data.SqlClient.SqlBulkCopy> is usually more efficient than using a separate instance for each operation.</span></span>  
  
 <span data-ttu-id="84559-107">동일한 <xref:System.Data.SqlClient.SqlBulkCopy> 개체를 사용하여 여러 대량 복사 작업을 수행하는 경우 각 작업에서 소스 또는 대상 정보가 동일한지 여부에 대한 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="84559-107">If you perform several bulk copy operations using the same <xref:System.Data.SqlClient.SqlBulkCopy> object, there are no restrictions on whether source or target information is equal or different in each operation.</span></span> <span data-ttu-id="84559-108">그러나 열 연결 정보는 서버에 쓸 때마다 올바르게 설정되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84559-108">However, you must ensure that column association information is properly set each time you write to the server.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="84559-109">이 샘플을 만들지 않은 경우 작업 테이블에 설명 된 대로 실행 되지 것입니다 [대량 복사 예제 설정](../../../../../docs/framework/data/adonet/sql/bulk-copy-example-setup.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="84559-109">This sample will not run unless you have created the work tables as described in [Bulk Copy Example Setup](../../../../../docs/framework/data/adonet/sql/bulk-copy-example-setup.md).</span></span> <span data-ttu-id="84559-110">이 코드는 사용 하는 구문을 보여 주기 위해 제공 됩니다 **SqlBulkCopy** 만 합니다.</span><span class="sxs-lookup"><span data-stu-id="84559-110">This code is provided to demonstrate the syntax for using **SqlBulkCopy** only.</span></span> <span data-ttu-id="84559-111">소스 테이블과 대상 테이블이 동일한 SQL Server 인스턴스에 있으면 Transact-SQL `INSERT … SELECT` 문을 사용하여 데이터를 더 쉽고 빠르게 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84559-111">If the source and destination tables are located in the same SQL Server instance, it is easier and faster to use a Transact-SQL `INSERT … SELECT` statement to copy the data.</span></span>  
  
 [!code-csharp[DataWorks SqlBulkCopy.ColumnMappingOrdersDetails#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.ColumnMappingOrdersDetails/CS/source.cs#1)]
 [!code-vb[DataWorks SqlBulkCopy.ColumnMappingOrdersDetails#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.ColumnMappingOrdersDetails/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="84559-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="84559-112">See Also</span></span>  
 [<span data-ttu-id="84559-113">SQL Server에서 대량 복사 작업</span><span class="sxs-lookup"><span data-stu-id="84559-113">Bulk Copy Operations in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/bulk-copy-operations-in-sql-server.md)  
 [<span data-ttu-id="84559-114">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="84559-114">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
