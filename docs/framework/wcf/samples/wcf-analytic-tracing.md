---
title: "WCF 분석 추적"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6029c7c7-3515-4d36-9d43-13e8f4971790
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5c238d4c923b00a6c3387caa9bdafd69b126753c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="wcf-analytic-tracing"></a><span data-ttu-id="f0654-102">WCF 분석 추적</span><span class="sxs-lookup"><span data-stu-id="f0654-102">WCF Analytic Tracing</span></span>
<span data-ttu-id="f0654-103">이 샘플에서는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]에서 [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]의 ETW에 기록하는 분석 추적 스트림에 추적 이벤트를 추가하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-103">This sample demonstrates how to add your own tracing events into the stream of analytic traces that [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] writes to ETW in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span></span> <span data-ttu-id="f0654-104">분석 추적은 성능을 크게 저하시키지 않으면서 서비스를 쉽게 확인할 수 있도록 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-104">Analytic traces are meant to make it easy to get visibility into your services without paying a high performance penalty.</span></span> <span data-ttu-id="f0654-105">이 샘플에서는 <xref:System.Diagnostics.Eventing?displayProperty=nameWithType> API를 사용하여 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스와 통합되는 이벤트를 기록하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-105">This sample shows how to use the <xref:System.Diagnostics.Eventing?displayProperty=nameWithType> APIs to write events that integrate with [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="f0654-106"> API에 대한 <xref:System.Diagnostics.Eventing?displayProperty=nameWithType>는 <xref:System.Diagnostics.Eventing?displayProperty=nameWithType>을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f0654-106"> the <xref:System.Diagnostics.Eventing?displayProperty=nameWithType> APIs, see <xref:System.Diagnostics.Eventing?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="f0654-107">Windows에서 이벤트 추적에 대 한 자세한 참조 [디버깅 개선 및 ETW를 사용한 성능 조정](http://go.microsoft.com/fwlink/?LinkId=166488)합니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-107">To learn more about event tracing in Windows, see [Improve Debugging and Performance Tuning with ETW](http://go.microsoft.com/fwlink/?LinkId=166488).</span></span>  
  
## <a name="disposing-eventprovider"></a><span data-ttu-id="f0654-108">EventProvider 삭제</span><span class="sxs-lookup"><span data-stu-id="f0654-108">Disposing EventProvider</span></span>  
 <span data-ttu-id="f0654-109">이 샘플에서는 <xref:System.Diagnostics.Eventing.EventProvider?displayProperty=nameWithType>을 구현하는 <xref:System.IDisposable?displayProperty=nameWithType> 클래스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-109">This sample uses the <xref:System.Diagnostics.Eventing.EventProvider?displayProperty=nameWithType> class, which implements <xref:System.IDisposable?displayProperty=nameWithType>.</span></span> <span data-ttu-id="f0654-110">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스에 대한 추적을 구현할 경우 서비스의 수명 동안 <xref:System.Diagnostics.Eventing.EventProvider>의 리소스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-110">When implementing tracing for a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service, it is likely that you may use the <xref:System.Diagnostics.Eventing.EventProvider>’s resources for the lifetime of the service.</span></span> <span data-ttu-id="f0654-111">이러한 이유로, 또한 읽기 쉽게 하려는 목적으로 이 샘플에서는 래핑된 <xref:System.Diagnostics.Eventing.EventProvider>를 삭제하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-111">For this reason, and for readability, this sample never disposes of the wrapped <xref:System.Diagnostics.Eventing.EventProvider>.</span></span> <span data-ttu-id="f0654-112">어떤 이유로 서비스에 다른 추적 요구 사항이 있으며 이 리소스를 삭제해야 하는 경우 관리되지 않는 리소스를 삭제하기 위한 최선의 방법에 따라 이 샘플을 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-112">If for some reason your service has different requirements for tracing and you must dispose of this resource, then you should modify this sample in accordance with the best practices for disposing of unmanaged resources.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="f0654-113">관리 되지 않는 리소스를 삭제, 참조 [Dispose 메서드를 구현](http://go.microsoft.com/fwlink/?LinkId=166436)합니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-113"> disposing unmanaged resources, see [Implementing a Dispose Method](http://go.microsoft.com/fwlink/?LinkId=166436).</span></span>  
  
## <a name="self-hosting-vs-web-hosting"></a><span data-ttu-id="f0654-114">자체 호스팅 및 웹 호스팅</span><span class="sxs-lookup"><span data-stu-id="f0654-114">Self-Hosting vs. Web Hosting</span></span>  
 <span data-ttu-id="f0654-115">웹 호스팅 서비스에 대 한 WCF의 분석 추적에서는 추적을 내보내는 서비스를 식별 하는 데 사용 되는 "hostreference" 필드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-115">For Web-hosted services, WCF’s analytic traces provide a field, called "HostReference", which is used to identify the service that is emitting the traces.</span></span> <span data-ttu-id="f0654-116">확장 가능한 사용자 추적이 이 모델에 관여할 수 있으며 이 샘플에서는 이 작업을 수행하기 위한 최선의 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-116">The extensible user traces can participate in this model and this sample demonstrates best practices for doing so.</span></span> <span data-ttu-id="f0654-117">경우 참조는 웹 호스트 형식은 파이프 ' &#124;' 문자는 결과에 실제로 표시 문자열에는 다음 중 하나가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-117">The format of a Web host reference when the pipe ‘&#124;’ character actually appears in the resulting string can be any one of the following:</span></span>  
  
-   <span data-ttu-id="f0654-118">응용 프로그램이 루트에 없는 경우</span><span class="sxs-lookup"><span data-stu-id="f0654-118">If the application is not at the root.</span></span>  
  
     <span data-ttu-id="f0654-119">\<사이트 이름 >\<ApplicationVirtualPath > &#124;\< ServiceVirtualPath > &#124; \<ServiceName ></span><span class="sxs-lookup"><span data-stu-id="f0654-119">\<SiteName>\<ApplicationVirtualPath>&#124;\<ServiceVirtualPath>&#124;\<ServiceName></span></span>  
  
-   <span data-ttu-id="f0654-120">응용 프로그램이 루트에 있는 경우</span><span class="sxs-lookup"><span data-stu-id="f0654-120">If the application is at the root.</span></span>  
  
     <span data-ttu-id="f0654-121">\<사이트 이름 > &#124; \<ServiceVirtualPath > &#124; \<ServiceName ></span><span class="sxs-lookup"><span data-stu-id="f0654-121">\<SiteName>&#124;\<ServiceVirtualPath>&#124;\<ServiceName></span></span>  
  
 <span data-ttu-id="f0654-122">자체 호스팅된 서비스에 대 한 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]의 분석 추석 "에서는 HostReference" 필드를 채우지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-122">For self-hosted services, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]’s analytic traces do not populate the "HostReference" field.</span></span> <span data-ttu-id="f0654-123">이 샘플의 `WCFUserEventProvider` 클래스는 자체 호스팅 서비스에서 사용될 때 일관성 있게 동작합니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-123">The `WCFUserEventProvider` class in this sample behaves consistently when used by a self-hosted service.</span></span>  
  
## <a name="custom-event-details"></a><span data-ttu-id="f0654-124">사용자 지정 이벤트 상세 정보</span><span class="sxs-lookup"><span data-stu-id="f0654-124">Custom Event Details</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="f0654-125">의 ETW 이벤트 공급자 매니페스트는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스 작성자가 서비스 코드 내에서 내보내도록 디자인한 세 개의 이벤트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-125">’s ETW Event Provider manifest defines three events that are designed to be emitted by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service authors from within service code.</span></span> <span data-ttu-id="f0654-126">다음 표에서는 세 개의 이벤트를 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-126">The following table shows a breakdown of the three events.</span></span>  
  
|<span data-ttu-id="f0654-127">이벤트</span><span class="sxs-lookup"><span data-stu-id="f0654-127">Event</span></span>|<span data-ttu-id="f0654-128">설명</span><span class="sxs-lookup"><span data-stu-id="f0654-128">Description</span></span>|<span data-ttu-id="f0654-129">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="f0654-129">Event ID</span></span>|  
|-----------|-----------------|--------------|  
|<span data-ttu-id="f0654-130">UserDefinedInformationEventOccurred</span><span class="sxs-lookup"><span data-stu-id="f0654-130">UserDefinedInformationEventOccurred</span></span>|<span data-ttu-id="f0654-131">문제는 아니지만 중요한 사항이 서비스에 발생하면 이 이벤트를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-131">Emit this event when something of note happens in your service that is not a problem.</span></span> <span data-ttu-id="f0654-132">예를 들어 데이터베이스를 성공적으로 호출한 후 이벤트를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-132">For example, you might emit an event after successfully making a call to a database.</span></span>|<span data-ttu-id="f0654-133">301</span><span class="sxs-lookup"><span data-stu-id="f0654-133">301</span></span>|  
|<span data-ttu-id="f0654-134">UserDefinedWarningOccurred</span><span class="sxs-lookup"><span data-stu-id="f0654-134">UserDefinedWarningOccurred</span></span>|<span data-ttu-id="f0654-135">이후에 오류를 초래할 수 있는 문제가 발생하면 이 이벤트를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-135">Emit this event when a problem occurs that may result in a failure in the future.</span></span> <span data-ttu-id="f0654-136">예를 들어 데이터베이스에 대한 호출에 실패했지만 중복 데이터 저장소를 대신 사용하여 복구할 수 있는 경우 경고 이벤트를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-136">For example, you may emit a warning event when a call to a database fails but you were able to recover by falling back to a redundant data store.</span></span>|<span data-ttu-id="f0654-137">302</span><span class="sxs-lookup"><span data-stu-id="f0654-137">302</span></span>|  
|<span data-ttu-id="f0654-138">UserDefinedErrorOccurred</span><span class="sxs-lookup"><span data-stu-id="f0654-138">UserDefinedErrorOccurred</span></span>|<span data-ttu-id="f0654-139">서비스가 예상한 대로 동작하지 않으면 이 이벤트를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-139">Emit this event when your service fails to behave as expected.</span></span> <span data-ttu-id="f0654-140">예를 들어 데이터베이스에 대한 호출에 실패하고 다른 위치에서 데이터를 검색할 수 없는 경우 이벤트를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-140">For example, you might emit an event if a call to a database fails and you could not retrieve the data from elsewhere.</span></span>|<span data-ttu-id="f0654-141">303</span><span class="sxs-lookup"><span data-stu-id="f0654-141">303</span></span>|  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="f0654-142">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="f0654-142">To use this sample</span></span>  
  
1.  <span data-ttu-id="f0654-143">[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]에서 WCFAnalyticTracingExtensibility.sln 솔루션 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-143">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the WCFAnalyticTracingExtensibility.sln solution file.</span></span>  
  
2.  <span data-ttu-id="f0654-144">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-144">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="f0654-145">Ctrl+F5를 눌러 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-145">To run the solution, press CTRL+F5.</span></span>  
  
     <span data-ttu-id="f0654-146">웹 브라우저에서 클릭 **Calculator.svc**합니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-146">In the Web browser, click **Calculator.svc**.</span></span> <span data-ttu-id="f0654-147">서비스의 WSDL 문서에 대한 URI가 브라우저에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-147">The URI of the WSDL document for the service should appear in the browser.</span></span> <span data-ttu-id="f0654-148">이 URI를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-148">Copy that URI.</span></span>  
  
4.  <span data-ttu-id="f0654-149">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 테스트 클라이언트(WcfTestClient.exe)를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-149">Run the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] test client (WcfTestClient.exe).</span></span>  
  
     <span data-ttu-id="f0654-150">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 에 있는 테스트 클라이언트 (WcfTestClient.exe)는 \< [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] Install > \Common7\IDE\ WcfTestClient.exe (기본 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 설치 디렉터리는 C:\Program Files\Microsoft Visual Studio 10.0).</span><span class="sxs-lookup"><span data-stu-id="f0654-150">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] test client (WcfTestClient.exe) is located in the \<[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] Install Dir>\Common7\IDE\ WcfTestClient.exe (default [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] install dir is C:\Program Files\Microsoft Visual Studio 10.0).</span></span>  
  
