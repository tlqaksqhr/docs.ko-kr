---
title: "SQL Server에서 저장 프로시저를 사용하여 권한 관리"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 08fa34e8-2ffa-470d-ba62-e511a5f8558e
caps.latest.revision: "6"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 806cd23060dde3f7b466df0d4ce39162353380e6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="managing-permissions-with-stored-procedures-in-sql-server"></a><span data-ttu-id="ec932-102">SQL Server에서 저장 프로시저를 사용하여 권한 관리</span><span class="sxs-lookup"><span data-stu-id="ec932-102">Managing Permissions with Stored Procedures in SQL Server</span></span>
<span data-ttu-id="ec932-103">데이터베이스 주변을 방어하는 여러 줄을 작성하는 한 가지 방법은 저장 프로시저 또는 사용자 정의 함수를 사용하여 모든 데이터 액세스를 구현하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ec932-103">One method of creating multiple lines of defense around your database is to implement all data access using stored procedures or user-defined functions.</span></span> <span data-ttu-id="ec932-104">테이블과 같은 원본 개체에 대한 모든 권한을 취소하거나 거부하고 저장 프로시저에 EXECUTE 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="ec932-104">You revoke or deny all permissions to underlying objects, such as tables, and grant EXECUTE permissions on stored procedures.</span></span> <span data-ttu-id="ec932-105">그러면 효율적으로 데이터 및 데이터베이스 개체 주변에 보안 경계를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ec932-105">This effectively creates a security perimeter around your data and database objects.</span></span>  
  
## <a name="stored-procedure-benefits"></a><span data-ttu-id="ec932-106">저장 프로시저의 장점</span><span class="sxs-lookup"><span data-stu-id="ec932-106">Stored Procedure Benefits</span></span>  
 <span data-ttu-id="ec932-107">저장 프로시저에는 다음과 같은 장점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec932-107">Stored procedures have the following benefits:</span></span>  
  
-   <span data-ttu-id="ec932-108">데이터 논리 및 비즈니스 규칙을 캡슐화하여 개발자 및 데이터베이스 관리자가 의도하는 방식으로만 사용자가 데이터 및 개체에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec932-108">Data logic and business rules can be encapsulated so that users can access data and objects only in ways that developers and database administrators intend.</span></span>  
  
-   <span data-ttu-id="ec932-109">모든 사용자 입력의 유효성을 확인하는 매개 변수화된 저장 프로시저를 사용하여 SQL 삽입 공격을 막을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec932-109">Parameterized stored procedures that validate all user input can be used to thwart SQL injection attacks.</span></span> <span data-ttu-id="ec932-110">동적 SQL을 사용하는 경우 명령을 매개 변수화하고 매개 변수 값을 쿼리 문자열에 직접 넣지 마세요.</span><span class="sxs-lookup"><span data-stu-id="ec932-110">If you use dynamic SQL, be sure to parameterize your commands, and never include parameter values directly into a query string.</span></span>  
  
-   <span data-ttu-id="ec932-111">임시 쿼리 및 데이터 수정은 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ec932-111">Ad hoc queries and data modifications can be disallowed.</span></span> <span data-ttu-id="ec932-112">실수로 또는 악의적으로 데이터를 파괴하거나 서버 또는 네트워크의 성능을 약화시키는 쿼리를 실행하지 못하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec932-112">This prevents users from maliciously or inadvertently destroying data or executing queries that impair performance on the server or the network.</span></span>  
  
-   <span data-ttu-id="ec932-113">오류를 클라이언트 응용 프로그램으로 직접 전달하지 않고 프로시저 코드에서 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec932-113">Errors can be handled in procedure code without being passed directly to client applications.</span></span> <span data-ttu-id="ec932-114">그러면 검색 공격을 도울 수 있는 오류 메시지가 반환되지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="ec932-114">This prevents error messages from being returned that could aid in a probing attack.</span></span> <span data-ttu-id="ec932-115">오류를 기록하고 서버에서 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="ec932-115">Log errors and handle them on the server.</span></span>  
  
-   <span data-ttu-id="ec932-116">저장 프로시저는 한 번만 작성되어 여러 응용 프로그램에서 액세스될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec932-116">Stored procedures can be written once, and accessed by many applications.</span></span>  
  
-   <span data-ttu-id="ec932-117">클라이언트 응용 프로그램에서는 내부 데이터 구조에 대해서는 몰라도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec932-117">Client applications do not need to know anything about the underlying data structures.</span></span> <span data-ttu-id="ec932-118">변경 내용이 매개 변수 목록 또는 반환된 데이터 형식에 영향을 미치지 않는 경우 클라이언트 응용 프로그램에서 변경할 필요 없이 저장 프로시저 코드를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec932-118">Stored procedure code can be changed without requiring changes in client applications as long as the changes do not affect parameter lists or returned data types.</span></span>  
  
