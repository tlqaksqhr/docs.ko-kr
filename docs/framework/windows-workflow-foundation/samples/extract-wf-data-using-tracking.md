---
title: 추적을 사용하여 WF 데이터 추출
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e30c68f5-8c6a-495a-bd20-667a4364c68e
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 44e49aa0c9b3b9b53b921fe90838875ab34b7772
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2018
---
# <a name="extract-wf-data-using-tracking"></a><span data-ttu-id="da7ba-102">추적을 사용하여 WF 데이터 추출</span><span class="sxs-lookup"><span data-stu-id="da7ba-102">Extract WF Data using Tracking</span></span>
<span data-ttu-id="da7ba-103">이 샘플에서는 워크플로 추적을 사용하여 활동에서 워크플로 변수와 인수를 추출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="da7ba-103">This sample demonstrates how to use workflow tracking to extract workflow variables and arguments from activities.</span></span> <span data-ttu-id="da7ba-104">또한 여기에서는 추적 레코드에 주석을 추가하고 사용자 지정 추적 레코드 내의 데이터 페이로드를 추출하는 방법도 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="da7ba-104">It also shows the addition of annotations to tracking records and the extraction of data payload within custom tracking records.</span></span> <span data-ttu-id="da7ba-105">이 샘플에서 워크플로의 데이터를 추출하는 데는 ETW(Event Tracing for Windows) 추적 참가자가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="da7ba-105">The sample uses the Event Tracing for Windows (ETW) tracking participant to extract data from the workflow.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="da7ba-106">샘플 세부 정보</span><span class="sxs-lookup"><span data-stu-id="da7ba-106">Sample Details</span></span>  
 <span data-ttu-id="da7ba-107">Windows WF (Workflow Foundation) 워크플로 인스턴스 실행에 추적을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="da7ba-107">Windows Workflow Foundation (WF) provides tracking to gain visibility into the execution of a workflow instance.</span></span> <span data-ttu-id="da7ba-108">추적 런타임에서는 워크플로를 실행하는 동안 워크플로 추적 레코드를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="da7ba-108">The tracking runtime emits workflow tracking records during the execution of the workflow.</span></span> <span data-ttu-id="da7ba-109">워크플로 추적 레코드와 함께 워크플로 인스턴스 내의 데이터를 워크플로에서 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da7ba-109">Along with the workflow tracking records, data within the workflow instance can be extracted from the workflow.</span></span> <span data-ttu-id="da7ba-110">다음 목록에는 추적 레코드로부터 추출할 수 있는 데이터의 형식에 대한 자세한 설명이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da7ba-110">The following list details the types of data that can be extracted from tracking records:</span></span>  
  
1.  <span data-ttu-id="da7ba-111">활동을 실행하는 동안의 활동 및 추적 레코드 내의 워크플로 변수.</span><span class="sxs-lookup"><span data-stu-id="da7ba-111">Workflow variables within an activity and tracking records during activity execution.</span></span>  
  
     <span data-ttu-id="da7ba-112">워크플로 변수를 추출하려면 추출할 변수를 프로필에 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da7ba-112">To extract workflow variables, the variables to be extracted are specified in a profile.</span></span> <span data-ttu-id="da7ba-113">추출할 변수를 지정하는 데는 `ActivityStateQueries`만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da7ba-113">Variables to be extracted can only be specified with `ActivityStateQueries`.</span></span> <span data-ttu-id="da7ba-114">다음 코드 예제에서는 활동으로부터 워크플로 변수를 추출하는 데 사용되는 추적 프로필을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="da7ba-114">The following code example demonstrates a tracking profile used to extract the workflow variable from an activity.</span></span>  
  
    ```xml  
    <activityStateQuery activityName="StockPriceService">  
         <states>  
              <state name="Closed"/>  
         </states>  
         <variables>  
              <variable name="symbol"/>  
         </variables>  
    </activityStateQuery>  
    ```  
  