5.  <span data-ttu-id="f0654-151">내에서 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트 테스트를 선택 하 여 서비스를 추가 **파일**, 차례로 **서비스 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-151">Within the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] test client, add the service by selecting **File**, and then **Add Service**.</span></span>  
  
     <span data-ttu-id="f0654-152">입력 상자에 끝점 주소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-152">Add the endpoint address in the input box.</span></span>  
  
6.  <span data-ttu-id="f0654-153">클릭 **확인** 는 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-153">Click **OK** to close the dialog.</span></span>  
  
     <span data-ttu-id="f0654-154">ICalculator 서비스가 아래 왼쪽된 창에서 추가 된 **내 서비스 프로젝트**합니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-154">The ICalculator service is added in the left pane under **My Service Projects**.</span></span>  
  
7.  <span data-ttu-id="f0654-155">이벤트 뷰어 응용 프로그램을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-155">Open the Event Viewer application.</span></span>  
  
     <span data-ttu-id="f0654-156">서비스를 호출하기 전에 이벤트 뷰어를 시작하고 이벤트 로그가 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스에서 내보낸 추적 이벤트를 수신 대기하고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-156">Before invoking the service, start Event Viewer and ensure that the event log is listening for tracking events emitted from the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span>  
  
8.  <span data-ttu-id="f0654-157">**시작** 메뉴 선택 **관리 도구**, 차례로 **이벤트 뷰어**합니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-157">From the **Start** menu, select **Administrative Tools**, and then **Event Viewer**.</span></span> <span data-ttu-id="f0654-158">사용 하도록 설정 된 **분석** 및 **디버그** 로그 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-158">Enable the **Analytic** and **Debug** logs.</span></span>  
  
