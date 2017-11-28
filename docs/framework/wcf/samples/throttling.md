---
title: "스로틀"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- service behaviors, throttling sample
- Throttling Sample [Windows Communication Foundation]
ms.assetid: 40bb3582-8ae9-4410-96f0-6c515bfaf47c
caps.latest.revision: "18"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 33d7d3be7c28f5fb22bd50f7b57b041abd642c32
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="throttling"></a><span data-ttu-id="fb67b-102">스로틀</span><span class="sxs-lookup"><span data-stu-id="fb67b-102">Throttling</span></span>
<span data-ttu-id="fb67b-103">Throttling 샘플에서는 스로틀 컨트롤을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fb67b-103">The Throttling sample demonstrates the use of throttling controls.</span></span> <span data-ttu-id="fb67b-104">스로틀은 리소스가 과도하게 사용되는 것을 방지하기 위해 동시 호출, 인스턴스 또는 세션 수를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="fb67b-104">Throttling controls place limits on the number of concurrent calls, instances, or sessions to prevent over-consumption of resources.</span></span> <span data-ttu-id="fb67b-105">스로틀 동작은 서비스 구성 파일 설정에 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb67b-105">Throttling behavior is specified in service configuration file settings.</span></span> <span data-ttu-id="fb67b-106">이 샘플에 따라는 [시작](../../../../docs/framework/wcf/samples/getting-started-sample.md) 계산기 서비스를 구현 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb67b-106">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service.</span></span>  
  
 <span data-ttu-id="fb67b-107">이 샘플에서 클라이언트는 콘솔 응용 프로그램(.exe)이고 서비스는 IIS(인터넷 정보 서비스)를 통해 호스트됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb67b-107">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fb67b-108">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb67b-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="fb67b-109">서비스 구성 파일에서 조정 컨트롤을 지정 된 [ \<serviceThrottling >](../../../../docs/framework/configure-apps/file-schema/wcf/servicethrottling.md)다음 샘플 구성에 표시 된 것 처럼 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb67b-109">The service configuration file specifies throttling controls in a [\<serviceThrottling>](../../../../docs/framework/configure-apps/file-schema/wcf/servicethrottling.md), as shown in the following sample configuration.</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="CalculatorServiceBehavior">  
      <serviceDebug includeExceptionDetailInFaults="False" />  
      <serviceMetadata httpGetEnabled="True"/>  
      <!-- Specify throttling behavior -->  
    <serviceThrottling maxConcurrentCalls="2"  
                       maxConcurrentInstances="10"/>  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 <span data-ttu-id="fb67b-110">구성된 것과 같이 서비스에서는 최대 동시 호출을 2로 제한하고 최대 동시 인스턴스 수를 10으로 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="fb67b-110">As configured, the service limits the maximum concurrent calls to 2, and the maximum number of concurrent instances to 10.</span></span>  
  
 <span data-ttu-id="fb67b-111">스로틀을 보여 주기 위해 다음과 같이 서비스 메서드에 절전 모드 시간을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="fb67b-111">In order to demonstrate throttling we define a sleep time on the service methods as follows:</span></span>  
  
```  
public double Add(double n1, double n2)  
{  
    System.Threading.Thread.Sleep(2000);  
    return n1 + n2;  
}  
```  
  
 <span data-ttu-id="fb67b-112">샘플을 실행하면 작업 요청 및 응답이 클라이언트 콘솔 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb67b-112">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="fb67b-113">Add 및 Subtract 메서드가 동시에 실행되고 Multiply 및 Divide 메서드가 동시에 실행되어 최대 2개의 메서드가 동시에 실행될 수 있으므로 스로틀을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb67b-113">The Add and Subtract methods are executed concurrently and the Multiply and Divide methods are executed concurrently proving that not more than 2 methods can be executed concurrently thus demonstrating throttling.</span></span>  
  
```  
Press <ENTER> to terminate client.  
Add(100,15.99)  
Subtract(145,76.54)  
Multiply(9,81.25)  
Divide(22,7)  
  
Add Result: 115.99  
Subtract Result: 68.46  
Multiply Result: 731.25  
Divide Result: 3.14285714285714  
  
Press any key to continue . . .  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="fb67b-114">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="fb67b-114">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="fb67b-115">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fb67b-115">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="fb67b-116">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="fb67b-116">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="fb67b-117">지침에 따라 단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fb67b-117">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="fb67b-118">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb67b-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="fb67b-119">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="fb67b-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="fb67b-120">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="fb67b-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="fb67b-121">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb67b-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Behaviors\Throttling`  
  
## <a name="see-also"></a><span data-ttu-id="fb67b-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fb67b-122">See Also</span></span>
