---
title: "필터 선택"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 67ab5af9-b9d9-4300-b3b1-41abb5a1fd10
caps.latest.revision: "8"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e81af51be3e281faa94bcea17ff75b41341abb33
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="choosing-a-filter"></a><span data-ttu-id="b0ab3-102">필터 선택</span><span class="sxs-lookup"><span data-stu-id="b0ab3-102">Choosing a Filter</span></span>
<span data-ttu-id="b0ab3-103">라우팅 서비스를 구성할 때는 올바른 메시지 필터를 선택하고 수신하는 메시지와 정확히 일치하도록 메시지 필터를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-103">When configuring the Routing Service, it is important to select correct message filters and configure them to allow you to make exact matches against the messages you receive.</span></span> <span data-ttu-id="b0ab3-104">선택한 필터가 과도하게 광범위하거나 올바르게 구성되지 않은 경우 메시지가 잘못 라우트됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-104">If the filters you select are overly broad in their matches or are incorrectly configured, messages are routed incorrectly.</span></span> <span data-ttu-id="b0ab3-105">필터가 너무 제한적인 경우에는 일부 메시지에 유효한 경로가 제공되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-105">If the filters are too restrictive, you may not have any valid routes available for some of your messages.</span></span>  
  
## <a name="filter-types"></a><span data-ttu-id="b0ab3-106">필터 형식</span><span class="sxs-lookup"><span data-stu-id="b0ab3-106">Filter Types</span></span>  
 <span data-ttu-id="b0ab3-107">라우팅 서비스에 사용되는 필터를 선택할 때는 각 필터가 작동하는 방식뿐 아니라 들어오는 메시지의 일부로 제공되는 정보도 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-107">When selecting the filters that are used by the Routing Service, it is important that you understand how each filter works as well as what information is available as part of the incoming messages.</span></span> <span data-ttu-id="b0ab3-108">예를 들어 모든 메시지를 동일한 끝점을 통해 받는 경우 Address 및 EndpointName 필터는 유용하지 않습니다. 이는 모든 메시지가 이러한 필터와 일치하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-108">For instance, if all messages are received over the same endpoint, the Address and EndpointName filters are not useful because all messages match these filters.</span></span>  
  
### <a name="action"></a><span data-ttu-id="b0ab3-109">작업</span><span class="sxs-lookup"><span data-stu-id="b0ab3-109">Action</span></span>  
 <span data-ttu-id="b0ab3-110">Action 필터는 <xref:System.ServiceModel.Channels.MessageHeaders.Action%2A> 속성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-110">The Action filter inspects the <xref:System.ServiceModel.Channels.MessageHeaders.Action%2A> property.</span></span> <span data-ttu-id="b0ab3-111">메시지에 있는 Action 헤더의 내용이 필터 구성에 지정된 필터 데이터 값과 일치하면 이 필터는 `true`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-111">If the contents of the Action header in the message match the filter data value specified in the filter configuration, then this filter returns `true`.</span></span> <span data-ttu-id="b0ab3-112">다음 예제에서는 정의 `FilterElement` 하는 작업 필터를 사용 하 여 "http://namespace/contract/operation/" 값이 있는 action 헤더와 메시지를 일치 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-112">The following example defines a `FilterElement` that uses the Action filter to match messages with an action header that contains a value of "http://namespace/contract/operation/".</span></span>  
  
```xml  
<filter name="action1" filterType="Action" filterData="http://namespace/contract/operation/" />  
```  
  
```csharp  
ActionMessageFilter action1 = new ActionMessageFilter(new string[] { "http://namespace/contract/operation" });  
```  
  
 <span data-ttu-id="b0ab3-113">이 필터는 고유한 Action 헤더가 있는 메시지를 라우트할 때 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-113">This filter should be used when routing messages that contain a unique Action header.</span></span>  
  
### <a name="endpointaddress"></a><span data-ttu-id="b0ab3-114">EndpointAddress</span><span class="sxs-lookup"><span data-stu-id="b0ab3-114">EndpointAddress</span></span>  
 <span data-ttu-id="b0ab3-115">EndpointAddress 필터는 메시지를 수신하는 EndpointAddress를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-115">The EndpointAddress filter inspects the EndpointAddress that the message was received on.</span></span> <span data-ttu-id="b0ab3-116">메시지를 수신하는 주소가 필터 구성에 지정된 필터 주소와 정확히 일치하면 이 필터는 `true`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-116">If the address that the message arrives at exactly matches the filter address specified in the filter configuration, then this filter returns `true`.</span></span> <span data-ttu-id="b0ab3-117">다음 예제에서는 정의 `FilterElement` 하는 주소 필터에 지정 된 모든 메시지를 사용 하 여 "http://\<호스트 이름 > / vdir/s.svc/b"입니다.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-117">The following example defines a `FilterElement` that uses the Address filter to match any messages addressed to "http://\<hostname>/vdir/s.svc/b".</span></span>  
  
