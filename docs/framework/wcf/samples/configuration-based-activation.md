---
title: "구성 기반 활성화"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 21bb762e-c43e-4b0c-887b-5e434d665838
caps.latest.revision: "26"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cc39a282cbb12b014c0749b3eb807f3248fca16e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="configuration-based-activation"></a><span data-ttu-id="6ed65-102">구성 기반 활성화</span><span class="sxs-lookup"><span data-stu-id="6ed65-102">Configuration-Based Activation</span></span>
<span data-ttu-id="6ed65-103">이 샘플에서는 .svc 파일 없이 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 서비스를 활성화하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6ed65-103">This sample demonstrates how to activate [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] services without requiring a .svc file.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6ed65-104">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ed65-104">The samples may already be installed on your computer.</span></span> <span data-ttu-id="6ed65-105">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="6ed65-105">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="6ed65-106">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="6ed65-106">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="6ed65-107">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ed65-107">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\ConfigBasedActivation`  
  
## <a name="sample-details"></a><span data-ttu-id="6ed65-108">샘플 세부 정보</span><span class="sxs-lookup"><span data-stu-id="6ed65-108">Sample Details</span></span>  
 <span data-ttu-id="6ed65-109">이 샘플에서 클라이언트는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 테스트 클라이언트이고 서비스는 IIS에서 호스팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ed65-109">In this sample, the client is the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] test client and the service is hosted in IIS.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6ed65-110">이 샘플의 설치 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ed65-110">The setup and build instructions for this sample are located at the end of this topic.</span></span>  
  
### <a name="activation-of-services-without-requiring-a-svc-file"></a><span data-ttu-id="6ed65-111">.svc 파일 없이 서비스 활성화</span><span class="sxs-lookup"><span data-stu-id="6ed65-111">Activation of services without requiring a .svc file</span></span>  
 <span data-ttu-id="6ed65-112">[!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)]에서는 서비스를 활성화는 데 .svc 파일이 필요했습니다.</span><span class="sxs-lookup"><span data-stu-id="6ed65-112">In [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)], a .svc file was required for activating a service.</span></span> <span data-ttu-id="6ed65-113">이 경우 응용 프로그램과 함께 추가 파일을 배포 및 유지 관리해야 하므로 관리 오버헤드가 증가했습니다.</span><span class="sxs-lookup"><span data-stu-id="6ed65-113">This caused additional management overhead, because an additional file was required to be deployed and maintained along with the application.</span></span> <span data-ttu-id="6ed65-114">[!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] 릴리스에서는 응용 프로그램 구성 파일을 사용하여 활성화 구성 요소를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ed65-114">With the release of [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)], the activation components can be configured using the application configuration file.</span></span>  
  
 [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)]<span data-ttu-id="6ed65-115">에서는 응용 프로그램 구성 파일의 <xref:System.ServiceModel.Configuration.ServiceActivationElement>에 새 구성 요소(<xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>)가 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6ed65-115"> introduces a new configuration element (<xref:System.ServiceModel.Configuration.ServiceActivationElement>), in the <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection> of the application configuration file.</span></span> <span data-ttu-id="6ed65-116"><xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection> 컬렉션은 다음 코드 예제와 같이 서비스 컬렉션을 받아들여 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="6ed65-116">The <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection> collection accepts a collection of services to activate, as shown in the following code example.</span></span>  
  
```xml  
<serviceActivations>  
   <add relativeAddress="Calculator.svc" service="Microsoft.ServiceModel.Samples.CalculatorService" />  
  
