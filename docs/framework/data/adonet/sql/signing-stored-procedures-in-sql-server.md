---
title: "SQL Server에서 저장 프로시저에 서명"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eeed752c-0084-48e5-9dca-381353007a0d
caps.latest.revision: "6"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: a3f1ed66ed7caf2272ca27097dc9a838bec7d0ae
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="signing-stored-procedures-in-sql-server"></a><span data-ttu-id="9ff41-102">SQL Server에서 저장 프로시저에 서명</span><span class="sxs-lookup"><span data-stu-id="9ff41-102">Signing Stored Procedures in SQL Server</span></span>
<span data-ttu-id="9ff41-103">인증서나 비대칭 키를 사용하여 저장 프로시저에 서명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ff41-103">You can sign a stored procedure with a certificate or an asymmetric key.</span></span> <span data-ttu-id="9ff41-104">이 기능은 권한을 소유권 체인을 통해 상속할 수 없거나 동적 SQL과 같이 소유권 체인이 끊어진 시나리오를 위해 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9ff41-104">This is designed for scenarios when permissions cannot be inherited through ownership chaining or when the ownership chain is broken, such as dynamic SQL.</span></span> <span data-ttu-id="9ff41-105">인증서에 매핑된 사용자를 만들고 저장 프로시저에서 액세스해야 하는 개체에 대한 인증서 사용자 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ff41-105">You then create a user mapped to the certificate, granting the certificate user permissions on the objects the stored procedure needs to access.</span></span>  
  
 <span data-ttu-id="9ff41-106">저장 프로시저가 실행되면 SQL Server에서 인증서 사용자의 권한을 호출자의 권한과 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="9ff41-106">When the stored procedure is executed, SQL Server combines the permissions of the certificate user with those of the caller.</span></span> <span data-ttu-id="9ff41-107">EXECUTE AS 절과는 달리 프로시저의 실행 컨텍스트는 변경하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9ff41-107">Unlike the EXECUTE AS clause, it does not change the execution context of the procedure.</span></span> <span data-ttu-id="9ff41-108">로그인과 사용자 이름을 반환하는 기본 제공 함수는 인증서 사용자 이름이 아니라 호출자의 이름을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9ff41-108">Built-in functions that return login and user names return the name of the caller, not the certificate user name.</span></span>  
  
 <span data-ttu-id="9ff41-109">디지털 설명은 서명자의 개인 키로 암호화된 데이터 다이제스트입니다.</span><span class="sxs-lookup"><span data-stu-id="9ff41-109">A digital signature is a data digest encrypted with the private key of the signer.</span></span> <span data-ttu-id="9ff41-110">개인 키를 사용하면 디지털 서명이 소유자별로 고유하게 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ff41-110">The private key ensures that the digital signature is unique to its bearer or owner.</span></span> <span data-ttu-id="9ff41-111">저장 프로시저, 함수 또는 트리거에 서명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ff41-111">You can sign stored procedures, functions, or triggers.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9ff41-112">master 데이터베이스에서 인증서를 만들어 서버 수준 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ff41-112">You can create a certificate in the master database to grant server-level permissions.</span></span>  
  
## <a name="creating-certificates"></a><span data-ttu-id="9ff41-113">인증서 만들기</span><span class="sxs-lookup"><span data-stu-id="9ff41-113">Creating Certificates</span></span>  
 <span data-ttu-id="9ff41-114">저장 프로시저에 인증서로 서명할 때는 저장 프로시저 코드의 암호화된 해시로 구성된 데이터 다이제스트가 개인 키를 사용하여 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="9ff41-114">When you sign a stored procedure with a certificate, a data digest consisting of the encrypted hash of the stored procedure code is created using the private key.</span></span> <span data-ttu-id="9ff41-115">런타임에 데이터 다이제스트는 공개 키로 암호 해독되어 저장 프로시저의 해시 값과 비교됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ff41-115">At run time, the data digest is decrypted with the public key and compared with the hash value of the stored procedure.</span></span> <span data-ttu-id="9ff41-116">저장 프로시저를 수정하면 해시 값이 무효화되어 디지털 서명이 더 이상 일치하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9ff41-116">Modifying the stored procedure invalidates the hash value so that the digital signature no longer matches.</span></span> <span data-ttu-id="9ff41-117">이를 통해 개인 키에 대한 액세스 권한이 없는 사용자는 저장 프로시저 코드를 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9ff41-117">This prevents someone who does not have access to the private key from changing the stored procedure code.</span></span> <span data-ttu-id="9ff41-118">따라서 프로시저를 수정할 때마다 다시 서명해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ff41-118">Therefore you must re-sign the procedure each time you modify it.</span></span>  
  
 <span data-ttu-id="9ff41-119">모듈에 서명할 때는 다음 네 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="9ff41-119">There are four steps involved in signing a module:</span></span>  
  
1.  <span data-ttu-id="9ff41-120">Transact-SQL `CREATE CERTIFICATE [certificateName]` 문을 사용하여 인증서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9ff41-120">Create a certificate using the Transact-SQL `CREATE CERTIFICATE [certificateName]` statement.</span></span> <span data-ttu-id="9ff41-121">이 문에는 시작 및 종료 날짜와 암호를 설정하기 위한 몇 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ff41-121">This statement has several options for setting a start and end date and a password.</span></span> <span data-ttu-id="9ff41-122">기본 만료일은 1년입니다.</span><span class="sxs-lookup"><span data-stu-id="9ff41-122">The default expiration date is one year</span></span>  
  
