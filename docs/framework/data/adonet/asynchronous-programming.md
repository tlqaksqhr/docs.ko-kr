---
title: 비동기 프로그래밍
ms.date: 03/30/2017
ms.assetid: 85da7447-7125-426e-aa5f-438a290d1f77
ms.openlocfilehash: 29324a07ffdaf99d1b7631ad8e94e773ed509fcc
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="asynchronous-programming"></a><span data-ttu-id="e776c-102">비동기 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="e776c-102">Asynchronous Programming</span></span>

<span data-ttu-id="e776c-103">이 항목에서는의 비동기 프로그래밍에 대 한 지원을 설명는 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 에 도입 된 비동기 프로그래밍 기능을 지 원하는 향상 된 기능을 포함 하 여 Data Provider for SQL Server (SqlClient) [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="e776c-103">This topic discusses support for asynchronous programming in the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for SQL Server (SqlClient) including enhancements made to support asynchronous programming functionality that was introduced in [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)].</span></span>  
  
## <a name="legacy-asynchronous-programming"></a><span data-ttu-id="e776c-104">레거시 비동기 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="e776c-104">Legacy Asynchronous Programming</span></span>  
 <span data-ttu-id="e776c-105">[!INCLUDE[net_v45](../../../../includes/net-v45-md.md)] 이전에 SqlClient의 비동기 프로그래밍은 다음 메서드 및 `Asynchronous Processing=true` 연결 속성을 사용하여 수행되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e776c-105">Prior to [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], asynchronous programming with SqlClient was done with the following methods and the `Asynchronous Processing=true` connection property:</span></span>  
  
1.  <xref:System.Data.SqlClient.SqlCommand.BeginExecuteNonQuery%2A?displayProperty=nameWithType>  
  
2.  <xref:System.Data.SqlClient.SqlCommand.BeginExecuteReader%2A?displayProperty=nameWithType>  
  
3.  <xref:System.Data.SqlClient.SqlCommand.BeginExecuteXmlReader%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="e776c-106">[!INCLUDE[net_v45](../../../../includes/net-v45-md.md)]에서 이 기능은 SqlClient에 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e776c-106">This functionality remains in SqlClient in [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)].</span></span>  
  
 <span data-ttu-id="e776c-107">[!INCLUDE[net_v45](../../../../includes/net-v45-md.md)]부터는 더 이상 이러한 메서드를 사용하기 위해 연결 문자열에서 `Asynchronous Processing=true`를 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e776c-107">Beginning in the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], these methods no longer require `Asynchronous Processing=true` in the connection string.</span></span>  
  
## <a name="asynchronous-programming-features-added-in-includenetv45includesnet-v45-mdmd"></a><span data-ttu-id="e776c-108">[!INCLUDE[net_v45](../../../../includes/net-v45-md.md)]에 추가된 비동기 프로그래밍 기능</span><span class="sxs-lookup"><span data-stu-id="e776c-108">Asynchronous Programming Features Added in [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)]</span></span>  
 <span data-ttu-id="e776c-109">새로운 비동기 프로그래밍 기능에서는 코드를 비동기화하는 간단한 기술을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e776c-109">The new asynchronous programming feature provides a simple technique to make code asynchronous.</span></span>  
  
 <span data-ttu-id="e776c-110">[!INCLUDE[net_v45](../../../../includes/net-v45-md.md)]에서 도입된 비동기 프로그래밍 기능에 대한 자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e776c-110">For more information about the asynchronous programming feature that was introduced in [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], see:</span></span>  
  
