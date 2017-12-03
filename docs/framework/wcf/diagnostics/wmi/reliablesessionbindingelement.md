---
title: ReliableSessionBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: effda125-b8d3-4de6-8c0e-f59f5ea8f6eb
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 35a8a92ca93525c9f04ab984073ca64188f03284
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="reliablesessionbindingelement"></a><span data-ttu-id="2b2b5-102">ReliableSessionBindingElement</span><span class="sxs-lookup"><span data-stu-id="2b2b5-102">ReliableSessionBindingElement</span></span>
<span data-ttu-id="2b2b5-103">ReliableSessionBindingElement</span><span class="sxs-lookup"><span data-stu-id="2b2b5-103">ReliableSessionBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b2b5-104">구문</span><span class="sxs-lookup"><span data-stu-id="2b2b5-104">Syntax</span></span>  
  
```  
class ReliableSessionBindingElement : BindingElement  
{  
  datetime AcknowledgementInterval;  
  boolean FlowControlEnabled;  
  datetime InactivityTimeout;  
  sint32 MaxPendingChannels;  
  sint32 MaxRetryCount;  
  sint32 MaxTransferWindowSize;  
  boolean Ordered;  
  integer ReliableMessagingVersion;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="2b2b5-105">메서드</span><span class="sxs-lookup"><span data-stu-id="2b2b5-105">Methods</span></span>  
 <span data-ttu-id="2b2b5-106">ReliableSessionBindingElement 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2b2b5-106">The ReliableSessionBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="2b2b5-107">속성</span><span class="sxs-lookup"><span data-stu-id="2b2b5-107">Properties</span></span>  
 <span data-ttu-id="2b2b5-108">ReliableSessionBindingElement 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b2b5-108">The ReliableSessionBindingElement class has the following properties:</span></span>  
  
### <a name="acknowledgementinterval"></a><span data-ttu-id="2b2b5-109">AcknowledgementInterval</span><span class="sxs-lookup"><span data-stu-id="2b2b5-109">AcknowledgementInterval</span></span>  
 <span data-ttu-id="2b2b5-110">데이터 형식: datetime</span><span class="sxs-lookup"><span data-stu-id="2b2b5-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="2b2b5-111">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="2b2b5-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2b2b5-112">팩터리에서 만든 신뢰할 수 있는 채널의 메시지 소스에 승인을 보내기 전에 대상이 대기하는 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="2b2b5-112">The interval of time that a destination waits before sending an acknowledgement to the message source on reliable channels that are created by the factory.</span></span>  
  
### <a name="flowcontrolenabled"></a><span data-ttu-id="2b2b5-113">FlowControlEnabled</span><span class="sxs-lookup"><span data-stu-id="2b2b5-113">FlowControlEnabled</span></span>  
 <span data-ttu-id="2b2b5-114">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="2b2b5-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="2b2b5-115">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="2b2b5-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2b2b5-116">흐름 제어 활성화 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2b2b5-116">A Boolean value that specifies whether flow control is enabled.</span></span>  
  
### <a name="inactivitytimeout"></a><span data-ttu-id="2b2b5-117">InactivityTimeout</span><span class="sxs-lookup"><span data-stu-id="2b2b5-117">InactivityTimeout</span></span>  
 <span data-ttu-id="2b2b5-118">데이터 형식: datetime</span><span class="sxs-lookup"><span data-stu-id="2b2b5-118">Data type: datetime</span></span>  
  
 <span data-ttu-id="2b2b5-119">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="2b2b5-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2b2b5-120">통신 상대방이 메시지를 보내지 않아도 채널에서 오류로 간주하지 않도록 허용하는 최대 기간을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2b2b5-120">Specifies the maximum duration the channel is going to allow the other communicating party not to send any messages before faulting the channel.</span></span>  
  
### <a name="maxpendingchannels"></a><span data-ttu-id="2b2b5-121">MaxPendingChannels</span><span class="sxs-lookup"><span data-stu-id="2b2b5-121">MaxPendingChannels</span></span>  
 <span data-ttu-id="2b2b5-122">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="2b2b5-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="2b2b5-123">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="2b2b5-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2b2b5-124">수신기에서 수락하기까지 대기할 수 있는 최대 채널 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2b2b5-124">The maximum number of channels that can wait to be accepted on the listener.</span></span>  
  
### <a name="maxretrycount"></a><span data-ttu-id="2b2b5-125">MaxRetryCount</span><span class="sxs-lookup"><span data-stu-id="2b2b5-125">MaxRetryCount</span></span>  
 <span data-ttu-id="2b2b5-126">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="2b2b5-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="2b2b5-127">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="2b2b5-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2b2b5-128">신뢰할 수 있는 채널이 기본 채널에서 `Send`를 호출하여 아직 승인을 받지 않은 메시지를 다시 전송하기 위해 시도할 수 있는 최대 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="2b2b5-128">The maximum number of times a reliable channel attempts to retransmit a message it has not received an acknowledgement for, by calling `Send` on its underlying channel.</span></span>  
  
### <a name="maxtransferwindowsize"></a><span data-ttu-id="2b2b5-129">MaxTransferWindowSize</span><span class="sxs-lookup"><span data-stu-id="2b2b5-129">MaxTransferWindowSize</span></span>  
 <span data-ttu-id="2b2b5-130">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="2b2b5-130">Data type: sint32</span></span>  
  
 <span data-ttu-id="2b2b5-131">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="2b2b5-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2b2b5-132">신뢰할 수 있는 세션에 대한 최대 전송 창 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="2b2b5-132">The maximum transfer window size for the reliable session.</span></span>  
  
### <a name="ordered"></a><span data-ttu-id="2b2b5-133">Ordered</span><span class="sxs-lookup"><span data-stu-id="2b2b5-133">Ordered</span></span>  
 <span data-ttu-id="2b2b5-134">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="2b2b5-134">Data type: boolean</span></span>  
  
 <span data-ttu-id="2b2b5-135">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="2b2b5-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2b2b5-136">메시지가 전송된 순서대로 도착하도록 보장하는지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2b2b5-136">A Boolean value that specifies whether messages are guaranteed to arrive in the order they were sent.</span></span>  
  
### <a name="reliablemessagingversion"></a><span data-ttu-id="2b2b5-137">ReliableMessagingVersion</span><span class="sxs-lookup"><span data-stu-id="2b2b5-137">ReliableMessagingVersion</span></span>  
 <span data-ttu-id="2b2b5-138">데이터 형식: integer</span><span class="sxs-lookup"><span data-stu-id="2b2b5-138">Data type: integer</span></span>  
  
 <span data-ttu-id="2b2b5-139">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="2b2b5-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2b2b5-140">신뢰할 수 있는 세션에 사용된 WS-ReliableMessaging 프로토콜을 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="2b2b5-140">An integer that specifies the WS-ReliableMessaging protocol version used in the reliable session.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b2b5-141">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2b2b5-141">Requirements</span></span>  
  
|<span data-ttu-id="2b2b5-142">MOF</span><span class="sxs-lookup"><span data-stu-id="2b2b5-142">MOF</span></span>|<span data-ttu-id="2b2b5-143">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b2b5-143">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="2b2b5-144">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="2b2b5-144">Namespace</span></span>|<span data-ttu-id="2b2b5-145">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b2b5-145">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2b2b5-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2b2b5-146">See Also</span></span>  
 <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>
