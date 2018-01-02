---
title: "메시지 인코딩"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f30ee941-aca9-4c67-82a5-421568496f07
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b3040a16b6d167c4f066b2ddbd0a542741f88d62
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="message-encoding"></a><span data-ttu-id="4c5d3-102">메시지 인코딩</span><span class="sxs-lookup"><span data-stu-id="4c5d3-102">Message Encoding</span></span>
<span data-ttu-id="4c5d3-103">인코딩은 유니코드 문자 집합을 바이트 시퀀스로 변환하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="4c5d3-103">Encoding is the process of transforming a set of Unicode characters into a sequence of bytes.</span></span> <span data-ttu-id="4c5d3-104">디코딩은 역프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="4c5d3-104">Decoding is the reverse process.</span></span> <span data-ttu-id="4c5d3-105">WCF(Windows Communication Foundation)에서는 SOAP 메시지에 대해 텍스트, 이진 및 MTOM(Message Transmission Optimization Mechanism)이라는 세 가지 형식의 인코딩을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4c5d3-105">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="4c5d3-106">`binaryMessageEncoding` 구성 섹션은 이진 기반 XML 메시지에 사용되는 문자 인코딩 및 메시지 버전 관리를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4c5d3-106">The `binaryMessageEncoding` configuration section specifies the character encoding and message versioning used for binary-based XML messages.</span></span> <span data-ttu-id="4c5d3-107">이진 메시지 인코더는 통신 중에 WCF(Windows Communication Foundation) 메시지를 이진 형식으로 인코딩합니다.</span><span class="sxs-lookup"><span data-stu-id="4c5d3-107">The binary message encoder encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span> <span data-ttu-id="4c5d3-108">이 인코딩은 전송 속도가 매우 빠르지만 WS-* 표준과 호환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4c5d3-108">While this encoding results in very fast transmission of messages, interoperability based on the WS-* standards is lost.</span></span>  
  
 <span data-ttu-id="4c5d3-109">`mtomMessageEncoding` 구성 섹션은 MTOM(Message Transmission Optimization Mechanism) 인코딩을 사용하는 메시지에 사용되는 문자 인코딩 및 메시지 버전 관리를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4c5d3-109">The `mtomMessageEncoding` configuration section specifies the character encoding and message versioning used for a message using a Message Transmission Optimization Mechanism (MTOM) encoding.</span></span> <span data-ttu-id="4c5d3-110">MTOM은 WCF(Windows Communication Foundation) 메시지의 이진 데이터를 효율적으로 전송하는 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="4c5d3-110">(MTOM) is an efficient technology for transmitting binary data in Windows Communication Foundation (WCF) messages.</span></span> <span data-ttu-id="4c5d3-111">MTOM 인코더는 효율성과 상호 운용성 간의 균형을 유지하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c5d3-111">The MTOM encoder attempts to strike a balance between efficiency and interoperability.</span></span> <span data-ttu-id="4c5d3-112">MTOM 인코딩은 대부분의 XML을 텍스트 형식으로 전송하지만, 큰 이진 데이터 블록의 경우에는 텍스트로 변환하지 않고 있는 그대로 전송하여 최적화합니다.</span><span class="sxs-lookup"><span data-stu-id="4c5d3-112">The MTOM encoding transmits most XML in textual form, but optimizes large blocks of binary data by transmitting them as-is, without conversion to text.</span></span>  
  
 <span data-ttu-id="4c5d3-113">`textMessageEncoding` 구성 섹션은 통신 중에 텍스트 기반 메시지를 만드는 데 사용되는 텍스트 인코더를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4c5d3-113">The `textMessageEncoding` configuration section specifies a text encoder used to create text-based messages on the wire.</span></span> <span data-ttu-id="4c5d3-114">이 인코더에서 생성하는 메시지는 WS-* 기반 interop과 호환됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c5d3-114">Messages produced by this encoder are suitable for WS-* based interop.</span></span> <span data-ttu-id="4c5d3-115">웹 서비스 또는 웹 서비스 클라이언트는 일반적으로 텍스트 XML을 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c5d3-115">Web service or Web service client can generally understand textual XML.</span></span> <span data-ttu-id="4c5d3-116">그러나 큰 이진 데이터 블록을 텍스트 형태로 전송하는 것은 가장 비효율적인 XML 메시지 인코딩 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="4c5d3-116">However, transmitting large blocks of binary data as text is the least efficient method for encoding XML messages</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c5d3-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4c5d3-117">See Also</span></span>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>  
 [<span data-ttu-id="4c5d3-118">바인딩</span><span class="sxs-lookup"><span data-stu-id="4c5d3-118">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="4c5d3-119">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="4c5d3-119">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="4c5d3-120">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="4c5d3-120">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="4c5d3-121">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="4c5d3-121">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="4c5d3-122">메시지 인코더 선택</span><span class="sxs-lookup"><span data-stu-id="4c5d3-122">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)