```xml  
<filter name="address1" filterType="EndpointAddress" filterData="http://host/vdir/s.svc/b" />  
```  
  
```csharp  
EndpointAddressMessageFilter address1 = new EndpointAddressMessageFilter(new EndpointAddress("http://host/vdir/s.svc/b"), false);  
```  
  
> [!NOTE]
>  <span data-ttu-id="b0ab3-118">주소의 호스트 이름 부분은 클라이언트에서 정규화된 도메인 이름, NetBIOS 이름, IP 주소 또는 기타 이름을 사용하는지 여부에 따라 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-118">It is important to note that the host name portion of an address can differ based on whether the client uses the fully qualified domain name, NetBIOS name, IP address, or other name.</span></span> <span data-ttu-id="b0ab3-119">여러 값이 동일한 호스트를 참조할 수 있으므로 이 비교의 기본 동작은 일치를 수행할 때 주소의 호스트 이름 부분을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-119">Because differing values can refer to the same host, the default behavior for this comparison is to not use the host name portion of the address when performing matches.</span></span>  
>   
>  <span data-ttu-id="b0ab3-120">이 동작은 라우팅 서비스를 프로그래밍 방식으로 구성할 때 비교 시 호스트 이름을 확인하도록 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-120">This behavior can be modified to allow the comparison to evaluate the host name when configuring the Routing Service programmatically.</span></span>  
  
 <span data-ttu-id="b0ab3-121">이 필터는 들어오는 메시지의 주소가 고유한 주소로 지정된 경우에 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-121">This filter should be used when the incoming messages are addressed to a unique address.</span></span>  
  
### <a name="endpointaddressprefix"></a><span data-ttu-id="b0ab3-122">EndpointAddressPrefix</span><span class="sxs-lookup"><span data-stu-id="b0ab3-122">EndpointAddressPrefix</span></span>  
 <span data-ttu-id="b0ab3-123">EndpointAddressPrefix 필터는 EndpointAddress 필터와 마찬가지로</span><span class="sxs-lookup"><span data-stu-id="b0ab3-123">The EndpointAddressPrefix filter is similar to the EndpointAddress filter.</span></span> <span data-ttu-id="b0ab3-124">메시지를 수신하는 EndpointAddress를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-124">The EndpointAddressPrefix filter inspects the EndpointAddress that the message was received on.</span></span> <span data-ttu-id="b0ab3-125">그러나 EndpointAddressPrefix 필터는 필터 구성에 지정된 값으로 시작하는 주소를 일치시켜 와일드카드 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-125">However the EndpointAddressPrefix filter acts as a wildcard by matching addresses that begin with the value specified in the filter configuration.</span></span> <span data-ttu-id="b0ab3-126">다음 예제에서는 정의 `FilterElement` EndpointAddressPrefix 필터를 사용 하 여 주소가 지정 된 모든 메시지를 일치 하 "http://\<호스트 이름 > / //<hostname>/vdir *"입니다.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-126">The following example defines a `FilterElement` that uses the EndpointAddressPrefix filter to match any messages addressed to "http://\<hostname>/vdir*".</span></span>  
  
```xml  
<filter name="prefix1" filterType="EndpointAddressPrefix" filterData="http://host/vdir" />  
```  
  
```csharp  
PrefixEndpointAddressMessageFilter prefix1 = new PrefixEndpointAddressMessageFilter(new EndpointAddress("http://host/vdir/s.svc/b"), false);  
```  
  
> [!NOTE]
>  <span data-ttu-id="b0ab3-127">주소의 호스트 이름 부분은 클라이언트에서 정규화된 도메인 이름, NetBIOS 이름, IP 주소 또는 기타 이름을 사용하는지 여부에 따라 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-127">It is important to note that the host name portion of an address can differ based on whether the client uses the fully qualified domain name, NetBIOS name, IP address, or other name.</span></span> <span data-ttu-id="b0ab3-128">여러 값이 동일한 호스트를 참조할 수 있으므로 이 비교의 기본 동작은 일치를 수행할 때 주소의 호스트 이름 부분을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-128">Because differing values can refer to the same host, the default behavior for this comparison is to not use the host name portion of the address when performing matches.</span></span>  
  
 <span data-ttu-id="b0ab3-129">이 필터는 공통 주소 접두사를 공유하는 들어오는 메시지를 라우트할 때 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-129">This filter should be used when routing incoming messages that share a common address prefix.</span></span>  
  
