---
title: "청크 채널"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e4d53379-b37c-4b19-8726-9cc914d5d39f
caps.latest.revision: "14"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 414f350b7fe70cae196ad056f96a158da8128dd4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="chunking-channel"></a><span data-ttu-id="16644-102">청크 채널</span><span class="sxs-lookup"><span data-stu-id="16644-102">Chunking Channel</span></span>
<span data-ttu-id="16644-103">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]를 사용하여 큰 메시지를 보낼 경우 일반적으로 이러한 메시지를 버퍼링하는 데 사용되는 메모리 양을 제한하는 것이 바람직합니다.</span><span class="sxs-lookup"><span data-stu-id="16644-103">When sending large messages using [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], it is often desirable to limit the amount of memory used to buffer those messages.</span></span> <span data-ttu-id="16644-104">가능한 한 가지 솔루션은 본문에 대량의 데이터가 있다고 가정하고 메시지 본문을 스트리밍하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="16644-104">One possible solution is to stream the message body (assuming the bulk of the data is in the body).</span></span> <span data-ttu-id="16644-105">그러나 일부 프로토콜에서는 전체 메시지를 버퍼링해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="16644-105">However some protocols require buffering of the entire message.</span></span> <span data-ttu-id="16644-106">이와 같은 두 가지 예로 신뢰할 수 있는 메시징과 보안을 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16644-106">Reliable messaging and security are two such examples.</span></span> <span data-ttu-id="16644-107">가능한 또 다른 솔루션은 큰 메시지를 청크라는 더 작은 메시지로 나누고 이러한 청크를 한 번에 하나씩 보낸 다음 받는 쪽에서 큰 메시지를 다시 구성하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="16644-107">Another possible solution is to divide up the large message into smaller messages called chunks, send those chunks one chunk at a time, and reconstitute the large message on the receiving side.</span></span> <span data-ttu-id="16644-108">응용 프로그램은 이 청크 및 청크 취소를 직접 수행하거나 사용자 지정 채널을 사용하여 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16644-108">The application itself could do this chunking and de-chunking or it could use a custom channel to do it.</span></span> <span data-ttu-id="16644-109">이 Chunking Channel 샘플에서는 사용자 지정 프로토콜이나 계층화된 채널을 사용하여 임의 크기의 메시지를 청크 및 청크 취소하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="16644-109">The chunking channel sample shows how a custom protocol or layered channel can be used to do chunking and de-chunking of arbitrarily large messages.</span></span>  
  
 <span data-ttu-id="16644-110">청크는 항상 보낼 전체 메시지를 생성한 후에만 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="16644-110">Chunking should always be employed only after the entire message to be sent has been constructed.</span></span> <span data-ttu-id="16644-111">청크 채널은 항상 보안 채널 및 신뢰할 수 있는 세션 채널 아래에 계층화되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="16644-111">A chunking channel should always be layered below a security channel and a reliable session channel.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="16644-112">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16644-112">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="16644-113">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16644-113">The samples may already be installed on your machine.</span></span> <span data-ttu-id="16644-114">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="16644-114">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="16644-115">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="16644-115">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="16644-116">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16644-116">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\ChunkingChannel`  
  
## <a name="chunking-channel-assumptions-and-limitations"></a><span data-ttu-id="16644-117">청크 채널 가정 및 제한 사항</span><span class="sxs-lookup"><span data-stu-id="16644-117">Chunking Channel Assumptions and Limitations</span></span>  
  
### <a name="message-structure"></a><span data-ttu-id="16644-118">메시지 구조</span><span class="sxs-lookup"><span data-stu-id="16644-118">Message Structure</span></span>  
 <span data-ttu-id="16644-119">청크 채널에서는 청크할 메시지에 대해 다음 메시지 구조를 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="16644-119">The chunking channel assumes the following message structure for messages to be chunked:</span></span>  
  
```xml  
<soap:Envelope ...>  
  <!-- headers -->  
  <soap:Body>  
    <operationElement>  
      <paramElement>data to be chunked</paramElement>  
    </operationElement>  
  </soap:Body>  
</soap:Envelope>  
```  
  
 <span data-ttu-id="16644-120">ServiceModel을 사용하는 경우 입력 매개 변수가 하나인 계약 작업은 입력 메시지에 이 메시지 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="16644-120">When using the ServiceModel, contract operations that have 1 input parameter comply with this shape of message for their input message.</span></span> <span data-ttu-id="16644-121">마찬가지로 출력 매개 변수나 반환 값이 하나인 계약 작업은 출력 메시지에 이 메시지 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="16644-121">Similarly, contract operations that have 1 output parameter or return value comply with this shape of message for their output message.</span></span> <span data-ttu-id="16644-122">다음은 이러한 작업의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="16644-122">The following are examples of such operations:</span></span>  
  
```  
[ServiceContract]  
interface ITestService  
{  
    [OperationContract]  
    Stream EchoStream(Stream stream);  
  
    [OperationContract]  
    Stream DownloadStream();  
  
    [OperationContract(IsOneWay = true)]  
    void UploadStream(Stream stream);  
}  
```  
  
### <a name="sessions"></a><span data-ttu-id="16644-123">세션</span><span class="sxs-lookup"><span data-stu-id="16644-123">Sessions</span></span>  
 <span data-ttu-id="16644-124">청크 채널에서는 메시지(청크)가 배달 순서를 유지하면서 한 번에 배달되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="16644-124">The chunking channel requires messages to be delivered exactly once, in ordered delivery of messages (chunks).</span></span> <span data-ttu-id="16644-125">이는 기본 채널 스택이 세션 채널 스택이어야 한다는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="16644-125">This means the underlying channel stack must be sessionful.</span></span> <span data-ttu-id="16644-126">세션은 전송(예: TCP 전송)에 의해 제공되거나 세션 프로토콜 채널(예: ReliableSession 채널)에 의해 제공될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16644-126">Sessions can be provided by the transport (for example, TCP transport) or by a sessionful protocol channel (for example, ReliableSession channel).</span></span>  
  
### <a name="asynchronous-send-and-receive"></a><span data-ttu-id="16644-127">비동기 발신 및 수신</span><span class="sxs-lookup"><span data-stu-id="16644-127">Asynchronous Send and Receive</span></span>  
 <span data-ttu-id="16644-128">비동기 발신 및 수신 메서드는 이 버전의 Chunking Channel 샘플에서 구현되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="16644-128">Asynchronous send and receive methods are not implemented in this version of the chunking channel sample.</span></span>  
  
