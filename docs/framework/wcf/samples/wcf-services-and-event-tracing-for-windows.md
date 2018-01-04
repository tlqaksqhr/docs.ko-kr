---
title: "Windows용 WCF 서비스 및 이벤트 추척"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eda4355d-0bd0-4dc9-80a2-d2c832152272
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cb8924cc04442e3b9eda5e251e6dcdc57f5660c5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="wcf-services-and-event-tracing-for-windows"></a><span data-ttu-id="a945d-102">Windows용 WCF 서비스 및 이벤트 추척</span><span class="sxs-lookup"><span data-stu-id="a945d-102">WCF Services and Event Tracing for Windows</span></span>
<span data-ttu-id="a945d-103">이 샘플에서는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]의 분석 추적을 사용하여 ETW(Windows용 이벤트 추적)의 이벤트를 내보내는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a945d-103">This sample demonstrates how to use the analytic tracing in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] to emit events in Event Tracing for Windows (ETW).</span></span> <span data-ttu-id="a945d-104">분석 추적은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 스택에서 주요 시점에 내보내는 이벤트로서, 프로덕션 환경에서 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스의 문제를 해결하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a945d-104">The analytic traces are events emitted at key points in the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] stack that allow troubleshooting of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services in production environment.</span></span>  
  
 <span data-ttu-id="a945d-105">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스의 분석 추적은 프로덕션 환경에서 성능에 최소한의 영향만 주면서 설정할 수 있는 추적입니다.</span><span class="sxs-lookup"><span data-stu-id="a945d-105">Analytic trace in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services is tracing that can be turned on in a production environment with minimal impact on performance.</span></span> <span data-ttu-id="a945d-106">이러한 추적은 ETW 세션에 이벤트로 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="a945d-106">These traces are emitted as events to an ETW session.</span></span>  
  
 <span data-ttu-id="a945d-107">이 샘플에는 서비스에서 이벤트 뷰어를 사용하여 볼 수 있는 이벤트 로그로 이벤트를 내보내는 기본 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a945d-107">This sample includes a basic [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service in which events are emitted from the service to the event log, which can be viewed using Event Viewer.</span></span> <span data-ttu-id="a945d-108">또한 이 샘플에서는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스의 이벤트를 수신 대기하는 전용 ETW 세션을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a945d-108">It is also possible to start a dedicated ETW session that listens for events from the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span> <span data-ttu-id="a945d-109">이 샘플에는 이벤트 뷰어를 사용하여 읽을 수 있는 이진 파일에 이벤트를 저장하는 전용 ETW 세션을 만드는 스크립트가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a945d-109">The sample includes a script to create a dedicated ETW session that stores events in a binary file that can be read using Event Viewer.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="a945d-110">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="a945d-110">To use this sample</span></span>  
  
1.  <span data-ttu-id="a945d-111">[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]에서 EtwAnalyticTraceSample.sln 솔루션 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a945d-111">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the EtwAnalyticTraceSample.sln solution file.</span></span>  
  
2.  <span data-ttu-id="a945d-112">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="a945d-112">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="a945d-113">Ctrl+F5를 눌러 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a945d-113">To run the solution, press CTRL+F5.</span></span>  
  
     <span data-ttu-id="a945d-114">웹 브라우저에서 클릭 **Calculator.svc**합니다.</span><span class="sxs-lookup"><span data-stu-id="a945d-114">In the Web browser, click **Calculator.svc**.</span></span> <span data-ttu-id="a945d-115">서비스의 WSDL 문서에 대한 URI가 브라우저에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="a945d-115">The URI of the WSDL document for the service should appear in the browser.</span></span> <span data-ttu-id="a945d-116">이 URI를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="a945d-116">Copy that URI.</span></span>  
  
     <span data-ttu-id="a945d-117">기본적으로 서비스는 포트 1378(http://localhost:1378/Calculator.svc)에서 요청을 수신 대기하기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="a945d-117">By default, the service starts listening for requests on port 1378 (http://localhost:1378/Calculator.svc).</span></span>  
  
4.  <span data-ttu-id="a945d-118">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 테스트 클라이언트(WcfTestClient.exe)를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a945d-118">Run the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] test client (WcfTestClient.exe).</span></span>  
  
     <span data-ttu-id="a945d-119">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 에 있는 테스트 클라이언트 (WcfTestClient.exe)는 \< [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] Install > \Common7\IDE\ WcfTestClient.exe (기본 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 설치 디렉터리는 C:\Program Files\Microsoft Visual Studio 10.0).</span><span class="sxs-lookup"><span data-stu-id="a945d-119">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] test client (WcfTestClient.exe) is located in the \<[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] Install Dir>\Common7\IDE\ WcfTestClient.exe (default [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] install dir is C:\Program Files\Microsoft Visual Studio 10.0).</span></span>  
  