-   <span data-ttu-id="ec932-119">여러 작업을 하나의 프로시저 호출로 결합하므로 저장 프로시저는 네트워크 트래픽을 줄여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ec932-119">Stored procedures can reduce network traffic by combining multiple operations into one procedure call.</span></span>  
  
## <a name="stored-procedure-execution"></a><span data-ttu-id="ec932-120">저장 프로시저 실행</span><span class="sxs-lookup"><span data-stu-id="ec932-120">Stored Procedure Execution</span></span>  
 <span data-ttu-id="ec932-121">저장 프로시저는 소유권 체인의 장점을 활용하여 데이터에 대한 액세스를 제공하므로 사용자는 데이터베이스 개체에 액세스하기 위해 명시적 권한을 가질 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ec932-121">Stored procedures take advantage of ownership chaining to provide access to data so that users do not need to have explicit permission to access database objects.</span></span> <span data-ttu-id="ec932-122">소유권 체인은 순차적으로 서로 액세스하는 개체가 동일한 사용자에 의해 소유될 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="ec932-122">An ownership chain exists when objects that access each other sequentially are owned by the same user.</span></span> <span data-ttu-id="ec932-123">예를 들어 저장 프로시저가 다른 저장 프로시저를 호출할 수 있으며 여러 테이블에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec932-123">For example, a stored procedure can call other stored procedures, or a stored procedure can access multiple tables.</span></span> <span data-ttu-id="ec932-124">실행 체인에 있는 모든 개체의 소유자가 동일한 경우 SQL Server는 호출자의 다른 개체에 대한 권한이 아닌 호출자에 대한 EXECUTE 권한만 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ec932-124">If all objects in the chain of execution have the same owner, then SQL Server only checks the EXECUTE permission for the caller, not the caller's permissions on other objects.</span></span> <span data-ttu-id="ec932-125">따라서 저장 프로시저에 EXECUTE 권한만 부여해야 하며 원본 테이블에 대한 모든 권한을 취소하거나 거부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec932-125">Therefore you need to grant only EXECUTE permissions on stored procedures; you can revoke or deny all permissions on the underlying tables.</span></span>  
  
## <a name="best-practices"></a><span data-ttu-id="ec932-126">모범 사례</span><span class="sxs-lookup"><span data-stu-id="ec932-126">Best Practices</span></span>  
 <span data-ttu-id="ec932-127">저장 프로시저를 작성하는 것만으로 응용 프로그램이 충분히 보호되는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="ec932-127">Simply writing stored procedures isn't enough to adequately secure your application.</span></span> <span data-ttu-id="ec932-128">다음과 같은 잠재적인 보안 허점을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec932-128">You should also consider the following potential security holes.</span></span>  
  
-   <span data-ttu-id="ec932-129">저장 프로시저에서 데이터에 액세스하려는 데이터베이스 역할에 대해 EXECUTE 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="ec932-129">Grant EXECUTE permissions on the stored procedures for database roles you want to be able to access the data.</span></span>  
  
-   <span data-ttu-id="ec932-130">`public` 역할을 포함하여 데이터베이스의 모든 역할과 사용자에 대해 원본 테이블에 대한 모든 권한을 취소하거나 거부합니다.</span><span class="sxs-lookup"><span data-stu-id="ec932-130">Revoke or deny all permissions to the underlying tables for all roles and users in the database, including the `public` role.</span></span> <span data-ttu-id="ec932-131">모든 사용자는 public에서 권한을 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="ec932-131">All users inherit permissions from public.</span></span> <span data-ttu-id="ec932-132">따라서 `public`에 대한 권한을 거부하면 소유자 및 `sysadmin` 멤버만 액세스할 수 있으며 다른 모든 사용자는 다른 역할의 멤버에서 권한을 상속할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec932-132">Therefore denying permissions to `public` means that only owners and `sysadmin` members have access; all other users will be unable to inherit permissions from membership in other roles.</span></span>  
  
-   <span data-ttu-id="ec932-133">`sysadmin` 또는 `db_owner` 역할에 사용자 또는 역할을 추가하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="ec932-133">Do not add users or roles to the `sysadmin` or `db_owner` roles.</span></span> <span data-ttu-id="ec932-134">시스템 관리자 및 데이터베이스 소유자가 모든 데이터베이스 개체에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec932-134">System administrators and database owners can access all database objects.</span></span>  
  
