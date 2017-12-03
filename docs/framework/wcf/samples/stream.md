---
title: "스트림"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 58a3db81-20ab-4627-bf31-39d30b70b4fe
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c0cbbae6ae8ba486791c525b70e8d208880661d7
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="stream"></a><span data-ttu-id="816fe-102">스트림</span><span class="sxs-lookup"><span data-stu-id="816fe-102">Stream</span></span>
<span data-ttu-id="816fe-103">Stream 샘플에서는 스트리밍 전송 모드 통신의 사용 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="816fe-103">The Stream sample demonstrates the use of streaming transfer mode communication.</span></span> <span data-ttu-id="816fe-104">이 서비스는 스트림을 보내고 받는 몇 가지 작업을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="816fe-104">The service exposes several operations that send and receive streams.</span></span> <span data-ttu-id="816fe-105">이 샘플은 자체 호스팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="816fe-105">This sample is self-hosted.</span></span> <span data-ttu-id="816fe-106">클라이언트와 서버는 모두 콘솔 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="816fe-106">Both the client and service are console programs.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="816fe-107">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="816fe-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="816fe-108">는 버퍼링 모드와 스트리밍 모드의 두 가지 전송 모드로 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="816fe-108"> can communicate in two transfer modes—buffered or streaming.</span></span> <span data-ttu-id="816fe-109">기본 설정인 버퍼링 전송 모드에서는 메시지가 완전히 전달되어야 수신자가 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="816fe-109">In the default buffered transfer mode, a message must be completely delivered before a receiver can read it.</span></span> <span data-ttu-id="816fe-110">스트리밍 전송 모드에서는 메시지가 완전히 전달되기 전에 수신자가 메시지 처리를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="816fe-110">In the streaming transfer mode, the receiver can begin to process the message before it is completely delivered.</span></span> <span data-ttu-id="816fe-111">전달되는 정보가 길고 순차적으로 처리 가능한 경우 스트리밍 모드가 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="816fe-111">The streaming mode is useful when the information that is passed is lengthy and can be processed serially.</span></span> <span data-ttu-id="816fe-112">또한 전체를 버퍼링하기에는 메시지가 너무 큰 경우에도 스트리밍 모드가 효과적입니다.</span><span class="sxs-lookup"><span data-stu-id="816fe-112">Streaming mode is also useful when the message is too large to be entirely buffered.</span></span>  
  