## <a name="chunking-protocol"></a><span data-ttu-id="16644-129">청크 프로토콜</span><span class="sxs-lookup"><span data-stu-id="16644-129">Chunking Protocol</span></span>  
 <span data-ttu-id="16644-130">청크 채널은 연속된 청크의 시작 및 끝과 각 청크의 시퀀스 번호를 나타내는 프로토콜을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="16644-130">The chunking channel defines a protocol that indicates the start and end of a series of chunks as well as the sequence number of each chunk.</span></span> <span data-ttu-id="16644-131">다음 세 개의 예제 메시지는 시작, 청크 및 끝 메시지를 보여 주며 각각의 주요 특성을 설명하는 주석을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="16644-131">The following three example messages demonstrate the start, chunk and end messages with comments that describe the key aspects of each.</span></span>  
  
### <a name="start-message"></a><span data-ttu-id="16644-132">시작 메시지</span><span class="sxs-lookup"><span data-stu-id="16644-132">Start Message</span></span>  
  
```xml  
<s:Envelope xmlns:a="http://www.w3.org/2005/08/addressing"   
            xmlns:s="http://www.w3.org/2003/05/soap-envelope">  
  <s:Header>  
<!—Original message action is replaced with a chunking-specific action. -->  
    <a:Action s:mustUnderstand="1">http://samples.microsoft.com/chunkingAction</a:Action>  
<!--  
Original message is assigned a unique id that is transmitted   
in a MessageId header. Note that this is different from the WS-Addressing MessageId header.  
-->  
    <MessageId s:mustUnderstand="1" xmlns="http://samples.microsoft.com/chunking">  
53f183ee-04aa-44a0-b8d3-e45224563109  
</MessageId>  
<!--  
ChunkingStart header signals the start of a chunked message.  
-->  
    <ChunkingStart s:mustUnderstand="1" i:nil="true" xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://samples.microsoft.com/chunking" />  
<!--  
Original message action is transmitted in OriginalAction.  
This is required to re-create the original message on the other side.  
-->  
    <OriginalAction xmlns="http://samples.microsoft.com/chunking">  
http://tempuri.org/ITestService/EchoStream  
    </OriginalAction>  
   <!--  
    All original message headers are included here.  
   -->  
  </s:Header>  
  <s:Body>  
<!--  
Chunking assumes this structure of Body content:  
<element>  
  <childelement>large data to be chunked<childelement>  
</element>  
The start message contains just <element> and <childelement> without  
the data to be chunked.  
-->  
    <EchoStream xmlns="http://tempuri.org/">  
      <stream />  
    </EchoStream>  
  </s:Body>  
</s:Envelope>  
```  
  
### <a name="chunk-message"></a><span data-ttu-id="16644-133">청크 메시지</span><span class="sxs-lookup"><span data-stu-id="16644-133">Chunk Message</span></span>  
  
```xml  
<s:Envelope   
  xmlns:a="http://www.w3.org/2005/08/addressing"   
  xmlns:s="http://www.w3.org/2003/05/soap-envelope">  
  <s:Header>  
   <!--  
    All chunking protocol messages have this action.  
   -->  
    <a:Action s:mustUnderstand="1">  
      http://samples.microsoft.com/chunkingAction  
    </a:Action>  
<!--  
Same as MessageId in the start message. The GUID indicates which original message this chunk belongs to.  
-->  
    <MessageId s:mustUnderstand="1"   
               xmlns="http://samples.microsoft.com/chunking">  
      53f183ee-04aa-44a0-b8d3-e45224563109  
    </MessageId>  
<!--  
The sequence number of the chunk.  
This number restarts at 1 with each new sequence of chunks.  
-->  
    <ChunkNumber s:mustUnderstand="1"   
                 xmlns="http://samples.microsoft.com/chunking">  
      1096  
    </ChunkNumber>  
  </s:Header>  
  <s:Body>  
<!--  
The chunked data is wrapped in a chunk element.  
The encoding of this data (and the entire message)   
depends on the encoder used. The chunking channel does not mandate an encoding.  
-->  
    <chunk xmlns="http://samples.microsoft.com/chunking">  
kfSr2QcBlkHTvQ==  
    </chunk>  
  </s:Body>  
</s:Envelope>  
```  
  
### <a name="end-message"></a><span data-ttu-id="16644-134">끝 메시지</span><span class="sxs-lookup"><span data-stu-id="16644-134">End Message</span></span>  
  
```xml  
<s:Envelope xmlns:a="http://www.w3.org/2005/08/addressing"   
            xmlns:s="http://www.w3.org/2003/05/soap-envelope">  
  <s:Header>  
    <a:Action s:mustUnderstand="1">  
      http://samples.microsoft.com/chunkingAction  
    </a:Action>  
<!--  
Same as MessageId in the start message. The GUID indicates which original message this chunk belongs to.  
-->  
    <MessageId s:mustUnderstand="1"   
               xmlns="http://samples.microsoft.com/chunking">  
      53f183ee-04aa-44a0-b8d3-e45224563109  
    </MessageId>  
<!--  
ChunkingEnd header signals the end of a chunk sequence.  
-->  
    <ChunkingEnd s:mustUnderstand="1" i:nil="true"   
                 xmlns:i="http://www.w3.org/2001/XMLSchema-instance"   
                 xmlns="http://samples.microsoft.com/chunking" />  
<!--  
ChunkingEnd messages have a sequence number.  
-->  
    <ChunkNumber s:mustUnderstand="1"   
                 xmlns="http://samples.microsoft.com/chunking">  
      79  
    </ChunkNumber>  
  </s:Header>  
  <s:Body>  
<!--  
The ChunkingEnd message has the same <element><childelement> structure  
as the ChunkingStart message.  
-->  
    <EchoStream xmlns="http://tempuri.org/">  
      <stream />  
    </EchoStream>  
  </s:Body>  
</s:Envelope>  
```  
  