9. <span data-ttu-id="f0654-159">이벤트 뷰어의 트리 뷰에서 이동 **이벤트 뷰어**, **Applications and Services Logs**, **Microsoft**, **Windows**, 한 다음 **응용 프로그램 서버-응용 프로그램**합니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-159">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="f0654-160">마우스 오른쪽 단추로 클릭 **응용 프로그램 서버-응용 프로그램**선택, **보기**, 차례로 **분석 및 디버그 로그 표시**합니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-160">Right-click **Application Server-Applications**, select **View**, and then **Show Analytic and Debug Logs**.</span></span>  
  
     <span data-ttu-id="f0654-161">확인 된 **분석 및 디버그 로그 표시** 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-161">Ensure that the **Show Analytic and Debug Logs** option is checked.</span></span> <span data-ttu-id="f0654-162">사용 하도록 설정 된 **분석** 로그 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-162">Enable the **Analytic** log.</span></span>  
  
     <span data-ttu-id="f0654-163">이벤트 뷰어의 트리 뷰에서 이동 **이벤트 뷰어**, **Applications and Services Logs**, **Microsoft**, **Windows**,  **응용 프로그램 서버-응용 프로그램**, 차례로 **분석**합니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-163">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**, and then **Analytic**.</span></span> <span data-ttu-id="f0654-164">마우스 오른쪽 단추로 클릭 **분석** 선택 **로그 사용**합니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-164">Right-click **Analytic** and select **Enable Log**.</span></span>  
  
