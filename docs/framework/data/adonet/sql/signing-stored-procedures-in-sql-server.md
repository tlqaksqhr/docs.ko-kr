---
title: "SQL Server에서 저장 프로시저에 서명"
ms.custom: 
ms.date: 01/05/2018
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eeed752c-0084-48e5-9dca-381353007a0d
caps.latest.revision: 
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 15771cc214ee17bc2c98bab2423013483d1355f1
ms.sourcegitcommit: f28752eab00d2bd97e971542c0f49ce63cfbc239
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2018
---
# <a name="signing-stored-procedures-in-sql-server"></a><span data-ttu-id="c9413-102">SQL Server에서 저장 프로시저에 서명</span><span class="sxs-lookup"><span data-stu-id="c9413-102">Signing Stored Procedures in SQL Server</span></span>
 <span data-ttu-id="c9413-103">디지털 설명은 서명자의 개인 키로 암호화된 데이터 다이제스트입니다.</span><span class="sxs-lookup"><span data-stu-id="c9413-103">A digital signature is a data digest encrypted with the private key of the signer.</span></span> <span data-ttu-id="c9413-104">개인 키를 사용하면 디지털 서명이 소유자별로 고유하게 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9413-104">The private key ensures that the digital signature is unique to its bearer or owner.</span></span> <span data-ttu-id="c9413-105">저장된 프로시저, 함수 (인라인 테이블 반환 함수)를 제외한, 트리거 및 어셈블리를 서명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9413-105">You can sign stored procedures, functions (except for inline table-valued functions), triggers, and assemblies.</span></span>  
  
 <span data-ttu-id="c9413-106">인증서나 비대칭 키를 사용하여 저장 프로시저에 서명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9413-106">You can sign a stored procedure with a certificate or an asymmetric key.</span></span> <span data-ttu-id="c9413-107">이 기능은 권한을 소유권 체인을 통해 상속할 수 없거나 동적 SQL과 같이 소유권 체인이 끊어진 시나리오를 위해 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c9413-107">This is designed for scenarios when permissions cannot be inherited through ownership chaining or when the ownership chain is broken, such as dynamic SQL.</span></span> <span data-ttu-id="c9413-108">그런 다음 인증서를 저장된 프로시저에 액세스 해야 하는 개체에 대 한 사용자 권한을 부여 인증서에 매핑된 사용자를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9413-108">You can then create a user mapped to the certificate, granting the certificate user permissions on the objects the stored procedure needs to access.</span></span>  

 <span data-ttu-id="c9413-109">동일한 인증서에 매핑된 로그인을 만들 및 다음 해당 로그인에 필요한 서버 수준 사용 권한을 부여 하거나 수도 하나 이상의 고정된 서버 역할에 로그인을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9413-109">You can also create a login mapped to the same certificate, and then grant any necessary server-level permissions to that login, or add the login to one or more of the fixed server roles.</span></span> <span data-ttu-id="c9413-110">사용 하지 않도록 설정 하도록 설계 되어는 `TRUSTWORTHY` 데이터베이스 더 높은 수준의 사용 권한이 필요한 시나리오에 대 한 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="c9413-110">This is designed to avoid enabling the `TRUSTWORTHY` database setting for scenarios in which higher level permissions are needed.</span></span>  
  
 <span data-ttu-id="c9413-111">저장된 프로시저를 실행 하면 SQL Server와 호출자의 로그인 및/또는 인증서 사용자의 사용 권한을 결합 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9413-111">When the stored procedure is executed, SQL Server combines the permissions of the certificate user and/or login with those of the caller.</span></span> <span data-ttu-id="c9413-112">와 달리는 `EXECUTE AS` 절, 프로시저의 실행 컨텍스트를 변경 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c9413-112">Unlike the `EXECUTE AS` clause, it does not change the execution context of the procedure.</span></span> <span data-ttu-id="c9413-113">로그인과 사용자 이름을 반환하는 기본 제공 함수는 인증서 사용자 이름이 아니라 호출자의 이름을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c9413-113">Built-in functions that return login and user names return the name of the caller, not the certificate user name.</span></span>  
  