2.  <span data-ttu-id="da7ba-115">활동 인수 및 활동 상태 추적 레코드.</span><span class="sxs-lookup"><span data-stu-id="da7ba-115">Activity arguments and activity state tracking records.</span></span>  
  
     <span data-ttu-id="da7ba-116">인수는 데이터가 활동을 드나들며 이동하는 방식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="da7ba-116">Arguments define the way data flows in or out of an activity.</span></span> <span data-ttu-id="da7ba-117">추출할 인수를 지정하는 데는 <xref:System.Activities.Tracking.ActivityStateQuery>를 사용합니다. 다음 코드 예제에서는 `Value` 인수를 추출하는 추적 프로필을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="da7ba-117">Arguments to be extracted are specified using an <xref:System.Activities.Tracking.ActivityStateQuery>.The following code example is a tracking profile that extracts the `Value` argument.</span></span>  
  
    ```xml  
    <activityStateQuery activityName="GetStockPrice">  
         <states>  
              <state name="Closed"/>  
         </states>  
         <arguments>  
              <argument name="Value"/>  
         </arguments>  
    </activityStateQuery>  
    ```  
  
3.  <span data-ttu-id="da7ba-118">주석은 내보낸 임의의 추적 레코드에 추가할 수 있는 키/값 쌍입니다.</span><span class="sxs-lookup"><span data-stu-id="da7ba-118">Annotations are key/value pairs that can be added to any tracking record that is emitted.</span></span>  
  
     <span data-ttu-id="da7ba-119">주석은 추적 레코드에 대한 태그 설정 메커니즘 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="da7ba-119">Annotations serve as a tagging mechanism for tracking records.</span></span> <span data-ttu-id="da7ba-120">주석은 추적 프로필을 통해 추적 레코드에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="da7ba-120">Annotations are added to tracking records through a tracking profile.</span></span> <span data-ttu-id="da7ba-121">주석을 추가할 수 있는 워크플로 추적 쿼리의 유형에는 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="da7ba-121">Annotations can be added to any type of a workflow tracking query.</span></span> <span data-ttu-id="da7ba-122">다음 코드 예제에는 추적 레코드에 주석을 추가하는 방법을 보여 주는 추적 프로필이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da7ba-122">The following code example is a tracking profile that shows how an annotation can be added to a tracking record.</span></span>  
  
    ```xml  
    <workflowInstanceQuery>  
         <states>  
              <state name="Started"/>  
         </states>  
         <annotations>  
              <annotation name="StockPriceWorkflow" value="Begin"/>  
         </annotations>  
    </workflowInstanceQuery>  
    ```  
  
4.  <span data-ttu-id="da7ba-123">사용자 지정 추적 레코드는 사용자 정의 활동으로부터 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="da7ba-123">Custom tracking records are emitted from user-defined activities.</span></span>  
  
     <span data-ttu-id="da7ba-124">사용자 지정 추적 레코드는 이 활동 내에 정의된 페이로드 데이터를 지닐 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da7ba-124">Custom tracking records can carry payload data defined within this activity.</span></span> <span data-ttu-id="da7ba-125">추적 프로필에서 사용자 지정 추적 레코드를 구독하면 추적 레코드 내의 페이로드를 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da7ba-125">Subscribing for custom tracking records in a tracking profile allows the extraction of the payload within the tracking record.</span></span> <span data-ttu-id="da7ba-126">사용자 지정 추적 레코드는 사용자 지정 <xref:System.Activities.Tracking.TrackingQuery>를 사용하여 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da7ba-126">The custom tracking records can be extracted with custom a <xref:System.Activities.Tracking.TrackingQuery>.</span></span> <span data-ttu-id="da7ba-127">다음 코드 예제에서는 사용자 지정 추적 레코드를 해당 페이로드와 함께 추출하는 추적 프로필을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="da7ba-127">The following code example is a tracking profile that extracts a custom tracking record along with its payload.</span></span>  
  
    ```xml  
    <customTrackingQuery name="QuoteLookupEvent" activityName="GetStockPrice"/>  
    ```  
  
 <span data-ttu-id="da7ba-128">이 샘플에서는 Web.config에 지정된 프로필을 사용하여 변수, 인수 및 사용자 지정 레코드를 추출하고 주석을 추가하는 방법을 보여 줍니다. 샘플 워크플로 서비스에 대해 추적 기능을 사용하기 위해 `<etwTracking>` 동작 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="da7ba-128">The sample demonstrates the extraction of a variables, arguments, custom records and adding annotations using a profile specified in a Web.config. Tracking is enabled on the sample workflow service by adding an `<etwTracking>` behavior element.</span></span> <span data-ttu-id="da7ba-129">다음 코드 예제에서는 `ExtractWorkflowVariables` 추적 프로필에 대한 추적을 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="da7ba-129">The following code example enables tracking for the `ExtractWorkflowVariables` tracking profile.</span></span>  
  