## <a name="chunking-channel-architecture"></a><span data-ttu-id="16644-135">청크 채널 아키텍처</span><span class="sxs-lookup"><span data-stu-id="16644-135">Chunking Channel Architecture</span></span>  
 <span data-ttu-id="16644-136">청크 채널은 상위 수준에서 일반적인 채널 아키텍처를 따르는 `IDuplexSessionChannel`입니다.</span><span class="sxs-lookup"><span data-stu-id="16644-136">The chunking channel is an `IDuplexSessionChannel` that, at a high level, follows the typical channel architecture.</span></span> <span data-ttu-id="16644-137">`ChunkingBindingElement` 및 `ChunkingChannelFactory`를 빌드할 수 있는 `ChunkingChannelListener`가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16644-137">There is a `ChunkingBindingElement` that can build a `ChunkingChannelFactory` and a `ChunkingChannelListener`.</span></span> <span data-ttu-id="16644-138">`ChunkingChannelFactory`는 요청을 받은 경우 `ChunkingChannel`의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="16644-138">The `ChunkingChannelFactory` creates instances of `ChunkingChannel` when it is asked to.</span></span> <span data-ttu-id="16644-139">`ChunkingChannelListener`는 새 내부 채널이 수락된 경우 `ChunkingChannel`의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="16644-139">The `ChunkingChannelListener` creates instances of `ChunkingChannel` when a new inner channel is accepted.</span></span> <span data-ttu-id="16644-140">`ChunkingChannel` 자체는 메시지를 보내고 받는 작업을 담당합니다.</span><span class="sxs-lookup"><span data-stu-id="16644-140">The `ChunkingChannel` itself is responsible for sending and receiving messages.</span></span>  
  
 <span data-ttu-id="16644-141">다음 하위 수준에서 `ChunkingChannel`은 서버 구성 요소에 의존하여 청크 프로토콜을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="16644-141">At the next level down, `ChunkingChannel` relies on several components to implement the chunking protocol.</span></span> <span data-ttu-id="16644-142">보내는 쪽에서 채널은 실제 청크를 수행하는 `XmlDictionaryWriter`라는 사용자 지정 `ChunkingWriter`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="16644-142">On the send side, the channel uses a custom `XmlDictionaryWriter` called `ChunkingWriter` that does the actual chunking.</span></span> <span data-ttu-id="16644-143">`ChunkingWriter`는 내부 채널을 직접 사용하여 청크를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="16644-143">`ChunkingWriter` uses the inner channel directly to send chunks.</span></span> <span data-ttu-id="16644-144">사용자 지정 `XmlDictionaryWriter`를 사용하면 원본 메시지의 큰 본문이 기록될 때 청크를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16644-144">Using a custom `XmlDictionaryWriter` allows us to send out chunks as the large body of the original message is being written.</span></span> <span data-ttu-id="16644-145">이는 전체 원본 메시지를 버퍼링하지 않는다는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="16644-145">This means we do not buffer the entire original message.</span></span>  
  
 <span data-ttu-id="16644-146">![청크 채널](../../../../docs/framework/wcf/samples/media/chunkingchannel1.gif "ChunkingChannel1")</span><span class="sxs-lookup"><span data-stu-id="16644-146">![Chunking Channel](../../../../docs/framework/wcf/samples/media/chunkingchannel1.gif "ChunkingChannel1")</span></span>  
  
 <span data-ttu-id="16644-147">받는 쪽 `ChunkingChannel`은 내부 채널의 메시지를 끌어와 `XmlDictionaryReader`라는 사용자 지정 `ChunkingReader`에 전달하여 들어오는 청크로부터 원본 메시지를 다시 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="16644-147">On the receive side, `ChunkingChannel` pulls messages from the inner channel and hands them to a custom `XmlDictionaryReader` called `ChunkingReader`, which reconstitutes the original message from the incoming chunks.</span></span> <span data-ttu-id="16644-148">`ChunkingChannel`은 `ChunkingReader`라는 사용자 지정 `Message` 구현에서 이 `ChunkingMessage`를 래핑하고 이 메시지를 위 계층에 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="16644-148">`ChunkingChannel` wraps this `ChunkingReader` in a custom `Message` implementation called `ChunkingMessage` and returns this message to the layer above.</span></span> <span data-ttu-id="16644-149">이렇게 `ChunkingReader`와 `ChunkingMessage`를 함께 사용하면 전체 원본 메시지 본문을 버퍼링하는 대신 위 계층에서 읽을 때 원본 메시지 본문의 청크를 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16644-149">This combination of `ChunkingReader` and `ChunkingMessage` allows us to de-chunk the original message body as it is being read by the layer above instead of having to buffer the entire original message body.</span></span> <span data-ttu-id="16644-150">`ChunkingReader`에는 구성 가능한 최대 버퍼링된 청크 수까지 들어오는 청크를 버퍼링하는 큐가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16644-150">`ChunkingReader` has a queue where it buffers incoming chunks up to a maximum configurable number of buffered chunks.</span></span> <span data-ttu-id="16644-151">이 최대 한도에 도달하면 판독기는 위 계층에서 원본 메시지 본문을 읽어서 큐의 메시지가 비워지기를 기다리거나 최대 수신 시간 제한에 도달할 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="16644-151">When this maximum limit is reached, the reader waits for messages to be drained from the queue by the layer above (that is, by just reading from the original message body) or until the maximum receive timeout is reached.</span></span>  
  
 <span data-ttu-id="16644-152">![청크 채널](../../../../docs/framework/wcf/samples/media/chunkingchannel2.gif "ChunkingChannel2")</span><span class="sxs-lookup"><span data-stu-id="16644-152">![Chunking Channel](../../../../docs/framework/wcf/samples/media/chunkingchannel2.gif "ChunkingChannel2")</span></span>  
  
## <a name="chunking-programming-model"></a><span data-ttu-id="16644-153">청크 프로그래밍 모델</span><span class="sxs-lookup"><span data-stu-id="16644-153">Chunking Programming Model</span></span>  
 <span data-ttu-id="16644-154">서비스 개발자는 `ChunkingBehavior` 특성을 계약 내의 작업에 적용하여 청크할 메시지를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16644-154">Service developers can specify which messages are to be chunked by applying the `ChunkingBehavior` attribute to operations within the contract.</span></span> <span data-ttu-id="16644-155">이 특성은 청크를 입력 메시지, 출력 메시지 또는 둘 다에 적용할지 여부를 개발자가 지정할 수 있게 하는 `AppliesTo` 속성을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="16644-155">The attribute exposes an `AppliesTo` property that allows the developer to specify whether chunking applies to the input message, the output message or both.</span></span> <span data-ttu-id="16644-156">다음 예제에서는 `ChunkingBehavior` 특성의 사용법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="16644-156">The following example shows the usage of `ChunkingBehavior` attribute:</span></span>  
  