## <a name="streaming-and-service-contracts"></a><span data-ttu-id="816fe-113">스트리밍 및 서비스 계약</span><span class="sxs-lookup"><span data-stu-id="816fe-113">Streaming and Service Contracts</span></span>  
 <span data-ttu-id="816fe-114">스트리밍은 서비스 계약을 설계할 때 고려할 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="816fe-114">Streaming is something to be considered when designing a service contract.</span></span> <span data-ttu-id="816fe-115">어떤 작업에서 많은 양의 데이터를 수신하거나 반환할 경우 입출력 메시지의 버퍼링 때문에 지나치게 많은 메모리가 사용되지 않도록 이 데이터를 스트리밍하는 것을 고려할 필요가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="816fe-115">If an operation receives or returns large amounts of data, you should consider streaming this data to avoid high memory utilization due to buffering of input or output messages.</span></span> <span data-ttu-id="816fe-116">데이터를 스트리밍하려면 그 데이터를 포함하는 매개 변수가 메시지에서 유일한 매개 변수가 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="816fe-116">To stream data, the parameter that holds that data must be the only parameter in the message.</span></span> <span data-ttu-id="816fe-117">예를 들어, 입력 메시지를 스트리밍할 경우 해당 작업은 단 하나의 입력 매개 변수만 가져야 합니다.</span><span class="sxs-lookup"><span data-stu-id="816fe-117">For example, if the input message is the one to be streamed, the operation must have exactly one input parameter.</span></span> <span data-ttu-id="816fe-118">마찬가지로, 출력 메시지를 스트리밍할 경우 해당 작업에는 출력 매개 변수 또는 반환 값이 하나만 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="816fe-118">Similarly, if the output message is to be streamed, the operation must have either exactly one output parameter or a return value.</span></span> <span data-ttu-id="816fe-119">두 경우 모두 매개 변수 또는 반환 값 형식은 `Stream`, `Message` 또는 `IXmlSerializable`이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="816fe-119">In either case, the parameter or return value type must be either `Stream`, `Message`, or `IXmlSerializable`.</span></span> <span data-ttu-id="816fe-120">다음은 이 스트리밍 샘플에서 사용된 서비스 계약입니다.</span><span class="sxs-lookup"><span data-stu-id="816fe-120">The following is the service contract used in this streaming sample.</span></span>  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface IStreamingSample  
{  
    [OperationContract]  
    Stream GetStream(string data);  
    [OperationContract]  
    bool UploadStream(Stream stream);  
    [OperationContract]  
    Stream EchoStream(Stream stream);  
    [OperationContract]  
    Stream GetReversedStream();  
  
}  
```  
  
 <span data-ttu-id="816fe-121">`GetStream` 작업은 버퍼링되는 문자열로 입력 데이터를 받고, 스트리밍되는 `Stream`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="816fe-121">The `GetStream` operation receives some input data as a string, which is buffered, and returns a `Stream`, which is streamed.</span></span> <span data-ttu-id="816fe-122">반대로, `UploadStream`은 스트리밍된 `Stream`을 받아 버퍼링된 `bool`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="816fe-122">Conversely, `UploadStream` takes in a `Stream` (streamed) and returns a `bool` (buffered).</span></span> <span data-ttu-id="816fe-123">`EchoStream`은 `Stream`을 받고 반환하므로 입출력 메시지 모두 스트리밍되는 작업의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="816fe-123">`EchoStream` takes and returns `Stream` and is an example of an operation whose input and output messages are both streamed.</span></span> <span data-ttu-id="816fe-124">마지막으로, `GetReversedStream`은 어떤 입력도 받지 않고 스트리밍되는 `Stream`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="816fe-124">Finally, `GetReversedStream` takes no inputs and returns a `Stream` (streamed).</span></span>  
  
## <a name="enabling-streamed-transfers"></a><span data-ttu-id="816fe-125">스트리밍 전송 사용</span><span class="sxs-lookup"><span data-stu-id="816fe-125">Enabling Streamed Transfers</span></span>  
 <span data-ttu-id="816fe-126">앞서 설명한 대로 작업 계약을 정의하면 프로그래밍 모델 수준에서 스트리밍을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="816fe-126">Defining operation contracts as previously described provides streaming at the programming model level.</span></span> <span data-ttu-id="816fe-127">여기서 중지하면 전송에서는 계속 메시지의 내용 전체를 버퍼링합니다.</span><span class="sxs-lookup"><span data-stu-id="816fe-127">If you stop there, the transport still buffers the entire message content.</span></span> <span data-ttu-id="816fe-128">전송 스트리밍을 사용하려면 전송의 바인딩 요소에서 전송 모드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="816fe-128">To enable transport streaming, select a transfer mode on the binding element of the transport.</span></span> <span data-ttu-id="816fe-129">바인딩 요소에는 `TransferMode`, `Buffered`, `Streamed` 또는 `StreamedRequest`로 설정할 수 있는 `StreamedResponse` 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="816fe-129">The binding element has a `TransferMode` property that can be set to `Buffered`, `Streamed`, `StreamedRequest`, or `StreamedResponse`.</span></span> <span data-ttu-id="816fe-130">전송 모드를 `Streamed`로 설정하면 양방향 스트리밍 통신이 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="816fe-130">Setting the transfer mode to `Streamed` enables streaming communication in both directions.</span></span> <span data-ttu-id="816fe-131">전송 모드를 `StreamedRequest` 또는 `StreamedResponse`로 설정하면 각각 요청 또는 응답에서만 스트리밍 통신을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="816fe-131">Setting the transfer mode to `StreamedRequest` or `StreamedResponse` enables streaming communication in only the request or response, respectively.</span></span>  
  
 <span data-ttu-id="816fe-132">`basicHttpBinding`은 `TransferMode` 및 `NetTcpBinding`과 같이 바인딩의 `NetNamedPipeBinding` 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="816fe-132">The `basicHttpBinding` exposes the `TransferMode` property on the binding as does `NetTcpBinding` and `NetNamedPipeBinding`.</span></span> <span data-ttu-id="816fe-133">다른 전송의 경우 전송 모드를 설정하려면 사용자 지정 바인딩을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="816fe-133">For other transports, you must create a custom binding to set the transfer mode.</span></span>  
  
 <span data-ttu-id="816fe-134">샘플 중 다음 구성 코드에서는 `TransferMode` 및 사용자 지정 HTTP 바인딩에서 `basicHttpBinding` 속성을 스트리밍으로 설정하는 것을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="816fe-134">The following configuration code from the sample shows setting the `TransferMode` property to streaming on the `basicHttpBinding` and a custom HTTP binding:</span></span>  
  
```xml  
<!-- An example basicHttpBinding using streaming. -->  
<basicHttpBinding>  
  <binding name="HttpStreaming" maxReceivedMessageSize="67108864"  
           transferMode="Streamed"/>  
