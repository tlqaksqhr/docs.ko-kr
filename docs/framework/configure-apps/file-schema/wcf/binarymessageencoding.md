---
title: '&lt;binaryMessageEncoding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e4ae3cd4-6b67-4ce1-af4b-9400e0a38dba
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4e1314347dfb83fb0631ebaa98b4d35bb0ac402f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="ltbinarymessageencodinggt"></a><span data-ttu-id="52bbb-102">&lt;binaryMessageEncoding&gt;</span><span class="sxs-lookup"><span data-stu-id="52bbb-102">&lt;binaryMessageEncoding&gt;</span></span>
<span data-ttu-id="52bbb-103">통신 중에 WCF(Windows Communication Foundation) 메시지를 이진 형식으로 인코딩하는 이진 메시지 인코더를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="52bbb-103">Defines a binary message encoder that encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span>  
  
 <span data-ttu-id="52bbb-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="52bbb-104">\<system.serviceModel></span></span>  
<span data-ttu-id="52bbb-105">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="52bbb-105">\<bindings></span></span>  
<span data-ttu-id="52bbb-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="52bbb-106">\<customBinding></span></span>  
<span data-ttu-id="52bbb-107">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="52bbb-107">\<binding></span></span>  
<span data-ttu-id="52bbb-108">\<binaryMessageEncoding ></span><span class="sxs-lookup"><span data-stu-id="52bbb-108">\<binaryMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52bbb-109">구문</span><span class="sxs-lookup"><span data-stu-id="52bbb-109">Syntax</span></span>  
  
