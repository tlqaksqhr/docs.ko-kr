---
title: "MARS(Multiple Active Result Sets) 사용"
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
ms.assetid: 576079e4-debe-4ab5-9204-fcbe2ca7a5e2
caps.latest.revision: "6"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 0235a63a24f81968718d526ff676b023c060b9a6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="enabling-multiple-active-result-sets"></a><span data-ttu-id="d0929-102">MARS(Multiple Active Result Sets) 사용</span><span class="sxs-lookup"><span data-stu-id="d0929-102">Enabling Multiple Active Result Sets</span></span>
<span data-ttu-id="d0929-103">MARS(Multiple Active Result Sets)는 단일 연결에서 여러 배치를 실행할 수 있도록 하는 SQL Server의 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="d0929-103">Multiple Active Result Sets (MARS) is a feature that works with SQL Server to allow the execution of multiple batches on a single connection.</span></span> <span data-ttu-id="d0929-104">SQL Server에 MARS가 활성화되어 있으면 명령 개체를 사용할 때마다 연결에 세션이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0929-104">When MARS is enabled for use with SQL Server, each command object used adds a session to the connection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d0929-105">단일 MARS 세션은 사용할 MARS에 대해 하나의 논리적 연결을 연 다음 각 활성 명령에 대해 논리적 연결을 하나씩 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d0929-105">A single MARS session opens one logical connection for MARS to use and then one logical connection for each active command.</span></span>  
  
## <a name="enabling-and-disabling-mars-in-the-connection-string"></a><span data-ttu-id="d0929-106">연결 문자열에서 MARS 활성화 및 비활성화</span><span class="sxs-lookup"><span data-stu-id="d0929-106">Enabling and Disabling MARS in the Connection String</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d0929-107">샘플을 사용 하는 다음 연결 문자열에서는 **AdventureWorks** SQL Server에 포함 된 데이터베이스입니다.</span><span class="sxs-lookup"><span data-stu-id="d0929-107">The following connection strings use the sample **AdventureWorks** database included with SQL Server.</span></span> <span data-ttu-id="d0929-108">제공된 연결 문자열은 데이터베이스가 MSSQL1이라는 서버에 설치되었다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="d0929-108">The connection strings provided assume that the database is installed on a server named MSSQL1.</span></span> <span data-ttu-id="d0929-109">사용자 환경의 필요에 따라 연결 문자열을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="d0929-109">Modify the connection string as necessary for your environment.</span></span>  
  
 <span data-ttu-id="d0929-110">MARS 기능은 기본적으로 비활성화되어 있으며</span><span class="sxs-lookup"><span data-stu-id="d0929-110">The MARS feature is disabled by default.</span></span> <span data-ttu-id="d0929-111">연결 문자열에 "MultipleActiveResultSets=True" 키워드 쌍을 추가하여 활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0929-111">It can be enabled by adding the "MultipleActiveResultSets=True" keyword pair to your connection string.</span></span> <span data-ttu-id="d0929-112">MARS를 활성화하는 유일한 유효 값은 "True"입니다.</span><span class="sxs-lookup"><span data-stu-id="d0929-112">"True" is the only valid value for enabling MARS.</span></span> <span data-ttu-id="d0929-113">다음 예제에서는 SQL Server의 인스턴스에 연결하는 방법과 MARS를 활성화하도록 지정하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d0929-113">The following example demonstrates how to connect to an instance of SQL Server and how to specify that MARS should be enabled.</span></span>  
  
```vb  
Dim connectionString As String = "Data Source=MSSQL1;" & _  
    "Initial Catalog=AdventureWorks;Integrated Security=SSPI;" & _  
    "MultipleActiveResultSets=True"  
```  
  
```csharp  
string connectionString = "Data Source=MSSQL1;" +   
    "Initial Catalog=AdventureWorks;Integrated Security=SSPI;" +  
    "MultipleActiveResultSets=True";  
```  
  
 <span data-ttu-id="d0929-114">연결 문자열에 "MultipleActiveResultSets=False" 키워드 쌍을 추가하면 MARS를 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0929-114">You can disable MARS by adding the "MultipleActiveResultSets=False" keyword pair to your connection string.</span></span> <span data-ttu-id="d0929-115">MARS를 비활성화하는 유일한 유효 값은 "False"입니다.</span><span class="sxs-lookup"><span data-stu-id="d0929-115">"False" is the only valid value for disabling MARS.</span></span> <span data-ttu-id="d0929-116">다음 연결 문자열에서는 MARS를 비활성화하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d0929-116">The following connection string demonstrates how to disable MARS.</span></span>  
  
