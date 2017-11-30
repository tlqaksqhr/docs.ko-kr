---
title: "메시징 프로토콜"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5b20bca7-87b3-4c8f-811b-f215b5987104
caps.latest.revision: "14"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4052971746086061cb2ed091bd13c962318b2d89
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="messaging-protocols"></a><span data-ttu-id="ec1c7-102">메시징 프로토콜</span><span class="sxs-lookup"><span data-stu-id="ec1c7-102">Messaging Protocols</span></span>
<span data-ttu-id="ec1c7-103">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 채널 스택에서는 인코딩 및 전송 채널을 통해 내부 메시지 표현을 통신 형식으로 변환한 후 특정 전송을 사용하여 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-103">The [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] channel stack employs encoding and transport channels to transform internal message representation into its wire format and send it by using a particular transport.</span></span> <span data-ttu-id="ec1c7-104">웹 서비스 상호 운용성을 위해 사용되는 가장 일반적인 전송은 HTTP이고, 웹 서비스에 사용되는 가장 일반적인 인코딩은 XML 기반 SOAP 1.1, SOAP 1.2 및 MTOM(Message Transmission Optimization Mechanism)입니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-104">The most common transport used for Web services interoperability is HTTP, and the most common encodings used by Web services are XML-based SOAP 1.1, SOAP 1.2, and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="ec1c7-105">이 항목에서는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에 사용되는 다음 프로토콜에 대한 <xref:System.ServiceModel.Channels.HttpTransportBindingElement> 구현 정보에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-105">This topic covers [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementation details for the following protocols employed by <xref:System.ServiceModel.Channels.HttpTransportBindingElement>.</span></span>  
  
|<span data-ttu-id="ec1c7-106">사양/문서</span><span class="sxs-lookup"><span data-stu-id="ec1c7-106">Specification/document</span></span>|<span data-ttu-id="ec1c7-107">링크</span><span class="sxs-lookup"><span data-stu-id="ec1c7-107">Link</span></span>|  
|-----------------------------|----------|  
|<span data-ttu-id="ec1c7-108">HTTP 1.1</span><span class="sxs-lookup"><span data-stu-id="ec1c7-108">HTTP 1.1</span></span>|<span data-ttu-id="ec1c7-109">http://www.ietf.org/rfc/rfc2616.txt</span><span class="sxs-lookup"><span data-stu-id="ec1c7-109">http://www.ietf.org/rfc/rfc2616.txt</span></span>|  
|<span data-ttu-id="ec1c7-110">SOAP 1.1 HTTP 바인딩</span><span class="sxs-lookup"><span data-stu-id="ec1c7-110">SOAP 1.1 HTTP Binding</span></span>|<span data-ttu-id="ec1c7-111">http://www.w3.org/TR/2000/NOTE-SOAP-20000508/, 단원 7</span><span class="sxs-lookup"><span data-stu-id="ec1c7-111">http://www.w3.org/TR/2000/NOTE-SOAP-20000508/, Section 7</span></span>|  
|<span data-ttu-id="ec1c7-112">SOAP 1.2 HTTP 바인딩</span><span class="sxs-lookup"><span data-stu-id="ec1c7-112">SOAP 1.2 HTTP Binding</span></span>|<span data-ttu-id="ec1c7-113">http://www.w3.org/TR/soap12-part2/, 단원 7</span><span class="sxs-lookup"><span data-stu-id="ec1c7-113">http://www.w3.org/TR/soap12-part2/, Section 7</span></span>|  
  
 <span data-ttu-id="ec1c7-114">이 항목에서는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 및 <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>에 사용되는 다음 프로토콜에 대한 <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> 구현 정보에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-114">This topic covers [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementation details for the following protocols  that <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> and <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> employ.</span></span>  
  
|<span data-ttu-id="ec1c7-115">사양/문서</span><span class="sxs-lookup"><span data-stu-id="ec1c7-115">Specification/Document</span></span>|<span data-ttu-id="ec1c7-116">링크</span><span class="sxs-lookup"><span data-stu-id="ec1c7-116">Link</span></span>|  
|-----------------------------|----------|  
|<span data-ttu-id="ec1c7-117">XML</span><span class="sxs-lookup"><span data-stu-id="ec1c7-117">XML</span></span>|<span data-ttu-id="ec1c7-118">http://www.w3.org/TR/REC-xml</span><span class="sxs-lookup"><span data-stu-id="ec1c7-118">http://www.w3.org/TR/REC-xml</span></span>|  
|<span data-ttu-id="ec1c7-119">SOAP 1.1</span><span class="sxs-lookup"><span data-stu-id="ec1c7-119">SOAP 1.1</span></span>|<span data-ttu-id="ec1c7-120">http://www.w3.org/TR/2000/NOTE-SOAP-20000508/</span><span class="sxs-lookup"><span data-stu-id="ec1c7-120">http://www.w3.org/TR/2000/NOTE-SOAP-20000508/</span></span>|  
|<span data-ttu-id="ec1c7-121">SOAP 1.2 Core</span><span class="sxs-lookup"><span data-stu-id="ec1c7-121">SOAP 1.2 Core</span></span>|<span data-ttu-id="ec1c7-122">http://www.w3.org/TR/soap12-part1/</span><span class="sxs-lookup"><span data-stu-id="ec1c7-122">http://www.w3.org/TR/soap12-part1/</span></span>|  
|<span data-ttu-id="ec1c7-123">WS-Addressing 2004/08</span><span class="sxs-lookup"><span data-stu-id="ec1c7-123">WS-Addressing 2004/08</span></span>|<span data-ttu-id="ec1c7-124">http://www.w3.org/Submission/2004/SUBM-ws-addressing-20040810/</span><span class="sxs-lookup"><span data-stu-id="ec1c7-124">http://www.w3.org/Submission/2004/SUBM-ws-addressing-20040810/</span></span>|  
|<span data-ttu-id="ec1c7-125">W3C Web Services Addressing 1.0 - Core</span><span class="sxs-lookup"><span data-stu-id="ec1c7-125">W3C Web Services Addressing 1.0 - Core</span></span>|<span data-ttu-id="ec1c7-126">http://www.w3.org/TR/2006/REC-ws-addr-core-20060509</span><span class="sxs-lookup"><span data-stu-id="ec1c7-126">http://www.w3.org/TR/2006/REC-ws-addr-core-20060509</span></span>|  
|<span data-ttu-id="ec1c7-127">W3C Web Services Addressing 1.0 - SOAP 바인딩</span><span class="sxs-lookup"><span data-stu-id="ec1c7-127">W3C Web Services Addressing 1.0 - SOAP Binding</span></span>|<span data-ttu-id="ec1c7-128">http://www.w3.org/TR/2006/REC-ws-addr-soap-20060509</span><span class="sxs-lookup"><span data-stu-id="ec1c7-128">http://www.w3.org/TR/2006/REC-ws-addr-soap-20060509</span></span>|  
|<span data-ttu-id="ec1c7-129">W3C Web Services Addressing 1.0 - WSDL 바인딩</span><span class="sxs-lookup"><span data-stu-id="ec1c7-129">W3C Web Services Addressing 1.0 - WSDL Binding</span></span>|<span data-ttu-id="ec1c7-130">http://www.w3.org/TR/2006/CR-ws-addr-wsdl-20060529/</span><span class="sxs-lookup"><span data-stu-id="ec1c7-130">http://www.w3.org/TR/2006/CR-ws-addr-wsdl-20060529/</span></span>|  
<span data-ttu-id="ec1c7-131">W3C Web Services Addressing 1.0 - Metadata</span><span class="sxs-lookup"><span data-stu-id="ec1c7-131">W3C Web Services Addressing 1.0 - Metadata</span></span>|<span data-ttu-id="ec1c7-132">http://www.w3.org/TR/ws-addr-metadata/</span><span class="sxs-lookup"><span data-stu-id="ec1c7-132">http://www.w3.org/TR/ws-addr-metadata/</span></span>|  
|<span data-ttu-id="ec1c7-133">WSDL SOAP1.1 바인딩</span><span class="sxs-lookup"><span data-stu-id="ec1c7-133">WSDL SOAP1.1 Binding</span></span>|<span data-ttu-id="ec1c7-134">http://www.w3.org/TR/wsdl/</span><span class="sxs-lookup"><span data-stu-id="ec1c7-134">http://www.w3.org/TR/wsdl/</span></span>|  
|<span data-ttu-id="ec1c7-135">WSDL SOAP1.2 바인딩</span><span class="sxs-lookup"><span data-stu-id="ec1c7-135">WSDL SOAP1.2 Binding</span></span>|<span data-ttu-id="ec1c7-136">http://www.w3.org/Submission/wsdl11soap12/</span><span class="sxs-lookup"><span data-stu-id="ec1c7-136">http://www.w3.org/Submission/wsdl11soap12/</span></span>|  
  
 <span data-ttu-id="ec1c7-137">이 항목에서는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에 사용되는 다음 프로토콜에 대한 <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> 구현 정보에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-137">This topic covers [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementation details for the following protocols that <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> employs.</span></span>  
  
|<span data-ttu-id="ec1c7-138">사양/문서</span><span class="sxs-lookup"><span data-stu-id="ec1c7-138">Specification/document</span></span>|<span data-ttu-id="ec1c7-139">링크</span><span class="sxs-lookup"><span data-stu-id="ec1c7-139">Link</span></span>|  
|-----------------------------|----------|  
|<span data-ttu-id="ec1c7-140">XOP</span><span class="sxs-lookup"><span data-stu-id="ec1c7-140">XOP</span></span>|<span data-ttu-id="ec1c7-141">http://www.w3.org/TR/xop10/</span><span class="sxs-lookup"><span data-stu-id="ec1c7-141">http://www.w3.org/TR/xop10/</span></span>|  
|<span data-ttu-id="ec1c7-142">MTOM + SOAP 1.2 바인딩</span><span class="sxs-lookup"><span data-stu-id="ec1c7-142">MTOM + SOAP 1.2 Binding</span></span>|<span data-ttu-id="ec1c7-143">http://www.w3.org/TR/soap12-mtom/</span><span class="sxs-lookup"><span data-stu-id="ec1c7-143">http://www.w3.org/TR/soap12-mtom/</span></span>|  
|<span data-ttu-id="ec1c7-144">MTOM SOAP 1.1 바인딩</span><span class="sxs-lookup"><span data-stu-id="ec1c7-144">MTOM SOAP 1.1 Binding</span></span>|<span data-ttu-id="ec1c7-145">http://www.w3.org/Submission/soap11mtom10/</span><span class="sxs-lookup"><span data-stu-id="ec1c7-145">http://www.w3.org/Submission/soap11mtom10/</span></span>|  
|<span data-ttu-id="ec1c7-146">MTOM WS-Policy Assertion</span><span class="sxs-lookup"><span data-stu-id="ec1c7-146">MTOM WS-Policy Assertion</span></span>|<span data-ttu-id="ec1c7-147">http://www.w3.org/Submission/2006/SUBM-WS-MTOMPolicy-20061101/</span><span class="sxs-lookup"><span data-stu-id="ec1c7-147">http://www.w3.org/Submission/2006/SUBM-WS-MTOMPolicy-20061101/.</span></span>|  
  
 <span data-ttu-id="ec1c7-148">다음 XML 네임스페이스 및 관련 접두사는 이 항목 전체에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-148">The following XML namespaces and associated prefixes are used throughout this topic.</span></span>  
  
|<span data-ttu-id="ec1c7-149">접두사</span><span class="sxs-lookup"><span data-stu-id="ec1c7-149">Prefix</span></span>|<span data-ttu-id="ec1c7-150">네임스페이스 URI(Uniform Resource Identifier)</span><span class="sxs-lookup"><span data-stu-id="ec1c7-150">Namespace Uniform Resource Identifier (URI)</span></span>|  
|------------|---------------------------------------------------|  
|<span data-ttu-id="ec1c7-151">s11</span><span class="sxs-lookup"><span data-stu-id="ec1c7-151">s11</span></span>|<span data-ttu-id="ec1c7-152">http://schemas.xmlsoap.org/soap/envelope</span><span class="sxs-lookup"><span data-stu-id="ec1c7-152">http://schemas.xmlsoap.org/soap/envelope</span></span>|  
|<span data-ttu-id="ec1c7-153">s12</span><span class="sxs-lookup"><span data-stu-id="ec1c7-153">s12</span></span>|<span data-ttu-id="ec1c7-154">http://www.w3.org/2003/05/soap-envelope</span><span class="sxs-lookup"><span data-stu-id="ec1c7-154">http://www.w3.org/2003/05/soap-envelope</span></span>|  
|<span data-ttu-id="ec1c7-155">wsa</span><span class="sxs-lookup"><span data-stu-id="ec1c7-155">wsa</span></span>|<span data-ttu-id="ec1c7-156">http://www.w3.org/2004/08/addressing</span><span class="sxs-lookup"><span data-stu-id="ec1c7-156">http://www.w3.org/2004/08/addressing</span></span>|  
|<span data-ttu-id="ec1c7-157">wsam</span><span class="sxs-lookup"><span data-stu-id="ec1c7-157">wsam</span></span>|<span data-ttu-id="ec1c7-158">http://www.w3.org/2007/05/addressing/metadata</span><span class="sxs-lookup"><span data-stu-id="ec1c7-158">http://www.w3.org/2007/05/addressing/metadata</span></span>|  
|<span data-ttu-id="ec1c7-159">wsap</span><span class="sxs-lookup"><span data-stu-id="ec1c7-159">wsap</span></span>|<span data-ttu-id="ec1c7-160">http://schemas.xmlsoap.org/ws/2004/09/policy/addressing</span><span class="sxs-lookup"><span data-stu-id="ec1c7-160">http://schemas.xmlsoap.org/ws/2004/09/policy/addressing</span></span>|  
|<span data-ttu-id="ec1c7-161">wsa10</span><span class="sxs-lookup"><span data-stu-id="ec1c7-161">wsa10</span></span>|<span data-ttu-id="ec1c7-162">http://www.w3.org/2005/08/addressing</span><span class="sxs-lookup"><span data-stu-id="ec1c7-162">http://www.w3.org/2005/08/addressing</span></span>|  
|<span data-ttu-id="ec1c7-163">wsaw10</span><span class="sxs-lookup"><span data-stu-id="ec1c7-163">wsaw10</span></span>|<span data-ttu-id="ec1c7-164">http://www.w3.org/2006/05/addressing/wsdl</span><span class="sxs-lookup"><span data-stu-id="ec1c7-164">http://www.w3.org/2006/05/addressing/wsdl</span></span>|  
|<span data-ttu-id="ec1c7-165">xop</span><span class="sxs-lookup"><span data-stu-id="ec1c7-165">xop</span></span>|<span data-ttu-id="ec1c7-166">http://www.w3.org/2004/08/xop/include</span><span class="sxs-lookup"><span data-stu-id="ec1c7-166">http://www.w3.org/2004/08/xop/include</span></span>|  
|<span data-ttu-id="ec1c7-167">xmime</span><span class="sxs-lookup"><span data-stu-id="ec1c7-167">xmime</span></span>|<span data-ttu-id="ec1c7-168">http://www.w3.org/2004/06/xmlmime</span><span class="sxs-lookup"><span data-stu-id="ec1c7-168">http://www.w3.org/2004/06/xmlmime</span></span><br /><br /> <span data-ttu-id="ec1c7-169">http://www.w3.org/2005/05/xmlmime</span><span class="sxs-lookup"><span data-stu-id="ec1c7-169">http://www.w3.org/2005/05/xmlmime</span></span>|  
<span data-ttu-id="ec1c7-170">dp</span><span class="sxs-lookup"><span data-stu-id="ec1c7-170">dp</span></span>|<span data-ttu-id="ec1c7-171">http://schemas.microsoft.com/net/2006/06/duplex</span><span class="sxs-lookup"><span data-stu-id="ec1c7-171">http://schemas.microsoft.com/net/2006/06/duplex</span></span>|  
  
