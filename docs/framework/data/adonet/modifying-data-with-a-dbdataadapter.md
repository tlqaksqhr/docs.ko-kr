---
title: "DbDataAdapter로 데이터 수정"
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
ms.assetid: e35c7f9e-648b-4fcc-9361-d365c3e42c9a
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 0834e23c4530e2800eae0d0088b6701d02dd2a1a
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="modifying-data-with-a-dbdataadapter"></a><span data-ttu-id="40e75-102">DbDataAdapter로 데이터 수정</span><span class="sxs-lookup"><span data-stu-id="40e75-102">Modifying Data with a DbDataAdapter</span></span>
<span data-ttu-id="40e75-103"><xref:System.Data.Common.DbProviderFactory.CreateDataAdapter%2A> 개체의 <xref:System.Data.Common.DbProviderFactory> 메서드를 사용하면 팩터리를 만들 때 지정한 기본 데이터 공급자에 대해 강력한 형식의 <xref:System.Data.Common.DbDataAdapter> 개체를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40e75-103">The <xref:System.Data.Common.DbProviderFactory.CreateDataAdapter%2A> method of a <xref:System.Data.Common.DbProviderFactory> object gives you a <xref:System.Data.Common.DbDataAdapter> object that is strongly typed to the underlying data provider specified at the time you create the factory.</span></span> <span data-ttu-id="40e75-104">그런 다음 <xref:System.Data.Common.DbCommandBuilder>를 사용하여 데이터를 <xref:System.Data.DataSet>에서 데이터 소스로 삽입하고, 업데이트하고, 삭제하는 명령을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40e75-104">You can then use a <xref:System.Data.Common.DbCommandBuilder> to create commands to insert, update, and delete data from a <xref:System.Data.DataSet> to a data source.</span></span>  
  