```  
[ServiceContract]  
interface ITestService  
{  
    [OperationContract]  
    [ChunkingBehavior(ChunkingAppliesTo.Both)]  
    Stream EchoStream(Stream stream);  
  
    [OperationContract]  
    [ChunkingBehavior(ChunkingAppliesTo.OutMessage)]  
    Stream DownloadStream();  
  
    [OperationContract(IsOneWay=true)]  
    [ChunkingBehavior(ChunkingAppliesTo.InMessage)]  
    void UploadStream(Stream stream);  
  
}  
```  
  
 <span data-ttu-id="16644-157">이 프로그래밍 모델에서 `ChunkingBindingElement`는 청크할 메시지를 식별하는 동작 URI 목록을 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="16644-157">From this programming model, the `ChunkingBindingElement` compiles a list of action URIs that identify messages to be chunked.</span></span> <span data-ttu-id="16644-158">보내는 각 메시지의 동작을 이 목록과 비교하여 메시지를 청크해야 할지 직접 보내야 할지를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="16644-158">The action of each outgoing message is compared against this list to determine if the message should be chunked or sent directly.</span></span>  
  
## <a name="implementing-the-send-operation"></a><span data-ttu-id="16644-159">Send 작업 구현</span><span class="sxs-lookup"><span data-stu-id="16644-159">Implementing the Send Operation</span></span>  
 <span data-ttu-id="16644-160">상위 수준에서 Send 작업은 보내는 메시지를 청크해야 하는지 먼저 확인하고 그럴 필요가 없는 경우 내부 채널을 사용하여 메시지를 직접 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="16644-160">At a high level, the Send operation first checks whether the outgoing message must be chunked and, if not, sends the message directly using the inner channel.</span></span>  
  
 <span data-ttu-id="16644-161">메시지를 청크해야 할 경우 Send는 새 `ChunkingWriter`를 만들고 보내는 메시지에서 `WriteBodyContents`를 호출하여 이 `ChunkingWriter`를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="16644-161">If the message must be chunked, Send creates a new `ChunkingWriter` and calls `WriteBodyContents` on the outgoing message passing it this `ChunkingWriter`.</span></span> <span data-ttu-id="16644-162">그런 다음 `ChunkingWriter`는 메시지 청크(원본 메시지 헤더를 시작 청크 메시지에 복사하는 작업 포함)를 수행하고 내부 채널을 사용하여 청크를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="16644-162">The `ChunkingWriter` then does the message chunking (including copying original message headers to the start chunk message) and sends chunks using the inner channel.</span></span>  
  
 <span data-ttu-id="16644-163">주목할 만한 몇 가지 세부 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="16644-163">A few details worth noting:</span></span>  
  
-   <span data-ttu-id="16644-164">Send는 `ThrowIfDisposedOrNotOpened`가 Opened인지 확인하기 위해 먼저 `CommunicationState`를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="16644-164">Send first calls `ThrowIfDisposedOrNotOpened` to ensure the `CommunicationState` is opened.</span></span>  
  
-   <span data-ttu-id="16644-165">보내기는 동기화되므로 각 세션에 대해 한 번에 하나의 메시지만 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16644-165">Sending is synchronized so that only one message can be sent at a time for each session.</span></span> <span data-ttu-id="16644-166">청크된 메시지를 보낼 때 다시 설정되는 `ManualResetEvent`이라는 `sendingDone`가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16644-166">There is a `ManualResetEvent` named `sendingDone` that is reset when a chunked message is being sent.</span></span> <span data-ttu-id="16644-167">끝 청크 메시지가 보내지고 나면 이 이벤트가 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="16644-167">Once the end chunk message is sent, this event is set.</span></span> <span data-ttu-id="16644-168">Send 메서드는 보내는 메시지를 보내려고 시도하기 전에 이 이벤트가 설정되기를 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="16644-168">The Send method waits for this event to be set before it tries to send the outgoing message.</span></span>  
  
-   <span data-ttu-id="16644-169">Send는 보내는 도중 동기화된 상태 변경을 방지하기 위해 `CommunicationObject.ThisLock`을 잠급니다.</span><span class="sxs-lookup"><span data-stu-id="16644-169">Send locks the `CommunicationObject.ThisLock` to prevent synchronized state changes while sending.</span></span> <span data-ttu-id="16644-170"><xref:System.ServiceModel.Channels.CommunicationObject> 상태 및 상태 시스템에 대한 자세한 내용은 <xref:System.ServiceModel.Channels.CommunicationObject> 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="16644-170">See the <xref:System.ServiceModel.Channels.CommunicationObject> documentation for more information about <xref:System.ServiceModel.Channels.CommunicationObject> states and state machine.</span></span>  
  
-   <span data-ttu-id="16644-171">Send에 전달되는 시간 제한은 모든 청크의 보내기를 포함하는 전체 Send 작업의 시간 제한으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="16644-171">The timeout passed to Send is used as the timeout for the entire send operation which includes sending all of the chunks.</span></span>  
  
-   <span data-ttu-id="16644-172">전체 원본 메시지 본문의 버퍼링을 방지하기 위해 사용자 지정 `XmlDictionaryWriter` 디자인이 선택되었습니다.</span><span class="sxs-lookup"><span data-stu-id="16644-172">The custom `XmlDictionaryWriter` design was chosen to avoid buffering the entire original message body.</span></span> <span data-ttu-id="16644-173">`XmlDictionaryReader`를 사용하여 본문에서 `message.GetReaderAtBodyContents`를 가져올 경우에는 전체 본문이 버퍼링됩니다.</span><span class="sxs-lookup"><span data-stu-id="16644-173">If we were to get an `XmlDictionaryReader` on the body using `message.GetReaderAtBodyContents` the entire body would be buffered.</span></span> <span data-ttu-id="16644-174">이렇게 하는 대신에 사용자 지정 `XmlDictionaryWriter`가 `message.WriteBodyContents`에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="16644-174">Instead, we have a custom `XmlDictionaryWriter` that is passed to `message.WriteBodyContents`.</span></span> <span data-ttu-id="16644-175">메시지가 작성기에서 WriteBase64를 호출할 경우 작성기는 청크를 메시지에 패키지하고 내부 채널을 사용하여 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="16644-175">As the message calls WriteBase64 on the writer, the writer packages up chunks into messages and sends them using the inner channel.</span></span> <span data-ttu-id="16644-176">청크가 보내질 때까지 WriteBase64는 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="16644-176">WriteBase64 blocks until the chunk is sent.</span></span>  
  
