---
title: "ASP.NET 호환성"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c8b51f1e-c096-4c42-ad99-0519887bbbc5
caps.latest.revision: "25"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2c8cf38e65bbc917720b1a1c5b604d81ca536c14
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="aspnet-compatibility"></a><span data-ttu-id="61b6b-102">ASP.NET 호환성</span><span class="sxs-lookup"><span data-stu-id="61b6b-102">ASP.NET Compatibility</span></span>
<span data-ttu-id="61b6b-103">이 샘플에서는 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]에서 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 호환 모드를 사용하도록 설정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="61b6b-103">This sample demonstrates how to enable [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Compatibility mode in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span></span> <span data-ttu-id="61b6b-104">[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 호환 모드에서 실행되는 서비스는 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 응용 프로그램 파이프라인에 완전히 참여하고 파일/URL 권한 부여, 세션 상태 및 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 클래스와 같은 <xref:System.Web.HttpContext> 기능을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61b6b-104">Services running in [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Compatibility mode participate fully in the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] application pipeline and can make use of [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] features such as file/URL authorization, session state, and the <xref:System.Web.HttpContext> class.</span></span> <span data-ttu-id="61b6b-105"><xref:System.Web.HttpContext> 클래스는 쿠키, 세션 및 기타 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 기능에 대한 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="61b6b-105">The <xref:System.Web.HttpContext> class allows access to cookies, sessions, and other [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] features.</span></span> <span data-ttu-id="61b6b-106">이 모드에서는 바인딩에 HTTP 전송이 사용되고 서비스 자체가 IIS에서 호스트되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61b6b-106">This mode requires that the bindings use the HTTP transport and the service itself must be hosted in IIS.</span></span>  
  
 <span data-ttu-id="61b6b-107">이 샘플에서 클라이언트는 콘솔 응용 프로그램(실행 파일)이고 서비스는 IIS(인터넷 정보 서비스)에서 호스트됩니다.</span><span class="sxs-lookup"><span data-stu-id="61b6b-107">In this sample, the client is a console application (an executable) and the service is hosted in Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="61b6b-108">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61b6b-108">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="61b6b-109">이 샘플을 실행하려면 [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] 응용 프로그램 풀이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="61b6b-109">This sample requires a [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] application pool in order to run.</span></span> <span data-ttu-id="61b6b-110">새 응용 프로그램 풀을 만들거나 기본 응용 프로그램 풀을 수정하려면 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="61b6b-110">To create a new application pool, or to modify the default application pool, follow these steps.</span></span>  
>   
>  1.  <span data-ttu-id="61b6b-111">**제어판**을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="61b6b-111">Open **Control Panel**.</span></span>  <span data-ttu-id="61b6b-112">열기는 **관리 도구** 아래 애플릿을 **시스템 및 보안** 제목입니다.</span><span class="sxs-lookup"><span data-stu-id="61b6b-112">Open the **Administrative Tools** applet under the **System and Security** heading.</span></span> <span data-ttu-id="61b6b-113">열기는 **인터넷 정보 서비스 (IIS) 관리자** 애플릿을 합니다.</span><span class="sxs-lookup"><span data-stu-id="61b6b-113">Open the **Internet Information Services (IIS) Manager** applet.</span></span>  
> 2.  <span data-ttu-id="61b6b-114">트리 뷰를 확장 된 **연결** 창.</span><span class="sxs-lookup"><span data-stu-id="61b6b-114">Expand the treeview in the **Connections** pane.</span></span> <span data-ttu-id="61b6b-115">선택 된 **응용 프로그램 풀** 노드.</span><span class="sxs-lookup"><span data-stu-id="61b6b-115">Select the **Application Pools** node.</span></span>  
> 3.  <span data-ttu-id="61b6b-116">기본 응용 프로그램 풀 사용 하도록 설정 하려면 [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] (기존 사이트와의 비 호환성 문제가 발생할 수 있습니다는)을 마우스 오른쪽 단추로 클릭는 **DefaultAppPool** 목록 항목 및 선택 **기본 설정 중...** .</span><span class="sxs-lookup"><span data-stu-id="61b6b-116">To set the default application pool to use [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] (which may cause incompatibility problems with existing sites), right-click the **DefaultAppPool** list item and select **Basic Settings…**.</span></span> <span data-ttu-id="61b6b-117">설정의 **.NET Framework 버전** 풀다운을 **.NET Framework v4.0.30128** (또는 이상).</span><span class="sxs-lookup"><span data-stu-id="61b6b-117">Set the **.Net Framework Version** pull-down to **.Net Framework v4.0.30128** (or later).</span></span>  
> 4.  <span data-ttu-id="61b6b-118">사용 하는 새 응용 프로그램 풀을 만들려면 [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] (유지 하기 위해 다른 응용 프로그램에 대 한 호환성)를 마우스 오른쪽 단추로 클릭는 **응용 프로그램 풀** 노드 선택한 **응용 프로그램 풀 추가...** .</span><span class="sxs-lookup"><span data-stu-id="61b6b-118">To create a new application pool that uses [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] (to preserve compatibility for other applications), right-click the **Application Pools** node and select **Add Application Pool…**.</span></span> <span data-ttu-id="61b6b-119">새 응용 프로그램 풀 이름을 지정 하 고 설정 된 **.NET Framework 버전** 풀다운을 **.NET Framework v4.0.30128** (또는 이상).</span><span class="sxs-lookup"><span data-stu-id="61b6b-119">Name the new application pool, and set the **.Net Framework Version** pull-down to **.Net Framework v4.0.30128** (or later).</span></span> <span data-ttu-id="61b6b-120">아래 단계는 설치 프로그램을 실행 한 후 마우스 오른쪽 단추로 클릭는 **ServiceModelSamples** 응용 프로그램 및 선택 **응용 프로그램 관리**, **고급 설정 중...** .</span><span class="sxs-lookup"><span data-stu-id="61b6b-120">After running the setup steps below, right-click the **ServiceModelSamples** application and select **Manage Application**, **Advanced Settings…**.</span></span> <span data-ttu-id="61b6b-121">설정의 **응용 프로그램 풀** 새 응용 프로그램 풀에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61b6b-121">Set the **Application Pool** to the new application pool.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="61b6b-122">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61b6b-122">The samples may already be installed on your computer.</span></span> <span data-ttu-id="61b6b-123">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="61b6b-123">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="61b6b-124">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="61b6b-124">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="61b6b-125">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61b6b-125">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebHost\ASPNetCompatibility`  
  
 <span data-ttu-id="61b6b-126">이 샘플에 따라는 [시작](../../../../docs/framework/wcf/samples/getting-started-sample.md)를 계산기 서비스를 구현 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="61b6b-126">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md), which implements a calculator service.</span></span> <span data-ttu-id="61b6b-127">실행 결과를 유지하면서 일련의 작업을 수행할 수 있도록 `ICalculator` 계약은 `ICalculatorSession` 계약으로 수정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="61b6b-127">The `ICalculator` contract has been modified as the `ICalculatorSession` contract to allow a set of operations to be performed, while keeping a running result.</span></span>  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface ICalculatorSession  
{  
    [OperationContract]  
    void Clear();  
    [OperationContract]  
    void AddTo(double n);  
    [OperationContract]  
    void SubtractFrom(double n);  
    [OperationContract]  
    void MultiplyBy(double n);  
    [OperationContract]  
    void DivideBy(double n);  
    [OperationContract]  
    double Result();  
}  
```  
  
 <span data-ttu-id="61b6b-128">계산을 수행하기 위해 여러 서비스 작업이 호출될 때 서비스는 이 기능을 사용하여 각 클라이언트에 대한 상태를 유지 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="61b6b-128">The service maintains state, using the feature, for each client as multiple service operations are called to perform a calculation.</span></span> <span data-ttu-id="61b6b-129">클라이언트는 `Result`를 호출하여 현재 결과를 검색하고 `Clear`를 호출하여 결과를 0으로 지울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61b6b-129">The client can retrieve the current result by calling `Result` and can clear the result to zero by calling `Clear`.</span></span>  
  
 <span data-ttu-id="61b6b-130">서비스는 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 세션을 사용하여 각 클라이언트 세션의 결과를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="61b6b-130">The service uses the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] session to store the result for each client session.</span></span> <span data-ttu-id="61b6b-131">따라서 서비스는 여러 서비스 호출에서 각 클라이언트에 대한 실행 결과를 유지 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61b6b-131">This allows the service to maintain the running result for each client across multiple calls to the service.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]<span data-ttu-id="61b6b-132"> 세션 상태와 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 세션은 전혀 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="61b6b-132"> session state and [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sessions are very different things.</span></span>  <span data-ttu-id="61b6b-133">참조는 [세션](../../../../docs/framework/wcf/samples/session.md) 대 한 자세한 내용은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 세션입니다.</span><span class="sxs-lookup"><span data-stu-id="61b6b-133">See the [Session](../../../../docs/framework/wcf/samples/session.md) for details on [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sessions.</span></span>  
  
 <span data-ttu-id="61b6b-134">서비스는 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 세션 상태에 크게 의존하며 올바른 작동을 위해 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 호환 모드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="61b6b-134">The service has an intimate dependency on [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] session state and requires [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] compatibility mode to function correctly.</span></span> <span data-ttu-id="61b6b-135">이러한 요구 사항은 `AspNetCompatibilityRequirements` 특성을 적용하여 선언적으로 표현됩니다.</span><span class="sxs-lookup"><span data-stu-id="61b6b-135">These requirements are expressed declaratively by applying the `AspNetCompatibilityRequirements` attribute.</span></span>  
  
```  
[AspNetCompatibilityRequirements(RequirementsMode =  
                       AspNetCompatibilityRequirementsMode.Required)]  
public class CalculatorService : ICalculatorSession  
{  
    double Result  
    {  // store result in AspNet Session  
       get {  
          if (HttpContext.Current.Session["Result"] != null)  
             return (double)HttpContext.Current.Session["Result"];  
          return 0.0D;  
       }  
       set  
       {  
          HttpContext.Current.Session["Result"] = value;  
       }  
    }  
    public void Clear()  
    {  
        Result = 0.0D;  
    }  
    public void AddTo(double n)  
    {  
        Result += n;  
    }  
    public void SubtractFrom(double n)  
    {  
        Result -= n;  
    }  
    public void MultiplyBy(double n)  
    {  
        Result *= n;  
    }  
    public void DivideBy(double n)  
    {  
        Result /= n;  
    }  
    public double Result()  
    {  
        return Result;  
    }  
}  
```  
  
 <span data-ttu-id="61b6b-136">샘플을 실행하면 작업 요청 및 응답이 클라이언트 콘솔 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="61b6b-136">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="61b6b-137">클라이언트를 종료하려면 클라이언트 창에서 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="61b6b-137">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
0, + 100, - 50, * 17.65, / 2 = 441.25  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="61b6b-138">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="61b6b-138">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="61b6b-139">수행한 반드시는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="61b6b-139">Be sure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="61b6b-140">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="61b6b-140">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="61b6b-141">솔루션을 빌드한 후 Setup.bat를 실행하여 [!INCLUDE[iisver](../../../../includes/iisver-md.md)]에 ServiceModelSamples 응용 프로그램을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="61b6b-141">After the solution has been built, run Setup.bat to set up the ServiceModelSamples Application in [!INCLUDE[iisver](../../../../includes/iisver-md.md)].</span></span> <span data-ttu-id="61b6b-142">이제 ServiceModelSamples 디렉터리가 [!INCLUDE[iisver](../../../../includes/iisver-md.md)] 응용 프로그램으로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="61b6b-142">The ServiceModelSamples directory should now appear as an [!INCLUDE[iisver](../../../../includes/iisver-md.md)] Application.</span></span>  
  
4.  <span data-ttu-id="61b6b-143">지침에 따라 단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="61b6b-143">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61b6b-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="61b6b-144">See Also</span></span>  
 [<span data-ttu-id="61b6b-145">AppFabric 호스팅 및 지 속성 샘플</span><span class="sxs-lookup"><span data-stu-id="61b6b-145">AppFabric Hosting and Persistence Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193961)
