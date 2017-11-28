---
title: "&lt;localServiceSettings&gt; 요소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0658549c-3f65-46dd-8c5c-9895441ed734
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1e251c226484788b7ebc059cd68caf1f3c150c62
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltlocalservicesettingsgt-element"></a><span data-ttu-id="3139f-102">&lt;localServiceSettings&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="3139f-102">&lt;localServiceSettings&gt; element</span></span>
<span data-ttu-id="3139f-103">이 바인딩에 대한 로컬 서비스의 보안 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3139f-103">Specifies the security settings of a local service for this binding.</span></span>  
  
 <span data-ttu-id="3139f-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="3139f-104">\<system.serviceModel></span></span>  
<span data-ttu-id="3139f-105">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="3139f-105">\<bindings></span></span>  
<span data-ttu-id="3139f-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="3139f-106">\<customBinding></span></span>  
<span data-ttu-id="3139f-107">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="3139f-107">\<binding></span></span>  
<span data-ttu-id="3139f-108">\<보안 ></span><span class="sxs-lookup"><span data-stu-id="3139f-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3139f-109">구문</span><span class="sxs-lookup"><span data-stu-id="3139f-109">Syntax</span></span>  
  
```xml  
<security>  
   <localServiceSettings detectReplays="Boolean"  
      inactivityTimeout="TimeSpan"  
      issuedCookieLifeTime="TimeSpan"  
      maxCachedCookies="Integer"   
      maxClockSkew="TimeSpan"   
      maxPendingSessions="Integer"  
      maxStatefulNegotiations="Integer"  
      negotiationTimeout="TimeSpan"  
      reconnectTransportOnFailure="Boolean"  
            replayCacheSize="Integer"  
      replayWindow="TimeSpan"  
      sessionKeyRenewalInterval="TimeSpan"  
      sessionKeyRolloverInterval="TimeSpan"  
      timestampValidityDuration="TimeSpan" />  
</security>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3139f-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="3139f-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3139f-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3139f-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3139f-112">특성</span><span class="sxs-lookup"><span data-stu-id="3139f-112">Attributes</span></span>  
  
|<span data-ttu-id="3139f-113">특성</span><span class="sxs-lookup"><span data-stu-id="3139f-113">Attribute</span></span>|<span data-ttu-id="3139f-114">설명</span><span class="sxs-lookup"><span data-stu-id="3139f-114">Description</span></span>|  
|---------------|-----------------|  
|`detectReplays`|<span data-ttu-id="3139f-115">채널에 대한 재생 공격이 검색되어 자동으로 처리되는지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="3139f-115">A Boolean value that specifies whether replay attacks against the channel are detected and dealt with automatically.</span></span> <span data-ttu-id="3139f-116">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="3139f-116">The default is `false`.</span></span>|  
|`inactivityTimeout`|<span data-ttu-id="3139f-117">채널에서 제한 시간이 초과되기 전에 대기하는 비활성 기간을 지정하는 <xref:System.TimeSpan>(양수)입니다. 기본값은 "01:00:00"입니다.</span><span class="sxs-lookup"><span data-stu-id="3139f-117">A positive <xref:System.TimeSpan> that specifies the duration of inactivity the channel waits before it times out. The default is "01:00:00".</span></span>|  
|`issuedCookieLifeTime`|<span data-ttu-id="3139f-118">새로운 모든 보안 쿠키에 발급되는 수명을 지정하는 <xref:System.TimeSpan>입니다.</span><span class="sxs-lookup"><span data-stu-id="3139f-118">A <xref:System.TimeSpan> that specifies the lifetime issued to all new security cookies.</span></span> <span data-ttu-id="3139f-119">수명이 지난 쿠키는 재활용되며 다시 협상되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3139f-119">Cookies that exceed their lifetime are recycled and need to be negotiated again.</span></span> <span data-ttu-id="3139f-120">기본값은 "10:00:00"입니다.</span><span class="sxs-lookup"><span data-stu-id="3139f-120">The default value is "10:00:00".</span></span>|  
|`maxCachedCookies`|<span data-ttu-id="3139f-121">캐시할 수 있는 최대 쿠키 수를 지정하는 양의 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="3139f-121">A positive integer that specifies the maximum number of cookies that can be cached.</span></span> <span data-ttu-id="3139f-122">기본값은 1000입니다.</span><span class="sxs-lookup"><span data-stu-id="3139f-122">The default is 1000.</span></span>|  
|`maxClockSkew`|<span data-ttu-id="3139f-123">서로 통신하는 양쪽의 시스템 클록 간의 최대 시간 차이를 지정하는 <xref:System.TimeSpan>입니다.</span><span class="sxs-lookup"><span data-stu-id="3139f-123">A <xref:System.TimeSpan> that specifies the maximum time difference between the system clocks of the two communicating parties.</span></span> <span data-ttu-id="3139f-124">기본값은 "00:05:00"입니다.</span><span class="sxs-lookup"><span data-stu-id="3139f-124">The default value is "00:05:00".</span></span><br /><br /> <span data-ttu-id="3139f-125">이 값을 기본값으로 설정하면 수신자는 메시지를 받은 시간을 기준으로 보낸 시간 타임스탬프가 전후 5분 이내인 메시지를 수신 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="3139f-125">When this value is set to the default, the receiver accepts messages with send-time time stamps up to 5 minutes later or earlier than the time the message was received.</span></span> <span data-ttu-id="3139f-126">보낸 시간 테스트를 통과하지 못한 메시지는 거부됩니다.</span><span class="sxs-lookup"><span data-stu-id="3139f-126">Messages that do not pass the send-time test are rejected.</span></span> <span data-ttu-id="3139f-127">이 설정은 `replayWindow` 특성과 함께 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3139f-127">This setting is used in conjunction with the `replayWindow` attribute.</span></span>|  
|`maxPendingSessions`|<span data-ttu-id="3139f-128">서비스에서 지원하는 보류 중인 보안 세션의 최대 수를 지정하는 양의 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="3139f-128">A positive integer that specifies the maximum number of pending security sessions that the service supports.</span></span> <span data-ttu-id="3139f-129">이 한도에 도달하면 모든 새 클라이언트가 SOAP 오류를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="3139f-129">When this limit is reached, all new clients receive SOAP faults.</span></span> <span data-ttu-id="3139f-130">기본값은 1000입니다.</span><span class="sxs-lookup"><span data-stu-id="3139f-130">The default value is 1000.</span></span>|  
|`maxStatefulNegotiations`|<span data-ttu-id="3139f-131">동시에 활성 상태를 유지할 수 있는 보안 협상 수를 지정하는 양의 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="3139f-131">A positive integer that specifies the number of security negotiations that can be active concurrently.</span></span> <span data-ttu-id="3139f-132">한도를 초과하는 협상 세션은 큐에 대기되며 한도 아래로 떨어져야 완료될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3139f-132">Negotiation sessions in excess of the limit are queued and can only be completed when a space below the limit becomes available.</span></span> <span data-ttu-id="3139f-133">기본값은 1024입니다.</span><span class="sxs-lookup"><span data-stu-id="3139f-133">The default value is 1024.</span></span>|  
|`negotiationTimeout`|<span data-ttu-id="3139f-134">채널에서 사용하는 보안 정책의 수명을 지정하는 <xref:System.TimeSpan>입니다.</span><span class="sxs-lookup"><span data-stu-id="3139f-134">A <xref:System.TimeSpan> that specifies the lifetime of the security policy used by channel.</span></span> <span data-ttu-id="3139f-135">시간이 만료되면 채널이 새로운 보안 정책에 대해 클라이언트와 재협상합니다.</span><span class="sxs-lookup"><span data-stu-id="3139f-135">When the time expires, the channel renegotiates with the client for a new security policy.</span></span> <span data-ttu-id="3139f-136">기본값은 "00:02:00"입니다.</span><span class="sxs-lookup"><span data-stu-id="3139f-136">The default value is "00:02:00".</span></span>|  
|`reconnectTransportOnFailure`|<span data-ttu-id="3139f-137">WS-Reliable Messaging을 사용하는 연결에서 전송 실패 후 다시 연결을 시도할지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="3139f-137">A Boolean value that specifies whether connections using WS-Reliable messaging will attempt to reconnect after transport failures.</span></span> <span data-ttu-id="3139f-138">기본값은 `true`로, 다시 연결이 무한히 시도된다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="3139f-138">The default is `true`, which means that infinite attempts to reconnect are attempted.</span></span> <span data-ttu-id="3139f-139">이 순환은 비활성 제한 시간이 초과되어야만 중단되며, 이 경우 채널에서 다시 연결할 수 없으면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="3139f-139">The cycle is broken by the inactivity time-out, which causes the channel to throw an exception when it cannot be reconnected.</span></span>|  
|`replayCacheSize`|<span data-ttu-id="3139f-140">재생 검색에 사용되는 캐시된 Nonce의 수를 지정하는 양의 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="3139f-140">A positive integer that specifies the number of cached nonces used for replay detection.</span></span> <span data-ttu-id="3139f-141">이 제한을 초과하면 가장 오래된 Nonce가 제거되고 새 메시지에 대해 새로운 Nonce가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="3139f-141">If this limit is exceeded, the oldest nonce is removed and a new nonce is created for the new message.</span></span> <span data-ttu-id="3139f-142">기본값은 500000입니다.</span><span class="sxs-lookup"><span data-stu-id="3139f-142">The default value is 500000.</span></span>|  
|`replayWindow`|<span data-ttu-id="3139f-143">개별 메시지 Nonce의 유효 기간을 지정하는 <xref:System.TimeSpan>입니다.</span><span class="sxs-lookup"><span data-stu-id="3139f-143">A <xref:System.TimeSpan> that specifies the duration in which individual message nonces are valid.</span></span><br /><br /> <span data-ttu-id="3139f-144">이 속성에서 지정한 시간이 지나면 이전에 보낸 메시지와 동일한 Nonce를 갖는 메시지는 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3139f-144">After this duration, a message sent with the same nonce as the one sent before will not be accepted.</span></span> <span data-ttu-id="3139f-145">이 특성은 `maxClockSkew` 특성과 함께 사용되어 재생 공격을 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="3139f-145">This attribute is used in conjunction with the `maxClockSkew` attribute to prevent replay attacks.</span></span> <span data-ttu-id="3139f-146">메시지 재생 창이 만료된 후에 공격자가 그 메시지를 재생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3139f-146">An attacker could replay a message after its replay window has expired.</span></span> <span data-ttu-id="3139f-147">그러나 이 메시지는 `maxClockSkew` 테스트를 통과하지 못합니다. 해당 테스트는 메시지의 보낸 시간 타임스탬프가 메시지를 받은 시간보다 지정된 시간 이상으로 늦거나 빠르면 그 메시지를 거부합니다.</span><span class="sxs-lookup"><span data-stu-id="3139f-147">This message, however, would fail the `maxClockSkew` test which rejects messages with send-time timestamps up to a specified time later or earlier than the time the message was received.</span></span>|  
|`sessionKeyRenewalInterval`|<span data-ttu-id="3139f-148">개시자가 보안 세션을 위해 키를 갱신하는 시간 간격을 지정하는 <xref:System.TimeSpan>입니다.</span><span class="sxs-lookup"><span data-stu-id="3139f-148">A <xref:System.TimeSpan> that specifies the duration after which the initiator will renew the key for the security session.</span></span> <span data-ttu-id="3139f-149">기본값은 "10:00:00"입니다.</span><span class="sxs-lookup"><span data-stu-id="3139f-149">The default is "10:00:00".</span></span>|  
|`sessionKeyRolloverInterval`|<span data-ttu-id="3139f-150">키 갱신 중에 들어오는 메시지에서 이전 세션 키를 사용할 수 있는 시간 간격을 지정하는 <xref:System.TimeSpan>입니다.</span><span class="sxs-lookup"><span data-stu-id="3139f-150">A <xref:System.TimeSpan> that specifies the time interval a previous session key is valid on incoming messages during a key renewal.</span></span> <span data-ttu-id="3139f-151">기본값은 "00:05:00"입니다.</span><span class="sxs-lookup"><span data-stu-id="3139f-151">The default is "00:05:00".</span></span><br /><br /> <span data-ttu-id="3139f-152">키 갱신 중에 클라이언트와 서버는 반드시 사용 가능한 최신 키를 사용하여 메시지를 보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3139f-152">During key renewal, the client and server must always send messages using the most current available key.</span></span> <span data-ttu-id="3139f-153">양쪽 모두 롤오버 시간이 만료될 때까지는 이전 세션 키를 사용하여 보안되는 메시지를 수락할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3139f-153">Both parties will accept incoming messages secured with the previous session key until the rollover time expires.</span></span>|  
|`timestampValidityDuration`|<span data-ttu-id="3139f-154">타임스탬프의 유효 기간을 지정하는 <xref:System.TimeSpan>(양수)입니다.</span><span class="sxs-lookup"><span data-stu-id="3139f-154">A positive <xref:System.TimeSpan> that specifies the duration in which a time stamp is valid.</span></span> <span data-ttu-id="3139f-155">기본값은 "00:15:00"입니다.</span><span class="sxs-lookup"><span data-stu-id="3139f-155">The default is "00:15:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3139f-156">자식 요소</span><span class="sxs-lookup"><span data-stu-id="3139f-156">Child Elements</span></span>  
 <span data-ttu-id="3139f-157">없음</span><span class="sxs-lookup"><span data-stu-id="3139f-157">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3139f-158">부모 요소</span><span class="sxs-lookup"><span data-stu-id="3139f-158">Parent Elements</span></span>  
  
|<span data-ttu-id="3139f-159">요소</span><span class="sxs-lookup"><span data-stu-id="3139f-159">Element</span></span>|<span data-ttu-id="3139f-160">설명</span><span class="sxs-lookup"><span data-stu-id="3139f-160">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3139f-161">\<보안 ></span><span class="sxs-lookup"><span data-stu-id="3139f-161">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)|<span data-ttu-id="3139f-162">사용자 지정 바인딩에 대한 보안 옵션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3139f-162">Specifies the security options for a custom binding.</span></span>|  
|[<span data-ttu-id="3139f-163">\<secureConversationBootstrap ></span><span class="sxs-lookup"><span data-stu-id="3139f-163">\<secureConversationBootstrap></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)|<span data-ttu-id="3139f-164">보안 대화 서비스 개시에 사용되는 기본값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3139f-164">Specifies the default values used for initiating a secure conversation service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3139f-165">설명</span><span class="sxs-lookup"><span data-stu-id="3139f-165">Remarks</span></span>  
 <span data-ttu-id="3139f-166">이 설정은 서비스 보안 정책의 일부로 게시되지 않고 클라이언트의 바인딩에 영향을 주지 않으므로 로컬 속성에 속합니다.</span><span class="sxs-lookup"><span data-stu-id="3139f-166">The settings are local because they are not published as part of the security policy of the service and do not affect the client's binding.</span></span>  
  
 <span data-ttu-id="3139f-167">`localServiceSecuritySettings` 요소의 다음 특성을 사용하면 DOS(서비스 거부) 보안 공격을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3139f-167">The following attributes of the `localServiceSecuritySettings` element can help mitigate a denial-of-service (DOS) security attack:</span></span>  
  
-   <span data-ttu-id="3139f-168">`maxCachedCookies`: SPNEGO 또는 SSL 협상 후에 서버에서 캐시하는 시간 제한 SecurityContextToken의 최대 개수를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="3139f-168">`maxCachedCookies`: controls the maximum number of time-bounded SecurityContextTokens that are cached by the server after doing SPNEGO or SSL negotiation.</span></span>  
  
-   <span data-ttu-id="3139f-169">`issuedCookieLifetime`: SPNEGO 또는 SSL 협상 후에 서버에서 발급하는 SecurityContextToken의 수명을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="3139f-169">`issuedCookieLifetime`: controls the lifetime of the SecurityContextTokens that are issued by the server following SPNEGO or SSL negotiation.</span></span> <span data-ttu-id="3139f-170">서버는 이 기간 동안 SecurityContextToken을 캐시합니다.</span><span class="sxs-lookup"><span data-stu-id="3139f-170">The server caches the SecurityContextTokens for this period of time.</span></span>  
  
-   <span data-ttu-id="3139f-171">`maxPendingSessions`: 서버에서 설정되었지만 응용 프로그램 메시지가 처리되지 않은 보안 대화의 최대 개수를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="3139f-171">`maxPendingSessions`: controls the maximum number of secure conversations that are established at the server but for which no application messages have been processed.</span></span> <span data-ttu-id="3139f-172">이 할당량은 클라이언트가 서비스에서 보안 대화를 설정할 수 없도록 하고 서비스에서 각 클라이언트의 상태를 유지 관리하게 하지만 사용하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3139f-172">This quota prevents clients from establishing secure conversations at the service, thereby causing the service to maintain state for each client, but never using them.</span></span>  
  
-   <span data-ttu-id="3139f-173">`inactivityTimeout`: 응용 프로그램 메시지가 수신되지 않을 때 서비스에서 보안 대화를 활성 상태로 유지하는 최대 시간을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="3139f-173">`inactivityTimeout`: controls the maximum time that the service keeps a secure conversation alive without ever receiving an application message on it.</span></span> <span data-ttu-id="3139f-174">이 할당량은 클라이언트가 서비스에서 보안 대화를 설정할 수 없도록 하고 서비스에서 각 클라이언트의 상태를 유지 관리하게 하지만 사용하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3139f-174">This quota prevents clients from establishing secure conversations at the service, thereby causing the service to maintain state for each client, but never using them.</span></span>  
  
 <span data-ttu-id="3139f-175">보안 대화 세션에서 바인딩의 `inactivityTimeout` 및 `receiveTimeout` 특성은 모두 세션 시간 제한에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3139f-175">In a secure conversation session, note that both `inactivityTimeout` and the `receiveTimeout` attributes on the binding affect session timeout.</span></span> <span data-ttu-id="3139f-176">제한 시간은 두 속성 값 중 짧은 시간으로 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="3139f-176">The shorter of the two determines when timeouts occur.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3139f-177">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3139f-177">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.LocalServiceSecuritySettingsElement>  
 <xref:System.ServiceModel.Configuration.SecurityElementBase.LocalServiceSettings%2A>  
 <xref:System.ServiceModel.Channels.SecurityBindingElement.LocalServiceSettings%2A>  
 <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="3139f-178">바인딩</span><span class="sxs-lookup"><span data-stu-id="3139f-178">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="3139f-179">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="3139f-179">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="3139f-180">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="3139f-180">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="3139f-181">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="3139f-181">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="3139f-182">방법: SecurityBindingElement를 사용 하 여 사용자 지정 바인딩을 만들려면</span><span class="sxs-lookup"><span data-stu-id="3139f-182">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [<span data-ttu-id="3139f-183">사용자 지정 바인딩 보안</span><span class="sxs-lookup"><span data-stu-id="3139f-183">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)