## <a name="implementing-the-receive-operation"></a><span data-ttu-id="16644-177">Receive 작업 구현</span><span class="sxs-lookup"><span data-stu-id="16644-177">Implementing the Receive Operation</span></span>  
 <span data-ttu-id="16644-178">상위 수준에서 Receive 작업은 먼저 들어오는 메시지가 `null`이 아니고 해당 동작이 `ChunkingAction`인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="16644-178">At a high level, the Receive operation first checks that the incoming message is not `null` and that its action is the `ChunkingAction`.</span></span> <span data-ttu-id="16644-179">두 조건을 충족하지 않을 경우 메시지는 Receive에서 변경되지 않은 상태로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="16644-179">If it does not meet both criteria, the message is returned unchanged from Receive.</span></span> <span data-ttu-id="16644-180">두 조건을 충족할 경우 Receive는 새 `ChunkingReader`와 `ChunkingMessage`를 호출하여 이를 래핑하는 새 `GetNewChunkingMessage` 메시지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="16644-180">Otherwise, Receive creates a new `ChunkingReader` and a new `ChunkingMessage` wrapped around it (by calling `GetNewChunkingMessage`).</span></span> <span data-ttu-id="16644-181">새 `ChunkingMessage`를 반환하기 전에 Receive는 threadpool 스레드를 사용하여 `ReceiveChunkLoop`를 실행합니다. 따라서 끝 청크 메시지가 수신되거나 수신 시간 제한에 도달할 때까지 루프에서 `innerChannel.Receive`가 호출되고 `ChunkingReader`에 청크가 보내집니다.</span><span class="sxs-lookup"><span data-stu-id="16644-181">Before returning that new `ChunkingMessage`, Receive uses a threadpool thread to execute `ReceiveChunkLoop`, which calls `innerChannel.Receive` in a loop and hands off chunks to the `ChunkingReader` until the end chunk message is received or the receive timeout is hit.</span></span>  
  
 <span data-ttu-id="16644-182">주목할 만한 몇 가지 세부 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="16644-182">A few details worth noting:</span></span>  
  
-   <span data-ttu-id="16644-183">Send와 마찬가지로 Receive는 `ThrowIfDisposedOrNotOepned`가 Opened인지 확인하기 위해 먼저 `CommunicationState`를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="16644-183">Like Send, Receive first calls `ThrowIfDisposedOrNotOepned` to ensure the `CommunicationState` is Opened.</span></span>  
  
-   <span data-ttu-id="16644-184">또한 Receive는 동기화되므로 세션에서 한 번에 하나의 메시지만 수신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16644-184">Receive is also synchronized so that only one message can be received at a time from the session.</span></span> <span data-ttu-id="16644-185">시작 청크 메시지가 수신되고 나면 끝 청크 메시지가 수신될 때까지 수신되는 이후의 모든 메시지가 청크로 간주되므로 이 기능이 특히 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="16644-185">This is especially important because once a start chunk message is received, all subsequent received messages are expected to be chunks within this new chunk sequence until an end chunk message is received.</span></span> <span data-ttu-id="16644-186">현재 청크 취소하는 중인 메시지에 속하는 모든 청크가 수신될 때까지 Receive는 내부 채널에서 메시지를 끌어올 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="16644-186">Receive cannot pull messages from the inner channel until all chunks that belong to the message currently being de-chunked are received.</span></span> <span data-ttu-id="16644-187">이를 위해 Receive는 끝 청크 메시지가 수신될 때 설정되고 새 시작 청크 메시지가 수신될 때 다시 설정되는 `ManualResetEvent`라는 `currentMessageCompleted`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="16644-187">To accomplish this, Receive uses a `ManualResetEvent` named `currentMessageCompleted`, which is set when the end chunk message is received and reset when a new start chunk message is received.</span></span>  
  
-   <span data-ttu-id="16644-188">Send와 달리 Receive에서는 동기화된 상태 전환이 수신 중에 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="16644-188">Unlike Send, Receive does not prevent synchronized state transitions while receiving.</span></span> <span data-ttu-id="16644-189">예를 들어, Close가 수신 중에 호출되어 원본 메시지의 보류 중인 수신이 완료되거나 지정된 시간 제한 값에 도달할 때까지 대기할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16644-189">For example, Close can be called while receiving and waits until the pending receive of the original message is completed or the specified timeout value is reached.</span></span>  
  
-   <span data-ttu-id="16644-190">Receive에 전달되는 시간 제한은 모든 청크의 수신을 포함하는 전체 Receive 작업의 시간 제한으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="16644-190">The timeout passed to Receive is used as the timeout for the entire receive operation, which includes receiving all of the chunks.</span></span>  
  
-   <span data-ttu-id="16644-191">메시지를 소비하는 계층이 들어오는 청크 메시지의 속도보다 느린 속도로 메시지 본문을 소비하는 중이면 `ChunkingReader`는 `ChunkingBindingElement.MaxBufferedChunks`에 지정된 한도까지 이러한 들어오는 청크를 버퍼링합니다.</span><span class="sxs-lookup"><span data-stu-id="16644-191">If the layer that consumes the message is consuming the message body at a rate lower than the rate of incoming chunk messages, the `ChunkingReader` buffers those incoming chunks up to the limit specified by `ChunkingBindingElement.MaxBufferedChunks`.</span></span> <span data-ttu-id="16644-192">해당 한도에 도달하고 나면 버퍼링된 청크가 소비되거나 수신 시간 제한에 도달할 때까지 청크를 더 이상 하위 계층에서 끌어오지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="16644-192">Once that limit is reached, no more chunks are pulled from the lower layer until either a buffered chunk is consumed or the receive timeout is reached.</span></span>  
  
## <a name="communicationobject-overrides"></a><span data-ttu-id="16644-193">CommunicationObject 재정의</span><span class="sxs-lookup"><span data-stu-id="16644-193">CommunicationObject Overrides</span></span>  
  
