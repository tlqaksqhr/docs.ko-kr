---
title: '&lt;webMessageEncoding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 892ca485-e21a-4a44-8e40-633161ef6796
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b3b5a8ff5fdf9e3da8824e7eb9443f71613899dc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltwebmessageencodinggt"></a><span data-ttu-id="01046-102">&lt;webMessageEncoding&gt;</span><span class="sxs-lookup"><span data-stu-id="01046-102">&lt;webMessageEncoding&gt;</span></span>
<span data-ttu-id="01046-103">[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 바인딩에 사용될 경우 일반 텍스트 XML, JSON(JavaScript Object Notation) 메시지 인코딩 및 "원시" 이진 콘텐츠를 읽고 쓸 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="01046-103">Enables plain-text XML, JavaScript Object Notation (JSON) message encodings and "raw" binary content to be read and written when used in a [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] binding.</span></span>  
  
 <span data-ttu-id="01046-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="01046-104">\<system.serviceModel></span></span>  
<span data-ttu-id="01046-105">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="01046-105">\<bindings></span></span>  
<span data-ttu-id="01046-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="01046-106">\<customBinding></span></span>  
<span data-ttu-id="01046-107">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="01046-107">\<binding></span></span>  
<span data-ttu-id="01046-108">\<webMessageEncoding ></span><span class="sxs-lookup"><span data-stu-id="01046-108">\<webMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01046-109">구문</span><span class="sxs-lookup"><span data-stu-id="01046-109">Syntax</span></span>  
  
```xml  
<webMessageEncoding   
      maxReadPoolSize="Integer"  
   maxWritePoolSize="Integer"  
  
writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="01046-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="01046-110">Attributes and Elements</span></span>  
 <span data-ttu-id="01046-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="01046-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="01046-112">특성</span><span class="sxs-lookup"><span data-stu-id="01046-112">Attributes</span></span>  
  
|<span data-ttu-id="01046-113">특성</span><span class="sxs-lookup"><span data-stu-id="01046-113">Attribute</span></span>|<span data-ttu-id="01046-114">설명</span><span class="sxs-lookup"><span data-stu-id="01046-114">Description</span></span>|  
|---------------|-----------------|  
|`maxReadPoolSize`|<span data-ttu-id="01046-115">새 판독기를 할당하지 않고 동시에 읽을 수 있는 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="01046-115">The amount of messages that can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="01046-116">풀 크기가 커지면 작업 집합이 커지는 단점이 있지만 동작이 많을 경우의 시스템 안정성이 높아집니다.</span><span class="sxs-lookup"><span data-stu-id="01046-116">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="01046-117">기본값으로 각 내부 인코더(텍스트, JSON 및 "원시")에 대해 64개의 판독기가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="01046-117">The default is 64 readers for each of the inner encoders (text, JSON, and "raw").</span></span><br /><br /> <span data-ttu-id="01046-118">이 값을 늘리면 메모리 사용량이 증가하지만, 판독기를 새로 만들 필요 없이 이미 만들어진 풀의 판독기를 사용할 수 있기 때문에 인코더가 갑자기 많은 메시지가 들어오는 경우에 대비할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01046-118">Increasing this number increases memory consumption, but prepares the encoder to deal with sudden bursts of incoming messages because it is able to use readers from the pool that are already created instead of creating new ones.</span></span>|  
|`maxWritePoolSize`|<span data-ttu-id="01046-119">새 작성기를 할당하지 않고 동시에 보낼 수 있는 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="01046-119">The amount of messages that can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="01046-120">풀 크기가 커지면 작업 집합이 커지는 단점이 있지만 동작이 많을 경우의 시스템 안정성이 높아집니다.</span><span class="sxs-lookup"><span data-stu-id="01046-120">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="01046-121">기본값으로 각 내부 인코더(텍스트, JSON 및 "원시")에 대해 16개의 작성기가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="01046-121">The default is 16 writers for each of the inner encoders (text, JSON, and "raw").</span></span><br /><br /> <span data-ttu-id="01046-122">이 값을 늘리면 메모리 사용량이 증가하지만, 작성기를 새로 만들 필요 없이 풀에서 이미 만들어진 작성기를 사용할 수 있기 때문에 인코더가 갑자기 많은 메시지가 나가는 경우에 대비할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01046-122">Increasing this number increases memory consumption, but prepares the encoder to deal with sudden bursts of outgoing messages because it is able to use writers from the pool that are already created instead of creating new ones.</span></span>|  
|`writeEncoding`|<span data-ttu-id="01046-123">바인딩에서 메시지를 내보내는 데 사용되는 문자 집합 인코딩을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="01046-123">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="01046-124">올바른 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="01046-124">Valid values are:</span></span><br /><br /> <span data-ttu-id="01046-125">-UnicodeFffeTextEncoding: 유니코드 Big Endian 인코딩</span><span class="sxs-lookup"><span data-stu-id="01046-125">-   UnicodeFffeTextEncoding: Unicode Big Endian encoding.</span></span><br /><span data-ttu-id="01046-126">-Utf16TextEncoding: 유니코드 인코딩</span><span class="sxs-lookup"><span data-stu-id="01046-126">-   Utf16TextEncoding: Unicode encoding.</span></span><br /><span data-ttu-id="01046-127">-Utf8TextEncoding: 8 비트 인코딩입니다.</span><span class="sxs-lookup"><span data-stu-id="01046-127">-   Utf8TextEncoding: 8-bit encoding.</span></span><br /><br /> <span data-ttu-id="01046-128">기본값은 Utf8TextEncoding입니다.</span><span class="sxs-lookup"><span data-stu-id="01046-128">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="01046-129">이 특성은 <xref:System.Text.Encoding> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="01046-129">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="01046-130">자식 요소</span><span class="sxs-lookup"><span data-stu-id="01046-130">Child Elements</span></span>  
  
|<span data-ttu-id="01046-131">요소</span><span class="sxs-lookup"><span data-stu-id="01046-131">Element</span></span>|<span data-ttu-id="01046-132">설명</span><span class="sxs-lookup"><span data-stu-id="01046-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="01046-133">\<readerQuotas ></span><span class="sxs-lookup"><span data-stu-id="01046-133">\<readerQuotas></span></span>](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="01046-134">이 바인딩으로 구성된 끝점에서 처리할 수 있는 SOAP 메시지의 복잡성에 대한 제약 조건을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="01046-134">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="01046-135">이 요소는 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="01046-135">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="01046-136">부모 요소</span><span class="sxs-lookup"><span data-stu-id="01046-136">Parent Elements</span></span>  
  
|<span data-ttu-id="01046-137">요소</span><span class="sxs-lookup"><span data-stu-id="01046-137">Element</span></span>|<span data-ttu-id="01046-138">설명</span><span class="sxs-lookup"><span data-stu-id="01046-138">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="01046-139">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="01046-139">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="01046-140">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="01046-140">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="01046-141">설명</span><span class="sxs-lookup"><span data-stu-id="01046-141">Remarks</span></span>  
 <span data-ttu-id="01046-142">인코딩은 메시지를 바이트 시퀀스로 변형하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="01046-142">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="01046-143">디코딩은 역프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="01046-143">Decoding is the reverse process.</span></span> <span data-ttu-id="01046-144">이러한 프로세스에서는 문자 인코딩을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="01046-144">These processes require the specification of a character encoding.</span></span>  
  
 <span data-ttu-id="01046-145">`webMessageEncoding` 요소는 일반 텍스트 XML 및 JSON 인코딩과 "원시" 이진 데이터 처리를 일련의 내부 인코더에 위임하는 방식으로 동작하며</span><span class="sxs-lookup"><span data-stu-id="01046-145">The `webMessageEncoding` element works by delegating to a series of inner encoders to handle the plain-text XML and JSON encodings, and "raw" binary data.</span></span> <span data-ttu-id="01046-146">이 위임은 복합 메시지 인코더에 의해 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="01046-146">This delegation is done by a composite message encoder.</span></span>  
  
 <span data-ttu-id="01046-147">이 바인딩 요소와 요소의 복합 인코더는 `webHttpBinding` 요소에 사용되는 SOAP 메시징을 사용하지 않는 시나리오에서 인코딩을 제어하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="01046-147">This binding element and its composite encoder are used to control the encoding in scenarios that do not use SOAP messaging used by the `webHttpBinding` element.</span></span> <span data-ttu-id="01046-148">이러한 시나리오에는 POX("Plain Old XML"), REST(Representational State Transfer), RSS(Really Simple Syndication) 및 Atom 배포, AJAX(Asynchronous JavaScript and XML) 등이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01046-148">These scenarios include "Plain Old XML" (POX), Representational State Transfer (REST), Really Simple Syndication (RSS) and Atom syndication, and Asynchronous JavaScript and XML (AJAX).</span></span> <span data-ttu-id="01046-149">복합 메시지 인코더는 SOAP 또는 WS-Addressing을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="01046-149">The composite message encoder does not support SOAP or WS-Addressing.</span></span>  
  
 <span data-ttu-id="01046-150">바인딩 요소는 `writeEncoding` 특성을 사용하여 쓰기 문자 인코딩으로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01046-150">The binding element can be configured with a write character encoding by using the `writeEncoding` attribute.</span></span> <span data-ttu-id="01046-151">제공된 <xref:System.Text.Encoding> 값은 JSON 및 텍스트 XML에 대한 쓰기 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="01046-151">The supplied <xref:System.Text.Encoding> value specifies the behavior on write for the JSON and Textual XML cases.</span></span> <span data-ttu-id="01046-152">읽기의 경우 유효한 모든 메시지 인코딩 및 텍스트 인코딩이 인식됩니다.</span><span class="sxs-lookup"><span data-stu-id="01046-152">On read, any valid message encoding and text encoding is understood.</span></span>  
  
 <span data-ttu-id="01046-153">`maxReadPoolSize` 및 `maxWritePoolSize`를 사용하여 할당할 판독기 및 작성기의 최대 수를 각각 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01046-153">`maxReadPoolSize` and `maxWritePoolSize` can also be used to set the maximum number of readers and writers to be allocated respectively.</span></span> <span data-ttu-id="01046-154">기본적으로 64개의 판독기와 16개의 작성기가 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="01046-154">By default 64 readers and 16 writers are allocated.</span></span>  
  
 <span data-ttu-id="01046-155">기본 복잡성 제약 조건을 사용 하 여 설정 됩니다는 [ \<readerQuotas >](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd) DOS (서비스)의 서비스 거부를 방지 하기 위해 요소를 메시지 복잡성을 사용 하 여 끝점 처리를 계속 사용 하려면 공격 리소스입니다.</span><span class="sxs-lookup"><span data-stu-id="01046-155">Default complexity constraints are also set using the [\<readerQuotas>](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd) element to protect against a class of denial of service (DOS) attacks that attempt to use message complexity to tie up endpoint processing resources.</span></span>  
  
## <a name="example"></a><span data-ttu-id="01046-156">예</span><span class="sxs-lookup"><span data-stu-id="01046-156">Example</span></span>  
  
```xml  
<webMessageEncoding   
    maxReadPoolSize="256"  
    maxWritePoolSize="128"  
    messageVersion="None"  
    textEncoding="utf-8"   
/>  
```  
  
## <a name="see-also"></a><span data-ttu-id="01046-157">참고 항목</span><span class="sxs-lookup"><span data-stu-id="01046-157">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WebMessageEncodingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>  
 <xref:System.ServiceModel.Channels.WebMessageEncodingBindingElement>  
 [<span data-ttu-id="01046-158">메시지 인코딩</span><span class="sxs-lookup"><span data-stu-id="01046-158">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)  
 [<span data-ttu-id="01046-159">메시지 인코더 선택</span><span class="sxs-lookup"><span data-stu-id="01046-159">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 [<span data-ttu-id="01046-160">바인딩</span><span class="sxs-lookup"><span data-stu-id="01046-160">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="01046-161">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="01046-161">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="01046-162">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="01046-162">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="01046-163">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="01046-163">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