- [<span data-ttu-id="e776c-111">C#에서 비동기 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="e776c-111">Asynchronous programming in C#</span></span>](../../../csharp/async.md)

- [<span data-ttu-id="e776c-112">Async 및 Await를 사용한 비동기 프로그래밍(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e776c-112">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/async/index.md)

- [<span data-ttu-id="e776c-113">.NET 4.5 (파트 1)에서 SqlDataReader의 새로운 비동기 메서드 사용</span><span class="sxs-lookup"><span data-stu-id="e776c-113">Using SqlDataReader’s new async methods in .Net 4.5 (Part 1)</span></span>](https://blogs.msdn.microsoft.com/adonet/2012/04/20/using-sqldatareaders-new-async-methods-in-net-4-5/)

- [<span data-ttu-id="e776c-114">SqlDataReader의 새로운 비동기 메서드를 사용 하 여.net 4.5 (2 부)</span><span class="sxs-lookup"><span data-stu-id="e776c-114">Using SqlDataReader’s new async methods in .Net 4.5 (Part 2)</span></span>](https://blogs.msdn.microsoft.com/adonet/2012/07/15/using-sqldatareaders-new-async-methods-in-net-4-5-part-2-examples/)
 
 <span data-ttu-id="e776c-115">사용자 인터페이스가 응답하지 않거나 서버가 확장되지 않을 경우 코드를 좀 더 비동기화해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e776c-115">When your user interface is unresponsive or your server does not scale, it is likely that you need your code to be more asynchronous.</span></span>  <span data-ttu-id="e776c-116">기존에는 비동기 코드를 작성하려면 비동기 작업이 완료될 때 발생하는 논리를 표현하기 위한 콜백 설치 과정(연속이라고도 함)이 필요했습니다.</span><span class="sxs-lookup"><span data-stu-id="e776c-116">Writing asynchronous code has traditionally involved installing a callback (also called continuation) to express the logic that occurs after the asynchronous operation finishes.</span></span> <span data-ttu-id="e776c-117">이로 인해 비동기 코드의 구조는 동기 코드에 비해 복잡했습니다.</span><span class="sxs-lookup"><span data-stu-id="e776c-117">This complicates the structure of asynchronous code as compared with synchronous code.</span></span>  
  
 <span data-ttu-id="e776c-118">이제 콜백을 사용하거나 코드를 분할하지 않고도 여러 메서드나 람다 식에서 비동기 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e776c-118">You can now call into asynchronous methods without using callbacks, and without splitting your code across multiple methods or lambda expressions.</span></span>  
  
 <span data-ttu-id="e776c-119">`async` 한정자는 메서드가 비동기 메서드임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e776c-119">The `async` modifier specifies that a method is asynchronous.</span></span> <span data-ttu-id="e776c-120">`async` 메서드를 호출하면 작업이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="e776c-120">When calling an `async` method, a task is returned.</span></span> <span data-ttu-id="e776c-121">경우는 `await` 연산자에는 작업에 적용 되는 경우 현재 메서드가 즉시 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e776c-121">When the `await` operator is applied to a task, the current method exits immediately.</span></span> <span data-ttu-id="e776c-122">작업이 끝나면 동일한 메서드에서 실행이 재개됩니다.</span><span class="sxs-lookup"><span data-stu-id="e776c-122">When the task finishes, execution resumes in the same method.</span></span>
  
> [!WARNING]
>  <span data-ttu-id="e776c-123">응용 프로그램에서 `Context Connection` 연결 문자열 키워드도 사용하는 경우에는 비동기 호출이 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e776c-123">Asynchronous calls are not supported if an application also uses the `Context Connection` connection string keyword.</span></span>  
  
 <span data-ttu-id="e776c-124">`async` 메서드를 호출할 때는 추가 스레드가 할당되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e776c-124">Calling an `async` method does not allocate any additional threads.</span></span> <span data-ttu-id="e776c-125">완료 시 기존 I/O 완료 스레드를 잠시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e776c-125">It may use the existing I/O completion thread briefly at the end.</span></span>  
  
 <span data-ttu-id="e776c-126">[!INCLUDE[net_v45](../../../../includes/net-v45-md.md)]에서는 비동기 프로그래밍을 지원하기 위해 다음 메서드가 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e776c-126">The following methods were added in [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)] to support asynchronous programming:</span></span>  
  
-   <xref:System.Data.Common.DbConnection.OpenAsync%2A?displayProperty=nameWithType>  
  
-   <xref:System.Data.Common.DbCommand.ExecuteDbDataReaderAsync%2A?displayProperty=nameWithType>  
  
-   <xref:System.Data.Common.DbCommand.ExecuteNonQueryAsync%2A?displayProperty=nameWithType>  
  
-   <xref:System.Data.Common.DbCommand.ExecuteReaderAsync%2A?displayProperty=nameWithType>  
  
-   <xref:System.Data.Common.DbCommand.ExecuteScalarAsync%2A?displayProperty=nameWithType>  
  
-   <xref:System.Data.Common.DbDataReader.GetFieldValueAsync%2A>  
  
-   <xref:System.Data.Common.DbDataReader.IsDBNullAsync%2A>  
  
-   <xref:System.Data.Common.DbDataReader.NextResultAsync%2A?displayProperty=nameWithType>  
  
-   <xref:System.Data.Common.DbDataReader.ReadAsync%2A?displayProperty=nameWithType>  
  
-   <xref:System.Data.SqlClient.SqlConnection.OpenAsync%2A?displayProperty=nameWithType>  
  
-   <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQueryAsync%2A?displayProperty=nameWithType>  
  
-   <xref:System.Data.SqlClient.SqlCommand.ExecuteReaderAsync%2A?displayProperty=nameWithType>  
  
-   <xref:System.Data.SqlClient.SqlCommand.ExecuteScalarAsync%2A?displayProperty=nameWithType>  
  
-   <xref:System.Data.SqlClient.SqlCommand.ExecuteXmlReaderAsync%2A?displayProperty=nameWithType>  
  
-   <xref:System.Data.SqlClient.SqlDataReader.NextResultAsync%2A?displayProperty=nameWithType>  
  
-   <xref:System.Data.SqlClient.SqlDataReader.ReadAsync%2A?displayProperty=nameWithType>  
  
-   <xref:System.Data.SqlClient.SqlBulkCopy.WriteToServerAsync%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="e776c-127">다른 비동기 멤버가 추가 된 지원 하기 [SqlClient 스트리밍 지원](../../../../docs/framework/data/adonet/sqlclient-streaming-support.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e776c-127">Other asynchronous members were added to support [SqlClient Streaming Support](../../../../docs/framework/data/adonet/sqlclient-streaming-support.md).</span></span>  
  
### <a name="synchronous-to-asynchronous-connection-open"></a><span data-ttu-id="e776c-128">비동기에서 동기로의 연결 열기</span><span class="sxs-lookup"><span data-stu-id="e776c-128">Synchronous to Asynchronous Connection Open</span></span>  
 <span data-ttu-id="e776c-129">새 비동기 기능을 사용하도록 기존 응용 프로그램을 업그레이드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e776c-129">You can upgrade an existing application to use the new asynchronous feature.</span></span> <span data-ttu-id="e776c-130">예를 들어 응용 프로그램이 동기 연결 알고리즘을 사용하며, 데이터베이스에 연결할 때마다 UI 스레드를 차단하고 연결 후에는 방금 로그인한 사용자를 다른 사용자에게 알리는 저장 프로시저를 호출한다고 가정해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="e776c-130">For example, assume an application has a synchronous connection algorithm and blocks the UI thread every time it connects to the database and, once connected, the application calls a stored procedure that signals other users of the one who just signed in.</span></span>  
  
```csharp
using SqlConnection conn = new SqlConnection("…");  
{  
   conn.Open();  
   using (SqlCommand cmd = new SqlCommand("StoredProcedure_Logon", conn))  
   {  
      cmd.ExecuteNonQuery();  
   }  
}  
```  
  
 <span data-ttu-id="e776c-131">새로운 비동기 기능을 사용하도록 변환할 경우 프로그램은 다음과 같이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e776c-131">When converted to use the new asynchronous functionality, the program would look like:</span></span>  
  
```csharp
using System;  
using System.Data.SqlClient;  
using System.Threading.Tasks;  
  
class A {  
  
   static async Task<int> Method(SqlConnection conn, SqlCommand cmd) {  
      await conn.OpenAsync();  
      await cmd.ExecuteNonQueryAsync();  
      return 1;  
   }  
  
   public static void Main() {  
      using (SqlConnection conn = new SqlConnection("Data Source=(local); Initial Catalog=NorthWind; Integrated Security=SSPI")) {  
         SqlCommand command = new SqlCommand("select top 2 * from orders", conn);  
  
         int result = A.Method(conn, command).Result;  
  
         SqlDataReader reader = command.ExecuteReader();  
         while (reader.Read())  
            Console.WriteLine(String.Format("{0}", reader[0]));  
      }  
   }  
}  
```  
  
### <a name="adding-the-new-asynchronous-feature-in-an-existing-application-mixing-old-and-new-patterns"></a><span data-ttu-id="e776c-132">기존 응용 프로그램에 새로운 비동기 기능 추가(기존 패턴과 새 패턴 혼합)</span><span class="sxs-lookup"><span data-stu-id="e776c-132">Adding the New Asynchronous Feature in an Existing Application (Mixing Old and New Patterns)</span></span>  
 <span data-ttu-id="e776c-133">기존 비동기 논리를 변경하지 않고 새로운 비동기 기능(SqlConnection::OpenAsync)을 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e776c-133">It is also possible to add new asynchronous capability (SqlConnection::OpenAsync) without changing the existing asynchronous logic.</span></span> <span data-ttu-id="e776c-134">예를 들어 응용 프로그램에서 현재 다음과 같은 알고리즘을 사용한다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="e776c-134">For example, if an application currently uses:</span></span>  
  
```csharp
AsyncCallback productList = new AsyncCallback(ProductList);  
SqlConnection conn = new SqlConnection("…");  
conn.Open();  
SqlCommand cmd = new SqlCommand("SELECT * FROM [Current Product List]", conn);  
IAsyncResult ia = cmd.BeginExecuteReader(productList, cmd);  
```  
  
 <span data-ttu-id="e776c-135">이 기존 알고리즘을 크게 변경하지 않고도 새로운 비동기 패턴을 사용하기 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e776c-135">You can begin to use the new asynchronous pattern without substantially changing the existing algorithm.</span></span>  
  
```csharp
using System;  
using System.Data.SqlClient;  
using System.Threading.Tasks;  
  
class A {  
   static void ProductList(IAsyncResult result) { }  
  
   public static void Main() {  
      // AsyncCallback productList = new AsyncCallback(ProductList);  
      // SqlConnection conn = new SqlConnection("Data Source=(local); Initial Catalog=NorthWind; Integrated Security=SSPI");  
      // conn.Open();  
      // SqlCommand cmd = new SqlCommand("select top 2 * from orders", conn);  
      // IAsyncResult ia = cmd.BeginExecuteReader(productList, cmd);  
  
      AsyncCallback productList = new AsyncCallback(ProductList);  
      SqlConnection conn = new SqlConnection("Data Source=(local); Initial Catalog=NorthWind; Integrated Security=SSPI");  
      conn.OpenAsync().ContinueWith((task) => {  
         SqlCommand cmd = new SqlCommand("select top 2 * from orders", conn);  
         IAsyncResult ia = cmd.BeginExecuteReader(productList, cmd);  
      }, TaskContinuationOptions.OnlyOnRanToCompletion);  
   }  
}  
```  
  
### <a name="using-the-base-provider-model-and-the-new-asynchronous-feature"></a><span data-ttu-id="e776c-136">기본 공급자 모델 및 새로운 비동기 기능 사용</span><span class="sxs-lookup"><span data-stu-id="e776c-136">Using the Base Provider Model and the New Asynchronous Feature</span></span>  
 <span data-ttu-id="e776c-137">다른 데이터베이스에 연결하고 쿼리를 실행할 수 있는 도구를 만들어야 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e776c-137">You may need to create a tool that is able to connect to different databases and execute queries.</span></span> <span data-ttu-id="e776c-138">이러한 경우 기본 공급자 모델과 새로운 비동기 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e776c-138">You can use the base provider model and the new asynchronous feature.</span></span>  
  
 <span data-ttu-id="e776c-139">서버에서 분산 트랜잭션을 사용하기 위해 MSDTC(Microsoft Distributed Transaction Coordinator)를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e776c-139">The Microsoft Distributed Transaction Controller (MSDTC) must be enabled on the server to use distributed transactions.</span></span> <span data-ttu-id="e776c-140">MSDTC를 사용 하도록 설정 하는 방법에 대 한 정보를 참조 하십시오. [웹 서버에서 MSDTC를 사용 하는 방법을](http://msdn.microsoft.com/library/dd327979.aspx)합니다.</span><span class="sxs-lookup"><span data-stu-id="e776c-140">For information on how to enable MSDTC, see [How to Enable MSDTC on a Web Server](http://msdn.microsoft.com/library/dd327979.aspx).</span></span>  
  
```csharp
using System;  
using System.Data.Common;  
using System.Data.SqlClient;  
using System.Threading.Tasks;  
  
class A {  
   static async Task PerformDBOperationsUsingProviderModel(string connectionString, string providerName) {  
      DbProviderFactory factory = DbProviderFactories.GetFactory(providerName);  
      using (DbConnection connection = factory.CreateConnection()) {  
         connection.ConnectionString = connectionString;  
         await connection.OpenAsync();  
  
         DbCommand command = connection.CreateCommand();  
         command.CommandText = "SELECT * FROM AUTHORS";  
  
         using (DbDataReader reader = await command.ExecuteReaderAsync()) {  
            while (await reader.ReadAsync()) {  
               for (int i = 0; i < reader.FieldCount; i++) {  
                  // Process each column as appropriate  
                  object obj = await reader.GetFieldValueAsync<object>(i);  
                  Console.WriteLine(obj);  
               }  
            }  
         }  
      }  
   }  
  
   public static void Main()   
   {  
       SqlConnectionStringBuilder builder = new SqlConnectionStringBuilder();  
       // replace these with your own values  
       builder.DataSource = "your_server";  
       builder.InitialCatalog = "pubs";  
       builder.IntegratedSecurity = true;  
       string provider = "System.Data.SqlClient";  
  
       Task task = PerformDBOperationsUsingProviderModel(builder.ConnectionString, provider);  
       task.Wait();  
   }  
}  
```  
  
### <a name="using-sql-transactions-and-the-new-asynchronous-feature"></a><span data-ttu-id="e776c-141">SQL 트랜잭션 및 새로운 비동기 기능 사용</span><span class="sxs-lookup"><span data-stu-id="e776c-141">Using SQL Transactions and the New Asynchronous Feature</span></span>  
  
```csharp
using System;  
using System.Data.SqlClient;  
using System.Threading.Tasks;  
  
class Program {  
   static void Main() {  
      string connectionString =  
          "Persist Security Info=False;Integrated Security=SSPI;database=Northwind;server=(local)";  
      Task task = ExecuteSqlTransaction(connectionString);  
      task.Wait();  
   }  
  
   static async Task ExecuteSqlTransaction(string connectionString) {  
      using (SqlConnection connection = new SqlConnection(connectionString)) {  
         await connection.OpenAsync();  
  
         SqlCommand command = connection.CreateCommand();  
         SqlTransaction transaction = null;  
  
         // Start a local transaction.  
         transaction = await Task.Run<SqlTransaction>(  
             () => connection.BeginTransaction("SampleTransaction")  
             );  
  
         // Must assign both transaction object and connection  
         // to Command object for a pending local transaction  
         command.Connection = connection;  
         command.Transaction = transaction;  
  
         try {  
            command.CommandText =  
                "Insert into Region (RegionID, RegionDescription) VALUES (555, 'Description')";  
            await command.ExecuteNonQueryAsync();  
  
            command.CommandText =  
                "Insert into Region (RegionID, RegionDescription) VALUES (556, 'Description')";  
            await command.ExecuteNonQueryAsync();  
  
            // Attempt to commit the transaction.  
            await Task.Run(() => transaction.Commit());  
            Console.WriteLine("Both records are written to database.");  
         }  
         catch (Exception ex) {  
            Console.WriteLine("Commit Exception Type: {0}", ex.GetType());  
            Console.WriteLine("  Message: {0}", ex.Message);  
  
            // Attempt to roll back the transaction.  
            try {  
               transaction.Rollback();  
            }  
            catch (Exception ex2) {  
               // This catch block will handle any errors that may have occurred  
               // on the server that would cause the rollback to fail, such as  
               // a closed connection.  
               Console.WriteLine("Rollback Exception Type: {0}", ex2.GetType());  
               Console.WriteLine("  Message: {0}", ex2.Message);  
            }  
         }  
      }  
   }  
}  
```  
  
### <a name="using-sql-transactions-and-the-new-asynchronous-feature"></a><span data-ttu-id="e776c-142">SQL 트랜잭션 및 새로운 비동기 기능 사용</span><span class="sxs-lookup"><span data-stu-id="e776c-142">Using SQL Transactions and the New Asynchronous Feature</span></span>  
 <span data-ttu-id="e776c-143">엔터프라이즈 응용 프로그램의 경우 일부 시나리오에서 분산 트랜잭션을 추가하여 여러 데이터베이스 서버 간에 트랜잭션을 사용하도록 설정해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e776c-143">In an enterprise application, you may need to add distributed transactions in some scenarios, to enable transactions between multiple database servers.</span></span> <span data-ttu-id="e776c-144">다음과 같이 System.Transactions 네임스페이스를 사용하고 분산 트랜잭션을 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e776c-144">You can use the System.Transactions namespace and enlist a distributed transaction, as follows:</span></span>  
  
```csharp
using System;  
using System.Data.SqlClient;  
using System.Threading.Tasks;  
using System.Transactions;  
  
class Program {  
   public static void Main()   
   {  
       SqlConnectionStringBuilder builder = new SqlConnectionStringBuilder();  
       // replace these with your own values  
       builder.DataSource = "your_server";  
       builder.InitialCatalog = "your_data_source";  
       builder.IntegratedSecurity = true;  
  
       Task task = ExecuteDistributedTransaction(builder.ConnectionString, builder.ConnectionString);  
       task.Wait();  
   }  
  
   static async Task ExecuteDistributedTransaction(string connectionString1, string connectionString2) {  
      using (SqlConnection connection1 = new SqlConnection(connectionString1))  
      using (SqlConnection connection2 = new SqlConnection(connectionString2)) {  
         using (CommittableTransaction transaction = new CommittableTransaction()) {  
            await connection1.OpenAsync();  
            connection1.EnlistTransaction(transaction);  
  
            await connection2.OpenAsync();  
            connection2.EnlistTransaction(transaction);  
  
            try {  
               SqlCommand command1 = connection1.CreateCommand();  
               command1.CommandText = "Insert into RegionTable1 (RegionID, RegionDescription) VALUES (100, 'Description')";  
               await command1.ExecuteNonQueryAsync();  
  
               SqlCommand command2 = connection2.CreateCommand();  
               command2.CommandText = "Insert into RegionTable2 (RegionID, RegionDescription) VALUES (100, 'Description')";  
               await command2.ExecuteNonQueryAsync();  
  
               transaction.Commit();  
            }  
            catch (Exception ex) {  
               Console.WriteLine("Exception Type: {0}", ex.GetType());  
               Console.WriteLine("  Message: {0}", ex.Message);  
  
               try {  
                  transaction.Rollback();  
               }  
               catch (Exception ex2) {  
                  Console.WriteLine("Rollback Exception Type: {0}", ex2.GetType());  
                  Console.WriteLine("  Message: {0}", ex2.Message);  
               }  
            }  
         }  
      }  
   }  
}  
```  
  
### <a name="cancelling-an-asynchronous-operation"></a><span data-ttu-id="e776c-145">비동기 작업 취소</span><span class="sxs-lookup"><span data-stu-id="e776c-145">Cancelling an Asynchronous Operation</span></span>  
 <span data-ttu-id="e776c-146"><xref:System.Threading.CancellationToken>을 사용하여 비동기 요청을 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e776c-146">You can cancel an asynchronous request by using the <xref:System.Threading.CancellationToken>.</span></span>  
  
```csharp
using System;  
using System.Data.SqlClient;  
using System.Threading;  
using System.Threading.Tasks;  
  
namespace Samples {  
   class CancellationSample {  
      public static void Main(string[] args) {  
         CancellationTokenSource source = new CancellationTokenSource();  
         source.CancelAfter(2000); // give up after 2 seconds  
         try {  
            Task result = CancellingAsynchronousOperations(source.Token);  
            result.Wait();  
         }  
         catch (AggregateException exception) {  
            if (exception.InnerException is SqlException) {  
               Console.WriteLine("Operation canceled");  
            }  
            else {  
               throw;  
            }  
         }  
      }  
  
      static async Task CancellingAsynchronousOperations(CancellationToken cancellationToken) {  
         using (SqlConnection connection = new SqlConnection("Server=(local);Integrated Security=true")) {  
            await connection.OpenAsync(cancellationToken);  
  
            SqlCommand command = new SqlCommand("WAITFOR DELAY '00:10:00'", connection);  
            await command.ExecuteNonQueryAsync(cancellationToken);  
         }  
      }  
   }  
}  
```  
  
### <a name="asynchronous-operations-with-sqlbulkcopy"></a><span data-ttu-id="e776c-147">SqlBulkCopy의 비동기 작업</span><span class="sxs-lookup"><span data-stu-id="e776c-147">Asynchronous Operations with SqlBulkCopy</span></span>  
 <span data-ttu-id="e776c-148"><xref:System.Data.SqlClient.SqlBulkCopy?displayProperty=nameWithType>에도 <xref:System.Data.SqlClient.SqlBulkCopy.WriteToServerAsync%2A?displayProperty=nameWithType>를 통해 비동기 기능이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e776c-148">Asynchronous capabilities were also added to <xref:System.Data.SqlClient.SqlBulkCopy?displayProperty=nameWithType> with <xref:System.Data.SqlClient.SqlBulkCopy.WriteToServerAsync%2A?displayProperty=nameWithType>.</span></span>  
  
```csharp
using System;  
using System.Collections.Generic;  
using System.Data;  
using System.Data.Odbc;  
using System.Data.SqlClient;  
using System.Linq;  
using System.Text;  
using System.Threading;  
using System.Threading.Tasks;  
  
namespace SqlBulkCopyAsyncCodeSample {  
   class Program {  
      static string selectStatment = "SELECT * FROM [pubs].[dbo].[titles]";  
      static string createDestTableStatement =  
          @"CREATE TABLE {0} (  
            [title_id] [varchar](6) NOT NULL,  
            [title] [varchar](80) NOT NULL,  
            [type] [char](12) NOT NULL,  
            [pub_id] [char](4) NULL,  
            [price] [money] NULL,  
            [advance] [money] NULL,  
            [royalty] [int] NULL,  
            [ytd_sales] [int] NULL,  
            [notes] [varchar](200) NULL,  
            [pubdate] [datetime] NOT NULL)";  
  
      // Replace the connection string if needed, for instance to connect to SQL Express: @"Server=(local)\SQLEXPRESS;Database=Demo;Integrated Security=true"  
      // static string connectionString = @"Server=(localdb)\V11.0;Database=Demo";  
      static string connectionString = @"Server=(local);Database=Demo;Integrated Security=true";  
  
      // static string odbcConnectionString = @"Driver={SQL Server};Server=(localdb)\V11.0;UID=oledb;Pwd=1Password!;Database=Demo";  
      static string odbcConnectionString = @"Driver={SQL Server};Server=(local);Database=Demo;Integrated Security=true";  
  
      // static string marsConnectionString = @"Server=(localdb)\V11.0;Database=Demo;MultipleActiveResultSets=true;";  
      static string marsConnectionString = @"Server=(local);Database=Demo;MultipleActiveResultSets=true;Integrated Security=true";  
  
      // Replace the Server name with your actual sql azure server name and User ID/Password  
      static string azureConnectionString = @"Server=SqlAzure;User ID=myUserID;Password=myPassword;Database=Demo";  
  
      static void Main(string[] args) {  
         SynchronousSqlBulkCopy();  
         AsyncSqlBulkCopy().Wait();  
         MixSyncAsyncSqlBulkCopy().Wait();  
         AsyncSqlBulkCopyNotifyAfter().Wait();  
         AsyncSqlBulkCopyDataRows().Wait();  
         // AsyncSqlBulkCopySqlServerToSqlAzure().Wait();  
         // AsyncSqlBulkCopyCancel().Wait();  
         AsyncSqlBulkCopyMARS().Wait();  
      }  
  
      // 3.1.1 Synchronous bulk copy in .NET 4.5  
      private static void SynchronousSqlBulkCopy() {  
         using (SqlConnection conn = new SqlConnection(connectionString)) {  
            conn.Open();  
            DataTable dt = new DataTable();  
            using (SqlCommand cmd = new SqlCommand(selectStatment, conn)) {  
               SqlDataAdapter adapter = new SqlDataAdapter(cmd);  
               adapter.Fill(dt);  
  
               string temptable = "[#" + Guid.NewGuid().ToString("N") + "]";  
               cmd.CommandText = string.Format(createDestTableStatement, temptable);  
               cmd.ExecuteNonQuery();  
  
               using (SqlBulkCopy bcp = new SqlBulkCopy(conn)) {  
                  bcp.DestinationTableName = temptable;  
                  bcp.WriteToServer(dt);  
               }  
            }  
         }  
  
      }  
  
      // 3.1.2 Asynchrounous bulk copy in .NET 4.5  
      private static async Task AsyncSqlBulkCopy() {  
         using (SqlConnection conn = new SqlConnection(connectionString)) {  
            await conn.OpenAsync();  
            DataTable dt = new DataTable();  
            using (SqlCommand cmd = new SqlCommand(selectStatment, conn)) {  
               SqlDataAdapter adapter = new SqlDataAdapter(cmd);  
               adapter.Fill(dt);  
  
               string temptable = "[#" + Guid.NewGuid().ToString("N") + "]";  
               cmd.CommandText = string.Format(createDestTableStatement, temptable);  
               await cmd.ExecuteNonQueryAsync();  
  
               using (SqlBulkCopy bcp = new SqlBulkCopy(conn)) {  
                  bcp.DestinationTableName = temptable;  
                  await bcp.WriteToServerAsync(dt);  
               }  
            }  
         }  
      }  
  
      // 3.2 Add new Async.NET capabilities in an existing application (Mixing synchronous and asynchornous calls)  
      private static async Task MixSyncAsyncSqlBulkCopy() {  
         using (OdbcConnection odbcconn = new OdbcConnection(odbcConnectionString)) {  
            odbcconn.Open();  
            using (OdbcCommand odbccmd = new OdbcCommand(selectStatment, odbcconn)) {  
               using (OdbcDataReader odbcreader = odbccmd.ExecuteReader()) {  
                  using (SqlConnection conn = new SqlConnection(connectionString)) {  
                     await conn.OpenAsync();  
                     string temptable = "temptable";//"[#" + Guid.NewGuid().ToString("N") + "]";  
                     SqlCommand createCmd = new SqlCommand(string.Format(createDestTableStatement, temptable), conn);  
                     await createCmd.ExecuteNonQueryAsync();  
                     using (SqlBulkCopy bcp = new SqlBulkCopy(conn)) {  
                        bcp.DestinationTableName = temptable;  
                        await bcp.WriteToServerAsync(odbcreader);  
                     }  
                  }  
               }  
            }  
         }  
      }  
  
      // 3.3 Using the NotifyAfter property  
      private static async Task AsyncSqlBulkCopyNotifyAfter() {  
         using (SqlConnection conn = new SqlConnection(connectionString)) {  
            await conn.OpenAsync();  
            DataTable dt = new DataTable();  
            using (SqlCommand cmd = new SqlCommand(selectStatment, conn)) {  
               SqlDataAdapter adapter = new SqlDataAdapter(cmd);  
               adapter.Fill(dt);  
  
               string temptable = "[#" + Guid.NewGuid().ToString("N") + "]";  
               cmd.CommandText = string.Format(createDestTableStatement, temptable);  
               await cmd.ExecuteNonQueryAsync();  
  
               using (SqlBulkCopy bcp = new SqlBulkCopy(conn)) {  
                  bcp.DestinationTableName = temptable;  
                  bcp.NotifyAfter = 5;  
                  bcp.SqlRowsCopied += new SqlRowsCopiedEventHandler(OnSqlRowsCopied);  
                  await bcp.WriteToServerAsync(dt);  
               }  
            }  
         }  
      }  
  
      private static void OnSqlRowsCopied(object sender, SqlRowsCopiedEventArgs e) {  
         Console.WriteLine("Copied {0} so far...", e.RowsCopied);  
      }  
  
      // 3.4 Using the new SqlBulkCopy Async.NET capabilities with DataRow[]  
      private static async Task AsyncSqlBulkCopyDataRows() {  
         using (SqlConnection conn = new SqlConnection(connectionString)) {  
            await conn.OpenAsync();  
            DataTable dt = new DataTable();  
            using (SqlCommand cmd = new SqlCommand(selectStatment, conn)) {  
               SqlDataAdapter adapter = new SqlDataAdapter(cmd);  
               adapter.Fill(dt);  
               DataRow[] rows = dt.Select();  
  
               string temptable = "[#" + Guid.NewGuid().ToString("N") + "]";  
               cmd.CommandText = string.Format(createDestTableStatement, temptable);  
               await cmd.ExecuteNonQueryAsync();  
  
               using (SqlBulkCopy bcp = new SqlBulkCopy(conn)) {  
                  bcp.DestinationTableName = temptable;  
                  await bcp.WriteToServerAsync(rows);  
               }  
            }  
         }  
      }  
  
      // 3.5 Copying data from SQL Server to SQL Azure in .NET 4.5  
      //private static async Task AsyncSqlBulkCopySqlServerToSqlAzure() {  
      //   using (SqlConnection srcConn = new SqlConnection(connectionString))  
      //   using (SqlConnection destConn = new SqlConnection(azureConnectionString)) {  
      //      await srcConn.OpenAsync();  
      //      await destConn.OpenAsync();  
      //      using (SqlCommand srcCmd = new SqlCommand(selectStatment, srcConn)) {  
      //         using (SqlDataReader reader = await srcCmd.ExecuteReaderAsync()) {  
      //            string temptable = "[#" + Guid.NewGuid().ToString("N") + "]";  
      //            using (SqlCommand destCmd = new SqlCommand(string.Format(createDestTableStatement, temptable), destConn)) {  
      //               await destCmd.ExecuteNonQueryAsync();  
      //               using (SqlBulkCopy bcp = new SqlBulkCopy(destConn)) {  
      //                  bcp.DestinationTableName = temptable;  
      //                  await bcp.WriteToServerAsync(reader);  
      //               }  
      //            }  
      //         }  
      //      }  
      //   }  
      //}  
  
      // 3.6 Cancelling an Asynchronous Operation to SQL Azure  
      //private static async Task AsyncSqlBulkCopyCancel() {  
      //   CancellationTokenSource cts = new CancellationTokenSource();  
      //   using (SqlConnection srcConn = new SqlConnection(connectionString))  
      //   using (SqlConnection destConn = new SqlConnection(azureConnectionString)) {  
      //      await srcConn.OpenAsync(cts.Token);  
      //      await destConn.OpenAsync(cts.Token);  
      //      using (SqlCommand srcCmd = new SqlCommand(selectStatment, srcConn)) {  
      //         using (SqlDataReader reader = await srcCmd.ExecuteReaderAsync(cts.Token)) {  
      //            string temptable = "[#" + Guid.NewGuid().ToString("N") + "]";  
      //            using (SqlCommand destCmd = new SqlCommand(string.Format(createDestTableStatement, temptable), destConn)) {  
      //               await destCmd.ExecuteNonQueryAsync(cts.Token);  
      //               using (SqlBulkCopy bcp = new SqlBulkCopy(destConn)) {  
      //                  bcp.DestinationTableName = temptable;  
      //                  await bcp.WriteToServerAsync(reader, cts.Token);  
      //                  //Cancel Async SqlBulCopy Operation after 200 ms  
      //                  cts.CancelAfter(200);  
      //               }  
      //            }  
      //         }  
      //      }  
      //   }  
      //}  
  
      // 3.7 Using Async.Net and MARS  
      private static async Task AsyncSqlBulkCopyMARS() {  
         using (SqlConnection marsConn = new SqlConnection(marsConnectionString)) {  
            await marsConn.OpenAsync();  
  
            SqlCommand titlesCmd = new SqlCommand("SELECT * FROM [pubs].[dbo].[titles]", marsConn);  
            SqlCommand authorsCmd = new SqlCommand("SELECT * FROM [pubs].[dbo].[authors]", marsConn);  
            //With MARS we can have multiple active results sets on the same connection  
            using (SqlDataReader titlesReader = await titlesCmd.ExecuteReaderAsync())  
            using (SqlDataReader authorsReader = await authorsCmd.ExecuteReaderAsync()) {  
               await authorsReader.ReadAsync();  
  
               string temptable = "[#" + Guid.NewGuid().ToString("N") + "]";  
               using (SqlConnection destConn = new SqlConnection(connectionString)) {  
                  await destConn.OpenAsync();  
                  using (SqlCommand destCmd = new SqlCommand(string.Format(createDestTableStatement, temptable), destConn)) {  
                     await destCmd.ExecuteNonQueryAsync();  
                     using (SqlBulkCopy bcp = new SqlBulkCopy(destConn)) {  
                        bcp.DestinationTableName = temptable;  
                        await bcp.WriteToServerAsync(titlesReader);  
                     }  
                  }  
               }  
            }  
         }  
      }  
   }  
}  
```  
  
## <a name="asynchronously-using-multiple-commands-with-mars"></a><span data-ttu-id="e776c-149">MARS를 사용하여 여러 명령을 비동기적으로 사용</span><span class="sxs-lookup"><span data-stu-id="e776c-149">Asynchronously Using Multiple Commands with MARS</span></span>  
 <span data-ttu-id="e776c-150">이 예제에서는 단일 연결을 열어 고 **AdventureWorks** 데이터베이스입니다.</span><span class="sxs-lookup"><span data-stu-id="e776c-150">The example opens a single connection to the **AdventureWorks** database.</span></span> <span data-ttu-id="e776c-151"><xref:System.Data.SqlClient.SqlCommand> 개체를 사용하면 <xref:System.Data.SqlClient.SqlDataReader>가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="e776c-151">Using a <xref:System.Data.SqlClient.SqlCommand> object, a <xref:System.Data.SqlClient.SqlDataReader> is created.</span></span> <span data-ttu-id="e776c-152">판독기를 사용하면 두 번째 <xref:System.Data.SqlClient.SqlDataReader>가 열리고 첫 번째 <xref:System.Data.SqlClient.SqlDataReader>의 데이터가 두 번째 판독기의 WHERE 절에 대한 입력으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e776c-152">As the reader is used, a second <xref:System.Data.SqlClient.SqlDataReader> is opened, using data from the first <xref:System.Data.SqlClient.SqlDataReader> as input to the WHERE clause for the second reader.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e776c-153">다음 예제에서는 샘플을 사용 하 여 **AdventureWorks** SQL Server에 포함 된 데이터베이스입니다.</span><span class="sxs-lookup"><span data-stu-id="e776c-153">The following example uses the sample **AdventureWorks** database included with SQL Server.</span></span> <span data-ttu-id="e776c-154">샘플 코드에 제공된 연결 문자열은 데이터베이스가 로컬 컴퓨터에 설치되었으며 사용 가능하다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="e776c-154">The connection string provided in the sample code assumes that the database is installed and available on the local computer.</span></span> <span data-ttu-id="e776c-155">사용자 환경의 필요에 따라 연결 문자열을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="e776c-155">Modify the connection string as necessary for your environment.</span></span>  
  
```csharp
using System;  
using System.Data;  
using System.Data.SqlClient;  
using System.Threading.Tasks;  
  
class Class1 {  
   static void Main() {  
      Task task = MultipleCommands();  
      task.Wait();  
   }  
  
   static async Task MultipleCommands() {  
      // By default, MARS is disabled when connecting to a MARS-enabled.  
      // It must be enabled in the connection string.  
      string connectionString = GetConnectionString();  
  
      int vendorID;  
      SqlDataReader productReader = null;  
      string vendorSQL =  
        "SELECT VendorId, Name FROM Purchasing.Vendor";  
      string productSQL =  
        "SELECT Production.Product.Name FROM Production.Product " +  
        "INNER JOIN Purchasing.ProductVendor " +  
        "ON Production.Product.ProductID = " +  
        "Purchasing.ProductVendor.ProductID " +  
        "WHERE Purchasing.ProductVendor.VendorID = @VendorId";  
  
      using (SqlConnection awConnection =  
        new SqlConnection(connectionString)) {  
         SqlCommand vendorCmd = new SqlCommand(vendorSQL, awConnection);  
         SqlCommand productCmd =  
           new SqlCommand(productSQL, awConnection);  
  
         productCmd.Parameters.Add("@VendorId", SqlDbType.Int);  
  
         await awConnection.OpenAsync();  
         using (SqlDataReader vendorReader = await vendorCmd.ExecuteReaderAsync()) {  
            while (await vendorReader.ReadAsync()) {  
               Console.WriteLine(vendorReader["Name"]);  
  
               vendorID = (int)vendorReader["VendorId"];  
  
               productCmd.Parameters["@VendorId"].Value = vendorID;  
               // The following line of code requires a MARS-enabled connection.  
               productReader = await productCmd.ExecuteReaderAsync();  
               using (productReader) {  
                  while (await productReader.ReadAsync()) {  
                     Console.WriteLine("  " +  
                       productReader["Name"].ToString());  
                  }  
               }  
            }  
         }  
      }  
   }  
  
   private static string GetConnectionString() {  
      // To avoid storing the connection string in your code, you can retrive it from a configuration file.  
      return "Data Source=(local);Integrated Security=SSPI;Initial Catalog=AdventureWorks;MultipleActiveResultSets=True";  
   }  
}  
```  
  
## <a name="asynchronously-reading-and-updating-data-with-mars"></a><span data-ttu-id="e776c-156">MARS를 사용하여 비동기적으로 데이터 읽기 및 업데이트</span><span class="sxs-lookup"><span data-stu-id="e776c-156">Asynchronously Reading and Updating Data with MARS</span></span>  
 <span data-ttu-id="e776c-157">MARS를 사용하면 하나의 연결을 둘 이상의 보류 중인 작업과 함께 읽기 작업 및 DML(데이터 조작 언어) 작업 모두에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e776c-157">MARS allows a connection to be used for both read operations and data manipulation language (DML) operations with more than one pending operation.</span></span> <span data-ttu-id="e776c-158">이 기능을 사용하면 응용 프로그램에서 연결 사용 오류를 처리할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e776c-158">This feature eliminates the need for an application to deal with connection-busy errors.</span></span> <span data-ttu-id="e776c-159">또한 MARS는 일반적으로 더 많은 리소스를 사용하는 서버측 커서의 사용자를 대체할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e776c-159">In addition, MARS can replace the user of server-side cursors, which generally consume more resources.</span></span> <span data-ttu-id="e776c-160">마지막으로 여러 작업이 단일 연결에서 실행 수, 있으므로 사용 하지 않아도 동일한 트랜잭션 컨텍스트를 공유 수 **sp_getbindtoken** 및 **sp_bindsession** 시스템 저장 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="e776c-160">Finally, because multiple operations can operate on a single connection, they can share the same transaction context, eliminating the need to use **sp_getbindtoken** and **sp_bindsession** system stored procedures.</span></span>  
  
 <span data-ttu-id="e776c-161">다음 콘솔 응용 프로그램에서는 두 개의 <xref:System.Data.SqlClient.SqlDataReader> 개체와 MARS가 활성화된 세 개의 <xref:System.Data.SqlClient.SqlCommand> 개체 및 하나의 <xref:System.Data.SqlClient.SqlConnection> 개체를 함께 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e776c-161">The following Console application demonstrates how to use two <xref:System.Data.SqlClient.SqlDataReader> objects with three <xref:System.Data.SqlClient.SqlCommand> objects and a single <xref:System.Data.SqlClient.SqlConnection> object with MARS enabled.</span></span> <span data-ttu-id="e776c-162">첫 번째 명령 개체에서는 신용 등급이 5인 공급업체 목록을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="e776c-162">The first command object retrieves a list of vendors whose credit rating is 5.</span></span> <span data-ttu-id="e776c-163">두 번째 명령 개체는 <xref:System.Data.SqlClient.SqlDataReader>에서 제공한 공급업체 ID를 사용하여 두 번째 <xref:System.Data.SqlClient.SqlDataReader>와 함께 특정 공급업체의 모든 제품을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="e776c-163">The second command object uses the vendor ID provided from a <xref:System.Data.SqlClient.SqlDataReader> to load the second <xref:System.Data.SqlClient.SqlDataReader> with all of the products for the particular vendor.</span></span> <span data-ttu-id="e776c-164">각 제품 레코드에는 두 번째 <xref:System.Data.SqlClient.SqlDataReader>에서 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="e776c-164">Each product record is visited by the second <xref:System.Data.SqlClient.SqlDataReader>.</span></span> <span data-ttu-id="e776c-165">새로운 결정 하는 계산을 수행 하는 **OnOrderQty** 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e776c-165">A calculation is performed to determine what the new **OnOrderQty** should be.</span></span> <span data-ttu-id="e776c-166">세 번째 명령 개체는 다음 업데이트 하는 데는 **ProductVendor** 새 값이 있는 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="e776c-166">The third command object is then used to update the **ProductVendor** table with the new value.</span></span> <span data-ttu-id="e776c-167">이 전체 프로세스가 단일 트랜잭션에서 발생하며 프로세스가 끝나면 롤백됩니다.</span><span class="sxs-lookup"><span data-stu-id="e776c-167">This entire process takes place within a single transaction, which is rolled back at the end.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e776c-168">다음 예제에서는 샘플을 사용 하 여 **AdventureWorks** SQL Server에 포함 된 데이터베이스입니다.</span><span class="sxs-lookup"><span data-stu-id="e776c-168">The following example uses the sample **AdventureWorks** database included with SQL Server.</span></span> <span data-ttu-id="e776c-169">샘플 코드에 제공된 연결 문자열은 데이터베이스가 로컬 컴퓨터에 설치되었으며 사용 가능하다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="e776c-169">The connection string provided in the sample code assumes that the database is installed and available on the local computer.</span></span> <span data-ttu-id="e776c-170">사용자 환경의 필요에 따라 연결 문자열을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="e776c-170">Modify the connection string as necessary for your environment.</span></span>  
  
```csharp
using System;  
using System.Collections.Generic;  
using System.Text;  
using System.Data;  
using System.Data.SqlClient;  
using System.Threading.Tasks;  
  
class Program {  
   static void Main() {  
      Task task = ReadingAndUpdatingData();  
      task.Wait();  
   }  
  
   static async Task ReadingAndUpdatingData() {  
      // By default, MARS is disabled when connecting to a MARS-enabled host.  
      // It must be enabled in the connection string.  
      string connectionString = GetConnectionString();  
  
      SqlTransaction updateTx = null;  
      SqlCommand vendorCmd = null;  
      SqlCommand prodVendCmd = null;  
      SqlCommand updateCmd = null;  
  
      SqlDataReader prodVendReader = null;  
  
      int vendorID = 0;  
      int productID = 0;  
      int minOrderQty = 0;  
      int maxOrderQty = 0;  
      int onOrderQty = 0;  
      int recordsUpdated = 0;  
      int totalRecordsUpdated = 0;  
  
      string vendorSQL =  
          "SELECT VendorID, Name FROM Purchasing.Vendor " +  
          "WHERE CreditRating = 5";  
      string prodVendSQL =  
          "SELECT ProductID, MaxOrderQty, MinOrderQty, OnOrderQty " +  
          "FROM Purchasing.ProductVendor " +  
          "WHERE VendorID = @VendorID";  
      string updateSQL =  
          "UPDATE Purchasing.ProductVendor " +  
          "SET OnOrderQty = @OrderQty " +  
          "WHERE ProductID = @ProductID AND VendorID = @VendorID";  
  
      using (SqlConnection awConnection =  
        new SqlConnection(connectionString)) {  
         await awConnection.OpenAsync();  
         updateTx = await Task.Run(() => awConnection.BeginTransaction());  
  
         vendorCmd = new SqlCommand(vendorSQL, awConnection);  
         vendorCmd.Transaction = updateTx;  
  
         prodVendCmd = new SqlCommand(prodVendSQL, awConnection);  
         prodVendCmd.Transaction = updateTx;  
         prodVendCmd.Parameters.Add("@VendorId", SqlDbType.Int);  
  
         updateCmd = new SqlCommand(updateSQL, awConnection);  
         updateCmd.Transaction = updateTx;  
         updateCmd.Parameters.Add("@OrderQty", SqlDbType.Int);  
         updateCmd.Parameters.Add("@ProductID", SqlDbType.Int);  
         updateCmd.Parameters.Add("@VendorID", SqlDbType.Int);  
  
         using (SqlDataReader vendorReader = await vendorCmd.ExecuteReaderAsync()) {  
            while (await vendorReader.ReadAsync()) {  
               Console.WriteLine(vendorReader["Name"]);  
  
               vendorID = (int)vendorReader["VendorID"];  
               prodVendCmd.Parameters["@VendorID"].Value = vendorID;  
               prodVendReader = await prodVendCmd.ExecuteReaderAsync();  
  
               using (prodVendReader) {  
                  while (await prodVendReader.ReadAsync()) {  
                     productID = (int)prodVendReader["ProductID"];  
  
                     if (prodVendReader["OnOrderQty"] == DBNull.Value) {  
                        minOrderQty = (int)prodVendReader["MinOrderQty"];  
                        onOrderQty = minOrderQty;  
                     }  
                     else {  
                        maxOrderQty = (int)prodVendReader["MaxOrderQty"];  
                        onOrderQty = (int)(maxOrderQty / 2);  
                     }  
  
                     updateCmd.Parameters["@OrderQty"].Value = onOrderQty;  
                     updateCmd.Parameters["@ProductID"].Value = productID;  
                     updateCmd.Parameters["@VendorID"].Value = vendorID;  
  
                     recordsUpdated = await updateCmd.ExecuteNonQueryAsync();  
                     totalRecordsUpdated += recordsUpdated;  
                  }  
               }  
            }  
         }  
         Console.WriteLine("Total Records Updated: ", totalRecordsUpdated.ToString());  
         await Task.Run(() => updateTx.Rollback());  
         Console.WriteLine("Transaction Rolled Back");  
      }  
   }  
  
   private static string GetConnectionString() {  
      // To avoid storing the connection string in your code, you can retrive it from a configuration file.  
      return "Data Source=(local);Integrated Security=SSPI;Initial Catalog=AdventureWorks;MultipleActiveResultSets=True";  
   }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="e776c-171">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e776c-171">See Also</span></span>  
 [<span data-ttu-id="e776c-172">ADO.NET에서 데이터 검색 및 수정</span><span class="sxs-lookup"><span data-stu-id="e776c-172">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
