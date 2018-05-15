---
title: 예상되는 예외
ms.date: 03/30/2017
ms.assetid: 299a6987-ae6b-43c6-987f-12b034b583ae
ms.openlocfilehash: 6c4af62e0870cdd670c46ead169033ff72902fc0
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="expected-exceptions"></a><span data-ttu-id="8cffd-102">예상되는 예외</span><span class="sxs-lookup"><span data-stu-id="8cffd-102">Expected Exceptions</span></span>
<span data-ttu-id="8cffd-103">이 샘플에서는 형식화된 클라이언트를 사용할 때 예상되는 예외를 catch하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8cffd-103">This sample demonstrates how to catch expected exceptions when using a typed client.</span></span> <span data-ttu-id="8cffd-104">이 샘플에 따라는 [시작](../../../../docs/framework/wcf/samples/getting-started-sample.md) 계산기 서비스를 구현 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cffd-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service.</span></span> <span data-ttu-id="8cffd-105">이 샘플에서 클라이언트는 콘솔 응용 프로그램(.exe)이고 서비스는 IIS(인터넷 정보 서비스)를 통해 호스트됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cffd-105">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8cffd-106">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cffd-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="8cffd-107">이 샘플에서는 올바른 프로그램에서 처리해야 하는 두 가지 예상되는 예외 형식 `TimeoutException` 및 `CommunicationException`을 catch하고 처리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8cffd-107">This sample demonstrates catching and handling the two expected exception types that correct programs must handle: `TimeoutException` and `CommunicationException`.</span></span>  
  
 <span data-ttu-id="8cffd-108">Windows Communication Foundation (WCF) 클라이언트에서 통신 메서드에서 throw 되는 예외는 예상 또는 예기치 않은 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cffd-108">Exceptions that are thrown from communication methods on a Windows Communication Foundation (WCF) client are either expected or unexpected.</span></span> <span data-ttu-id="8cffd-109">예기치 않은 예외에는 `OutOfMemoryException`과 같은 치명적인 실패와 `ArgumentNullException` 또는 `InvalidOperationException` 등의 프로그래밍 오류가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cffd-109">Unexpected exceptions include catastrophic failures like `OutOfMemoryException` and programming errors like `ArgumentNullException` or `InvalidOperationException`.</span></span> <span data-ttu-id="8cffd-110">일반적으로 보통를 catch 하지 말아야 하는 WCF 클라이언트 통신 메서드를 호출할 때, 예기치 않은 오류를 해결 하는 유용한 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cffd-110">Typically there is no useful way to handle unexpected errors, so typically you should not catch them when calling a WCF client communication method.</span></span>  
  
 <span data-ttu-id="8cffd-111">예외는 WCF 클라이언트에서 통신 메서드에서 예상 `TimeoutException`, `CommunicationException`, 및의 모든 파생 클래스가 `CommunicationException`합니다.</span><span class="sxs-lookup"><span data-stu-id="8cffd-111">Expected exceptions from communication methods on a WCF client include `TimeoutException`, `CommunicationException`, and any derived class of `CommunicationException`.</span></span> <span data-ttu-id="8cffd-112">이 WCF 클라이언트를 중단 하 고 통신 실패를 보고 하 여 안전 하 게 처리 될 수 있는 통신 하는 동안 문제를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8cffd-112">These indicate a problem during communication that can be safely handled by aborting the WCF client and reporting a communication failure.</span></span> <span data-ttu-id="8cffd-113">어느 응용 프로그램에서나 외부 요소에 의해 이런 오류가 발생할 수 있기 때문에 올바른 응용 프로그램에서는 이런 예외를 catch할 수 있어야 하며, 이런 예외가 발생한 경우 복구할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cffd-113">Because external factors can cause these errors in any application, correct applications must catch these exceptions and recover when they occur.</span></span>  
  
 <span data-ttu-id="8cffd-114">클라이언트에서 throw할 수 있는 `CommunicationException`의 파생 클래스가 몇 가지 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cffd-114">There are several derived classes of `CommunicationException` that a client can throw.</span></span> <span data-ttu-id="8cffd-115">경우에 따라 응용 프로그램에서 이 중 일부를 catch하여 특수 처리를 수행하고, 나머지는 `CommunicationException`으로 처리할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cffd-115">In some cases, applications also catch some of these to do special handling, but let the others be handled as a `CommunicationException`.</span></span> <span data-ttu-id="8cffd-116">보다 한정된 예외 형식을 먼저 catch한 다음 이후의 catch 절에서 `CommunicationException`을 catch하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cffd-116">This can be accomplished by catching the more specific exception type first and then catching `CommunicationException` in a later catch-clause.</span></span>  
  
 <span data-ttu-id="8cffd-117">클라이언트 통신 메서드를 호출하는 코드는 `TimeoutException` 및 `CommunicationException`을 캐치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cffd-117">Code that calls a client communication method must catch the `TimeoutException` and `CommunicationException`.</span></span> <span data-ttu-id="8cffd-118">그런 오류를 처리하는 방법 중 하나는 클라이언트를 중단하고 통신 오류를 보고하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8cffd-118">One way to handle such errors is to abort the client and report the communication failure.</span></span>  
  
