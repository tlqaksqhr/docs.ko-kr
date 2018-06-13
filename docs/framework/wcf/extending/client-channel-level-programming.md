---
title: 클라이언트 채널 수준 프로그래밍
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3b787719-4e77-4e77-96a6-5b15a11b995a
ms.openlocfilehash: ff399a2f3a4b86404695502fb002ee6920bea758
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33486507"
---
# <a name="client-channel-level-programming"></a><span data-ttu-id="89ad1-102">클라이언트 채널 수준 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="89ad1-102">Client Channel-Level Programming</span></span>
<span data-ttu-id="89ad1-103">이 항목에서는 사용 하지 않고 Windows Communication Foundation (WCF) 클라이언트 응용 프로그램을 작성 하는 방법을 설명는 <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType> 클래스 및 관련된 개체 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="89ad1-103">This topic describes how to write a Windows Communication Foundation (WCF) client application without using the <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType> class and its associated object model.</span></span>  
  
## <a name="sending-messages"></a><span data-ttu-id="89ad1-104">메시지 보내기</span><span class="sxs-lookup"><span data-stu-id="89ad1-104">Sending Messages</span></span>  
 <span data-ttu-id="89ad1-105">메시지를 보낸 다음 회신을 받고 처리할 준비를 하려면 다음 단계가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="89ad1-105">To be ready to send messages and receive and process replies, the following steps are required:</span></span>  
  
1.  <span data-ttu-id="89ad1-106">바인딩을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="89ad1-106">Create a binding.</span></span>  
  
2.  <span data-ttu-id="89ad1-107">채널 팩터리를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="89ad1-107">Build a channel factory.</span></span>  
  
3.  <span data-ttu-id="89ad1-108">채널을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="89ad1-108">Create a channel.</span></span>  
  
4.  <span data-ttu-id="89ad1-109">요청을 보내고 회신을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="89ad1-109">Send a request and read the reply.</span></span>  
  
5.  <span data-ttu-id="89ad1-110">모든 채널 개체를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="89ad1-110">Close all channel objects.</span></span>  
  
#### <a name="creating-a-binding"></a><span data-ttu-id="89ad1-111">바인딩 만들기</span><span class="sxs-lookup"><span data-stu-id="89ad1-111">Creating a Binding</span></span>  
 <span data-ttu-id="89ad1-112">수신 하는 경우와 비슷하며 (참조 [서비스 채널 수준 프로그래밍](../../../../docs/framework/wcf/extending/service-channel-level-programming.md)), 바인딩을 만들어야만 시작 메시지를 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="89ad1-112">Similar to the receiving case (see [Service Channel-Level Programming](../../../../docs/framework/wcf/extending/service-channel-level-programming.md)), sending messages starts by creating a binding.</span></span> <span data-ttu-id="89ad1-113">이 예제에서는 새 <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType>을 만들고 <xref:System.ServiceModel.Channels.HttpTransportBindingElement?displayProperty=nameWithType>를 요소 컬렉션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="89ad1-113">This example creates a new <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType> and adds an <xref:System.ServiceModel.Channels.HttpTransportBindingElement?displayProperty=nameWithType> to its Elements collection.</span></span>  
  
#### <a name="building-a-channelfactory"></a><span data-ttu-id="89ad1-114">ChannelFactory 빌드</span><span class="sxs-lookup"><span data-stu-id="89ad1-114">Building a ChannelFactory</span></span>  
 <span data-ttu-id="89ad1-115">이번에는 <xref:System.ServiceModel.Channels.IChannelListener?displayProperty=nameWithType>를 만드는 대신 형식 매개 변수가 <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>인 바인딩에서 <xref:System.ServiceModel.ChannelFactory.CreateFactory%2A?displayProperty=nameWithType>를 호출하여 <xref:System.ServiceModel.Channels.IRequestChannel?displayProperty=nameWithType>를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="89ad1-115">Instead of creating a <xref:System.ServiceModel.Channels.IChannelListener?displayProperty=nameWithType>, this time we create a <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType> by calling <xref:System.ServiceModel.ChannelFactory.CreateFactory%2A?displayProperty=nameWithType> on the binding where the type parameter is <xref:System.ServiceModel.Channels.IRequestChannel?displayProperty=nameWithType>.</span></span> <span data-ttu-id="89ad1-116">채널 수신기는 들어오는 메시지를 기다리는 측에서 사용하는 반면에 채널 팩터리는 채널을 만들기 위해 통신을 시작하는 측에서 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="89ad1-116">While channel listeners are used by the side that waits for incoming messages, channel factories are used by the side that initiates the communication to create a channel.</span></span> <span data-ttu-id="89ad1-117">채널 수신기에서처럼 채널 팩터리를 사용하기 전에 먼저 열어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89ad1-117">Just like channel listeners, channel factories must be opened first before they can be used.</span></span>  
  