5.  <span data-ttu-id="a945d-120">내에서 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트 테스트를 선택 하 여 서비스를 추가 **파일**, 차례로 **서비스 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="a945d-120">Within the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] test client, add the service by selecting **File**, and then **Add Service**.</span></span>  
  
     <span data-ttu-id="a945d-121">입력 상자에 끝점 주소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a945d-121">Add the endpoint address in the input box.</span></span> <span data-ttu-id="a945d-122">기본값은 http://localhost:1378/Calculator.svc입니다.</span><span class="sxs-lookup"><span data-stu-id="a945d-122">The default is http://localhost:1378/Calculator.svc.</span></span>  
  
6.  <span data-ttu-id="a945d-123">이벤트 뷰어 응용 프로그램을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a945d-123">Open the Event Viewer application.</span></span>  
  
     <span data-ttu-id="a945d-124">서비스를 호출하기 전에 이벤트 뷰어를 시작하고 이벤트 로그가 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스에서 내보낸 추적 이벤트를 수신 대기하고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a945d-124">Before invoking the service, start Event Viewer and ensure that the event log is listening for tracking events emitted from the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span>  
  
7.  <span data-ttu-id="a945d-125">**시작** 메뉴 선택 **관리 도구**, 차례로 **이벤트 뷰어**합니다.</span><span class="sxs-lookup"><span data-stu-id="a945d-125">From the **Start** menu, select **Administrative Tools**, and then **Event Viewer**.</span></span>  <span data-ttu-id="a945d-126">사용 하도록 설정 된 **분석** 및 **디버그** 로그 합니다.</span><span class="sxs-lookup"><span data-stu-id="a945d-126">Enable the **Analytic** and **Debug** logs.</span></span>  
  
8.  <span data-ttu-id="a945d-127">이벤트 뷰어의 트리 뷰에서 이동 **이벤트 뷰어**, **Applications and Services Logs**, **Microsoft**, **Windows**, 한 다음 **응용 프로그램 서버-응용 프로그램**합니다.</span><span class="sxs-lookup"><span data-stu-id="a945d-127">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="a945d-128">마우스 오른쪽 단추로 클릭 **응용 프로그램 서버-응용 프로그램**선택, **보기**, 차례로 **분석 및 디버그 로그 표시**합니다.</span><span class="sxs-lookup"><span data-stu-id="a945d-128">Right-click **Application Server-Applications**, select **View**, and then **Show Analytic and Debug Logs**.</span></span>  
  
     <span data-ttu-id="a945d-129">확인 된 **분석 및 디버그 로그 표시** 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a945d-129">Ensure that the **Show Analytic and Debug Logs** option is checked.</span></span>  
  
9. <span data-ttu-id="a945d-130">사용 하도록 설정 된 **분석** 로그 합니다.</span><span class="sxs-lookup"><span data-stu-id="a945d-130">Enable the **Analytic** log.</span></span>  
  
     <span data-ttu-id="a945d-131">이벤트 뷰어의 트리 뷰에서 이동 **이벤트 뷰어**, **Applications and Services Logs**, **Microsoft**, **Windows**, 한 다음 **응용 프로그램 서버-응용 프로그램**합니다.</span><span class="sxs-lookup"><span data-stu-id="a945d-131">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="a945d-132">마우스 오른쪽 단추로 클릭 **분석** 선택 **로그 사용**합니다.</span><span class="sxs-lookup"><span data-stu-id="a945d-132">Right-click **Analytic** and select **Enable Log**.</span></span>  
  
#### <a name="to-test-the-service"></a><span data-ttu-id="a945d-133">서비스를 테스트하려면</span><span class="sxs-lookup"><span data-stu-id="a945d-133">To test the service</span></span>  
  
1.  <span data-ttu-id="a945d-134">다시 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 테스트 클라이언트로 전환하고 `Divide`를 두 번 클릭한 다음 분모 0을 지정하는 기본값을 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="a945d-134">Switch back to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] test client and double-click `Divide` and keep the default values, which specify a denominator of 0.</span></span>  
  
     <span data-ttu-id="a945d-135">분모가 0이면 서비스에서는 오류를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="a945d-135">If the denominator is 0, then the service throws a fault.</span></span>  
  
