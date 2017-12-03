---
title: "ConcurrencyMode 재진입"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b2046c38-53d8-4a6c-a084-d6c7091d92b1
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bf852c67bec8abb2af3593d537010e5cc2718176
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="concurrencymode-reentrant"></a><span data-ttu-id="16f98-102">ConcurrencyMode 재진입</span><span class="sxs-lookup"><span data-stu-id="16f98-102">ConcurrencyMode Reentrant</span></span>
<span data-ttu-id="16f98-103">이 샘플에서는 서비스 구현에서 ConcurrencyMode.Reentrant 사용의 필요성과 의미를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="16f98-103">This sample demonstrates the necessity and implications of using ConcurrencyMode.Reentrant on a service implementation.</span></span> <span data-ttu-id="16f98-104">ConcurrencyMode.Reentrant는 서비스나 콜백이 특정 시점에 하나의 메시지만 처리한다는 것을 의미합니다(`ConcurencyMode.Single`과 유사함).</span><span class="sxs-lookup"><span data-stu-id="16f98-104">ConcurrencyMode.Reentrant implies that the service (or callback) processes only one message at a given time (analogous to `ConcurencyMode.Single`).</span></span> <span data-ttu-id="16f98-105">스레드로부터 안전을 보장하기 위해 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]는 다른 메시지를 처리할 수 없도록 메시지를 처리하는 `InstanceContext`를 잠급니다.</span><span class="sxs-lookup"><span data-stu-id="16f98-105">To ensure thread safety, [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] locks the `InstanceContext` processing a message so that no other messages can be processed.</span></span> <span data-ttu-id="16f98-106">재진입 모드의 경우 서비스가 나가는 호출을 수행하기 직전에 `InstanceContext`의 잠금이 해제되므로 이 샘플에 나온 것처럼 재진입할 수 있는 후속 호출은 다음에 서비스에 들어갈 때 잠길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16f98-106">In case of Reentrant mode, the `InstanceContext` is unlocked just before the service makes an outgoing call thereby allowing the subsequent call, (which can be reentrant as demonstrated in the sample) to get the lock next time it comes in to the service.</span></span> <span data-ttu-id="16f98-107">이 동작을 설명하기 위해 이 샘플에서는 클라이언트와 서비스가 이중 계약을 사용하여 서로 메시지를 보낼 수 있는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="16f98-107">To demonstrate the behavior, the sample shows how a client and service can send messages between each other using a duplex contract.</span></span>  
  
 <span data-ttu-id="16f98-108">정의된 계약은 서비스에 의해 구현되는 `Ping` 메서드와 클라이언트에 의해 구현되는 콜백 메서드 `Pong`을 가지는 이중 계약입니다.</span><span class="sxs-lookup"><span data-stu-id="16f98-108">The contract defined is a duplex contract with the `Ping` method being implemented by the service and the callback method `Pong` being implemented by the client.</span></span> <span data-ttu-id="16f98-109">클라이언트는 서버의 `Ping` 메서드를 틱 수와 함께 호출하여 호출을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="16f98-109">A client invokes the server's `Ping` method with a tick count thereby initiating the call.</span></span> <span data-ttu-id="16f98-110">서비스는 틱 수가 0이 아닌지 확인한 다음 틱 수를 줄이는 동안 콜백의 `Pong` 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="16f98-110">The service checks whether the tick count is not equal to 0 and then invokes the callbacks `Pong` method while decrementing the tick count.</span></span> <span data-ttu-id="16f98-111">샘플의 다음 코드에서 이 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="16f98-111">This is done by the following code in the sample.</span></span>  
  