```vb  
Dim connectionString As String = "Data Source=MSSQL1;" & _  
    "Initial Catalog=AdventureWorks;Integrated Security=SSPI;" & _  
    "MultipleActiveResultSets=False"  
```  
  
```csharp  
string connectionString = "Data Source=MSSQL1;" +   
    "Initial Catalog=AdventureWorks;Integrated Security=SSPI;" +  
    "MultipleActiveResultSets=False";  
```  
  
## <a name="special-considerations-when-using-mars"></a><span data-ttu-id="d0929-117">MARS를 사용할 때 특별히 고려할 사항</span><span class="sxs-lookup"><span data-stu-id="d0929-117">Special Considerations When Using MARS</span></span>  
 <span data-ttu-id="d0929-118">일반적으로 MARS 사용 연결을 사용하기 위해 기존 응용 프로그램을 수정할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d0929-118">In general, existing applications should not need modification to use a MARS-enabled connection.</span></span> <span data-ttu-id="d0929-119">그러나 응용 프로그램에서 MARS 기능을 사용하려면 다음의 특별히 고려할 사항을 알아 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0929-119">However, if you wish to use MARS features in your applications, you should understand the following special considerations.</span></span>  
  
### <a name="statement-interleaving"></a><span data-ttu-id="d0929-120">문 인터리빙</span><span class="sxs-lookup"><span data-stu-id="d0929-120">Statement Interleaving</span></span>  
 <span data-ttu-id="d0929-121">MARS 작업은 서버에서 동기적으로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0929-121">MARS operations execute synchronously on the server.</span></span> <span data-ttu-id="d0929-122">또한 SELECT 및 BULK INSERT 문의 문 인터리빙이 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0929-122">Statement interleaving of SELECT and BULK INSERT statements is allowed.</span></span> <span data-ttu-id="d0929-123">그러나 DML(데이터 조작 언어) 및 DDL(데이터 정의 언어) 문은 원자적으로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0929-123">However, data manipulation language (DML) and data definition language (DDL) statements execute atomically.</span></span> <span data-ttu-id="d0929-124">원자 배치가 실행되는 동안 실행하려는 문은 모두 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0929-124">Any statements attempting to execute while an atomic batch is executing are blocked.</span></span> <span data-ttu-id="d0929-125">서버에서의 병렬 실행은 MARS 기능이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="d0929-125">Parallel execution at the server is not a MARS feature.</span></span>  
  
 <span data-ttu-id="d0929-126">MARS 연결에서 두 개의 배치, 즉 SELECT 문이 포함된 배치와 DML 문이 포함된 배치를 전송하면 DML은 SELECT 문을 실행하는 동안 실행을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0929-126">If two batches are submitted under a MARS connection, one of them containing a SELECT statement, the other containing a DML statement, the DML can begin execution within execution of the SELECT statement.</span></span> <span data-ttu-id="d0929-127">그러나 SELECT 문을 계속 실행하려면 반드시 DML 문의 실행을 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0929-127">However, the DML statement must run to completion before the SELECT statement can make progress.</span></span> <span data-ttu-id="d0929-128">두 문이 모두 동일한 트랜잭션에서 실행되는 경우 SELECT 문이 실행을 시작한 후 DML 문에서 변경한 모든 내용은 읽기 작업에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d0929-128">If both statements are running under the same transaction, any changes made by a DML statement after the SELECT statement has started execution are not visible to the read operation.</span></span>  
  
 <span data-ttu-id="d0929-129">SELECT 문 내부의 WAITFOR 문은 첫 번째 행이 생성될 때까지 기다리는 동안 트랜잭션을 만들지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d0929-129">A WAITFOR statement inside a SELECT statement does not yield the transaction while it is waiting, that is, until the first row is produced.</span></span> <span data-ttu-id="d0929-130">즉, WAITFOR 문이 대기 중인 경우에는 동일한 연결에서 다른 배치를 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d0929-130">This implies that no other batches can execute within the same connection while a WAITFOR statement is waiting.</span></span>  
  
