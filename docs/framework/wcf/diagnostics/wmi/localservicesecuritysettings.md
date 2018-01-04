---
title: LocalServiceSecuritySettings
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 490aa0e5-5242-4f8d-b505-5ec6287633b4
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: f4cc5d0676ef397f67bd9d16b2b19c6f3ee2d57e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="localservicesecuritysettings"></a><span data-ttu-id="538d2-102">LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="538d2-102">LocalServiceSecuritySettings</span></span>
<span data-ttu-id="538d2-103">LocalServiceSecuritySettings</span><span class="sxs-lookup"><span data-stu-id="538d2-103">LocalServiceSecuritySettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="538d2-104">구문</span><span class="sxs-lookup"><span data-stu-id="538d2-104">Syntax</span></span>  
  
```  
class LocalServiceSecuritySettings  
{  
  boolean DetectReplays;  
  datetime InactivityTimeout;  
  datetime IssuedCookieLifetime;  
  sint32 MaxCachedCookies;  
  datetime MaxClockSkew;  
  sint32 MaxPendingSessions;  
  sint32 MaxStatefulNegotiations;  
  datetime NegotiationTimeout;  
  boolean ReconnectTransportOnFailure;  
  sint32 ReplayCacheSize;  
  datetime ReplayWindow;  
  datetime SessionKeyRenewalInterval;  
  datetime SessionKeyRolloverInterval;  
  datetime TimestampValidityDuration;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="538d2-105">메서드</span><span class="sxs-lookup"><span data-stu-id="538d2-105">Methods</span></span>  
 <span data-ttu-id="538d2-106">LocalServiceSecuritySettings 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="538d2-106">The LocalServiceSecuritySettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="538d2-107">속성</span><span class="sxs-lookup"><span data-stu-id="538d2-107">Properties</span></span>  
 <span data-ttu-id="538d2-108">LocalServiceSecuritySettings 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="538d2-108">The LocalServiceSecuritySettings class has the following properties:</span></span>  
  
### <a name="detectreplays"></a><span data-ttu-id="538d2-109">DetectReplays</span><span class="sxs-lookup"><span data-stu-id="538d2-109">DetectReplays</span></span>  
 <span data-ttu-id="538d2-110">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="538d2-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="538d2-111">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="538d2-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="538d2-112">채널에 대한 재생 공격이 검색되어 자동으로 처리되는지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="538d2-112">A Boolean value that specifies whether replay attacks against the channel are detected and dealt with automatically.</span></span>  
  
### <a name="inactivitytimeout"></a><span data-ttu-id="538d2-113">InactivityTimeout</span><span class="sxs-lookup"><span data-stu-id="538d2-113">InactivityTimeout</span></span>  
 <span data-ttu-id="538d2-114">데이터 형식: datetime</span><span class="sxs-lookup"><span data-stu-id="538d2-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="538d2-115">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="538d2-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="538d2-116">서비스가 지원하는 보류 중인 보안 세션의 최대 수입니다.</span><span class="sxs-lookup"><span data-stu-id="538d2-116">The maximum number of pending security sessions that the service supports.</span></span>  
  
### <a name="issuedcookielifetime"></a><span data-ttu-id="538d2-117">IssuedCookieLifetime</span><span class="sxs-lookup"><span data-stu-id="538d2-117">IssuedCookieLifetime</span></span>  
 <span data-ttu-id="538d2-118">데이터 형식: datetime</span><span class="sxs-lookup"><span data-stu-id="538d2-118">Data type: datetime</span></span>  
  
 <span data-ttu-id="538d2-119">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="538d2-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="538d2-120">모든 새 보안 쿠키에 발급된 수명을 지정하는 TimeSpan입니다.</span><span class="sxs-lookup"><span data-stu-id="538d2-120">A TimeSpan that specifies the lifetime issued to all new security cookies.</span></span>  
  
### <a name="maxcachedcookies"></a><span data-ttu-id="538d2-121">MaxCachedCookies</span><span class="sxs-lookup"><span data-stu-id="538d2-121">MaxCachedCookies</span></span>  
 <span data-ttu-id="538d2-122">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="538d2-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="538d2-123">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="538d2-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="538d2-124">캐시될 수 있는 최대 쿠키 수입니다.</span><span class="sxs-lookup"><span data-stu-id="538d2-124">The maximum number of cookies that can be cached.</span></span>  
  
### <a name="maxclockskew"></a><span data-ttu-id="538d2-125">MaxClockSkew</span><span class="sxs-lookup"><span data-stu-id="538d2-125">MaxClockSkew</span></span>  
 <span data-ttu-id="538d2-126">데이터 형식: datetime</span><span class="sxs-lookup"><span data-stu-id="538d2-126">Data type: datetime</span></span>  
  
 <span data-ttu-id="538d2-127">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="538d2-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="538d2-128">통신하는 두 상대방의 시스템 시계 사이의 최대 시간 차이를 지정하는 TimeSpan입니다.</span><span class="sxs-lookup"><span data-stu-id="538d2-128">A TimeSpan that specifies the maximum time difference between the system clocks of the two communicating parties.</span></span>  
  
### <a name="maxpendingsessions"></a><span data-ttu-id="538d2-129">MaxPendingSessions</span><span class="sxs-lookup"><span data-stu-id="538d2-129">MaxPendingSessions</span></span>  
 <span data-ttu-id="538d2-130">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="538d2-130">Data type: sint32</span></span>  
  
 <span data-ttu-id="538d2-131">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="538d2-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="538d2-132">서비스에서 보류 중인 최대 연결 수입니다.</span><span class="sxs-lookup"><span data-stu-id="538d2-132">The maximum number of pending connections on the service.</span></span>  
  
### <a name="maxstatefulnegotiations"></a><span data-ttu-id="538d2-133">MaxStatefulNegotiations</span><span class="sxs-lookup"><span data-stu-id="538d2-133">MaxStatefulNegotiations</span></span>  
 <span data-ttu-id="538d2-134">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="538d2-134">Data type: sint32</span></span>  
  
 <span data-ttu-id="538d2-135">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="538d2-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="538d2-136">동시에 활성화될 수 있는 보안 협상의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="538d2-136">The number of security negotiations that can be active concurrently.</span></span>  
  
### <a name="negotiationtimeout"></a><span data-ttu-id="538d2-137">NegotiationTimeout</span><span class="sxs-lookup"><span data-stu-id="538d2-137">NegotiationTimeout</span></span>  
 <span data-ttu-id="538d2-138">데이터 형식: datetime</span><span class="sxs-lookup"><span data-stu-id="538d2-138">Data type: datetime</span></span>  
  
 <span data-ttu-id="538d2-139">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="538d2-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="538d2-140">서버와 클라이언트 간 보안 협상 단계에 대한 최대 기간을 지정하는 TimeSpan입니다.</span><span class="sxs-lookup"><span data-stu-id="538d2-140">A TimeSpan that specifies the maximum duration for the security negotiation phase between server and client.</span></span>  
  
### <a name="reconnecttransportonfailure"></a><span data-ttu-id="538d2-141">ReconnectTransportOnFailure</span><span class="sxs-lookup"><span data-stu-id="538d2-141">ReconnectTransportOnFailure</span></span>  
 <span data-ttu-id="538d2-142">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="538d2-142">Data type: boolean</span></span>  
  
 <span data-ttu-id="538d2-143">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="538d2-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="538d2-144">WS-Reliable Messaging을 사용하는 연결에서 전송 실패 후 다시 연결을 시도할지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="538d2-144">A Boolean value that specifies whether connections using WS-Reliable messaging attempt to reconnect after transport failures.</span></span>  
  
### <a name="replaycachesize"></a><span data-ttu-id="538d2-145">ReplayCacheSize</span><span class="sxs-lookup"><span data-stu-id="538d2-145">ReplayCacheSize</span></span>  
 <span data-ttu-id="538d2-146">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="538d2-146">Data type: sint32</span></span>  
  
 <span data-ttu-id="538d2-147">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="538d2-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="538d2-148">재생 검색에 사용되는 캐시된 nonces 수입니다.</span><span class="sxs-lookup"><span data-stu-id="538d2-148">The number of cached nonces used for replay detection.</span></span>  
  
### <a name="replaywindow"></a><span data-ttu-id="538d2-149">ReplayWindow</span><span class="sxs-lookup"><span data-stu-id="538d2-149">ReplayWindow</span></span>  
 <span data-ttu-id="538d2-150">데이터 형식: datetime</span><span class="sxs-lookup"><span data-stu-id="538d2-150">Data type: datetime</span></span>  
  
 <span data-ttu-id="538d2-151">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="538d2-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="538d2-152">개별 메시지 nonce를 사용할 수 있는 기간을 지정하는 TimeSpan입니다.</span><span class="sxs-lookup"><span data-stu-id="538d2-152">A TimeSpan that specifies the duration in which individual message nonces are valid.</span></span>  
  
### <a name="sessionkeyrenewalinterval"></a><span data-ttu-id="538d2-153">SessionKeyRenewalInterval</span><span class="sxs-lookup"><span data-stu-id="538d2-153">SessionKeyRenewalInterval</span></span>  
 <span data-ttu-id="538d2-154">데이터 형식: datetime</span><span class="sxs-lookup"><span data-stu-id="538d2-154">Data type: datetime</span></span>  
  
 <span data-ttu-id="538d2-155">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="538d2-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="538d2-156">해당 기간이 지나면 개시자가 보안 세션에 대한 키를 갱신할 수 있는 기간을 지정하는 TimeSpan입니다.</span><span class="sxs-lookup"><span data-stu-id="538d2-156">A TimeSpan that specifies the duration after which the initiator renews the key for the security session.</span></span>  
  
### <a name="sessionkeyrolloverinterval"></a><span data-ttu-id="538d2-157">SessionKeyRolloverInterval</span><span class="sxs-lookup"><span data-stu-id="538d2-157">SessionKeyRolloverInterval</span></span>  
 <span data-ttu-id="538d2-158">데이터 형식: datetime</span><span class="sxs-lookup"><span data-stu-id="538d2-158">Data type: datetime</span></span>  
  
 <span data-ttu-id="538d2-159">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="538d2-159">Access type: Read-only</span></span>  
  
 <span data-ttu-id="538d2-160">키 갱신 중에 들어오는 메시지에서 이전 세션 키를 사용할 수 있는 시간 간격을 지정하는 TimeSpan입니다.</span><span class="sxs-lookup"><span data-stu-id="538d2-160">A TimeSpan that specifies the time interval a previous session key is valid on incoming messages during a key renewal.</span></span>  
  
### <a name="timestampvalidityduration"></a><span data-ttu-id="538d2-161">TimestampValidityDuration</span><span class="sxs-lookup"><span data-stu-id="538d2-161">TimestampValidityDuration</span></span>  
 <span data-ttu-id="538d2-162">데이터 형식: datetime</span><span class="sxs-lookup"><span data-stu-id="538d2-162">Data type: datetime</span></span>  
  
 <span data-ttu-id="538d2-163">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="538d2-163">Access type: Read-only</span></span>  
  
 <span data-ttu-id="538d2-164">타임스탬프를 사용할 수 있는 기간을 지정하는 TimeSpan입니다.</span><span class="sxs-lookup"><span data-stu-id="538d2-164">A TimeSpan that specifies the duration in which a time stamp is valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="538d2-165">요구 사항</span><span class="sxs-lookup"><span data-stu-id="538d2-165">Requirements</span></span>  
  
|<span data-ttu-id="538d2-166">MOF</span><span class="sxs-lookup"><span data-stu-id="538d2-166">MOF</span></span>|<span data-ttu-id="538d2-167">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="538d2-167">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="538d2-168">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="538d2-168">Namespace</span></span>|<span data-ttu-id="538d2-169">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="538d2-169">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="538d2-170">참고 항목</span><span class="sxs-lookup"><span data-stu-id="538d2-170">See Also</span></span>  
 <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>