### <a name="and"></a><span data-ttu-id="b0ab3-130">AND</span><span class="sxs-lookup"><span data-stu-id="b0ab3-130">AND</span></span>  
 <span data-ttu-id="b0ab3-131">AND 필터는 메시지 내의 값을 직접 필터링하지 않지만 두 개의 다른 필터를 결합하여 AND 필터가 `AND`를 반환하기 전에 두 필터가 모두 메시지와 일치해야 하는 `true` 조건을 만드는 데 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-131">The AND filter does not directly filter on a value within a message, but allows you to combine two other filters to create an `AND` condition where both filters must match the message before the AND filter evaluates to `true`.</span></span> <span data-ttu-id="b0ab3-132">이렇게 하면 모든 하위 필터가 일치할 때만 일치하는 복잡한 필터를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-132">This allows you to create complex filters that only match if all the sub-filters match.</span></span> <span data-ttu-id="b0ab3-133">다음 예제에서는 Address 필터와 Action 필터를 정의한 다음 이 두 필터를 기준으로 메시지를 평가하는 AND 필터를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-133">The following example defines an address filter and an action filter, and then defines an AND filter that evaluates a message against both the address and action filters.</span></span> <span data-ttu-id="b0ab3-134">Address 필터와 Action 필터가 둘 다 일치하면 AND 필터가 `true`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-134">If both the address and the action filters match, then the AND filter returns `true`.</span></span>  
  
```xml  
<filter name="address1" filterType="AddressPrefix" filterData="http://host/vdir"/>  
<filter name="action1" filterType="Action" filterData="http://namespace/contract/operation/"/>  
<filter name="and1" filterType="And" filter1="address1" filter2="action1" />  
```  
  
```csharp  
EndpointAddressMessageFilter address1 = new EndpointAddressMessageFilter(new EndpointAddress("http://host/vdir/s.svc/b"), false);  
ActionMessageFilter action1 = new ActionMessageFilter(new string[] { "http://namespace/contract/operation" });  
StrictAndMessageFilter and1=new StrictAndMessageFilter(address1, action1);  
```  
  
 <span data-ttu-id="b0ab3-135">이 필터는 여러 필터의 논리를 결합하여 일치를 수행해야 하는 시기를 결정해야 하는 경우에 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-135">This filter should be used when you must combine the logic from multiple filters to determine when a match should be made.</span></span> <span data-ttu-id="b0ab3-136">예를 들어 특정 주소로 동작과 메시지의 특정 조합만 수신해야 하는 대상이 여러 개 있는 경우 AND 필터를 사용하여 필요한 Action 필터와 Address 필터를 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-136">For example, if you have multiple destinations that must receive only certain combinations of actions and messages to particular addresses, you can use an AND filter to combine the necessary Action and Address filters.</span></span>  
  
### <a name="custom"></a><span data-ttu-id="b0ab3-137">사용자 지정</span><span class="sxs-lookup"><span data-stu-id="b0ab3-137">Custom</span></span>  
 <span data-ttu-id="b0ab3-138">포함 된 어셈블리의 형식을 포함 하는 customType 값을 제공 해야 사용자 지정 필터 종류를 선택할 때는 **MessageFilter** 이 필터에 사용할 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-138">When selecting the Custom filter type, you must provide a customType value that contains the type of the assembly that contains the **MessageFilter** implementation to be used for this filter.</span></span> <span data-ttu-id="b0ab3-139">또한 filterData에는 사용자 지정 필터가 메시지를 평가할 때 필요할 수 있는 값이 들어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-139">Additionally, filterData must contain any values that the custom filter may require in its evaluation of messages.</span></span> <span data-ttu-id="b0ab3-140">다음 예제에서는 `FilterElement` MessageFilter 구현을 사용하는 `CustomAssembly.MyCustomMsgFilter`를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-140">The following example defines a `FilterElement` that uses the `CustomAssembly.MyCustomMsgFilter` MessageFilter implementation.</span></span>  
  
