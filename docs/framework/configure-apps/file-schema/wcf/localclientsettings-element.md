---
title: '&lt;localClientSettings&gt; 요소'
ms.date: 03/30/2017
ms.assetid: 4680ace5-f4e1-4fcb-b9d8-a4a4af5cd7ae
ms.openlocfilehash: a960a18c472bed64609947220dffedf9ec90945c
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltlocalclientsettingsgt-element"></a><span data-ttu-id="c39bd-102">&lt;localClientSettings&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="c39bd-102">&lt;localClientSettings&gt; element</span></span>
<span data-ttu-id="c39bd-103">이 바인딩에 대한 로컬 클라이언트의 보안 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c39bd-103">Specifies the security settings of a local client for this binding.</span></span>  
  
 <span data-ttu-id="c39bd-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="c39bd-104">\<system.serviceModel></span></span>  
<span data-ttu-id="c39bd-105">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="c39bd-105">\<bindings></span></span>  
<span data-ttu-id="c39bd-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="c39bd-106">\<customBinding></span></span>  
<span data-ttu-id="c39bd-107">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="c39bd-107">\<binding></span></span>  
<span data-ttu-id="c39bd-108">\<security></span><span class="sxs-lookup"><span data-stu-id="c39bd-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c39bd-109">구문</span><span class="sxs-lookup"><span data-stu-id="c39bd-109">Syntax</span></span>  
  