```  
public void Ping(int ticks)  
{  
     Console.WriteLine("Ping: Ticks = " + ticks);  
     //Keep pinging back and forth till Ticks reaches 0.  
     if (ticks != 0)  
     {  
         OperationContext.Current.GetCallbackChannel<IPingPongCallback>().Pong((ticks - 1));  
     }  
}  
```  
  
 콜백의 `Pong` 구현은 `Ping` 구현과 동일한 논리를 가집니다. 즉, 틱 수가 0이 아닌지 확인한 다음 1씩 감소하는 틱 수를 사용하여 콜백 채널(이 경우에는 원래 `Ping` 메시지를 보내는 데 사용된 채널)에서 `Ping` 메서드를 호출합니다. 틱 수가 0에 도달하면 메서드가 반환되므로 호출을 시작한 클라이언트의 첫 번째 호출로 모든 회신의 래핑이 해제됩니다. <span data-ttu-id="16f98-115">콜백 구현에서 이를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16f98-115">This is shown in the callback implementation.</span></span>  
  
```  
public void Pong(int ticks)  
{  
    Console.WriteLine("Pong: Ticks = " + ticks);  
    if (ticks != 0)  
    {  
        //Retrieve the Callback  Channel (in this case the Channel which was used to send the  
        //original message) and make an outgoing call until ticks reaches 0.  
        IPingPong channel = OperationContext.Current.GetCallbackChannel<IPingPong>();  
        channel.Ping((ticks - 1));  
    }  
}  
```  
  
 `Ping` 및 `Pong` 메서드는 둘 다 요청/회신이므로 `Ping`에 대한 첫 번째 호출은 `CallbackChannel<T>.Pong()`에 대한 호출이 반환될 때까지 반환되지 않습니다. 클라이언트에서 `Pong` 메서드는 다음 `Ping` 호출이 반환될 때까지 반환될 수 없습니다. <span data-ttu-id="16f98-118">콜백과 서비스는 둘 다 보류 중인 요청에 회신할 수 있으려면 먼저 나가는 요청/회신 호출을 수행해야 하므로 두 구현 모두 ConcurrencyMode.Reentrant 동작으로 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="16f98-118">Because both the callback and the service must make outgoing request/reply calls before they can reply for the pending request, both the implementations must be marked with the ConcurrencyMode.Reentrant behavior.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="16f98-119">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="16f98-119">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="16f98-120">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="16f98-120">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="16f98-121">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="16f98-121">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="16f98-122">지침에 따라 단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="16f98-122">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="16f98-123">세부 항목</span><span class="sxs-lookup"><span data-stu-id="16f98-123">Demonstrates</span></span>  
 <span data-ttu-id="16f98-124">샘플을 실행하려면 클라이언트 및 서버 프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="16f98-124">To run the sample, build the client and server projects.</span></span> <span data-ttu-id="16f98-125">두 개의 명령 창을 열고 디렉터리를 변경는 \<샘플 > \CS\Service\bin\debug 및 \<샘플 > \CS\Client\bin\debug 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="16f98-125">Then open two command windows and change the directories to the \<sample>\CS\Service\bin\debug and \<sample>\CS\Client\bin\debug directories.</span></span> <span data-ttu-id="16f98-126">다음을 입력 하 여 서비스를 시작 `service.exe` 입력 인수로 전달 된 틱의 초기 값을 사용 하 여 Client.exe를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="16f98-126">Then start the service by typing `service.exe` and then invoke the Client.exe with the initial value of ticks passed as an input argument.</span></span> <span data-ttu-id="16f98-127">그러면 10개 틱에 대한 샘플 출력이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="16f98-127">A sample output for 10 ticks is shown.</span></span>  
  
```  
Prompt>Service.exe  
ServiceHost Started. Press Enter to terminate service.  
Ping: Ticks = 10  
Ping: Ticks = 8  
Ping: Ticks = 6  
Ping: Ticks = 4  
Ping: Ticks = 2  
Ping: Ticks = 0  
  
Prompt>Client.exe 10  
Pong: Ticks = 9  
Pong: Ticks = 7  
Pong: Ticks = 5  
Pong: Ticks = 3  
Pong: Ticks = 1  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="16f98-128">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16f98-128">The samples may already be installed on your machine.</span></span> <span data-ttu-id="16f98-129">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="16f98-129">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="16f98-130">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="16f98-130">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="16f98-131">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16f98-131">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Reentrant`  
  
## <a name="see-also"></a><span data-ttu-id="16f98-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="16f98-132">See Also</span></span>