```xml  
<filter name="custom1" filterType="Custom" customType="CustomAssembly.MyCustomMsgFilter, CustomAssembly" filterData="Custom Data" />  
```  
  
```csharp  
MyCustomMsgFilter custom1=new MyCustomMsgFilter("Custom Data");  
```  
  
 <span data-ttu-id="b0ab3-141">와 함께 제공 된 필터에 의해 적용 되지 않는 메시지에 대해 사용자 지정 일치 논리를 수행 해야 하는 경우 [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)]를 구현 하는 사용자 지정 필터를 만들어야 합니다는 **MessageFilter** 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-141">If you need to perform custom matching logic against a message that is not covered by the filters provided with [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)], you must create a custom filter that is an implementation of the **MessageFilter** class.</span></span> <span data-ttu-id="b0ab3-142">예를 들어 들어오는 메시지의 필드를 필터에 구성으로 제공된 알려진 값의 목록과 비교하거나 특정 메시지 요소를 해시한 다음 해당 값을 검사하여 필터가 `true`를 반환해야 하는지 아니면 `false`를 반환해야 하는지 여부를 확인하는 사용자 지정 필터를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-142">For example, you might create a custom filter that compares a field in the incoming message against a list of known values given to the filter as configuration, or that hashes a particular message element and then examines that value to determine whether the filter should return `true` or `false`.</span></span>  
  
### <a name="endpointname"></a><span data-ttu-id="b0ab3-143">EndpointName</span><span class="sxs-lookup"><span data-stu-id="b0ab3-143">EndpointName</span></span>  
 <span data-ttu-id="b0ab3-144">EndpointName 필터는 메시지를 수신한 끝점의 이름을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-144">The EndpointName filter inspects the name of the endpoint that received the message.</span></span> <span data-ttu-id="b0ab3-145">다음 예제에서는 정의 `FilterElement` "SvcEndpoint"에서 받은 메시지를 라우팅하는 데 EndpointName 필터를 사용 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-145">The following example defines a `FilterElement` that uses the EndpointName filter to route messages received on the "SvcEndpoint".</span></span>  
  
```xml  
<filter name="name1" filterType="Endpoint" filterData="SvcEndpoint" />  
```  
  
```csharp  
EndpointNameMessageFilter name1 = new EndpointNameMessageFilter("SvcEndpoint");  
```  
  
 <span data-ttu-id="b0ab3-146">이 필터는 라우팅 서비스가 둘 이상의 명명된 서비스 끝점을 노출하는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-146">This filter is useful when the Routing Service exposes more than one named service endpoint.</span></span> <span data-ttu-id="b0ab3-147">예를 들어 라우팅 서비스가 메시지를 받을 때 사용하는 두 개의 끝점을 노출할 수 있습니다. 이러한 두 끝점은 하나는 메시지를 실시간으로 처리해야 하는 우수 고객용이고 다른 하나는 시간이 중요하지 않은 메시지를 받기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-147">For example, you might expose two endpoints that the Routing Service uses to receive messages; one is used by priority customers who require real-time processing of their messages, while the other endpoint receives messages that are not time sensitive.</span></span>  
  
 <span data-ttu-id="b0ab3-148">일반적으로 전체 주소 일치를 사용하여 메시지가 수신된 끝점을 확인할 수 있지만 끝점 이름을 대신 사용하면, 특히 끝점 이름이 필수 특성인 구성 파일을 사용하여 라우팅 서비스를 구성하는 경우 이 작업을 더 쉽고 빠르게 수행할 수 있고 오류가 발생할 가능성도 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-148">While you can often use full address matching to determine which endpoint a message was received on, using the defined endpoint name instead is a convenient shortcut that is often less error prone, especially when configuring a Routing Service using a configuration file (where endpoint names are a required attribute).</span></span>  
  
### <a name="matchall"></a><span data-ttu-id="b0ab3-149">MatchAll</span><span class="sxs-lookup"><span data-stu-id="b0ab3-149">MatchAll</span></span>  
 <span data-ttu-id="b0ab3-150">MatchAll 필터는 수신되는 모든 메시지를 일치시킵니다.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-150">The MatchAll filter matches any received message.</span></span> <span data-ttu-id="b0ab3-151">이 필터는 수신되는 모든 메시지의 복사본을 저장하는 로깅 서비스와 같이 수신되는 모든 메시지를 항상 특정 끝점에 라우트해야 하는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-151">It is useful if you must always route all received messages to a specific endpoint, such as a logging service that stores a copy of all received messages.</span></span> <span data-ttu-id="b0ab3-152">다음 예제에서는 MatchAll 필터를 사용하는 `FilterElement`를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-152">The following example defines a `FilterElement` that uses the MatchAll filter.</span></span>  
  
