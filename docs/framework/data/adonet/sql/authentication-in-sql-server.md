---
title: SQL Server에서 인증
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 646ddbf5-dd4e-4285-8e4a-f565f666c5cc
caps.latest.revision: 9
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 1c918df5de4a66c00f6fd9b9dd1719ac05041ce1
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="authentication-in-sql-server"></a><span data-ttu-id="3f737-102">SQL Server에서 인증</span><span class="sxs-lookup"><span data-stu-id="3f737-102">Authentication in SQL Server</span></span>
<span data-ttu-id="3f737-103">SQL Server에서는 Windows 인증 모드와 혼합 모드의 두 가지 인증 모드를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="3f737-103">SQL Server supports two authentication modes, Windows authentication mode and mixed mode.</span></span>  
  
-   <span data-ttu-id="3f737-104">Windows 인증은 기본 인증이며 흔히 통합 보안이라고 하는데, 그 이유는 이 SQL Server 보안 모델이 Windows와 긴밀하게 통합되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="3f737-104">Windows authentication is the default, and is often referred to as integrated security because this SQL Server security model is tightly integrated with Windows.</span></span> <span data-ttu-id="3f737-105">이 보안 모델에서는 특정 Windows 사용자 및 그룹 계정에 SQL Server에 로그인할 수 있는 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="3f737-105">Specific Windows user and group accounts are trusted to log in to SQL Server.</span></span> <span data-ttu-id="3f737-106">이미 인증된 Windows 사용자는 추가 자격 증명을 제공할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3f737-106">Windows users who have already been authenticated do not have to present additional credentials.</span></span>  
  
-   <span data-ttu-id="3f737-107">혼합 모드에서는 Windows 인증과 SQL Server 인증을 모두 지원하며</span><span class="sxs-lookup"><span data-stu-id="3f737-107">Mixed mode supports authentication both by Windows and by SQL Server.</span></span> <span data-ttu-id="3f737-108">사용자 이름 및 암호 쌍이 SQL Server 내에서 유지 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f737-108">User name and password pairs are maintained within SQL Server.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3f737-109">가급적 Windows 인증을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3f737-109">We recommend using Windows authentication wherever possible.</span></span> <span data-ttu-id="3f737-110">Windows 인증은 일련의 암호화된 메시지를 사용하여 SQL Server에서 사용자를 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="3f737-110">Windows authentication uses a series of encrypted messages to authenticate users in SQL Server.</span></span> <span data-ttu-id="3f737-111">SQL Server 로그인을 사용하는 경우 SQL Server 로그인 이름과 암호가 네트워크를 통해 전달되므로 Windows 인증에 비해 보안이 떨어집니다.</span><span class="sxs-lookup"><span data-stu-id="3f737-111">When SQL Server logins are used, SQL Server login names and passwords are passed across the network, which makes them less secure.</span></span>  
  
 <span data-ttu-id="3f737-112">Windows 인증을 사용하는 경우 사용자가 Windows에 이미 로그온되어 있으므로 SQL Server에 별도로 로그온할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3f737-112">With Windows authentication, users are already logged onto Windows and do not have to log on separately to SQL Server.</span></span> <span data-ttu-id="3f737-113">다음 `SqlConnection.ConnectionString`은 사용자 이름이나 암호를 제공할 필요가 없는 Windows 인증을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3f737-113">The following `SqlConnection.ConnectionString` specifies Windows authentication without requiring the a user name or password.</span></span>  
  
```  
"Server=MSSQL1;Database=AdventureWorks;Integrated Security=true;  
```  
  
> [!NOTE]
>  <span data-ttu-id="3f737-114">로그인은 데이터베이스 사용자와는 다른 개념입니다.</span><span class="sxs-lookup"><span data-stu-id="3f737-114">Logins are distinct from database users.</span></span> <span data-ttu-id="3f737-115">따라서 로그인이나 Windows 그룹을 데이터베이스 사용자나 역할에 매핑하는 작업을 별도로 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f737-115">You must map logins or Windows groups to database users or roles in a separate operation.</span></span> <span data-ttu-id="3f737-116">그런 다음 데이터베이스 개체에 액세스할 수 있도록 사용자나 역할에 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="3f737-116">You then grant permissions to users or roles to access database objects.</span></span>  
  
## <a name="authentication-scenarios"></a><span data-ttu-id="3f737-117">인증 시나리오</span><span class="sxs-lookup"><span data-stu-id="3f737-117">Authentication Scenarios</span></span>  
 <span data-ttu-id="3f737-118">일반적으로 Windows 인증은 다음과 같은 환경에서 가장 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="3f737-118">Windows authentication is usually the best choice in the following situations:</span></span>  
  
-   <span data-ttu-id="3f737-119">도메인 컨트롤러가 있는 경우</span><span class="sxs-lookup"><span data-stu-id="3f737-119">There is a domain controller.</span></span>  
  
-   <span data-ttu-id="3f737-120">응용 프로그램과 데이터베이스가 동일한 컴퓨터에 있는 경우</span><span class="sxs-lookup"><span data-stu-id="3f737-120">The application and the database are on the same computer.</span></span>  
  