## <a name="retrieving-data-with-a-dbdataadapter"></a><span data-ttu-id="40e75-105">DbDataAdapter를 사용하여 데이터 검색</span><span class="sxs-lookup"><span data-stu-id="40e75-105">Retrieving Data with a DbDataAdapter</span></span>  
 <span data-ttu-id="40e75-106">이 예제에서는 공급자 이름과 연결 문자열을 기반으로 강력한 형식의 `DbDataAdapter`를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="40e75-106">This example demonstrates how to create a strongly typed `DbDataAdapter` based on a provider name and connection string.</span></span> <span data-ttu-id="40e75-107">이 코드에서는 <xref:System.Data.Common.DbProviderFactory.CreateConnection%2A>의 <xref:System.Data.Common.DbProviderFactory> 메서드를 사용하여 <xref:System.Data.Common.DbConnection>을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="40e75-107">The code uses the <xref:System.Data.Common.DbProviderFactory.CreateConnection%2A> method of the <xref:System.Data.Common.DbProviderFactory> to create a <xref:System.Data.Common.DbConnection>.</span></span> <span data-ttu-id="40e75-108">그런 다음 <xref:System.Data.Common.DbProviderFactory.CreateCommand%2A> 메서드를 사용하고 <xref:System.Data.Common.DbCommand> 및 `CommandText` 속성을 설정하여 데이터를 선택하기 위한 `Connection`를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="40e75-108">Next, the code uses the <xref:System.Data.Common.DbProviderFactory.CreateCommand%2A> method to create a <xref:System.Data.Common.DbCommand> to select data by setting its `CommandText` and `Connection` properties.</span></span> <span data-ttu-id="40e75-109">마지막으로, <xref:System.Data.Common.DbDataAdapter> 메서드를 사용하여 <xref:System.Data.Common.DbProviderFactory.CreateDataAdapter%2A> 개체를 만들고 해당 `SelectCommand` 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="40e75-109">Finally, the code creates a <xref:System.Data.Common.DbDataAdapter> object using the <xref:System.Data.Common.DbProviderFactory.CreateDataAdapter%2A> method and sets its `SelectCommand` property.</span></span> <span data-ttu-id="40e75-110">`Fill`의 `DbDataAdapter` 메서드는 데이터를 <xref:System.Data.DataTable>로 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="40e75-110">The `Fill` method of the `DbDataAdapter` loads the data into a <xref:System.Data.DataTable>.</span></span>  
  
 [!code-csharp[DataWorks DbProviderFactories.DbDataAdapter#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.DbDataAdapter/CS/source.cs#1)]
 [!code-vb[DataWorks DbProviderFactories.DbDataAdapter#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.DbDataAdapter/VB/source.vb#1)]  
  
## <a name="modifying-data-with-a-dbdataadapter"></a><span data-ttu-id="40e75-111">DbDataAdapter로 데이터 수정</span><span class="sxs-lookup"><span data-stu-id="40e75-111">Modifying Data with a DbDataAdapter</span></span>  
 <span data-ttu-id="40e75-112">이 예제에서는 `DataTable`를 사용하여 데이터 소스의 데이터를 업데이트하는 데 필요한 명령을 생성함으로써 <xref:System.Data.Common.DbDataAdapter>를 사용하여 <xref:System.Data.Common.DbCommandBuilder>의 데이터를 수정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="40e75-112">This example demonstrates how to modify data in a `DataTable` using a <xref:System.Data.Common.DbDataAdapter> by using a <xref:System.Data.Common.DbCommandBuilder> to generate the commands required for updating data at the data source.</span></span> <span data-ttu-id="40e75-113"><xref:System.Data.Common.DbDataAdapter.SelectCommand%2A>의 `DbDataAdapter`를 설정하여 Customers 테이블에서 CustomerID 및 CompanyName을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="40e75-113">The <xref:System.Data.Common.DbDataAdapter.SelectCommand%2A> of the `DbDataAdapter` is set to retrieve the CustomerID and CompanyName from the Customers table.</span></span> <span data-ttu-id="40e75-114"><xref:System.Data.Common.DbCommandBuilder.GetInsertCommand%2A> 메서드는 <xref:System.Data.Common.DbDataAdapter.InsertCommand%2A> 속성을 설정하는 데 사용되고, <xref:System.Data.Common.DbCommandBuilder.GetUpdateCommand%2A> 메서드는 <xref:System.Data.Common.DbDataAdapter.UpdateCommand%2A> 속성을 설정하는 데 사용되고, <xref:System.Data.Common.DbCommandBuilder.GetDeleteCommand%2A> 메서드는 <xref:System.Data.Common.DbDataAdapter.DeleteCommand%2A> 속성을 설정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="40e75-114">The <xref:System.Data.Common.DbCommandBuilder.GetInsertCommand%2A> method is used to set the <xref:System.Data.Common.DbDataAdapter.InsertCommand%2A> property, the <xref:System.Data.Common.DbCommandBuilder.GetUpdateCommand%2A> method is used to set the <xref:System.Data.Common.DbDataAdapter.UpdateCommand%2A> property, and the <xref:System.Data.Common.DbCommandBuilder.GetDeleteCommand%2A> method is used to set the <xref:System.Data.Common.DbDataAdapter.DeleteCommand%2A> property.</span></span> <span data-ttu-id="40e75-115">코드에서는 Customers 테이블에 새 행을 추가하고 데이터 소스를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="40e75-115">The code adds a new row to the Customers table and updates the data source.</span></span> <span data-ttu-id="40e75-116">그런 다음 Customers 테이블에 대해 정의된 기본 키인 CustomerID를 검색하여 추가된 행을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="40e75-116">The code then locates the added row by searching on the CustomerID, which is the primary key defined for the Customers table.</span></span> <span data-ttu-id="40e75-117">그런 후 CompanyName을 변경하고 데이터 소스를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="40e75-117">It changes the CompanyName and updates the data source.</span></span> <span data-ttu-id="40e75-118">마지막으로 행을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="40e75-118">Finally, the code deletes the row.</span></span>  
  
 [!code-csharp[DataWorks DbProviderFactories.DbDataAdapterModify#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.DbDataAdapterModify/CS/source.cs#1)]
 [!code-vb[DataWorks DbProviderFactories.DbDataAdapterModify#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.DbDataAdapterModify/VB/source.vb#1)]  
  
## <a name="handling-parameters"></a><span data-ttu-id="40e75-119">매개 변수 처리</span><span class="sxs-lookup"><span data-stu-id="40e75-119">Handling Parameters</span></span>  
 <span data-ttu-id="40e75-120">.NET Framework 데이터 공급자는 매개 변수와 매개 변수 자리 표시자를 다르게 지정하여 명명 작업을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="40e75-120">The .NET Framework data providers handle naming and specifying parameters and parameter placeholders differently.</span></span> <span data-ttu-id="40e75-121">이 구문은 다음 표에서 설명하는 것과 같이 특정 데이터 소스에 맞게 수정됩니다.</span><span class="sxs-lookup"><span data-stu-id="40e75-121">This syntax is tailored to a specific data source, as described in the following table.</span></span>  
  
|<span data-ttu-id="40e75-122">데이터 공급자</span><span class="sxs-lookup"><span data-stu-id="40e75-122">Data provider</span></span>|<span data-ttu-id="40e75-123">매개 변수 명명 구문</span><span class="sxs-lookup"><span data-stu-id="40e75-123">Parameter naming syntax</span></span>|  
|-------------------|-----------------------------|  
|`SqlClient`|<span data-ttu-id="40e75-124">`@`*parametername*형식의 명명된 매개 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="40e75-124">Uses named parameters in the format `@`*parametername*.</span></span>|  
|`OracleClient`|<span data-ttu-id="40e75-125">`:`*parmname* (또는 *parmname*) 형식의 명명된 매개 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="40e75-125">Uses named parameters in the format `:`*parmname* (or *parmname*).</span></span>|  
|`OleDb`|<span data-ttu-id="40e75-126">물음표(`?`)로 표시된 위치 매개 변수 마커를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="40e75-126">Uses positional parameter markers indicated by a question mark (`?`).</span></span>|  
|`Odbc`|<span data-ttu-id="40e75-127">물음표(`?`)로 표시된 위치 매개 변수 마커를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="40e75-127">Uses positional parameter markers indicated by a question mark (`?`).</span></span>|  
  
 <span data-ttu-id="40e75-128">팩터리 모델은 매개 변수화된 `DbCommand` 및 `DbDataAdapter` 개체를 만들 때는 유용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="40e75-128">The factory model is not helpful for creating parameterized `DbCommand` and `DbDataAdapter` objects.</span></span> <span data-ttu-id="40e75-129">코드에서 분기하여 데이터 공급자에 맞는 매개 변수를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="40e75-129">You will need to branch in your code to create parameters that are tailored to your data provider.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="40e75-130">문자열 연결을 사용하여 직접 SQL 문을 구성함으로써 공급자 특정 매개 변수를 사용하지 않는 것은 보안상 권장하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="40e75-130">Avoiding provider-specific parameters altogether by using string concatenation to construct direct SQL statements is not recommended for security reasons.</span></span> <span data-ttu-id="40e75-131">매개 변수 대신 문자열 연결을 사용하면 응용 프로그램이 SQL 삽입 공격에 취약해집니다.</span><span class="sxs-lookup"><span data-stu-id="40e75-131">Using string concatenation instead of parameters leaves your application vulnerable to SQL injection attacks.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40e75-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="40e75-132">See Also</span></span>  
 [<span data-ttu-id="40e75-133">DbProviderFactory</span><span class="sxs-lookup"><span data-stu-id="40e75-133">DbProviderFactories</span></span>](../../../../docs/framework/data/adonet/dbproviderfactories.md)  
 [<span data-ttu-id="40e75-134">DbProviderFactory 가져오기</span><span class="sxs-lookup"><span data-stu-id="40e75-134">Obtaining a DbProviderFactory</span></span>](../../../../docs/framework/data/adonet/obtaining-a-dbproviderfactory.md)  
 [<span data-ttu-id="40e75-135">DbConnection, DbCommand 및 DbException</span><span class="sxs-lookup"><span data-stu-id="40e75-135">DbConnection, DbCommand and DbException</span></span>](../../../../docs/framework/data/adonet/dbconnection-dbcommand-and-dbexception.md)  
 [<span data-ttu-id="40e75-136">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="40e75-136">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