```xml  
<filter name="matchAll1" filterType="MatchAll" />  
```  
  
```csharp  
MatchAllMessageFilter matchAll1 = new MatchAllMessageFilter();  
```  
  
### <a name="xpath"></a><span data-ttu-id="b0ab3-153">XPath</span><span class="sxs-lookup"><span data-stu-id="b0ab3-153">XPath</span></span>  
 <span data-ttu-id="b0ab3-154">XPath 필터를 사용하면 메시지 내의 특정 요소를 검사하는 데 사용되는 XPath 쿼리를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-154">The XPath filter allows you to specify an XPath query that is used to inspect a specific element within the message.</span></span> <span data-ttu-id="b0ab3-155">XPath 필터링은 메시지 내의 XML 주소 지정 가능 항목을 직접 검사하는 데 사용할 수 있는 강력한 필터링 옵션이지만 수신하는 메시지의 구조를 잘 알고 있어야 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-155">XPath filtering is a powerful filtering option that allows you to directly inspect any XML addressable entry within the message; however it requires that you have specific knowledge of the structure of the messages that you are receiving.</span></span> <span data-ttu-id="b0ab3-156">다음 예제에서는 정의 `FilterElement` XPath 필터를 사용 하 여 "ns" 네임 스페이스 접두사에 의해 참조 되는 네임 스페이스 내의 "element" 이라는 요소에 대 한 메시지를 검사 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-156">The following example defines a `FilterElement` that uses the XPath filter to inspect the message for an element named "element" within the namespace referenced by the "ns" namespace prefix.</span></span>  
  
```xml  
<filter name="xpath1" filterType="XPath" filterData="//ns:element" />  
```  
  
```csharp  
XPathMessageFilter xpath1=new XPathMessageFilter("//ns:element");  
```  
  
 <span data-ttu-id="b0ab3-157">이 필터는 수신하는 메시지에 특정 값이 포함되어 있다는 것을 알고 있는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-157">This filter is useful if you know that the messages you are receiving contain a specific value.</span></span> <span data-ttu-id="b0ab3-158">예를 들어 동일한 서비스의 두 버전을 호스팅하는 경우 더 새 버전의 서비스로 주소가 지정된 메시지에 고유한 사용자 지정 헤더 값이 포함되어 있다는 것을 알고 있으면 XPath를 사용하여 이 헤더를 찾아서 이 헤더에 있는 값을 파일 구성에 제공된 다른 값과 비교하여 필터가 일치하는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-158">For example, if you are hosting two versions of the same service and you know that messages addressed to the newer version of the service contain a unique value in a custom header, you can create a filter that uses XPath to navigate to this header and compares the value present in the header to another given in the filter configuration to determine if the filter matches.</span></span>  
  
 <span data-ttu-id="b0ab3-159">XPath 쿼리에는 종종 길거나 복잡한 문자열 값인 고유한 네임스페이스가 포함되어 있기 때문에 XPath 필터를 사용하면 네임스페이스 테이블을 통해 네임스페이스에 대한 고유한 접두사를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-159">Because XPath queries often contain unique namespaces, which are often lengthy or complex string values, the XPath filter allows you to use the namespace table to define unique prefixes for your namespaces.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="b0ab3-160">네임 스페이스 테이블 참조 [메시지 필터](../../../../docs/framework/wcf/feature-details/message-filters.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-160"> the namespace table, see [Message Filters](../../../../docs/framework/wcf/feature-details/message-filters.md).</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="b0ab3-161">XPath 쿼리를 디자인, 참조 [XPath 구문을](http://go.microsoft.com/fwlink/?LinkId=164592)합니다.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-161"> designing XPath queries, see [XPath Syntax](http://go.microsoft.com/fwlink/?LinkId=164592).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0ab3-162">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b0ab3-162">See Also</span></span>  
 [<span data-ttu-id="b0ab3-163">메시지 필터</span><span class="sxs-lookup"><span data-stu-id="b0ab3-163">Message Filters</span></span>](../../../../docs/framework/wcf/feature-details/message-filters.md)  
 [<span data-ttu-id="b0ab3-164">방법: 필터 사용</span><span class="sxs-lookup"><span data-stu-id="b0ab3-164">How To: Use Filters</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-filters.md)
