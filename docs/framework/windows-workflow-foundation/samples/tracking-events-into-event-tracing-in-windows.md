---
title: "Windows에서 이벤트 추적으로 이벤트 추적"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f812659b-0943-45ff-9430-4defa733182b
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 12dd8ee58b577df1ef7d54e8f820ff183cef6084
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="tracking-events-into-event-tracing-in-windows"></a><span data-ttu-id="11e98-102">Windows에서 이벤트 추적으로 이벤트 추적</span><span class="sxs-lookup"><span data-stu-id="11e98-102">Tracking Events into Event Tracing in Windows</span></span>
<span data-ttu-id="11e98-103">이 샘플에서는 워크플로 서비스에 대해 [!INCLUDE[wf](../../../../includes/wf-md.md)] 추적을 사용하고 ETW(Windows용 이벤트 추적)에 추적 이벤트를 내보내는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-103">This sample demonstrates how to enable [!INCLUDE[wf](../../../../includes/wf-md.md)] tracking on a workflow service and emit the tracking events in Event Tracing for Windows (ETW).</span></span> <span data-ttu-id="11e98-104">이 샘플에서는 ETW 추적 참가자(<xref:System.Activities.Tracking.EtwTrackingParticipant>)를 사용하여 워크플로 추적 레코드를 ETW로 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-104">To emit workflow tracking records into ETW, the sample uses the ETW tracking participant (<xref:System.Activities.Tracking.EtwTrackingParticipant>).</span></span>  
  
 <span data-ttu-id="11e98-105">샘플에서 워크플로는 요청을 받고, 입력 데이터의 상호 데이터를 입력 변수에 할당한 다음, 클라이언트에 상호 데이터를 다시 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-105">The workflow in the sample receives a request, assigns the reciprocal of the input data to the input variable and returns the reciprocal back to the client.</span></span> <span data-ttu-id="11e98-106">입력 데이터가 0인 경우 처리되지 않는 0으로 나누기 예외가 발생하여 워크플로가 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-106">When the input data is 0, a divide by zero exception occurs that is unhandled that causes the workflow to abort.</span></span> <span data-ttu-id="11e98-107">추적 기능을 사용하도록 설정되어 있으면 오류 추적 레코드가 ETW로 내보내지므로 나중에 오류 문제를 해결하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-107">With tracking enabled, the error track record is emitted to ETW, which can help troubleshoot the error later.</span></span> <span data-ttu-id="11e98-108">ETW 추적 참가자는 추적 레코드를 구독하도록 추적 프로필을 사용하여 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-108">The ETW tracking participant is configured with a tracking profile to subscribe to tracking records.</span></span> <span data-ttu-id="11e98-109">추적 프로필은 Web.config 파일에 정의되고 ETW 추적 참가자에 구성 매개 변수로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-109">The tracking profile is defined in the Web.config file and provided as a configuration parameter to the ETW tracking participant.</span></span> <span data-ttu-id="11e98-110">ETW 추적 참가자는 워크플로 서비스의 Web.config 파일에 구성되며 서비스에 서비스 동작으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-110">The ETW tracking participant is configured in the Web.config file of the workflow service and is applied to the service as a service behavior.</span></span> <span data-ttu-id="11e98-111">이 샘플에서는 이벤트 뷰어를 사용하여 이벤트 로그의 추적 이벤트를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-111">In this sample, you view the tracking events in the event log using Event Viewer.</span></span>  
  
## <a name="workflow-tracking-details"></a><span data-ttu-id="11e98-112">워크플로 추적 세부 정보</span><span class="sxs-lookup"><span data-stu-id="11e98-112">Workflow Tracking Details</span></span>  
 [!INCLUDE[wf2](../../../../includes/wf2-md.md)]<span data-ttu-id="11e98-113">은 워크플로 인스턴스 실행을 추적하기 위한 추적 인프라를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-113"> provides a tracking infrastructure to track the execution of a workflow instance.</span></span> <span data-ttu-id="11e98-114">추적 런타임은 워크플로 인스턴스를 만들어 워크플로 수명 주기와 관련된 이벤트, 워크플로 활동의 이벤트 및 사용자 지정 이벤트를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-114">The tracking runtime creates a workflow instance to emit events related to the workflow lifecycle, events from workflow activities and custom events.</span></span> <span data-ttu-id="11e98-115">다음 표에서는 추적 인프라의 기본 구성 요소에 대해 자세히 설명합니다</span><span class="sxs-lookup"><span data-stu-id="11e98-115">The following table details the primary components of the tracking infrastructure.</span></span>  
  