<serviceActivations>  
```  
  
 <span data-ttu-id="6ed65-117">이 구성은 .svc 파일의 구성과 매우 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="6ed65-117">The observation to make is the configuration looks very similar to the configuration of .svc files.</span></span> <span data-ttu-id="6ed65-118">도입된 추가 특성은 서비스의 주소를 제공하는 `relativeAddress`입니다.</span><span class="sxs-lookup"><span data-stu-id="6ed65-118">An additional attribute that is introduced is the `relativeAddress` that provides the address of the service.</span></span> <span data-ttu-id="6ed65-119">또한 상대 주소는 서비스의 가상 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="6ed65-119">The relative address is also the virtual path for the service.</span></span> <span data-ttu-id="6ed65-120">호스트에서는 `virtualPath` 위치에서 파일의 Web.config 파일을 검색하고, 이 파일이 없으면 해당 부모 폴더를 재귀적으로 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="6ed65-120">The host retrieves the Web.config file of the file from the `virtualPath` location, if present; otherwise the host searches its parent folder recursively.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6ed65-121">이 샘플은 IIS에서 호스팅해야 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="6ed65-121">This sample requires hosting in IIS to function.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="6ed65-122">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="6ed65-122">To use this sample</span></span>  
  
1.  <span data-ttu-id="6ed65-123">[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]에서 Service.csproj 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6ed65-123">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the Service.csproj file.</span></span>  
  
2.  <span data-ttu-id="6ed65-124">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="6ed65-124">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="6ed65-125">WCFTestClient.exe를 실행하여 서비스를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="6ed65-125">Test the service by running WCFTestClient.exe.</span></span>  
  
4.  <span data-ttu-id="6ed65-126">[!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)]를 사용하여 %SystemDrive%\Program Files\Microsoft Visual Studio 10.0\Common7\IDE 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="6ed65-126">Using [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], navigate to the %SystemDrive%\Program Files\Microsoft Visual Studio 10.0\Common7\IDE folder.</span></span>  
  
5.  <span data-ttu-id="6ed65-127">WcfTestClient.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6ed65-127">Run WcfTestClient.exe.</span></span>  
  
6.  <span data-ttu-id="6ed65-128">서비스의 MEX 주소를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6ed65-128">Set the MEX address of the service.</span></span>  
  
7.  <span data-ttu-id="6ed65-129">Ctrl+Shift+A를 눌러 서비스 주소를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6ed65-129">Press CTRL+SHIFT+A to set the service address.</span></span>  
  
8.  <span data-ttu-id="6ed65-130">주소를 http://localhost/ServiceModelSamples/Calculator.svc로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6ed65-130">Set the address to http://localhost/ServiceModelSamples/Calculator.svc.</span></span>  
  
9. <span data-ttu-id="6ed65-131">`Add` 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="6ed65-131">Perform the `Add` operation.</span></span> <span data-ttu-id="6ed65-132">`n1` 매개 변수의 값을 10으로 설정하고 `n2` 매개 변수의 값을 15로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6ed65-132">Set value on the `n1` parameter to 10 and set value on the `n2` parameter to 15.</span></span>  
  
10. <span data-ttu-id="6ed65-133">키를 눌러 **호출**합니다.</span><span class="sxs-lookup"><span data-stu-id="6ed65-133">Press **Invoke**.</span></span>  
  
     <span data-ttu-id="6ed65-134">예상 결과는 25입니다.</span><span class="sxs-lookup"><span data-stu-id="6ed65-134">The expected result is 25.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="6ed65-135">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="6ed65-135">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="6ed65-136">수행한 반드시는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6ed65-136">Be sure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="6ed65-137">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="6ed65-137">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="6ed65-138">솔루션을 빌드한 후 Setup.bat를 실행하여 IIS에 ServiceModelSamples 응용 프로그램을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="6ed65-138">After the solution has been built, run Setup.bat to set up the ServiceModelSamples Application in IIS.</span></span> <span data-ttu-id="6ed65-139">이제 ServiceModelSamples 디렉터리가 IIS 응용 프로그램으로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="6ed65-139">The ServiceModelSamples directory should now appear as an IIS Application.</span></span>  
  
4.  <span data-ttu-id="6ed65-140">지침에 따라 단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6ed65-140">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ed65-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6ed65-141">See Also</span></span>  
 [<span data-ttu-id="6ed65-142">AppFabric 호스팅 및 지 속성 샘플</span><span class="sxs-lookup"><span data-stu-id="6ed65-142">AppFabric Hosting and Persistence Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193961)