```xml  
<security>  
   <localClientSettings cacheCookies="Boolean"  
      cookieRenewalThresholdPercentage="Integer"  
      detectReplays="Boolean"  
      maxClockSkew="TimeSpan"  
      maxCookieCachingTime="TimeSpan"  
      reconnectTransportOnFailure="Boolean"  
      replayCacheSize="Integer"  
      replayWindow="TimeSpan"  
      sessionKeyRenewalInterval="TimeSpan"  
      sessionKeyRolloverInterval="TimeSpan"  
      timestampValidityDuration="TimeSpan" />  
</security>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c39bd-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c39bd-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c39bd-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c39bd-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c39bd-112">특성</span><span class="sxs-lookup"><span data-stu-id="c39bd-112">Attributes</span></span>  
  
|<span data-ttu-id="c39bd-113">특성</span><span class="sxs-lookup"><span data-stu-id="c39bd-113">Attribute</span></span>|<span data-ttu-id="c39bd-114">설명</span><span class="sxs-lookup"><span data-stu-id="c39bd-114">Description</span></span>|  
|---------------|-----------------|  
|`cacheCookies`|<span data-ttu-id="c39bd-115">쿠키 캐싱 활성화 여부를 나타내는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c39bd-115">A Boolean value that specifies whether cookie caching is enabled.</span></span> <span data-ttu-id="c39bd-116">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="c39bd-116">The default is `false`.</span></span>|  
|`cookieRenewalThresholdPercentage`|<span data-ttu-id="c39bd-117">갱신할 수 있는 최대 쿠키 백분율을 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="c39bd-117">An integer that specifies the maximum percentage of cookies that can be renewed.</span></span> <span data-ttu-id="c39bd-118">이 값은 0 이상 100 이하여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c39bd-118">This value should be between 0 and 100 inclusively.</span></span> <span data-ttu-id="c39bd-119">기본값은 90입니다.</span><span class="sxs-lookup"><span data-stu-id="c39bd-119">The default is 90.</span></span>|  
|`detectReplays`|<span data-ttu-id="c39bd-120">채널에 대한 재생 공격이 검색되어 자동으로 처리되는지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c39bd-120">A Boolean value that specifies whether replay attacks against the channel are detected and dealt with automatically.</span></span> <span data-ttu-id="c39bd-121">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="c39bd-121">The default is `false`.</span></span>|  
|`maxClockSkew`|<span data-ttu-id="c39bd-122">서로 통신하는 양쪽의 시스템 클록 간의 최대 시간 차이를 지정하는 <xref:System.TimeSpan>입니다.</span><span class="sxs-lookup"><span data-stu-id="c39bd-122">A <xref:System.TimeSpan> that specifies the maximum time difference between the system clocks of the two communicating parties.</span></span> <span data-ttu-id="c39bd-123">기본값은 "00:05:00"입니다.</span><span class="sxs-lookup"><span data-stu-id="c39bd-123">The default value is "00:05:00".</span></span><br /><br /> <span data-ttu-id="c39bd-124">이 값을 기본값으로 설정하면 수신자는 메시지를 받은 시간을 기준으로 보낸 시간 타임스탬프가 전후 5분 이내인 메시지를 수신 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="c39bd-124">When this value is set to the default, the receiver accepts messages with send-time time stamps up to 5 minutes later or earlier than the time the message was received.</span></span> <span data-ttu-id="c39bd-125">보낸 시간 테스트를 통과하지 못한 메시지는 거부됩니다.</span><span class="sxs-lookup"><span data-stu-id="c39bd-125">Messages that do not pass the send-time test are rejected.</span></span> <span data-ttu-id="c39bd-126">이 설정은 `replayWindow` 특성과 함께 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c39bd-126">This setting is used in conjunction with the `replayWindow` attribute.</span></span>|  
|`maxCookieCachingTime`|<span data-ttu-id="c39bd-127">쿠키의 최대 수명을 지정하는 <xref:System.TimeSpan>입니다.</span><span class="sxs-lookup"><span data-stu-id="c39bd-127">A <xref:System.TimeSpan> that specifies the maximum lifetime of cookies.</span></span> <span data-ttu-id="c39bd-128">기본값은 "10675199.02:48:05.4775807"입니다.</span><span class="sxs-lookup"><span data-stu-id="c39bd-128">The default value is "10675199.02:48:05.4775807".</span></span>|  
|`reconnectTransportOnFailure`|<span data-ttu-id="c39bd-129">WS-Reliable Messaging을 사용하는 연결에서 전송 실패 후 다시 연결을 시도할지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c39bd-129">A Boolean value that specifies whether connections using WS-Reliable messaging will attempt to reconnect after transport failures.</span></span> <span data-ttu-id="c39bd-130">기본값은 `true`로, 다시 연결이 무한히 시도된다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="c39bd-130">The default is `true`, which means that infinite attempts to reconnect are attempted.</span></span> <span data-ttu-id="c39bd-131">이 순환은 비활성 제한 시간이 초과되어야만 중단되며, 이 경우 채널에서 다시 연결할 수 없으면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="c39bd-131">The cycle is broken by the inactivity time-out, which causes the channel to throw an exception when it cannot be reconnected.</span></span>|  
|`replayCacheSize`|<span data-ttu-id="c39bd-132">재생 검색에 사용되는 캐시된 Nonce의 수를 지정하는 양의 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="c39bd-132">A positive integer that specifies the number of cached nonces used for replay detection.</span></span> <span data-ttu-id="c39bd-133">이 제한을 초과하면 가장 오래된 Nonce가 제거되고 새 메시지에 대해 새로운 Nonce가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="c39bd-133">If this limit is exceeded, the oldest nonce is removed and a new nonce is created for the new message.</span></span> <span data-ttu-id="c39bd-134">기본값은 500000입니다.</span><span class="sxs-lookup"><span data-stu-id="c39bd-134">The default value is 500000.</span></span>|  
|`replayWindow`|<span data-ttu-id="c39bd-135">개별 메시지 Nonce의 유효 기간을 지정하는 <xref:System.TimeSpan>입니다.</span><span class="sxs-lookup"><span data-stu-id="c39bd-135">A <xref:System.TimeSpan> that specifies the duration in which individual message nonces are valid.</span></span><br /><br /> <span data-ttu-id="c39bd-136">이 속성에서 지정한 시간이 지나면 이전에 보낸 메시지와 동일한 Nonce를 갖는 메시지는 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c39bd-136">After this duration, a message sent with the same nonce as the one sent before will not be accepted.</span></span> <span data-ttu-id="c39bd-137">이 특성은 `maxClockSkew` 특성과 함께 사용되어 재생 공격을 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="c39bd-137">This attribute is used in conjunction with the `maxClockSkew` attribute to prevent replay attacks.</span></span> <span data-ttu-id="c39bd-138">메시지 재생 창이 만료된 후에 공격자가 그 메시지를 재생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c39bd-138">An attacker could replay a message after its replay window has expired.</span></span> <span data-ttu-id="c39bd-139">그러나 이 메시지는 `maxClockSkew` 테스트를 통과하지 못합니다. 해당 테스트는 메시지의 보낸 시간 타임스탬프가 메시지를 받은 시간보다 지정된 시간 이상으로 늦거나 빠르면 그 메시지를 거부합니다.</span><span class="sxs-lookup"><span data-stu-id="c39bd-139">This message, however, would fail the `maxClockSkew` test which rejects messages with send-time timestamps up to a specified time later or earlier than the time the message was received.</span></span>|  
|`sessionKeyRenewalInterval`|<span data-ttu-id="c39bd-140">개시자가 보안 세션을 위해 키를 갱신하는 시간 간격을 지정하는 <xref:System.TimeSpan>입니다.</span><span class="sxs-lookup"><span data-stu-id="c39bd-140">A <xref:System.TimeSpan> that specifies the duration after which the initiator will renew the key for the security session.</span></span> <span data-ttu-id="c39bd-141">기본값은 "10:00:00"입니다.</span><span class="sxs-lookup"><span data-stu-id="c39bd-141">The default is "10:00:00".</span></span>|  
|`sessionKeyRolloverInterval`|<span data-ttu-id="c39bd-142">키 갱신 중에 들어오는 메시지에서 이전 세션 키를 사용할 수 있는 시간 간격을 지정하는 <xref:System.TimeSpan>입니다.</span><span class="sxs-lookup"><span data-stu-id="c39bd-142">A <xref:System.TimeSpan> that specifies the time interval a previous session key is valid on incoming messages during a key renewal.</span></span> <span data-ttu-id="c39bd-143">기본값은 "00:05:00"입니다.</span><span class="sxs-lookup"><span data-stu-id="c39bd-143">The default is "00:05:00".</span></span><br /><br /> <span data-ttu-id="c39bd-144">키 갱신 중에 클라이언트와 서버는 반드시 사용 가능한 최신 키를 사용하여 메시지를 보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c39bd-144">During key renewal, the client and server must always send messages using the most current available key.</span></span> <span data-ttu-id="c39bd-145">양쪽 모두 롤오버 시간이 만료될 때까지는 이전 세션 키를 사용하여 보안되는 메시지를 수락할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c39bd-145">Both parties will accept incoming messages secured with the previous session key until the rollover time expires.</span></span>|  
|`timestampValidityDuration`|<span data-ttu-id="c39bd-146">타임스탬프의 유효 기간을 지정하는 <xref:System.TimeSpan>(양수)입니다.</span><span class="sxs-lookup"><span data-stu-id="c39bd-146">A positive <xref:System.TimeSpan> that specifies the duration in which a time stamp is valid.</span></span> <span data-ttu-id="c39bd-147">기본값은 "00:15:00"입니다.</span><span class="sxs-lookup"><span data-stu-id="c39bd-147">The default is "00:15:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c39bd-148">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c39bd-148">Child Elements</span></span>  
 <span data-ttu-id="c39bd-149">없음</span><span class="sxs-lookup"><span data-stu-id="c39bd-149">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c39bd-150">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c39bd-150">Parent Elements</span></span>  
  
|<span data-ttu-id="c39bd-151">요소</span><span class="sxs-lookup"><span data-stu-id="c39bd-151">Element</span></span>|<span data-ttu-id="c39bd-152">설명</span><span class="sxs-lookup"><span data-stu-id="c39bd-152">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c39bd-153">\<security></span><span class="sxs-lookup"><span data-stu-id="c39bd-153">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)|<span data-ttu-id="c39bd-154">사용자 지정 바인딩에 대한 보안 옵션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c39bd-154">Specifies the security options for a custom binding.</span></span>|  
|[<span data-ttu-id="c39bd-155">\<secureConversationBootstrap ></span><span class="sxs-lookup"><span data-stu-id="c39bd-155">\<secureConversationBootstrap></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)|<span data-ttu-id="c39bd-156">보안 대화 서비스 개시에 사용되는 기본값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c39bd-156">Specifies the default values used for initiating a secure conversation service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c39bd-157">설명</span><span class="sxs-lookup"><span data-stu-id="c39bd-157">Remarks</span></span>  
 <span data-ttu-id="c39bd-158">이 설정은 서비스의 보안 정책에서 파생되는 설정이 아니므로 로컬 설정에 속합니다.</span><span class="sxs-lookup"><span data-stu-id="c39bd-158">The settings are local in the sense that they are not settings derived from the security policy of the service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c39bd-159">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c39bd-159">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.LocalClientSecuritySettingsElement>  
 <xref:System.ServiceModel.Configuration.SecurityElementBase.LocalClientSettings%2A>  
 <xref:System.ServiceModel.Channels.SecurityBindingElement.LocalClientSettings%2A>  
 <xref:System.ServiceModel.Channels.LocalClientSecuritySettings>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="c39bd-160">바인딩</span><span class="sxs-lookup"><span data-stu-id="c39bd-160">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="c39bd-161">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="c39bd-161">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="c39bd-162">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="c39bd-162">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="c39bd-163">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="c39bd-163">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="c39bd-164">방법: SecurityBindingElement를 사용하여 사용자 지정 바인딩 만들기</span><span class="sxs-lookup"><span data-stu-id="c39bd-164">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [<span data-ttu-id="c39bd-165">사용자 지정 바인딩 보안</span><span class="sxs-lookup"><span data-stu-id="c39bd-165">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)