|<span data-ttu-id="11e98-116">구성 요소</span><span class="sxs-lookup"><span data-stu-id="11e98-116">Component</span></span>|<span data-ttu-id="11e98-117">설명</span><span class="sxs-lookup"><span data-stu-id="11e98-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="11e98-118">추적 런타임</span><span class="sxs-lookup"><span data-stu-id="11e98-118">Tracking runtime</span></span>|<span data-ttu-id="11e98-119">추적 레코드를 내보낼 인프라를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-119">Provides the infrastructure to emit tracking records.</span></span>|  
|<span data-ttu-id="11e98-120">추적 참가자</span><span class="sxs-lookup"><span data-stu-id="11e98-120">Tracking participants</span></span>|<span data-ttu-id="11e98-121">추적 레코드에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-121">Accesses the tracking records.</span></span> [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)]<span data-ttu-id="11e98-122">에는 추적 레코드를 ETW(Windows용 이벤트 추적) 이벤트로 기록하는 추적 참가자가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-122"> ships with a tracking participant that writes tracking records as Event Tracing for Windows (ETW) events.</span></span>|  
|<span data-ttu-id="11e98-123">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="11e98-123">Tracking profile</span></span>|<span data-ttu-id="11e98-124">추적 참가자가 워크플로 인스턴스에서 내보낸 추적 레코드의 하위 집합을 구독할 수 있도록 하는 필터링 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-124">A filtering mechanism that allows a tracking participant to subscribe for a subset of the tracking records emitted from a workflow instance.</span></span>|  
  
 <span data-ttu-id="11e98-125">다음 표에서는 워크플로 런타임에서 내보내는 추적 레코드에 대해 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-125">The following table details the tracking records that the workflow runtime emits.</span></span>  
  