```xml  
<serviceBehaviors>  
     <behavior>  
               <etwTracking profileName="ExtractWorkflowVariables"/>  
     </behavior>  
</serviceBehaviors>  
```  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="da7ba-130">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="da7ba-130">To use this sample</span></span>  
  
1.  <span data-ttu-id="da7ba-131">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]을 사용하여 WFStockPriceApplication.sln 솔루션 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="da7ba-131">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the WFStockPriceApplication.sln solution file.</span></span>  
  
2.  <span data-ttu-id="da7ba-132">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="da7ba-132">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="da7ba-133">F5 키를 눌러 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="da7ba-133">To run the solution, press F5.</span></span>  
  
     <span data-ttu-id="da7ba-134">브라우저 창이 열리고 응용 프로그램의 디렉터리 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="da7ba-134">The browser window opens and shows the directory listing for the application.</span></span>  
  
4.  <span data-ttu-id="da7ba-135">브라우저에서 StockPriceService.xamlx를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="da7ba-135">In the browser, click StockPriceService.xamlx.</span></span>  
  
5.  <span data-ttu-id="da7ba-136">브라우저에 StockPriceService 페이지가 표시됩니다. 이 페이지에는 로컬 서비스 WSDL 주소가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da7ba-136">The browser displays the StockPriceService page, which contains the local service WSDL address.</span></span> <span data-ttu-id="da7ba-137">이 주소를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="da7ba-137">Copy this address.</span></span>  
  
     <span data-ttu-id="da7ba-138">다음은 로컬 서비스 WSDL 주소의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="da7ba-138">The following example shows a local service WSDL address.</span></span> `http://localhost:53797/StockPriceService.xamlx?wsdl`  
  
6.  <span data-ttu-id="da7ba-139">서비스를 호출하기 전에 이벤트 뷰어를 시작하고 이벤트 로그가 워크플로 서비스에서 내보낸 추적 이벤트를 수신 대기하고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="da7ba-139">Before invoking the service, start Event Viewer and ensure that the event log is listening for tracking events emitted from the workflow service.</span></span>  
  
7.  <span data-ttu-id="da7ba-140">**시작** 메뉴 선택 **관리 도구** 차례로 **이벤트 뷰어**합니다.</span><span class="sxs-lookup"><span data-stu-id="da7ba-140">From the **Start** menu, select **Administrative Tools** and then **Event Viewer**.</span></span>  
  
8.  <span data-ttu-id="da7ba-141">이벤트 뷰어의 트리 뷰에서 이동 **이벤트 뷰어**, **Applications and Services Logs**, 및 **Microsoft**합니다.</span><span class="sxs-lookup"><span data-stu-id="da7ba-141">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, and **Microsoft**.</span></span> <span data-ttu-id="da7ba-142">마우스 오른쪽 단추로 클릭 **Microsoft** 선택 **보기** 차례로 **분석 및 디버그 로그 표시**합니다.</span><span class="sxs-lookup"><span data-stu-id="da7ba-142">Right-click **Microsoft** and select **View** and then **Show Analytic and Debug Logs**.</span></span>  
  
     <span data-ttu-id="da7ba-143">확인 된 **분석 및 디버그 로그 표시** 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="da7ba-143">Ensure that the **Show Analytic and Debug Logs** option is checked.</span></span>  
  
