---
title: '&lt;ws2007FederationHttpBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9af4ec79-cdef-457e-9dca-09d5eb821594
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b1f85d4cc45075f82035fa5b8c0c95341ba142d6
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="ltws2007federationhttpbindinggt"></a><span data-ttu-id="5bfc0-102">&lt;ws2007FederationHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="5bfc0-102">&lt;ws2007FederationHttpBinding&gt;</span></span>
<span data-ttu-id="5bfc0-103">파생 되는 안전 하 고 상호 운용 가능한 바인딩을 [ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) 페더레이션된 보안을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-103">A secure and interoperable binding that derives from [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) and supports federated security.</span></span>  
  
 <span data-ttu-id="5bfc0-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="5bfc0-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="5bfc0-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="5bfc0-105">\<bindings></span></span>  
<span data-ttu-id="5bfc0-106">\<ws2007FederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="5bfc0-106">\<ws2007FederationHttpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bfc0-107">구문</span><span class="sxs-lookup"><span data-stu-id="5bfc0-107">Syntax</span></span>  
  
```xml  
<ws2007FederationHttpBinding>  
    <binding   
        bypassProxyOnLocal="Boolean"  
        closeTimeout="TimeSpan"   
        hostNameComparisonMode="StrongWildcard/Exact/WeakWildcard"  
        maxBufferPoolSize="integer"  
        maxReceivedMessageSize="integer"  
        messageEncoding="Text/Mtom"   
                name="string"  
        openTimeout="TimeSpan"   
        privacyNoticeAt="Uri"  
        privacyNoticeVersion="Integer"  
        proxyAddress="Uri"   
        receiveTimeout="TimeSpan"  
        sendTimeout="TimeSpan"  
        textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding"  
        transactionFlow="Boolean"  
        useDefaultWebProxy="Boolean">  
        <security mode="None/Message/TransportWithMessageCredential">  
           <message negotiateServiceCredential="Boolean"  
                algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
                issuedTokenType="string"  
                issuedKeyType="SymmetricKey/PublicKey"  
           </message>  
        </security>  
        <reliableSession ordered="Boolean"  
           inactivityTimeout="TimeSpan"  
           enabled="Boolean" />  
       <readerQuotas             maxArrayLength="Integer"            maxBytesPerRead="Integer"            maxDepth="Integer"             maxNameTableCharCount="Integer"                     maxStringContentLength="Integer" />    </binding>  
</ws2007FederationHttpBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5bfc0-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="5bfc0-108">Attributes and Elements</span></span>  
 <span data-ttu-id="5bfc0-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5bfc0-110">특성</span><span class="sxs-lookup"><span data-stu-id="5bfc0-110">Attributes</span></span>  
  
|<span data-ttu-id="5bfc0-111">특성</span><span class="sxs-lookup"><span data-stu-id="5bfc0-111">Attribute</span></span>|<span data-ttu-id="5bfc0-112">설명</span><span class="sxs-lookup"><span data-stu-id="5bfc0-112">Description</span></span>|  
|---------------|-----------------|  
|`bypassProxyOnLocal`|<span data-ttu-id="5bfc0-113">로컬 주소에 대해 프록시 서버를 우회할지 여부를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-113">A value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="5bfc0-114">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-114">The default is `false`.</span></span>|  
|`closeTimeout`|<span data-ttu-id="5bfc0-115">닫기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-115">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="5bfc0-116">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-116">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="5bfc0-117">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-117">The default is 00:01:00.</span></span>|  
|`hostnameComparisonMode`|<span data-ttu-id="5bfc0-118">URI 구문 분석에 사용되는 HTTP 호스트 이름 비교 모드를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-118">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="5bfc0-119">이 특성은 <xref:System.ServiceModel.HostNameComparisonMode> 형식이며 URI에 대해 비교할 때 호스트 이름이 서비스에 연결하는 데 사용되는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-119">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="5bfc0-120">기본값은 <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>이며 이 값은 비교 시 호스트 이름을 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-120">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="5bfc0-121">이 바인딩에 대한 최대 버퍼 풀 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-121">The maximum buffer pool size for this binding.</span></span> <span data-ttu-id="5bfc0-122">기본값은 524,288바이트(512 \* 1024)입니다.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-122">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="5bfc0-123">[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]의 많은 부분에서 버퍼를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-123">Many parts of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] use buffers.</span></span> <span data-ttu-id="5bfc0-124">버퍼를 사용할 때마다 만들고 삭제하면 비용이 많이 들며, 버퍼에 대한 가비지 수집 역시 비용이 많이 듭니다.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-124">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="5bfc0-125">버퍼 풀이 있으면 이 풀로부터 버퍼를 가져와 사용한 다음 다시 풀로 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-125">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="5bfc0-126">따라서 버퍼를 만들고 삭제하는 데 오버헤드를 피할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-126">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="5bfc0-127">이 바인딩으로 구성된 채널에서 받을 수 있는 헤더를 비롯한 최대 메시지 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-127">The maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="5bfc0-128">이 한도를 초과하는 메시지를 보낸 사람은 SOAP 오류를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-128">The sender of a message that exceeds this limit receives a SOAP fault.</span></span> <span data-ttu-id="5bfc0-129">수신자는 메시지를 삭제하고 추적 로그에 이벤트 항목을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-129">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="5bfc0-130">기본값은 65536입니다.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-130">The default is 65536.</span></span>|  
|`messageEncoding`|<span data-ttu-id="5bfc0-131">메시지를 인코딩하는 데 사용되는 인코더를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-131">Defines the encoder used to encode the message.</span></span> <span data-ttu-id="5bfc0-132">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-132">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="5bfc0-133">-Text: 텍스트 메시지 인코더를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-133">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="5bfc0-134">Mtom: 조직 메커니즘 1.0 MTOM (Message Transmission) 인코더를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-134">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><br /> <span data-ttu-id="5bfc0-135">기본값은 Text입니다.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-135">The default is Text.</span></span><br /><br /> <span data-ttu-id="5bfc0-136">이 특성은 <xref:System.ServiceModel.WSMessageEncoding> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-136">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|  
|`name`|<span data-ttu-id="5bfc0-137">바인딩의 구성 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-137">The configuration name of the binding.</span></span> <span data-ttu-id="5bfc0-138">이 값은 바인딩의 ID로 사용되므로 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-138">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="5bfc0-139">[!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)]부터는 바인딩 및 동작에 이름이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-139">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="5bfc0-140">기본 구성 및 이름이 없는 바인딩 및 동작에 대 한 자세한 내용은 참조 [단순화 된 구성](../../../../../docs/framework/wcf/simplified-configuration.md) 및 [WCF 서비스에 대 한 구성을 단순화](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-140">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="5bfc0-141">열기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-141">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="5bfc0-142">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-142">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="5bfc0-143">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-143">The default is 00:01:00.</span></span>|  
|`privactyNoticeAt`|<span data-ttu-id="5bfc0-144">개인 정보 알림이 있는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-144">A URI at which the privacy notice is located.</span></span>|  
|`privactyNoticeVersion`|<span data-ttu-id="5bfc0-145">현재 개인 정보 알림의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-145">The version of the current privacy notice.</span></span>|  
|`proxyAddress`|<span data-ttu-id="5bfc0-146">HTTP 프록시의 주소를 지정하는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-146">A URI that specifies the address of the HTTP proxy.</span></span> <span data-ttu-id="5bfc0-147">`useDefaultWebProxy`가 `true`일 경우 이 설정은 `null`이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-147">If `useDefaultWebProxy` is `true`, this setting must be `null`.</span></span> <span data-ttu-id="5bfc0-148">기본값은 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-148">The default is `null`.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="5bfc0-149">받기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-149">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="5bfc0-150">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-150">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="5bfc0-151">기본값은 00:10:00입니다.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-151">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="5bfc0-152">보내기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-152">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="5bfc0-153">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-153">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="5bfc0-154">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-154">The default is 00:01:00.</span></span>|  
|`textEncoding`|<span data-ttu-id="5bfc0-155">바인딩에서 메시지를 내보내는 데 사용되는 문자 집합 인코딩을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-155">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="5bfc0-156">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-156">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="5bfc0-157">-BigEndianUnicode: 유니코드 Big Endian 인코딩</span><span class="sxs-lookup"><span data-stu-id="5bfc0-157">-   BigEndianUnicode: Unicode Big Endian encoding.</span></span><br /><span data-ttu-id="5bfc0-158">-Unicode: 16 비트 인코딩입니다.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-158">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="5bfc0-159">UTF8: 8 비트 인코딩입니다.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-159">-   UTF8: 8-bit encoding.</span></span><br /><br /> <span data-ttu-id="5bfc0-160">기본값은 UTF8입니다.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-160">The default is UTF8.</span></span> <span data-ttu-id="5bfc0-161">이 특성은 <xref:System.Text.Encoding> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-161">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|`transactionFlow`|<span data-ttu-id="5bfc0-162">바인딩에서 WS-트랜잭션 이동을 지원할지 여부를 지정하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-162">A value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="5bfc0-163">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-163">The default is `false`.</span></span>|  
|`useDefaultWebProxy`|<span data-ttu-id="5bfc0-164">시스템의 자동 구성된 HTTP 프록시 사용 여부를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-164">A value that indicates whether the system’s auto-configured HTTP proxy is used.</span></span> <span data-ttu-id="5bfc0-165">이 특성이 `null`이면 프록시 주소는 `true`이어야 합니다(설정되지 않음).</span><span class="sxs-lookup"><span data-stu-id="5bfc0-165">The proxy address must be `null` (that is, not set) if this attribute is `true`.</span></span> <span data-ttu-id="5bfc0-166">기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-166">The default is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5bfc0-167">자식 요소</span><span class="sxs-lookup"><span data-stu-id="5bfc0-167">Child Elements</span></span>  
  
|<span data-ttu-id="5bfc0-168">요소</span><span class="sxs-lookup"><span data-stu-id="5bfc0-168">Element</span></span>|<span data-ttu-id="5bfc0-169">설명</span><span class="sxs-lookup"><span data-stu-id="5bfc0-169">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5bfc0-170">\<security></span><span class="sxs-lookup"><span data-stu-id="5bfc0-170">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md)|<span data-ttu-id="5bfc0-171">메시지에 대한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-171">Defines the security settings for the message.</span></span> <span data-ttu-id="5bfc0-172">이 요소는 <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-172">This element is of type <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>.</span></span>|  
|[<span data-ttu-id="5bfc0-173">\<readerQuotas></span><span class="sxs-lookup"><span data-stu-id="5bfc0-173">\<readerQuotas></span></span>](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="5bfc0-174">이 바인딩으로 구성된 끝점에서 처리할 수 있는 SOAP 메시지의 복잡성에 대한 제약 조건을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-174">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="5bfc0-175">이 요소는 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-175">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|[<span data-ttu-id="5bfc0-176">reliableSession</span><span class="sxs-lookup"><span data-stu-id="5bfc0-176">reliableSession</span></span>](http://msdn.microsoft.com/library/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b)|<span data-ttu-id="5bfc0-177">채널 끝점 간에 신뢰할 수 있는 세션이 설정되는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-177">Specifies whether reliable sessions are established between channel endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5bfc0-178">부모 요소</span><span class="sxs-lookup"><span data-stu-id="5bfc0-178">Parent Elements</span></span>  
  
|<span data-ttu-id="5bfc0-179">요소</span><span class="sxs-lookup"><span data-stu-id="5bfc0-179">Element</span></span>|<span data-ttu-id="5bfc0-180">설명</span><span class="sxs-lookup"><span data-stu-id="5bfc0-180">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5bfc0-181">\<bindings></span><span class="sxs-lookup"><span data-stu-id="5bfc0-181">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="5bfc0-182">이 요소는 표준 및 사용자 지정 바인딩의 컬렉션을 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-182">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5bfc0-183">설명</span><span class="sxs-lookup"><span data-stu-id="5bfc0-183">Remarks</span></span>  
 <span data-ttu-id="5bfc0-184">페더레이션은 인증 및 권한 부여를 위해 여러 회사나 트러스트 도메인 간에 ID를 공유하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-184">Federation is the ability to share identities across multiple enterprises or trust domains for authentication and authorization.</span></span> <span data-ttu-id="5bfc0-185">WS-Trust 프로토콜을 사용하여 ID 표현을 트러스트 도메인 간에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-185">It uses the WS-Trust protocol to map the identity representation from one trust domain to another.</span></span> <span data-ttu-id="5bfc0-186">페더레이션 HTTP 바인딩은 SOAP 보안과 혼합 모드 보안을 지원하지만 전송 보안을 지원하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-186">Federated HTTP binding supports SOAP security as well as mixed-mode security, but it does not support transport security.</span></span> <span data-ttu-id="5bfc0-187">이 바인딩으로 구성된 서비스는 HTTP 전송을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bfc0-187">Services configured with this binding must use the HTTP transport.</span></span> [!INCLUDE[crdefault](../../../../../includes/crdefault-md.md)]<span data-ttu-id="5bfc0-188"> [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="5bfc0-188"> [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5bfc0-189">예</span><span class="sxs-lookup"><span data-stu-id="5bfc0-189">Example</span></span>  
  
```xml  
<configuration>  
<system.ServiceModel>  
<bindings>  
<ws2007FederationHttpBinding>  
    <binding   
        bypassProxyOnLocal="false"  
        transactionFlow="false"  
        hostNameComparisonMode="WeakWildcard"  
        maxReceivedMessageSize="1000"  
        messageEncoding="Mtom"   
        proxyAddress="http://www.contoso.com"   
        textEncoding="Utf16TextEncoding"  
        useDefaultWebProxy="false">  
        <reliableSession ordered="false"  
            inactivityTimeout="00:02:00" enabled="true" />  
        <security mode="None">  
           <message negotiateServiceCredential="false"  
                algorithmSuite="Aes128"  
                issuedTokenType="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1"   
                issuedKeyType="PublicKey">  
               <issuer address="http://localhost/Sts" />  
           </message>  
        </security>  
    </binding>  
</ws2007FederationBinding>  
</bindings>  
</system.ServiceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5bfc0-190">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5bfc0-190">See Also</span></span>  
 <xref:System.ServiceModel.WS2007FederationHttpBinding>  
 <xref:System.ServiceModel.Configuration.WS2007FederationHttpBindingElement>  
 [<span data-ttu-id="5bfc0-191">\<wsFederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="5bfc0-191">\<wsFederationHttpBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)  
 [<span data-ttu-id="5bfc0-192">바인딩</span><span class="sxs-lookup"><span data-stu-id="5bfc0-192">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="5bfc0-193">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="5bfc0-193">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="5bfc0-194">바인딩을 사용 하 여 Windows Communication Foundation 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="5bfc0-194">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="5bfc0-195">\<binding></span><span class="sxs-lookup"><span data-stu-id="5bfc0-195">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