```csharp   
try  
{  
    ...  
    double result = client.Add(value1, value2);  
    ...  
    client.Close();  
}  
catch (TimeoutException exception)  
{  
    Console.WriteLine("Got {0}", exception.GetType());  
    client.Abort();  
}  
catch (CommunicationException exception)  
{  
    Console.WriteLine("Got {0}", exception.GetType());  
    client.Abort();  
}  
```  
  
 <span data-ttu-id="8cffd-119">예상된 예외가 발생한 경우 이후에 클라이언트를 사용할 수 있거나 사용하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cffd-119">If an expected exception occurs, the client may or may not be usable afterwards.</span></span> <span data-ttu-id="8cffd-120">클라이언트를 여전히 사용할 수 있는지 확인하려면 `State` 속성이 `CommunicationState`.Opened인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8cffd-120">To determine if the client is still usable, check that the `State` property is `CommunicationState`.Opened.</span></span> <span data-ttu-id="8cffd-121">아직 열려 있다면 여전히 사용 가능한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8cffd-121">If it is still opened, then it is still usable.</span></span> <span data-ttu-id="8cffd-122">그렇지 않다면 클라이언트를 중단하고 이에 대한 참조를 모두 해제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cffd-122">Otherwise you should abort the client and release all references to it.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="8cffd-123">예외가 발생한 후에 세션이 있는 클라이언트를 더 이상 사용하지 못하게 되는 경우가 많으며, 세션이 없는 클라이언트는 예외가 발생한 후에도 계속 사용 가능한 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="8cffd-123">You may observe that clients that have a session are often no longer usable after an exception, and clients that do not have a session are often still usable after an exception.</span></span> <span data-ttu-id="8cffd-124">하지만 항상 적용되는 사항은 아니기 때문에 예외가 발생한 후에도 클라이언트를 계속 사용해 보려면 `State` 속성을 확인하여 클라이언트가 아직 열려 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cffd-124">However, neither of these is guaranteed, so if you want to try to continue using the client after an exception your application should check the `State` property to verify the client is still opened.</span></span>  
  
 <span data-ttu-id="8cffd-125">샘플을 실행하면 작업 응답 및 예외가 클라이언트 콘솔 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cffd-125">When you run the sample, the operation responses and exceptions are displayed in the client console window.</span></span>  
  
 <span data-ttu-id="8cffd-126">클라이언트 프로세스에서는 두 개의 시나리오를 실행하며, 각 시나리오에서는 `Add` 뒤에 `Divide`를 호출하려 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cffd-126">The client process runs two scenarios, each of which attempts to call `Add` followed by `Divide`.</span></span> <span data-ttu-id="8cffd-127">첫 번째 시나리오에서는 `Divide`에 대한 호출을 수행하기 전에 클라이언트를 중단하여 네트워크 문제를 시뮬레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="8cffd-127">The first scenario simulates a network issue by aborting the client before making the call to `Divide`.</span></span> <span data-ttu-id="8cffd-128">두 번째 시나리오에서는 시간 제한을 메서드가 완료되기에 충분하지 않은 짧은 값으로 설정하여 시간 초과 조건을 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="8cffd-128">The second scenario causes a timeout condition by setting the timeout too short for the method to complete.</span></span> <span data-ttu-id="8cffd-129">클라이언트 프로세스로부터의 예상 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8cffd-129">The expected output from the client process is:</span></span>  
  
```  
Add(100,15.99) = 115.99  
Simulated network problem occurs...  
Got System.ServiceModel.CommunicationObjectAbortedException  
Add(100,15.99) = 115.99  
Set timeout too short for method to complete...  
Got System.TimeoutException  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="8cffd-130">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="8cffd-130">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="8cffd-131">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8cffd-131">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="8cffd-132">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="8cffd-132">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="8cffd-133">지침에 따라 단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8cffd-133">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8cffd-134">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cffd-134">The samples may already be installed on your machine.</span></span> <span data-ttu-id="8cffd-135">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="8cffd-135">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="8cffd-136">이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="8cffd-136">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="8cffd-137">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cffd-137">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Client\ExpectedExceptions`  
  
## <a name="see-also"></a><span data-ttu-id="8cffd-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8cffd-138">See Also</span></span>