## <a name="soap-11-and-soap-12"></a><span data-ttu-id="ec1c7-172">SOAP 1.1 및 SOAP 1.2</span><span class="sxs-lookup"><span data-stu-id="ec1c7-172">SOAP 1.1 and SOAP 1.2</span></span>  
  
### <a name="envelope-and-processing-model"></a><span data-ttu-id="ec1c7-173">봉투 및 처리 모델</span><span class="sxs-lookup"><span data-stu-id="ec1c7-173">Envelope and Processing Model</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="ec1c7-174">에서는 BP11(Basic Profile 1.1) 및 SSBP10(Basic Profile 1.0)에 따라 SOAP 1.1 봉투 처리를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-174"> implements SOAP 1.1 envelope processing following Basic Profile 1.1 (BP11) and Basic Profile 1.0 (SSBP10).</span></span> <span data-ttu-id="ec1c7-175">SOAP 1.2 봉투 처리는 SOAP12-Part1에 따라 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-175">SOAP 1.2 Envelope processing is implemented following SOAP12-Part1.</span></span>  
  
 <span data-ttu-id="ec1c7-176">이 단원에서는 BP11 및 SOAP12-Part1과 관련하여 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 제공되는 특정 구현 선택 항목에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-176">This section explains certain implementation choices taken by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] with regard to BP11 and SOAP12-Part1.</span></span>  
  
#### <a name="mandatory-header-processing"></a><span data-ttu-id="ec1c7-177">필수 헤더 처리</span><span class="sxs-lookup"><span data-stu-id="ec1c7-177">Mandatory Header Processing</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="ec1c7-178">에서는 SOAP 1.1 및 SOAP 1.2 사양에 명시된 `mustUnderstand` 헤더 처리 규칙을 다음과 같이 변형하여 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-178"> follows rules for processing headers marked `mustUnderstand` described in the SOAP 1.1 and SOAP 1.2 specifications, with the following variations.</span></span>  
  
 <span data-ttu-id="ec1c7-179">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 채널 스택에 전달되는 메시지는 텍스트 메시지 인코딩, 보안, 신뢰할 수 있는 메시징, 트랜잭션 등과 같은 관련 바인딩 요소로 구성된 개별 채널에 의해 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-179">A message that enters the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] channel stack is processed by individual channels configured by associated binding elements, for example, Text Message Encoding, Security, Reliable Messaging, and Transactions.</span></span> <span data-ttu-id="ec1c7-180">각 채널은 연결된 네임스페이스에서 헤더를 인식한 후 인식된 것으로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-180">Each channel recognizes headers from the associated namespace and marks them as understood.</span></span> <span data-ttu-id="ec1c7-181">메시지가 디스패처에 전달되면 작업 포맷터는 해당 메시지/작업 계약에 필요한 헤더를 읽고 인식된 것으로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-181">Once a message enters the dispatcher, the operation formatter reads headers expected by the corresponding message/operation contract and marks them understood.</span></span> <span data-ttu-id="ec1c7-182">그런 다음 디스패처는 나머지 헤더가 인식되지 않았지만 `mustUnderstand`로 표시되지 않았는지 확인하고 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-182">Then the dispatcher verifies whether any remaining headers are not understood but marked as `mustUnderstand` and throws an exception.</span></span> <span data-ttu-id="ec1c7-183">받는 사람을 대상으로 하는 `mustUnderstand` 헤더가 포함된 메시지는 받는 사람 응용 프로그램 코드로 처리되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-183">Messages that contain `mustUnderstand` headers that are targeted at the recipient are not processed by recipient application code.</span></span>  
  
 <span data-ttu-id="ec1c7-184">이러한 계층화된 처리를 사용하면 SOAP 노드의 응용 프로그램 계층과 인프라 계층을 분리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-184">Such layered processing allows for separation between infrastructure layers and application layers of the SOAP node:</span></span>  
  
-   <span data-ttu-id="ec1c7-185">B1111: 인식되지 않은 헤더는 메시지가 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 인프라 채널 스택에서 처리되고 나서 응용 프로그램에서 처리되기 전에 감지됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-185">B1111: Headers that are not understood are detected after the message is processed by the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] infrastructure channel stack, but before it is processed by application</span></span>  
  
     <span data-ttu-id="ec1c7-186">SOAP 1.1과 SOAP 1.2의 `mustUnderstand` 헤더 값은 서로 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-186">The `mustUnderstand` header value differs between SOAP 1.1 and SOAP 1.2.</span></span> <span data-ttu-id="ec1c7-187">Basic Profile 1.1에서 SOAP 1.1 메시지의 `mustUnderstand` 값은 0 또는 1이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-187">Basic Profile 1.1 requires that the `mustUnderstand` value be 0 or 1 for SOAP 1.1 messages.</span></span> <span data-ttu-id="ec1c7-188">SOAP 1.2에서는 0, 1, `false` 및 `true`를 값으로 사용할 수 있지만 정식으로 표현된 `xs:boolean` 값(`false`, `true`)을 내보내는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-188">SOAP 1.2 allows 0, 1, `false`, and `true` as values, but recommends emitting a canonical representation of `xs:boolean` values (`false`, `true`).</span></span>  
  
-   <span data-ttu-id="ec1c7-189">B1112: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 SOAP 1.1과 SOAP 1.2 버전 SOAP 봉투 모두에 대해 `mustUnderstand` 값 0과 1을 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-189">B1112: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] emits `mustUnderstand` values 0 and 1 for both SOAP 1.1 and SOAP 1.2 versions of the SOAP envelope.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="ec1c7-190">에서는 `xs:boolean` 헤더에 `mustUnderstand`의 전체 값 공간(0, 1, `false`, `true`)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-190"> accepts the entire value space of `xs:boolean` for the `mustUnderstand` header (0, 1, `false`, `true`)</span></span>  
  
#### <a name="soap-faults"></a><span data-ttu-id="ec1c7-191">SOAP 오류</span><span class="sxs-lookup"><span data-stu-id="ec1c7-191">SOAP Faults</span></span>  
 <span data-ttu-id="ec1c7-192">다음은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 관련 SOAP 오류 구현 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-192">The following is a list of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-specific SOAP fault implementations.</span></span>  
  
-   <span data-ttu-id="ec1c7-193">B2121: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] SOAP 1.1 오류 코드는 다음 반환: `s11:mustUnderstand`, `s11:Client`, 및 `s11:Server`합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-193">B2121: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] returns the following SOAP 1.1 Fault Codes: `s11:mustUnderstand`, `s11:Client`, and `s11:Server`.</span></span>  
  
-   <span data-ttu-id="ec1c7-194">B2122: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 `s12:MustUnderstand`, `s12:Sender` 및 `s12:Receiver`와 같은 SOAP 1.2 오류 코드를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-194">B2122: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] returns the following SOAP 1.2 Fault Codes: `s12:MustUnderstand`, `s12:Sender`, and `s12:Receiver`.</span></span>  
  
### <a name="http-binding"></a><span data-ttu-id="ec1c7-195">HTTP 바인딩</span><span class="sxs-lookup"><span data-stu-id="ec1c7-195">HTTP Binding</span></span>  
  
#### <a name="soap-11-http-binding"></a><span data-ttu-id="ec1c7-196">SOAP 1.1 HTTP 바인딩</span><span class="sxs-lookup"><span data-stu-id="ec1c7-196">SOAP 1.1 HTTP Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="ec1c7-197">에서는 Basic Profile 1.1 사양 단원 3.4에 따라 SOAP1.1 HTTP 바인딩을 다음과 같이 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-197"> implements SOAP1.1 HTTP binding following the Basic Profile 1.1 specification section 3.4 with the following clarifications:</span></span>  
  
-   <span data-ttu-id="ec1c7-198">B2211: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스에서는 HTTP POST 요청의 리디렉션을 구현하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-198">B2211: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service does not implement redirection of HTTP POST requests.</span></span>  
  
-   <span data-ttu-id="ec1c7-199">B2212: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트는 3.4.8에 따라 HTTP 쿠키를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-199">B2212: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] clients support HTTP Cookies in accordance with 3.4.8.</span></span>  
  
#### <a name="soap-12-http-binding"></a><span data-ttu-id="ec1c7-200">SOAP 1.2 HTTP 바인딩</span><span class="sxs-lookup"><span data-stu-id="ec1c7-200">SOAP 1.2 HTTP Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="ec1c7-201">에서는 SOAP12Part2(SOAP 1.2-part 2) 사양에 설명된 대로 SOAP 1.2 HTTP 바인딩을 다음과 같이 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-201"> implements SOAP 1.2 HTTP binding as described in the SOAP 1.2-part 2 (SOAP12Part2) specification with the following clarifications.</span></span>  
  
 <span data-ttu-id="ec1c7-202">SOAP 1.2에는 `application/soap+xml` 미디어 유형에 대한 선택적 작업 매개 변수가 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-202">SOAP 1.2 introduced an optional action parameter for the `application/soap+xml` media type.</span></span> <span data-ttu-id="ec1c7-203">이 매개 변수는 WS-Addressing을 사용하지 않을 때 SOAP 메시지 본문을 구문 분석할 필요 없이 메시지 디스패치를 최적화하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-203">This parameter is useful to optimize message dispatch without requiring that the body of the SOAP message be parsed when WS-Addressing is not used.</span></span>  
  
-   <span data-ttu-id="ec1c7-204">R2221: `application/soap+xml` 작업 매개 변수(SOAP 1.2 요청에 있는 경우)는 해당 WSDL 바인딩 내 `soapAction` 요소의 `wsoap12:operation` 특성과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-204">R2221: The `application/soap+xml` action parameter, when present on a SOAP 1.2 request, must match the `soapAction` attribute on the `wsoap12:operation` element inside the corresponding WSDL binding.</span></span>  
  
-   <span data-ttu-id="ec1c7-205">R2222: WS-Addressing 2004/08 또는 WS-Addressing 1.0을 사용할 경우 `application/soap+xml` 작업 매개 변수(SOAP 1.2 메시지에 있는 경우)가 `wsa:Action`과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-205">R2222: The `application/soap+xml` action parameter, when present on a SOAP 1.2 message, must match `wsa:Action` when WS-Addressing 2004/08 or WS-Addressing 1.0 are used.</span></span>  
  
 <span data-ttu-id="ec1c7-206">WS-Addressing을 사용하지 않고 들어오는 요청에 작업 매개 변수가 없는 경우 메시지 `Action`이 지정되지 않은 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-206">When WS-Addressing is disabled and an incoming request does not contain an action parameter, message `Action` is considered not specified.</span></span>  
  
## <a name="ws-addressing"></a><span data-ttu-id="ec1c7-207">WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="ec1c7-207">WS-Addressing</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="ec1c7-208">에서는 다음과 같은 세 가지 버전의 WS-Addressing을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-208"> implements 3 versions of WS-Addressing:</span></span>  
  
-   <span data-ttu-id="ec1c7-209">WS-Addressing 2004/08</span><span class="sxs-lookup"><span data-stu-id="ec1c7-209">WS-Addressing 2004/08</span></span>  
  
-   <span data-ttu-id="ec1c7-210">W3C Web Services Addressing 1.0 Core(ADDR10-CORE) 및 SOAP 바인딩(ADDR10-SOAP)</span><span class="sxs-lookup"><span data-stu-id="ec1c7-210">W3C Web Services Addressing 1.0 Core  (ADDR10-CORE) and SOAP Binding (ADDR10-SOAP)</span></span>  
  
-   <span data-ttu-id="ec1c7-211">WS-Addressing 1.0 - Metadata</span><span class="sxs-lookup"><span data-stu-id="ec1c7-211">WS-Addressing 1.0 - Metadata</span></span>  
  
### <a name="endpoint-references"></a><span data-ttu-id="ec1c7-212">끝점 참조</span><span class="sxs-lookup"><span data-stu-id="ec1c7-212">Endpoint References</span></span>  
 <span data-ttu-id="ec1c7-213">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 구현되는 모든 WS-Addressing 버전에서는 끝점 참조를 사용하여 끝점을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-213">All versions of WS-Addressing that [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implements use endpoint references to describe endpoints.</span></span>  
  