#### <a name="creating-a-channel"></a><span data-ttu-id="89ad1-118">채널 만들기</span><span class="sxs-lookup"><span data-stu-id="89ad1-118">Creating a Channel</span></span>  
 <span data-ttu-id="89ad1-119"><xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A?displayProperty=nameWithType>을 호출하여 <xref:System.ServiceModel.Channels.IRequestChannel>을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="89ad1-119">We then call <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A?displayProperty=nameWithType> to create an <xref:System.ServiceModel.Channels.IRequestChannel>.</span></span> <span data-ttu-id="89ad1-120">이 호출을 통해 만들려는 새 채널을 사용하여 통신할 끝점의 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="89ad1-120">This call takes the address of the endpoint with which we want to communicate using the new channel being created.</span></span> <span data-ttu-id="89ad1-121">채널이 있는 경우 채널에서 열기를 호출하여 통신 준비 상태로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="89ad1-121">Once we have a channel, we call Open on it to put it in a state ready for communication.</span></span> <span data-ttu-id="89ad1-122">전송 특성에 따라 이 열기 호출을 통해 대상 끝점과 연결을 시작하거나 네트워크 상에서 아무것도 수행하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89ad1-122">Depending on the nature of the transport, this call to Open may initiate a connection with the target endpoint or may do nothing at all on the network.</span></span>  
  
#### <a name="sending-a-request-and-reading-the-reply"></a><span data-ttu-id="89ad1-123">요청 보내기 및 회신 읽기</span><span class="sxs-lookup"><span data-stu-id="89ad1-123">Sending a Request and Reading the Reply</span></span>  
 <span data-ttu-id="89ad1-124">채널이 열린 상태이면 메시지를 만들고 채널 요청 메서드를 사용하여 해당 요청을 보낸 다음 수신할 회신을 기다릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89ad1-124">Once we have an opened channel, we can create a message and use the channel’s Request method to send the request and wait for the reply to come back.</span></span> <span data-ttu-id="89ad1-125">이 메서드가 반환되면 끝점의 회신이 무엇인지 찾기 위해 읽을 수 있는 회신 메시지를 제공 받습니다.</span><span class="sxs-lookup"><span data-stu-id="89ad1-125">When this method returns, we have a reply message that we can read to find out what the endpoint’s reply was.</span></span>  
  
#### <a name="closing-objects"></a><span data-ttu-id="89ad1-126">개체 닫기</span><span class="sxs-lookup"><span data-stu-id="89ad1-126">Closing Objects</span></span>  
 <span data-ttu-id="89ad1-127">리소스 누수를 방지하기 위해 통신에서 사용되는 개체가 더 이상 필요 없는 경우 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="89ad1-127">To avoid leaking resources, we close objects used in communications when they are no longer required.</span></span>  
  
 <span data-ttu-id="89ad1-128">다음 코드 예제에서는 메시지를 보내고 회신을 읽기 위해 채널 팩터리를 사용하는 기본 클라이언트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="89ad1-128">The following code example shows a basic client using the channel factory to send a message and read the reply.</span></span>  
  
 [!code-csharp[ChannelProgrammingBasic#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/channelprogrammingbasic/cs/clientprogram.cs#2)]
 [!code-vb[ChannelProgrammingBasic#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/channelprogrammingbasic/vb/clientprogram.vb#2)]