9. <span data-ttu-id="da7ba-144">이벤트 뷰어의 트리 뷰에서 이동 **이벤트 뷰어**, **Applications and Services Logs**, **Microsoft**, **Windows**,  **응용 프로그램 서버-응용 프로그램**합니다.</span><span class="sxs-lookup"><span data-stu-id="da7ba-144">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span> <span data-ttu-id="da7ba-145">마우스 오른쪽 단추로 클릭 **분석** 선택 **로그 사용**합니다.</span><span class="sxs-lookup"><span data-stu-id="da7ba-145">Right-click **Analytic** and select **Enable Log**.</span></span>  
  
10. <span data-ttu-id="da7ba-146">[!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)]를 사용하여 WCF 테스트 클라이언트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="da7ba-146">Using [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], open the WCF test client.</span></span>  
  
     <span data-ttu-id="da7ba-147">WCF 테스트 클라이언트 (WcfTestClient.exe)에 \< [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 설치 폴더 > \Common7\IDE\ 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="da7ba-147">The WCF test client (WcfTestClient.exe) is located in the \<[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] installation folder>\Common7\IDE\ folder.</span></span>  
  
     <span data-ttu-id="da7ba-148">기본 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 설치 폴더는 C:\Program Files\Microsoft Visual Studio 10.0입니다.</span><span class="sxs-lookup"><span data-stu-id="da7ba-148">The default [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] installation folder is C:\Program Files\Microsoft Visual Studio 10.0.</span></span>  
  
11. <span data-ttu-id="da7ba-149">WCF 테스트 클라이언트에서 선택 **서비스 추가** 에서 **파일** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="da7ba-149">In WCF test client, select **Add Service** from the **File** menu.</span></span>  
  
     <span data-ttu-id="da7ba-150">앞서 복사한 로컬 서비스 WSDL 주소를 입력 상자에 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="da7ba-150">Add the local service WSDL address you copied earlier in the input box.</span></span>  
  
12. <span data-ttu-id="da7ba-151">WCF 테스트 클라이언트에서 `GetStockPrice`를 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="da7ba-151">In WCF test client, double-click `GetStockPrice`.</span></span>  
  
     <span data-ttu-id="da7ba-152">그러면 `GetStockPrice` 메서드가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="da7ba-152">This opens the `GetStockPrice` method.</span></span> <span data-ttu-id="da7ba-153">요청에 매개 변수 한 개가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="da7ba-153">The request accepts one parameter.</span></span> <span data-ttu-id="da7ba-154">값을 사용 하 여 **Contoso**합니다.</span><span class="sxs-lookup"><span data-stu-id="da7ba-154">Use the value **Contoso**.</span></span>  
  
13. <span data-ttu-id="da7ba-155">클릭 **호출**합니다.</span><span class="sxs-lookup"><span data-stu-id="da7ba-155">Click **Invoke**.</span></span>  
  
14. <span data-ttu-id="da7ba-156">이벤트 뷰어로 다시 전환한 이동한 **이벤트 뷰어**, **Applications and Services Logs**, **Microsoft**, **Windows**,  **응용 프로그램 서버-응용 프로그램**합니다.</span><span class="sxs-lookup"><span data-stu-id="da7ba-156">Switch back to Event Viewer and navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span> <span data-ttu-id="da7ba-157">마우스 오른쪽 단추로 클릭 **분석** 선택 **새로 고침**합니다.</span><span class="sxs-lookup"><span data-stu-id="da7ba-157">Right-click **Analytic** and select **Refresh**.</span></span> <span data-ttu-id="da7ba-158">워크플로 이벤트의 이벤트 ID 범위는 100-199입니다.</span><span class="sxs-lookup"><span data-stu-id="da7ba-158">The workflow events are in the event ID ranges 100-199.</span></span>  
  
     <span data-ttu-id="da7ba-159">이벤트에 주석, 변수, 인수 및 사용자 지정 추적 레코드가 포함되어 있고 이러한 내용을 이벤트 뷰어에서 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da7ba-159">The events contain the annotations, variables, arguments and custom tracking records that can be viewed in the event viewer.</span></span>  
  
## <a name="cleaning-up-in-the-event-viewer"></a><span data-ttu-id="da7ba-160">이벤트 뷰어 정리</span><span class="sxs-lookup"><span data-stu-id="da7ba-160">Cleaning up in the Event Viewer</span></span>  
 <span data-ttu-id="da7ba-161">이벤트 뷰어에서 다음과 같이 이벤트 로그의 분석 채널을 정리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da7ba-161">The analytic channel in the event log can be cleaned up in the Event Viewer by doing the following.</span></span>  
  
#### <a name="to-clean-up-optional"></a><span data-ttu-id="da7ba-162">정리하려면(옵션)</span><span class="sxs-lookup"><span data-stu-id="da7ba-162">To clean up (Optional)</span></span>  
  
1.  <span data-ttu-id="da7ba-163">이벤트 뷰어를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="da7ba-163">Open Event Viewer.</span></span>  
  
2.  <span data-ttu-id="da7ba-164">로 이동 **이벤트 뷰어**, **Applications and Services Logs**, **Microsoft**, **Windows**, **응용 프로그램 서버-응용 프로그램**합니다.</span><span class="sxs-lookup"><span data-stu-id="da7ba-164">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span> <span data-ttu-id="da7ba-165">마우스 오른쪽 단추로 클릭 **분석** 선택 **로그 사용 안 함**합니다.</span><span class="sxs-lookup"><span data-stu-id="da7ba-165">Right-click **Analytic** and select **Disable Log**.</span></span>  
  
3.  <span data-ttu-id="da7ba-166">로 이동 **이벤트 뷰어**, **Applications and Services Logs**, **Microsoft**, **Windows**, **응용 프로그램 서버-응용 프로그램**합니다.</span><span class="sxs-lookup"><span data-stu-id="da7ba-166">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span> <span data-ttu-id="da7ba-167">마우스 오른쪽 단추로 클릭 **분석** 선택 **로그 지우기**합니다.</span><span class="sxs-lookup"><span data-stu-id="da7ba-167">Right-click **Analytic** and select **Clear Log**.</span></span>  
  
     <span data-ttu-id="da7ba-168">선택 된 **지우기** 이벤트를 해결 하는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="da7ba-168">Choose the **Clear** option to clear the events.</span></span>  
  
## <a name="known-issue"></a><span data-ttu-id="da7ba-169">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="da7ba-169">Known Issue</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="da7ba-170">ETW 이벤트가 디코딩되지 않을 수 있으며, 이는 이벤트 뷰어와 관련하여 알려진 문제입니다.</span><span class="sxs-lookup"><span data-stu-id="da7ba-170">There is a known issue in the Event Viewer where it may fail to decode ETW events.</span></span> <span data-ttu-id="da7ba-171">다음과 같은 오류 메시지가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da7ba-171">You may see an error message that looks like the following.</span></span>  
>   
>  `The description for Event ID <id> from source Microsoft-Windows-Application Server-Applications cannot be found. Either the component that raises this event is not installed on your local computer or the installation is corrupted. You can install or repair the component on the local computer.`  
>   
>  <span data-ttu-id="da7ba-172">이 오류를 발생 하는 경우 클릭 **새로 고침** 작업 창에서.</span><span class="sxs-lookup"><span data-stu-id="da7ba-172">If you encounter this error, click **Refresh** in the actions pane.</span></span> <span data-ttu-id="da7ba-173">그러면 이벤트가 올바르게 디코딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="da7ba-173">The event should now decode properly.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="da7ba-174">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da7ba-174">The samples may already be installed on your computer.</span></span> <span data-ttu-id="da7ba-175">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="da7ba-175">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="da7ba-176">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="da7ba-176">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="da7ba-177">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da7ba-177">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Tracking\ExtractWfData`  
  
## <a name="see-also"></a><span data-ttu-id="da7ba-178">참고 항목</span><span class="sxs-lookup"><span data-stu-id="da7ba-178">See Also</span></span>  
 [<span data-ttu-id="da7ba-179">AppFabric 모니터링 샘플</span><span class="sxs-lookup"><span data-stu-id="da7ba-179">AppFabric Monitoring Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193959)