2.  <span data-ttu-id="a945d-136">서비스에서 내보낸 이벤트를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a945d-136">Observe the events emitted from the service.</span></span>  
  
     <span data-ttu-id="a945d-137">이벤트 뷰어로 다시 전환한 이동한 **이벤트 뷰어**, **Applications and Services Logs**, **Microsoft**, **Windows**, 한 다음 **응용 프로그램 서버-응용 프로그램**합니다.</span><span class="sxs-lookup"><span data-stu-id="a945d-137">Switch back to Event Viewer and navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="a945d-138">마우스 오른쪽 단추로 클릭 **분석** 선택 **새로 고침**합니다.</span><span class="sxs-lookup"><span data-stu-id="a945d-138">Right-click **Analytic** and select **Refresh**.</span></span>  
  
     <span data-ttu-id="a945d-139">WCF 분석 추적 이벤트가 이벤트 뷰어에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a945d-139">The WCF analytic trace events are displayed in the event viewer.</span></span> <span data-ttu-id="a945d-140">서비스에서 오류가 throw되었으므로 이벤트 뷰어에 오류 추적 이벤트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a945d-140">Notice that because a fault was thrown by the service an error trace event is displayed in the event viewer.</span></span>  
  
3.  <span data-ttu-id="a945d-141">1-2단계를 반복하되 이번에는 유효한 입력을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a945d-141">Repeat steps 1 and 2, but with valid inputs.</span></span> <span data-ttu-id="a945d-142">`N2` 매개 변수 값으로는 0 이외의 모든 숫자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a945d-142">The value of the `N2` parameter can be any number other than 0.</span></span>  
  
     <span data-ttu-id="a945d-143">분석 채널을 새로 고쳐 WCF 이벤트에 오류 이벤트가 포함되어 있지 않은지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a945d-143">Refresh the analytic channel to view the WCF events do not include any error events.</span></span>  
  
 <span data-ttu-id="a945d-144">이 샘플에서는 WCF 서비스에서 내보낸 분석 추적 이벤트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a945d-144">The sample demonstrates the analytic trace events emitted from a WCF service.</span></span>  
  
#### <a name="to-cleanup-optional"></a><span data-ttu-id="a945d-145">정리하려면(옵션)</span><span class="sxs-lookup"><span data-stu-id="a945d-145">To cleanup (Optional)</span></span>  
  
1.  <span data-ttu-id="a945d-146">이벤트 뷰어를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a945d-146">Open Event Viewer.</span></span>  
  
2.  <span data-ttu-id="a945d-147">로 이동 **이벤트 뷰어**, **Applications and Services Logs**, **Microsoft**, **Windows**, 차례로  **응용 프로그램 서버-응용 프로그램**합니다.</span><span class="sxs-lookup"><span data-stu-id="a945d-147">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application-Server-Applications**.</span></span> <span data-ttu-id="a945d-148">마우스 오른쪽 단추로 클릭 **분석** 선택 **로그 사용 안 함**합니다.</span><span class="sxs-lookup"><span data-stu-id="a945d-148">Right-click **Analytic** and select **Disable Log**.</span></span>  
  
3.  <span data-ttu-id="a945d-149">로 이동 **이벤트 뷰어**, **Applications and Services Logs**, **Microsoft**, **Windows**, 차례로  **응용 프로그램 서버-응용 프로그램**합니다.</span><span class="sxs-lookup"><span data-stu-id="a945d-149">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application-Server-Applications**.</span></span> <span data-ttu-id="a945d-150">마우스 오른쪽 단추로 클릭 **분석** 선택 **로그 지우기**합니다.</span><span class="sxs-lookup"><span data-stu-id="a945d-150">Right-click **Analytic** and select **Clear Log**.</span></span>  
  
4.  <span data-ttu-id="a945d-151">선택 된 **지우기** 이벤트를 해결 하는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="a945d-151">Choose the **Clear** option to clear the events.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a945d-152">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a945d-152">The samples may already be installed on your computer.</span></span> <span data-ttu-id="a945d-153">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="a945d-153">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="a945d-154">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="a945d-154">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a945d-155">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a945d-155">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ETWTracing`  
  
## <a name="see-also"></a><span data-ttu-id="a945d-156">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a945d-156">See Also</span></span>  
 [<span data-ttu-id="a945d-157">AppFabric 모니터링 샘플</span><span class="sxs-lookup"><span data-stu-id="a945d-157">AppFabric Monitoring Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193959)
