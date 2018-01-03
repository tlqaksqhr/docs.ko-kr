---
title: '&lt;ws2007HttpBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8586ecc9-bdaa-44d6-8d4d-7038e4ea1741
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0a92ab5b85a65793473dcafbd67ac710912a476f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltws2007httpbindinggt"></a><span data-ttu-id="9402c-102">&lt;ws2007HttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="9402c-102">&lt;ws2007HttpBinding&gt;</span></span>
<span data-ttu-id="9402c-103">올바른 버전의 <xref:System.ServiceModel.WSHttpBinding.Security%2A>, <xref:System.ServiceModel.ReliableSession> 및 <xref:System.ServiceModel.WSHttpBindingBase.TransactionFlow%2A> 바인딩 요소를 지원하는 상호 운용 가능한 바인딩을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9402c-103">Defines an interoperable binding that provides support for the correct versions of the <xref:System.ServiceModel.WSHttpBinding.Security%2A>, <xref:System.ServiceModel.ReliableSession>, and <xref:System.ServiceModel.WSHttpBindingBase.TransactionFlow%2A> binding elements.</span></span>  
  
 <span data-ttu-id="9402c-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="9402c-104">\<system.serviceModel></span></span>  
<span data-ttu-id="9402c-105">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="9402c-105">\<bindings></span></span>  
<span data-ttu-id="9402c-106">\<ws2007HttpBinding ></span><span class="sxs-lookup"><span data-stu-id="9402c-106">\<ws2007HttpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9402c-107">구문</span><span class="sxs-lookup"><span data-stu-id="9402c-107">Syntax</span></span>  
  
