---
title: '&lt;discoveryEndpoint&gt;'
ms.date: 03/30/2017
ms.assetid: fae2f48b-a635-4e4b-859d-a1432ac37e1c
ms.openlocfilehash: 6a352fbfced08001f76dceaff283d6bca25f56f9
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltdiscoveryendpointgt"></a><span data-ttu-id="77f64-102">&lt;discoveryEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="77f64-102">&lt;discoveryEndpoint&gt;</span></span>

<span data-ttu-id="77f64-103">이 구성 요소는 고정 검색 계약이 있는 표준 끝점을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="77f64-103">This configuration element defines a standard endpoint with a fixed discovery contract.</span></span> <span data-ttu-id="77f64-104">서비스 구성에 추가되면 검색 메시지를 수신하는 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="77f64-104">When added to the service configuration, it specifies where to listen for the discovery messages.</span></span> <span data-ttu-id="77f64-105">클라이언트 구성에 추가되면 검색 쿼리를 보내는 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="77f64-105">When added to the client configuration it specifies where to send the discovery queries.</span></span>  
  
<span data-ttu-id="77f64-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="77f64-106">\<system.serviceModel></span></span>  
<span data-ttu-id="77f64-107">\<d a r d ></span><span class="sxs-lookup"><span data-stu-id="77f64-107">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77f64-108">구문</span><span class="sxs-lookup"><span data-stu-id="77f64-108">Syntax</span></span>

