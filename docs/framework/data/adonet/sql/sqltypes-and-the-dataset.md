---
title: "SqlType 및 DataSet"
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
ms.assetid: 9172c20a-9876-4b3b-9c97-1963c02b1993
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 86132e266b4421cce048ea38fc91967267a6ae6c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="sqltypes-and-the-dataset"></a><span data-ttu-id="bf25f-102">SqlType 및 DataSet</span><span class="sxs-lookup"><span data-stu-id="bf25f-102">SqlTypes and the DataSet</span></span>
<span data-ttu-id="bf25f-103">ADO.NET 2.0에서는 `DataSet` 네임스페이스를 통해 <xref:System.Data.SqlTypes>에 대한 형식 지원이 향상되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bf25f-103">ADO.NET 2.0 introduced enhanced type support for the `DataSet` through the  <xref:System.Data.SqlTypes> namespace.</span></span> <span data-ttu-id="bf25f-104"><xref:System.Data.SqlTypes>의 형식은 SQL Server 데이터베이스의 데이터 형식과 의미 체계 및 정밀도가 동일한 데이터 형식을 제공하도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bf25f-104">The types in <xref:System.Data.SqlTypes> are designed to provide data types with the same semantics and precision as the data types in a SQL Server database.</span></span> <span data-ttu-id="bf25f-105"><xref:System.Data.SqlTypes>의 각 데이터 형식은 SQL Server의 데이터 형식과 동일하며 기본 데이터 표현도 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bf25f-105">Each data type in <xref:System.Data.SqlTypes> has an equivalent data type in SQL Server, with the same underlying data representation.</span></span>  
  
 <span data-ttu-id="bf25f-106"><xref:System.Data.SqlTypes>에 <xref:System.Data.DataSet>를 직접 사용하면 SQL Server 데이터 형식으로 작업할 때 몇 가지 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf25f-106">Using <xref:System.Data.SqlTypes> directly in a <xref:System.Data.DataSet> confers several benefits when working with SQL Server data types.</span></span> <span data-ttu-id="bf25f-107">우선 <xref:System.Data.SqlTypes>는 SQL Server 기본 데이터 형식과 동일한 의미 체계를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="bf25f-107"><xref:System.Data.SqlTypes> supports the same semantics as SQL Server native data types.</span></span> <span data-ttu-id="bf25f-108"><xref:System.Data.SqlTypes> 정의에 <xref:System.Data.DataColumn> 중 하나를 지정하면 decimal 또는 숫자 데이터 형식을 CLR(공용 언어 런타임) 데이터 형식 중 하나로 변환할 때 발생할 수 있는 전체 자릿수 손실을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf25f-108">Specifying one of the <xref:System.Data.SqlTypes> in the definition of a <xref:System.Data.DataColumn> eliminates the loss of precision that can occur when converting decimal or numeric data types to one of the common language runtime (CLR) data types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bf25f-109">예제</span><span class="sxs-lookup"><span data-stu-id="bf25f-109">Example</span></span>  
 <span data-ttu-id="bf25f-110">다음 예제에서는 <xref:System.Data.DataTable> 개체를 만들고 CLR 형식 대신 <xref:System.Data.DataColumn>를 사용하여 <xref:System.Data.SqlTypes> 데이터 형식을 명시적으로 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="bf25f-110">The following example creates a <xref:System.Data.DataTable> object, explicitly defining the <xref:System.Data.DataColumn> data types by using <xref:System.Data.SqlTypes> instead of CLR types.</span></span> <span data-ttu-id="bf25f-111">이 코드는 SQL Server의 AdventureWorks 데이터베이스에 있는 Sales.SalesOrderDetail 테이블의 데이터로 <xref:System.Data.DataTable>을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="bf25f-111">The code fills the <xref:System.Data.DataTable> with data from the Sales.SalesOrderDetail table in the AdventureWorks database in SQL Server.</span></span> <span data-ttu-id="bf25f-112">콘솔 창에 표시된 출력은 각 열의 데이터 형식과 SQL Server에서 검색한 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="bf25f-112">The output displayed in the console window shows the data type of each column, and the values retrieved from SQL Server.</span></span>  
  
 [!code-csharp[DataWorks SqlTypes.GetTypeAW#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlTypes.GetTypeAW/CS/source.cs#1)]
 [!code-vb[DataWorks SqlTypes.GetTypeAW#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlTypes.GetTypeAW/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="bf25f-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bf25f-113">See Also</span></span>  
 [<span data-ttu-id="bf25f-114">SQL Server 데이터 형식 매핑</span><span class="sxs-lookup"><span data-stu-id="bf25f-114">SQL Server Data Type Mappings</span></span>](../../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md)  
 [<span data-ttu-id="bf25f-115">매개 변수 및 매개 변수 데이터 형식 구성</span><span class="sxs-lookup"><span data-stu-id="bf25f-115">Configuring Parameters and Parameter Data Types</span></span>](../../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)  
 [<span data-ttu-id="bf25f-116">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="bf25f-116">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