```xml  
<ws2007HttpBinding>  
    <binding   
        allowCookies="Boolean"  
        bypassProxyOnLocal="Boolean"  
        closeTimeout="TimeSpan"  
        hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"  
        maxBufferPoolSize="integer"  
        maxReceivedMessageSize="Integer"  
        messageEncoding="Text/Mtom"   
                name="string"  
        openTimeout="TimeSpan"   
        proxyAddress="URI"  
        receiveTimeout="TimeSpan"  
        sendTimeout="TimeSpan"  
  
textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding"  
        transactionFlow="Boolean"  
        useDefaultWebProxy="Boolean">  
        <reliableSession ordered="Boolean"  
           inactivityTimeout="TimeSpan"  
           enabled="Boolean" />  
        <security mode="Message/None/Transport/TransportWithCredential">  
           <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"  
                proxyCredentialType="Basic/Digest/None/Ntlm/Windows"  
                realm="string"   
                                />  
          <message clientCredentialType ="Certificate/IssuedToken/None/UserName/Windows"  
           negotiateServiceCredential="Boolean"  
           algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
           establishSecurityContext="Boolean"   
           negotiateServiceCredential="Boolean"/>  
        </security>  
       <readerQuotas             maxArrayLength="Integer"            maxBytesPerRead="Integer"            maxDepth="Integer"             maxNameTableCharCount="Integer"                     maxStringContentLength="Integer" />    </binding>  
</ws2007HttpBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9402c-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="9402c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="9402c-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9402c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9402c-110">특성</span><span class="sxs-lookup"><span data-stu-id="9402c-110">Attributes</span></span>  
  
|<span data-ttu-id="9402c-111">특성</span><span class="sxs-lookup"><span data-stu-id="9402c-111">Attribute</span></span>|<span data-ttu-id="9402c-112">설명</span><span class="sxs-lookup"><span data-stu-id="9402c-112">Description</span></span>|  
|---------------|-----------------|  
|`allowCookies`|<span data-ttu-id="9402c-113">클라이언트가 쿠키를 수락하고 그러한 쿠키를 이후 요청에 전파할지 여부를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9402c-113">A value that indicates whether the client accepts cookies and propagates them on future requests.</span></span> <span data-ttu-id="9402c-114">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="9402c-114">The default is `false`.</span></span><br /><br /> <span data-ttu-id="9402c-115">쿠키를 사용하는 ASP.NET 웹 서비스(ASMX)와 상호 작용할 때 이 속성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9402c-115">You can use this property when you interact with ASP.NET Web services (ASMX) that use cookies.</span></span> <span data-ttu-id="9402c-116">이 속성을 사용하면 서버에서 반환하는 쿠키가 해당 서비스에 대한 이후의 모든 클라이언트 요청에 자동으로 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="9402c-116">This ensures that cookies that the server returns are automatically copied to all future client requests for that service.</span></span>|  
|`bypassProxyOnLocal`|<span data-ttu-id="9402c-117">로컬 주소에 대해 프록시 서버를 우회할지 여부를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9402c-117">A value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="9402c-118">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="9402c-118">The default is `false`.</span></span>|  
|`closeTimeout`|<span data-ttu-id="9402c-119">닫기 작업을 완료하기 위한 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9402c-119">A <xref:System.TimeSpan> value that specifies the time interval for a close operation to complete.</span></span> <span data-ttu-id="9402c-120">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9402c-120">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="9402c-121">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="9402c-121">The default is 00:01:00.</span></span>|  
|`hostnameComparisonMode`|<span data-ttu-id="9402c-122">URI(Uniform Resource Identifier) 구문 분석에 사용되는 HTTP 호스트 이름 비교 모드를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9402c-122">Specifies the HTTP hostname comparison mode used to parse Uniform Resource Identifiers (URIs).</span></span> <span data-ttu-id="9402c-123">이 특성은 <xref:System.ServiceModel.HostNameComparisonMode> 형식이며 URI에 대해 비교할 때 호스트 이름이 서비스에 연결하는 데 사용되는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9402c-123">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="9402c-124">기본값은 <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>이며 이 값은 비교 시 호스트 이름을 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="9402c-124">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="9402c-125">이 바인딩에 대한 최대 버퍼 풀 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="9402c-125">The maximum buffer pool size for this binding.</span></span> <span data-ttu-id="9402c-126">기본값은 524,288바이트(512 x 1,024)입니다.</span><span class="sxs-lookup"><span data-stu-id="9402c-126">The default is 524,288 bytes (512 × 1,024).</span></span> <span data-ttu-id="9402c-127">[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]의 많은 부분에서 버퍼를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9402c-127">Many parts of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] use buffers.</span></span> <span data-ttu-id="9402c-128">버퍼가 필요할 때마다 버퍼를 만들고 삭제하면 비용이 많이 들며, 버퍼에 대한 가비지 수집 비용도 무시할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9402c-128">Creating and destroying buffers each time they are used is expensive, as is garbage collection for buffers.</span></span> <span data-ttu-id="9402c-129">버퍼 풀이 있으면 이 풀에서 버퍼를 가져와 사용한 다음 다시 풀로 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9402c-129">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool when you are done.</span></span> <span data-ttu-id="9402c-130">따라서 버퍼를 만들고 삭제하는 오버헤드를 피할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9402c-130">This avoids the overhead in creating and destroying buffers.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="9402c-131">이 바인딩으로 구성된 채널에서 받을 수 있는 최대 메시지 크기(헤더 포함)로 단위는 바이트입니다.</span><span class="sxs-lookup"><span data-stu-id="9402c-131">The maximum message size, in bytes, including headers, which a channel configured with this binding, can receive.</span></span> <span data-ttu-id="9402c-132">이 한도를 초과하는 메시지를 보낸 발신자는 SOAP 오류를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="9402c-132">The sender of a message exceeding this limit receives a SOAP fault.</span></span> <span data-ttu-id="9402c-133">수신자는 메시지를 삭제하고 추적 로그에 이벤트 항목을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9402c-133">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="9402c-134">기본값은 65536입니다.</span><span class="sxs-lookup"><span data-stu-id="9402c-134">The default is 65536.</span></span>|  
|`messageEncoding`|<span data-ttu-id="9402c-135">메시지를 인코딩하는 데 사용되는 인코더를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9402c-135">Defines the encoder used to encode the message.</span></span> <span data-ttu-id="9402c-136">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9402c-136">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="9402c-137">-   `Text`: 텍스트 메시지 인코더를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9402c-137">-   `Text`: Use a text message encoder.</span></span><br /><span data-ttu-id="9402c-138">-   `Mtom`: 조직 메커니즘 1.0 MTOM (Message Transmission) 인코더를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9402c-138">-   `Mtom`: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><br /> <span data-ttu-id="9402c-139">기본값은 `Text`입니다.</span><span class="sxs-lookup"><span data-stu-id="9402c-139">The default is `Text`.</span></span><br /><br /> <span data-ttu-id="9402c-140">이 특성은 <xref:System.ServiceModel.WSMessageEncoding> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="9402c-140">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|  
|`name`|<span data-ttu-id="9402c-141">바인딩의 구성 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9402c-141">The configuration name of the binding.</span></span> <span data-ttu-id="9402c-142">이 값은 바인딩의 ID로 사용되므로 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9402c-142">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="9402c-143">[!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)]부터는 바인딩 및 동작에 이름이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9402c-143">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="9402c-144">기본 구성 및 이름이 없는 바인딩 및 동작에 대 한 자세한 내용은 참조 [단순화 된 구성](../../../../../docs/framework/wcf/simplified-configuration.md) 및 [WCF 서비스에 대 한 구성을 단순화](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9402c-144">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="9402c-145">열기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9402c-145">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="9402c-146">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9402c-146">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="9402c-147">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="9402c-147">The default is 00:01:00.</span></span>|  
|`proxyAddress`|<span data-ttu-id="9402c-148">HTTP 프록시의 주소를 지정하는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="9402c-148">A URI that specifies the address of the HTTP proxy.</span></span> <span data-ttu-id="9402c-149">`useSystemWebProxy`가 `true`일 경우 이 설정은 `null`이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9402c-149">If `useSystemWebProxy` is `true`, this setting must be `null`.</span></span> <span data-ttu-id="9402c-150">기본값은 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="9402c-150">The default is `null`.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="9402c-151">받기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9402c-151">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="9402c-152">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9402c-152">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="9402c-153">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="9402c-153">The default is 00:01:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="9402c-154">보내기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9402c-154">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="9402c-155">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9402c-155">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="9402c-156">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="9402c-156">The default is 00:01:00.</span></span>|  
|`textEncoding`|<span data-ttu-id="9402c-157">바인딩에서 메시지를 내보내는 데 사용할 문자 집합 인코딩을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9402c-157">Specifies the character set encoding to use for emitting messages on the binding.</span></span> <span data-ttu-id="9402c-158">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9402c-158">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="9402c-159">-   `UnicodeFffeTextEncoding`: 유니코드 Big Endian 인코딩.</span><span class="sxs-lookup"><span data-stu-id="9402c-159">-   `UnicodeFffeTextEncoding`: Unicode Big Endian encoding.</span></span><br /><span data-ttu-id="9402c-160">-   `Utf16TextEncoding`: 16 비트 인코딩입니다.</span><span class="sxs-lookup"><span data-stu-id="9402c-160">-   `Utf16TextEncoding`: 16-bit encoding.</span></span><br /><span data-ttu-id="9402c-161">-   `Utf8TextEncoding`: 8 비트 인코딩입니다.</span><span class="sxs-lookup"><span data-stu-id="9402c-161">-   `Utf8TextEncoding`: 8-bit encoding.</span></span><br /><br /> <span data-ttu-id="9402c-162">기본값은 `Utf8TextEncoding`입니다.</span><span class="sxs-lookup"><span data-stu-id="9402c-162">The default is `Utf8TextEncoding`.</span></span><br /><br /> <span data-ttu-id="9402c-163">이 특성은 <xref:System.Text.Encoding> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="9402c-163">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|`transactionFlow`|<span data-ttu-id="9402c-164">바인딩에서 WS-트랜잭션 이동을 지원할지 여부를 지정하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9402c-164">A value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="9402c-165">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="9402c-165">The default is `false`.</span></span>|  
|`useDefaultWebProxy`|<span data-ttu-id="9402c-166">시스템의 자동 구성된 HTTP 프록시 사용 여부를 지정하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9402c-166">A value that specifies whether the system’s auto-configured HTTP proxy is used.</span></span> <span data-ttu-id="9402c-167">기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="9402c-167">The default is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9402c-168">자식 요소</span><span class="sxs-lookup"><span data-stu-id="9402c-168">Child Elements</span></span>  
  
|<span data-ttu-id="9402c-169">요소</span><span class="sxs-lookup"><span data-stu-id="9402c-169">Element</span></span>|<span data-ttu-id="9402c-170">설명</span><span class="sxs-lookup"><span data-stu-id="9402c-170">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9402c-171">\<보안 ></span><span class="sxs-lookup"><span data-stu-id="9402c-171">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md)|<span data-ttu-id="9402c-172">바인딩에 대한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9402c-172">Defines the security settings for the binding.</span></span> <span data-ttu-id="9402c-173">이 요소는 <xref:System.ServiceModel.Configuration.WSHttpSecurityElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="9402c-173">This element is of type <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>.</span></span>|  
|[<span data-ttu-id="9402c-174">\<readerQuotas ></span><span class="sxs-lookup"><span data-stu-id="9402c-174">\<readerQuotas></span></span>](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="9402c-175">이 바인딩으로 구성된 끝점에서 처리할 수 있는 SOAP 메시지의 복잡성에 대한 제약 조건을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9402c-175">Defines the constraints on the complexity of SOAP messages that endpoints configured with this binding can process.</span></span> <span data-ttu-id="9402c-176">이 요소는 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="9402c-176">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|[<span data-ttu-id="9402c-177">reliableSession</span><span class="sxs-lookup"><span data-stu-id="9402c-177">reliableSession</span></span>](http://msdn.microsoft.com/en-us/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b)|<span data-ttu-id="9402c-178">채널 끝점 간에 신뢰할 수 있는 세션이 설정되는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9402c-178">Specifies whether reliable sessions are established between channel endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9402c-179">부모 요소</span><span class="sxs-lookup"><span data-stu-id="9402c-179">Parent Elements</span></span>  
  
|<span data-ttu-id="9402c-180">요소</span><span class="sxs-lookup"><span data-stu-id="9402c-180">Element</span></span>|<span data-ttu-id="9402c-181">설명</span><span class="sxs-lookup"><span data-stu-id="9402c-181">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9402c-182">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="9402c-182">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="9402c-183">이 요소는 표준 및 사용자 지정 바인딩의 컬렉션을 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="9402c-183">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9402c-184">설명</span><span class="sxs-lookup"><span data-stu-id="9402c-184">Remarks</span></span>  
 <span data-ttu-id="9402c-185">`WS2007HttpBinding`은 `WSHttpBinding`과 비슷한 시스템 제공 바인딩을 추가하지만, OASIS(Organization for the Advancement of Structured Information Standards) 표준 버전의 ReliableSession, Security 및 TransactionFlow 프로토콜을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9402c-185">The `WS2007HttpBinding` adds a system-provided binding similar to `WSHttpBinding` but uses the Organization for the Advancement of Structured Information Standards (OASIS) standard versions of the ReliableSession, Security, and TransactionFlow protocols.</span></span> <span data-ttu-id="9402c-186">이 바인딩을 사용할 때는 개체 모델이나 기본 설정을 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9402c-186">No changes to the object model or default settings are required when using this binding.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9402c-187">예</span><span class="sxs-lookup"><span data-stu-id="9402c-187">Example</span></span>  
  
```xml  
<configuration>  
    <system.ServiceModel>  
        <bindings>  
            <ws2007HttpBinding>  
                <binding   
                    closeTimeout="00:00:10"  
                    openTimeout="00:00:20"   
                    receiveTimeout="00:00:30"  
                    sendTimeout="00:00:40"  
                    bypassProxyOnLocal="false"  
                    transactionFlow="false"   
                    hostNameComparisonMode="WeakWildcard"  
                    maxReceivedMessageSize="1000"  
                    messageEncoding="Mtom"   
                    proxyAddress="http://www.contoso.com"  
                    textEncoding="utf-16"  
                    useDefaultWebProxy="false">  
                    <reliableSession ordered="false"  
                         inactivityTimeout="00:02:00"  
                         enabled="true" />  
                    <security mode="Transport">  
                         <transport clientCredentialType="Digest"  
                            proxyCredentialType="None"  
                            realm="someRealm" />  
                         <message clientCredentialType="Windows"  
                            negotiateServiceCredential="false"  
                            algorithmSuite="Aes128"   
                            defaultProtectionLevel="None" />  
                    </security>  
                </binding>  
           </ws2007HttpBinding>  
        </bindings>  
    </system.ServiceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9402c-188">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9402c-188">See Also</span></span>  
 <xref:System.ServiceModel.WS2007HttpBinding>  
 <xref:System.ServiceModel.Configuration.WS2007HttpBindingElement>  
 [<span data-ttu-id="9402c-189">바인딩</span><span class="sxs-lookup"><span data-stu-id="9402c-189">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="9402c-190">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="9402c-190">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="9402c-191">바인딩을 사용 하 여 Windows Communication Foundation 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="9402c-191">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="9402c-192">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="9402c-192">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
