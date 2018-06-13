---
title: '&lt;udpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: fa291901-8340-45c6-9c44-5d9281c70bc3
ms.openlocfilehash: 1d9535f60bca101e53b678da25915ac9afb41aab
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32756217"
---
# <a name="ltudpbindinggt"></a><span data-ttu-id="73480-102">&lt;udpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="73480-102">&lt;udpBinding&gt;</span></span>
<span data-ttu-id="73480-103"><xref:System.ServiceModel.UdpBinding> 바인딩을 구성하는 데 사용되는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="73480-103">A configuration element used to configure the <xref:System.ServiceModel.UdpBinding> binding.</span></span>  
  
 <span data-ttu-id="73480-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="73480-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="73480-105">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="73480-105">\<bindings></span></span>  
<span data-ttu-id="73480-106">\<udpBinding></span><span class="sxs-lookup"><span data-stu-id="73480-106">\<udpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73480-107">구문</span><span class="sxs-lookup"><span data-stu-id="73480-107">Syntax</span></span>  
  
```xml  
<udpBinding>  
   <binding   
       closeTimeout="TimeSpan"   
       duplicateMessageHistoryLength="Integer"  
       maxBufferPoolSize="Integer"  
       maxBufferSize="Integer"       maxPendingMessagesTotalSize="Integer"  
       maxReceivedMessageSize="Integer"       maxRetransmitCount="Integer"  
       multicastInterfaceId="Integer"  
              name="string"   
       openTimeout="TimeSpan"   
       receiveTimeout="TimeSpan"  
       sendTimeout="TimeSpan"  
       textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding"  
       timeToLive="TimeSpan">  
       <readerQuotas   
            maxArrayLength="Integer"  
            maxBytesPerRead="Integer"  
            maxDepth="Integer"             maxNameTableCharCount="Integer"                maxStringContentLength="Integer" />  
   </binding>  
</basicHttpBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="73480-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="73480-108">Attributes and Elements</span></span>  
 <span data-ttu-id="73480-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="73480-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="73480-110">특성</span><span class="sxs-lookup"><span data-stu-id="73480-110">Attributes</span></span>  
  
|<span data-ttu-id="73480-111">특성</span><span class="sxs-lookup"><span data-stu-id="73480-111">Attribute</span></span>|<span data-ttu-id="73480-112">설명</span><span class="sxs-lookup"><span data-stu-id="73480-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="73480-113">닫기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="73480-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="73480-114">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73480-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="73480-115">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="73480-115">The default is 00:01:00.</span></span>|  
|`duplicateMessageHistoryLength`|<span data-ttu-id="73480-116">중복 메시지 기록 길이를 지정하는 정수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="73480-116">An integer value that specifies the duplicate message history length.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="73480-117">채널에서 메시지를 수신하는 메시지 버퍼 관리자가 사용하도록 할당된 최대 메모리를 지정하는 정수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="73480-117">An integer value that specifies the maximum amount of memory that is allocated for use by the manager of the message buffers that receive messages from the channel.</span></span> <span data-ttu-id="73480-118">기본값은 524288(0x80000)바이트입니다.</span><span class="sxs-lookup"><span data-stu-id="73480-118">The default value is 524288 (0x80000) bytes.</span></span>|  
|`maxBufferSize`|<span data-ttu-id="73480-119">이 바인딩으로 구성된 끝점에 대해 메시지가 처리되는 동안 해당 메시지를 저장하는 버퍼의 최대 크기(바이트)를 지정하는 정수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="73480-119">An integer value that specifies the maximum size, in bytes, of a buffer that stores messages while they are processed for an endpoint configured with this binding.</span></span> <span data-ttu-id="73480-120">기본값은 65,536바이트입니다.</span><span class="sxs-lookup"><span data-stu-id="73480-120">The default value is 65,536 bytes.</span></span>|  
|`maxPendingMessagesTotalSize`|<span data-ttu-id="73480-121">수신되었으나 개별 채널 인스턴스의 입력 큐에서 아직 제거되지 않은 최대 메시지 수를 지정하는 정수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="73480-121">An integer value that specifies the maximum number of messages that are received but not yet removed from the input queue for an individual channel instance.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="73480-122">이 바인딩으로 구성된 채널에서 받을 수 있는 메시지(헤더 포함)의 최대 메시지 크기(바이트)를 정의하는 양의 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="73480-122">A positive integer that defines the maximum message size, in bytes, including headers, for a message that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="73480-123">수신자에게 너무 큰 메시지를 보낸 발신자에게는 SOAP 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="73480-123">The sender receives a SOAP fault if the message is too large for the receiver.</span></span> <span data-ttu-id="73480-124">수신자는 메시지를 삭제하고 추적 로그에 이벤트 항목을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="73480-124">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="73480-125">기본값은 65,536바이트입니다.</span><span class="sxs-lookup"><span data-stu-id="73480-125">The default is 65,536 bytes.</span></span>|  
|`maxRetransmitCount`|<span data-ttu-id="73480-126">메시지를 재전송하는 최대 횟수를 지정하는 정수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="73480-126">An integer value that specifies the maximum number of retransmit messages.</span></span>|  
|`multicastInterfaceId`|<span data-ttu-id="73480-127">멀티캐스트 인터페이스 ID를 지정하는 정수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="73480-127">An integer value that specifies the multicast interface ID.</span></span>|  
|`name`|<span data-ttu-id="73480-128">바인딩의 구성 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="73480-128">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="73480-129">이 값은 바인딩의 ID로 사용되므로 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73480-129">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="73480-130">각 바인딩에는 서비스의 메타데이터에서 함께 바인딩을 고유하게 식별하는 `name` 및 `namespace` 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73480-130">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="73480-131">또한 이 이름은 동일한 형식의 바인딩 간에 고유합니다.</span><span class="sxs-lookup"><span data-stu-id="73480-131">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="73480-132">[!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)]부터는 바인딩 및 동작에 이름이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="73480-132">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="73480-133">기본 구성 및 이름이 없는 바인딩 및 동작에 대 한 자세한 내용은 참조 [단순화 된 구성](../../../../../docs/framework/wcf/simplified-configuration.md) 및 [WCF 서비스에 대 한 구성을 단순화](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="73480-133">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="73480-134">열기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="73480-134">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="73480-135">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73480-135">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="73480-136">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="73480-136">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="73480-137">받기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="73480-137">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="73480-138">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73480-138">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="73480-139">기본값은 00:10:00입니다.</span><span class="sxs-lookup"><span data-stu-id="73480-139">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="73480-140">보내기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="73480-140">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="73480-141">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73480-141">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="73480-142">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="73480-142">The default is 00:01:00.</span></span>|  
|`textEncoding`|<span data-ttu-id="73480-143">바인딩에서 메시지를 내보내는 데 사용되는 문자 집합 인코딩을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="73480-143">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="73480-144">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="73480-144">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="73480-145">-BigEndianUnicode: 유니코드 BigEndian 인코딩입니다.</span><span class="sxs-lookup"><span data-stu-id="73480-145">-   BigEndianUnicode: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="73480-146">-Unicode: 16 비트 인코딩입니다.</span><span class="sxs-lookup"><span data-stu-id="73480-146">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="73480-147">UTF8: 8 비트 인코딩</span><span class="sxs-lookup"><span data-stu-id="73480-147">-   UTF8: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="73480-148">기본값은 UTF8입니다.</span><span class="sxs-lookup"><span data-stu-id="73480-148">The default is UTF8.</span></span> <span data-ttu-id="73480-149">이 특성은 <xref:System.Text.Encoding> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="73480-149">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|`timeToLive`|<span data-ttu-id="73480-150">바인딩에 대한 TTL(Time To Live)을 지정하는 Timespan 값입니다.</span><span class="sxs-lookup"><span data-stu-id="73480-150">A timespan value that specifies the time to live for the binding.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="73480-151">자식 요소</span><span class="sxs-lookup"><span data-stu-id="73480-151">Child Elements</span></span>  
  
|<span data-ttu-id="73480-152">요소</span><span class="sxs-lookup"><span data-stu-id="73480-152">Element</span></span>|<span data-ttu-id="73480-153">설명</span><span class="sxs-lookup"><span data-stu-id="73480-153">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="73480-154">\<readerQuotas></span><span class="sxs-lookup"><span data-stu-id="73480-154">\<readerQuotas></span></span>](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="73480-155">이 바인딩으로 구성된 끝점에서 처리할 수 있는 SOAP 메시지의 복잡성에 대한 제약 조건을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="73480-155">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="73480-156">이 요소는 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="73480-156">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="73480-157">부모 요소</span><span class="sxs-lookup"><span data-stu-id="73480-157">Parent Elements</span></span>  
  
|<span data-ttu-id="73480-158">요소</span><span class="sxs-lookup"><span data-stu-id="73480-158">Element</span></span>|<span data-ttu-id="73480-159">설명</span><span class="sxs-lookup"><span data-stu-id="73480-159">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="73480-160">\<bindings></span><span class="sxs-lookup"><span data-stu-id="73480-160">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="73480-161">이 요소는 표준 및 사용자 지정 바인딩의 컬렉션을 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="73480-161">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="73480-162">설명</span><span class="sxs-lookup"><span data-stu-id="73480-162">Remarks</span></span>  
 <span data-ttu-id="73480-163">UdpBinding을 사용하면 WCF 서비스가 UDP 전송을 통해 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73480-163">The UdpBinding allows WCF services to communicate over the UDP transport.</span></span> <span data-ttu-id="73480-164">여기서는 클라이언트는 서비스에 메시지를 보냅니다 응답을 기대 하지 다시 "fire and forget" 메시지 교환에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73480-164">It allows for "fire and forget" message exchanges where a client sends a message to a service and expects no response back.</span></span>  
  
## <a name="example"></a><span data-ttu-id="73480-165">예제</span><span class="sxs-lookup"><span data-stu-id="73480-165">Example</span></span>  
 <span data-ttu-id="73480-166">다음 예제에서는 <<xref:System.ServiceModel.UdpBinding>> 요소를 사용하여 `udpBinding`을 구성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="73480-166">The following example shows how to configure the <xref:System.ServiceModel.UdpBinding> using the <`udpBinding`> element.</span></span>  
  
```xml  
<udpBinding>  
        <binding  closeTimeout="00:10:00"  
                   duplicateMessageHistoryLength="100"  
                   maxBufferPoolSize="100"  
                   maxPendingMessagesTotalSize="100000"  
                   maxReceivedMessageSize="65536"  
                    maxRetransmitCount="10"  
                   multicastInterfaceId="00000"  
                   name="myUdpBinding"  
                   openTimeout="00:10:00"  
                   receiveTimeout="00:10:00"  
                   sendTimeout="00:10:00"  
                   textEncoding="utf-8"  
                   timeToLive="00:10:00"  
          <readerQuotas/>   
        </binding>  
      </udpBinding>  
```  
  
## <a name="see-also"></a><span data-ttu-id="73480-167">참고 항목</span><span class="sxs-lookup"><span data-stu-id="73480-167">See Also</span></span>  
 <xref:System.ServiceModel.Channels.Binding>  
 <xref:System.ServiceModel.Channels.BindingElement>  
 <xref:System.ServiceModel.BasicHttpBinding>  
 <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>  
 [<span data-ttu-id="73480-168">바인딩</span><span class="sxs-lookup"><span data-stu-id="73480-168">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="73480-169">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="73480-169">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="73480-170">바인딩을 사용 하 여 Windows Communication Foundation 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="73480-170">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="73480-171">\<binding></span><span class="sxs-lookup"><span data-stu-id="73480-171">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