### <a name="onopen"></a><span data-ttu-id="16644-194">OnOpen</span><span class="sxs-lookup"><span data-stu-id="16644-194">OnOpen</span></span>  
 <span data-ttu-id="16644-195">`OnOpen`은 `innerChannel.Open`을 호출하여 내부 채널을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="16644-195">`OnOpen` calls `innerChannel.Open` to open the inner channel.</span></span>  
  
### <a name="onclose"></a><span data-ttu-id="16644-196">OnClose</span><span class="sxs-lookup"><span data-stu-id="16644-196">OnClose</span></span>  
 <span data-ttu-id="16644-197">`OnClose`는 먼저 `stopReceive`를 `true`로 설정하여 보류 중인 `ReceiveChunkLoop`를 중지할 것을 알립니다.</span><span class="sxs-lookup"><span data-stu-id="16644-197">`OnClose` first sets `stopReceive` to `true` to signal the pending `ReceiveChunkLoop` to stop.</span></span> <span data-ttu-id="16644-198">그런 다음는 `receiveStopped``ManualResetEvent`때 설정 된 `ReceiveChunkLoop` 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="16644-198">It then waits for the `receiveStopped``ManualResetEvent`, which is set when `ReceiveChunkLoop` stops.</span></span> <span data-ttu-id="16644-199">`ReceiveChunkLoop`가 지정된 시간 제한 내에 중지한다고 가정하고 `OnClose`는 남은 시간 제한을 사용하여 `innerChannel.Close`를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="16644-199">Assuming the `ReceiveChunkLoop` stops within the specified timeout, `OnClose` calls `innerChannel.Close` with the remaining timeout.</span></span>  
  
### <a name="onabort"></a><span data-ttu-id="16644-200">OnAbort</span><span class="sxs-lookup"><span data-stu-id="16644-200">OnAbort</span></span>  
 <span data-ttu-id="16644-201">`OnAbort`는 `innerChannel.Abort`를 호출하여 내부 채널을 중단합니다.</span><span class="sxs-lookup"><span data-stu-id="16644-201">`OnAbort` calls `innerChannel.Abort` to abort the inner channel.</span></span> <span data-ttu-id="16644-202">보류 중인 `ReceiveChunkLoop`가 있을 경우 보류 중인 `innerChannel.Receive` 호출에서 예외를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="16644-202">If there is a pending `ReceiveChunkLoop` it gets an exception from the pending `innerChannel.Receive` call.</span></span>  
  
### <a name="onfaulted"></a><span data-ttu-id="16644-203">OnFaulted</span><span class="sxs-lookup"><span data-stu-id="16644-203">OnFaulted</span></span>  
 <span data-ttu-id="16644-204">채널에 오류가 발생하여 `ChunkingChannel`가 재정의되지 않을 경우 `OnFaulted`에는 특수한 동작이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="16644-204">The `ChunkingChannel` does not require special behavior when the channel is faulted so `OnFaulted` is not overridden.</span></span>  
  
## <a name="implementing-channel-factory"></a><span data-ttu-id="16644-205">채널 팩터리 구현</span><span class="sxs-lookup"><span data-stu-id="16644-205">Implementing Channel Factory</span></span>  
 <span data-ttu-id="16644-206">`ChunkingChannelFactory`는 `ChunkingDuplexSessionChannel`의 인스턴스를 만들고 내부 채널 팩터리에 상태 전환을 적용하는 작업을 담당합니다.</span><span class="sxs-lookup"><span data-stu-id="16644-206">The `ChunkingChannelFactory` is responsible for creating instances of `ChunkingDuplexSessionChannel` and for cascading state transitions to the inner channel factory.</span></span>  
  
 <span data-ttu-id="16644-207">`OnCreateChannel`은 내부 채널 팩터리를 사용하여 `IDuplexSessionChannel` 내부 채널을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="16644-207">`OnCreateChannel` uses the inner channel factory to create an `IDuplexSessionChannel` inner channel.</span></span> <span data-ttu-id="16644-208">그런 다음 새 `ChunkingDuplexSessionChannel`을 만들어 청크할 메시지 동작 목록 및 수신 시에 버퍼링할 최대 청크 수와 함께 이 내부 채널을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="16644-208">It then creates a new `ChunkingDuplexSessionChannel` passing it this inner channel along with the list of message actions to be chunked and the maximum number of chunks to buffer upon receive.</span></span> <span data-ttu-id="16644-209">이 생성자의 `ChunkingChannelFactory`에 전달되는 두 개의 매개 변수는 청크할 메시지 동작 목록 및 버퍼링할 최대 청크 수입니다.</span><span class="sxs-lookup"><span data-stu-id="16644-209">The list of message actions to be chunked and the maximum number of chunks to buffer are two parameters passed to `ChunkingChannelFactory` in its constructor.</span></span> <span data-ttu-id="16644-210">`ChunkingBindingElement` 관련 단원에서 이러한 값의 출처에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="16644-210">The section on `ChunkingBindingElement` describes where these values come from.</span></span>  
  
 <span data-ttu-id="16644-211">`OnOpen`, `OnClose`, `OnAbort` 및 동등한 해당 비동기 항목은 내부 채널 팩터리에서 해당 상태 전환 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="16644-211">The `OnOpen`, `OnClose`, `OnAbort` and their asynchronous equivalents call the corresponding state transition method on the inner channel factory.</span></span>  
  
## <a name="implementing-channel-listener"></a><span data-ttu-id="16644-212">채널 수신기 구현</span><span class="sxs-lookup"><span data-stu-id="16644-212">Implementing Channel Listener</span></span>  
 <span data-ttu-id="16644-213">`ChunkingChannelListener`는 내부 채널 수신기에 대한 래퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="16644-213">The `ChunkingChannelListener` is a wrapper around an inner channel listener.</span></span> <span data-ttu-id="16644-214">해당 내부 수신기에 대한 대리자 호출 외에 이 래퍼의 기본 기능은 내부 채널 수신기에서 받은 채널 주위에 새 `ChunkingDuplexSessionChannels`를 래핑하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="16644-214">Its main function, besides delegate calls to that inner channel listener, is to wrap new `ChunkingDuplexSessionChannels` around channels accepted from the inner channel listener.</span></span> <span data-ttu-id="16644-215">이 작업은 `OnAcceptChannel` 및 `OnEndAcceptChannel`에서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="16644-215">This is done in `OnAcceptChannel` and `OnEndAcceptChannel`.</span></span> <span data-ttu-id="16644-216">새로 만든 `ChunkingDuplexSessionChannel`에는 위에 설명된 다른 매개 변수와 함께 내부 채널이 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="16644-216">The newly created `ChunkingDuplexSessionChannel` is passed the inner channel along with the other parameters previously described.</span></span>  
  