|<span data-ttu-id="11e98-126">추적 레코드</span><span class="sxs-lookup"><span data-stu-id="11e98-126">Tracking record</span></span>|<span data-ttu-id="11e98-127">설명</span><span class="sxs-lookup"><span data-stu-id="11e98-127">Description</span></span>|  
|---------------------|-----------------|  
|<span data-ttu-id="11e98-128">워크플로 인스턴스 추적 레코드</span><span class="sxs-lookup"><span data-stu-id="11e98-128">Workflow instance tracking records.</span></span>|<span data-ttu-id="11e98-129">워크플로 인스턴스의 수명 주기에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-129">Describes the lifecycle of the workflow instance.</span></span> <span data-ttu-id="11e98-130">예를 들어 워크플로가 시작되거나 완료되면 인스턴스 레코드를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-130">For example, an instance record is emitted when the workflow starts or completes.</span></span>|  
|<span data-ttu-id="11e98-131">활동 상태 추적 레코드</span><span class="sxs-lookup"><span data-stu-id="11e98-131">Activity state tracking records.</span></span>|<span data-ttu-id="11e98-132">활동 실행에 대해 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-132">Details activity execution.</span></span> <span data-ttu-id="11e98-133">이러한 레코드는 활동이 예약된 시점, 활동이 완료된 시점, 오류가 throw된 시점 등과 같은 워크플로 활동 상태를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-133">These records indicate the state of a workflow activity such as when an activity is scheduled or when the activity completes or when a fault is thrown.</span></span>|  
|<span data-ttu-id="11e98-134">책갈피 다시 시작 레코드</span><span class="sxs-lookup"><span data-stu-id="11e98-134">Bookmark resumption record.</span></span>|<span data-ttu-id="11e98-135">워크플로 인스턴스 내의 책갈피를 다시 시작할 때마다 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-135">Emitted whenever a bookmark within a workflow instance is resumed.</span></span>|  
|<span data-ttu-id="11e98-136">사용자 지정 추적 레코드</span><span class="sxs-lookup"><span data-stu-id="11e98-136">Custom tracking records.</span></span>|<span data-ttu-id="11e98-137">워크플로 작성자가 사용자 지정 추적 레코드를 만들어 사용자 지정 활동 중에 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-137">A workflow author can create custom tracking records and emit them within the custom activity.</span></span>|  
|<xref:System.Activities.Tracking.ActivityScheduledRecord>|<span data-ttu-id="11e98-138">이 레코드는 활동이 다른 활동을 예약할 때 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-138">This record is emitted when an activity schedules another activity.</span></span>|  
|<xref:System.Activities.Tracking.FaultPropagationRecord>|<span data-ttu-id="11e98-139">이 레코드는 활동에서 오류가 전파될 때 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-139">This record is emitted when a fault is propagated from an activity.</span></span>|  
|<xref:System.Activities.Tracking.CancelRequestedRecord>|<span data-ttu-id="11e98-140">이 레코드는 활동이 다른 활동에 의해 취소될 때 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-140">This record is emitted when an activity is canceled by another activity.</span></span>|  
  
 <span data-ttu-id="11e98-141">추적 참가자는 추적 프로필을 사용하여 내보낸 추적 레코드의 하위 집합을 구독합니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-141">The tracking participant subscribes for a subset of the emitted tracking records using tracking profiles.</span></span> <span data-ttu-id="11e98-142">추적 프로필에는 특정 추적 레코드 형식을 구독할 수 있도록 허용하는 추적 쿼리가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-142">A tracking profile contains tracking queries that allow subscribing for a particular tracking record type.</span></span> <span data-ttu-id="11e98-143">추적 프로필은 코드나 구성에 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-143">Tracking profiles can be specified in code or in configuration.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="11e98-144">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="11e98-144">To use this sample</span></span>  
  
1.  <span data-ttu-id="11e98-145">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]을 사용하여 EtwTrackingParticipantSample.sln 솔루션 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-145">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the EtwTrackingParticipantSample.sln solution file.</span></span>  
  
