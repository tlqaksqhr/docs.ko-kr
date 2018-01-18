---
title: "샘플 데이터베이스 다운로드(LINQ to DataSet)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eb42a7af-d410-4b7f-b4a8-13c72ce6fd09
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: c8c1c2dabb13393764ca8b1fd9c1a717b9e2527e
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="downloading-sample-databases-linq-to-dataset"></a><span data-ttu-id="ce76a-102">샘플 데이터베이스 다운로드(LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="ce76a-102">Downloading Sample Databases (LINQ to DataSet)</span></span>
<span data-ttu-id="ce76a-103">샘플 및 연습에는 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 설명서 AdventureWorks 예제 데이터베이스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce76a-103">The samples and walkthroughs in the [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] documentation use the AdventureWorks sample database.</span></span> <span data-ttu-id="ce76a-104">이 제품은 Microsoft 다운로드 사이트에서 무료로 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce76a-104">You can download this product free of charge from the Microsoft download site.</span></span> <span data-ttu-id="ce76a-105">[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 설명서의 샘플과 연습에서는 SQL Server를 데이터 저장소로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ce76a-105">The samples and walkthroughs in the [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] documentation use SQL Server as the data store.</span></span> <span data-ttu-id="ce76a-106">SQL Server 대신 무료로 사용할 수 있는 SQL Server Express Edition을 데이터 저장소로 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce76a-106">SQL Server Express Edition, which is available without charge, can also be used as the data store instead of SQL Server.</span></span>  
  
## <a name="downloading-and-installing-the-adventureworks-database"></a><span data-ttu-id="ce76a-107">AdventureWorks 데이터베이스 다운로드 및 설치</span><span class="sxs-lookup"><span data-stu-id="ce76a-107">Downloading and Installing the AdventureWorks Database</span></span>  
  
#### <a name="to-download-and-install-the-adventureworks-sample-database-for-sql-server"></a><span data-ttu-id="ce76a-108">SQL Server용 AdventureWorks 샘플 데이터베이스를 다운로드하고 설치하려면</span><span class="sxs-lookup"><span data-stu-id="ce76a-108">To download and install the AdventureWorks sample database for SQL Server</span></span>  
  
1.  <span data-ttu-id="ce76a-109">Internet Explorer를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ce76a-109">Open Internet Explorer.</span></span>  
  
2.  <span data-ttu-id="ce76a-110">이동 하 여 [SQL Server 2005 예제 및 예제 데이터베이스](http://go.microsoft.com/fwlink/?linkid=31046) 웹 사이트입니다.</span><span class="sxs-lookup"><span data-stu-id="ce76a-110">Go to the [SQL Server 2005 Samples and Sample Databases](http://go.microsoft.com/fwlink/?linkid=31046) Web site.</span></span>  
  
3.  <span data-ttu-id="ce76a-111">지침에 따라 프로세서 유형에 해당하는 AdventureWorks 샘플 데이터베이스(예: AdventureWorksDB.msi)를 다운로드하고 .MSI 파일을 로컬 컴퓨터에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="ce76a-111">Follow the instructions for downloading the AdventureWorks sample database for your processor type (such as AdventureWorksDB.msi), and save the .MSI file to your local computer.</span></span>  
  
4.  <span data-ttu-id="ce76a-112">다운로드한 파일이나 SQL Server 설치 프로그램을 실행하는 동안 이전 버전의 AdventureWorks가 설치되어 있으면 AdventureWorks.msi를 실행하기 전에 이전 버전을 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce76a-112">If you have a previous version of AdventureWorks installed from the download or during the SQL Server setup, you must remove it before running AdventureWorks.msi.</span></span>  
  
#### <a name="to-remove-a-previous-download-of-an-adventureworks-sample-database"></a><span data-ttu-id="ce76a-113">AdventureWorks 샘플 데이터베이스의 이전 다운로드를 제거하려면</span><span class="sxs-lookup"><span data-stu-id="ce76a-113">To remove a previous download of an AdventureWorks sample database</span></span>  
  
1.  <span data-ttu-id="ce76a-114">AdventureWorks 또는 AdventureWorksDW 데이터베이스를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="ce76a-114">Drop the AdventureWorks or AdventureWorksDW database.</span></span>  
  
2.  <span data-ttu-id="ce76a-115">**프로그램 추가 / 제거**선택, **AdventureWorksDB** 또는 **AdventureWorksBI** 클릭 **제거**합니다.</span><span class="sxs-lookup"><span data-stu-id="ce76a-115">From **Add or Remove Programs**, select **AdventureWorksDB** or **AdventureWorksBI** and click **Remove**.</span></span>  
  
#### <a name="to-remove-an-adventureworks-sample-database-previously-installed-using-setup"></a><span data-ttu-id="ce76a-116">설치 프로그램을 사용하여 이전에 설치된 AdventureWorks 샘플 데이터베이스를 제거하려면</span><span class="sxs-lookup"><span data-stu-id="ce76a-116">To remove an AdventureWorks sample database previously installed using Setup</span></span>  
  
1.  <span data-ttu-id="ce76a-117">AdventureWorks 또는 AdventureWorksDW 데이터베이스를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="ce76a-117">Drop the AdventureWorks or AdventureWorksDW database.</span></span>  
  
2.  <span data-ttu-id="ce76a-118">**프로그램 추가 / 제거**선택, **Microsoft SQL Server 2005** 클릭 **변경**합니다.</span><span class="sxs-lookup"><span data-stu-id="ce76a-118">From **Add or Remove Programs**, select **Microsoft SQL Server 2005** and click **Change**.</span></span>  
  
3.  <span data-ttu-id="ce76a-119">**구성 요소 선택**선택, **워크스테이션 구성 요소** 클릭 하 고 **다음**합니다.</span><span class="sxs-lookup"><span data-stu-id="ce76a-119">From **Component Selection**, select **Workstation Components** and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="ce76a-120">**SQL Server 설치 마법사 시작**, 클릭 **다음**합니다.</span><span class="sxs-lookup"><span data-stu-id="ce76a-120">From **Welcome to the SQL Server Installation Wizard**, click **Next**.</span></span>  
  
5.  <span data-ttu-id="ce76a-121">**시스템 구성 검사**, 클릭 **다음**합니다.</span><span class="sxs-lookup"><span data-stu-id="ce76a-121">From **System Configuration Check**, click **Next**.</span></span>  
  
6.  <span data-ttu-id="ce76a-122">**인스턴스 변경 또는 제거**, 클릭 **설치 구성 요소 변경**합니다.</span><span class="sxs-lookup"><span data-stu-id="ce76a-122">From **Change or Remove Instance**, click **Change Installed Components**.</span></span>  
  
7.  <span data-ttu-id="ce76a-123">**기능 선택**를 확장 하 고는 **문서, 예제 및 예제 데이터베이스** 노드.</span><span class="sxs-lookup"><span data-stu-id="ce76a-123">From **Feature Selection**, expand the **Documentation, Samples, and Sample Databases** node.</span></span>  
  
8.  <span data-ttu-id="ce76a-124">선택 **예제 코드 및 응용 프로그램**합니다.</span><span class="sxs-lookup"><span data-stu-id="ce76a-124">Select **Sample Code and Applications**.</span></span> <span data-ttu-id="ce76a-125">확장 **예제 데이터베이스**, 샘플 데이터베이스를 제거할 수 있으며, 선택 선택 **모든 기능을 사용할 수 없게 됩니다**합니다.</span><span class="sxs-lookup"><span data-stu-id="ce76a-125">Expand **Sample Databases**, select the sample database to be removed, and select **Entire feature will be unavailable**.</span></span> <span data-ttu-id="ce76a-126">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ce76a-126">Click **Next**.</span></span>  
  
9. <span data-ttu-id="ce76a-127">클릭 **설치** 설치 마법사를 마칩니다.</span><span class="sxs-lookup"><span data-stu-id="ce76a-127">Click **Install** and finish the installation wizard.</span></span>  
  
#### <a name="to-attach-the-adventureworks-sample-database-files-to-an-instance-of-sql-server"></a><span data-ttu-id="ce76a-128">AdventureWorks 샘플 데이터베이스 파일을 SQL Server 인스턴스에 연결하려면</span><span class="sxs-lookup"><span data-stu-id="ce76a-128">To attach the AdventureWorks sample database files to an instance of SQL Server</span></span>  
  
1.  <span data-ttu-id="ce76a-129">파일 예제 데이터베이스 설치 관리자 파일을 다운로드 한 후 두 번 클릭은 **AdventureWorksDB.msi** 파일 (또는 다운로드 한 파일)는 데이터베이스를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce76a-129">After the file sample database installer file has downloaded, double-click the **AdventureWorksDB.msi** file (or the file you downloaded) to install the database.</span></span> <span data-ttu-id="ce76a-130">기본적으로 데이터베이스는 c:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data에 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce76a-130">By default, the database is installed at c:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data.</span></span>  
  
2.  <span data-ttu-id="ce76a-131">다음 스크립트 SQLCMD 또는 SQL Server Management Studio를 실행하여 AdventureWorks 데이터베이스 파일을 SQL Server 인스턴스에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="ce76a-131">Attach the AdventureWorks database files to an instance of SQL Server by executing the following script SQLCMD or SQL Server Management Studio:</span></span>  
  
    ```  
    exec sp_attach_db @dbname=N'AdventureWorks', @filename1=N'C:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data\AdventureWorks_Data.mdf', @filename2=N'C:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data\AdventureWorks_log.ldf'  
    ```  
  
     <span data-ttu-id="ce76a-132">이러한 파일을 다른 드라이브나 디렉터리에 설치한 경우에는 `sp_attach_db` 저장 프로시저를 실행하기 전에 경로를 올바르게 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce76a-132">If you have installed these files to a different drive or directory, you must revise the paths appropriately before you execute the `sp_attach_db` stored procedure.</span></span>  
  
## <a name="downloading-sql-server-express-edition"></a><span data-ttu-id="ce76a-133">SQL Server Express Edition 다운로드</span><span class="sxs-lookup"><span data-stu-id="ce76a-133">Downloading SQL Server Express Edition</span></span>  
 <span data-ttu-id="ce76a-134">[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 단원의 샘플과 연습에서는 SQL Server 2005를 데이터 저장소로 사용하지만 SQL Server Express Edition을 대신 사용하도록 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce76a-134">The samples and walkthroughs in the [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] section use SQL Server 2005 as the data store but can be modified to use SQL Server Express Edition, instead.</span></span> <span data-ttu-id="ce76a-135">SQL Server Express Edition은 무료로 제공되며 응용 프로그램과 함께 재배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce76a-135">SQL Server Express Edition is available without charge, and you can redistribute it with applications.</span></span> <span data-ttu-id="ce76a-136">[!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]를 사용하고 있는 경우에는 SQL Server Express Edition이 Pro 이상의 에디션에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce76a-136">If you are using [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], SQL Server Express Edition is included in the Pro and higher editions.</span></span>  
  
#### <a name="to-download-and-install-sql-server-express-edition"></a><span data-ttu-id="ce76a-137">SQL Server Express Edition을 다운로드하여 설치하려면</span><span class="sxs-lookup"><span data-stu-id="ce76a-137">To download and install SQL Server Express Edition</span></span>  
  
1.  <span data-ttu-id="ce76a-138">Internet Explorer를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="ce76a-138">Start Internet Explorer.</span></span>  
  
2.  <span data-ttu-id="ce76a-139">이동 하는 [Microsoft SQL Server 2005 Express Edition](http://go.microsoft.com/fwlink/?LinkID=31070) 페이지를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce76a-139">Go to the  [Microsoft SQL Server 2005 Express Edition](http://go.microsoft.com/fwlink/?LinkID=31070) download page.</span></span>  
  
3.  <span data-ttu-id="ce76a-140">웹 사이트의 설치 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="ce76a-140">Follow the installation instructions on the Web site.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce76a-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ce76a-141">See Also</span></span>  
 [<span data-ttu-id="ce76a-142">시작</span><span class="sxs-lookup"><span data-stu-id="ce76a-142">Getting Started</span></span>](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)