-   <span data-ttu-id="3f737-121">SQL Server Express 또는 LocalDB의 인스턴스를 사용 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f737-121">You are using an instance of SQL Server Express or LocalDB.</span></span>  
  
 <span data-ttu-id="3f737-122">SQL Server 로그인은 대개 다음과 같은 환경에서 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3f737-122">SQL Server logins are often used in the following situations:</span></span>  
  
-   <span data-ttu-id="3f737-123">작업 그룹이 있는 경우</span><span class="sxs-lookup"><span data-stu-id="3f737-123">If you have a workgroup.</span></span>  
  
-   <span data-ttu-id="3f737-124">사용자가 신뢰할 수 없는 여러 도메인에서 연결하는 경우</span><span class="sxs-lookup"><span data-stu-id="3f737-124">Users connect from different, non-trusted domains.</span></span>  
  
-   <span data-ttu-id="3f737-125">[!INCLUDE[vstecasp](../../../../../includes/vstecasp-md.md)]과 같은 인터넷 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="3f737-125">Internet applications, such as [!INCLUDE[vstecasp](../../../../../includes/vstecasp-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3f737-126">Windows 인증을 지정하더라도 SQL Server 로그인이 비활성화되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3f737-126">Specifying Windows authentication does not disable SQL Server logins.</span></span> <span data-ttu-id="3f737-127">ALTER LOGIN DISABLE을 사용 하 여 [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] 문을 높은 권한을 가진 SQL Server 로그인을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f737-127">Use the ALTER LOGIN DISABLE [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] statement to disable highly-privileged SQL Server logins.</span></span>  
  
## <a name="login-types"></a><span data-ttu-id="3f737-128">로그인 유형</span><span class="sxs-lookup"><span data-stu-id="3f737-128">Login Types</span></span>  
 <span data-ttu-id="3f737-129">SQL Server에서는 세 가지 유형의 로그인을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="3f737-129">SQL Server supports three types of logins:</span></span>  
  
-   <span data-ttu-id="3f737-130">로컬 Windows 사용자 계정 또는 신뢰할 수 있는 도메인 계정.</span><span class="sxs-lookup"><span data-stu-id="3f737-130">A local Windows user account or trusted domain account.</span></span> <span data-ttu-id="3f737-131">SQL Server는 Windows를 통해 Windows 사용자 계정을 인증합니다.</span><span class="sxs-lookup"><span data-stu-id="3f737-131">SQL Server relies on Windows to authenticate the Windows user accounts.</span></span>  
  
-   <span data-ttu-id="3f737-132">Windows 그룹.</span><span class="sxs-lookup"><span data-stu-id="3f737-132">Windows group.</span></span> <span data-ttu-id="3f737-133">Windows 그룹에 권한을 부여하면 해당 그룹에 속한 모든 Windows 사용자 로그인에도 동일한 권한이 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f737-133">Granting access to a Windows group grants access to all Windows user logins that are members of the group.</span></span>  
  
-   <span data-ttu-id="3f737-134">SQL Server 로그인.</span><span class="sxs-lookup"><span data-stu-id="3f737-134">SQL Server login.</span></span> <span data-ttu-id="3f737-135">SQL Server에서는 사용자 이름과 암호 해시를 모두 master 데이터베이스에 저장하고, 내부 인증 방법을 사용하여 로그인 시도가 유효한지 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="3f737-135">SQL Server stores both the username and a hash of the password in the master database, by using internal authentication methods to verify login attempts.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3f737-136">SQL Server는 인증서 또는 코드 서명 용도로 사용 되는 비대칭 키에서 만든 로그인을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f737-136">SQL Server provides logins created from certificates or asymmetric keys that are used only for code signing.</span></span> <span data-ttu-id="3f737-137">이러한 로그인은 SQL Server에 연결하는 데 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3f737-137">They cannot be used to connect to SQL Server.</span></span>  
  
## <a name="mixed-mode-authentication"></a><span data-ttu-id="3f737-138">혼합 모드 인증</span><span class="sxs-lookup"><span data-stu-id="3f737-138">Mixed Mode Authentication</span></span>  
 <span data-ttu-id="3f737-139">불가피하게 혼합 모드 인증을 사용하는 경우 SQL Server 로그인을 만들어야 합니다. 이 로그인은 SQL Server에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f737-139">If you must use mixed mode authentication, you must create SQL Server logins, which are stored in SQL Server.</span></span> <span data-ttu-id="3f737-140">그런 다음 런타임에 SQL Server 사용자 이름과 암호를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f737-140">You then have to supply the SQL Server user name and password at run time.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3f737-141">SQL Server는 `sa`("system administrator"의 약어)라는 SQL Server 로그인으로 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f737-141">SQL Server installs with a SQL Server login named `sa` (an abbreviation of "system administrator").</span></span> <span data-ttu-id="3f737-142">따라서 `sa` 로그인에는 강력한 암호를 지정해야 하고 응용 프로그램에는 `sa` 로그인을 사용하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f737-142">Assign a strong password to the `sa` login and do not use the `sa` login in your application.</span></span> <span data-ttu-id="3f737-143">`sa` 로그인은 전체 서버에 대해 취소할 수 없는 관리 자격 증명을 가지는 `sysadmin` 고정 서버 역할에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f737-143">The `sa` login maps to the `sysadmin` fixed server role, which has irrevocable administrative credentials on the whole server.</span></span> <span data-ttu-id="3f737-144">따라서 공격자가 sa(시스템 관리자)로 액세스할 경우 입을 수 있는 피해는 상상을 초월합니다.</span><span class="sxs-lookup"><span data-stu-id="3f737-144">There are no limits to the potential damage if an attacker gains access as a system administrator.</span></span> <span data-ttu-id="3f737-145">Windows `BUILTIN\Administrators` 그룹(로컬 관리자 그룹)의 모든 멤버는 기본적으로 `sysadmin` 역할의 멤버이지만 이 역할에서 멤버를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f737-145">All members of the Windows `BUILTIN\Administrators` group (the local administrator's group) are members of the `sysadmin` role by default, but can be removed from that role.</span></span>  
  
 <span data-ttu-id="3f737-146">SQL Server에서 실행 되는 SQL Server 로그인에 대 한 Windows 암호 정책 메커니즘을 제공 [!INCLUDE[winxpsvr](../../../../../includes/winxpsvr-md.md)] 또는 이후 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="3f737-146">SQL Server provides Windows password policy mechanisms for SQL Server logins when it is running on [!INCLUDE[winxpsvr](../../../../../includes/winxpsvr-md.md)] or later versions.</span></span> <span data-ttu-id="3f737-147">암호 복잡성 정책은 가능한 암호의 수를 늘려 무차별 암호 대입 공격(brute force attack)을 방지하도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3f737-147">Password complexity policies are designed to deter brute force attacks by increasing the number of possible passwords.</span></span> <span data-ttu-id="3f737-148">SQL Server에서 사용 되는 동일한 복잡성 및 만료 정책을 적용할 수 [!INCLUDE[winxpsvr](../../../../../includes/winxpsvr-md.md)] SQL Server 내에서 사용 된 암호입니다.</span><span class="sxs-lookup"><span data-stu-id="3f737-148">SQL Server can apply the same complexity and expiration policies used in [!INCLUDE[winxpsvr](../../../../../includes/winxpsvr-md.md)] to passwords used inside SQL Server.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3f737-149">사용자 입력의 연결 문자열 연결로 인해 문자열 삽입 공격에 노출될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f737-149">Concatenating connection strings from user input can leave you vulnerable to a connection string injection attack.</span></span> <span data-ttu-id="3f737-150"><xref:System.Data.SqlClient.SqlConnectionStringBuilder>를 사용하면 런타임에 구문상 유효한 연결 문자열을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f737-150">Use the <xref:System.Data.SqlClient.SqlConnectionStringBuilder> to create syntactically valid connection strings at run time.</span></span> <span data-ttu-id="3f737-151">자세한 내용은 참조 [연결 문자열 작성기](../../../../../docs/framework/data/adonet/connection-string-builders.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3f737-151">For more information, see [Connection String Builders](../../../../../docs/framework/data/adonet/connection-string-builders.md).</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="3f737-152">외부 리소스</span><span class="sxs-lookup"><span data-stu-id="3f737-152">External Resources</span></span>  
 <span data-ttu-id="3f737-153">자세한 내용은 다음 리소스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3f737-153">For more information, see the following resources.</span></span>  
  
|<span data-ttu-id="3f737-154">리소스</span><span class="sxs-lookup"><span data-stu-id="3f737-154">Resource</span></span>|<span data-ttu-id="3f737-155">설명</span><span class="sxs-lookup"><span data-stu-id="3f737-155">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="3f737-156">[보안 주체](http://msdn.microsoft.com/library/bb543165.aspx) SQL Server 온라인 설명서의</span><span class="sxs-lookup"><span data-stu-id="3f737-156">[Principals](http://msdn.microsoft.com/library/bb543165.aspx) in SQL Server Books Online</span></span>|<span data-ttu-id="3f737-157">로그인 및 SQL Server의 다른 보안 주체에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f737-157">Describes logins and other security principals in SQL Server.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3f737-158">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3f737-158">See Also</span></span>  
 [<span data-ttu-id="3f737-159">ADO.NET 응용 프로그램 보안</span><span class="sxs-lookup"><span data-stu-id="3f737-159">Securing ADO.NET Applications</span></span>](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [<span data-ttu-id="3f737-160">SQL Server의 응용 프로그램 보안 시나리오</span><span class="sxs-lookup"><span data-stu-id="3f737-160">Application Security Scenarios in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 [<span data-ttu-id="3f737-161">데이터 소스에 연결</span><span class="sxs-lookup"><span data-stu-id="3f737-161">Connecting to a Data Source</span></span>](../../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)  
 [<span data-ttu-id="3f737-162">연결 문자열</span><span class="sxs-lookup"><span data-stu-id="3f737-162">Connection Strings</span></span>](../../../../../docs/framework/data/adonet/connection-strings.md)  
 [<span data-ttu-id="3f737-163">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="3f737-163">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
