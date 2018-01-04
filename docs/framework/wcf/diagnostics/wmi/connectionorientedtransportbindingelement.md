---
title: ConnectionOrientedTransportBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c1308313-f0e2-49e6-977d-6b4ce9ad35d1
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c0d399eb859118dfe94eb9e0a421fa405ae0f414
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="connectionorientedtransportbindingelement"></a><span data-ttu-id="bfb5c-102">ConnectionOrientedTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="bfb5c-102">ConnectionOrientedTransportBindingElement</span></span>
<span data-ttu-id="bfb5c-103">ConnectionOrientedTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="bfb5c-103">ConnectionOrientedTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfb5c-104">구문</span><span class="sxs-lookup"><span data-stu-id="bfb5c-104">Syntax</span></span>  
  
```  
class ConnectionOrientedTransportBindingElement : TransportBindingElement  
{  
  datetime ChannelInitializationTimeout;  
  sint32 ConnectionBufferSize;  
  string HostNameComparisonMode;  
  sint32 MaxBufferSize;  
  datetime MaxOutputDelay;  
  sint32 MaxPendingAccepts;  
  sint32 MaxPendingConnections;  
  string TransferMode;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="bfb5c-105">메서드</span><span class="sxs-lookup"><span data-stu-id="bfb5c-105">Methods</span></span>  
 <span data-ttu-id="bfb5c-106">ConnectionOrientedTransportBindingElement 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bfb5c-106">The ConnectionOrientedTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="bfb5c-107">속성</span><span class="sxs-lookup"><span data-stu-id="bfb5c-107">Properties</span></span>  
 <span data-ttu-id="bfb5c-108">ConnectionOrientedTransportBindingElement 클래스에는 다음 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfb5c-108">The ConnectionOrientedTransportBindingElement class has the following properties:</span></span>  
  
### <a name="channelinitializationtimeout"></a><span data-ttu-id="bfb5c-109">ChannelInitializationTimeout</span><span class="sxs-lookup"><span data-stu-id="bfb5c-109">ChannelInitializationTimeout</span></span>  
 <span data-ttu-id="bfb5c-110">데이터 형식: datetime</span><span class="sxs-lookup"><span data-stu-id="bfb5c-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="bfb5c-111">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="bfb5c-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bfb5c-112">제한 시간이 초과되기 전에 채널 초기화가 완료되어야 하는 기간을 지정하는 timespan입니다.</span><span class="sxs-lookup"><span data-stu-id="bfb5c-112">The timespan that specifies how long the channel initialization has to complete before timing out.</span></span>  
  
### <a name="connectionbuffersize"></a><span data-ttu-id="bfb5c-113">ConnectionBufferSize</span><span class="sxs-lookup"><span data-stu-id="bfb5c-113">ConnectionBufferSize</span></span>  
 <span data-ttu-id="bfb5c-114">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="bfb5c-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="bfb5c-115">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="bfb5c-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bfb5c-116">통신 중에 클라이언트나 서비스로부터 serialize된 메시지 청크를 전송할 때 사용되는 버퍼의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="bfb5c-116">The size of the buffer used to transmit a chunk of the serialized message on the wire from the client or service.</span></span>  
  
### <a name="hostnamecomparisonmode"></a><span data-ttu-id="bfb5c-117">HostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="bfb5c-117">HostNameComparisonMode</span></span>  
 <span data-ttu-id="bfb5c-118">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="bfb5c-118">Data type: string</span></span>  
  
 <span data-ttu-id="bfb5c-119">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="bfb5c-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bfb5c-120">URI를 일치시킬 때 서비스에 연결하기 위해 호스트 이름이 사용되는지 여부를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="bfb5c-120">A value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>  
  
### <a name="maxbuffersize"></a><span data-ttu-id="bfb5c-121">MaxBufferSize</span><span class="sxs-lookup"><span data-stu-id="bfb5c-121">MaxBufferSize</span></span>  
 <span data-ttu-id="bfb5c-122">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="bfb5c-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="bfb5c-123">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="bfb5c-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bfb5c-124">사용할 버퍼의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="bfb5c-124">The maximum size of the buffer to use.</span></span>  
  
### <a name="maxoutputdelay"></a><span data-ttu-id="bfb5c-125">MaxOutputDelay</span><span class="sxs-lookup"><span data-stu-id="bfb5c-125">MaxOutputDelay</span></span>  
 <span data-ttu-id="bfb5c-126">데이터 형식: datetime</span><span class="sxs-lookup"><span data-stu-id="bfb5c-126">Data type: datetime</span></span>  
  
 <span data-ttu-id="bfb5c-127">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="bfb5c-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bfb5c-128">메시지 청크 또는 전체 메시지를 보내기 전에 메모리에 버퍼링된 상태로 유지할 수 있는 최대 시간 간격입니다.</span><span class="sxs-lookup"><span data-stu-id="bfb5c-128">The maximum interval of time that a chunk of a message or a full message can remain buffered in memory before being sent out.</span></span>  
  
### <a name="maxpendingaccepts"></a><span data-ttu-id="bfb5c-129">MaxPendingAccepts</span><span class="sxs-lookup"><span data-stu-id="bfb5c-129">MaxPendingAccepts</span></span>  
 <span data-ttu-id="bfb5c-130">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="bfb5c-130">Data type: sint32</span></span>  
  
 <span data-ttu-id="bfb5c-131">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="bfb5c-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bfb5c-132">서비스에서 들어오는 연결을 처리하는 데 사용할 수 있는 보류 중인 최대 비동기 수락 스레드 수입니다.</span><span class="sxs-lookup"><span data-stu-id="bfb5c-132">The maximum number of pending asynchronous accept threads that are available for processing incoming connections on the service.</span></span>  
  
### <a name="maxpendingconnections"></a><span data-ttu-id="bfb5c-133">MaxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="bfb5c-133">MaxPendingConnections</span></span>  
 <span data-ttu-id="bfb5c-134">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="bfb5c-134">Data type: sint32</span></span>  
  
 <span data-ttu-id="bfb5c-135">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="bfb5c-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bfb5c-136">보류 중 연결의 최대 수입니다.</span><span class="sxs-lookup"><span data-stu-id="bfb5c-136">The maximum number of pending connections.</span></span>  
  
### <a name="transfermode"></a><span data-ttu-id="bfb5c-137">TransferMode</span><span class="sxs-lookup"><span data-stu-id="bfb5c-137">TransferMode</span></span>  
 <span data-ttu-id="bfb5c-138">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="bfb5c-138">Data type: string</span></span>  
  
 <span data-ttu-id="bfb5c-139">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="bfb5c-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bfb5c-140">메시지가 연결 지향 전송을 사용하여 버퍼링되는지 아니면 스트리밍되는지를 지정하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="bfb5c-140">A value that specifies whether the messages are buffered or streamed with the connection-oriented transport.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bfb5c-141">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bfb5c-141">Requirements</span></span>  
  
|<span data-ttu-id="bfb5c-142">MOF</span><span class="sxs-lookup"><span data-stu-id="bfb5c-142">MOF</span></span>|<span data-ttu-id="bfb5c-143">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfb5c-143">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="bfb5c-144">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="bfb5c-144">Namespace</span></span>|<span data-ttu-id="bfb5c-145">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfb5c-145">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bfb5c-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bfb5c-146">See Also</span></span>  
 <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement>