```xml
<system.serviceModel>
  <standardEndpoints>
    <discoveryEndpoint>
      <standardEndpoint discoveryMode="Adhoc/Managed" 
                        discoveryVersion="WSDiscovery11/WSDiscoveryApril2005" 
                        maxResponseDelay="Timespan" 
                        name="String" />
    </discoveryEndpoint>
  </standardEndpoints>
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="77f64-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="77f64-109">Attributes and elements</span></span>

<span data-ttu-id="77f64-110">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="77f64-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="77f64-111">특성</span><span class="sxs-lookup"><span data-stu-id="77f64-111">Attributes</span></span>

| <span data-ttu-id="77f64-112">특성</span><span class="sxs-lookup"><span data-stu-id="77f64-112">Attribute</span></span>        | <span data-ttu-id="77f64-113">설명</span><span class="sxs-lookup"><span data-stu-id="77f64-113">Description</span></span> |  
| ---------------- | ----------- |  
| <span data-ttu-id="77f64-114">discoveryMode</span><span class="sxs-lookup"><span data-stu-id="77f64-114">discoveryMode</span></span>    | <span data-ttu-id="77f64-115">검색 프로토콜의 모드를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="77f64-115">A string that specifies the mode of discovery protocol.</span></span> <span data-ttu-id="77f64-116">유효한 값은 "Adhoc" 및 "Managed"입니다.</span><span class="sxs-lookup"><span data-stu-id="77f64-116">Valid values are "Adhoc" and "Managed".</span></span> <span data-ttu-id="77f64-117">관리 모드에서는 프로토콜이 검색 가능한 서비스의 리포지토리로 작동하는 검색 프록시를 사용하고,</span><span class="sxs-lookup"><span data-stu-id="77f64-117">In managed mode the protocol relies on a Discovery Proxy, which acts as a repository of Discoverable services.</span></span> <span data-ttu-id="77f64-118">애드혹 모드에서는 프로토콜이 UDP 멀티캐스트 메커니즘을 사용하여 사용 가능한 서비스를 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77f64-118">Adhoc mode requires the protocol to use UDP multicast mechanism to find available services.</span></span> <span data-ttu-id="77f64-119">속성에 대 한 자세한 내용은 참조 하십시오. <xref:System.ServiceModel.Discovery.DiscoveryEndpoint.DiscoveryMode%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="77f64-119">For more information on the property, see <xref:System.ServiceModel.Discovery.DiscoveryEndpoint.DiscoveryMode%2A>.</span></span> |  
| <span data-ttu-id="77f64-120">discoveryVersion</span><span class="sxs-lookup"><span data-stu-id="77f64-120">discoveryVersion</span></span> | <span data-ttu-id="77f64-121">WS-Discovery 프로토콜의 두 버전 중 하나를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="77f64-121">A string that specifies one of the two versions of WS-Discovery protocol.</span></span> <span data-ttu-id="77f64-122">유효한 값은 WSDiscovery11 및 WSDiscoveryApril2005입니다.</span><span class="sxs-lookup"><span data-stu-id="77f64-122">Valid values are WSDiscovery11 and WSDiscoveryApril2005.</span></span> <span data-ttu-id="77f64-123">이 값은 <xref:System.ServiceModel.Discovery.DiscoveryVersion> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="77f64-123">This value is of type <xref:System.ServiceModel.Discovery.DiscoveryVersion>.</span></span> |  
| <span data-ttu-id="77f64-124">maxResponseDelay</span><span class="sxs-lookup"><span data-stu-id="77f64-124">maxResponseDelay</span></span> | <span data-ttu-id="77f64-125">검색 프로토콜이 Probe Match 또는 Resolve Match 같은 특정 메시지가 전송될 때까지 대기하는 최대 지연 값을 지정하는 Timespan 값입니다.</span><span class="sxs-lookup"><span data-stu-id="77f64-125">A Timespan value that specifies the maximum value for the delay the Discovery protocol will wait before sending certain messages such as Probe Match or Resolve Match.</span></span><br /><br /> <span data-ttu-id="77f64-126">모든 Probe Match가 동시에 전송되는 경우 네트워크 폭주가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77f64-126">If all ProbeMatches are sent at the same time, a network storm may result.</span></span> <span data-ttu-id="77f64-127">이러한 현상이 발생하는 것을 방지하기 위해 각 Probe Match 사이에 임의의 지연 간격을 두고 Probe Match가 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="77f64-127">To prevent this from occurring, ProbeMatches are sent with a random delay between each ProbeMatch.</span></span> <span data-ttu-id="77f64-128">0에서 이 특성에 의해 설정되는 값까지의 범위 내에서 임의의 지연 간격이 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="77f64-128">The random delay is in the range of 0 to the value set by this attribute.</span></span> <span data-ttu-id="77f64-129">이 특성이 0으로 설정되면 Probe Match 메시지가 지연 간격 없이 연속하여 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="77f64-129">If this attribute is set to 0, then the ProbeMatches messages are sent in a tight loop without any delay.</span></span> <span data-ttu-id="77f64-130">그렇지 않으면 모든 Probe Match 메시지를 보내는 데 걸리는 총 시간이 maxResponseDelay를 초과하지 않는 범위 내에서 Probe Match 메시지가 약간의 임의의 지연 간격을 두고 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="77f64-130">Otherwise, the ProbeMatches messages are sent with some random delay such that the total time taken to send all ProbeMatches messages does not exceed the maxResponseDelay.</span></span> <span data-ttu-id="77f64-131">이 값은 서비스에만 관련된 것으로 클라이언트에서 사용되는 값은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="77f64-131">This value is only relevant for services, it is not used by clients.</span></span> |  
| `name`           | <span data-ttu-id="77f64-132">표준 끝점의 구성 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="77f64-132">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="77f64-133">이 이름은 서비스 끝점의 `endpointConfiguration` 특성에서 표준 끝점을 해당 구성에 연결하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="77f64-133">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span> |  
  
### <a name="child-elements"></a><span data-ttu-id="77f64-134">자식 요소</span><span class="sxs-lookup"><span data-stu-id="77f64-134">Child elements</span></span>

<span data-ttu-id="77f64-135">없음</span><span class="sxs-lookup"><span data-stu-id="77f64-135">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="77f64-136">부모 요소</span><span class="sxs-lookup"><span data-stu-id="77f64-136">Parent elements</span></span>

| <span data-ttu-id="77f64-137">요소</span><span class="sxs-lookup"><span data-stu-id="77f64-137">Element</span></span> | <span data-ttu-id="77f64-138">설명</span><span class="sxs-lookup"><span data-stu-id="77f64-138">Description</span></span> |  
| ------- | ----------- |  
| [<span data-ttu-id="77f64-139">\<d a r d ></span><span class="sxs-lookup"><span data-stu-id="77f64-139">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md) | <span data-ttu-id="77f64-140">하나 이상의 속성(주소, 바인딩, 계약)이 고정된 미리 정의된 끝점인 표준 끝점의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="77f64-140">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span> |  
  
## <a name="example"></a><span data-ttu-id="77f64-141">예제</span><span class="sxs-lookup"><span data-stu-id="77f64-141">Example</span></span>

<span data-ttu-id="77f64-142">다음 예제에서는 피어 넷 멀티캐스트 전송을 통해 검색 메시지를 수신하는 서비스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="77f64-142">The following example demonstrates a service listening on the discovery messages over a peer net multicast transport.</span></span> <span data-ttu-id="77f64-143">이 예제에서는 WS-Discovery April 2005 버전을 명시적으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="77f64-143">The example explicitly specifies WS-Discovery April 2005 version.</span></span>  
  
<span data-ttu-id="77f64-144">표준 끝점 구성이 서비스별로 정의되고 서비스 간에 공유될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="77f64-144">The standard endpoint configuration is defined per service and cannot be shared across the service.</span></span> <span data-ttu-id="77f64-145">따라서 다른 서비스에서 동일한 검색 끝점을 사용하려는 경우 해당 서비스의 섹션에 동일한 구성을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77f64-145">If another service would like to have the same discovery endpoint, the same configuration needs to be added to that service’s section.</span></span>  
  
```xml
<services>  
  <service name="CalculatorService"
           behaviorConfiguration="CalculatorServiceBehavior">
    <endpoint binding="basicHttpBinding" 
              address="calculator" 
              contract="ICalculatorService" />  
    <endpoint name="peerNetDiscovery"  
              binding="peerTcpBinding"  
              address="net.p2p://discoveryMesh/multicast"  
              kind="discoveryEndpoint"  
              endpointConfiguration="peerTcpDiscoveryEndpointConfiguration"  
              bindingConfiguration="discoveryPeerTcpBindingConfig" />      
  </service>  
</services>  
<standardEndpoints>  
  <discoveryEndpoint>  
    <standardEndpoint name="peerTcpDiscoveryEndpointConfiguration"                         
                      version="WSDiscoveryApril2005" />  
  </discoveryEndpoint>  
</standardEndpoints>  
```  
  
## <a name="see-also"></a><span data-ttu-id="77f64-146">참고자료</span><span class="sxs-lookup"><span data-stu-id="77f64-146">See also</span></span>

<xref:System.ServiceModel.Discovery.DiscoveryEndpoint>