</basicHttpBinding>  
<!-- An example customBinding using HTTP and streaming.-->  
<customBinding>  
  <binding name="Soap12">  
    <textMessageEncoding messageVersion="Soap12WSAddressing10" />  
    <httpTransport transferMode="Streamed"  
                   maxReceivedMessageSize="67108864"/>  
  </binding>  
</customBinding>  
```  
  
 <span data-ttu-id="816fe-135">앞의 구성 코드는 `transferMode`를 `Streamed`로 설정할 뿐 아니라 `maxReceivedMessageSize`를 64MB로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="816fe-135">In addition to setting the `transferMode` to `Streamed`, the previous configuration code sets the `maxReceivedMessageSize` to 64MB.</span></span> <span data-ttu-id="816fe-136">보호 장치 차원에서 `maxReceivedMessageSize`는 받을 수 있는 최대 메시지 크기를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="816fe-136">As a defense mechanism, `maxReceivedMessageSize` places a cap on the maximum allowable size of messages on receive.</span></span> <span data-ttu-id="816fe-137">기본 `maxReceivedMessageSize`는 64KB이며, 이는 스트리밍 시나리오에서는 일반적으로 너무 낮은 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="816fe-137">The default `maxReceivedMessageSize` is 64 KB, which is usually too low for streaming scenarios.</span></span>  
  
## <a name="processing-data-as-it-is-streamed"></a><span data-ttu-id="816fe-138">스트리밍 과정에서 데이터 처리</span><span class="sxs-lookup"><span data-stu-id="816fe-138">Processing Data As It Is Streamed</span></span>  
 <span data-ttu-id="816fe-139">`GetStream`, `UploadStream` 및 `EchoStream` 작업 모두 파일로부터 바로 데이터를 보내거나 받은 데이터를 파일에 바로 저장하는 일을 담당합니다.</span><span class="sxs-lookup"><span data-stu-id="816fe-139">The operations `GetStream`, `UploadStream` and `EchoStream` all deal with sending data directly from a file or saving received data directly to a file.</span></span> <span data-ttu-id="816fe-140">그러나 많은 양의 데이터를 보내거나 받을 필요가 있어 보내거나 받는 과정에 데이터의 청크를 대상으로 처리 작업을 수행하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="816fe-140">However in some cases, there is a requirement to send or receive large amounts of data and perform some processing on chunks of the data as it is being sent or received.</span></span> <span data-ttu-id="816fe-141">그러나 시나리오를 해결하는 방법 중 하나는 읽거나 기록하는 과정에서 데이터를 처리하는 사용자 지정 스트림(<xref:System.IO.Stream>에서 파생되는 클래스)을 작성하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="816fe-141">One way to address such scenarios is to write a custom stream (a class that derives from <xref:System.IO.Stream>) that processes data as it is read or written.</span></span> <span data-ttu-id="816fe-142">`GetReversedStream` 작업 및 `ReverseStream` 클래스가 해당됩니다.</span><span class="sxs-lookup"><span data-stu-id="816fe-142">The `GetReversedStream` operation and `ReverseStream` class are an example of this.</span></span>  
  
 <span data-ttu-id="816fe-143">`GetReversedStream`은 `ReverseStream`의 새 인스턴스를 만들어 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="816fe-143">`GetReversedStream` creates and returns a new instance of `ReverseStream`.</span></span> <span data-ttu-id="816fe-144">시스템이 해당 `ReverseStream` 개체로부터 읽을 때 실제 처리가 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="816fe-144">The actual processing happens as the system reads from that `ReverseStream` object.</span></span> <span data-ttu-id="816fe-145">`ReverseStream.Read` 구현은 기본 파일로부터 바이트 청크를 읽고 이를 반대로 바꾼 다음 그 바이트를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="816fe-145">The `ReverseStream.Read` implementation reads a chunk of bytes from the underlying file, reverses them, then returns the reversed bytes.</span></span> <span data-ttu-id="816fe-146">여기서 파일의 내용 전체를 반대로 바꾸지는 않습니다. 한 번에 하나의 바이트 청크를 반대로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="816fe-146">This does not reverse the entire file content; it reverses one chunk of bytes at a time.</span></span> <span data-ttu-id="816fe-147">이는 스트림에서 콘텐츠를 읽거나 기록하는 중에 스트림 처리를 수행하는 방법을 보여 주는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="816fe-147">This is an example to show how you can perform stream processing as the content is being read or written from and to the stream.</span></span>  
  
```  
class ReverseStream : Stream  
{  
  
    FileStream inStream;  
    internal ReverseStream(string filePath)  
    {  
        //Opens the file and places a StreamReader around it.  
        inStream = File.OpenRead(filePath);  
    }  
  
    // Other methods removed for brevity.  
  