-   <span data-ttu-id="ec932-135">`guest` 계정을 비활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="ec932-135">Disable the `guest` account.</span></span> <span data-ttu-id="ec932-136">그러면 익명 사용자가 데이터베이스에 연결하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="ec932-136">This will prevent anonymous users from connecting to the database.</span></span> <span data-ttu-id="ec932-137">새 데이터베이스에서 guest 계정은 기본적으로 비활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec932-137">The guest account is disabled by default in new databases.</span></span>  
  
-   <span data-ttu-id="ec932-138">오류 처리를 구현하고 오류를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="ec932-138">Implement error handling and log errors.</span></span>  
  
-   <span data-ttu-id="ec932-139">모든 사용자 입력의 유효성을 확인하는 매개 변수화된 저장 프로시저를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ec932-139">Create parameterized stored procedures that validate all user input.</span></span> <span data-ttu-id="ec932-140">모든 사용자 입력을 신뢰되지 않은 것으로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="ec932-140">Treat all user input as untrusted.</span></span>  
  
-   <span data-ttu-id="ec932-141">동적 SQL은 반드시 필요한 경우에만 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="ec932-141">Avoid dynamic SQL unless absolutely necessary.</span></span> <span data-ttu-id="ec932-142">입력 문자열에서 문자열 값을 구분하고 구분 기호가 생기지 않도록 Transact-SQL QUOTENAME() 함수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ec932-142">Use the Transact-SQL QUOTENAME() function to delimit a string value and escape any occurrence of the delimiter in the input string.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="ec932-143">외부 리소스</span><span class="sxs-lookup"><span data-stu-id="ec932-143">External Resources</span></span>  
 <span data-ttu-id="ec932-144">자세한 내용은 다음 리소스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ec932-144">For more information, see the following resources.</span></span>  
  
|<span data-ttu-id="ec932-145">리소스</span><span class="sxs-lookup"><span data-stu-id="ec932-145">Resource</span></span>|<span data-ttu-id="ec932-146">설명</span><span class="sxs-lookup"><span data-stu-id="ec932-146">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="ec932-147">[저장 프로시저](http://msdn.microsoft.com/library/ms190782.aspx) 및 [SQL 주입](http://go.microsoft.com/fwlink/?LinkId=98234) SQL Server 온라인 설명서의</span><span class="sxs-lookup"><span data-stu-id="ec932-147">[Stored Procedures](http://msdn.microsoft.com/library/ms190782.aspx) and [SQL Injection](http://go.microsoft.com/fwlink/?LinkId=98234) in SQL Server Books Online</span></span>|<span data-ttu-id="ec932-148">저장 프로시저를 만드는 방법과 SQL 삽입이 작동하는 방식을 설명하는 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="ec932-148">Topics describe how to create stored procedures and how SQL Injection works.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ec932-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ec932-149">See Also</span></span>  
 [<span data-ttu-id="ec932-150">ADO.NET 응용 프로그램 보안</span><span class="sxs-lookup"><span data-stu-id="ec932-150">Securing ADO.NET Applications</span></span>](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [<span data-ttu-id="ec932-151">SQL Server 보안 개요</span><span class="sxs-lookup"><span data-stu-id="ec932-151">Overview of SQL Server Security</span></span>](../../../../../docs/framework/data/adonet/sql/overview-of-sql-server-security.md)  
 [<span data-ttu-id="ec932-152">SQL Server의 응용 프로그램 보안 시나리오</span><span class="sxs-lookup"><span data-stu-id="ec932-152">Application Security Scenarios in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 [<span data-ttu-id="ec932-153">보안 SQL Server에서 동적 SQL 작성</span><span class="sxs-lookup"><span data-stu-id="ec932-153">Writing Secure Dynamic SQL in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/writing-secure-dynamic-sql-in-sql-server.md)  
 [<span data-ttu-id="ec932-154">SQL Server에서 저장된 프로시저에 서명</span><span class="sxs-lookup"><span data-stu-id="ec932-154">Signing Stored Procedures in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/signing-stored-procedures-in-sql-server.md)  
 [<span data-ttu-id="ec932-155">SQL Server에서 가장으로 권한 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="ec932-155">Customizing Permissions with Impersonation in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/customizing-permissions-with-impersonation-in-sql-server.md)  
 [<span data-ttu-id="ec932-156">저장된 프로시저를 사용 하 여 데이터 수정</span><span class="sxs-lookup"><span data-stu-id="ec932-156">Modifying Data with Stored Procedures</span></span>](../../../../../docs/framework/data/adonet/modifying-data-with-stored-procedures.md)  
 [<span data-ttu-id="ec932-157">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="ec932-157">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