### <a name="mars-session-cache"></a><span data-ttu-id="d0929-131">MARS 세션 캐시</span><span class="sxs-lookup"><span data-stu-id="d0929-131">MARS Session Cache</span></span>  
 <span data-ttu-id="d0929-132">MARS가 활성화된 연결이 열리면 논리 세션이 만들어져 오버헤드가 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0929-132">When a connection is opened with MARS enabled, a logical session is created, which adds additional overhead.</span></span> <span data-ttu-id="d0929-133">오버 헤드를 최소화 하 고 성능을 향상 하려면 **SqlClient** 연결 내에서 MARS 세션을 캐시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0929-133">To minimize overhead and enhance performance, **SqlClient** caches the MARS session within a connection.</span></span> <span data-ttu-id="d0929-134">캐시에는 최대 10개의 MARS 세션이 포함되며</span><span class="sxs-lookup"><span data-stu-id="d0929-134">The cache contains at most 10 MARS sessions.</span></span> <span data-ttu-id="d0929-135">이 값은 사용자가 조정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d0929-135">This value is not user adjustable.</span></span> <span data-ttu-id="d0929-136">세션 제한에 도달하면 새 세션이 만들어지며, 이때 오류는 생성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d0929-136">If the session limit is reached, a new session is created—an error is not generated.</span></span> <span data-ttu-id="d0929-137">캐시와 캐시에 포함된 세션은 각 연결을 기준으로 하므로 여러 연결에서 공유되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d0929-137">The cache and sessions contained in it are per-connection; they are not shared across connections.</span></span> <span data-ttu-id="d0929-138">세션이 해제되면 풀의 상한에 도달할 때까지 풀로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0929-138">When a session is released, it is returned to the pool unless the pool's upper limit has been reached.</span></span> <span data-ttu-id="d0929-139">캐시 풀이 꽉 차면 세션이 닫힙니다.</span><span class="sxs-lookup"><span data-stu-id="d0929-139">If the cache pool is full, the session is closed.</span></span> <span data-ttu-id="d0929-140">MARS 세션은 만료되지 않으며</span><span class="sxs-lookup"><span data-stu-id="d0929-140">MARS sessions do not expire.</span></span> <span data-ttu-id="d0929-141">연결 개체가 삭제될 때 정리되기만 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0929-141">They are only cleaned up when the connection object is disposed.</span></span> <span data-ttu-id="d0929-142">MARS 세션 캐시는 미리 로드되지 않고</span><span class="sxs-lookup"><span data-stu-id="d0929-142">The MARS session cache is not preloaded.</span></span> <span data-ttu-id="d0929-143">응용 프로그램에 추가 세션이 필요할 때 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0929-143">It is loaded as the application requires more sessions.</span></span>  
  
### <a name="thread-safety"></a><span data-ttu-id="d0929-144">스레드로부터의 안전성</span><span class="sxs-lookup"><span data-stu-id="d0929-144">Thread Safety</span></span>  
 <span data-ttu-id="d0929-145">MARS 작업은 스레드로부터 안전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d0929-145">MARS operations are not thread-safe.</span></span>  
  
### <a name="connection-pooling"></a><span data-ttu-id="d0929-146">연결 풀링</span><span class="sxs-lookup"><span data-stu-id="d0929-146">Connection Pooling</span></span>  
 <span data-ttu-id="d0929-147">MARS 사용 연결도 다른 모든 연결과 마찬가지로 풀링됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0929-147">MARS-enabled connections are pooled like any other connection.</span></span> <span data-ttu-id="d0929-148">응용 프로그램에서 두 개의 연결, 즉 MARS가 활성화되어 있는 연결과 MARS가 비활성화되어 있는 연결을 여는 경우 이 두 연결은 개별 풀에 위치합니다.</span><span class="sxs-lookup"><span data-stu-id="d0929-148">If an application opens two connections, one with MARS enabled and one with MARS disabled, the two connections are in separate pools.</span></span> <span data-ttu-id="d0929-149">자세한 내용은 참조 [SQL Server 연결 풀링 (ADO.NET)](../../../../../docs/framework/data/adonet/sql-server-connection-pooling.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d0929-149">For more information, see [SQL Server Connection Pooling (ADO.NET)](../../../../../docs/framework/data/adonet/sql-server-connection-pooling.md).</span></span>  
  