10. <span data-ttu-id="f0654-165">WCF 테스트 클라이언트를 사용하여 서비스를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-165">Test the service using the WCF Test Client.</span></span>  
  
    1.  <span data-ttu-id="f0654-166">WCF 테스트 클라이언트에서 두 번 클릭 **add ()** ICalculator 서비스 노드에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-166">In the WCF Test Client, double-click **Add()** under the ICalculator service node.</span></span>  
  
         <span data-ttu-id="f0654-167">**add ()** 메서드가 두 개의 매개 변수가 있는 오른쪽 창에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-167">The **Add()** method appears in the right pane with two parameters.</span></span>  
  
    2.  <span data-ttu-id="f0654-168">첫 번째 매개 변수에 2를 입력하고 두 번째 매개 변수에 3을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-168">Type in 2 for the first parameter and 3 for the second parameter.</span></span>  
  
    3.  <span data-ttu-id="f0654-169">클릭 **Invoke** 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-169">Click **Invoke** to invoke the method.</span></span>  
  
11. <span data-ttu-id="f0654-170">이동 하는 **이벤트 뷰어** 이미 열려 있는 창입니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-170">Go to the **Event Viewer** window that you have already opened.</span></span> <span data-ttu-id="f0654-171">로 이동 **이벤트 뷰어**, **Applications and Services Logs**, **Microsoft**, **Windows**, **응용 프로그램 서버-응용 프로그램**합니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-171">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span>  
  
12. <span data-ttu-id="f0654-172">마우스 오른쪽 단추로 클릭는 **분석** 노드 선택한 **새로 고침**합니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-172">Right-click the **Analytic** node and select **Refresh**.</span></span>  
  
     <span data-ttu-id="f0654-173">오른쪽 창에 이벤트가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-173">The events appear in the right pane.</span></span>  
  
