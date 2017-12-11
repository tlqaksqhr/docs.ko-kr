---
title: "전송: UDP 샘플에 의한 사용자 지정 트랜잭션"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6cebf975-41bd-443e-9540-fd2463c3eb23
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b17cb737533f1542b5f702097da4592df8e17eac
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="transport-custom-transactions-over-udp-sample"></a><span data-ttu-id="6fcc8-102">전송: UDP 샘플에 의한 사용자 지정 트랜잭션</span><span class="sxs-lookup"><span data-stu-id="6fcc8-102">Transport: Custom Transactions over UDP Sample</span></span>
<span data-ttu-id="6fcc8-103">이 샘플에 따라는 [전송: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) 샘플는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] [전송 확장성](../../../../docs/framework/wcf/samples/transport-extensibility.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6fcc8-103">This sample is based on the [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) sample in the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)][Transport Extensibility](../../../../docs/framework/wcf/samples/transport-extensibility.md).</span></span> <span data-ttu-id="6fcc8-104">이 샘플은 사용자 지정 트랜잭션 흐름을 지원하도록 UDP 전송 샘플을 확장하고 <xref:System.ServiceModel.Channels.TransactionMessageProperty> 속성의 사용 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6fcc8-104">It extends the UDP Transport sample to support custom transaction flow and demonstrates the use of the <xref:System.ServiceModel.Channels.TransactionMessageProperty> property.</span></span>  
  
## <a name="code-changes-in-the-udp-transport-sample"></a><span data-ttu-id="6fcc8-105">UDP 전송 샘플의 코드 변경</span><span class="sxs-lookup"><span data-stu-id="6fcc8-105">Code Changes in the UDP Transport Sample</span></span>  
 <span data-ttu-id="6fcc8-106">트랜잭션 흐름을 보여 주기 위해 이 샘플에서는 `ICalculatorContract`의 트랜잭션 범위가 필요하도록 `CalculatorService.Add()`의 서비스 계약을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="6fcc8-106">To demonstrate transaction flow, the sample changes the service contract for `ICalculatorContract` to require a transaction scope for `CalculatorService.Add()`.</span></span> <span data-ttu-id="6fcc8-107">또한 `System.Guid` 작업의 계약에 `Add` 매개 변수를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6fcc8-107">The sample also adds an extra `System.Guid` parameter to the contract of the `Add` operation.</span></span> <span data-ttu-id="6fcc8-108">이 매개 변수는 클라이언트 트랜잭션의 식별자를 서비스에 전달하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fcc8-108">This parameter is used to pass the identifier of the client transaction to the service.</span></span>  
  
```  
class CalculatorService : IDatagramContract, ICalculatorContract  
{  
    [OperationBehavior(TransactionScopeRequired=true)]  
    public int Add(int x, int y, Guid clientTransactionId)  
    {  
        if(Transaction.Current.TransactionInformation.DistributedIdentifier == clientTransactionId)  
    {  
        Console.WriteLine("The client transaction has flowed to the service");  
    }  
    else  
    {  
     Console.WriteLine("The client transaction has NOT flowed to the service");  
    }  
  
    Console.WriteLine("   adding {0} + {1}", x, y);              
    return (x + y);  
    }  
  
    [...]  
}  
```  
  
 <span data-ttu-id="6fcc8-109">[전송: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) 샘플 UDP 패킷을 사용 하 여 클라이언트와 서비스 간의 메시지를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fcc8-109">The [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) sample uses UDP packets to pass messages between a client and a service.</span></span> <span data-ttu-id="6fcc8-110">[전송: 사용자 지정 전송 샘플](../../../../docs/framework/wcf/samples/transport-custom-transactions-over-udp-sample.md) 동일한 메커니즘을 사용 하 여 메시지를 전송 하려면 되지만 트랜잭션이 이동은 인코딩된 메시지와 함께 UDP 패킷을에 삽입 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fcc8-110">The [Transport: Custom Transport Sample](../../../../docs/framework/wcf/samples/transport-custom-transactions-over-udp-sample.md) uses the same mechanism to transport messages, but when a transaction is flowed, it is inserted into the UDP packet along with the encoded message.</span></span>  
  
```  
byte[] txmsgBuffer =                TransactionMessageBuffer.WriteTransactionMessageBuffer(txPropToken, messageBuffer);  
  
int bytesSent = this.socket.SendTo(txmsgBuffer, 0, txmsgBuffer.Length, SocketFlags.None, this.remoteEndPoint);  
```  
  
 <span data-ttu-id="6fcc8-111">`TransactionMessageBuffer.WriteTransactionMessageBuffer`는 현재 트랜잭션의 전파 토큰을 메시지 엔터티와 병합하고 이를 버퍼에 배치하는 새로운 기능이 포함된 도우미 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="6fcc8-111">`TransactionMessageBuffer.WriteTransactionMessageBuffer` is a helper method that contains new functionality to merge the propagation token for the current transaction with the message entity and place it into a buffer.</span></span>  
  
 <span data-ttu-id="6fcc8-112">사용자 지정 트랜잭션 흐름 전송의 경우 클라이언트 구현에서는 트랜잭션 흐름이 필요한 서비스 작업을 파악하고 이 정보를 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fcc8-112">For custom transaction flow transport, the client implementation must know what service operations require transaction flow and to pass this information to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="6fcc8-113">또한 사용자 트랜잭션을 전송 계층으로 전송하기 위한 메커니즘도 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fcc8-113">There should also be a mechanism for transmitting the user transaction to the transport layer.</span></span> <span data-ttu-id="6fcc8-114">이 샘플에서는 "[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 메시지 검사자"를 사용하여 이 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6fcc8-114">This sample uses "[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] message inspectors" to obtain this information.</span></span> <span data-ttu-id="6fcc8-115">여기서 구현된 `TransactionFlowInspector`라는 클라이언트 메시지 검사자는 다음 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="6fcc8-115">The client message inspector implemented here, which is called `TransactionFlowInspector`, performs the following tasks:</span></span>  
  
-   <span data-ttu-id="6fcc8-116">지정된 메시지 작업에 대해 트랜잭션을 이동해야 하는지 여부를 결정합니다. 이 작업은 `IsTxFlowRequiredForThisOperation()`에서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fcc8-116">Determines whether a transaction must be flowed for a given message action (this takes place in `IsTxFlowRequiredForThisOperation()`).</span></span>  
  
-   <span data-ttu-id="6fcc8-117">트랜잭션을 이동해야 하는 경우 `TransactionFlowProperty`를 사용하여 현재 앰비언트 트랜잭션을 메시지에 연결합니다. 이 작업은 `BeforeSendRequest()`에서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fcc8-117">Attaches the current ambient transaction to the message using `TransactionFlowProperty`, if a transaction is required to be flowed (this is done in `BeforeSendRequest()`).</span></span>  
  
```  
public class TransactionFlowInspector : IClientMessageInspector  
{  
   void IClientMessageInspector.AfterReceiveReply(ref           System.ServiceModel.Channels.Message reply, object correlationState)  
  {  
  }  
  
   public object BeforeSendRequest(ref System.ServiceModel.Channels.Message request, System.ServiceModel.IClientChannel channel)  
   {  
       // obtain the tx propagation token  
       byte[] propToken = null;             
       if (Transaction.Current != null && IsTxFlowRequiredForThisOperation(request.Headers.Action))  
       {  
           try  
           {  
               propToken = TransactionInterop.GetTransmitterPropagationToken(Transaction.Current);  
           }  
           catch (TransactionException e)  
           {  
              throw new CommunicationException("TransactionInterop.GetTransmitterPropagationToken failed.", e);  
           }  
       }  
  
      // set the propToken on the message in a TransactionFlowProperty  
       TransactionFlowProperty.Set(propToken, request);  
  
       return null;              
    }  
  }  
  
  static bool IsTxFlowRequiredForThisOperation(String action)  
 {  
       // In general, this should contain logic to identify which operations (actions)      require transaction flow.  
      [...]  
 }  
}  
```  
  
 <span data-ttu-id="6fcc8-118">`TransactionFlowInspector` 자체는 사용자 지정 동작인 `TransactionFlowBehavior`를 사용하여 프레임워크에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fcc8-118">The `TransactionFlowInspector` itself is passed to the framework using a custom behavior: the `TransactionFlowBehavior`.</span></span>  
  
```  
public class TransactionFlowBehavior : IEndpointBehavior  
{  
       public void AddBindingParameters(ServiceEndpoint endpoint,            System.ServiceModel.Channels.BindingParameterCollection bindingParameters)  
      {  
      }  
  
       public void ApplyClientBehavior(ServiceEndpoint endpoint, System.ServiceModel.Dispatcher.ClientRuntime clientRuntime)  
      {  
            TransactionFlowInspector inspector = new TransactionFlowInspector();  
            clientRuntime.MessageInspectors.Add(inspector);  
      }  
  
      public void ApplyDispatchBehavior(ServiceEndpoint endpoint, System.ServiceModel.Dispatcher.EndpointDispatcher endpointDispatcher)  
     {  
     }  
  
      public void Validate(ServiceEndpoint endpoint)  
      {  
      }  
}  
```  
  
 <span data-ttu-id="6fcc8-119">위 메커니즘을 유지한 상태에서 사용자 코드는 서비스 작업을 호출하기 전에 `TransactionScope`를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6fcc8-119">With the preceding mechanism in place, the user code creates a `TransactionScope` before calling the service operation.</span></span> <span data-ttu-id="6fcc8-120">트랜잭션을 서비스 작업으로 이동해야 하는 경우 메시지 검사자는 트랜잭션이 전송에 전달되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6fcc8-120">The message inspector ensures that the transaction is passed to the transport in case it is required to be flowed to the service operation.</span></span>  
  
```  
CalculatorContractClient calculatorClient = new CalculatorContractClient("SampleProfileUdpBinding_ICalculatorContract");  
calculatorClient.Endpoint.Behaviors.Add(new TransactionFlowBehavior());               
  
try  
{  
       for (int i = 0; i < 5; ++i)  
      {  
              // call the 'Add' service operation under a transaction scope  
             using (TransactionScope ts = new TransactionScope())  
             {  
        [...]  
        Console.WriteLine(calculatorClient.Add(i, i * 2));  
         }  
      }               
       calculatorClient.Close();  
}  
catch (TimeoutException)  
{  
    calculatorClient.Abort();  
}  
catch (CommunicationException)  
{  
    calculatorClient.Abort();  
}  
catch (Exception)  
{  
    calculatorClient.Abort();  
    throw;  
}  
```  
  
 <span data-ttu-id="6fcc8-121">서비스는 클라이언트로부터 UDP 패킷을 수신한 다음 이 패킷을 deserialize하여 메시지와 트랜잭션을 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="6fcc8-121">Upon receiving a UDP packet from the client, the service deserializes it to extract the message and possibly a transaction.</span></span>  
  
```  
count = listenSocket.EndReceiveFrom(result, ref dummy);  
  
// read the transaction and message                       TransactionMessageBuffer.ReadTransactionMessageBuffer(buffer, count, out transaction, out msg);  
```  
  
 <span data-ttu-id="6fcc8-122">`TransactionMessageBuffer.ReadTransactionMessageBuffer()`는 `TransactionMessageBuffer.WriteTransactionMessageBuffer()`가 수행한 serialization 프로세스를 반대로 하는 도우미 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="6fcc8-122">`TransactionMessageBuffer.ReadTransactionMessageBuffer()` is the helper method that reverses the serialization process performed by `TransactionMessageBuffer.WriteTransactionMessageBuffer()`.</span></span>  
  
 <span data-ttu-id="6fcc8-123">트랜잭션이 이동하면 `TransactionMessageProperty`의 메시지에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fcc8-123">If a transaction was flowed in, it is appended to the message in the `TransactionMessageProperty`.</span></span>  
  
```  
message = MessageEncoderFactory.Encoder.ReadMessage(msg, bufferManager);  
  
if (transaction != null)  
{  
       TransactionMessageProperty.Set(transaction, message);  
}  
```  
  
 <span data-ttu-id="6fcc8-124">이렇게 하면 디스패처가 디스패치할 때 트랜잭션을 선택한 다음 메시지에 설명된 서비스 작업을 호출할 때 이 트랜잭션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6fcc8-124">This ensures that the dispatcher picks up the transaction at dispatch time and uses it when calling the service operation addressed by the message.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="6fcc8-125">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="6fcc8-125">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="6fcc8-126">지침에 따라 솔루션을 빌드하려면 [Windows Communication Foundation 샘플 빌드](../../../../docs/framework/wcf/samples/building-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6fcc8-126">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2.  <span data-ttu-id="6fcc8-127">현재 샘플 유사 하 게 실행 해야는 [전송: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) 샘플.</span><span class="sxs-lookup"><span data-stu-id="6fcc8-127">The current sample should be run similarly to the [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) sample.</span></span> <span data-ttu-id="6fcc8-128">이 샘플을 실행하려면 UdpTestService.exe를 실행하여 서비스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="6fcc8-128">To run it, start the service with UdpTestService.exe.</span></span> <span data-ttu-id="6fcc8-129">[!INCLUDE[windowsver](../../../../includes/windowsver-md.md)]를 실행하는 경우에는 높은 권한으로 서비스를 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fcc8-129">If you are running [!INCLUDE[windowsver](../../../../includes/windowsver-md.md)], you must start the service with elevated privileges.</span></span> <span data-ttu-id="6fcc8-130">이렇게 하려면에서 UdpTestService.exe를 마우스 오른쪽 단추로 [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] 클릭 **관리자 권한으로 실행**합니다.</span><span class="sxs-lookup"><span data-stu-id="6fcc8-130">To do so, right-click UdpTestService.exe in [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] and click **Run as administrator**.</span></span>  
  
3.  <span data-ttu-id="6fcc8-131">다음과 같은 출력이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fcc8-131">This produces the following output.</span></span>  
  
    ```  
    Testing Udp From Code.  
    Service is started from code...  
    Press <ENTER> to terminate the service and start service from config...  
    ```  
  
4.  <span data-ttu-id="6fcc8-132">이때 UdpTestClient.exe를 실행하여 클라이언트를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fcc8-132">At this time, you can start the client by running UdpTestClient.exe.</span></span> <span data-ttu-id="6fcc8-133">클라이언트에서 생성되는 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6fcc8-133">The output produced by the client is as follows.</span></span>  
  
    ```  
    0  
    3  
    6  
    9  
    12  
    Press <ENTER> to complete test.  
    ```  
  
5.  <span data-ttu-id="6fcc8-134">서비스 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6fcc8-134">The service output is as follows.</span></span>  
  
    ```  
    Hello, world!  
    Hello, world!  
    Hello, world!  
    Hello, world!  
    Hello, world!  
    The client transaction has flowed to the service  
       adding 0 + 0  
    The client transaction has flowed to the service  
       adding 1 + 2  
    The client transaction has flowed to the service  
       adding 2 + 4  
    The client transaction has flowed to the service  
       adding 3 + 6  
    The client transaction has flowed to the service  
       adding 4 + 8  
    ```  
  
6.  <span data-ttu-id="6fcc8-135">서비스 응용 프로그램은 클라이언트가 보낸, `The client transaction has flowed to the service` 작업의 `clientTransactionId` 매개 변수에 포함된 트랜잭션 식별자를 서비스 트랜잭션의 식별자와 일치시킬 수 있는 경우 `CalculatorService.Add()`라는 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="6fcc8-135">The service application displays the message `The client transaction has flowed to the service` if it can match the transaction identifier sent by the client, in the `clientTransactionId` parameter of the `CalculatorService.Add()` operation, to the identifier of the service transaction.</span></span> <span data-ttu-id="6fcc8-136">이 두 식별자는 클라이언트 트랜잭션이 서비스로 이동한 경우에만 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="6fcc8-136">A match is obtained only if the client transaction has flowed to the service.</span></span>  
  
7.  <span data-ttu-id="6fcc8-137">구성을 사용하여 게시된 끝점에 대해 클라이언트 응용 프로그램을 실행하려면 서비스 응용 프로그램 창에서 Enter 키를 누른 다음 테스트 클라이언트를 다시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6fcc8-137">To run the client application against endpoints published using configuration, press ENTER on the service application window and then run the test client again.</span></span> <span data-ttu-id="6fcc8-138">서비스에서 다음과 같이 출력되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fcc8-138">You should see the following output on the service.</span></span>  
  
    ```  
    Testing Udp From Config.  
    Service is started from config...  
    Press <ENTER> to terminate the service and exit...  
    ```  
  
8.  <span data-ttu-id="6fcc8-139">서비스에 대해 클라이언트를 실행하면 이전과 비슷한 출력이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fcc8-139">Running the client against the service now produces similar output as before.</span></span>  
  
9. <span data-ttu-id="6fcc8-140">Svcutil.exe를 사용하여 클라이언트 코드 및 구성을 다시 생성하려면 서비스 응용 프로그램을 시작한 다음 샘플의 루트 디렉터리에서 다음 Svcutil.exe 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6fcc8-140">To regenerate the client code and configuration using Svcutil.exe, start the service application and then run the following Svcutil.exe command from the root directory of the sample.</span></span>  
  
    ```  
    svcutil http://localhost:8000/udpsample/ /reference:UdpTranport\bin\UdpTransport.dll /svcutilConfig:svcutil.exe.config  
    ```  
  
10. <span data-ttu-id="6fcc8-141">Svcutil.exe는 `sampleProfileUdpBinding`에 대한 바인딩 확장 구성을 생성하지 않으므로 직접 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fcc8-141">Note that Svcutil.exe does not generate the binding extension configuration for the `sampleProfileUdpBinding`; you must add it manually.</span></span>  
  
    ```xml  
    <configuration>  
        <system.serviceModel>      
            …  
            <extensions>  
                <!-- This was added manually because svcutil.exe does not add this extension to the file -->  
                <bindingExtensions>  
                    <add name="sampleProfileUdpBinding" type="Microsoft.ServiceModel.Samples.SampleProfileUdpBindingCollectionElement, UdpTransport" />  
                </bindingExtensions>  
            </extensions>  
        </system.serviceModel>  
    </configuration>  
    ```  
  
> [!IMPORTANT]
>  <span data-ttu-id="6fcc8-142">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fcc8-142">The samples may already be installed on your machine.</span></span> <span data-ttu-id="6fcc8-143">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="6fcc8-143">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="6fcc8-144">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="6fcc8-144">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="6fcc8-145">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fcc8-145">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Transactions\TransactionMessagePropertyUDPTransport`  
  
## <a name="see-also"></a><span data-ttu-id="6fcc8-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6fcc8-146">See Also</span></span>  
 [<span data-ttu-id="6fcc8-147">전송: UDP</span><span class="sxs-lookup"><span data-stu-id="6fcc8-147">Transport: UDP</span></span>](../../../../docs/framework/wcf/samples/transport-udp.md)