#### <a name="endpoint-references-and-ws-addressing-versions"></a><span data-ttu-id="ec1c7-214">끝점 참조 및 WS-Addressing 버전</span><span class="sxs-lookup"><span data-stu-id="ec1c7-214">Endpoint References and WS-Addressing Versions</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="ec1c7-215">에서는 WS-Addressing을 사용하는 많은 인프라 프로토콜을 구현하며 특히, `EndpointReference` 요소 및 `W3C.WsAddressing.EndpointReferenceType` 클래스(예: WS-ReliableMessaging, WS-SecureConversation, WS-Trust)를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-215"> implements a number of the infrastructure protocols that use WS-Addressing and in particular the `EndpointReference` element and `W3C.WsAddressing.EndpointReferenceType` class (for example, WS-ReliableMessaging, WS-SecureConversation, and WS-Trust).</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="ec1c7-216">에서는 WS-Addressing 버전을 다른 인프라 프로토콜과 함께 사용할 수 있도록 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-216"> supports the use of either version of WS-Addressing with other infrastructure protocols.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="ec1c7-217"> 끝점은 끝점당 하나의 WS-Addressing 버전을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-217"> endpoints support one version of WS-Addressing per endpoint.</span></span>  
  
 <span data-ttu-id="ec1c7-218">R3111에서 `EndpointReference` 끝점과 교환된 메시지에 사용된 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 요소 또는 형식의 네임스페이스는 이 끝점에서 구현된 WS-Addressing 버전과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-218">For R3111, the namespace for the `EndpointReference` element or type used in messages exchanged with a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] endpoint must match the version of WS-Addressing implemented by this endpoint.</span></span>  
  
 <span data-ttu-id="ec1c7-219">예를 들어, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 끝점에서 WS-ReliableMessaging을 구현하는 경우 `AcksTo`에서 이러한 끝점에 의해 반환되는 `CreateSequenceResponse` 헤더는 `EncodingBinding` 요소가 이 끝점에 대해 지정하는 WS-Addressing 버전을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-219">For example, if a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] endpoint implements WS-ReliableMessaging, the `AcksTo` header returned by such an endpoint inside `CreateSequenceResponse` uses the WS-Addressing version that the `EncodingBinding` element specifies for this endpoint.</span></span>  
  
#### <a name="endpoint-references-and-metadata"></a><span data-ttu-id="ec1c7-220">끝점 참조 및 메타데이터</span><span class="sxs-lookup"><span data-stu-id="ec1c7-220">Endpoint References and Metadata</span></span>  
 <span data-ttu-id="ec1c7-221">대부분의 시나리오에서는 지정된 끝점에 대해 메타데이터 또는 메타데이터 참조를 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-221">A number of scenarios require communicating metadata or a reference to metadata for a given endpoint.</span></span>  
  
 <span data-ttu-id="ec1c7-222">B3121: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 WS-MetadataExchange(MEX) 사양 단원 6에 명시된 메커니즘을 사용하여 값으로 또는 참조로 끝점 참조에 대한 메타데이터를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-222">B3121: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] employs mechanisms described in the WS-MetadataExchange (MEX) specification Section 6 to include metadata for endpoint references by value or by reference.</span></span>  
  
 <span data-ttu-id="ec1c7-223">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스에서 http://sts.fabrikam123.com의 토큰 발급자가 발급한 SAML(Security Assertions Markup Language) 토큰을 사용하여 인증해야 하는 시나리오를 생각해 봅니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 끝점에서는 토큰 발급자를 가리키는 중첩 `sp:IssuedToken` 어설션과 함께 `sp:Issuer` 어설션을 사용하여 이 인증 요구 사항을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-223">Consider a scenario where a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service requires authentication using a Security Assertions Markup Language (SAML) token issued by the token issuer at http://sts.fabrikam123.com. The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] endpoint describes this authentication requirement by using `sp:IssuedToken` assertion with a nested `sp:Issuer` assertion pointing to the token issuer.</span></span> <span data-ttu-id="ec1c7-224">`sp:Issuer` 어설션에 액세스하는 클라이언트 응용 프로그램은 토큰 발급자 끝점과 통신하는 방법을 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-224">Client applications that access the `sp:Issuer` assertion need to know how to communicate with the token issuer endpoint.</span></span> <span data-ttu-id="ec1c7-225">클라이언트는 토큰 발급자에 대한 메타데이터를 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-225">The client needs to know metadata about the token issuer.</span></span> <span data-ttu-id="ec1c7-226">MEX에 정의된 끝점 참조 메타데이터 확장을 사용하여 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 토큰 발급자 메타데이터에 대한 참조를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-226">Using the endpoint reference metadata extensions defined in MEX, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] provides a reference to the token issuer metadata.</span></span>  
  
```xml  
<sp:IssuedToken>  
  <sp:Issuer>  
    <wsa10:Address>  
      http://sts.fabrikam123.com  
    </wsa10:Address>  
    <wsa10:Metadata>  
      <mex:Metadata>  
        <mex:MetadataSection>  
          <mex:MetadataReference>  
            <wsa10:Address>  
              http://sts.fabrikam123.com/mex  
            </wsa10:Address>  
          </mex:MetadataReference>  
        </mex:MetadataSection>  
      </mex:Metadata>  
    </wsa10:Metadata>  
  </sp:Issuer>  
</sp:IssuedToken>  
```  
  
### <a name="message-addressing-headers"></a><span data-ttu-id="ec1c7-227">메시지 주소 지정 헤더</span><span class="sxs-lookup"><span data-stu-id="ec1c7-227">Message Addressing Headers</span></span>  
  
#### <a name="message-headers"></a><span data-ttu-id="ec1c7-228">메시지 헤더</span><span class="sxs-lookup"><span data-stu-id="ec1c7-228">Message Headers</span></span>  
 <span data-ttu-id="ec1c7-229">두 Ws-addressing 버전에 대해 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 사양에 설명 된 대로 다음 메시지 헤더를 사용 하 여 `wsa:To`, `wsa:ReplyTo`, `wsa:Action`, `wsa:MessageID`, 및 `wsa:RelatesTo`합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-229">For both WS-Addressing versions, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses the following message headers as prescribed by the specifications `wsa:To`, `wsa:ReplyTo`, `wsa:Action`, `wsa:MessageID`,and `wsa:RelatesTo`.</span></span>  
  
 <span data-ttu-id="ec1c7-230">B3211: 모든 WS-Addressing 버전에 대해 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 WS-Addressing 메시지 헤더인 `wsa:FaultTo` 및 `wsa:From`을 사용하지만 이 헤더를 즉시 생성하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-230">B3211: For all WS-Addressing versions, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] honors, but does not produce out of the box, WS-Addressing message headers `wsa:FaultTo` and `wsa:From`.</span></span>  
  
 <span data-ttu-id="ec1c7-231">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응용 프로그램과 상호 작용하는 응용 프로그램은 이러한 메시지 헤더를 추가할 수 있으며 이에 따라 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 해당 메시지 헤더를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-231">Applications that interact with [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications can add these message headers and [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] will process them accordingly.</span></span>  
  
#### <a name="reference-parameters-and-properties"></a><span data-ttu-id="ec1c7-232">참조 매개 변수 및 속성</span><span class="sxs-lookup"><span data-stu-id="ec1c7-232">Reference Parameters and Properties</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="ec1c7-233">에서는 끝점 참조 매개 변수 및 참조 속성을</span><span class="sxs-lookup"><span data-stu-id="ec1c7-233"> implements processing of endpoint reference parameters and reference p</span></span>  
  
 <span data-ttu-id="ec1c7-234">해당 사양에 따라 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-234">roperties in accordance with respective specifications.</span></span>  
  
 <span data-ttu-id="ec1c7-235">B3221: WS-Addressing 2004/08을 사용하도록 구성된 경우 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 끝점은 참조 속성과 참조 매개 변수의 처리를 구분하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-235">B3221: When configured to use WS-Addressing 2004/08, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] endpoints do not differentiate between processing Reference Properties and Reference Parameters.</span></span>  
  
### <a name="message-exchange-patterns"></a><span data-ttu-id="ec1c7-236">메시지 교환 패턴</span><span class="sxs-lookup"><span data-stu-id="ec1c7-236">Message Exchange Patterns</span></span>  
 <span data-ttu-id="ec1c7-237">웹 서비스 작업 호출에 관련 된 메시지의 시퀀스 라고는 *메시지 교환 패턴*합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-237">The sequence of messages involved in the Web service operation invocation is referred to as the *message exchange pattern*.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="ec1c7-238">는 단방향, 요청-회신 및 이중 메시지 교환 패턴을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-238"> supports one-way, request-reply, and duplex message exchange patterns.</span></span> <span data-ttu-id="ec1c7-239">이 단원에서는 사용 중인 메시지 교환 패턴에 따른 메시지 처리에 대한 WS-Addressing 요구 사항에 대해 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-239">This section clarifies WS-Addressing requirements on message processing depending on the message exchange pattern being used.</span></span>  
  
 <span data-ttu-id="ec1c7-240">이 단원에서 요청자는 첫 번째 메시지를 보내고 응답자는 첫 번째 메시지를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-240">Throughout this section, the requester sends the first message and the responder receives the first message.</span></span>  
  
#### <a name="one-way-message"></a><span data-ttu-id="ec1c7-241">단방향 메시지</span><span class="sxs-lookup"><span data-stu-id="ec1c7-241">One-Way Message</span></span>  
 <span data-ttu-id="ec1c7-242">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 끝점이 지정된 `Action`을 포함하는 메시지를 지원하도록 구성되어 단방향 패턴을 따르는 경우 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 끝점은 다음과 같은 동작 및 요구 사항을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-242">When a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] endpoint is configured to support messages with a given `Action` to follow a one-way pattern, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] endpoint follows the following behaviors and requirements.</span></span> <span data-ttu-id="ec1c7-243">별도로 지정하지 않는 한 동작과 규칙은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 지원되는 두 WS-Addressing 버전 모두에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-243">Unless otherwise specified, behaviors and rules apply for both versions of WS-Addressing supported in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span></span>  
  
-   <span data-ttu-id="ec1c7-244">R3311: 요청자는 `wsa:To`, `wsa:Action` 및 끝점 참조에 지정된 모든 참조 매개 변수에 대한 헤더를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-244">R3311: The requester must include `wsa:To`, `wsa:Action`, and headers for all reference parameters specified by the endpoint reference.</span></span> <span data-ttu-id="ec1c7-245">WS-Addressing 2004/08을 사용하고 [reference properties]이 끝점 참조에 지정된 경우에도 해당 헤더를 메시지에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-245">When WS-Addressing 2004/08 is used and [reference properties] are specified by the endpoint reference, the corresponding headers must be added to the message too.</span></span>  
  
-   <span data-ttu-id="ec1c7-246">B3312: 요청자가 `MessageID`, `ReplyTo` 및 `FaultTo` 헤더를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-246">B3312: The requester may include `MessageID`, `ReplyTo`, and `FaultTo` headers.</span></span> <span data-ttu-id="ec1c7-247">이러한 헤더는 수신자 인프라에서 무시되고 응용 프로그램으로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-247">The receiver infrastructure will ignore them, and they will be passed to the application.</span></span>  
  
-   <span data-ttu-id="ec1c7-248">R3313: HTTP를 사용하고 HTTP 응답 레그에 전송 중인 메시지가 없을 때 응답자는 HTTP 202 상태 코드와 함께 본문이 빈 HTTP 응답을 보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-248">R3313: When HTTP is used and no message is being sent on the HTTP response leg, the responder must send an HTTP response with an empty body and an HTTP 202 status code.</span></span>  
  
     <span data-ttu-id="ec1c7-249">HTTP 전송을 사용 중이고 작업 계약에 메시지가 단방향으로 선언되어 있는 경우에도 인프라 메시지를 보내는 데 HTTP 응답을 사용할 수 있습니다. 예를 들어, 신뢰할 수 있는 메시징을 사용하여 HTTP 응답에서 `SequenceAcknowledgement` 메시지를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-249">When the HTTP transport is in use and the operation contract declares a message one-way, the HTTP response can still be used for sending infrastructure messages—for example, reliable messaging can send a `SequenceAcknowledgement` message on an HTTP response.</span></span>  
  
-   <span data-ttu-id="ec1c7-250">B3314: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응답자는 단방향 메시지에 대한 응답으로 오류 메시지를 보내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-250">B3314: The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] responder does not send a fault message in response to a one-way message.</span></span>  
  
#### <a name="request-reply"></a><span data-ttu-id="ec1c7-251">요청-회신</span><span class="sxs-lookup"><span data-stu-id="ec1c7-251">Request-Reply</span></span>  
 <span data-ttu-id="ec1c7-252">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 끝점이 지정된 `Action`을 포함하는 메시지가 요청-회신 패턴을 따르도록 구성되어 있는 경우 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 끝점은 다음과 같은 동작 및 요구 사항을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-252">When a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] endpoint is configured for a message with a given `Action` to follow the request-reply pattern, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] endpoint follows the behaviors and requirements below.</span></span> <span data-ttu-id="ec1c7-253">별도로 지정하지 않는 한 동작과 규칙은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 지원되는 두 WS-Addressing 버전 모두에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-253">Unless specified otherwise, behaviors and rules apply for both versions of WS-Addressing supported in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span></span>  
  
-   <span data-ttu-id="ec1c7-254">R3321: 요청자는 요청에 포함 해야 `wsa:To`, `wsa:Action`, `wsa:MessageID`, 모든 참조 매개 변수 또는 참조 속성 (또는 둘 다) 끝점 참조에 지정 된에 대 한 헤더입니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-254">R3321: The requester must include in the request `wsa:To`, `wsa:Action`, `wsa:MessageID`, and headers for all reference parameters or reference properties (or both) specified by the endpoint reference.</span></span>  
  