## <a name="implementing-binding-element-and-binding"></a><span data-ttu-id="16644-217">바인딩 요소 및 바인딩 구현</span><span class="sxs-lookup"><span data-stu-id="16644-217">Implementing Binding Element and Binding</span></span>  
 <span data-ttu-id="16644-218">`ChunkingBindingElement`는 `ChunkingChannelFactory` 및 `ChunkingChannelListener`를 만드는 작업을 담당합니다.</span><span class="sxs-lookup"><span data-stu-id="16644-218">`ChunkingBindingElement` is responsible for creating the `ChunkingChannelFactory` and `ChunkingChannelListener`.</span></span> <span data-ttu-id="16644-219">`ChunkingBindingElement` 확인 여부를에 T `CanBuildChannelFactory` \<T > 및 `CanBuildChannelListener` \<T > 형식의 `IDuplexSessionChannel` (청크 채널에서 지 원하는 유일한 채널) 그리고 바인딩에 있는 다른 바인딩 요소가이 지원 채널 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="16644-219">The `ChunkingBindingElement` checks whether T in `CanBuildChannelFactory`\<T> and `CanBuildChannelListener`\<T> is of type `IDuplexSessionChannel` (the only channel supported by the chunking channel) and that the other binding elements in the binding support this channel type.</span></span>  
  
 <span data-ttu-id="16644-220">`BuildChannelFactory`\<T > 먼저 확인 하는 요청한 채널 형식을 생성할 수 하 고 다음 청크 할 메시지 동작 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="16644-220">`BuildChannelFactory`\<T> first checks that the requested channel type can be built and then gets a list of message actions to be chunked.</span></span> <span data-ttu-id="16644-221">자세한 내용은 다음 단원을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="16644-221">For more information, see the following section.</span></span> <span data-ttu-id="16644-222">그런 다음 새 `ChunkingChannelFactory`를 만들어 내부 채널 팩터리(`context.BuildInnerChannelFactory<IDuplexSessionChannel>`에서 반환), 메시지 동작 목록 및 버퍼링할 최대 청크 수를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="16644-222">It then creates a new `ChunkingChannelFactory` passing it the inner channel factory (as returned from `context.BuildInnerChannelFactory<IDuplexSessionChannel>`), the list of message actions, and the maximum number of chunks to buffer.</span></span> <span data-ttu-id="16644-223">최대 청크 수는 `MaxBufferedChunks`에 의해 노출되는 `ChunkingBindingElement`라는 속성에서 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="16644-223">The maximum number of chunks comes from a property called `MaxBufferedChunks` exposed by the `ChunkingBindingElement`.</span></span>  
  
 <span data-ttu-id="16644-224">`BuildChannelListener<T>`에서도 `ChunkingChannelListener`를 만들어 내부 채널 수신기에 전달하는 구현 방법이 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="16644-224">`BuildChannelListener<T>` has a similar implementation for creating `ChunkingChannelListener` and passing it the inner channel listener.</span></span>  
  
 <span data-ttu-id="16644-225">이 샘플에는 `TcpChunkingBinding`이라는 예제 바인딩이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16644-225">There is an example binding included in this sample named `TcpChunkingBinding`.</span></span> <span data-ttu-id="16644-226">이 바인딩은 두 개의 바인딩 요소인 `TcpTransportBindingElement` 및 `ChunkingBindingElement`로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="16644-226">This binding consists of two binding elements: `TcpTransportBindingElement` and `ChunkingBindingElement`.</span></span> <span data-ttu-id="16644-227">`MaxBufferedChunks` 속성을 노출하는 것 외에도 이 바인딩은 `TcpTransportBindingElement`(헤더에 대해 `MaxReceivedMessageSize` + 100KB로 설정)와 같은 일부 `ChunkingUtils.ChunkSize` 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="16644-227">In addition to exposing the `MaxBufferedChunks` property, the binding also sets some of the `TcpTransportBindingElement` properties such as `MaxReceivedMessageSize` (sets it to `ChunkingUtils.ChunkSize` + 100KB bytes for headers).</span></span>  
  
 <span data-ttu-id="16644-228">또한 `TcpChunkingBinding`은 `IBindingRuntimePreferences`를 구현하고 동기 Receive 호출만 구현된다는 것을 나타내는 `ReceiveSynchronously` 메서드에서 true를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="16644-228">`TcpChunkingBinding` also implements `IBindingRuntimePreferences` and returns true from the `ReceiveSynchronously` method indicating that only the synchronous Receive calls are implemented.</span></span>  
  
