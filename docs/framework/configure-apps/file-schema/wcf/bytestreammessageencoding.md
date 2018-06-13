---
title: '&lt;byteStreamMessageEncoding&gt;'
ms.date: 03/30/2017
ms.assetid: bbadd8dd-60a2-4007-b959-89373a8a7d60
ms.openlocfilehash: 3493588d4613131ad9526a8d26912ecdb601ea25
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32753276"
---
# <a name="ltbytestreammessageencodinggt"></a><span data-ttu-id="d8eb3-102">&lt;byteStreamMessageEncoding&gt;</span><span class="sxs-lookup"><span data-stu-id="d8eb3-102">&lt;byteStreamMessageEncoding&gt;</span></span>
<span data-ttu-id="d8eb3-103">문자 인코딩을 지정하는 옵션을 사용하여 메시지 인코딩을 바이트 스트림으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d8eb3-103">Specifies the message encoding as a stream of bytes, with the option to specify the character encoding.</span></span>  
  
 <span data-ttu-id="d8eb3-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="d8eb3-104">\<system.serviceModel></span></span>  
<span data-ttu-id="d8eb3-105">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="d8eb3-105">\<bindings></span></span>  
<span data-ttu-id="d8eb3-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="d8eb3-106">\<customBinding></span></span>  
<span data-ttu-id="d8eb3-107">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="d8eb3-107">\<binding></span></span>  
<span data-ttu-id="d8eb3-108">\<binaryMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="d8eb3-108">\<binaryMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8eb3-109">구문</span><span class="sxs-lookup"><span data-stu-id="d8eb3-109">Syntax</span></span>  
  
```xml  
<byteStreamMessageEncoding/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d8eb3-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d8eb3-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d8eb3-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d8eb3-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d8eb3-112">특성</span><span class="sxs-lookup"><span data-stu-id="d8eb3-112">Attributes</span></span>  
  
|<span data-ttu-id="d8eb3-113">특성</span><span class="sxs-lookup"><span data-stu-id="d8eb3-113">Attribute</span></span>|<span data-ttu-id="d8eb3-114">설명</span><span class="sxs-lookup"><span data-stu-id="d8eb3-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d8eb3-115">messageVersion</span><span class="sxs-lookup"><span data-stu-id="d8eb3-115">messageVersion</span></span>|<span data-ttu-id="d8eb3-116">바인딩을 사용하여 보낸 메시지의 SOAP 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d8eb3-116">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="d8eb3-117">이 속성은 <xref:System.ServiceModel.Channels.MessageVersion.None%2A>의 메시지 버전 값으로만 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8eb3-117">This property can only be set to the message version value of <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span> <span data-ttu-id="d8eb3-118">바이트 스트림 메시지 인코더는 다른 메시지 버전을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d8eb3-118">The byte stream message encoder does not support any other message versions.</span></span><br /><br /> <span data-ttu-id="d8eb3-119">이 특성은 <xref:System.ServiceModel.Channels.MessageVersion> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d8eb3-119">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d8eb3-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d8eb3-120">Child Elements</span></span>  
  
|<span data-ttu-id="d8eb3-121">요소</span><span class="sxs-lookup"><span data-stu-id="d8eb3-121">Element</span></span>|<span data-ttu-id="d8eb3-122">설명</span><span class="sxs-lookup"><span data-stu-id="d8eb3-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d8eb3-123">\<readerQuotas></span><span class="sxs-lookup"><span data-stu-id="d8eb3-123">\<readerQuotas></span></span>](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="d8eb3-124">이 바인딩으로 구성된 끝점에서 처리할 수 있는 SOAP 메시지의 복잡성에 대한 제약 조건을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d8eb3-124">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="d8eb3-125">이 요소는 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d8eb3-125">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d8eb3-126">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d8eb3-126">Parent Elements</span></span>  
  
|<span data-ttu-id="d8eb3-127">요소</span><span class="sxs-lookup"><span data-stu-id="d8eb3-127">Element</span></span>|<span data-ttu-id="d8eb3-128">설명</span><span class="sxs-lookup"><span data-stu-id="d8eb3-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d8eb3-129">\<binding></span><span class="sxs-lookup"><span data-stu-id="d8eb3-129">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="d8eb3-130">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d8eb3-130">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d8eb3-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d8eb3-131">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ByteStreamMessageEncodingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>  
 <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>  
 [<span data-ttu-id="d8eb3-132">메시지 인코딩</span><span class="sxs-lookup"><span data-stu-id="d8eb3-132">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)  
 [<span data-ttu-id="d8eb3-133">메시지 인코더 선택</span><span class="sxs-lookup"><span data-stu-id="d8eb3-133">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 [<span data-ttu-id="d8eb3-134">바인딩</span><span class="sxs-lookup"><span data-stu-id="d8eb3-134">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="d8eb3-135">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="d8eb3-135">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="d8eb3-136">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="d8eb3-136">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="d8eb3-137">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="d8eb3-137">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
