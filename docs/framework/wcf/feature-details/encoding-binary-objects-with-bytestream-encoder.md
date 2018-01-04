---
title: "ByteStream 인코더를 사용하여 이진 개체 인코딩"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 020ee981-c889-4b12-a3ea-91823ef46444
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2cf68356ffa5fe20de7bd417c77388cd214ca718
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="encoding-binary-objects-with-bytestream-encoder"></a><span data-ttu-id="eb6c4-102">ByteStream 인코더를 사용하여 이진 개체 인코딩</span><span class="sxs-lookup"><span data-stu-id="eb6c4-102">Encoding Binary Objects with ByteStream Encoder</span></span>
<span data-ttu-id="eb6c4-103">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]을 사용한 원시 이진 데이터의 보내기 및 받기는 <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>를 사용하여 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb6c4-103">Sending and receiving raw binary data with [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] is configured using <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>.</span></span>  
  
## <a name="byte-stream-message-encoder-architecture"></a><span data-ttu-id="eb6c4-104">바이트 스트림 메시지 인코더 아키텍처</span><span class="sxs-lookup"><span data-stu-id="eb6c4-104">Byte Stream Message Encoder Architecture</span></span>  
 <span data-ttu-id="eb6c4-105">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 사용하는 이진 메시지 인코더에는 메시지의 내부 이진 데이터를 처리하거나, 유효성을 검사하거나, 식별하는 기능이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eb6c4-105">The binary message encoder used by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] has no facility for processing, validating, or identifying the underlying binary data in the message.</span></span> <span data-ttu-id="eb6c4-106">데이터 패키지는 XML로 인코딩된 후 보내기, 받기 및 디코딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb6c4-106">The data package is encoded into XML, sent, received, and decoded.</span></span> <span data-ttu-id="eb6c4-107">인코더는 데이터가 전송에 전달된 후와 메시지가 메시지 큐에 보내지기 전에 데이터를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="eb6c4-107">The encoder processes the data after being passed to the transport and before the message is sent to the message queue.</span></span> <span data-ttu-id="eb6c4-108">이진 인코더는 메시지 데이터를 `<binary>` 요소에 래핑하고 메시지를 받은 후 이 요소를 제거하는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="eb6c4-108">Functionally, the binary encoder wraps the message data in `<binary>` elements for sending and removes the elements after the message is received.</span></span>  
  
## <a name="using-the-byte-stream-message-encoder"></a><span data-ttu-id="eb6c4-109">바이트 스트림 메시지 인코더 사용</span><span class="sxs-lookup"><span data-stu-id="eb6c4-109">Using the Byte Stream Message Encoder</span></span>  
 <span data-ttu-id="eb6c4-110">다음 예제에서는 바이트 스트림 메시지 인코더를 구현하는 서비스 계약을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="eb6c4-110">The following example shows a service contract that implements the byte stream message encoder.</span></span>  
  
```csharp  
[OperationContract]  
Void Myfunction(Stream stream);  
```  
  
 <span data-ttu-id="eb6c4-111">다음 예제에서는 호출되는 서비스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="eb6c4-111">The following example shows the service being invoked.</span></span>  
  
```csharp  
proxy.MyFunction(stream);  
```  
  
 <span data-ttu-id="eb6c4-112">라우터와 같은 메시지 인프라를 구현하는 서비스를 사용하는 경우 다음 예제와 같이 메시지가 검사, 유효성 검사 또는 상호 작용 없이 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb6c4-112">In the case of using a service that implements a message infrastructure (such as a router), the message is processed without inspecting, validating, or otherwise interacting with the message, as shown in the following example.</span></span>  
  
```csharp  
[OperationContract]  
void ProcessMessage(Message message) ;  
```  
  
## <a name="scenarios"></a><span data-ttu-id="eb6c4-113">시나리오</span><span class="sxs-lookup"><span data-stu-id="eb6c4-113">Scenarios</span></span>  
 <span data-ttu-id="eb6c4-114">바이트 스트림 인코더는 다음과 같은 시나리오에서 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="eb6c4-114">The Byte Stream Encoder is useful in the following scenarios.</span></span>  
  
-   <span data-ttu-id="eb6c4-115">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]를 사용하여 컴퓨터 간에 JPEG 이미지를 전송하는 경우.</span><span class="sxs-lookup"><span data-stu-id="eb6c4-115">Transferring a JPEG image between computers using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="eb6c4-116">이 시나리오에서는 이미지가 외부 소스에서의 전송을 통해 도착하며 전송된 데이터는 이미지를 구성하는 원시 바이트입니다.</span><span class="sxs-lookup"><span data-stu-id="eb6c4-116">In this scenario, the image will arrive through the transport from an outside source, and the data sent will be the raw bytes that make up the image.</span></span> <span data-ttu-id="eb6c4-117">서비스는 이진 데이터를 받고 이미지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="eb6c4-117">A service will receive the binary data and display the image.</span></span>  
  
-   <span data-ttu-id="eb6c4-118">메시지 큐에서 정보를 읽고 처리하는 경우.</span><span class="sxs-lookup"><span data-stu-id="eb6c4-118">Reading information out of a message queue and processing it.</span></span> <span data-ttu-id="eb6c4-119">메시지 큐 관리자에서 메시지를 읽으며 이 메시지는 처리되기 위해 메시지 큐 채널 위로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb6c4-119">The message will be read from a message queue manager, and passed up the message queue channel to be handled.</span></span> <span data-ttu-id="eb6c4-120">메시지 큐 채널은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 채널 스택에서 큐 관리자 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb6c4-120">The message queue channel will act as a queue manager in the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] channel stack.</span></span>  
  
 <span data-ttu-id="eb6c4-121">메시지 큐 채널을 통해 메시지를 보내는 경우 보낸 사람은 큐 관리자에서 받은 바이트를 제어할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eb6c4-121">In the case of sending a message over a message queue channel, the sender has no control over the bytes received from the queue manager.</span></span> <span data-ttu-id="eb6c4-122">받는 프로세스에 원시 바이트를 읽는 기능이 없는 경우 메시지가 잘못된 형식으로 수신되고 처리되지 않습니다. 받는 프로세스에는 받은 바이트를 사용 가능한 형식으로 다시 변환하는 기능이 있다고 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb6c4-122">If the receiving process has no capability to read raw bytes, the message will be received as badly formatted and will not be processed; it is assumed that the receiving process will have the capability of translating the received bytes back into a usable format.</span></span>
