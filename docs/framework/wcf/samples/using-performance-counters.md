---
title: "성능 카운터 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 00a787af-1876-473c-a48d-f52b51e28a3f
caps.latest.revision: "31"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 84cbbf83c240ae11099e2c9646150c810a437e71
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="using-performance-counters"></a><span data-ttu-id="98344-102">성능 카운터 사용</span><span class="sxs-lookup"><span data-stu-id="98344-102">Using Performance Counters</span></span>
<span data-ttu-id="98344-103">이 샘플은 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 성능 카운터에 액세스하고 사용자 정의 성능 카운터를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="98344-103">This sample demonstrates how to access [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] performance counters and how to create user-defined performance counters.</span></span> <span data-ttu-id="98344-104">이 샘플에 따라는 [시작](../../../../docs/framework/wcf/samples/getting-started-sample.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="98344-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="98344-105">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98344-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="98344-106">이 샘플에서 클라이언트는 `ICalculator` 서비스의 메서드 4개를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="98344-106">In this sample, the client calls the four methods of the `ICalculator` service.</span></span> <span data-ttu-id="98344-107">클라이언트는 사용자가 중단할 때까지 이 작업을 계속 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="98344-107">The client continues to do this until it is interrupted by the user.</span></span> <span data-ttu-id="98344-108">서비스는 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="98344-108">The service remains unchanged.</span></span>  
  
 <span data-ttu-id="98344-109">성능 카운터는 다음 샘플 구성에 표시된 것과 같이 서비스에 대한 Web.config 파일의 진단 섹션에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98344-109">Performance counters are enabled in the diagnostics section of the Web.config file for the service, as shown in the following sample configuration.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <diagnostics performanceCounters="All" />   
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="98344-110">이 작업을 수행할 수도 있습니다를 사용 하 여 [Configuration Editor 도구 (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="98344-110">This task can also be done using the [Configuration Editor Tool (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).</span></span>  
  
 <span data-ttu-id="98344-111">성능 카운터가 사용되면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 성능 카운터 모음 전체가 서비스에 대해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="98344-111">When performance counters are enabled, the entire suite of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] performance counters is enabled for the service.</span></span> <span data-ttu-id="98344-112">.NET Framework는 `ServiceModelService`, `ServiceModelEndpoint` 및 `ServiceModelOperation`의 세 가지 수준에서 성능 데이터를 자동으로 유지 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="98344-112">The .NET Framework automatically maintains performance data at three levels: `ServiceModelService`, `ServiceModelEndpoint` and `ServiceModelOperation`.</span></span> <span data-ttu-id="98344-113">이러한 각 수준에는 "Calls", "Calls per Second" 및 "Security Calls Not Authorized"와 같은 성능 카운터가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98344-113">Each of these levels has performance counters such as "Calls", "Calls per Second", and "Security Calls Not Authorized".</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="98344-114">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="98344-114">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="98344-115">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="98344-115">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="98344-116">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="98344-116">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="98344-117">지침에 따라 단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="98344-117">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
### <a name="to-view-performance-data"></a><span data-ttu-id="98344-118">성능 데이터를 보려면</span><span class="sxs-lookup"><span data-stu-id="98344-118">To view performance data</span></span>  
  
1.  <span data-ttu-id="98344-119">클릭 하 여 성능 모니터 도구를 시작 **시작**, **실행...** , 입력 `perfmon` 클릭 **확인** 하거나 제어판에서 선택 **관리 도구** 두 번 클릭 하 고 **성능**합니다.</span><span class="sxs-lookup"><span data-stu-id="98344-119">Start the Performance Monitor Tool by clicking **Start**, **Run…**, enter `perfmon` and click **OK,** or from Control Panel, select **Administrative Tools** and double-click **Performance**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="98344-120">샘플 코드가 실행될 때까지는 카운터를 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="98344-120">You cannot add counters until the sample code is running.</span></span>  
  
2.  <span data-ttu-id="98344-121">나열된 성능 카운터를 선택한 다음 Delete 키를 누르면 성능 카운터를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98344-121">Remove the performance counters that are listed by selecting them and pressing the Delete key.</span></span>  
  
3.  <span data-ttu-id="98344-122">추가 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 그래프 창을 마우스 오른쪽 단추로 클릭 하 고 선택 하 여 카운터 **카운터 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="98344-122">Add [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] counters by right-clicking the graph pane and selecting **Add Counters**.</span></span> <span data-ttu-id="98344-123">에 **카운터 추가** 대화 상자에서 **ServiceModelOperation 3.0.0.0, ServiceModelEndpoint 3.0.0.0 또는 ServiceModelService 3.0.0.0** 성능 개체에 있는 드롭다운 목록 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="98344-123">In the **Add Counters** dialog box, select **ServiceModelOperation 3.0.0.0, ServiceModelEndpoint 3.0.0.0, or ServiceModelService 3.0.0.0** in the Performance object drop down list box.</span></span> <span data-ttu-id="98344-124">목록에서 보려는 카운터를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="98344-124">Select the counters you want to view from the list.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="98344-125">컴퓨터에서 실행 중인 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스가 없는 경우에는 서비스의 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 성능 카운터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="98344-125">There are no [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] performance counters for a service if there are no [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services running on the computer.</span></span>  
  
### <a name="to-use-the-configuration-editor-to-enable-counters"></a><span data-ttu-id="98344-126">Configuration Editor를 사용하여 카운터를 사용하려면</span><span class="sxs-lookup"><span data-stu-id="98344-126">To use the Configuration Editor to enable counters</span></span>  
  
1.  <span data-ttu-id="98344-127">SvcConfigEditor.exe의 인스턴스를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="98344-127">Open an instance of the SvcConfigEditor.exe.</span></span>  
  
2.  <span data-ttu-id="98344-128">파일 메뉴에서 클릭 **열려** 클릭 한 다음 **구성 파일 중...** .</span><span class="sxs-lookup"><span data-stu-id="98344-128">On the File menu, click **Open** and then click **Config file…**.</span></span>  
  
3.  <span data-ttu-id="98344-129">샘플 응용 프로그램의 서비스 폴더로 이동한 다음 Web.config 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="98344-129">Navigate to the sample application's service folder and open the Web.config file.</span></span>  
  
4.  <span data-ttu-id="98344-130">클릭 **진단** 구성 트리에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="98344-130">Click **Diagnostics** on the Configuration tree.</span></span>  
  
5.  <span data-ttu-id="98344-131">설정/해제 **성능 카운터** 에 **진단** '모두' 표시 하기 위해 창입니다.</span><span class="sxs-lookup"><span data-stu-id="98344-131">Toggle **Performance Counter** in the **Diagnostics** window to show 'All'.</span></span>  
  
6.  <span data-ttu-id="98344-132">구성 파일을 저장하고 편집기를 끝냅니다.</span><span class="sxs-lookup"><span data-stu-id="98344-132">Save the configuration file and exit the editor.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="98344-133">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98344-133">The samples may already be installed on your computer.</span></span> <span data-ttu-id="98344-134">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="98344-134">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="98344-135">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="98344-135">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="98344-136">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98344-136">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\PerfCounters`  
  
## <a name="see-also"></a><span data-ttu-id="98344-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="98344-137">See Also</span></span>  
 [<span data-ttu-id="98344-138">AppFabric 모니터링 샘플</span><span class="sxs-lookup"><span data-stu-id="98344-138">AppFabric Monitoring Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193959)
