---
title: 데이터 원본에 연결(ADO.NET)
ms.date: 03/30/2017
ms.assetid: 9abc3f92-1be3-4e1a-b360-762dc689650e
ms.openlocfilehash: 27653c3e1f14e08fc8b5e1225a441072778a0cc8
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32757114"
---
# <a name="connecting-to-a-data-source-in-adonet"></a><span data-ttu-id="0945d-102">데이터 원본에 연결(ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="0945d-102">Connecting to a Data Source in ADO.NET</span></span>
<span data-ttu-id="0945d-103">ADO.NET에서 사용 하는 **연결** 개체에 연결 문자열에 필요한 인증 정보를 제공 하 여 특정 데이터 원본에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="0945d-103">In ADO.NET you use a **Connection** object to connect to a specific data source by supplying necessary authentication information in a connection string.</span></span> <span data-ttu-id="0945d-104">**연결** 개체를 사용 하면 데이터 원본의 유형에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="0945d-104">The **Connection** object you use depends on the type of data source.</span></span>  
  
 <span data-ttu-id="0945d-105">.NET Framework에 포함된 각 .NET Framework 데이터 공급자에는 <xref:System.Data.Common.DbConnection> 개체가 있습니다. .NET Framework Data Provider for OLE DB에는 <xref:System.Data.OleDb.OleDbConnection> 개체가 있고 .NET Framework Data Provider for SQL Server에는 <xref:System.Data.SqlClient.SqlConnection> 개체가 있으며 .NET Framework Data Provider for ODBC에는 <xref:System.Data.Odbc.OdbcConnection> 개체가 있고 .NET Framework Data Provider for Oracle에는 <xref:System.Data.OracleClient.OracleConnection> 개체가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0945d-105">Each .NET Framework data provider included with the .NET Framework has a <xref:System.Data.Common.DbConnection> object: the .NET Framework Data Provider for OLE DB includes an <xref:System.Data.OleDb.OleDbConnection> object, the .NET Framework Data Provider for SQL Server includes a <xref:System.Data.SqlClient.SqlConnection> object, the .NET Framework Data Provider for ODBC includes an <xref:System.Data.Odbc.OdbcConnection> object, and the .NET Framework Data Provider for Oracle includes an <xref:System.Data.OracleClient.OracleConnection> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0945d-106">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="0945d-106">In This Section</span></span>  
 [<span data-ttu-id="0945d-107">연결 설정</span><span class="sxs-lookup"><span data-stu-id="0945d-107">Establishing the Connection</span></span>](../../../../docs/framework/data/adonet/establishing-the-connection.md)  
 <span data-ttu-id="0945d-108">사용 하는 방법에 설명 된 **연결** 데이터 원본에 대 한 연결을 설정 하기 위해 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="0945d-108">Describes how to use a **Connection** object to establish a connection to a data source.</span></span>  
  
 [<span data-ttu-id="0945d-109">연결 이벤트</span><span class="sxs-lookup"><span data-stu-id="0945d-109">Connection Events</span></span>](../../../../docs/framework/data/adonet/connection-events.md)  
 <span data-ttu-id="0945d-110">사용 하는 방법에 설명 된 **InfoMessage** 이벤트를 데이터 원본에서 정보 메시지를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="0945d-110">Describes how to use an **InfoMessage** event to retrieve informational messages from a data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0945d-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0945d-111">See Also</span></span>  
 [<span data-ttu-id="0945d-112">연결 문자열</span><span class="sxs-lookup"><span data-stu-id="0945d-112">Connection Strings</span></span>](../../../../docs/framework/data/adonet/connection-strings.md)  
 [<span data-ttu-id="0945d-113">연결 풀링</span><span class="sxs-lookup"><span data-stu-id="0945d-113">Connection Pooling</span></span>](../../../../docs/framework/data/adonet/connection-pooling.md)  
 [<span data-ttu-id="0945d-114">명령 및 매개 변수</span><span class="sxs-lookup"><span data-stu-id="0945d-114">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [<span data-ttu-id="0945d-115">DataAdapter 및 DataReader</span><span class="sxs-lookup"><span data-stu-id="0945d-115">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [<span data-ttu-id="0945d-116">트랜잭션 및 동시성</span><span class="sxs-lookup"><span data-stu-id="0945d-116">Transactions and Concurrency</span></span>](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)  
 [<span data-ttu-id="0945d-117">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="0945d-117">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
