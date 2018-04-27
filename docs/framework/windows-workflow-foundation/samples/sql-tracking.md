---
title: SQL 추적
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bcaebeb1-b9e5-49e8-881b-e49af66fd341
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2eeb5cf57e6efac77de4a76fe8131189273d5438
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2018
---
# <a name="sql-tracking"></a><span data-ttu-id="b1b25-102">SQL 추적</span><span class="sxs-lookup"><span data-stu-id="b1b25-102">SQL Tracking</span></span>
<span data-ttu-id="b1b25-103">이 샘플에서는 SQL 데이터베이스에 추적 레코드를 기록하는 사용자 지정 SQL 추적 참가자를 작성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b1b25-103">This sample demonstrates how to write a custom SQL tracking participant, that writes tracking records to a SQL database.</span></span> <span data-ttu-id="b1b25-104">Windows WF (Workflow Foundation) 워크플로 워크플로 인스턴스 실행에 추적을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1b25-104">Windows Workflow Foundation (WF) provides workflow tracking to gain visibility into the execution of a workflow instance.</span></span> <span data-ttu-id="b1b25-105">추적 런타임에서는 워크플로를 실행하는 동안 워크플로 추적 레코드를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="b1b25-105">The tracking runtime emits workflow tracking records during the execution of the workflow.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="b1b25-106"> 워크플로 추적을 참조 하세요. [워크플로 추적 및 트레이싱](../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b1b25-106"> workflow tracking, see [Workflow Tracking and Tracing](../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md).</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="b1b25-107">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="b1b25-107">To use this sample</span></span>  
  
1.  <span data-ttu-id="b1b25-108">SQL Server 2008 또는 SQL Server 2008 Express 이상 버전이 설치되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b1b25-108">Verify you have SQL Server 2008, SQL Server 2008 Express or newer installed.</span></span> <span data-ttu-id="b1b25-109">샘플과 함께 제공되는 스크립트에서는 로컬 컴퓨터에 SQL Express 인스턴스가 사용되는 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="b1b25-109">The scripts packaged with the sample assume the use of a SQL Express instance on your local computer.</span></span> <span data-ttu-id="b1b25-110">로컬 컴퓨터에 다른 인스턴스를 사용하고 있으면 샘플을 실행하기 전에 데이터베이스 관련 스크립트를 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1b25-110">If you have a different instance please modify the database-related scripts before running the sample.</span></span>  
  
2.  <span data-ttu-id="b1b25-111">스크립트 디렉터리(\WF\Basic\Tracking\SqlTracking\CS\Scripts)에서 Trackingsetup.cmd를 실행하여 SQL Server 추적 데이터베이스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b1b25-111">Create the SQL Server tracking database by running Trackingsetup.cmd in the scripts directory (\WF\Basic\Tracking\SqlTracking\CS\Scripts).</span></span> <span data-ttu-id="b1b25-112">이렇게 하면 TrackingSample이라는 데이터베이스가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1b25-112">This creates a database called TrackingSample.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b1b25-113">이 스크립트에서는 SQL Express의 기본 인스턴스를 기반으로 데이터베이스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b1b25-113">The script creates the database on the default instance of SQL Express.</span></span> <span data-ttu-id="b1b25-114">다른 데이터베이스 인스턴스를 기반으로 이를 설치하려면 Trackingsetup.cmd 스크립트를 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="b1b25-114">If you want to install it on a different database instance, edit the Trackingsetup.cmd script.</span></span>  
  
3.  <span data-ttu-id="b1b25-115">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 SqlTrackingSample.sln을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b1b25-115">Open SqlTrackingSample.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
4.  <span data-ttu-id="b1b25-116">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="b1b25-116">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
5.  <span data-ttu-id="b1b25-117">F5 키를 눌러 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b1b25-117">Press F5 to run the application.</span></span>  
  
     <span data-ttu-id="b1b25-118">브라우저 창이 열리고 응용 프로그램의 디렉터리 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1b25-118">The browser window opens and shows the directory listing for the application.</span></span>  
  
6.  <span data-ttu-id="b1b25-119">브라우저에서 StockPriceService.xamlx를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b1b25-119">In the browser, click StockPriceService.xamlx.</span></span>  
  
7.  <span data-ttu-id="b1b25-120">브라우저에 StockPriceService 페이지가 표시됩니다. 이 페이지에는 로컬 서비스 WSDL 주소가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1b25-120">The browser displays the StockPriceService page, which contains the local service WSDL address.</span></span> <span data-ttu-id="b1b25-121">이 주소를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="b1b25-121">Copy this address.</span></span>  
  
     <span data-ttu-id="b1b25-122">로컬 서비스 WSDL 주소의 예로 http://localhost:65193/StockPriceService.xamlx?wsdl합니다.</span><span class="sxs-lookup"><span data-stu-id="b1b25-122">An example of the local service WSDL address is http://localhost:65193/StockPriceService.xamlx?wsdl.</span></span>  
  
8.  <span data-ttu-id="b1b25-123">[!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)]를 사용하여 WCF 테스트 클라이언트(WcfTestClient.exe)를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b1b25-123">Using [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], run the WCF test client (WcfTestClient.exe).</span></span> <span data-ttu-id="b1b25-124">이는 Microsoft Visual Studio 10.0\Common7\IDE 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1b25-124">It is located in the Microsoft Visual Studio 10.0\Common7\IDE directory.</span></span>  
  
