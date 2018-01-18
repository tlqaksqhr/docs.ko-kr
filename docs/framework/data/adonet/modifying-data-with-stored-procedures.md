---
title: "저장 프로시저로 데이터 수정"
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
ms.assetid: 7d8e9a46-1af6-4a02-bf61-969d77ae07e0
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: dbc928e70ee7762b494d7efe60bc52b9f9783013
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="modifying-data-with-stored-procedures"></a><span data-ttu-id="d7f7a-102">저장 프로시저로 데이터 수정</span><span class="sxs-lookup"><span data-stu-id="d7f7a-102">Modifying Data with Stored Procedures</span></span>
<span data-ttu-id="d7f7a-103">저장 프로시저는 입력 매개 변수로 데이터를 받아들이고 출력 매개 변수, 결과 집합 또는 반환 값으로 데이터를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7f7a-103">Stored procedures can accept data as input parameters and can return data as output parameters, result sets, or return values.</span></span> <span data-ttu-id="d7f7a-104">다음 샘플에서는 ADO.NET에서 입력 매개 변수, 출력 매개 변수 및 반환 값을 보내고 받는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d7f7a-104">The sample below illustrates how ADO.NET sends and receives input parameters, output parameters, and return values.</span></span> <span data-ttu-id="d7f7a-105">이 예제에서는 기본 키 열이 SQL Server 데이터베이스의 ID 열인 테이블에 새 레코드를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="d7f7a-105">The example inserts a new record into a table where the primary key column is an identity column in a SQL Server database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d7f7a-106">SQL Server 저장 프로시저를 통해 <xref:System.Data.SqlClient.SqlDataAdapter>로 데이터를 편집하거나 삭제하는 경우에는 저장 프로시저 정의에 SET NOCOUNT ON을 사용하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7f7a-106">If you are using SQL Server stored procedures to edit or delete data using a <xref:System.Data.SqlClient.SqlDataAdapter>, make sure that you do not use SET NOCOUNT ON in the stored procedure definition.</span></span> <span data-ttu-id="d7f7a-107">SET NOCOUNT ON을 사용하는 경우 반환되는 행 개수가 0이 되어 `DataAdapter`가 이를 동시성 충돌로 인식합니다.</span><span class="sxs-lookup"><span data-stu-id="d7f7a-107">This causes the rows affected count returned to be zero, which the `DataAdapter` interprets as a concurrency conflict.</span></span> <span data-ttu-id="d7f7a-108">그 결과 <xref:System.Data.DBConcurrencyException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7f7a-108">In this event, a <xref:System.Data.DBConcurrencyException> will be thrown.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7f7a-109">예</span><span class="sxs-lookup"><span data-stu-id="d7f7a-109">Example</span></span>  
 <span data-ttu-id="d7f7a-110">샘플에 새 범주를 삽입 하는 다음 저장된 프로시저를 사용 하 여 **Northwind** **범주** 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="d7f7a-110">The sample uses the following stored procedure to insert a new category into the **Northwind** **Categories** table.</span></span> <span data-ttu-id="d7f7a-111">저장된 프로시저의 값을 가져와 **CategoryName** id 필드의 새 값을 검색 하는 입력된 매개 변수 및 scope_identity () 사용 하 여 열 함수 **CategoryID**, 반환 출력 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="d7f7a-111">The stored procedure takes the value in the **CategoryName** column as an input parameter and uses the SCOPE_IDENTITY() function to retrieve the new value of the identity field, **CategoryID**, and return it in an output parameter.</span></span> <span data-ttu-id="d7f7a-112">RETURN 문을 사용 하는 @@ROWCOUNT 삽입 된 행의 수를 반환 하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="d7f7a-112">The RETURN statement uses the @@ROWCOUNT function to return the number of rows inserted.</span></span>  
  
```  
CREATE PROCEDURE dbo.InsertCategory  
  @CategoryName nvarchar(15),  
  @Identity int OUT  
AS  
INSERT INTO Categories (CategoryName) VALUES(@CategoryName)  
SET @Identity = SCOPE_IDENTITY()  
RETURN @@ROWCOUNT  
```  
  
 <span data-ttu-id="d7f7a-113">다음 코드 예제에서는 위의 `InsertCategory` 저장 프로시저를 <xref:System.Data.SqlClient.SqlDataAdapter.InsertCommand%2A>의 <xref:System.Data.SqlClient.SqlDataAdapter>에 대한 소스로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d7f7a-113">The following code example uses the `InsertCategory` stored procedure shown above as the source for the <xref:System.Data.SqlClient.SqlDataAdapter.InsertCommand%2A> of the <xref:System.Data.SqlClient.SqlDataAdapter>.</span></span> <span data-ttu-id="d7f7a-114">`@Identity`의 <xref:System.Data.DataSet> 메서드를 호출하면 데이터베이스에 레코드가 삽입된 후 `Update` 출력 매개 변수가 <xref:System.Data.SqlClient.SqlDataAdapter>에 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7f7a-114">The `@Identity` output parameter will be reflected in the <xref:System.Data.DataSet> after the record has been inserted into the database when the `Update` method of the <xref:System.Data.SqlClient.SqlDataAdapter> is called.</span></span> <span data-ttu-id="d7f7a-115">이 코드는 반환 값도 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="d7f7a-115">The code also retrieves the return value.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d7f7a-116">사용 하는 경우는 <xref:System.Data.OleDb.OleDbDataAdapter>, 매개 변수를 지정 해야 합니다는 <xref:System.Data.ParameterDirection> 의 **ReturnValue** 다른 매개 변수 앞입니다.</span><span class="sxs-lookup"><span data-stu-id="d7f7a-116">When using the <xref:System.Data.OleDb.OleDbDataAdapter>, you must specify parameters with a <xref:System.Data.ParameterDirection> of **ReturnValue** before the other parameters.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.SprocIdentityReturn#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.SprocIdentityReturn/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.SprocIdentityReturn#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.SprocIdentityReturn/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="d7f7a-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d7f7a-117">See Also</span></span>  
 [<span data-ttu-id="d7f7a-118">ADO.NET에서 데이터 검색 및 수정</span><span class="sxs-lookup"><span data-stu-id="d7f7a-118">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="d7f7a-119">DataAdapter 및 DataReader</span><span class="sxs-lookup"><span data-stu-id="d7f7a-119">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [<span data-ttu-id="d7f7a-120">명령 실행</span><span class="sxs-lookup"><span data-stu-id="d7f7a-120">Executing a Command</span></span>](../../../../docs/framework/data/adonet/executing-a-command.md)  
 [<span data-ttu-id="d7f7a-121">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="d7f7a-121">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