### <a name="sql-server-batch-execution-environment"></a><span data-ttu-id="d0929-150">SQL Server 배치 실행 환경</span><span class="sxs-lookup"><span data-stu-id="d0929-150">SQL Server Batch Execution Environment</span></span>  
 <span data-ttu-id="d0929-151">연결이 열리면 기본 환경이 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0929-151">When a connection is opened, a default environment is defined.</span></span> <span data-ttu-id="d0929-152">그런 다음 이 환경은 논리 MARS 세션에 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0929-152">This environment is then copied into a logical MARS session.</span></span>  
  
 <span data-ttu-id="d0929-153">배치 실행 환경에는 다음 구성 요소가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0929-153">The batch execution environment includes the following components:</span></span>  
  
-   <span data-ttu-id="d0929-154">설정 옵션(예: ANSI_NULLS, DATE_FORMAT, LANGUAGE, TEXTSIZE)</span><span class="sxs-lookup"><span data-stu-id="d0929-154">Set options (for example, ANSI_NULLS, DATE_FORMAT, LANGUAGE, TEXTSIZE)</span></span>  
  
-   <span data-ttu-id="d0929-155">보안 컨텍스트(사용자/응용 프로그램 역할)</span><span class="sxs-lookup"><span data-stu-id="d0929-155">Security context (user/application role)</span></span>  
  
-   <span data-ttu-id="d0929-156">데이터베이스 컨텍스트(현재 데이터베이스)</span><span class="sxs-lookup"><span data-stu-id="d0929-156">Database context (current database)</span></span>  
  
-   <span data-ttu-id="d0929-157">실행 상태 변수 (예를 들어 @@ERROR, @@ROWCOUNT, @@FETCH_STATUS @@IDENTITY)</span><span class="sxs-lookup"><span data-stu-id="d0929-157">Execution state variables (for example, @@ERROR, @@ROWCOUNT, @@FETCH_STATUS @@IDENTITY)</span></span>  
  
-   <span data-ttu-id="d0929-158">최상위 임시 테이블</span><span class="sxs-lookup"><span data-stu-id="d0929-158">Top-level temporary tables</span></span>  
  
 <span data-ttu-id="d0929-159">MARS가 활성화되면 기본 실행 환경이 연결에 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0929-159">With MARS, a default execution environment is associated to a connection.</span></span> <span data-ttu-id="d0929-160">지정된 연결에서 새 배치가 실행을 시작할 때마다 기본 환경의 복사본을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="d0929-160">Every new batch that starts executing under a given connection receives a copy of the default environment.</span></span> <span data-ttu-id="d0929-161">지정된 배치에서 코드가 실행될 때마다 해당 환경의 모든 변경 내용은 특정 배치로 범위가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0929-161">Whenever code is executed under a given batch, all changes made to the environment are scoped to the specific batch.</span></span> <span data-ttu-id="d0929-162">실행이 종료되면 실행 설정은 기본 환경에 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0929-162">Once execution finishes, the execution settings are copied into the default environment.</span></span> <span data-ttu-id="d0929-163">동일한 트랜잭션에서 여러 개의 명령을 실행하는 단일 배치를 순차적으로 실행하는 경우 의미 체계는 이전 클라이언트 또는 서버와 관련된 연결에서 노출한 의미 체계와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="d0929-163">In the case of a single batch issuing several commands to be executed sequentially under the same transaction, semantics are the same as those exposed by connections involving earlier clients or servers.</span></span>  
  
