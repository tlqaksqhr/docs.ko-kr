---
title: '&lt;reliableSession&gt;'
ms.date: 03/30/2017
ms.assetid: 129b4a59-37f0-4030-b664-03795d257d29
ms.openlocfilehash: 6b8049e2c493a652405a93eed68f05438819aecb
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltreliablesessiongt"></a><span data-ttu-id="4f103-102">&lt;reliableSession&gt;</span><span class="sxs-lookup"><span data-stu-id="4f103-102">&lt;reliableSession&gt;</span></span>
<span data-ttu-id="4f103-103">WS-Reliable Messaging 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="4f103-103">Defines setting for WS-Reliable Messaging.</span></span> <span data-ttu-id="4f103-104">이 요소가 사용자 지정 바인딩에 추가되면 그 결과로 만들어지는 채널에서 EOD(Exactly-Once Delivery) 보증을 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f103-104">When this element is added to a custom binding, the resulting channel can support exactly-once delivery assurances.</span></span>  
  
 <span data-ttu-id="4f103-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="4f103-105">\<system.serviceModel></span></span>  
<span data-ttu-id="4f103-106">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="4f103-106">\<bindings></span></span>  
<span data-ttu-id="4f103-107">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="4f103-107">\<customBinding></span></span>  
<span data-ttu-id="4f103-108">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="4f103-108">\<binding></span></span>  
<span data-ttu-id="4f103-109">\<reliableSession ></span><span class="sxs-lookup"><span data-stu-id="4f103-109">\<reliableSession></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f103-110">구문</span><span class="sxs-lookup"><span data-stu-id="4f103-110">Syntax</span></span>  
  
