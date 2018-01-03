---
title: "방법: IIS에서 실행되는 WCF Data Services 개발"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, developing
- WCF Data Services, deploying
- WCF Data Services, hosting
ms.assetid: f6f768c5-4989-49e3-a36f-896ab4ded86e
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b93b6e8b6e687f2e39fd5792aba08eaa47fa29fd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-develop-a-wcf-data-service-running-on-iis"></a><span data-ttu-id="317a5-102">방법: IIS에서 실행되는 WCF Data Services 개발</span><span class="sxs-lookup"><span data-stu-id="317a5-102">How to: Develop a WCF Data Service Running on IIS</span></span>
<span data-ttu-id="317a5-103">이 항목에서는 사용 하는 방법을 보여 줍니다. [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 인터넷 정보 서비스 (IIS)에서 실행 중인 ASP.NET 웹 응용 프로그램에 의해 호스팅되는 Northwind 샘플 데이터베이스를 기반으로 하는 데이터 서비스를 만드는 합니다.</span><span class="sxs-lookup"><span data-stu-id="317a5-103">This topic shows how to use [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] to create a data service that is based on the Northwind sample database that is hosted by an ASP.NET Web application that is running on Internet Information Services (IIS).</span></span> <span data-ttu-id="317a5-104">ASP.NET 개발 서버에서 실행 되는 ASP.NET 웹 응용 프로그램으로 동일한 Northwind 데이터 서비스를 만드는 방법의 예제를 보려면는 [WCF Data Services 퀵 스타트](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="317a5-104">For an example of how to create the same Northwind data service as an ASP.NET Web application that runs on the ASP.NET Development Server, see the [WCF Data Services quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="317a5-105">Northwind 데이터 서비스를 만들려면 로컬 컴퓨터에 Northwind 샘플 데이터베이스를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="317a5-105">To create the Northwind data service, you must have installed the Northwind sample database on the local computer.</span></span> <span data-ttu-id="317a5-106">이 샘플 데이터베이스를 다운로드하려면 [SQL Server용 샘플 데이터베이스](http://go.microsoft.com/fwlink/?linkid=24758)다운로드 페이지를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="317a5-106">To download this sample database, see the download page, [Sample Databases for SQL Server](http://go.microsoft.com/fwlink/?linkid=24758).</span></span>  
  
 <span data-ttu-id="317a5-107">이 항목에서는 Entity Framework 공급자를 사용하여 데이터 서비스를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="317a5-107">This topic shows how to create a data service by using the Entity Framework provider.</span></span> <span data-ttu-id="317a5-108">다른 데이터 서비스 공급자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="317a5-108">Other data services providers are available.</span></span> <span data-ttu-id="317a5-109">자세한 내용은 참조 [데이터 서비스 공급자](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="317a5-109">For more information, see [Data Services Providers](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="317a5-110">서비스를 만든 후 데이터 서비스 리소스에 대한 액세스 권한을 명시적으로 부여해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="317a5-110">After you create the service, you must explicitly provide access to data service resources.</span></span> <span data-ttu-id="317a5-111">자세한 내용은 참조 [하는 방법: 데이터 서비스에 대 한 액세스 사용](../../../../docs/framework/data/wcf/how-to-enable-access-to-the-data-service-wcf-data-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="317a5-111">For more information, see [How to: Enable Access to the Data Service](../../../../docs/framework/data/wcf/how-to-enable-access-to-the-data-service-wcf-data-services.md).</span></span>  
  
### <a name="to-create-the-aspnet-web-application-that-runs-on-iis"></a><span data-ttu-id="317a5-112">IIS에서 실행되는 ASP.NET 웹 응용 프로그램을 만들려면</span><span class="sxs-lookup"><span data-stu-id="317a5-112">To create the ASP.NET Web application that runs on IIS</span></span>  
  
1.  <span data-ttu-id="317a5-113">Visual Studio에서에 **파일** 메뉴 선택 **새로**를 선택한 후 **프로젝트**합니다.</span><span class="sxs-lookup"><span data-stu-id="317a5-113">In Visual Studio, on the **File** menu, select **New**, and then select **Project**.</span></span>  
  
2.  <span data-ttu-id="317a5-114">에 **새 프로젝트** 대화 상자에서 Visual Basic 또는 Visual C#의 프로그래밍 언어로 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="317a5-114">In the **New Project** dialog box, select either Visual Basic or Visual C# as the programming language.</span></span>  
  
3.  <span data-ttu-id="317a5-115">에 **템플릿** 창 선택 **ASP.NET 웹 응용 프로그램**합니다.</span><span class="sxs-lookup"><span data-stu-id="317a5-115">In the **Templates** pane, select **ASP.NET Web Application**.</span></span> <span data-ttu-id="317a5-116">참고: Visual Studio Web Developer를 사용하는 경우 새 웹 응용 프로그램 대신 새 웹 사이트를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="317a5-116">Note: If you use Visual Studio Web Developer, you must create a new Web site instead of a new Web application.</span></span>  
  
4.  <span data-ttu-id="317a5-117">형식 `NorthwindService` 프로젝트의 이름으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="317a5-117">Type `NorthwindService` as the name of the project.</span></span>  
  
5.  <span data-ttu-id="317a5-118">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="317a5-118">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="317a5-119">에 **프로젝트** 메뉴 선택 **NorthwindService 속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="317a5-119">On the **Project** menu, select **NorthwindService Properties**.</span></span>  
  
7.  <span data-ttu-id="317a5-120">선택 된 **웹** 탭을 선택한 다음 선택 **로컬 IIS 웹 서버 사용**합니다.</span><span class="sxs-lookup"><span data-stu-id="317a5-120">Select the **Web** tab, and then select **Use Local IIS Web Server**.</span></span>  
  
8.  <span data-ttu-id="317a5-121">클릭 **가상 디렉터리 만들기** 클릭 하 고 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="317a5-121">Click **Create Virtual Directory** and then click **OK**.</span></span>  
  
9. <span data-ttu-id="317a5-122">관리자 권한으로 실행되는 명령 프롬프트에서 운영 체제에 따라 다음 명령 중 하나를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="317a5-122">From the command prompt with administrator privileges, execute one of the following commands (depending on the operating system):</span></span>  
  
    -   <span data-ttu-id="317a5-123">32비트 시스템:</span><span class="sxs-lookup"><span data-stu-id="317a5-123">32-bit systems:</span></span>  
  
        ```console
        "%windir%\Microsoft.NET\Framework\v3.0\Windows Communication Foundation\ServiceModelReg.exe" -i  
        ```  
  
    -   <span data-ttu-id="317a5-124">64비트 시스템:</span><span class="sxs-lookup"><span data-stu-id="317a5-124">64-bit systems:</span></span>  
  
        ```console
        "%windir%\Microsoft.NET\Framework64\v3.0\Windows Communication Foundation\ServiceModelReg.exe" -i  
        ```  
  
     <span data-ttu-id="317a5-125">이렇게 하면 WCF(Windows Communication Foundation)가 컴퓨터에 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="317a5-125">This makes sure that Windows Communication Foundation (WCF) is registered on the computer.</span></span>  
  
10. <span data-ttu-id="317a5-126">관리자 권한으로 실행되는 명령 프롬프트에서 운영 체제에 따라 다음 명령 중 하나를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="317a5-126">From the command prompt with administrator privileges, execute one of the following commands (depending on the operating system):</span></span>  
  
    -   <span data-ttu-id="317a5-127">32비트 시스템:</span><span class="sxs-lookup"><span data-stu-id="317a5-127">32-bit systems:</span></span>  
  
        ```console
        "%windir%\Microsoft.NET\Framework\v4.0.30319\aspnet_regiis.exe" -i -enable  
        ```  
  
    -   <span data-ttu-id="317a5-128">64비트 시스템:</span><span class="sxs-lookup"><span data-stu-id="317a5-128">64-bit systems:</span></span>  
  
        ```console
        "%windir%\Microsoft.NET\Framework64\v4.0.30319\aspnet_regiis.exe" -i -enable  
        ```  
  
     <span data-ttu-id="317a5-129">이렇게 하면 WCF가 컴퓨터에 설치된 후 IIS가 제대로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="317a5-129">This makes sure that IIS runs correctly after WCF has been installed on the computer.</span></span> <span data-ttu-id="317a5-130">또한 IIS를 다시 시작해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="317a5-130">You might have to also restart IIS.</span></span>  
  
11. <span data-ttu-id="317a5-131">ASP.NET 응용 프로그램이 IIS7에서 실행되는 경우 다음 단계도 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="317a5-131">When the ASP.NET application runs on IIS7, you must also perform the following steps:</span></span>  
  
    1.  <span data-ttu-id="317a5-132">IIS 관리자를 열고 아래의 PhotoService 응용 프로그램으로 이동 **기본 웹 사이트**합니다.</span><span class="sxs-lookup"><span data-stu-id="317a5-132">Open IIS Manager and navigate to the PhotoService application under **Default Web Site**.</span></span>  
  
    2.  <span data-ttu-id="317a5-133">**기능 보기**를 두 번 클릭 **인증**합니다.</span><span class="sxs-lookup"><span data-stu-id="317a5-133">In **Features View**, double-click **Authentication**.</span></span>  
  
    3.  <span data-ttu-id="317a5-134">에 **인증** 페이지에서 **익명 인증**합니다.</span><span class="sxs-lookup"><span data-stu-id="317a5-134">On the **Authentication** page, select **Anonymous Authentication**.</span></span>  
  
    4.  <span data-ttu-id="317a5-135">에 **동작** 창에서 클릭 **편집** 보안을 설정 하는 보안 주체는 익명 사용자에서 사이트에 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="317a5-135">In the **Actions** pane, click **Edit** to set the security principal under which anonymous users will connect to the site.</span></span>  
  
    5.  <span data-ttu-id="317a5-136">에 **익명 인증 자격 증명 편집** 대화 상자에서 **응용 프로그램 풀 id**합니다.</span><span class="sxs-lookup"><span data-stu-id="317a5-136">In the **Edit Anonymous Authentication Credentials** dialog box, select **Application pool identity**.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="317a5-137">Network Service 계정을 사용하는 경우 해당 계정과 연결된 모든 내부 네트워크 액세스 권한이 익명 사용자에게 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="317a5-137">When you use the Network Service account, you grant anonymous users all the internal network access associated with that account.</span></span>  
  
12. <span data-ttu-id="317a5-138">SQL Server Management Studio, sqlcmd.exe 유틸리티 또는 Visual Studio의 Transact-SQL 편집기를 사용하여 Northwind 데이터베이스가 연결된 SQL Server 인스턴스에 대해 다음 Transact-SQL 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="317a5-138">By using SQL Server Management Studio, the sqlcmd.exe utility, or the Transact-SQL Editor in Visual Studio, execute the following Transact-SQL command against the instance of SQL Server that has the Northwind database attached:</span></span>  
  
    ```sql  
    CREATE LOGIN [NT AUTHORITY\NETWORK SERVICE] FROM WINDOWS;  
    GO   
    ```  
  
     <span data-ttu-id="317a5-139">이렇게 하면 IIS를 실행하는 데 사용되는 Windows 계정에 대한 로그인이 SQL Server 인스턴스에서 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="317a5-139">This creates a login in the SQL Server instance for the Windows account used to run IIS.</span></span> <span data-ttu-id="317a5-140">이에 따라 IIS에서 SQL Server 인스턴스에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="317a5-140">This enables IIS to connect to the SQL Server instance.</span></span>  
  
13. <span data-ttu-id="317a5-141">Northwind 데이터베이스가 연결된 상태에서 다음 Transact-SQL 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="317a5-141">With the Northwind database attached, execute the following Transact-SQL commands:</span></span>  
  
    ```sql  
    USE Northwind  
    GO  
    CREATE USER [NT AUTHORITY\NETWORK SERVICE]   
    FOR LOGIN [NT AUTHORITY\NETWORK SERVICE] WITH DEFAULT_SCHEMA=[dbo];  
    GO  
    ALTER LOGIN [NT AUTHORITY\NETWORK SERVICE]   
    WITH DEFAULT_DATABASE=[Northwind];   
    GO  
    EXEC sp_addrolemember 'db_datareader', 'NT AUTHORITY\NETWORK SERVICE'  
    GO  
    EXEC sp_addrolemember 'db_datawriter', 'NT AUTHORITY\NETWORK SERVICE'  
    GO   
    ```  
  
     <span data-ttu-id="317a5-142">이렇게 하면 새 로그인에 권한이 부여되어 IIS에서 Northwind 데이터베이스에 있는 데이터를 읽고 Northwind 데이터베이스에 데이터를 쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="317a5-142">This grants rights to the new login, which enables IIS to read data from and write data to the Northwind database.</span></span>  
  
### <a name="to-define-the-data-model"></a><span data-ttu-id="317a5-143">데이터 모델을 정의하려면</span><span class="sxs-lookup"><span data-stu-id="317a5-143">To define the data model</span></span>  
  
1.  <span data-ttu-id="317a5-144">**솔루션 탐색기**ASP.NET 프로젝트의 이름을 마우스 오른쪽 단추로 클릭 한 다음 클릭 **새 항목 추가 합니다.**</span><span class="sxs-lookup"><span data-stu-id="317a5-144">In **Solution Explorer**, right-click the name of the ASP.NET project, and then click **Add New Item.**</span></span>  
  
2.  <span data-ttu-id="317a5-145">에 **새 항목 추가** 대화 상자에서 **ADO.NET 엔터티 데이터 모델**합니다.</span><span class="sxs-lookup"><span data-stu-id="317a5-145">In the **Add New Item** dialog box, select **ADO.NET Entity Data Model**.</span></span>  
  
3.  <span data-ttu-id="317a5-146">데이터 모델의 이름으로 입력 `Northwind.edmx`합니다.</span><span class="sxs-lookup"><span data-stu-id="317a5-146">For the name of the data model, type `Northwind.edmx`.</span></span>  
  
4.  <span data-ttu-id="317a5-147">엔터티 데이터 모델 마법사에서 선택 **데이터베이스에서 생성**, 클릭 하 고 **다음**합니다.</span><span class="sxs-lookup"><span data-stu-id="317a5-147">In the Entity Data Model Wizard, select **Generate from Database**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="317a5-148">다음 단계 중 하나를 수행 하 여 데이터 모델 데이터베이스에 연결 하 고 클릭 **다음**:</span><span class="sxs-lookup"><span data-stu-id="317a5-148">Connect the data model to the database by doing one of the following steps, and then click **Next**:</span></span>  
  
    -   <span data-ttu-id="317a5-149">데이터베이스 연결이 이미 구성 되어 있으면 클릭 **새 연결** 고 새 연결을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="317a5-149">If you do not have a database connection already configured, click **New Connection** and create a new connection.</span></span> <span data-ttu-id="317a5-150">자세한 내용은 참조 [하는 방법: SQL Server 데이터베이스에 대 한 연결 만들기](http://go.microsoft.com/fwlink/?LinkId=123631)합니다.</span><span class="sxs-lookup"><span data-stu-id="317a5-150">For more information, see [How to: Create Connections to SQL Server Databases](http://go.microsoft.com/fwlink/?LinkId=123631).</span></span> <span data-ttu-id="317a5-151">이 [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] 인스턴스에는 Northwind 샘플 데이터베이스가 연결되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="317a5-151">This [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] instance must have the Northwind sample database attached.</span></span>  
  
         <span data-ttu-id="317a5-152">\- 또는 -</span><span class="sxs-lookup"><span data-stu-id="317a5-152">\- or -</span></span>  
  
    -   <span data-ttu-id="317a5-153">Northwind 데이터베이스에 연결할 수 있도록 데이터베이스 연결이 이미 구성되어 있는 경우 연결 목록에서 해당 연결을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="317a5-153">If you have a database connection already configured to connect to the Northwind database, select that connection from the list of connections.</span></span>  
  
6.  <span data-ttu-id="317a5-154">마법사의 마지막 페이지에서 데이터베이스의 모든 테이블에 대한 확인란을 선택하고 뷰 및 저장 프로시저에 대한 확인란의 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="317a5-154">On the final page of the wizard, select the check boxes for all tables in the database, and clear the check boxes for views and stored procedures.</span></span>  
  
7.  <span data-ttu-id="317a5-155">클릭 **마침** 마법사를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="317a5-155">Click **Finish** to close the wizard.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="317a5-156">생성된 이 데이터 모델은 엔터티 형식의 외래 키 속성을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="317a5-156">This generated data model exposes foreign key properties on entity types.</span></span> <span data-ttu-id="317a5-157">Visual Studio 2008을 사용하여 만들어진 데이터 모델에는 이러한 외래 키 속성이 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="317a5-157">Data models created using Visual Studio 2008 do not include these foreign key properties.</span></span> <span data-ttu-id="317a5-158">이 때문에 이 버전의 Northwind 데이터 서비스에 액세스하기 전에 Visual Studio 2008을 사용하여 만들어진 Northwind 데이터 서비스에 액세스하기 위해 만들어진 모든 클라이언트 응용 프로그램의 클라이언트 데이터 서비스 클래스를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="317a5-158">Because of this, you must update the client data service classes of any client applications that were created to access the Northwind data service that was created using Visual Studio 2008 before attempting to access this version of the Northwind data service.</span></span>  
  
### <a name="to-create-the-data-service"></a><span data-ttu-id="317a5-159">데이터 서비스를 만들려면</span><span class="sxs-lookup"><span data-stu-id="317a5-159">To create the data service</span></span>  
  
1.  <span data-ttu-id="317a5-160">**솔루션 탐색기**ASP.NET 프로젝트 이름을 마우스 오른쪽 단추로 클릭 한 다음 클릭 **새 항목 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="317a5-160">In **Solution Explorer**, right-click the name of your ASP.NET project, and then click **Add New Item**.</span></span>  
  
2.  <span data-ttu-id="317a5-161">에 **새 항목 추가** 대화 상자에서 **ADO.NET 데이터 서비스**합니다.</span><span class="sxs-lookup"><span data-stu-id="317a5-161">In the **Add New Item** dialog box, select **ADO.NET Data Service**.</span></span>  
  
3.  <span data-ttu-id="317a5-162">서비스의 이름으로 입력 `Northwind`합니다.</span><span class="sxs-lookup"><span data-stu-id="317a5-162">For the name of the service, type `Northwind`.</span></span>  
  
     <span data-ttu-id="317a5-163">Visual Studio에서 새 서비스의 XML 태그 및 코드 파일이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="317a5-163">Visual Studio creates the XML markup and code files for the new service.</span></span> <span data-ttu-id="317a5-164">기본적으로 코드 편집기 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="317a5-164">By default, the code-editor window opens.</span></span> <span data-ttu-id="317a5-165">**솔루션 탐색기**, 서비스 이름은, 확장명을 갖습니다. svc.cs 또는. svc.vb 합니다.</span><span class="sxs-lookup"><span data-stu-id="317a5-165">In **Solution Explorer**, the service will have the name, Northwind, with the extension .svc.cs or .svc.vb.</span></span>  
  
4.  <span data-ttu-id="317a5-166">데이터 서비스 코드에서 데이터 서비스를 정의하는 클래스 정의의 `/* TODO: put your data source class name here */` 주석을 데이터 모델의 엔터티 컨테이너인 형식(이 경우 `NorthwindEntities`)으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="317a5-166">In the code for the data service, replace the comment `/* TODO: put your data source class name here */` in the definition of the class that defines the data service with the type that is the entity container of the data model, which in this case is `NorthwindEntities`.</span></span> <span data-ttu-id="317a5-167">클래스 정의는 다음과 같이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="317a5-167">The class definition should look this the following:</span></span>  
  
     [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#servicedefinition)]
     [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#servicedefinition)]  
  
## <a name="see-also"></a><span data-ttu-id="317a5-168">참고 항목</span><span class="sxs-lookup"><span data-stu-id="317a5-168">See Also</span></span>  
 [<span data-ttu-id="317a5-169">서비스로 데이터 노출</span><span class="sxs-lookup"><span data-stu-id="317a5-169">Exposing Your Data as a Service</span></span>](../../../../docs/framework/data/wcf/exposing-your-data-as-a-service-wcf-data-services.md)