2.  <span data-ttu-id="11e98-146">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-146">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="11e98-147">F5 키를 눌러 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-147">To run the solution, press F5.</span></span>  
  
     <span data-ttu-id="11e98-148">기본적으로 서비스는 포트 53797(http://localhost:53797/SampleWorkflowService.xamlx)에서 수신 대기하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-148">By default, the service is listening on port 53797 (http://localhost:53797/SampleWorkflowService.xamlx).</span></span>  
  
4.  <span data-ttu-id="11e98-149">[!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)]를 사용하여 WCF 테스트 클라이언트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-149">Using [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], open the WCF test client.</span></span>  
  
     <span data-ttu-id="11e98-150">WCF 테스트 클라이언트 (WcfTestClient.exe)에 \< [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 설치 폴더 > \Common7\IDE\ 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-150">The WCF test client (WcfTestClient.exe) is located in the \<[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] installation folder>\Common7\IDE\ folder.</span></span>  
  
     <span data-ttu-id="11e98-151">기본 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 설치 폴더는 C:\Program Files\Microsoft Visual Studio 10.0입니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-151">The default [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] installation folder is C:\Program Files\Microsoft Visual Studio 10.0.</span></span>  
  
5.  <span data-ttu-id="11e98-152">WCF 테스트 클라이언트에서 선택 **서비스 추가** 에서 **파일** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="11e98-152">In WCF test client, select **Add Service** from the **File** menu.</span></span>  
  
     <span data-ttu-id="11e98-153">입력 상자에 끝점 주소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-153">Add the endpoint address in the input box.</span></span> <span data-ttu-id="11e98-154">기본값은 http://localhost:53797/SampleWorkflowService.xamlx입니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-154">The default is http://localhost:53797/SampleWorkflowService.xamlx.</span></span>  
  
6.  <span data-ttu-id="11e98-155">이벤트 뷰어 응용 프로그램을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-155">Open the Event Viewer application.</span></span>  
  
     <span data-ttu-id="11e98-156">이벤트 뷰어를 시작 서비스를 호출 하기 전에 **시작** 메뉴 선택 **실행** 에 입력 하 고 `eventvwr.exe`합니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-156">Before invoking the service, start Event Viewer from the **Start** menu, select **Run** and type in `eventvwr.exe`.</span></span> <span data-ttu-id="11e98-157">이벤트 로그가 워크플로 서비스에서 내보낸 추적 이벤트를 수신 대기하고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-157">Ensure that the event log is listening for tracking events emitted from the workflow service.</span></span>  
  
7.  <span data-ttu-id="11e98-158">이벤트 뷰어의 트리 뷰에서 이동 **이벤트 뷰어**, **Applications and Services Logs**, 및 **Microsoft**합니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-158">In the tree view of the Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, and **Microsoft**.</span></span> <span data-ttu-id="11e98-159">마우스 오른쪽 단추로 클릭 **Microsoft** 선택 **보기** 차례로 **분석 및 디버그 로그 표시** 사용 분석 및 디버그 로그에</span><span class="sxs-lookup"><span data-stu-id="11e98-159">Right-click **Microsoft** and select **View** and then **Show Analytic and Debug Logs** to enable the analytic and debug logs</span></span>  
  
     <span data-ttu-id="11e98-160">확인 된 **분석 및 디버그 로그 표시** 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-160">Ensure that the **Show Analytic and Debug Logs** option is checked.</span></span>  
  
8.  <span data-ttu-id="11e98-161">이벤트 뷰어의 트리 뷰에서 이동 **이벤트 뷰어**, **Applications and Services Logs**, **Microsoft**, **Windows**,  **응용 프로그램 서버-응용 프로그램**합니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-161">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span> <span data-ttu-id="11e98-162">마우스 오른쪽 단추로 클릭 **분석** 선택 **로그 사용** 사용할 수 있도록는 **분석** 로그 합니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-162">Right-click **Analytic** and select **Enable Log** to enable the **Analytic** log.</span></span>  
  
9. <span data-ttu-id="11e98-163">`GetData`를 두 번 클릭하여 WCF 테스트 클라이언트로 서비스를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-163">Test the service using the WCF test client by double-clicking `GetData`.</span></span>  
  
     <span data-ttu-id="11e98-164">그러면 `GetData` 메서드가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-164">This opens the `GetData` method.</span></span> <span data-ttu-id="11e98-165">요청은 하나의 매개 변수를 받아들이고 값이 기본값인 0인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-165">The request accepts one parameter and ensures that the value is 0, which is the default.</span></span>  
  
     <span data-ttu-id="11e98-166">클릭 **호출**합니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-166">Click **Invoke**.</span></span>  
  
10. <span data-ttu-id="11e98-167">워크플로에서 내보낸 이벤트를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-167">Observe the events emitted from the workflow.</span></span>  
  
     <span data-ttu-id="11e98-168">이벤트 뷰어로 다시 전환한 이동한 **이벤트 뷰어**, **Applications and Services Logs**, **Microsoft**, **Windows**,  **응용 프로그램 서버-응용 프로그램**합니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-168">Switch back to Event Viewer and navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span> <span data-ttu-id="11e98-169">마우스 오른쪽 단추로 클릭 **분석** 선택 **새로 고침**합니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-169">Right-click **Analytic** and select **Refresh**.</span></span>  
  
     <span data-ttu-id="11e98-170">이벤트 뷰어에 워크플로 이벤트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-170">The workflow events are displayed in the event viewer.</span></span> <span data-ttu-id="11e98-171">워크플로 실행 이벤트가 표시되며, 이 중 하나는 워크플로의 오류에 해당하는 처리되지 않은 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-171">Notice that workflow execution events are displayed and that one of them is an unhandled exception that corresponds to the error in workflow.</span></span> <span data-ttu-id="11e98-172">또한 워크플로 활동에서 경고 이벤트를 내보내며 이는 활동이 오류를 throw할 것임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-172">Also, a warning event is emitted from the workflow activity, which indicates that the activity is throwing a fault.</span></span>  
  
11. <span data-ttu-id="11e98-173">오류가 throw되지 않도록 0 이외의 입력 데이터를 사용하여 9단계와 10단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-173">Repeat steps 9 and 10 with an input of data other than 0, so that no error is thrown.</span></span>  
  
 <span data-ttu-id="11e98-174">추적 프로필을 사용하면 워크플로 인스턴스 상태가 변경될 때 런타임에서 내보내는 이벤트를 구독할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-174">Tracking profiles allow you to subscribe to events that are emitted by the runtime when the state of a workflow instance changes.</span></span> <span data-ttu-id="11e98-175">모니터링 요구 사항에 따라 워크플로에서 상위 수준의 상태 변경 내용 중 작은 부분만 구독하는 매우 개괄적인 프로필을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-175">Depending on your monitoring requirements, you can create a profile that is very coarse, which subscribes to a small set of high-level state changes on a workflow.</span></span> <span data-ttu-id="11e98-176">그러나 나중에 실행을 다시 생성할 수 있을 정도로 출력이 풍부한 매우 정확한 프로필을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-176">On the other hand, you can create a very precise profile whose output is rich enough to reconstruct the execution later.</span></span> <span data-ttu-id="11e98-177">이 샘플에서는 작은 이벤트 집합을 내보내는 `HealthMonitoring Tracking Profile`을 사용하여 워크플로 런타임에서 ETW로 내보내는 이벤트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-177">The sample demonstrates the events emitted from the workflow runtime to ETW using the `HealthMonitoring Tracking Profile`, which emits a small set of events.</span></span> <span data-ttu-id="11e98-178">추가 워크플로 추적 이벤트를 내보내는 다른 프로필도 `Troubleshooting Tracking Profile`이라는 Web.config에 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-178">A different profile that emits more workflow tracking events is also provided in the Web.config that is named `Troubleshooting Tracking Profile`.</span></span> <span data-ttu-id="11e98-179">[!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)]가 설치되어 있으면 Machine.config 파일에 이름이 비어 있는 기본 프로필이 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-179">When the [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)] is installed, a default profile with an empty name is configured in the Machine.config file.</span></span> <span data-ttu-id="11e98-180">프로필 이름을 지정하지 않았거나 빈 프로필 이름을 지정한 경우에는 ETW 추적 동작 구성에서 이 프로필을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-180">This profile is used by the ETW tracking behavior configuration when no profile name or an empty profile name is specified.</span></span>  
  
 <span data-ttu-id="11e98-181">상태 모니터링 추적 프로필은 워크플로 인스턴스 레코드와 활동 오류 전파 레코드를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-181">The health monitoring tracking profile emits workflow instance records and activity fault propagation records.</span></span> <span data-ttu-id="11e98-182">이 프로필은 Web.config 구성 파일에 다음 추적 프로필을 추가하여 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-182">This profile is created by adding the following tracking profile to a Web.config configuration file.</span></span>  
  
