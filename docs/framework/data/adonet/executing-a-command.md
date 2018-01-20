---
title: "명령 실행"
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
ms.assetid: 40494916-c25a-4cb8-8f7c-fcb8d378464e
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: c4879c49a410dfb40999f3163d8b23158cb71f0e
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="executing-a-command"></a><span data-ttu-id="07120-102">명령 실행</span><span class="sxs-lookup"><span data-stu-id="07120-102">Executing a Command</span></span>
<span data-ttu-id="07120-103">.NET Framework에 포함된 각 .NET Framework 데이터 공급자에는 <xref:System.Data.Common.DbCommand>에서 상속되는 고유 명령 개체가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07120-103">Each .NET Framework data provider included with the .NET Framework has its own command object that inherits from <xref:System.Data.Common.DbCommand>.</span></span> <span data-ttu-id="07120-104">.NET Framework Data Provider for OLE DB에는 <xref:System.Data.OleDb.OleDbCommand> 개체가 있고, .NET Framework Data Provider for SQL Server에는 <xref:System.Data.SqlClient.SqlCommand> 개체가 있으며, .NET Framework Data Provider for ODBC와 .NET Framework Data Provider for Oracle에는 각각 <xref:System.Data.Odbc.OdbcCommand> 개체와 <xref:System.Data.OracleClient.OracleCommand> 개체가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07120-104">The .NET Framework Data Provider for OLE DB includes an <xref:System.Data.OleDb.OleDbCommand> object, the .NET Framework Data Provider for SQL Server includes a <xref:System.Data.SqlClient.SqlCommand> object, the .NET Framework Data Provider for ODBC includes an <xref:System.Data.Odbc.OdbcCommand> object, and the .NET Framework Data Provider for Oracle includes an <xref:System.Data.OracleClient.OracleCommand> object.</span></span> <span data-ttu-id="07120-105">이러한 각 개체는 명령의 유형 및 원하는 반환 값을 기준으로 명령 실행을 위한 메서드를 노출합니다. 다음 표에는 이러한 명령 및 해당 반환 값이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07120-105">Each of these objects exposes methods for executing commands based on the type of command and desired return value, as described in the following table.</span></span>  
  
|<span data-ttu-id="07120-106">명령</span><span class="sxs-lookup"><span data-stu-id="07120-106">Command</span></span>|<span data-ttu-id="07120-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="07120-107">Return Value</span></span>|  
|-------------|------------------|  
|`ExecuteReader`|<span data-ttu-id="07120-108">`DataReader` 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="07120-108">Returns a `DataReader` object.</span></span>|  
|`ExecuteScalar`|<span data-ttu-id="07120-109">단일 스칼라 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="07120-109">Returns a single scalar value.</span></span>|  
|`ExecuteNonQuery`|<span data-ttu-id="07120-110">어떠한 행도 반환하지 않는 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="07120-110">Executes a command that does not return any rows.</span></span>|  
|`ExecuteXMLReader`|<span data-ttu-id="07120-111"><xref:System.Xml.XmlReader>를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="07120-111">Returns an <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="07120-112">`SqlCommand` 개체에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07120-112">Available for a `SqlCommand` object only.</span></span>|  
  
 <span data-ttu-id="07120-113">강력한 형식의 각 명령 개체는 명령 문자열의 해석 방법을 지정하는 <xref:System.Data.CommandType> 열거형도 지원합니다. 다음 표에는 CommandType의 각 열거형이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07120-113">Each strongly typed command object also supports a <xref:System.Data.CommandType> enumeration that specifies how a command string is interpreted, as described in the following table.</span></span>  
  