2.  <span data-ttu-id="9ff41-123">Transact-SQL `CREATE USER [userName] FROM CERTIFICATE [certificateName]` 문을 사용하여 해당 인증서와 연결된 데이터베이스 사용자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9ff41-123">Create a database user associated with that certificate using the Transact-SQL `CREATE USER [userName] FROM CERTIFICATE [certificateName]` statement.</span></span> <span data-ttu-id="9ff41-124">이 사용자는 데이터베이스에만 존재하며 로그인과는 관련되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9ff41-124">This user exists in the database only and is not associated with a login.</span></span>  
  
3.  <span data-ttu-id="9ff41-125">데이터베이스 개체에 대해 필요한 권한을 인증서 사용자에게 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="9ff41-125">Grant the certificate user the required permissions on the database objects.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9ff41-126">인증서는 DENY 문을 사용하여 호출된 권한을 가진 사용자에게 권한을 부여할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9ff41-126">A certificate cannot grant permissions to a user that has had permissions revoked using the DENY statement.</span></span> <span data-ttu-id="9ff41-127">DENY는 항상 GRANT보다 높은 우선 순위를 갖기 때문에 호출자가 인증서 사용자에게 부여된 권한을 상속 받지 않도록 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="9ff41-127">DENY always takes precedence over GRANT, preventing the caller from inheriting permissions granted to the certificate user.</span></span>  
  
1.  <span data-ttu-id="9ff41-128">Transact-SQL `ADD SIGNATURE TO [procedureName] BY CERTIFICATE [certificateName]` 문을 사용하여 프로시저에 인증서로 서명합니다.</span><span class="sxs-lookup"><span data-stu-id="9ff41-128">Sign the procedure with the certificate using the Transact-SQL `ADD SIGNATURE TO [procedureName] BY CERTIFICATE [certificateName]` statement.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="9ff41-129">외부 리소스</span><span class="sxs-lookup"><span data-stu-id="9ff41-129">External Resources</span></span>  
 <span data-ttu-id="9ff41-130">자세한 내용은 다음 리소스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9ff41-130">For more information, see the following resources.</span></span>  
  
|<span data-ttu-id="9ff41-131">리소스</span><span class="sxs-lookup"><span data-stu-id="9ff41-131">Resource</span></span>|<span data-ttu-id="9ff41-132">설명</span><span class="sxs-lookup"><span data-stu-id="9ff41-132">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="9ff41-133">[모듈 서명](http://go.microsoft.com/fwlink/?LinkId=98590) SQL Server 온라인 설명서의</span><span class="sxs-lookup"><span data-stu-id="9ff41-133">[Module Signing](http://go.microsoft.com/fwlink/?LinkId=98590) in SQL Server Books Online</span></span>|<span data-ttu-id="9ff41-134">모듈 서명을 설명하고 샘플 시나리오 및 관련 Transact-SQL 항목 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9ff41-134">Describes module signing, providing a sample scenario and links to the relevant Transact-SQL topics.</span></span>|  
|<span data-ttu-id="9ff41-135">[인증서로 저장된 프로시저에 서명](http://msdn.microsoft.com/library/bb283630.aspx) SQL Server 온라인 설명서의</span><span class="sxs-lookup"><span data-stu-id="9ff41-135">[Signing Stored Procedures with a Certificate](http://msdn.microsoft.com/library/bb283630.aspx) in SQL Server Books Online</span></span>|<span data-ttu-id="9ff41-136">인증서로 저장 프로시저에 서명하는 방법에 대한 자습서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9ff41-136">Provides a tutorial for signing a stored procedure with a certificate.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9ff41-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9ff41-137">See Also</span></span>  
 [<span data-ttu-id="9ff41-138">ADO.NET 응용 프로그램 보안</span><span class="sxs-lookup"><span data-stu-id="9ff41-138">Securing ADO.NET Applications</span></span>](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [<span data-ttu-id="9ff41-139">SQL Server 보안 개요</span><span class="sxs-lookup"><span data-stu-id="9ff41-139">Overview of SQL Server Security</span></span>](../../../../../docs/framework/data/adonet/sql/overview-of-sql-server-security.md)  
 [<span data-ttu-id="9ff41-140">SQL Server의 응용 프로그램 보안 시나리오</span><span class="sxs-lookup"><span data-stu-id="9ff41-140">Application Security Scenarios in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 [<span data-ttu-id="9ff41-141">SQL Server에서 저장 프로시저를 사용하여 권한 관리</span><span class="sxs-lookup"><span data-stu-id="9ff41-141">Managing Permissions with Stored Procedures in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/managing-permissions-with-stored-procedures-in-sql-server.md)  
 [<span data-ttu-id="9ff41-142">SQL Server에서 동적 보안 SQL 작성</span><span class="sxs-lookup"><span data-stu-id="9ff41-142">Writing Secure Dynamic SQL in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/writing-secure-dynamic-sql-in-sql-server.md)  
 [<span data-ttu-id="9ff41-143">SQL Server에서 가장으로 권한 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="9ff41-143">Customizing Permissions with Impersonation in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/customizing-permissions-with-impersonation-in-sql-server.md)  
 [<span data-ttu-id="9ff41-144">저장 프로시저로 데이터 수정</span><span class="sxs-lookup"><span data-stu-id="9ff41-144">Modifying Data with Stored Procedures</span></span>](../../../../../docs/framework/data/adonet/modifying-data-with-stored-procedures.md)  
 [<span data-ttu-id="9ff41-145">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="9ff41-145">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