## <a name="creating-certificates"></a><span data-ttu-id="c9413-114">인증서 만들기</span><span class="sxs-lookup"><span data-stu-id="c9413-114">Creating Certificates</span></span>  
 <span data-ttu-id="c9413-115">인증서 나 비대칭 키를 execute와 함께 저장된 프로시저 코드의 암호화 된 해시로 구성 된 데이터 다이제스트가로 저장된 프로시저를 등록 하면-개인 키를 사용 하 여 만든이 사용자로 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9413-115">When you sign a stored procedure with a certificate or asymmetric key, a data digest consisting of the encrypted hash of the stored procedure code, along with the execute-as user, is created using the private key.</span></span> <span data-ttu-id="c9413-116">런타임에 데이터 다이제스트는 공개 키로 암호 해독되어 저장 프로시저의 해시 값과 비교됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9413-116">At run time, the data digest is decrypted with the public key and compared with the hash value of the stored procedure.</span></span> <span data-ttu-id="c9413-117">Execute 변경-대로 디지털 서명을 더 이상 일치 하도록 사용자 해시 값을 무효화 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9413-117">Changing the execute-as user invalidates the hash value so that the digital signature no longer matches.</span></span> <span data-ttu-id="c9413-118">저장된 프로시저 수정 삭제 서명을 완전히 방지 하는 코드를 변경 하면 저장된 프로시저에서 개인 키에 대 한 액세스 권한이 없는 사람이 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9413-118">Modifying the stored procedure drops the signature entirely, which prevents someone who does not have access to the private key from changing the stored procedure code.</span></span> <span data-ttu-id="c9413-119">두 경우 모두 다시 서명 해야 프로시저 코드 또는 execute를 변경할 때마다-사용자로 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9413-119">In either case, you must re-sign the procedure each time you change the code or the execute-as user.</span></span>  
  
 <span data-ttu-id="c9413-120">모듈에 서명할에 관련 된 두 단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9413-120">There are two required steps involved in signing a module:</span></span>  
  
1.  <span data-ttu-id="c9413-121">Transact-SQL `CREATE CERTIFICATE [certificateName]` 문을 사용하여 인증서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c9413-121">Create a certificate using the Transact-SQL `CREATE CERTIFICATE [certificateName]` statement.</span></span> <span data-ttu-id="c9413-122">이 문에는 시작 및 종료 날짜와 암호를 설정하기 위한 몇 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9413-122">This statement has several options for setting a start and end date and a password.</span></span> <span data-ttu-id="c9413-123">기본 만료 날짜는 1 년입니다.</span><span class="sxs-lookup"><span data-stu-id="c9413-123">The default expiration date is one year.</span></span>  
  
1.  <span data-ttu-id="c9413-124">Transact-SQL `ADD SIGNATURE TO [procedureName] BY CERTIFICATE [certificateName]` 문을 사용하여 프로시저에 인증서로 서명합니다.</span><span class="sxs-lookup"><span data-stu-id="c9413-124">Sign the procedure with the certificate using the Transact-SQL `ADD SIGNATURE TO [procedureName] BY CERTIFICATE [certificateName]` statement.</span></span>  

<span data-ttu-id="c9413-125">모듈에 서명 된 후 하나 이상의 보안 주체 인증서에 연결 해야 하는 추가 권한을 보유 하기 위해 만들 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9413-125">Once the module has been signed, one or more principals needs to be created in order to hold the additional permissions that should be associated with the certificate.</span></span>  

<span data-ttu-id="c9413-126">모듈이 데이터베이스 수준 사용 권한을 추가 해야 하는 경우:</span><span class="sxs-lookup"><span data-stu-id="c9413-126">If the module needs additional database-level permissions:</span></span>  
  
1.  <span data-ttu-id="c9413-127">Transact-SQL `CREATE USER [userName] FROM CERTIFICATE [certificateName]` 문을 사용하여 해당 인증서와 연결된 데이터베이스 사용자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c9413-127">Create a database user associated with that certificate using the Transact-SQL `CREATE USER [userName] FROM CERTIFICATE [certificateName]` statement.</span></span> <span data-ttu-id="c9413-128">이 사용자는 데이터베이스에 있으며 로그인도 동일한 인증서에서 생성 된 경우가 아니면 로그인과 연결 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c9413-128">This user exists in the database only and is not associated with a login unless a login has also been created from that same certificate.</span></span>  
  
1.  <span data-ttu-id="c9413-129">인증서 사용자에 게 필요한 데이터베이스 수준 사용 권한을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9413-129">Grant the certificate user the required database-level permissions.</span></span>  
  
<span data-ttu-id="c9413-130">모듈 추가 서버 수준 권한이 있어야 하는 경우:</span><span class="sxs-lookup"><span data-stu-id="c9413-130">If the module needs additional server-level permissions:</span></span>  
  
1.  <span data-ttu-id="c9413-131">인증서를 복사는 `master` 데이터베이스입니다.</span><span class="sxs-lookup"><span data-stu-id="c9413-131">Copy the certificate to the `master` database.</span></span>  
 