-   <span data-ttu-id="ec1c7-255">R3322: WS-Addressing 2004/08을 사용하는 경우 `ReplyTo`도 요청에 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-255">R3322: When WS-Addressing 2004/08 is used, `ReplyTo` must also be included in the request.</span></span>  
  
-   <span data-ttu-id="ec1c7-256">R3323: WS-Addressing 1.0을 사용하고 `ReplyTo`가 요청에 없는 경우 [address] 속성이 "http://www.w3.org/2005/08/addressing/anonymous"와 같은 기본 끝점 참조가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-256">R3323: When WS-Addressing 1.0 is used and `ReplyTo` is not present in the request, a default endpoint reference with the [address] property equal to "http://www.w3.org/2005/08/addressing/anonymous" is used.</span></span>  
  
-   <span data-ttu-id="ec1c7-257">R3324: 요청자 있어야 `wsa:To`, `wsa:Action`, 및 `wsa:RelatesTo` 회신 메시지의 헤더 뿐 아니라 모든 참조 매개 변수 또는 참조 속성 (또는 둘 다)으로 지정 된 헤더는 `ReplyTo` 끝점 참조에는 요청입니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-257">R3324: The requester must include `wsa:To`, `wsa:Action`, and `wsa:RelatesTo` headers in the reply message, as well as headers for all reference parameters or reference properties (or both) specified by the `ReplyTo` endpoint reference in the request.</span></span>  
  
### <a name="web-services-addressing-faults"></a><span data-ttu-id="ec1c7-258">Web Services Addressing 오류</span><span class="sxs-lookup"><span data-stu-id="ec1c7-258">Web Services Addressing Faults</span></span>  
 <span data-ttu-id="ec1c7-259">R3411: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 WS-Addressing 2004/08에 정의된 다음과 같은 오류를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-259">R3411: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] produces the following faults defined by WS-Addressing 2004/08.</span></span>  
  
|<span data-ttu-id="ec1c7-260">코드</span><span class="sxs-lookup"><span data-stu-id="ec1c7-260">Code</span></span>|<span data-ttu-id="ec1c7-261">원인</span><span class="sxs-lookup"><span data-stu-id="ec1c7-261">Cause</span></span>|  
|----------|-----------|  
|<span data-ttu-id="ec1c7-262">wsa:DestinationUnreachable</span><span class="sxs-lookup"><span data-stu-id="ec1c7-262">wsa:DestinationUnreachable</span></span>|<span data-ttu-id="ec1c7-263">이 채널에 대해 설정된 회신 주소와 다른 `ReplyTo`를 사용하여 메시지가 도착했습니다. 받는 사람 헤더에 지정된 주소에서 수신 대기하는 끝점이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-263">The message arrived with a `ReplyTo` that is different from the reply address established for this channel; there is no endpoint listening at the address specified in the To header.</span></span>|  
|<span data-ttu-id="ec1c7-264">wsa:ActionNotSupported</span><span class="sxs-lookup"><span data-stu-id="ec1c7-264">wsa:ActionNotSupported</span></span>|<span data-ttu-id="ec1c7-265">끝점과 연결된 인프라 채널 또는 디스패처가 `Action` 헤더에 지정된 동작을 인식하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-265">the infrastructure channels or dispatcher associated with the endpoint do not recognize the action specified in the `Action` header.</span></span>|  
  
 <span data-ttu-id="ec1c7-266">R3412: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 WS-Addressing 1.0에 정의된 다음과 같은 오류를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-266">R3412: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] produces the following faults defined by WS-Addressing 1.0.</span></span>  
  
|<span data-ttu-id="ec1c7-267">코드</span><span class="sxs-lookup"><span data-stu-id="ec1c7-267">Code</span></span>|<span data-ttu-id="ec1c7-268">원인</span><span class="sxs-lookup"><span data-stu-id="ec1c7-268">Cause</span></span>|  
|----------|-----------|  
|<span data-ttu-id="ec1c7-269">wsa10:InvalidAddressingHeader</span><span class="sxs-lookup"><span data-stu-id="ec1c7-269">wsa10:InvalidAddressingHeader</span></span>|<span data-ttu-id="ec1c7-270">중복 `wsa:To`, `wsa:ReplyTo`, `wsa:From` 또는 `wsa:MessageID`합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-270">Duplicate `wsa:To`, `wsa:ReplyTo`, `wsa:From` or `wsa:MessageID`.</span></span> <span data-ttu-id="ec1c7-271">중복 `wsa:RelatesTo` 같은 `RelationshipType`합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-271">Duplicate `wsa:RelatesTo` with the same `RelationshipType`.</span></span>|  
|<span data-ttu-id="ec1c7-272">wsa10:MessageAddressingHeaderRequired</span><span class="sxs-lookup"><span data-stu-id="ec1c7-272">wsa10:MessageAddressingHeaderRequired</span></span>|<span data-ttu-id="ec1c7-273">필수 주소 지정 헤더가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-273">The required Addressing header is missing.</span></span>|  
|<span data-ttu-id="ec1c7-274">wsa10:DestinationUnreachable</span><span class="sxs-lookup"><span data-stu-id="ec1c7-274">wsa10:DestinationUnreachable</span></span>|<span data-ttu-id="ec1c7-275">이 채널에 대해 설정된 회신 주소와 다른 `ReplyTo`를 사용하여 메시지가 도착했습니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-275">The message arrived with a `ReplyTo` that is different from the reply address established for this channel.</span></span> <span data-ttu-id="ec1c7-276">받는 사람 헤더에 지정된 주소에서 수신 대기하는 끝점이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-276">There is no endpoint listening at the address specified in the To header.</span></span>|  
|<span data-ttu-id="ec1c7-277">wsa10:ActionNotSupported</span><span class="sxs-lookup"><span data-stu-id="ec1c7-277">wsa10:ActionNotSupported</span></span>|<span data-ttu-id="ec1c7-278">`Action` 헤더에 지정된 동작이 끝점과 연결된 디스패처 또는 인프라 채널에서 인식되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-278">An action specified in the `Action` header is not recognized by the infrastructure channels or dispatcher associated with the endpoint.</span></span>|  
|<span data-ttu-id="ec1c7-279">wsa10:EndpointUnavailable</span><span class="sxs-lookup"><span data-stu-id="ec1c7-279">wsa10:EndpointUnavailable</span></span>|<span data-ttu-id="ec1c7-280">RM 채널에서 이 오류를 다시 보냅니다. 이는 끝점에서 `CreateSequence` 메시지의 주소 지정 헤더를 검사하여 시퀀스를 처리하지 않는다는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-280">The RM channel sends this fault back, indicating the endpoint will not process the sequence based upon examination of the `CreateSequence` message’s addressing headers.</span></span>|  
  
 <span data-ttu-id="ec1c7-281">위 표의 코드가 SOAP 1.1의 경우 `FaultCode`에 매핑되고 SOAP 1.2의 경우 `SubCode`(Code=Sender)에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-281">Code in the preceding tables maps to `FaultCode` in SOAP 1.1 and `SubCode` (with Code=Sender) in SOAP 1.2.</span></span>  
  
### <a name="wsdl-11-binding-and-ws-policy-assertions"></a><span data-ttu-id="ec1c7-282">WSDL 1.1 바인딩 및 WS-Policy Assertion</span><span class="sxs-lookup"><span data-stu-id="ec1c7-282">WSDL 1.1 Binding and WS-Policy Assertions</span></span>  
  
#### <a name="indicating-use-of-ws-addressing"></a><span data-ttu-id="ec1c7-283">WS-Addressing 사용 지정</span><span class="sxs-lookup"><span data-stu-id="ec1c7-283">Indicating Use of WS-Addressing</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="ec1c7-284">에서는 정책 어설션을 사용하여 특정 WS-Addressing 버전에 대한 끝점 지원을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-284"> uses policy assertions to indicate endpoint support for a particular WS-Addressing version.</span></span>  
  
 <span data-ttu-id="ec1c7-285">다음 정책 어설션은 끝점 정책 주체가 [WS-PA]이고 끝점에서 보내거나 받은 메시지가 WS-Addressing 2004/08을 사용해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-285">The following policy assertion has Endpoint Policy Subject [WS-PA] and indicates messages sent and received from the endpoint must use WS-Addressing 2004/08.</span></span>  
  
```xml  
<wsap:UsingAddressing />  
```  
  
 <span data-ttu-id="ec1c7-286">이 정책 어설션은 WS-Addressing 2004/08 사양을 보완합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-286">This policy assertion augments the WS-Addressing 2004/08 specification.</span></span>  
  
 <span data-ttu-id="ec1c7-287">다음 정책 어설션은 보내거나 받은 메시지가 WS-Addressing 1.0을 사용해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-287">The following policy assertion this indicates that messages sent/received must use WS-Addressing 1.0.</span></span>  
  
```xml
<wsam:Addressing/>   
```  
  
 <span data-ttu-id="ec1c7-288">다음 정책 어설션은 끝점 정책 주체가 [WS-PA]이고 끝점에서 보내거나 받은 메시지가 WS-Addressing 2004/08을 사용해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-288">The following policy assertion has an Endpoint Policy Subject [WS-PA] and indicates that messages sent and received from the endpoint must use WS-Addressing 2004/08.</span></span>  
  
```xml  
<wsaw10:UsingAddressing />  
```  
  
 <span data-ttu-id="ec1c7-289">`wsaw10:UsingAddressing` 요소는 [WS-Addressing-WSDL]에서 가져온 것이며 해당 사양 단원 3.1.2에 따라 WS-Policy 컨텍스트에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-289">The `wsaw10:UsingAddressing` element is borrowed from [WS-Addressing-WSDL] and is used in the context of WS-Policy in compliance with that specification, section 3.1.2.</span></span>  
  
 <span data-ttu-id="ec1c7-290">주소 지정을 사용해도 WSDL 1.1, SOAP 1.1 및 SOAP 1.2 HTTP 바인딩의 의미 체계가 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-290">Use of Addressing does not alter the semantics of WSDL 1.1, SOAP 1.1, and SOAP 1.2 HTTP Bindings.</span></span> <span data-ttu-id="ec1c7-291">예를 들어, 주소 지정 및 WSDL SOAP 1.x HTTP 바인딩을 사용하는 끝점에 보낸 요청에 대한 회신이 필요한 경우 HTTP 응답을 사용하여 회신을 보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-291">For example, if a reply is expected to a request that is sent to an endpoint that uses Addressing and WSDL SOAP 1.x HTTP binding, the reply must be sent by using the HTTP response.</span></span>  
  
 <span data-ttu-id="ec1c7-292">http 응답을 통해 전송되는 회신의 경우 WS-AM 어설션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-292">For replies sent over the http response, the WS-AM assertion is:</span></span>  
  
```xml  
<wsam:AnonymousResponses/>  
```  
  
 <span data-ttu-id="ec1c7-293">완성된 정책 어설션은 다음과 같을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-293">The complete policy assertion might look like this:</span></span>  
  
```xml  
<wsam:Addressing>  
    <wsp:Policy>  
        <wsam:AnonymousResponses />   
    </wsp:Policy>  
</wsam:Addressing>  
```  
  
 <span data-ttu-id="ec1c7-294">그러나 요청자와 응답자 간에 설정된 두 개의 독립적인 역방향 HTTP 연결을 활용하는 메시지 교환 패턴이 있습니다(예: 응답자가 보낸 원하지 않은 단방향 메시지).</span><span class="sxs-lookup"><span data-stu-id="ec1c7-294">However, there are message exchange patterns that benefit from having two independent converse HTTP connections established between the requester and the responder, for example, unsolicited one-way messages sent by the responder.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="ec1c7-295">에서는 두 기본 전송 채널에서 복합 이중 채널을 설정하는 데 사용할 수 있는 기능을 제공합니다. 복합 이중 채널에서는 입력 메시지에 하나의 채널이 사용되고 출력 메시지에 나머지 하나의 채널이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-295"> offers a feature by which two underlying transport channels can form a Composite Duplex channel, where one channel is used for input messages and the other is used for output messages.</span></span> <span data-ttu-id="ec1c7-296">HTTP 전송의 경우 복합 이중 채널은 두 개의 역방향 HTTP 연결을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-296">In the case of the HTTP Transport, Composite Duplex provides two converse HTTP connections.</span></span> <span data-ttu-id="ec1c7-297">요청자가 한 연결을 사용하여 메시지를 응답자에게 보내고, 응답자는 다른 연결을 사용하여 메시지를 요청자에게 다시 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-297">The requester uses one connection to send messages to the responder, and the responder uses the other to send messages back to the requester.</span></span>  
  
 <span data-ttu-id="ec1c7-298">별도의 http 요청을 통해 전송되는 회신의 경우 WS-AM 어설션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-298">For replies sent over separate http requests, the ws-am assertion is</span></span>  
  
```xml  
<wsam:NonAnonymousResponses/>  
```  
  
 <span data-ttu-id="ec1c7-299">완성된 정책 어설션은 다음과 같을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-299">The complete policy assertion might look like this:</span></span>  
  
```xml  
<wsam:Addressing>  
    <wsp:Policy>  
      <wsam:NonAnonymousResponses />   
   </wsp:Policy>  
  </wsam:Addressing>  
```  
  
 <span data-ttu-id="ec1c7-300">WSDL 1.1 SOAP 1.x HTTP 바인딩을 사용하는 끝점에서 끝점 정책 주체가 [WS-PA]인 다음 어설션을 사용하려면 요청자와 응답자 간에 주고 받는 메시지 흐름에 각각 사용할 두 개의 개별적인 역방향 HTTP 연결이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-300">Use of the following assertion that has Endpoint Policy Subject [WS-PA] on endpoints that use WSDL 1.1 SOAP 1.x HTTP bindings requires two separate converse HTTP connections to be used for messages flowing from requester to responder and responder to requester, respectively.</span></span>  
  