```xml  
<<tracking>  
      <profiles>  
        <trackingProfile name="HealthMonitoring Tracking Profile">  
          <workflow activityDefinitionId="*">  
            <workflowInstanceQueries>  
              <workflowInstanceQuery>  
                <states>  
                  <state name="Started"/>  
                  <state name="Completed"/>  
                  <state name="Aborted"/>  
                  <state name="UnhandledException"/>  
                </states>  
            </workflowInstanceQuery>  
           </workflowInstanceQueries>  
            <faultPropagationQueries>  
              <faultPropagationQuery faultSourceActivityName ="*" faultHandlerActivityName="*"/>  
            </faultPropagationQueries>  
          </workflow>  
        </trackingProfile>  
       </profiles>  
</tracking>  
```  
  
 <span data-ttu-id="11e98-183">`EtwTrackingParticipant` 구성을 다음 내용으로 변경하여 프로필을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-183">The profile can be changed by changing the `EtwTrackingParticipant` configuration to the following.</span></span>  
  
```xml  
<behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <etwTracking profileName="HealthMonitoring Tracking Profile"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
```  
  
#### <a name="to-clean-up-optional"></a><span data-ttu-id="11e98-184">정리하려면(옵션)</span><span class="sxs-lookup"><span data-stu-id="11e98-184">To clean up (Optional)</span></span>  
  