```xml  
<reliableSession acknowledgementInterval="TimeSpan"  
        flowControlEnabled="Boolean"   
    inactivityTimeout="TimeSpan"  
    maxPendingChannels="Integer"  
    maxRetryCount="Integer"   
        maxTransferWindowSize="Integer"  
    reliableMessagingVersion="Default/WSReliableMessagingFebruary2005/WSReliableMessaging11"  
    ordered="Boolean" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4f103-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="4f103-111">Attributes and Elements</span></span>  
 <span data-ttu-id="4f103-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4f103-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4f103-113">특성</span><span class="sxs-lookup"><span data-stu-id="4f103-113">Attributes</span></span>  
  
|<span data-ttu-id="4f103-114">특성</span><span class="sxs-lookup"><span data-stu-id="4f103-114">Attribute</span></span>|<span data-ttu-id="4f103-115">설명</span><span class="sxs-lookup"><span data-stu-id="4f103-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4f103-116">acknowledgementInterval</span><span class="sxs-lookup"><span data-stu-id="4f103-116">acknowledgementInterval</span></span>|<span data-ttu-id="4f103-117">채널이 해당 시점까지 받은 메시지에 대한 승인을 보내기 위해 대기하는 최대 시간 간격이 포함된 <xref:System.TimeSpan>입니다.</span><span class="sxs-lookup"><span data-stu-id="4f103-117">A <xref:System.TimeSpan> that contains the maximum time interval the channel is going to wait to send an acknowledgment for messages received up to that point.</span></span> <span data-ttu-id="4f103-118">기본값은 00:00:0.2입니다.</span><span class="sxs-lookup"><span data-stu-id="4f103-118">The default is 00:00:0.2.</span></span>|  
|<span data-ttu-id="4f103-119">flowControlEnabled</span><span class="sxs-lookup"><span data-stu-id="4f103-119">flowControlEnabled</span></span>|<span data-ttu-id="4f103-120">WS-Reliable Messaging에 대한 Microsoft 고유의 흐름 제어 구현인 고급 흐름 제어를 활성화할지 여부를 나타내는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="4f103-120">A Boolean value that indicates whether advanced flow control, a Microsoft-specific implementation of flow control for WS-Reliable messaging, is activated.</span></span> <span data-ttu-id="4f103-121">기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="4f103-121">The default is `true`.</span></span>|  
|<span data-ttu-id="4f103-122">InactivityTimeout</span><span class="sxs-lookup"><span data-stu-id="4f103-122">inactivityTimeout</span></span>|<span data-ttu-id="4f103-123">통신 상대방이 메시지를 보내지 않아도 채널에서 오류가 발생하지 않는 최대 기간을 지정하는 <xref:System.TimeSpan>입니다.</span><span class="sxs-lookup"><span data-stu-id="4f103-123">A <xref:System.TimeSpan> that specifies the maximum duration that the channel is going to allow the other communication party not to send any messages, before faulting the channel.</span></span> <span data-ttu-id="4f103-124">기본값은 00:10:00입니다.</span><span class="sxs-lookup"><span data-stu-id="4f103-124">The default is 00:10:00.</span></span><br /><br /> <span data-ttu-id="4f103-125">채널에서는 응용 프로그램 또는 인프라 메시지를 받는 작업이 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="4f103-125">Activity on a channel is defined as receiving an application or infrastructure messages.</span></span> <span data-ttu-id="4f103-126">이 속성은 비활성 세션을 유지하는 최대 시간을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="4f103-126">This property controls the maximum amount of time to keep an inactive session alive.</span></span> <span data-ttu-id="4f103-127">아무런 작업 없이 이 시간이 초과되면 인프라에서 해당 세션을 중단하며 채널에 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="4f103-127">If longer time passes with no activity, the session is aborted by the infrastructure and the channel faults.</span></span> <span data-ttu-id="4f103-128">**참고:** 주기적으로 연결을 유지 하는 메시지를 보내도록 응용 프로그램에 대 한 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4f103-128">**Note:**  It is not necessary for the application to periodically send messages to keep the connection alive.</span></span>|  
|<span data-ttu-id="4f103-129">maxPendingChannels</span><span class="sxs-lookup"><span data-stu-id="4f103-129">maxPendingChannels</span></span>|<span data-ttu-id="4f103-130">수신기에서 수락 대기할 수 있는 최대 채널 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="4f103-130">An integer that specifies the maximum number of channels that can wait on the listener to be accepted.</span></span> <span data-ttu-id="4f103-131">이 값은 1 이상 16384 이하여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f103-131">This value should be between 1 to 16384 inclusive.</span></span> <span data-ttu-id="4f103-132">기본값은 4입니다.</span><span class="sxs-lookup"><span data-stu-id="4f103-132">The default is 4.</span></span><br /><br /> <span data-ttu-id="4f103-133">수락 대기 중인 채널은 보류됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f103-133">Channels are pending when they are waiting to be accepted.</span></span> <span data-ttu-id="4f103-134">최대 채널 수에 도달하면 채널이 만들어지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4f103-134">Once that limit is reached, no channels are created.</span></span> <span data-ttu-id="4f103-135">대신 대기 중인 채널을 수락함으로써 채널 수가 줄어들 때까지 대기 중 모드를 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="4f103-135">Rather, they are put in pending mode until this number goes down (by accepting pending channels).</span></span> <span data-ttu-id="4f103-136">이것은 팩터리당 제한입니다.</span><span class="sxs-lookup"><span data-stu-id="4f103-136">This is a per-factory limit.</span></span><br /><br /> <span data-ttu-id="4f103-137">임계값에 도달하여 원격 응용 프로그램이 신뢰할 수 있는 새 세션을 설정하려고 하면 요청이 거부되고 열기 작업에 이 오류가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f103-137">When the threshold is reached and a remote application tries to establish a new reliable session, the request is denied and the open operation that prompted this faults.</span></span> <span data-ttu-id="4f103-138">이러한 제한은 보류 중인 보내는 채널 수에는 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4f103-138">This limit does not apply to the number of pending outgoing channels.</span></span>|  
|<span data-ttu-id="4f103-139">maxRetryCount</span><span class="sxs-lookup"><span data-stu-id="4f103-139">maxRetryCount</span></span>|<span data-ttu-id="4f103-140">신뢰할 수 있는 채널이 기본 채널에서 Send를 호출하여 아직 승인을 받지 않은 메시지를 다시 전송하기 위해 시도할 수 있는 최대 횟수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="4f103-140">An integer that specifies the maximum number of times a reliable channel attempts to retransmit a message it has not received an acknowledgment for, by calling Send on its underlying channel.</span></span><br /><br /> <span data-ttu-id="4f103-141">이 값은 0보다 커야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f103-141">This value should be greater than zero.</span></span> <span data-ttu-id="4f103-142">기본값은 8입니다.</span><span class="sxs-lookup"><span data-stu-id="4f103-142">The default is 8.</span></span><br /><br /> <span data-ttu-id="4f103-143">이 값은 0보다 큰 정수여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f103-143">This value should be an integer greater than zero.</span></span> <span data-ttu-id="4f103-144">마지막 재전송 이후 승인을 받지 못한 경우 채널에 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="4f103-144">If an acknowledgment is not received after the last retransmission, the channel faults.</span></span><br /><br /> <span data-ttu-id="4f103-145">받는 사람이 메시지 배달을 승인했으면 메시지가 전송된 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f103-145">A message is considered to be transferred if its delivery at the recipient has been acknowledged by the recipient.</span></span><br /><br /> <span data-ttu-id="4f103-146">전송된 메시지가 일정 시간 내에 승인을 받지 못하면 인프라에서 자동으로 메시지를 다시 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="4f103-146">If an acknowledgment has not been received within a certain amount of time for a message that has been transmitted, the infrastructure automatically retransmits the message.</span></span> <span data-ttu-id="4f103-147">인프라는 이 속성에 지정된 횟수만큼 메시지를 다시 보내려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f103-147">The infrastructure tries to resend the message for at most the number of times specified by this property.</span></span> <span data-ttu-id="4f103-148">마지막 재전송 이후 승인을 받지 못한 경우 채널에 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="4f103-148">If an acknowledgment is not received after the last retransmission, the channel faults.</span></span><br /><br /> <span data-ttu-id="4f103-149">인프라는 지수 백오프 알고리즘을 사용하여 계산된 평균 라운드트립 시간에 따라 재전송 시간을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="4f103-149">The infrastructure uses an exponential back-off algorithm to determine when to retransmit, based on a computed average round-trip time.</span></span> <span data-ttu-id="4f103-150">처음에 시간은 재전송 1초 전에 시작되고 재전송 시도마다 두 배씩 지연되어, 결과적으로 첫 번째 전송 시도와 마지막 전송 시도 간에 약 8.5분이 지나게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f103-150">The time initially starts at 1 second before retransmission and doubling the delay with every attempt, which results in approximately 8.5 minutes passing between the first transmission attempt and the last retransmission attempt.</span></span> <span data-ttu-id="4f103-151">첫 번째 재전송 시도는 계산된 라운드트립 시간에 따라 조정되고 결과적으로 재전송 시도에 따라 늘어나는 시간이 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="4f103-151">The time for the first retransmission attempt is adjusted according to the calculated round-trip time and the resulting stretch of time that those attempts take varies accordingly.</span></span> <span data-ttu-id="4f103-152">따라서 재전송 시간을 다양한 네트워크 조건에 맞게 동적으로 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f103-152">This allows the retransmission time to dynamically adapt to varying network conditions.</span></span>|  
|<span data-ttu-id="4f103-153">maxTransferWindowSize</span><span class="sxs-lookup"><span data-stu-id="4f103-153">maxTransferWindowSize</span></span>|<span data-ttu-id="4f103-154">버퍼의 최대 크기를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="4f103-154">An integer that specifies the maximum size of the buffer.</span></span> <span data-ttu-id="4f103-155">유효한 값은 1부터 4096까지입니다.</span><span class="sxs-lookup"><span data-stu-id="4f103-155">Valid values are from 1 to 4096 inclusive.</span></span><br /><br /> <span data-ttu-id="4f103-156">클라이언트에서 이 특성은 수신자가 승인하지 않은 메시지를 저장하기 위해 신뢰할 수 있는 채널에서 사용하는 최대 버퍼 크기를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="4f103-156">On the client, this attribute defines the maximum size of the buffer used by a reliable channel to hold messages not yet acknowledged by the receiver.</span></span> <span data-ttu-id="4f103-157">할당량 단위는 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="4f103-157">The unit of the quota is a message.</span></span> <span data-ttu-id="4f103-158">버퍼가 꽉 차면 더 이상의 보내기 작업은 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f103-158">If the buffer is full, further SEND operations are blocked.</span></span><br /><br /> <span data-ttu-id="4f103-159">수신자에서 이 특성은 응용 프로그램으로 발송되지 않은 들어오는 메시지를 저장하기 위해 채널에서 사용하는 최대 버퍼 크기를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="4f103-159">On the receiver, this attribute defines the maximum size of the buffer used by the channel to store incoming messages not yet dispatched to the application.</span></span> <span data-ttu-id="4f103-160">버퍼가 꽉 차면 그 이상의 메시지는 수신자에 의해 삭제되고 클라이언트가 다시 전송해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f103-160">If the buffer is full, further messages are silently dropped by the receiver and require retransmission by the client.</span></span>|  
|<span data-ttu-id="4f103-161">ordered</span><span class="sxs-lookup"><span data-stu-id="4f103-161">ordered</span></span>|<span data-ttu-id="4f103-162">전송된 순서대로 메시지 도착을 보장할지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="4f103-162">A Boolean that specifies whether messages are guaranteed to arrive in the order they were sent.</span></span> <span data-ttu-id="4f103-163">이 설정이 `false`일 경우 메시지가 순서와 관계없이 도착할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f103-163">If this setting is `false`, messages can arrive out of order.</span></span> <span data-ttu-id="4f103-164">기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="4f103-164">The default is `true`.</span></span>|  
|<span data-ttu-id="4f103-165">reliableMessagingVersion</span><span class="sxs-lookup"><span data-stu-id="4f103-165">reliableMessagingVersion</span></span>|<span data-ttu-id="4f103-166">사용할 WS-ReliableMessaging 버전을 지정하는 <xref:System.ServiceModel.ReliableMessagingVersion>의 유효한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="4f103-166">A valid value from <xref:System.ServiceModel.ReliableMessagingVersion> that specifies the WS-ReliableMessaging version to be used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4f103-167">자식 요소</span><span class="sxs-lookup"><span data-stu-id="4f103-167">Child Elements</span></span>  
 <span data-ttu-id="4f103-168">없음</span><span class="sxs-lookup"><span data-stu-id="4f103-168">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4f103-169">부모 요소</span><span class="sxs-lookup"><span data-stu-id="4f103-169">Parent Elements</span></span>  
  
|<span data-ttu-id="4f103-170">요소</span><span class="sxs-lookup"><span data-stu-id="4f103-170">Element</span></span>|<span data-ttu-id="4f103-171">설명</span><span class="sxs-lookup"><span data-stu-id="4f103-171">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4f103-172">\<binding></span><span class="sxs-lookup"><span data-stu-id="4f103-172">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="4f103-173">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="4f103-173">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4f103-174">설명</span><span class="sxs-lookup"><span data-stu-id="4f103-174">Remarks</span></span>  
 <span data-ttu-id="4f103-175">신뢰할 수 있는 세션은 신뢰할 수 있는 메시징 및 세션 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4f103-175">Reliable sessions provide features for reliable messaging and sessions.</span></span> <span data-ttu-id="4f103-176">신뢰할 수 있는 메시징 기능은 실패 시 통신을 다시 시도하고 메시지 차례로 도착과 같은 배달 보증을 지정할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f103-176">Reliable messaging retries communication on failure and allows delivery assurances such as in-order arrival of messages to be specified.</span></span> <span data-ttu-id="4f103-177">세션은 호출 간에 클라이언트의 상태를 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="4f103-177">Sessions maintain state for clients between calls.</span></span> <span data-ttu-id="4f103-178">이 요소는 메시지를 순서대로 배달하는 기능을 선택적으로도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4f103-178">This element also optionally provides ordered message delivery.</span></span> <span data-ttu-id="4f103-179">이 구현된 세션은 SOAP 매개자 및 전송 매개자에 적용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f103-179">This implemented session can cross SOAP and transport intermediaries.</span></span>  
  
 <span data-ttu-id="4f103-180">각 바인딩 요소는 메시지를 보내거나 받을 때의 처리 단계를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4f103-180">Each binding element represents a processing step when sending or receiving messages.</span></span> <span data-ttu-id="4f103-181">런타임에 바인딩 요소는 메시지를 주고 받는 데 필요한 나가는 채널 스택과 들어오는 채널 스택을 작성하기 위한 채널 팩터리 및 채널 수신기를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="4f103-181">At runtime, binding elements create the channel factories and listeners that are necessary to build outgoing and incoming channel stacks required to send and receive messages.</span></span> <span data-ttu-id="4f103-182">`reliableSession`는 끝점 간에 신뢰할 수 있는 세션을 설정하고 이 세션의 동작을 구성할 수 있는 선택적 계층을 스택에 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4f103-182">The `reliableSession` provides an optional layer in the stack that can establish a reliable session between endpoints and configure the behavior of this session.</span></span>  
  
 <span data-ttu-id="4f103-183">자세한 내용은 참조 [신뢰할 수 있는 세션](../../../../../docs/framework/wcf/feature-details/reliable-sessions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4f103-183">For more information, see [Reliable Sessions](../../../../../docs/framework/wcf/feature-details/reliable-sessions.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f103-184">예제</span><span class="sxs-lookup"><span data-stu-id="4f103-184">Example</span></span>  
 <span data-ttu-id="4f103-185">다음 예제에서는 다양한 전송 및 메시지 인코딩 요소, 특히 신뢰할 수 있는 세션 사용 등을 통해 사용자 지정 바인딩을 구성하는 방법을 보여 줍니다. 이렇게 하면 클라이언트 상태가 유지되며 차례로 배달 보증이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f103-185">The following example demonstrates how to configure a custom binding with various transport and message encoding elements, especially enabling reliable sessions, which maintains client state and specifies in-order delivery assurances.</span></span> <span data-ttu-id="4f103-186">이 기능은 클라이언트 및 서비스의 응용 프로그램 구성 파일에서 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f103-186">This feature is configured in the application configuration files for the client and service.</span></span> <span data-ttu-id="4f103-187">예제에서는 서비스 구성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4f103-187">The example show the service configuration.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service   
          name="Microsoft.ServiceModel.Samples.CalculatorService"  
          behaviorConfiguration="CalculatorServiceBehavior">  
        <!-- This endpoint is exposed at the base address provided by host: http://localhost/servicemodelsamples/service.svc  -->  
        <!-- specify customBinding binding and a binding configuration to use -->  
        <endpoint address=""  
                  binding="customBinding"  
                  bindingConfiguration="Binding1"   
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />  
        <!-- The mex endpoint is exposed at http://localhost/servicemodelsamples/service.svc/mex -->  
        <endpoint address="mex"  
                  binding="mexHttpBinding"  
                  contract="IMetadataExchange" />  
      </service>  
    </services>  
  
    <!-- custom binding configuration - configures HTTP transport, reliable sessions -->  
    <bindings>  
      <customBinding>  
        <binding name="Binding1">  
          <reliableSession />  
          <security authenticationMode="SecureConversation"  
                     requireSecurityContextCancellation="true">  
          </security>  
          <compositeDuplex />  
          <oneWay />  
          <textMessageEncoding messageVersion="Soap12WSAddressing10" writeEncoding="utf-8" />  
          <httpTransport authenticationScheme="Anonymous" bypassProxyOnLocal="false"  
                        hostNameComparisonMode="StrongWildcard"   
                        proxyAuthenticationScheme="Anonymous" realm=""   
                        useDefaultWebProxy="true" />  
        </binding>  
      </customBinding>  
    </bindings>  
  
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="CalculatorServiceBehavior">  
          <serviceMetadata httpGetEnabled="True"/>  
          <serviceDebug includeExceptionDetailInFaults="False" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4f103-188">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4f103-188">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ReliableSessionElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>  
 [<span data-ttu-id="4f103-189">신뢰할 수 있는 세션</span><span class="sxs-lookup"><span data-stu-id="4f103-189">Reliable Sessions</span></span>](../../../../../docs/framework/wcf/feature-details/reliable-sessions.md)  
 [<span data-ttu-id="4f103-190">바인딩</span><span class="sxs-lookup"><span data-stu-id="4f103-190">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="4f103-191">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="4f103-191">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="4f103-192">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="4f103-192">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="4f103-193">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="4f103-193">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