### <a name="parallel-execution"></a><span data-ttu-id="d0929-164">병렬 실행</span><span class="sxs-lookup"><span data-stu-id="d0929-164">Parallel Execution</span></span>  
 <span data-ttu-id="d0929-165">MARS를 사용하더라도 한 응용 프로그램의 여러 연결에 대한 모든 요구 사항은 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0929-165">MARS is not designed to remove all requirements for multiple connections in an application.</span></span> <span data-ttu-id="d0929-166">응용 프로그램에서 서버에 대한 명령의 실질적인 병렬 실행이 필요한 경우에는 여러 개의 연결을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0929-166">If an application needs true parallel execution of commands against a server, multiple connections should be used.</span></span>  
  
 <span data-ttu-id="d0929-167">예를 들어, 다음과 같은 시나리오를 가정해 봅시다.</span><span class="sxs-lookup"><span data-stu-id="d0929-167">For example, consider the following scenario.</span></span> <span data-ttu-id="d0929-168">두 개의 명령 개체, 즉 결과 집합을 처리하기 위한 명령 개체와 데이터를 업데이트하기 위한 명령 개체를 만듭니다. 이들 개체는 MARS를 통해 일반 연결을 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="d0929-168">Two command objects are created, one for processing a result set and another for updating data; they share a common connection via MARS.</span></span> <span data-ttu-id="d0929-169">이 시나리오는 `Transaction`합니다.`Commit`</span><span class="sxs-lookup"><span data-stu-id="d0929-169">In this scenario, the `Transaction`.`Commit`</span></span> <span data-ttu-id="d0929-170">업데이트를 수행 하지 못하므로 다음과 같은 예외가 발생 첫 번째 명령 개체에서 모든 결과 읽을 때까지:</span><span class="sxs-lookup"><span data-stu-id="d0929-170">fails on the update until all the results have been read on the first command object, yielding the following exception:</span></span>  
  
 <span data-ttu-id="d0929-171">메시지: 다른 세션에서 사용 중인 트랜잭션 컨텍스트</span><span class="sxs-lookup"><span data-stu-id="d0929-171">Message: Transaction context in use by another session.</span></span>  
  
 <span data-ttu-id="d0929-172">소스: .Net SqlClient Data Provider</span><span class="sxs-lookup"><span data-stu-id="d0929-172">Source: .Net SqlClient Data Provider</span></span>  
  
 <span data-ttu-id="d0929-173">예상: (null)</span><span class="sxs-lookup"><span data-stu-id="d0929-173">Expected: (null)</span></span>  
  
 <span data-ttu-id="d0929-174">수신: System.Data.SqlClient.SqlException</span><span class="sxs-lookup"><span data-stu-id="d0929-174">Received: System.Data.SqlClient.SqlException</span></span>  
  
 <span data-ttu-id="d0929-175">다음은 이 시나리오를 처리하기 위한 세 가지 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="d0929-175">There are three options for handling this scenario:</span></span>  
  
1.  <span data-ttu-id="d0929-176">판독기를 만든 후 트랜잭션을 시작하여 트랜잭션의 일부가 되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0929-176">Start the transaction after the reader is created, so that it is not part of the transaction.</span></span> <span data-ttu-id="d0929-177">그러면 모든 업데이트 작업이 고유한 트랜잭션이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0929-177">Every update then becomes its own transaction.</span></span>  
  
2.  <span data-ttu-id="d0929-178">판독기가 닫히면 모든 작업을 커밋합니다.</span><span class="sxs-lookup"><span data-stu-id="d0929-178">Commit all work after the reader is closed.</span></span> <span data-ttu-id="d0929-179">그러면 배치가 상당 부분 업데이트될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0929-179">This has the potential for a substantial batch of updates.</span></span>  
  
3.  <span data-ttu-id="d0929-180">MARS를 사용하는 대신 명령 개체마다 개별 연결을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="d0929-180">Don't use MARS; instead use a separate connection for each command object as you would have before MARS.</span></span>  
  
### <a name="detecting-mars-support"></a><span data-ttu-id="d0929-181">MARS 지원 검색</span><span class="sxs-lookup"><span data-stu-id="d0929-181">Detecting MARS Support</span></span>  
 <span data-ttu-id="d0929-182">응용 프로그램에서는 `SqlConnection.ServerVersion` 값을 읽어 MARS 지원 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0929-182">An application can check for MARS support by reading the `SqlConnection.ServerVersion` value.</span></span> <span data-ttu-id="d0929-183">SQL Server 2005의 주 번호는 9이고 SQL Server 2008의 주 번호는 10입니다.</span><span class="sxs-lookup"><span data-stu-id="d0929-183">The major number should be 9 for SQL Server 2005 and 10 for SQL Server 2008.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0929-184">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d0929-184">See Also</span></span>  
 [<span data-ttu-id="d0929-185">MARS(Multiple Active Result Sets)</span><span class="sxs-lookup"><span data-stu-id="d0929-185">Multiple Active Result Sets (MARS)</span></span>](../../../../../docs/framework/data/adonet/sql/multiple-active-result-sets-mars.md)  
 [<span data-ttu-id="d0929-186">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="d0929-186">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