```xml  
<binaryMessageEncoding   
      maxReadPoolSize="Integer"  
   maxSessionSize="Integer"   
   maxWritePoolSize="Integer"   messageVersion="Soap11Addressing10/Soap12Addressing10" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="52bbb-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="52bbb-110">Attributes and Elements</span></span>  
 <span data-ttu-id="52bbb-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="52bbb-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="52bbb-112">특성</span><span class="sxs-lookup"><span data-stu-id="52bbb-112">Attributes</span></span>  
  
|<span data-ttu-id="52bbb-113">특성</span><span class="sxs-lookup"><span data-stu-id="52bbb-113">Attribute</span></span>|<span data-ttu-id="52bbb-114">설명</span><span class="sxs-lookup"><span data-stu-id="52bbb-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="52bbb-115">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="52bbb-115">maxReadPoolSize</span></span>|<span data-ttu-id="52bbb-116">새 판독기를 할당하지 않고 동시에 읽을 수 있는 메시지 수를 정의하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="52bbb-116">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="52bbb-117">풀 크기가 커지면 작업 집합이 커지는 단점이 있지만 동작이 많을 경우의 시스템 안정성이 높아집니다.</span><span class="sxs-lookup"><span data-stu-id="52bbb-117">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="52bbb-118">기본값은 64입니다.</span><span class="sxs-lookup"><span data-stu-id="52bbb-118">The default is 64.</span></span>|  
|<span data-ttu-id="52bbb-119">maxSessionSize</span><span class="sxs-lookup"><span data-stu-id="52bbb-119">maxSessionSize</span></span>|<span data-ttu-id="52bbb-120">인코딩에 사용되는 버퍼의 크기(바이트)를 설정하는 양의 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="52bbb-120">A positive integer that sets the size, in bytes, of the buffer used for encoding.</span></span> <span data-ttu-id="52bbb-121">버퍼가 크면 작업 집합의 크기 문제가 생기지만 인코딩 속도가 빨라집니다.</span><span class="sxs-lookup"><span data-stu-id="52bbb-121">A larger buffer increases encoding speed at the expense of the size of the working set.</span></span> <span data-ttu-id="52bbb-122">기본값은 2048입니다.</span><span class="sxs-lookup"><span data-stu-id="52bbb-122">The default is 2048.</span></span>|  
|<span data-ttu-id="52bbb-123">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="52bbb-123">maxWritePoolSize</span></span>|<span data-ttu-id="52bbb-124">새 작성기를 할당하지 않고 동시에 보낼 수 있는 메시지 수를 정의하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="52bbb-124">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="52bbb-125">풀 크기가 커지면 작업 집합이 커지는 단점이 있지만 동작이 많을 경우의 시스템 안정성이 높아집니다.</span><span class="sxs-lookup"><span data-stu-id="52bbb-125">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="52bbb-126">기본값은 16입니다.</span><span class="sxs-lookup"><span data-stu-id="52bbb-126">The default is 16.</span></span>|  
|<span data-ttu-id="52bbb-127">messageVersion</span><span class="sxs-lookup"><span data-stu-id="52bbb-127">messageVersion</span></span>|<span data-ttu-id="52bbb-128">사용되거나 필요한 SOAP 메시지 및 WS-Addressing 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="52bbb-128">Specifies the SOAP message and WS-Addressing versions that are used or expected.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="52bbb-129">자식 요소</span><span class="sxs-lookup"><span data-stu-id="52bbb-129">Child Elements</span></span>  
  
|<span data-ttu-id="52bbb-130">요소</span><span class="sxs-lookup"><span data-stu-id="52bbb-130">Element</span></span>|<span data-ttu-id="52bbb-131">설명</span><span class="sxs-lookup"><span data-stu-id="52bbb-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="52bbb-132">\<readerQuotas ></span><span class="sxs-lookup"><span data-stu-id="52bbb-132">\<readerQuotas></span></span>](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="52bbb-133">이 바인딩으로 구성된 끝점에서 처리할 수 있는 SOAP 메시지의 복잡성에 대한 제약 조건을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="52bbb-133">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="52bbb-134">이 요소는 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="52bbb-134">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="52bbb-135">부모 요소</span><span class="sxs-lookup"><span data-stu-id="52bbb-135">Parent Elements</span></span>  
  
|<span data-ttu-id="52bbb-136">요소</span><span class="sxs-lookup"><span data-stu-id="52bbb-136">Element</span></span>|<span data-ttu-id="52bbb-137">설명</span><span class="sxs-lookup"><span data-stu-id="52bbb-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="52bbb-138">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="52bbb-138">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="52bbb-139">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="52bbb-139">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="52bbb-140">설명</span><span class="sxs-lookup"><span data-stu-id="52bbb-140">Remarks</span></span>  
 <span data-ttu-id="52bbb-141">인코딩은 메시지를 바이트 시퀀스로 변형하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="52bbb-141">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="52bbb-142">디코딩은 역프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="52bbb-142">Decoding is the reverse process.</span></span> <span data-ttu-id="52bbb-143">WCF(Windows Communication Foundation)에서는 SOAP 메시지에 대해 텍스트, 이진 및 MTOM(Message Transmission Optimization Mechanism)이라는 세 가지 형식의 인코딩을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="52bbb-143">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="52bbb-144">`binaryMessageEncoding` 요소는 XML에 대한 .NET 이진 형식을 지정하며, 사용할 SOAP 및 WS-Addressing 버전과 문자 인코딩을 지정하는 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="52bbb-144">The `binaryMessageEncoding` element specifies the .NET Binary Format for XML and has options to specify the character encoding and the SOAP and WS-Addressing version to be used.</span></span> <span data-ttu-id="52bbb-145">이진 메시지 인코더는 통신 중에 WCF(Windows Communication Foundation) 메시지를 이진 형식으로 인코딩합니다.</span><span class="sxs-lookup"><span data-stu-id="52bbb-145">The binary message encoder encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span> <span data-ttu-id="52bbb-146">이 인코딩은 전송 속도가 매우 빠르지만 WS-* 표준과 호환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="52bbb-146">While this encoding results in very fast transmission of messages, interoperability based on the WS-* standards is lost.</span></span>  
  
## <a name="example"></a><span data-ttu-id="52bbb-147">예제</span><span class="sxs-lookup"><span data-stu-id="52bbb-147">Example</span></span>  
  
```xml  
<binaryMessageEncoding maxReadPoolSize="211"  
   maxWritePoolSize="2132"  
   maxSessionSize="3141" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="52bbb-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="52bbb-148">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.BinaryMessageEncodingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>  
 <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>  
 [<span data-ttu-id="52bbb-149">메시지 인코딩</span><span class="sxs-lookup"><span data-stu-id="52bbb-149">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)  
 [<span data-ttu-id="52bbb-150">메시지 인코더 선택</span><span class="sxs-lookup"><span data-stu-id="52bbb-150">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 [<span data-ttu-id="52bbb-151">바인딩</span><span class="sxs-lookup"><span data-stu-id="52bbb-151">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="52bbb-152">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="52bbb-152">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="52bbb-153">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="52bbb-153">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="52bbb-154">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="52bbb-154">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