1.  <span data-ttu-id="11e98-185">이벤트 뷰어를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-185">Open Event Viewer.</span></span>  
  
2.  <span data-ttu-id="11e98-186">로 이동 **이벤트 뷰어**, **Applications and Services Logs**, **Microsoft**, **Windows**, **응용 프로그램 서버-응용 프로그램**합니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-186">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span> <span data-ttu-id="11e98-187">마우스 오른쪽 단추로 클릭 **분석** 선택 **로그 사용 안 함**합니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-187">Right-click **Analytic** and select **Disable Log**.</span></span>  
  
3.  <span data-ttu-id="11e98-188">로 이동 **이벤트 뷰어**, **Applications and Services Logs**, **Microsoft**, **Windows**, **응용 프로그램 서버-응용 프로그램**합니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-188">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span> <span data-ttu-id="11e98-189">마우스 오른쪽 단추로 클릭 **분석** 선택 **로그 지우기**합니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-189">Right-click **Analytic** and select **Clear Log**.</span></span>  
  
4.  <span data-ttu-id="11e98-190">선택 된 **지우기** 이벤트를 해결 하는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-190">Choose the **Clear** option to clear the events.</span></span>  
  
## <a name="known-issue"></a><span data-ttu-id="11e98-191">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="11e98-191">Known Issue</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="11e98-192">ETW 이벤트가 디코딩되지 않을 수 있으며, 이는 이벤트 뷰어와 관련하여 알려진 문제입니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-192">There is a known issue in the Event Viewer where it may fail to decode ETW events.</span></span> <span data-ttu-id="11e98-193">다음과 같은 오류 메시지가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-193">You may see an error message that looks like the following.</span></span>  
>   
>  <span data-ttu-id="11e98-194">이벤트 ID에 대 한 설명 \<id > Microsoft-Windows-응용 프로그램 서버-응용 프로그램을 찾을 수 없는 소스에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-194">The description for Event ID \<id> from source Microsoft-Windows-Application Server-Applications cannot be found.</span></span> <span data-ttu-id="11e98-195">이 이벤트를 발생시킨 구성 요소가 로컬 컴퓨터에 설치되어 있지 않거나 설치가 손상되었습니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-195">Either the component that raises this event is not installed on your local computer or the installation is corrupted.</span></span> <span data-ttu-id="11e98-196">로컬 컴퓨터에서 구성 요소를 설치 또는 복구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-196">You can install or repair the component on the local computer.</span></span>  
>   
>  <span data-ttu-id="11e98-197">이 오류가 발생하면 동작 창에서 새로 고침을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-197">If you encounter this error, click refresh in the actions pane.</span></span> <span data-ttu-id="11e98-198">그러면 이벤트가 올바르게 디코딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-198">The event should now decode properly.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="11e98-199">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-199">The samples may already be installed on your computer.</span></span> <span data-ttu-id="11e98-200">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="11e98-200">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="11e98-201">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="11e98-201">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="11e98-202">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11e98-202">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Tracking\EtwTracking`  
  
## <a name="see-also"></a><span data-ttu-id="11e98-203">참고 항목</span><span class="sxs-lookup"><span data-stu-id="11e98-203">See Also</span></span>  
 [<span data-ttu-id="11e98-204">AppFabric 모니터링 샘플</span><span class="sxs-lookup"><span data-stu-id="11e98-204">AppFabric Monitoring Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193959)