### <a name="determining-which-messages-to-chunk"></a><span data-ttu-id="16644-229">청크할 메시지 결정</span><span class="sxs-lookup"><span data-stu-id="16644-229">Determining Which Messages To Chunk</span></span>  
 <span data-ttu-id="16644-230">청크 채널은 `ChunkingBehavior` 특성을 통해 식별된 메시지만 청크합니다.</span><span class="sxs-lookup"><span data-stu-id="16644-230">The chunking channel chunks only the messages identified through the `ChunkingBehavior` attribute.</span></span> <span data-ttu-id="16644-231">`ChunkingBehavior` 클래스는 `IOperationBehavior`를 구현하며 `AddBindingParameter` 메서드 호출에 의해 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="16644-231">The `ChunkingBehavior` class implements `IOperationBehavior` and is implemented by calling the `AddBindingParameter` method.</span></span> <span data-ttu-id="16644-232">이 메서드에서 `ChunkingBehavior`는 해당 `AppliesTo` 속성의 값(`InMessage`, `OutMessage` 또는 둘 다)을 확인하여 청크해야 하는 메시지를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="16644-232">In this method, the `ChunkingBehavior` examines the value of its `AppliesTo` property (`InMessage`, `OutMessage` or both) to determine which messages should be chunked.</span></span> <span data-ttu-id="16644-233">그런 다음 `OperationDescription`의 메시지 컬렉션에서 이러한 각 메시지의 동작을 가져와 `ChunkingBindingParameter`의 인스턴스 내에 포함된 문자열 컬렉션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="16644-233">It then gets the action of each of those messages (from the Messages collection on `OperationDescription`) and adds it to a string collection contained within an instance of `ChunkingBindingParameter`.</span></span> <span data-ttu-id="16644-234">그런 다음 이 `ChunkingBindingParameter`를 제공된 `BindingParameterCollection`에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="16644-234">It then adds this `ChunkingBindingParameter` to the provided `BindingParameterCollection`.</span></span>  
  
 <span data-ttu-id="16644-235">바인딩의 각 바인딩 요소가 채널 팩터리나 채널 수신기를 빌드할 때 `BindingParameterCollection` 내에서 이 `BindingContext`이 해당 바인딩 요소에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="16644-235">This `BindingParameterCollection` is passed inside the `BindingContext` to each binding element in the binding when that binding element builds the channel factory or the channel listener.</span></span> <span data-ttu-id="16644-236">`ChunkingBindingElement`의 구현의 `BuildChannelFactory<T>` 및 `BuildChannelListener<T>` 약화 `ChunkingBindingParameter` 부재 중는 `BindingContext’`s `BindingParameterCollection`합니다.</span><span class="sxs-lookup"><span data-stu-id="16644-236">The `ChunkingBindingElement`'s implementation of `BuildChannelFactory<T>` and `BuildChannelListener<T>` pull this `ChunkingBindingParameter` out of the `BindingContext’`s `BindingParameterCollection`.</span></span> <span data-ttu-id="16644-237">그런 다음 `ChunkingBindingParameter` 내에 포함된 동작 컬렉션이 `ChunkingChannelFactory` 또는 `ChunkingChannelListener`에 전달된 다음 `ChunkingDuplexSessionChannel`에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="16644-237">The collection of actions contained within the `ChunkingBindingParameter` is then passed to the `ChunkingChannelFactory` or `ChunkingChannelListener`, which in turn passes it to the `ChunkingDuplexSessionChannel`.</span></span>  
  
## <a name="running-the-sample"></a><span data-ttu-id="16644-238">샘플 실행</span><span class="sxs-lookup"><span data-stu-id="16644-238">Running the Sample</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="16644-239">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="16644-239">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="16644-240">다음 명령을 사용하여 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="16644-240">Install [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 using the following command.</span></span>  
  
    ```  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2.  <span data-ttu-id="16644-241">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="16644-241">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
3.  <span data-ttu-id="16644-242">지침에 따라 솔루션을 빌드하려면 [Windows Communication Foundation 샘플 빌드](../../../../docs/framework/wcf/samples/building-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="16644-242">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4.  <span data-ttu-id="16644-243">지침에 따라 단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="16644-243">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
5.  <span data-ttu-id="16644-244">먼저 Service.exe를 실행한 다음 Client.exe를 실행하고 두 콘솔 창에서 출력을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="16644-244">Run Service.exe first, then run Client.exe and watch both console windows for output.</span></span>  
  
 <span data-ttu-id="16644-245">샘플을 실행할 경우의 예상 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="16644-245">When running the sample, the following output is expected.</span></span>  
  
 <span data-ttu-id="16644-246">클라이언트</span><span class="sxs-lookup"><span data-stu-id="16644-246">Client:</span></span>  
  
```  
Press enter when service is available  
  
 > Sent chunk 1 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10  
 > Sent chunk 2 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10  
 > Sent chunk 3 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10  
 > Sent chunk 4 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10  
 > Sent chunk 5 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10  
 > Sent chunk 6 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10  
 > Sent chunk 7 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10  
 > Sent chunk 8 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10  
 > Sent chunk 9 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10  
 > Sent chunk 10 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10  
 < Received chunk 1 of message 5b226ad5-c088-4988-b737-6a565e0563dd  
 < Received chunk 2 of message 5b226ad5-c088-4988-b737-6a565e0563dd  
 < Received chunk 3 of message 5b226ad5-c088-4988-b737-6a565e0563dd  
 < Received chunk 4 of message 5b226ad5-c088-4988-b737-6a565e0563dd  
 < Received chunk 5 of message 5b226ad5-c088-4988-b737-6a565e0563dd  
 < Received chunk 6 of message 5b226ad5-c088-4988-b737-6a565e0563dd  
 < Received chunk 7 of message 5b226ad5-c088-4988-b737-6a565e0563dd  
 < Received chunk 8 of message 5b226ad5-c088-4988-b737-6a565e0563dd  
 < Received chunk 9 of message 5b226ad5-c088-4988-b737-6a565e0563dd  
 < Received chunk 10 of message 5b226ad5-c088-4988-b737-6a565e0563dd  
```  
  
 <span data-ttu-id="16644-247">서버:</span><span class="sxs-lookup"><span data-stu-id="16644-247">Server:</span></span>  
  
```  
Service started, press enter to exit  
 < Received chunk 1 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10  
 < Received chunk 2 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10  
 < Received chunk 3 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10  
 < Received chunk 4 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10  
 < Received chunk 5 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10  
 < Received chunk 6 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10  
 < Received chunk 7 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10  
 < Received chunk 8 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10  
 < Received chunk 9 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10  
 < Received chunk 10 of message 867c1fd1-d39e-4be1-bc7b-32066d7ced10  
 > Sent chunk 1 of message 5b226ad5-c088-4988-b737-6a565e0563dd  
 > Sent chunk 2 of message 5b226ad5-c088-4988-b737-6a565e0563dd  
 > Sent chunk 3 of message 5b226ad5-c088-4988-b737-6a565e0563dd  
 > Sent chunk 4 of message 5b226ad5-c088-4988-b737-6a565e0563dd  
 > Sent chunk 5 of message 5b226ad5-c088-4988-b737-6a565e0563dd  
 > Sent chunk 6 of message 5b226ad5-c088-4988-b737-6a565e0563dd  
 > Sent chunk 7 of message 5b226ad5-c088-4988-b737-6a565e0563dd  
 > Sent chunk 8 of message 5b226ad5-c088-4988-b737-6a565e0563dd  
 > Sent chunk 9 of message 5b226ad5-c088-4988-b737-6a565e0563dd  
 > Sent chunk 10 of message 5b226ad5-c088-4988-b737-6a565e0563dd  
```  
  
## <a name="see-also"></a><span data-ttu-id="16644-248">참고 항목</span><span class="sxs-lookup"><span data-stu-id="16644-248">See Also</span></span>
