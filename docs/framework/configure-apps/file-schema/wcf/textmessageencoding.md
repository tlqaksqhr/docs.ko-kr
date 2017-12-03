---
title: '&lt;textMessageEncoding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e6d834d0-356e-45eb-b530-bbefbb9ec3f0
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a5e506d48c067871f5921d991c54ad8fb0d1593e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="lttextmessageencodinggt"></a><span data-ttu-id="d2bd6-102">&lt;textMessageEncoding&gt;</span><span class="sxs-lookup"><span data-stu-id="d2bd6-102">&lt;textMessageEncoding&gt;</span></span>
<span data-ttu-id="d2bd6-103">텍스트 기반 XML 메시지에 사용되는 문자 인코딩 및 메시지 버전 관리를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d2bd6-103">Specifies the character encoding and message versioning used for text-based XML messages.</span></span>  
  
 <span data-ttu-id="d2bd6-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="d2bd6-104">\<system.serviceModel></span></span>  
<span data-ttu-id="d2bd6-105">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="d2bd6-105">\<bindings></span></span>  
<span data-ttu-id="d2bd6-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="d2bd6-106">\<customBinding></span></span>  
<span data-ttu-id="d2bd6-107">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="d2bd6-107">\<binding></span></span>  
<span data-ttu-id="d2bd6-108">\<textMessageEncoding ></span><span class="sxs-lookup"><span data-stu-id="d2bd6-108">\<textMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2bd6-109">구문</span><span class="sxs-lookup"><span data-stu-id="d2bd6-109">Syntax</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="Integer"  
   maxWritePoolSize="Integer"  
   messageVersion="Soap11Addressing10/Soap12Addressing10"  
      writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d2bd6-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d2bd6-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d2bd6-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d2bd6-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d2bd6-112">특성</span><span class="sxs-lookup"><span data-stu-id="d2bd6-112">Attributes</span></span>  
  
|<span data-ttu-id="d2bd6-113">특성</span><span class="sxs-lookup"><span data-stu-id="d2bd6-113">Attribute</span></span>|<span data-ttu-id="d2bd6-114">설명</span><span class="sxs-lookup"><span data-stu-id="d2bd6-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d2bd6-115">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="d2bd6-115">maxReadPoolSize</span></span>|<span data-ttu-id="d2bd6-116">새 판독기를 할당하지 않고 동시에 읽을 수 있는 메시지 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="d2bd6-116">An integer that specifies how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="d2bd6-117">풀 크기가 커지면 작업 집합이 커지는 단점이 있지만 동작이 많을 경우의 시스템 안정성이 높아집니다.</span><span class="sxs-lookup"><span data-stu-id="d2bd6-117">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="d2bd6-118">기본값은 64입니다.</span><span class="sxs-lookup"><span data-stu-id="d2bd6-118">The default is 64.</span></span>|  
|<span data-ttu-id="d2bd6-119">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="d2bd6-119">maxWritePoolSize</span></span>|<span data-ttu-id="d2bd6-120">새 작성기를 할당하지 않고 동시에 보낼 수 있는 메시지 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="d2bd6-120">An integer that specifies how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="d2bd6-121">풀 크기가 커지면 작업 집합이 커지는 단점이 있지만 동작이 많을 경우의 시스템 안정성이 높아집니다.</span><span class="sxs-lookup"><span data-stu-id="d2bd6-121">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="d2bd6-122">기본값은 16입니다.</span><span class="sxs-lookup"><span data-stu-id="d2bd6-122">The default is 16.</span></span>|  
|<span data-ttu-id="d2bd6-123">messageVersion</span><span class="sxs-lookup"><span data-stu-id="d2bd6-123">messageVersion</span></span>|<span data-ttu-id="d2bd6-124">바인딩을 사용하여 보낸 메시지의 SOAP 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d2bd6-124">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="d2bd6-125">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d2bd6-125">Valid values are</span></span><br /><br /> <span data-ttu-id="d2bd6-126">-Soap11Addressing10</span><span class="sxs-lookup"><span data-stu-id="d2bd6-126">-   Soap11Addressing10</span></span><br /><span data-ttu-id="d2bd6-127">-Soap12Addressing10</span><span class="sxs-lookup"><span data-stu-id="d2bd6-127">-   Soap12Addressing10</span></span><br /><br /> <span data-ttu-id="d2bd6-128">기본값은 Soap12Addressing10입니다.</span><span class="sxs-lookup"><span data-stu-id="d2bd6-128">The default is Soap12Addressing10.</span></span> <span data-ttu-id="d2bd6-129">이 특성은 <xref:System.ServiceModel.Channels.MessageVersion> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d2bd6-129">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
|<span data-ttu-id="d2bd6-130">writeEncoding</span><span class="sxs-lookup"><span data-stu-id="d2bd6-130">writeEncoding</span></span>|<span data-ttu-id="d2bd6-131">바인딩에서 메시지를 내보내는 데 사용되는 문자 집합 인코딩을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d2bd6-131">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="d2bd6-132">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d2bd6-132">Valid values are</span></span><br /><br /> <span data-ttu-id="d2bd6-133">-UnicodeFffeTextEncoding: 유니코드 BigEndian 인코딩</span><span class="sxs-lookup"><span data-stu-id="d2bd6-133">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding</span></span><br /><span data-ttu-id="d2bd6-134">-Utf16TextEncoding: 유니코드 인코딩</span><span class="sxs-lookup"><span data-stu-id="d2bd6-134">-   Utf16TextEncoding: Unicode encoding</span></span><br /><span data-ttu-id="d2bd6-135">-Utf8TextEncoding: 8 비트 인코딩</span><span class="sxs-lookup"><span data-stu-id="d2bd6-135">-   Utf8TextEncoding: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="d2bd6-136">기본값은 Utf8TextEncoding입니다.</span><span class="sxs-lookup"><span data-stu-id="d2bd6-136">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="d2bd6-137">이 특성은 <xref:System.Text.Encoding> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d2bd6-137">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d2bd6-138">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d2bd6-138">Child Elements</span></span>  
  
