---
title: SQL Server에서 행 수준 권한 부여
ms.date: 03/30/2017
ms.assetid: a55aaa12-34ab-41cd-9dec-fd255b29258c
ms.openlocfilehash: 5f777b47c9b2f92c40fec01b4ff0c35fc28dbd89
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33361308"
---
# <a name="granting-row-level-permissions-in-sql-server"></a><span data-ttu-id="42583-102">SQL Server에서 행 수준 권한 부여</span><span class="sxs-lookup"><span data-stu-id="42583-102">Granting Row-Level Permissions in SQL Server</span></span>
<span data-ttu-id="42583-103">일부 시나리오에서는 권한 부여, 취소 또는 거부를 통해 제공되는 것보다 세부적인 수준으로 데이터에 대한 액세스를 제어해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="42583-103">In some scenarios, there is a requirement to control access to data at a more granular level than what simply granting, revoking, or denying permissions provides.</span></span> <span data-ttu-id="42583-104">예를 들어 병원용 데이터베이스 응용 프로그램에서는 개별 의사가 담당 환자에 관련된 정보에만 액세스하도록 제한해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42583-104">For example, a hospital database application may require individual Doctors to be restricted to accessing information related to only their patients.</span></span> <span data-ttu-id="42583-105">재무, 법률, 정부 및 군사용 응용 프로그램을 비롯한 다양한 환경에도 이러한 요구 사항이 적용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42583-105">Similar requirements exist in many environments, including finance, law, government, and military applications.</span></span> <span data-ttu-id="42583-106">이러한 시나리오를 해결할 수 있도록 SQL Server 2016에서는 보안 정책에서 행 수준 액세스 논리를 간소화하고 중앙 집중화하는 [행 수준 보안](https://msdn.microsoft.com/library/dn765131.aspx) 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="42583-106">To help address these scenarios, SQL Server 2016 provides a [Row-Level Security](https://msdn.microsoft.com/library/dn765131.aspx) feature that simplifies and centralizes row-level access logic in a security policy.</span></span> <span data-ttu-id="42583-107">초기 버전 SQL Server에서는 뷰를 사용하여 행 수준 필터링을 시행하는 방식으로 비슷한 기능을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42583-107">For earlier versions of SQL Server, similar functionality can be achieved by using views to enact row-level filtering.</span></span>  
  
## <a name="implementing-row-level-filtering"></a><span data-ttu-id="42583-108">행 수준 필터링 구현</span><span class="sxs-lookup"><span data-stu-id="42583-108">Implementing Row-level Filtering</span></span>  
 <span data-ttu-id="42583-109">행 수준 필터링은 위의 병원 예제처럼 정보를 단일 테이블에 저장하는 응용 프로그램에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="42583-109">Row-level filtering is used for applications storing information in a single table like in the hospital example above.</span></span> <span data-ttu-id="42583-110">행 수준 필터링을 구현하기 위해 각 행에는 사용자 이름, 레이블 또는 식별자와 같은 식별 매개 변수를 정의하는 열이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42583-110">To implement row-level filtering each row has a column that defines a differentiating parameter, such as a user name, label or other identifier.</span></span> <span data-ttu-id="42583-111">사용자가 액세스할 수 있는 행을 필터링하는 보안 정책 또는 테이블의 뷰를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="42583-111">You create either a security policy or a view on the table, which filters the rows that the user can access.</span></span> <span data-ttu-id="42583-112">그리고 사용자가 실행할 수 있는 쿼리 형식을 제어하는 매개 변수화된 저장 프로시저를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="42583-112">You then create parameterized stored procedures, which control the types of queries the user can execute.</span></span>  
  
 <span data-ttu-id="42583-113">다음 예제에서는 사용자 또는 로그인 이름을 기준으로 행 수준 필터링을 구성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="42583-113">The following example describes how to configure row-level filtering based on a user or login name:</span></span>  
  
-   <span data-ttu-id="42583-114">테이블을 만들고, 이름을 저장할 열을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="42583-114">Create the table, adding a column to store the name.</span></span>  
  
-   <span data-ttu-id="42583-115">행 수준 필터링을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="42583-115">Enable row-level filtering:</span></span>  
  
    -   <span data-ttu-id="42583-116">SQL Server 2016 이상이 사용 하는 경우 또는 [Azure SQL 데이터베이스](https://docs.microsoft.com/azure/sql-database/), 현재 데이터베이스 사용자 (CURRENT_USER는 사용 중 하 나와 일치 하는 것 반환 되는 행을 제한 하는 테이블에 있는 조건자를 추가 하는 보안 정책을 만듭니다 기본 제공 함수 사용) 또는 현재 로그인 이름 (suser_sname () 기본 제공 함수 사용):</span><span class="sxs-lookup"><span data-stu-id="42583-116">If you are using SQL Server 2016 or higher, or [Azure SQL Database](https://docs.microsoft.com/azure/sql-database/), create a security policy that adds a predicate on the table restricting the rows returned to those that match either the current database user (using the CURRENT_USER() built-in function) or the current login name (using the SUSER_SNAME() built-in function):</span></span>  
  
        ```tsql  
        CREATE SCHEMA Security  
        GO  
  
        CREATE FUNCTION Security.userAccessPredicate(@UserName sysname)  
            RETURNS TABLE  
            WITH SCHEMABINDING  
        AS  
            RETURN SELECT 1 AS accessResult  
            WHERE @UserName = SUSER_SNAME()  
        GO  
  
        CREATE SECURITY POLICY Security.userAccessPolicy  
            ADD FILTER PREDICATE Security.userAccessPredicate(UserName) ON dbo.MyTable,  
            ADD BLOCK PREDICATE Security.userAccessPredicate(UserName) ON dbo.MyTable  
        GO  
        ```  
  
    -   <span data-ttu-id="42583-117">SQL Server 2016 이전 버전을 사용하고 있으면 뷰를 사용하여 비슷한 기능을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42583-117">If you are using a version of SQL Server prior to 2016, you can achieve similar functionality using a view:</span></span>  
  
        ```tsql  
        CREATE VIEW vw_MyTable  
        AS  
            RETURN SELECT * FROM MyTable  
            WHERE UserName = SUSER_SNAME()  
        GO  
        ```  
  
-   <span data-ttu-id="42583-118">저장 프로시저를 만들어서 데이터를 선택, 삽입, 업데이트, 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="42583-118">Create stored procedures to select, insert, update, and delete data.</span></span> <span data-ttu-id="42583-119">필터링이 보안 정책을 통해 시행되면 저장 프로시저는 기본 테이블에서 직접 이들 작업을 수행해야 합니다. 그렇지 않고 필터링이 뷰를 통해 시행되면 저장 프로시저는 대신 뷰에서 작업을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="42583-119">If the filtering is enacted by a security policy, the stored procedures should perform these operations on the base table directly; otherwise, if the filtering is enacted by a view, the stored procedures should instead operate against the view.</span></span> <span data-ttu-id="42583-120">보안 정책 또는 뷰에서는 사용자 쿼리를 통해 반환 또는 수정되는 행을 자동으로 필터링하고, 저장 프로시저에서는 직접 쿼리 권한을 가진 사용자가 필터링된 데이터를 방해할 수 있는 쿼리를 실행하지 못하도록 더 강력한 보안 경계를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="42583-120">The security policy or view will automatically filter the rows returned or modified by user queries, and the stored procedure will provide a harder security boundary to prevent users with direct query access from successfully running queries that can infer the existence of filtered data.</span></span>  
  
-   <span data-ttu-id="42583-121">데이터를 삽입하는 저장 프로시저의 경우 보안 정책이나 뷰에 지정한 것과 동일한 함수를 사용하여 사용자 이름을 캡처하고 해당 값을 UserName 열에 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="42583-121">For stored procedures that insert data, capture the user name using the same function specified in the security policy or view, and insert that value into the UserName column.</span></span>  
  
-   <span data-ttu-id="42583-122">`public` 역할에 대해 테이블 및 뷰(적용 가능한 경우)에 대한 모든 권한을 거부합니다.</span><span class="sxs-lookup"><span data-stu-id="42583-122">Deny all permissions on the tables (and views, if applicable) to the `public` role.</span></span> <span data-ttu-id="42583-123">필터 조건자는 역할이 아니라 사용자 이름 또는 로그인 이름을 기반으로 하기 때문에 사용자는 다른 데이터베이스 역할에서 권한을 상속할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="42583-123">Users will not be able to inherit permissions from other database roles, because the filter predicate is based on user or login names, not on roles.</span></span>  
  
-   <span data-ttu-id="42583-124">데이터베이스 역할에 저장 프로시저에 대한 EXECUTE 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="42583-124">Grant EXECUTE on the stored procedures to database roles.</span></span> <span data-ttu-id="42583-125">사용자는 제공된 저장 프로시저를 통해서만 데이터에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42583-125">Users can only access data through the stored procedures provided.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="42583-126">외부 리소스</span><span class="sxs-lookup"><span data-stu-id="42583-126">External Resources</span></span>  
 <span data-ttu-id="42583-127">자세한 내용은 다음 리소스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="42583-127">For more information, see the following resource.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="42583-128">SQL Server TechCenter 사이트에서[SQL Server 2005를 사용하여 분류된 데이터베이스에서 행 및 셀 수준의 보안 성능을 구현](http://go.microsoft.com/fwlink/?LinkId=98227) 합니다.</span><span class="sxs-lookup"><span data-stu-id="42583-128">[Implementing Row- and Cell-Level Security in Classified Databases Using SQL Server 2005](http://go.microsoft.com/fwlink/?LinkId=98227) on the SQL Server TechCenter site.</span></span>|<span data-ttu-id="42583-129">행 및 셀 수준의 보안을 사용하여 기밀 데이터베이스의 보안 요구 사항을 충족하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="42583-129">Describes how to use row- and cell-level security to meet classified database security requirements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="42583-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="42583-130">See Also</span></span>  
 [<span data-ttu-id="42583-131">행 수준 보안</span><span class="sxs-lookup"><span data-stu-id="42583-131">Row-Level Security</span></span>](https://msdn.microsoft.com/library/dn765131.aspx)  
 [<span data-ttu-id="42583-132">ADO.NET 응용 프로그램 보안</span><span class="sxs-lookup"><span data-stu-id="42583-132">Securing ADO.NET Applications</span></span>](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [<span data-ttu-id="42583-133">SQL Server 보안 개요</span><span class="sxs-lookup"><span data-stu-id="42583-133">Overview of SQL Server Security</span></span>](../../../../../docs/framework/data/adonet/sql/overview-of-sql-server-security.md)  
 [<span data-ttu-id="42583-134">SQL Server의 응용 프로그램 보안 시나리오</span><span class="sxs-lookup"><span data-stu-id="42583-134">Application Security Scenarios in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 [<span data-ttu-id="42583-135">SQL Server에서 저장 프로시저를 사용하여 권한 관리</span><span class="sxs-lookup"><span data-stu-id="42583-135">Managing Permissions with Stored Procedures in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/managing-permissions-with-stored-procedures-in-sql-server.md)  
 [<span data-ttu-id="42583-136">SQL Server에서 동적 보안 SQL 작성</span><span class="sxs-lookup"><span data-stu-id="42583-136">Writing Secure Dynamic SQL in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/writing-secure-dynamic-sql-in-sql-server.md)  
 [<span data-ttu-id="42583-137">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="42583-137">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