9. <span data-ttu-id="b1b25-125">WCF 테스트 클라이언트에서 클릭는 **파일** 메뉴와 선택 **서비스 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="b1b25-125">In the WCF test client, click the **File** menu and select **Add Service**.</span></span> <span data-ttu-id="b1b25-126">로컬 서비스 주소를 텍스트 상자에 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="b1b25-126">Paste the local service address in the textbox.</span></span> <span data-ttu-id="b1b25-127">클릭 **확인** 는 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="b1b25-127">Click **OK** to close the dialog.</span></span>  
  
10. <span data-ttu-id="b1b25-128">WCF 테스트 클라이언트에서 두 번 클릭 **GetStockPrice**합니다.</span><span class="sxs-lookup"><span data-stu-id="b1b25-128">In the WCF test client, double click **GetStockPrice**.</span></span> <span data-ttu-id="b1b25-129">열립니다는 `GetStockPrice` 값을 입력 한 매개 변수를 사용 하는 작업 `Contoso` 클릭 **Invoke**합니다.</span><span class="sxs-lookup"><span data-stu-id="b1b25-129">This opens the `GetStockPrice` operation that takes one parameter, type in the value `Contoso` and click **Invoke**.</span></span>  
  
11. <span data-ttu-id="b1b25-130">내보낸 추적 레코드가 SQL 데이터베이스에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1b25-130">The emitted tracking records are written to a SQL database.</span></span> <span data-ttu-id="b1b25-131">추적 레코드를 보려면 SQL Management Studio에서 TrackingSample 데이터베이스를 열고 테이블을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b1b25-131">To view the tracking records, open the TrackingSample database in SQL Management Studio and navigate to the tables.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="b1b25-132"> SQL Server Management Studio 참조 [SQL Server Management Studio 소개](http://go.microsoft.com/fwlink/?LinkId=165645)합니다.</span><span class="sxs-lookup"><span data-stu-id="b1b25-132"> SQL Server Management Studio, see [Introducing SQL Server Management Studio](http://go.microsoft.com/fwlink/?LinkId=165645).</span></span> <span data-ttu-id="b1b25-133">SQL Server 2008 Management Studio Express를 다운로드할 수 있습니다 [여기](http://go.microsoft.com/fwlink/?LinkId=180520)합니다.</span><span class="sxs-lookup"><span data-stu-id="b1b25-133">SQL Server 2008 Management Studio Express can be downloaded [here](http://go.microsoft.com/fwlink/?LinkId=180520).</span></span> <span data-ttu-id="b1b25-134">테이블에 대해 선택 쿼리를 실행하면 해당 테이블에 저장되어 있는 추적 레코드 내의 데이터가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1b25-134">Running a select query on the tables displays the data within the tracking records stored in the respective tables.</span></span>  
  
#### <a name="to-uninstall-the-sample"></a><span data-ttu-id="b1b25-135">샘플을 제거하려면</span><span class="sxs-lookup"><span data-stu-id="b1b25-135">To uninstall the sample</span></span>  
  
1.  <span data-ttu-id="b1b25-136">샘플 디렉터리(\WF\Basic\Tracking\SqlTracking)에서 Trackingcleanup.cmd 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b1b25-136">Run theTrackingcleanup.cmd script in the sample directory (\WF\Basic\Tracking\SqlTracking).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b1b25-137">Trackingcleanup.cmd가 로컬 컴퓨터 SQL Express에서 데이터베이스를 삭제하려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="b1b25-137">The Trackingcleanup.cmd attempts to delete the database in your local computer SQL Express.</span></span> <span data-ttu-id="b1b25-138">다른 SQL Server 인스턴스를 사용하는 경우 Trackingcleanup.cmd를 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="b1b25-138">If you are using another SQL server instance, edit Trackingcleanup.cmd.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b1b25-139">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1b25-139">The samples may already be installed on your computer.</span></span> <span data-ttu-id="b1b25-140">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="b1b25-140">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="b1b25-141">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="b1b25-141">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b1b25-142">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1b25-142">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Tracking\SqlTracking`  
  
## <a name="see-also"></a><span data-ttu-id="b1b25-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b1b25-143">See Also</span></span>  
 [<span data-ttu-id="b1b25-144">AppFabric 모니터링 샘플</span><span class="sxs-lookup"><span data-stu-id="b1b25-144">AppFabric Monitoring Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193959)