1.  <span data-ttu-id="c9413-132">TRANSACT-SQL을 사용 하 여 해당 인증서와 연결 된 로그인 만들기 `CREATE LOGIN [userName] FROM CERTIFICATE [certificateName]` 문.</span><span class="sxs-lookup"><span data-stu-id="c9413-132">Create a login associated with that certificate using the Transact-SQL `CREATE LOGIN [userName] FROM CERTIFICATE [certificateName]` statement.</span></span>  
  
1.  <span data-ttu-id="c9413-133">인증서 로그인 필요한 서버 수준 사용 권한을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9413-133">Grant the certificate login the required server-level permissions.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c9413-134">인증서는 DENY 문을 사용하여 호출된 권한을 가진 사용자에게 권한을 부여할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c9413-134">A certificate cannot grant permissions to a user that has had permissions revoked using the DENY statement.</span></span> <span data-ttu-id="c9413-135">DENY는 항상 GRANT보다 높은 우선 순위를 갖기 때문에 호출자가 인증서 사용자에게 부여된 권한을 상속 받지 않도록 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="c9413-135">DENY always takes precedence over GRANT, preventing the caller from inheriting permissions granted to the certificate user.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="c9413-136">외부 리소스</span><span class="sxs-lookup"><span data-stu-id="c9413-136">External Resources</span></span>  
 <span data-ttu-id="c9413-137">자세한 내용은 다음 리소스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c9413-137">For more information, see the following resources.</span></span>  
  
|<span data-ttu-id="c9413-138">리소스</span><span class="sxs-lookup"><span data-stu-id="c9413-138">Resource</span></span>|<span data-ttu-id="c9413-139">설명</span><span class="sxs-lookup"><span data-stu-id="c9413-139">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="c9413-140">[모듈 서명](http://go.microsoft.com/fwlink/?LinkId=98590) SQL Server 온라인 설명서의</span><span class="sxs-lookup"><span data-stu-id="c9413-140">[Module Signing](http://go.microsoft.com/fwlink/?LinkId=98590) in SQL Server Books Online</span></span>|<span data-ttu-id="c9413-141">모듈 서명을 설명하고 샘플 시나리오 및 관련 Transact-SQL 항목 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c9413-141">Describes module signing, providing a sample scenario and links to the relevant Transact-SQL topics.</span></span>|  
|<span data-ttu-id="c9413-142">[인증서로 저장된 프로시저에 서명](http://msdn.microsoft.com/library/bb283630.aspx) SQL Server 온라인 설명서의</span><span class="sxs-lookup"><span data-stu-id="c9413-142">[Signing Stored Procedures with a Certificate](http://msdn.microsoft.com/library/bb283630.aspx) in SQL Server Books Online</span></span>|<span data-ttu-id="c9413-143">인증서로 저장 프로시저에 서명하는 방법에 대한 자습서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c9413-143">Provides a tutorial for signing a stored procedure with a certificate.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c9413-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c9413-144">See Also</span></span>  
 [<span data-ttu-id="c9413-145">ADO.NET 응용 프로그램 보안</span><span class="sxs-lookup"><span data-stu-id="c9413-145">Securing ADO.NET Applications</span></span>](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [<span data-ttu-id="c9413-146">SQL Server 보안 개요</span><span class="sxs-lookup"><span data-stu-id="c9413-146">Overview of SQL Server Security</span></span>](../../../../../docs/framework/data/adonet/sql/overview-of-sql-server-security.md)  
 [<span data-ttu-id="c9413-147">SQL Server의 응용 프로그램 보안 시나리오</span><span class="sxs-lookup"><span data-stu-id="c9413-147">Application Security Scenarios in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 [<span data-ttu-id="c9413-148">SQL Server에서 저장 프로시저를 사용하여 권한 관리</span><span class="sxs-lookup"><span data-stu-id="c9413-148">Managing Permissions with Stored Procedures in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/managing-permissions-with-stored-procedures-in-sql-server.md)  
 [<span data-ttu-id="c9413-149">SQL Server에서 동적 보안 SQL 작성</span><span class="sxs-lookup"><span data-stu-id="c9413-149">Writing Secure Dynamic SQL in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/writing-secure-dynamic-sql-in-sql-server.md)  
 [<span data-ttu-id="c9413-150">SQL Server에서 가장으로 권한 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="c9413-150">Customizing Permissions with Impersonation in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/customizing-permissions-with-impersonation-in-sql-server.md)  
 [<span data-ttu-id="c9413-151">저장 프로시저로 데이터 수정</span><span class="sxs-lookup"><span data-stu-id="c9413-151">Modifying Data with Stored Procedures</span></span>](../../../../../docs/framework/data/adonet/modifying-data-with-stored-procedures.md)  
 [<span data-ttu-id="c9413-152">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="c9413-152">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