|<span data-ttu-id="07120-114">CommandType</span><span class="sxs-lookup"><span data-stu-id="07120-114">CommandType</span></span>|<span data-ttu-id="07120-115">설명</span><span class="sxs-lookup"><span data-stu-id="07120-115">Description</span></span>|  
|-----------------|-----------------|  
|`Text`|<span data-ttu-id="07120-116">데이터 소스에 실행할 문을 정의하는 SQL 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="07120-116">An SQL command defining the statements to be executed at the data source.</span></span>|  
|`StoredProcedure`|<span data-ttu-id="07120-117">저장 프로시저의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="07120-117">The name of the stored procedure.</span></span> <span data-ttu-id="07120-118">호출하는 `Parameters` 메서드에 관계없이 명령의 `Execute` 속성을 사용하면 입력 및 출력 매개 변수와 반환 값에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07120-118">You can use the `Parameters` property of a command to access input and output parameters and return values, regardless of which `Execute` method is called.</span></span> <span data-ttu-id="07120-119">`ExecuteReader`를 사용하는 경우 `DataReader`가 닫히기 전에는 반환 값과 출력 매개 변수에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="07120-119">When using `ExecuteReader`, return values and output parameters will not be accessible until the `DataReader` is closed.</span></span>|  
|`TableDirect`|<span data-ttu-id="07120-120">테이블의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="07120-120">The name of a table.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="07120-121">예제</span><span class="sxs-lookup"><span data-stu-id="07120-121">Example</span></span>  
 <span data-ttu-id="07120-122">다음 코드 예제에서는 <xref:System.Data.SqlClient.SqlCommand> 개체를 만든 다음 해당 속성을 설정하여 저장 프로시저를 실행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="07120-122">The following code example demonstrates how to create a <xref:System.Data.SqlClient.SqlCommand> object to execute a stored procedure by setting its properties.</span></span> <span data-ttu-id="07120-123">저장 프로시저에 대한 입력 매개 변수를 지정하는 데는 <xref:System.Data.SqlClient.SqlParameter> 개체를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="07120-123">A <xref:System.Data.SqlClient.SqlParameter> object is used to specify the input parameter to the stored procedure.</span></span> <span data-ttu-id="07120-124"><xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> 메서드를 사용하여 명령을 실행하고 <xref:System.Data.SqlClient.SqlDataReader>의 출력을 콘솔 창에 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="07120-124">The command is executed using the <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> method, and the output from the <xref:System.Data.SqlClient.SqlDataReader> is displayed in the console window.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.StoredProcedure#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.StoredProcedure/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.StoredProcedure#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.StoredProcedure/VB/source.vb#1)]  
  
### <a name="troubleshooting-commands"></a><span data-ttu-id="07120-125">명령 문제 해결</span><span class="sxs-lookup"><span data-stu-id="07120-125">Troubleshooting Commands</span></span>  
 <span data-ttu-id="07120-126">.NET Framework Data Provider for SQL Server는 실패한 명령 실행과 관련된 간헐적인 문제를 감지할 수 있도록 성능 카운터를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="07120-126">The .NET Framework Data Provider for SQL Server adds performance counters to enable you to detect intermittent problems related to failed command executions.</span></span> <span data-ttu-id="07120-127">자세한 내용은 참조 [÷ ´ ֹ](../../../../docs/framework/data/adonet/performance-counters.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="07120-127">For more information see [Performance Counters](../../../../docs/framework/data/adonet/performance-counters.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07120-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="07120-128">See Also</span></span>  
 [<span data-ttu-id="07120-129">명령 및 매개 변수</span><span class="sxs-lookup"><span data-stu-id="07120-129">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [<span data-ttu-id="07120-130">DataAdapter 및 DataReader</span><span class="sxs-lookup"><span data-stu-id="07120-130">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [<span data-ttu-id="07120-131">DataReaders 작업</span><span class="sxs-lookup"><span data-stu-id="07120-131">Working with DataReaders</span></span>](http://msdn.microsoft.com/library/126a966a-d08d-4d22-a19f-f432908b2b54)  
 [<span data-ttu-id="07120-132">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="07120-132">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