13. <span data-ttu-id="f0654-174">ID가 303인 이벤트를 찾아서 두 번 클릭하여 열고 해당 내용을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-174">Locate the event with the ID of 303 and double-click it to open it up and inspect its contents.</span></span>  
  
     <span data-ttu-id="f0654-175">이 이벤트를 내보낸는 `Add()` ICalculator 서비스의 메서드, 페이로드 같음 "2 + 3 = 5"입니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-175">This event was emitted by the `Add()` method of the ICalculator service and has a payload equal to "2+3=5".</span></span>  
  
#### <a name="to-clean-up-optional"></a><span data-ttu-id="f0654-176">정리하려면(옵션)</span><span class="sxs-lookup"><span data-stu-id="f0654-176">To clean up (Optional)</span></span>  
  
1.  <span data-ttu-id="f0654-177">열기 **이벤트 뷰어**합니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-177">Open **Event Viewer**.</span></span>  
  
2.  <span data-ttu-id="f0654-178">로 이동 **이벤트 뷰어**, **Applications and Services Logs**, **Microsoft**, **Windows**, 차례로  **응용 프로그램 서버-응용 프로그램**합니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-178">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application-Server-Applications**.</span></span> <span data-ttu-id="f0654-179">마우스 오른쪽 단추로 클릭 **분석** 선택 **로그 사용 안 함**합니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-179">Right-click **Analytic** and select **Disable Log**.</span></span>  
  
3.  <span data-ttu-id="f0654-180">로 이동 **이벤트 뷰어**, **Applications and Services Logs**, **Microsoft**, **Windows**,  **응용 프로그램 서버-응용 프로그램**, 차례로 **분석**합니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-180">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application-Server-Applications**, and then **Analytic**.</span></span> <span data-ttu-id="f0654-181">마우스 오른쪽 단추로 클릭 **분석** 선택 **로그 지우기**합니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-181">Right-click **Analytic** and select **Clear Log**.</span></span>  
  
4.  <span data-ttu-id="f0654-182">클릭 **지우기** 이벤트의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-182">Click **Clear** to clear the events.</span></span>  
  
## <a name="known-issue"></a><span data-ttu-id="f0654-183">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="f0654-183">Known Issue</span></span>  
 <span data-ttu-id="f0654-184">알려진 문제가 **이벤트 뷰어** ETW 이벤트가 디코딩되지 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-184">There is a known issue in the **Event Viewer** where it may fail to decode ETW events.</span></span> <span data-ttu-id="f0654-185">없다는 오류 메시지가 표시 될 수 있습니다: "이벤트 ID에 대 한 설명 \<id > 소스에서 Microsoft-Windows-응용 프로그램 서버-응용 프로그램을 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-185">You may see an error message that says: "The description for Event ID \<id> from source Microsoft-Windows-Application Server-Applications cannot be found.</span></span> <span data-ttu-id="f0654-186">이 이벤트를 발생시킨 구성 요소가 로컬 컴퓨터에 설치되어 있지 않거나 설치가 손상되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-186">Either the component that raises this event is not installed on your local computer or the installation is corrupted.</span></span> <span data-ttu-id="f0654-187">설치 또는 로컬 컴퓨터에 구성 요소를 복구 합니다. "</span><span class="sxs-lookup"><span data-stu-id="f0654-187">You can install or repair the component on the local computer."</span></span> <span data-ttu-id="f0654-188">이 오류를 발생 하는 경우 선택 **새로 고침** 에서 **동작** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="f0654-188">If you encounter this error, select **Refresh** from the **Actions** menu.</span></span> <span data-ttu-id="f0654-189">그러면 이벤트가 올바르게 디코딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-189">The event should then decode properly.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f0654-190">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-190">The samples may already be installed on your computer.</span></span> <span data-ttu-id="f0654-191">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="f0654-191">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="f0654-192">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="f0654-192">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f0654-193">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0654-193">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ETWTrace`  
  
## <a name="see-also"></a><span data-ttu-id="f0654-194">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f0654-194">See Also</span></span>  
 [<span data-ttu-id="f0654-195">AppFabric 모니터링 샘플</span><span class="sxs-lookup"><span data-stu-id="f0654-195">AppFabric Monitoring Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193959)
