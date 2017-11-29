---
title: "중요한 추적"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 40a1770e-3b09-4142-b0dd-f9ef73642074
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 58322a472a59ee9d3ac9451ff1f20ed95405ac54
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="significant-traces"></a><span data-ttu-id="3bdd1-102">중요한 추적</span><span class="sxs-lookup"><span data-stu-id="3bdd1-102">Significant Traces</span></span>
<span data-ttu-id="3bdd1-103">이 항목에서는 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]에서 내보낸 일부 주요 추적을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3bdd1-103">This topic lists some of the major traces emitted by [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].</span></span>  
  
## <a name="significant-traces"></a><span data-ttu-id="3bdd1-104">중요한 추적</span><span class="sxs-lookup"><span data-stu-id="3bdd1-104">Significant Traces</span></span>  
  
|<span data-ttu-id="3bdd1-105">추적</span><span class="sxs-lookup"><span data-stu-id="3bdd1-105">Trace</span></span>|<span data-ttu-id="3bdd1-106">설명</span><span class="sxs-lookup"><span data-stu-id="3bdd1-106">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3bdd1-107">메시지 로그 추적</span><span class="sxs-lookup"><span data-stu-id="3bdd1-107">Message log trace</span></span>|<span data-ttu-id="3bdd1-108">[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 추적 소스를 사용할 때 `System.ServiceModel.MessageLogging` 메시지가 메시지 로깅 기능에 의해 기록되는 경우 이 추적을 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="3bdd1-108">The trace is emitted when a [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] message is logged by the message logging feature when the `System.ServiceModel.MessageLogging` trace source is enabled.</span></span> <span data-ttu-id="3bdd1-109">이 추적을 클릭하면 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3bdd1-109">Clicking this trace displays the message.</span></span> <span data-ttu-id="3bdd1-110">메시지에 대해 네 가지 구성 가능한 로깅 지점은 `ServiceLevelSendRequest`, `TransportSend`, `TransportReceive` 및 `ServiceLevelReceiveRequest`이며 이러한 로깅 지점도 메시지 로그 추적의 메시지 소스 특성에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3bdd1-110">There are four configurable logging points for a message: `ServiceLevelSendRequest`, `TransportSend`, `TransportReceive`, `ServiceLevelReceiveRequest`, also indicated by the Message Source attribute in the message log trace.</span></span>|  
|<span data-ttu-id="3bdd1-111">수신된 메시지 추적</span><span class="sxs-lookup"><span data-stu-id="3bdd1-111">Message received trace</span></span>|<span data-ttu-id="3bdd1-112">[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 추적 소스를 Information 또는 Verbose 수준에서 사용하는 경우 `System.ServiceModel` 메시지를 받을 때 이 추적을 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="3bdd1-112">This trace is emitted when a [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] message is received if the `System.ServiceModel` trace source is enabled at information or verbose level.</span></span> <span data-ttu-id="3bdd1-113">이 추적은 동작 그래프 보기에서 메시지 상관 관계 화살표를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3bdd1-113">This trace is necessary to see the message correlation arrow in the activity graph view.</span></span>|  
|<span data-ttu-id="3bdd1-114">전송된 메시지 추적</span><span class="sxs-lookup"><span data-stu-id="3bdd1-114">Message sent trace</span></span>|<span data-ttu-id="3bdd1-115">[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 추적 소스를 Information 또는 Verbose 수준에서 사용하는 경우 `System.ServiceModel` 메시지를 보낼 때 이 추적을 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="3bdd1-115">This trace is emitted when a [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] message is sent if the `System.ServiceModel` trace source is enabled at information or verbose level.</span></span> <span data-ttu-id="3bdd1-116">이 추적은 동작 그래프 보기에서 메시지 상관 관계 화살표를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3bdd1-116">This trace is necessary to see the message correlation arrow in the activity graph view.</span></span>|  
|<span data-ttu-id="3bdd1-117">Get ChannelEndpointElement</span><span class="sxs-lookup"><span data-stu-id="3bdd1-117">Get ChannelEndpointElement</span></span>|<span data-ttu-id="3bdd1-118">Information 수준에서 생성 채널 팩터리에 이 추적을 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="3bdd1-118">This trace is emitted in Construct channel factory, at information level.</span></span> <span data-ttu-id="3bdd1-119">클라이언트가 통신하는 끝점에 대한 설명(원격 주소, 바인딩, 계약 이름)을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3bdd1-119">It provides a description of the endpoint the client is talking to (remote address, binding, contract name).</span></span>|  
|<span data-ttu-id="3bdd1-120">Get ServiceElement</span><span class="sxs-lookup"><span data-stu-id="3bdd1-120">Get ServiceElement</span></span>|<span data-ttu-id="3bdd1-121">Information 수준에서 생성 서비스 호스트에 이 추적을 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="3bdd1-121">This trace is emitted in Construct service host, at Information level.</span></span> <span data-ttu-id="3bdd1-122">서비스 계약 및 바인딩의 설명을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3bdd1-122">It provides a description of the service contract and binding.</span></span>|  
|<span data-ttu-id="3bdd1-123">SocketConnection create</span><span class="sxs-lookup"><span data-stu-id="3bdd1-123">SocketConnection create</span></span>|<span data-ttu-id="3bdd1-124">클라이언트가 수행한 첫 번째 프로세스 동작 및 서비스의 Receive bytes 동작에 이 추적을 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="3bdd1-124">This trace is emitted in the first Process action performed by the client and in the Receive bytes activity on the service.</span></span> <span data-ttu-id="3bdd1-125">로컬 및 원격 IP 주소를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3bdd1-125">It provides the local and remote IP addresses.</span></span> <span data-ttu-id="3bdd1-126">Information 수준에서 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="3bdd1-126">It is emitted at Information level.</span></span>|