|<span data-ttu-id="d2bd6-139">요소</span><span class="sxs-lookup"><span data-stu-id="d2bd6-139">Element</span></span>|<span data-ttu-id="d2bd6-140">설명</span><span class="sxs-lookup"><span data-stu-id="d2bd6-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d2bd6-141">\<readerQuotas ></span><span class="sxs-lookup"><span data-stu-id="d2bd6-141">\<readerQuotas></span></span>](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="d2bd6-142">이 바인딩으로 구성된 끝점에서 처리할 수 있는 SOAP 메시지의 복잡성에 대한 제약 조건을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d2bd6-142">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="d2bd6-143">이 요소는 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d2bd6-143">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d2bd6-144">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d2bd6-144">Parent Elements</span></span>  
  
|<span data-ttu-id="d2bd6-145">요소</span><span class="sxs-lookup"><span data-stu-id="d2bd6-145">Element</span></span>|<span data-ttu-id="d2bd6-146">설명</span><span class="sxs-lookup"><span data-stu-id="d2bd6-146">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d2bd6-147">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="d2bd6-147">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="d2bd6-148">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d2bd6-148">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d2bd6-149">설명</span><span class="sxs-lookup"><span data-stu-id="d2bd6-149">Remarks</span></span>  
 <span data-ttu-id="d2bd6-150">인코딩은 메시지를 바이트 시퀀스로 변형하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="d2bd6-150">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="d2bd6-151">디코딩은 역프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="d2bd6-151">Decoding is the reverse process.</span></span> <span data-ttu-id="d2bd6-152">WCF(Windows Communication Foundation)에서는 SOAP 메시지에 대해 텍스트, 이진 및 MTOM(Message Transmission Optimization Mechanism)이라는 세 가지 형식의 인코딩을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d2bd6-152">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="d2bd6-153">`textMessageEncoding` 요소로 나타낸 텍스트 인코딩은 상호 운용성이 가장 뛰어나지만 XML 메시지에 대해서는 효율성이 가장 낮은 인코더입니다.</span><span class="sxs-lookup"><span data-stu-id="d2bd6-153">The text encoding represented by the `textMessageEncoding` element is the most interoperable, but the least efficient encoder for XML messages.</span></span>  <span data-ttu-id="d2bd6-154">텍스트 인코더는 통신 중에 텍스트 기반 메시지를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d2bd6-154">The text encoder creates text-based messages on the wire.</span></span> <span data-ttu-id="d2bd6-155">이 인코더에서 생성하는 메시지는 WS-* 기반 interop과 호환됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2bd6-155">Messages produced by this encoder are suitable for WS-* based interop.</span></span> <span data-ttu-id="d2bd6-156">웹 서비스 또는 웹 서비스 클라이언트는 일반적으로 텍스트 XML을 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2bd6-156">Web service or Web service client can generally understand textual XML.</span></span> <span data-ttu-id="d2bd6-157">그러나 큰 이진 데이터 블록을 텍스트 형태로 전송하는 것은 가장 비효율적인 XML 메시지 인코딩 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="d2bd6-157">However, transmitting large blocks of binary data as text is the least efficient method for encoding XML messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d2bd6-158">예제</span><span class="sxs-lookup"><span data-stu-id="d2bd6-158">Example</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="211"  
    maxWritePoolSize="2132"  
    messageVersion="Soap12Addressing10"  
    textEncoding="utf-8" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="d2bd6-159">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d2bd6-159">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.TextMessageEncodingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>  
 <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>  
 [<span data-ttu-id="d2bd6-160">메시지 인코더 선택</span><span class="sxs-lookup"><span data-stu-id="d2bd6-160">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 [<span data-ttu-id="d2bd6-161">메시지 인코딩</span><span class="sxs-lookup"><span data-stu-id="d2bd6-161">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)  
 [<span data-ttu-id="d2bd6-162">바인딩</span><span class="sxs-lookup"><span data-stu-id="d2bd6-162">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="d2bd6-163">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="d2bd6-163">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="d2bd6-164">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="d2bd6-164">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="d2bd6-165">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="d2bd6-165">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