    public override int Read(byte[] buffer, int offset, int count)  
    {  
        int countRead=inStream.Read(buffer, offset,count);  
        ReverseBuffer(buffer, offset, countRead);  
        return countRead;  
    }  
  
    public override void Close()  
    {  
        inStream.Close();  
        base.Close();  
    }  
    protected override void Dispose(bool disposing)  
    {  
        inStream.Dispose();  
        base.Dispose(disposing);  
    }  
    void ReverseBuffer(byte[] buffer, int offset, int count)  
    {  
        int i, j;  
        for (i = offset, j = offset + count - 1; i < j; i++, j--)  
        {  
            byte currenti = buffer[i];  
            buffer[i] = buffer[j];  
            buffer[j] = currenti;  
        }  
  
    }  
}  
```  
  
## <a name="running-the-sample"></a><span data-ttu-id="816fe-148">샘플 실행</span><span class="sxs-lookup"><span data-stu-id="816fe-148">Running the Sample</span></span>  
 <span data-ttu-id="816fe-149">샘플을 실행하려면 먼저 이 문서 끝부분의 지침대로 서비스와 클라이언트를 모두 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="816fe-149">To run the sample, first build both the service and the client by following the directions at the end of this document.</span></span> <span data-ttu-id="816fe-150">그런 다음 각기 다른 콘솔 창에서 서비스와 클라이언트를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="816fe-150">Then start the service and the client in two different console windows.</span></span> <span data-ttu-id="816fe-151">클라이언트가 시작하면 서비스가 준비되어 사용자가 Enter 키를 누를 때까지 대기합니다.</span><span class="sxs-lookup"><span data-stu-id="816fe-151">When the client starts, it waits for you to press ENTER when the service is ready.</span></span> <span data-ttu-id="816fe-152">그런 다음 클라이언트는 `GetStream()`, `UploadStream()` 및 `GetReversedStream()` 메서드를 처음에는 HTTP를 통해 그리고 나서 TCP를 통해 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="816fe-152">The client then calls the methods `GetStream()`, `UploadStream()` and `GetReversedStream()` first over HTTP and then over TCP.</span></span> <span data-ttu-id="816fe-153">서비스 출력의 예제와 클라이언트 출력의 예제를 차례로 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="816fe-153">Here is an example output from the service followed by example output from the client:</span></span>  
  
 <span data-ttu-id="816fe-154">서비스 출력:</span><span class="sxs-lookup"><span data-stu-id="816fe-154">Service Output:</span></span>  
  
```  
The streaming service is ready.  
Press <ENTER> to terminate service.  
  
Saving to file D:\...\uploadedfile  
......................  
File D:\...\uploadedfile saved  
Saving to file D:\...\uploadedfile  
...............  
File D:\...\uploadedfile saved  
```  
  
 <span data-ttu-id="816fe-155">클라이언트 출력:</span><span class="sxs-lookup"><span data-stu-id="816fe-155">Client Output:</span></span>  
  
```  
Press <ENTER> when service is ready  
------ Using HTTP ------   
Calling GetStream()  
Saving to file D:\...\clientfile  
......................  
Wrote 33405 bytes to stream  
  
File D:\...\clientfile saved  
Calling UploadStream()  
Calling GetReversedStream()  
Saving to file D:\...\clientfile  
......................  
Wrote 33405 bytes to stream  
  
File D:\...\clientfile saved  
------ Using Custom HTTP ------  
Calling GetStream()  
Saving to file D:\...\clientfile  
...............  
Wrote 33405 bytes to stream  
  
File D:\...\clientfile saved  
Calling UploadStream()  
Calling GetReversedStream()  
Saving to file D:\...\clientfile  
...............  
Wrote 33405 bytes to stream  
  
File D:\...\clientfile saved  
  
Press <ENTER> to terminate client.  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="816fe-156">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="816fe-156">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="816fe-157">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="816fe-157">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="816fe-158">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="816fe-158">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="816fe-159">지침에 따라 단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="816fe-159">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="816fe-160">Svcutil.exe를 사용하여 이 샘플에 대한 구성을 다시 생성할 경우 클라이언트 구성에서 끝점 이름을 클라이언트 코드와 일치하도록 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="816fe-160">If you use Svcutil.exe to regenerate the configuration for this sample, be sure to modify the endpoint name in the client configuration to match the client code.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="816fe-161">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="816fe-161">The samples may already be installed on your machine.</span></span> <span data-ttu-id="816fe-162">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="816fe-162">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="816fe-163">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="816fe-163">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="816fe-164">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="816fe-164">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Service\Stream`  
  
## <a name="see-also"></a><span data-ttu-id="816fe-165">참고 항목</span><span class="sxs-lookup"><span data-stu-id="816fe-165">See Also</span></span>