```xml  
<cdp:CompositeDuplex/>  
```  
  
 <span data-ttu-id="ec1c7-301">앞의 문에 따라 요청 메시지의 `wsa:ReplyTo` 헤더에 대해 다음 요구 사항이 충족되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-301">The previous statement leads to the following requirements on the `wsa:ReplyTo` header for request messages:</span></span>  
  
-   <span data-ttu-id="ec1c7-302">R3514: 끝점이 WSDL 1.1 SOAP 1.x HTTP 바인딩을 사용하고 `ReplyTo` 또는 `[address]` 어설션이 `wsap10:UsingAddressing`와 함께 연결된 정책 대안이 있는 경우 끝점에 보낸 요청 메시지에 `wsap:UsingAddressing` 속성이 "http://www.w3.org/2005/08/addressing/anonymous"가 아닌 `cdp:CompositeDuplex` 헤더가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-302">R3514: Request messages sent to an endpoint must have a `ReplyTo` header with the `[address]` property not equal to "http://www.w3.org/2005/08/addressing/anonymous" if the endpoint uses a WSDL 1.1 SOAP 1.x HTTP binding and has a policy alternative with a `wsap10:UsingAddressing` or `wsap:UsingAddressing` assertion coupled with `cdp:CompositeDuplex` attached.</span></span>  
  
-   <span data-ttu-id="ec1c7-303">R3515: 끝점이 WSDL 1.1 SOAP 1.x HTTP 바인딩을 사용하고 `ReplyTo` 어설션은 연결되어 있지만 `[address]` 어설션은 연결되지 않은 정책 대안이 있는 경우 끝점에 보낸 요청 메시지에 `ReplyTo` 속성이 "http://www.w3.org/2005/08/addressing/anonymous"인 `wsap10:UsingAddressing` 헤더가 있거나 `cdp:CompositeDuplex` 헤더가 전혀 없어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-303">R3515: Request messages sent to an endpoint must have a `ReplyTo` header with the `[address]` property equal to "http://www.w3.org/2005/08/addressing/anonymous", or not have a `ReplyTo` header at all, if the endpoint uses a WSDL 1.1 SOAP 1.x HTTP binding and has a policy alternative with `wsap10:UsingAddressing` assertion and no `cdp:CompositeDuplex` assertion attached.</span></span>  
  
-   <span data-ttu-id="ec1c7-304">R3516: 끝점이 WSDL 1.1 SOAP 1.x HTTP 바인딩을 사용하고 `ReplyTo` 어설션은 연결되어 있지만 `[address]` 어설션은 연결되지 않은 정책 대안이 있는 경우 끝점에 보낸 요청 메시지에 `wsap:UsingAddressing` 속성이 "http://www.w3.org/2005/08/addressing/anonymous"인 `cdp:CompositeDuplex` 헤더가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-304">R3516: Request messages sent to an endpoint must have a `ReplyTo` header with an `[address]` property equal to "http://www.w3.org/2005/08/addressing/anonymous" if the endpoint uses a WSDL 1.1 SOAP 1.x HTTP binding and has a policy alternative with `wsap:UsingAddressing` assertion and no `cdp:CompositeDuplex` assertion attached.</span></span>  
  
 <span data-ttu-id="ec1c7-305">WS-addressing WSDL 사양에서는 세 개의 텍스트 값(required, optional, prohibited)을 가진 `<wsaw:Anonymous/>`요소를 추가하여`wsa:ReplyTo` 헤더(단원 3.2)에 대한 요구 사항을 나타냄으로써 비슷한 프로토콜 바인딩을 설명하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-305">The WS-addressing WSDL specification attempts to describe similar protocol bindings by introducing an element `<wsaw:Anonymous/>` with three textual values (required, optional, and prohibited) to indicate requirements on the `wsa:ReplyTo` header (section 3.2).</span></span> <span data-ttu-id="ec1c7-306">그러나 해당 요소를 어설션으로 사용하여 대안 교차를 지원하려면 도메인별 확장이 필요하므로, 이러한 요소 정의는 WS-Policy 컨텍스트에서 어설션으로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-306">Unfortunately, such element definition is not particularly usable as an assertion in the context of WS-Policy, because it requires domain-specific extensions to support the intersection of alternatives using such an element as an assertion.</span></span> <span data-ttu-id="ec1c7-307">또한 이러한 요소 정의는 통신 중인 끝점 동작과 반대로 `ReplyTo` 헤더 값을 나타내므로 HTTP 전송에만 해당됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-307">Such element definition also indicates the value of the `ReplyTo` header as opposed to the endpoint behavior on the wire, which makes it specific to HTTP transport.</span></span>  
  
#### <a name="action-definition"></a><span data-ttu-id="ec1c7-308">동작 정의</span><span class="sxs-lookup"><span data-stu-id="ec1c7-308">Action Definition</span></span>  
 <span data-ttu-id="ec1c7-309">WS-Addressing 2004/08에서는 `wsa:Action` 요소에 대한 `wsdl:portType/wsdl:operation/[wsdl:input | wsdl:output | wsdl:fault]` 특성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-309">WS-Addressing 2004/08 defines a `wsa:Action` attribute for the `wsdl:portType/wsdl:operation/[wsdl:input | wsdl:output | wsdl:fault]` elements.</span></span> <span data-ttu-id="ec1c7-310">WS-ADDR10-WSDL(WS-Addressing 1.0 WSDL 바인딩)에서는 비슷한 특성인 `wsaw10:Action`을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-310">WS-Addressing 1.0 WSDL Binding (WS-ADDR10-WSDL) defines a similar attribute, `wsaw10:Action`.</span></span>  
  
 <span data-ttu-id="ec1c7-311">둘 간에는 WS-ADDR의 단원 3.3.2와 WS-ADDR10-WSDL의 단원 4.4.4에 각각 설명된 기본 동작 패턴의 의미 체계만 차이가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-311">The only difference between the two is the default Action pattern semantics described in section 3.3.2 of WS-ADDR and section 4.4.4 of WS-ADDR10-WSDL, respectively.</span></span>  
  
 <span data-ttu-id="ec1c7-312">동일한 `portType` 또는 계약([!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 용어)을 공유하지만 서로 다른 WS-Addressing 버전을 사용하는 두 개의 끝점을 사용하는 것이 바람직합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-312">It is a reasonable to have two endpoints that share the same `portType` (or contract, in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] terminology) but using different versions of WS-Addressing.</span></span> <span data-ttu-id="ec1c7-313">그러나 동작이 `portType`에 정의되어 있고 `portType`을 구현하는 끝점을 통해 변경되지 않아야 할 경우 두 기본 동작 패턴을 모두 지원할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-313">But given that Action is defined by the `portType` and should not change across the endpoints that implement the `portType`, it becomes impossible to support both default action patterns.</span></span>  
  
 <span data-ttu-id="ec1c7-314">이 문제를 해결하기 위해 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 단일 버전의 `Action` 특성을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-314">To resolve this controversy, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] supports a single version of the `Action` attribute.</span></span>  
  
 <span data-ttu-id="ec1c7-315">B3521: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 WS-ADDR10-WSDL에 정의된 대로 `wsaw10:Action` 요소에서 `wsdl:portType/wsdl:operation/[wsdl:input | wsdl:output | wsdl:fault]` 특성을 사용하여 끝점에 사용되는 WS-Addressing 버전에 상관없이 해당 메시지에 대한 `Action` URI를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-315">B3521: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses the `wsaw10:Action` attribute on `wsdl:portType/wsdl:operation/[wsdl:input | wsdl:output | wsdl:fault]` elements as defined in WS-ADDR10-WSDL to determine the `Action` URI for the corresponding messages irrespective of the WS-Addressing version used by the endpoint.</span></span>  
  
#### <a name="use-endpoint-reference-inside-wsdl-port"></a><span data-ttu-id="ec1c7-316">WSDL 포트에서 끝점 참조 사용</span><span class="sxs-lookup"><span data-stu-id="ec1c7-316">Use Endpoint Reference Inside WSDL Port</span></span>  
 <span data-ttu-id="ec1c7-317">WS-ADDR10-WSDL 단원 4.1에서는 `wsdl:port` 자식 요소를 포함하도록 `<wsa10:EndpointReference…/>` 요소를 확장하여 WS-Addressing 용어로 끝점을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-317">WS-ADDR10-WSDL section 4.1 extends the `wsdl:port` element to include the `<wsa10:EndpointReference…/>` child element to describe the endpoint in WS-Addressing terms.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="ec1c7-318">에서는 WS-Addressing 2004/08에서 이 유틸리티를 확장하여 `<wsa:EndpointReference…/>`를 `wsdl:port`의 자식 요소로 나타낼 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-318"> expands this utility on WS-Addressing 2004/08, allowing `<wsa:EndpointReference…/>` to appear as a child element of `wsdl:port`.</span></span>  
  
-   <span data-ttu-id="ec1c7-319">R3531: 끝점에 `<wsaw10:UsingAddressing/>` 정책 어설션과 연결된 정책 대안이 있는 경우 해당`wsdl:port` 요소는`<wsa10:EndpointReference …/>` 자식 요소를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-319">R3531: If an endpoint has an attached policy alternative with a `<wsaw10:UsingAddressing/>` policy assertion, the corresponding `wsdl:port` element can contain a child element `<wsa10:EndpointReference …/>`.</span></span>  
  
-   <span data-ttu-id="ec1c7-320">R3532: 경우는 `wsdl:port` 에 자식 요소가 `<wsa10:EndpointReference …/>`, `wsa10:EndpointReference/wsa10:Address` 자식 요소 값의 값과 일치 해야는 `@address` 형제의 특성 `wsdl:port` / `wsdl:location` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-320">R3532: If a `wsdl:port` contains a child element `<wsa10:EndpointReference …/>`, the `wsa10:EndpointReference/wsa10:Address` child element value must match the value of the `@address` attribute of the sibling `wsdl:port`/`wsdl:location` element.</span></span>  
  
-   <span data-ttu-id="ec1c7-321">R3533: 끝점에 `<wsap:UsingAddressing/>``wsdl:port` 정책 어설션과 연결된 정책 대안이 있는 경우 해당 `<wsa:EndpointReference …/>` 요소는 자식 요소를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-321">R3533: If an endpoint has an attached policy alternative with `<wsap:UsingAddressing/>` policy assertion, the corresponding `wsdl:port` element can contain a child element `<wsa:EndpointReference …/>`.</span></span>  
  
-   <span data-ttu-id="ec1c7-322">R3534: 경우는 `wsdl:port` 에 자식 요소가 `<wsa:EndpointReference …/>`, `wsa:EndpointReference/wsa:Address` 자식 요소 값의 값과 일치 해야는 `@address` 형제의 특성 `wsdl:port` / `wsdl:location` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-322">R3534: If a `wsdl:port` contains a child element `<wsa:EndpointReference …/>`, the `wsa:EndpointReference/wsa:Address` child element value must match the value of the `@address` attribute of the sibling `wsdl:port`/`wsdl:location` element.</span></span>  
  
### <a name="composition-with-ws-security"></a><span data-ttu-id="ec1c7-323">WS-Security를 사용하여 구성</span><span class="sxs-lookup"><span data-stu-id="ec1c7-323">Composition with WS-Security</span></span>  
 <span data-ttu-id="ec1c7-324">WS-ADDR 및 WS-ADDR10의 보안 고려 사항 단원에 따르면 모든 주소 지정 메시지 헤더를 메시지 본문과 함께 서명하여 바인딩하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-324">According to security consideration sections in WS-ADDR and WS-ADDR10, all addressing message headers are recommended to be signed together with the message body to bind them together.</span></span>  
  
 <span data-ttu-id="ec1c7-325">WS-Security가 메시지 무결성 보호를 위해 사용될 경우 WS-Addressing 메시지 헤더뿐 아니라 참조 매개 변수 또는 속성(또는 둘 모두)에서 생성된 헤더를 메시지 본문과 함께 서명해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-325">When WS-Security is used for message integrity protection, WS-Addressing message headers as well as headers resulted from reference parameters or properties (or both) must be signed together with the body of the message.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="ec1c7-326">예제</span><span class="sxs-lookup"><span data-stu-id="ec1c7-326">Examples</span></span>  
  
#### <a name="one-way-message"></a><span data-ttu-id="ec1c7-327">단방향 메시지</span><span class="sxs-lookup"><span data-stu-id="ec1c7-327">One-Way Message</span></span>  
 <span data-ttu-id="ec1c7-328">이 시나리오에서 발신자는 수신자에게 단방향 메시지를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-328">In this scenario, the sender sends a one-way message to the receiver.</span></span> <span data-ttu-id="ec1c7-329">SOAP 1.2, HTTP 1.1 및 W3C WS-Addressing 1.0이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-329">SOAP 1.2, HTTP 1.1, and W3C WS-Addressing 1.0 are used.</span></span>  
  
 <span data-ttu-id="ec1c7-330">요청 메시지 구조: 메시지 헤더는 `wsa10:To` 및 `wsa10:Action` 요소를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-330">The Request Message Structure: The message headers include `wsa10:To` and `wsa10:Action` elements.</span></span> <span data-ttu-id="ec1c7-331">메시지 본문은 응용 프로그램 네임스페이스의 특정 `<app:Ping>` 요소를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-331">The message body includes a specific `<app:Ping>` element from the application namespace.</span></span>  
  
 <span data-ttu-id="ec1c7-332">HTTP 헤더: POST의 대상이 URI에서 일치 하는 `wsa10:To` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-332">HTTP Headers: The destination in POST matches the URI in the `wsa10:To` element.</span></span>  
  
 <span data-ttu-id="ec1c7-333">Content-Type 헤더에는 SOAP 1.2에 필요한 `application/soap+xml` 값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-333">The Content-Type header has the value of `application/soap+xml` as required by SOAP 1.2.</span></span> <span data-ttu-id="ec1c7-334">`charset` 및 `action` 매개 변수가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-334">Parameters `charset` and `action` are included.</span></span> <span data-ttu-id="ec1c7-335">Content-Type 헤더의 `action` 매개 변수가 `wsa10:Action` 메시지 헤더의 값과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-335">The `action` parameter of the Content-Type header matches the value of the `wsa10:Action` message header.</span></span>  
  
```  
POST http://fabrikam123.com/Service HTTP/1.1  
Content-Type: application/soap+xml; charset=utf-8;    
              action="http://fabrikam123.com/Service/OneWay"  
Host: 131.107.72.15  
Content-Length: 1501  
Expect: 100-continue  
Proxy-Connection: Keep-Alive  
<s12:Envelope>  
  <s12:Header>  
    <wsa10:To s12:mustUnderstand="1">  
        http://fabrikam123.com/Service  
    </wsa10:To>  
    <wsa10:Action s12:mustUnderstand="1">  
        http://fabrikam123.com/Service/OneWay   
    </wsa10:Action>  
  </s12:Header>  
  <s12:Body>  
    <Ping xmlns="http://fabrikam123.com/Service/">  
      <Text>Hello World</Text>  
    </Ping>  
  </s12:Body>  
</s12:Envelope>  
```  
  
 <span data-ttu-id="ec1c7-336">수신자는 빈 HTTP 응답 및 상태 202를 사용하여 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-336">The receiver responds with an empty HTTP response and status 202.</span></span> <span data-ttu-id="ec1c7-337">HTTP 응답의 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-337">An example of the HTTP response:</span></span>  
  
```  
HTTP/1.1 202 Accepted  
Date: Fri, 15 Jul 2005 08:56:07 GMT  
Server: Microsoft-IIS/6.0  
MicrosoftOfficeWebServer: 5.0_Pub  
X-Powered-By: ASP.NET  
X-AspNet-Version: 2.0.50215  
Cache-Control: private  
Content-Length: 0  
```  
  
## <a name="soap-message-transmission-optimization-mechanism"></a><span data-ttu-id="ec1c7-338">SOAP MTOM(Message Transmission Optimization Mechanism)</span><span class="sxs-lookup"><span data-stu-id="ec1c7-338">SOAP Message Transmission Optimization Mechanism</span></span>  
 <span data-ttu-id="ec1c7-339">이 단원에서는 HTTP SOAP MTOM에 대한 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 구현 정보에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-339">This section describes the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementation details for the HTTP SOAP MTOM.</span></span> <span data-ttu-id="ec1c7-340">MTOM 기술은 기존 텍스트/XML 인코딩 또는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 이진 인코딩과 동일한 클래스의 SOAP 메시지 인코딩 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-340">MTOM technology is SOAP message encoding mechanism of the same class as traditional text/XML encoding or [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Binary encoding.</span></span> <span data-ttu-id="ec1c7-341">MTOM에는 다음과 같은 내용이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-341">MTOM includes the following:</span></span>  
  
-   <span data-ttu-id="ec1c7-342">base64 인코딩된 이진 데이터를 개별 이진 부분으로 포함하는 XML 정보 항목을 최적화하는 [XOP]에 설명된 XML 인코딩 및 패키징 메커니즘</span><span class="sxs-lookup"><span data-stu-id="ec1c7-342">An XML encoding and packaging mechanism described by [XOP] that optimizes XML information items containing base64-encoded binary data into separate binary parts.</span></span>  
  
-   <span data-ttu-id="ec1c7-343">XOP 패키지의 각 이진 부분 및 XML Infoset을 개별 MIME 부분으로 serialize하는 XOP 패키지의 MIME 캡슐화</span><span class="sxs-lookup"><span data-stu-id="ec1c7-343">A MIME encapsulation of the XOP package that serializes the XML Infoset and each binary part of the XOP package into a separate MIME part.</span></span>  
  
-   <span data-ttu-id="ec1c7-344">SOAP 1.x 봉투에 적용되는 MIME XOP 인코딩</span><span class="sxs-lookup"><span data-stu-id="ec1c7-344">A MIME XOP encoding applied to SOAP 1.x Envelope.</span></span>  
  
-   <span data-ttu-id="ec1c7-345">HTTP 전송 바인딩</span><span class="sxs-lookup"><span data-stu-id="ec1c7-345">An HTTP transport binding.</span></span>  
  
 <span data-ttu-id="ec1c7-346">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 HTTP를 사용하지 않는 전송에서 MTOM을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-346">It is possible to use MTOM with non-HTTP transports with [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="ec1c7-347">그러나 이 항목에서는 HTTP에 중점을 두어 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-347">However, in this topic we will focus on HTTP.</span></span>  
  
 <span data-ttu-id="ec1c7-348">MTOM 형식에서는 MTOM 자체와 XOP 및 MIME을 포함한 다양한 사양을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-348">The MTOM format leverages a large set of specifications covering MTOM itself, XOP, and MIME.</span></span> <span data-ttu-id="ec1c7-349">이 사양의 모듈성으로 인해 형식 및 처리 의미 체계에 대한 정확한 요구 사항을 재구성하기가 다소 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-349">Modularity of this specification set makes it somewhat difficult to reconstruct exact requirements on the format and processing semantics.</span></span> <span data-ttu-id="ec1c7-350">이 단원에서는 MTOM HTTP 바인딩의 형식 및 처리 요구 사항에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-350">This section describes the format and processing requirements for MTOM HTTP binding.</span></span>  
  
### <a name="mtom-message-encoding"></a><span data-ttu-id="ec1c7-351">MTOM 메시지 인코딩</span><span class="sxs-lookup"><span data-stu-id="ec1c7-351">MTOM Message Encoding</span></span>  
  
#### <a name="generating-mtom-messages"></a><span data-ttu-id="ec1c7-352">MTOM 메시지 생성</span><span class="sxs-lookup"><span data-stu-id="ec1c7-352">Generating MTOM messages</span></span>  
 <span data-ttu-id="ec1c7-353">[XOP] 단원 3.1에서는 base64 값을 추상적으로 정의된 XOP 패키지에 포함하는 요소 정보 항목을 사용하여 XML을 인코딩하는 프로세스를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-353">The [XOP] section 3.1 describes the process of encoding XML with element information items that contain base64 values into an abstractly defined XOP package.</span></span>  
  
 <span data-ttu-id="ec1c7-354">다음 단계에서는 MTOM 관련 인코딩 프로세스에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-354">The following sequence of steps describes the MTOM-specific encoding process:</span></span>  
  
1.  <span data-ttu-id="ec1c7-355">인코딩할 SOAP 봉투에 `[namespace name]`이 "http://www.w3.org/2004/08/xop/include"이고 `[local name]`이 `Include`인 요소 정보 항목이 포함되어 있지 않은지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-355">Ensure that the SOAP Envelope to be encoded contains no element information item with a `[namespace name]` of "http://www.w3.org/2004/08/xop/include" and a `[local name]` of `Include`.</span></span>  
  
2.  <span data-ttu-id="ec1c7-356">빈 MIME 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-356">Create an empty MIME package.</span></span>  
  
3.  <span data-ttu-id="ec1c7-357">원본 XML Infoset에서 최적화할 요소 정보 항목을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-357">Identify within the Original XML Infoset the element information items to be optimized.</span></span> <span data-ttu-id="ec1c7-358">항목을 최적화하려면 요소 정보 항목의 `[children]`을 구성하는 문자가 `xs:base64Binary`의 정규 형식(XSD-2, 3.2.16 base64Binary 참조)이고 공백 없는 콘텐츠 앞, 옆 또는 다음에 공백 문자를 포함하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-358">For the items to be optimized, the characters that make up the `[children]` of the element information item must be in the canonical form of `xs:base64Binary` (see XSD-2, 3.2.16 base64Binary) and must not contain any whitespace characters preceding, inline with, or following the non-whitespace content.</span></span>  
  
4.  <span data-ttu-id="ec1c7-359">원본 SOAP 봉투의 복사본인 XOP SOAP 봉투를 만듭니다. 단, 이전 단계에서 식별된 각 요소 정보 항목의 자식을 다음과 같이 구성된 `xop:Include` 요소 정보 항목으로 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-359">Create an XOP SOAP Envelope that is a copy of the Original SOAP Envelope, but with the children of each element information item identified in the previous step replaced by an `xop:Include` element information item constructed as follows:</span></span>  
  
    1.  <span data-ttu-id="ec1c7-360">대체된 문자를 base64 인코딩된 데이터로 처리하여 이진 데이터로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-360">Transform the replaced characters into binary data by processing them as base64-encoded data.</span></span>  
  
    2.  <span data-ttu-id="ec1c7-361">R3133 및 R3134 요구 사항을 충족하는 고유한 Content-ID 헤더 값을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-361">Generate a unique Content-ID header value that satisfies requirements R3133 and R3134.</span></span>  
  
    3.  <span data-ttu-id="ec1c7-362">이진 값을 사용하여 Content-Transfer-Encoding MIME 헤더를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-362">Generate a Content-Transfer-Encoding MIME header with the value binary.</span></span>  
  
    4.  <span data-ttu-id="ec1c7-363">최적화할 요소 정보 항목(새로 삽입된 `xop:Include` 요소 정보 항목의 [parent])에 `xmime:contentType` 특성 정보 항목이 있는 경우 `xmime:contentType` 특성 값을 사용하여 Content-Type MIME 헤더를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-363">If the element information item being optimized (the [parent] of the newly inserted `xop:Include` element information item) has an `xmime:contentType` attribute information item, generate a Content-Type MIME header with the value of the `xmime:contentType` attribute.</span></span>  
  
    5.  <span data-ttu-id="ec1c7-364">base64, 4b의 Content-ID 헤더, 4c의 Content- Transfer-Encoding 헤더, Content-Type 헤더(4d 단계에서 생성된 경우)로 처리된 대체 문자에서 디코딩된 이진 데이터로 형성된 콘텐츠를 사용하여 새 이진 MIME 부분을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-364">Generate a new binary MIME part with content formed by binary data decoded from the replaced characters processed as base64, Content-ID header from 4b, Content- Transfer-Encoding header from 4c, Content-Type header if generated in step 4d.</span></span>  
  
    6.  <span data-ttu-id="ec1c7-365">4b 단계에서 생성된 Content-ID 헤더 값에서 파생된 cid: uri 값을 사용하여 `href` 특성을 `xop:Include` 요소에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-365">Add an `href` attribute to the `xop:Include` element with the value cid: uri derived from Content-ID header value generated in step 4b.</span></span> <span data-ttu-id="ec1c7-366">묶는 제거 "\<" 및 ">" 문자를 이스케이프 URL 문자열 및 접두사를 추가 합니다. 나머지 `cid:`합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-366">Remove the enclosing "\<" and ">" characters, URL-escape the remaining string, and add the prefix `cid:`.</span></span> <span data-ttu-id="ec1c7-367">RFC1738 및 RFC2396으로 이스케이프하려면 다음과 같은 최소 문자 집합이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-367">The following minimum character set is required to be escaped by RFC1738 and RFC2396.</span></span> <span data-ttu-id="ec1c7-368">다른 문자를 이스케이프할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-368">Other characters can be escaped.</span></span>  
  
        ```  
        Hexadecimal 00-1F , 7F, 20, "<" | ">" | "#" | "%" | <">  
        "{" | "}" | "|" | "\" | "^" | "[" | "]" | "`" | "~" | "^"  
        ```  
  
5.  <span data-ttu-id="ec1c7-369">4단계의 XOP SOAP 봉투를 사용하여 루트 MIME 부분을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-369">Create a root MIME part with the XOP SOAP Envelope from step 4.</span></span>  
  
6.  <span data-ttu-id="ec1c7-370">HTTP Content-Type 헤더를 포함하여 HTTP 헤더를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-370">Write the HTTP headers, including the HTTP Content-Type header.</span></span>  
  
7.  <span data-ttu-id="ec1c7-371">MIME 패키지를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-371">Write the MIME package.</span></span>  
  
#### <a name="processing-mtom-messages"></a><span data-ttu-id="ec1c7-372">MTOM 메시지 처리</span><span class="sxs-lookup"><span data-stu-id="ec1c7-372">Processing MTOM messages</span></span>  
 <span data-ttu-id="ec1c7-373">MTOM 메시지 처리 과정은 이전 "MTOM 메시지 생성" 단원에서 설명한 프로세스와 정확히 반대입니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-373">Processing of an MTOM message is the exact reverse of the process described in the preceding "Generating MTOM messages" section:</span></span>  
  
1.  <span data-ttu-id="ec1c7-374">루트 MIME 부분에 Content-Type `application/xop+xml`이 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-374">Ensure the root MIME part has the Content-Type `application/xop+xml`.</span></span>  
  
2.  <span data-ttu-id="ec1c7-375">패키지의 루트 MIME 부분을 구문 분석하여 SOAP 봉투를 XML 문서로 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-375">Construct a SOAP Envelope by parsing the root MIME part of the package as an XML document.</span></span> <span data-ttu-id="ec1c7-376">문자 인코딩은 루트 MIME 부분 Content-Type의 `charset` 매개 변수에 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-376">Character encoding is determined by the `charset` parameter of the Content-Type of the root MIME part.</span></span>  
  
3.  <span data-ttu-id="ec1c7-377">`xop:Include` 요소 정보 항목을 [children] 속성의 단독 멤버로 가진 구성된 SOAP 봉투의 각 요소 정보 항목의 경우 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-377">For each element information item in the constructed SOAP Envelope, which has, as the sole member of its [children] property, an `xop:Include` element information item:</span></span>  
  
    1.  <span data-ttu-id="ec1c7-378">`cid:` 접두사를 제거하고 `@href` 요소의 `xop:Include` 특성 값에서 모든 URI 이스케이프 시퀀스(RFC 2396)를 이스케이프 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-378">Remove the `cid:` prefix and unescape all URI-escape sequences (RFC 2396) in the value of the `@href` attribute of the `xop:Include` element.</span></span> <span data-ttu-id="ec1c7-379">결과 문자열을 묶습니다 "\<", ">"입니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-379">Enclose the result string in "\<", ">".</span></span>  
  
    2.  <span data-ttu-id="ec1c7-380">3a 단계에서 파생된 문자열과 일치하는 Content-ID 헤더 값을 가진 MIME 부분을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-380">Locate the MIME part with the Content-ID header value that matches the string derived in step 3a.</span></span>  
  
    3.  <span data-ttu-id="ec1c7-381">각 항목의 `xop:Include` 속성에 나타나는 `children` 요소 정보 항목을 3b 단계에서 식별된 MIME 부분의 엔터티 본문의 정규 base64 인코딩(XSD-2, 3.2.16 base64Binary 참조)을 나타내는 문자 정보 항목으로 대체합니다. 즉, `xop:Include` 요소 정보 항목을 패키지 부분에서 재구성된 데이터로 효과적으로 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-381">Replace the `xop:Include` element information item that appears in the `children` property of each item with the character information items that represent the canonical base64 encoding (see XSD-2, 3.2.16 base64Binary) of the entity body of the MIME part identified in step 3b (effectively replace the `xop:Include` element information item with the data reconstructed from the package part).</span></span>  
  
#### <a name="http-content-type-header"></a><span data-ttu-id="ec1c7-382">HTTP Content-Type 헤더</span><span class="sxs-lookup"><span data-stu-id="ec1c7-382">HTTP Content-Type Header</span></span>  
 <span data-ttu-id="ec1c7-383">다음은 MTOM 및 RFC 2387에서 파생되고 MTOM 사양 자체에 명시된 요구 사항에서 파생된 SOAP 1.x MTOM 인코딩된 메시지의 HTTP Content-Type 헤더 형식에 대한 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]를 구현하는 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-383">The following is a list of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] clarifications for the format of the HTTP Content-Type header of a SOAP 1.x MTOM-encoded message derived from requirements stated in the MTOM specification itself and are derived from MTOM and RFC 2387.</span></span>  
  
-   <span data-ttu-id="ec1c7-384">R4131: HTTP Content-Type 헤더에는 multipart/related(대/소문자 구분 안 함) 값 및 해당 매개 변수가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-384">R4131: An HTTP Content-Type header must have the value of multipart/related (case-insensitive) and its parameters.</span></span> <span data-ttu-id="ec1c7-385">매개 변수 이름은 대/소문자를 구분하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-385">Parameter names are case-insensitive.</span></span> <span data-ttu-id="ec1c7-386">매개 변수의 순서는 중요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-386">Parameter order is not significant.</span></span>  
  
-   <span data-ttu-id="ec1c7-387">MIME 메시지에 대한 Content-Type 헤더의 전체 BNF(Backus-Naur Form)는 RFC 2045, 단원 5.1에 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-387">The full Backus-Naur Form (BNF) of the Content-Type header for MIME messages is listed in RFC 2045, section 5.1.</span></span>  
  
-   <span data-ttu-id="ec1c7-388">R4132: HTTP Content-Type 헤더에는 큰따옴표로 묶은 `application/xop+xml` 값을 가진 형식 매개 변수가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-388">R4132: An HTTP Content-Type header must have a type parameter with the value `application/xop+xml` enclosed in double quotation marks.</span></span>  
  
 <span data-ttu-id="ec1c7-389">큰따옴표 사용 요구 사항이 없으면 RFC 2387 텍스트에서 모든 multipart/related 미디어 형식 매개 변수에 가장 가능성이 높은 포함 되어 등의 문자는 예약 "@" or "/" 큰따옴표가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-389">While the requirement to use double quotation marks is not explicit in RFC 2387, the text observes that all of the multipart/related media type parameters most likely contain reserved characters like "@" or "/" and therefore need double quotation marks.</span></span>  
  
-   <span data-ttu-id="ec1c7-390">R4133: HTTP Content-Type 헤더에는 SOAP 1.x 봉투를 포함하는 MIMI 부분의 Content-ID 헤더 값이 큰따옴표로 묶인 시작 매개 변수가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-390">R4133: An HTTP Content-Type header should have a start parameter with the value of the Content-ID header of the MIME part that contains the SOAP 1.x Envelope, enclosed in double quotation marks.</span></span> <span data-ttu-id="ec1c7-391">시작 매개 변수가 생략된 경우 첫 번째 MIME 부분에 SOAP 1.x 봉투가 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-391">If the start parameter is omitted, the first MIME part must contain the SOAP 1.x Envelope.</span></span>  
  
-   <span data-ttu-id="ec1c7-392">R4134: SOAP 1.1 MTOM 인코딩된 메시지의 HTTP Content-Type 헤더는 큰따옴표로 묶인 text/xml 값을 가진 start-info 매개 변수를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-392">R4134: An HTTP Content-Type header for a SOAP 1.1 MTOM encoded message must include the start-info parameter with the value of text/xml, enclosed in double quotation marks.</span></span>  
  
-   <span data-ttu-id="ec1c7-393">R4135: SOAP 1.2 MTOM 인코딩된 메시지의 HTTP Content-Type 헤더는 큰따옴표로 묶인 `application/soap+xml` 값을 가진 start-info 매개 변수를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-393">R4135: An HTTP Content-Type header for a SOAP 1.2 MTOM-encoded message must include the start-info parameter with the value of `application/soap+xml`, enclosed in double quotation marks.</span></span>  
  
-   <span data-ttu-id="ec1c7-394">R4136: SOAP 1.x MTOM 인코딩된 메시지의 HTTP Content-Type 헤더에는 RFC 2046, 단원 5.1.1에 정의된 MIME 경계 BNF와 일치하는 큰따옴표로 묶인 값을 가진 boundary 매개 변수가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-394">R4136: HTTP Content-Type header for a SOAP 1.x MTOM-encoded message must have the boundary parameter with the value (enclosed in double quotation marks) that matches the MIME boundary BNF defined in RFC 2046, section 5.1.1</span></span>  
  
    ```  
    boundary := 0*69<bchars> bcharsnospace   
    bchars := bcharsnospace / " "   
    bcharsnospace :=    DIGIT / ALPHA / "'" / "(" / ")" / "+"   
                        / "_" / "," / "-" / "." / "/" / ":" / "=" / "?"  
    ```  
  
     <span data-ttu-id="ec1c7-395">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-395">Examples:</span></span>  
  
     <span data-ttu-id="ec1c7-396">올바른 예</span><span class="sxs-lookup"><span data-stu-id="ec1c7-396">CORRECT</span></span>  
  
    ```  
    Content-Type: multipart/related; type="application/xop+xml";start=" <part0@tempuri.org>";boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1";start-info="text/xml"  
    ```  
  
     <span data-ttu-id="ec1c7-397">올바른 예</span><span class="sxs-lookup"><span data-stu-id="ec1c7-397">CORRECT</span></span>  
  
    ```  
    Content-Type: Multipart/Related; type="application/xop+xml";start-info="text/xml";boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1"  
    ```  
  
     <span data-ttu-id="ec1c7-398">잘못된 예</span><span class="sxs-lookup"><span data-stu-id="ec1c7-398">INCORRECT</span></span>  
  
    ```  
    Content-Type: Multipart/Related; type=application/xop+xml;start=" <part0@tempuri.org>";start-info="text/xml";boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1"   
    ```  
  
#### <a name="infoset-mime-part"></a><span data-ttu-id="ec1c7-399">Infoset MIME 부분</span><span class="sxs-lookup"><span data-stu-id="ec1c7-399">Infoset MIME Part</span></span>  
 <span data-ttu-id="ec1c7-400">SOAP 1.x 봉투는 XOP MIME 패키지의 루트 부분으로 캡슐화되며 `infoset` 부분이라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-400">The SOAP 1.x Envelope is encapsulated as a root part of the XOP MIME package and is often called the `infoset` part.</span></span>  
  
-   <span data-ttu-id="ec1c7-401">R4141: SOAP 1.x 봉투는 XOP MIME 패키지의 루트 부분으로 캡슐화되어야 하고, `infoset` 부분이라고도 하며, HTTP Content-Type에서 참조되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-401">R4141: The SOAP 1.x Envelope must be encapsulated as a root part of the XOP MIME package, called the `infoset` part and referenced from the HTTP Content-Type.</span></span>  
  
-   <span data-ttu-id="ec1c7-402">R4142: SOAP `Infoset` 부분은 `Content-ID`, `Content-Transfer-Encoding` 및 `Content-Type` MIME 헤더를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-402">R4142: The SOAP `Infoset` part must include the following MIME headers: `Content-ID`, `Content-Transfer-Encoding`, and `Content-Type`.</span></span>  
  
 <span data-ttu-id="ec1c7-403">Content-ID 헤더의 형식은 RFC 2045에 다음과 같이 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-403">The format of the Content-ID header is defined by RFC 2045 as</span></span>  
  
```  
"Content-ID" ":" msg-id  
```  
  
 <span data-ttu-id="ec1c7-404">`msg-id`는 RFC 2822(RFC 822보다 우선하며, RFC 2045에서 참조됨)에 다음과 같이 정의되어 있으며</span><span class="sxs-lookup"><span data-stu-id="ec1c7-404">where `msg-id` is defined in RFC 2822 (that supersedes RFC 822, referenced in RFC 2045) as:</span></span>  
  
```  
msg-id    =       [CFWS] "<" id-left "@" id-right ">" [CFWS]  
```  
  
 <span data-ttu-id="ec1c7-405">효과적으로 전자 메일 주소 내에 포함 되어 및 "\<" 및 ">"입니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-405">and is effectively an e-mail address enclosed within "\<" and  ">".</span></span> <span data-ttu-id="ec1c7-406">`[CFWS]` 접두사와 접미사는 설명을 전달하기 위해 RFC 2822에 추가되었지만 상호 운용성을 유지하려면 사용하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-406">The `[CFWS]` prefix and suffix were added in RFC 2822 to carry comments and should not be used to preserve interoperability.</span></span>  
  
 <span data-ttu-id="ec1c7-407">R4143: Infoset MIME 부분의 Content-ID 헤더 값은 `msg-id` 접두사 및 접미사 부분을 생략한 상태의 RFC 2822의 `[CFWS]` 생성을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-407">R4143: The value of the Content-ID header for the Infoset MIME part must follow `msg-id` production from RFC 2822 with the `[CFWS]` prefix and suffix parts omitted.</span></span>  
  
 <span data-ttu-id="ec1c7-408">많은 MIME 구현 내에 포함 된 값에 대 한 요구 사항 완화 "\<" 및 ">" 전자 메일 주소를 사용 및 `absoluteURI` 로 묶인 "\<", ">" 전자 메일 주소와 함께 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-408">A number of MIME implementations relaxed requirements for the value enclosed within "\<" and ">" to be an e-mail address and used `absoluteURI` enclosed in "\<" , ">" in addition to the e-mail address.</span></span> <span data-ttu-id="ec1c7-409">이 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 버전에서는 다음과 같은 형식의 Content-ID MIME 헤더 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-409">This version of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses values of the Content-ID MIME header of the form:</span></span>  
  
```  
Content-ID: <http://tempuri.org/0>   
```  
  
 <span data-ttu-id="ec1c7-410">R4144: MTOM 프로세서는 다음과 같은 완화된 `msg-id`와 일치하는 Content-ID 헤더 값을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-410">R4144: MTOM processors should accept Content-ID header values that match the following relaxed `msg-id`.</span></span>  
  
```  
msg-id-relaxed =     [CFWS] "<" (absoluteURI | mail-address) ">" [CFWS]  
mail-address   =     id-left "@" id-right  
```  
  
 <span data-ttu-id="ec1c7-411">MIME(RFC 2045)은 MIME 부분의 콘텐츠 인코딩을 전달하기 위해 Content-Transfer-Encoding 헤더를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-411">MIME (RFC 2045) provides the Content-Transfer-Encoding header to communicate encoding of the content of the MIME part.</span></span> <span data-ttu-id="ec1c7-412">Content-Transfer-Encoding에 대해 정의된 기본값은 7비트로 대부분의 SOAP 메시지에 적합하지 않으므로 상호 운용성 향상을 위해 Content-Transfer-Encoding 헤더가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-412">The default defined for Content-Transfer-Encoding is 7-bit, which is not suitable for most SOAP messages, so the Content-Transfer-Encoding header is needed for greater interoperability:</span></span>  
  
-   <span data-ttu-id="ec1c7-413">R4145: SOAP Infoset 부분은 Content-Transfer-Encoding 헤더를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-413">R4145: The SOAP Infoset part must contain the Content-Transfer-Encoding header.</span></span>  
  
-   <span data-ttu-id="ec1c7-414">R4146: SOAP 봉투 문자 인코딩이 UTF-8이면 Content-Transfer-Encoding 헤더 값이 8비트여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-414">R4146: If the SOAP Envelope character encoding is UTF-8, the value of the Content-Transfer-Encoding header must be 8-bit.</span></span>  
  
-   <span data-ttu-id="ec1c7-415">R4147: SOAP 봉투 문자 인코딩이 UTF-16이면 Content-Transfer-Encoding 헤더 값이 이진이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-415">R4147: If the SOAP Envelope character encoding is UTF-16, the value of the Content-Transfer-Encoding header must be binary.</span></span>  
  
-   <span data-ttu-id="ec1c7-416">[XOP] 단원 5에 따르면</span><span class="sxs-lookup"><span data-stu-id="ec1c7-416">According to [XOP] section 5,</span></span>  
  
-   <span data-ttu-id="ec1c7-417">R4148: SOAP1.1 Infoset 부분은 미디어 형식이 application/xop + xml 콘텐츠 형식 헤더를 포함 해야 하 고 매개 변수가 type = "text/xml" 및 charset</span><span class="sxs-lookup"><span data-stu-id="ec1c7-417">R4148: SOAP1.1 Infoset part must contain Content-Type header with media type application/xop+xml and parameters type="text/xml" and charset</span></span>  
  
    ```  
    Content-Type: application/xop+xml;  
                  charset=utf-8;type="text/xml"  
    ```  
  
-   <span data-ttu-id="ec1c7-418">R4149: SOAP 1.2 Infoset 부분은 미디어 유형으로 Content-type 헤더를 포함 해야 `application/xop+xml` 고 매개 변수가 type = "`application/soap+xml`" 및 `charset`합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-418">R4149: The SOAP 1.2 Infoset part must contain the Content-Type header with media type `application/xop+xml` and parameters type="`application/soap+xml`" and `charset`.</span></span>  
  
    ```  
    Content-Type: application/xop+xml;  
                  charset=utf-8;type="application/soap+xml"  
    ```  
  
     <span data-ttu-id="ec1c7-419">XOP에서는 `charset`의 `application/xop+xml` 매개 변수를 선택적 요소로 정의하고 있지만, `charset` 미디어 형식의 `text/xml` 매개 변수에 대한 BP 1.1 요구 사항과 마찬가지로 상호 운용성을 위해 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-419">While XOP defines the `charset` parameter for `application/xop+xml` to be optional, it is needed for interoperability similar to the BP 1.1 requirement on the `charset` parameter for the `text/xml` media type.</span></span>  
  
-   <span data-ttu-id="ec1c7-420">R41410: `type` 및 `charset` 매개 변수가 SOAP 1.x Infoset 부분의 Content-Type 헤더에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-420">R41410: The `type` and `charset` parameters must be present on the Content-Type header of the SOAP 1.x Infoset part.</span></span>  
  
#### <a name="wcf-endpoint-support-for-mtom"></a><span data-ttu-id="ec1c7-421">MTOM에 대한 WCF 끝점 지원</span><span class="sxs-lookup"><span data-stu-id="ec1c7-421">WCF Endpoint Support for MTOM</span></span>  
 <span data-ttu-id="ec1c7-422">MTOM의 목적은 SOAP 메시지를 인코딩하여 base64 인코딩된 데이터를 최적화하는 데 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-422">The purpose of MTOM is to encode a SOAP message to optimize base64-encoded data.</span></span> <span data-ttu-id="ec1c7-423">다음은 제약 조건 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-423">The following is a list of constraints:</span></span>  
  
-   <span data-ttu-id="ec1c7-424">R4151: base64 인코딩된 데이터를 포함하는 모든 요소 정보 항목이 최적화될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-424">R4151: Any element information item that contains base64-encoded data may be optimized.</span></span>  
  
-   <span data-ttu-id="ec1c7-425">B4152: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 base64 인코딩된 데이터를 포함하고 길이가 1024바이트를 초과하는 요소 정보 항목을 최적화합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-425">B4152: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] optimizes element information items that contain base64-encoded data and exceed 1024 bytes in length.</span></span>  
  
 <span data-ttu-id="ec1c7-426">MTOM을 사용하도록 구성된 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 끝점은 항상 MTOM 인코딩된 메시지를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-426">A [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] endpoint configured to use MTOM will always send MTOM-encoded messages.</span></span> <span data-ttu-id="ec1c7-427">필수 조건을 충족하는 부분이 없더라도 MTOM 인코딩된 메시지를 보냅니다. 이 메시지는 단일 MIME 부분에서 SOAP 봉투를 포함하는 MIME 패키지로 serialize됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-427">Even if no parts meet the required criteria, the message is still MTOM-encoded (serialized as a MIME package with a single MIME part containing the SOAP envelope).</span></span>  
  
### <a name="ws-policy-assertion-for-mtom"></a><span data-ttu-id="ec1c7-428">MTOM WS-Policy Assertion</span><span class="sxs-lookup"><span data-stu-id="ec1c7-428">WS-Policy Assertion for MTOM</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="ec1c7-429">에서는 다음과 같은 정책 어설션을 사용하여 끝점의 MTOM 사용을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-429"> uses the following policy assertion to indicate MTOM usage by endpoint:</span></span>  
  
```xml  
<wsoma:OptimizedMimeSerialization ... />  
```  
  
-   <span data-ttu-id="ec1c7-430">R4211: 이전 정책 어설션은 끝점 정책 주체를 포함하고 MTOM을 사용하여 끝점에서 보내거나 받은 모든 메시지를 최적화하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-430">R4211: The preceding policy assertion has an Endpoint Policy Subject and specifies that all messages sent to and received from the endpoint must be optimized using MTOM.</span></span>  
  
-   <span data-ttu-id="ec1c7-431">B4212: MTOM 최적화를 사용하도록 구성된 경우 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 끝점은 해당 `wsdl:binding`에 연결된 정책에 MTOM 정책 어설션을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-431">B4212: When configured to use MTOM optimization, an [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] endpoint adds an MTOM Policy assertion to the policy attached to the corresponding `wsdl:binding`.</span></span>  
  
### <a name="composition-with-ws-security"></a><span data-ttu-id="ec1c7-432">WS-Security를 사용하여 구성</span><span class="sxs-lookup"><span data-stu-id="ec1c7-432">Composition with WS-Security</span></span>  
 <span data-ttu-id="ec1c7-433">MTOM은 `text/xml` 및 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 이진 XML과 비슷한 인코딩 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-433">MTOM is an encoding mechanism that is similar to `text/xml` and [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Binary XML.</span></span> <span data-ttu-id="ec1c7-434">MTOM은 WS-Security 및 기타 WS-* 프로토콜을 사용하여 자연스러운 구성을 제공합니다. WS-Security를 사용하여 보안된 메시지는 MTOM을 사용하여 최적화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-434">MTOM offers natural composition with WS-Security and other WS-* protocols: a message secured using WS-Security can be optimized using MTOM.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="ec1c7-435">예제</span><span class="sxs-lookup"><span data-stu-id="ec1c7-435">Examples</span></span>  
  
#### <a name="wcf-soap-11-message-encoded-using-mtom"></a><span data-ttu-id="ec1c7-436">MTOM을 사용하여 인코딩한 WCF SOAP 1.1 메시지</span><span class="sxs-lookup"><span data-stu-id="ec1c7-436">WCF SOAP 1.1 Message Encoded Using MTOM</span></span>  
  
```  
POST http://131.107.72.15/Mtom/svc/service.svc/Soap11MtomUTF8 HTTP/1.1  
SOAPAction: "http://xmlsoap.org/echoBinaryAsString"  
Content-Type: multipart/related;type="application/xop+xml";  
              start="<http://tempuri.org/0>";start-info="text/xml";  
       boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1"  
Host: 131.107.72.15  
Content-Length: 1501  
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1  
Content-ID: <http://tempuri.org/0>  
Content-Transfer-Encoding: 8bit  
Content-Type: application/xop+xml;charset=utf-8;type="text/xml"  
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
  <s:Body>  
    <EchoBinaryAsString xmlns="http://xmlsoap.org/Ping">  
      <array>  
        <xop:Include   
         href="cid:http%3A%2F%2Ftempuri.org%2F1%2F632618206521093670"   
         xmlns:xop="http://www.w3.org/2004/08/xop/include"/>  
      </array>  
    </EchoBinaryAsString>  
  </s:Body>  
</s:Envelope>  
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1  
Content-ID: <http://tempuri.org/1/632618206521093670>  
Content-Transfer-Encoding: binary  
Content-Type: application/octet-stream  
…Binary Content..  
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1  
```  
  
#### <a name="wcf-secure-soap-12-message-encoded-using-mtom"></a><span data-ttu-id="ec1c7-437">MTOM을 사용하여 인코딩한 WCF Secure SOAP 1.2 메시지</span><span class="sxs-lookup"><span data-stu-id="ec1c7-437">WCF Secure SOAP 1.2 Message Encoded Using MTOM</span></span>  
 <span data-ttu-id="ec1c7-438">이 예제에서 메시지는 WS-Security를 사용하여 보호된 SOAP 1.2 및 MTOM을 사용하여 인코딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-438">In this example, a message is encoded using MTOM and SOAP 1.2 that is protected using WS-Security.</span></span> <span data-ttu-id="ec1c7-439">인코딩을 위해 식별되는 이진 부분은 `BinarySecurityToken`의 콘텐츠로서, 암호화된 서명 및 암호화된 본문에 해당하는 `CipherValue`의 `EncryptedData`입니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-439">The binary parts identified for encoding are the contents of the `BinarySecurityToken`, `CipherValue` of the `EncryptedData` corresponding to the encrypted signature and encrypted body.</span></span> <span data-ttu-id="ec1c7-440">`CipherValue`의 `EncryptedKey`는 길이가 1024바이트 미만이므로 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 최적화하도록 식별되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ec1c7-440">Note that the `CipherValue` of the `EncryptedKey` was not identified for optimization by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], because its length is less then 1024 bytes.</span></span>  
  
```  
POST http://131.107.72.15/Mtom/service.svc/Soap12MtomSecureSignEncrypt HTTP/1.1  
Content-Type: multipart/related; type="application/xop+xml";  
              start="<http://tempuri.org/0>";  
            boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3";  
              start-info="application/soap+xml";   
              action="http://xmlsoap.org/echoBinaryAsString"  
Host: 131.107.72.15  
Content-Length: 1941  
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3  
Content-ID: <http://tempuri.org/0>  
Content-Transfer-Encoding: 8bit  
Content-Type: application/xop+xml;charset=utf-8;type="application/soap+xml"  
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/" xmlns:u="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">  
  <s:Header>  
    <o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">  
      <u:Timestamp u:Id="uuid-4d4ee765-5717-4d53-9ac9-99bddc07df6c-5">  
        <u:Created>2005-09-09T06:57:32.488Z</u:Created>  
        <u:Expires>2005-09-09T07:02:32.488Z</u:Expires>  
      </u:Timestamp>  
      <o:BinarySecurityToken u:Id="uuid-4d4ee765-5717-4d53-9ac9-99bddc07df6c-2" ValueType="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0#X509v3" EncodingType="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-soap-message-security-1.0#Base64Binary">  
        <xop:Include href="cid:http%3A%2F%2Ftempuri.org%2F1%2F632618206525089430" xmlns:xop="http://www.w3.org/2004/08/xop/include"/>  
      </o:BinarySecurityToken>  
      <e:EncryptedKey Id="_1" xmlns:e="http://www.w3.org/2001/04/xmlenc#">  
        <e:EncryptionMethod Algorithm="http://www.w3.org/2001/04/xmlenc#rsa-oaep-mgf1p"/>  
        <KeyInfo xmlns="http://www.w3.org/2000/09/xmldsig#">  
          <o:SecurityTokenReference>  
            <o:KeyIdentifier ValueType="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0#X509SubjectKeyIdentifier">Xeg55vRyK3ZhAEhEf+YT0z986L0=</o:KeyIdentifier>  
          </o:SecurityTokenReference>  
        </KeyInfo>  
        <e:CipherData>          <e:CipherValue>oQfpxwT8/SAGyZQzKE2b4yO6dXuQj7pwJ+5CGL3Rf7C06bQ5ttMoQ9GLJcQYkXTzin+WwHEgs5bj5ml9HKTW9QAU5JJ6lksdymmQvWP5ZtGPBVchO4sofEGoCKmBiZL/DYS/cnbzgnc/3a6NYnc10y2fWGaGLiqa00zijAw7o0Y=</e:CipherValue>  
        </e:CipherData>  
      </e:EncryptedKey>  
      <c:DerivedKeyToken u:Id="_2" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc">  
        <o:SecurityTokenReference>  
          <o:Reference URI="#_1"/>  
        </o:SecurityTokenReference>  
        <c:Nonce>OrEPRX7fISIS4sXYWPMv3g==</c:Nonce>  
      </c:DerivedKeyToken>  
      <e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#">  
        <e:DataReference URI="#_3"/>  
        <e:DataReference URI="#_4"/>  
      </e:ReferenceList>  
      <e:EncryptedData Id="_4" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#">  
        <e:EncryptionMethod Algorithm="http://www.w3.org/2001/04/xmlenc#aes256-cbc"/>  
        <KeyInfo xmlns="http://www.w3.org/2000/09/xmldsig#">  
          <o:SecurityTokenReference>  
            <o:Reference URI="#_2"/>  
          </o:SecurityTokenReference>  
        </KeyInfo>  
        <e:CipherData>  
          <e:CipherValue>  
            <xop:Include href="cid:http%3A%2F%2Ftempuri.org%2F2%2F632618206525089430" xmlns:xop="http://www.w3.org/2004/08/xop/include"/>  
          </e:CipherValue>  
        </e:CipherData>  
      </e:EncryptedData>  
    </o:Security>  
  </s:Header>  
  <s:Body u:Id="_0">  
    <e:EncryptedData Id="_3" Type="http://www.w3.org/2001/04/xmlenc#Content" xmlns:e="http://www.w3.org/2001/04/xmlenc#">  
      <e:EncryptionMethod Algorithm="http://www.w3.org/2001/04/xmlenc#aes256-cbc"/>  
      <KeyInfo xmlns="http://www.w3.org/2000/09/xmldsig#">  
        <o:SecurityTokenReference xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">  
          <o:Reference URI="#_2"/>  
        </o:SecurityTokenReference>  
      </KeyInfo>  
      <e:CipherData>  
        <e:CipherValue>  
          <xop:Include href="cid:http%3A%2F%2Ftempuri.org%2F3%2F632618206525089430" xmlns:xop="http://www.w3.org/2004/08/xop/include"/>  
        </e:CipherValue>  
      </e:CipherData>  
    </e:EncryptedData>  
  </s:Body>  
</s:Envelope>  
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3  
Content-ID: <http://tempuri.org/1/632618206525089430>  
Content-Transfer-Encoding: binary  
Content-Type: application/octet-stream  
...Binary content of BinarySecurityToken - X509 Certificate...  
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3  
Content-ID: <http://tempuri.org/2/632618206525089430>  
Content-Transfer-Encoding: binary  
Content-Type: application/octet-stream  
...Binary serialization of the encrypted primary signature...  
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3  
Content-ID: <http://tempuri.org/3/632618206525089430>  
Content-Transfer-Encoding: binary  
Content-Type: application/octet-stream  
...Binary serialization of the encrypted Body...  
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3--  
```
