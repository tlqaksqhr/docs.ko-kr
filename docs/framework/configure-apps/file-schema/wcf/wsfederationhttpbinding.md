---
title: '&lt;wsFederationHttpBinding&gt;'
ms.date: 03/30/2017
helpviewer_keywords:
- wsFederationBinding element
ms.assetid: 9c3312b4-2137-4e71-bf3f-de1cf8e9be79
ms.openlocfilehash: d89d0aeb68aed91b28ca7358a6140e171d3b36b2
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32759428"
---
# <a name="ltwsfederationhttpbindinggt"></a><span data-ttu-id="5e7de-102">&lt;wsFederationHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="5e7de-102">&lt;wsFederationHttpBinding&gt;</span></span>
<span data-ttu-id="5e7de-103">WS-Federation을 지원하는 바인딩을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-103">Defines a binding that supports WS-Federation.</span></span>  
  
 <span data-ttu-id="5e7de-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="5e7de-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="5e7de-105">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="5e7de-105">\<bindings></span></span>  
<span data-ttu-id="5e7de-106">wsFederationBinding 요소</span><span class="sxs-lookup"><span data-stu-id="5e7de-106">wsFederationBinding element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e7de-107">구문</span><span class="sxs-lookup"><span data-stu-id="5e7de-107">Syntax</span></span>  
  
```xml  
<wsFederationHttpBinding>  
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
        textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/ Utf8TextEncoding"  
        transactionFlow="Boolean"  
        useDefaultWebProxy="Boolean">  
        <security mode="None/Message/TransportWithMessageCredential">  
         <message   
            algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
            issuedTokenType="string"   
            issuedKeyType="SymmetricKey/PublicKey"  
            negotiateServiceCredential="Boolean" >  
            <claimTypeRequirements>  
               <add claimType="URI"  
                    isOptional="Boolean" />  
            </claimTypeRequirements>  
                        <issuer address="Uri" >  
               <headers>  
                  <add name="String"  
                       namespace="String" />  
                          </headers>  
                              <identity>  
                                 <certificate encodedValue="String"/>  
                                <certificateReference findValue="String"   
                                 isChainIncluded="Boolean"  
                            storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
                                  storeLocation="LocalMachine/CurrentUser"  
                                   X509FindType=System.Security.Cryptography.X509certificates.X509findtype/>  
                                   <dns value="String"/>  
                                <rsa value="String"/>  
                                <servicePrincipalName value="String"/>  
                                <usePrincipalName value="String"/>  
                              </identity>  
                        </issuer>  
                        <issuerMetadata address=String" >  
               <headers>  
                  <add name="String"  
                       namespace="String" />  
               </headers>  
               <identity>  
                  <certificate encodedValue="String"/>  
                  <certificateReference findValue="String"   
                     isChainIncluded="Boolean"  
                     storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
                     storeLocation="LocalMachine/CurrentUser"  
                     x509FindType=System.Security.Cryptography.X509certificates.X509findtype/>  
                  <dns value="String"/>  
                  <rsa value="String"/>  
                  <servicePrincipalName value="String"/>  
                  <usePrincipalName value="String"/>  
               </identity>  
                        </issuerMetadata>  
            <tokenRequestParameters>  
               <xmlElement>  
               </xmlElement>  
            </tokenRequestParameters>  
           </message>  
        </security>  
        <reliableSession ordered="Boolean"  
           inactivityTimeout="TimeSpan"  
           enabled="Boolean" />  
       <readerQuotas             maxArrayLength="Integer"            maxBytesPerRead="Integer"            maxDepth="Integer"             maxNameTableCharCount="Integer"                     maxStringContentLength="Integer" />    </binding>  
</wsFederationBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5e7de-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="5e7de-108">Attributes and Elements</span></span>  
 <span data-ttu-id="5e7de-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5e7de-110">특성</span><span class="sxs-lookup"><span data-stu-id="5e7de-110">Attributes</span></span>  
  
|<span data-ttu-id="5e7de-111">특성</span><span class="sxs-lookup"><span data-stu-id="5e7de-111">Attribute</span></span>|<span data-ttu-id="5e7de-112">설명</span><span class="sxs-lookup"><span data-stu-id="5e7de-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5e7de-113">bypassProxyOnLocal</span><span class="sxs-lookup"><span data-stu-id="5e7de-113">bypassProxyOnLocal</span></span>|<span data-ttu-id="5e7de-114">로컬 주소에 대해 프록시 서버를 사용하지 않을 것인지 여부를 나타내는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-114">A Boolean value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="5e7de-115">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-115">The default is `false`.</span></span>|  
|<span data-ttu-id="5e7de-116">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="5e7de-116">closeTimeout</span></span>|<span data-ttu-id="5e7de-117">닫기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-117">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="5e7de-118">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-118">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="5e7de-119">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-119">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="5e7de-120">hostnameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="5e7de-120">hostnameComparisonMode</span></span>|<span data-ttu-id="5e7de-121">URI 구문 분석에 사용되는 HTTP 호스트 이름 비교 모드를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-121">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="5e7de-122">이 특성은 <xref:System.ServiceModel.HostNameComparisonMode> 형식이며 URI에 대해 비교할 때 호스트 이름이 서비스에 연결하는 데 사용되는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-122">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="5e7de-123">기본값은 <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>이며 이 값은 비교 시 호스트 이름을 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-123">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|  
|<span data-ttu-id="5e7de-124">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="5e7de-124">maxBufferPoolSize</span></span>|<span data-ttu-id="5e7de-125">이 바인딩의 최대 버퍼 풀 크기를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-125">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="5e7de-126">기본값은 524,288바이트(512 \* 1024)입니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-126">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="5e7de-127">WCF(Windows Communication Foundation)의 많은 부분에서 버퍼를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-127">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="5e7de-128">버퍼를 사용할 때마다 만들고 삭제하면 비용이 많이 들며, 버퍼에 대한 가비지 수집 역시 비용이 많이 듭니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-128">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="5e7de-129">버퍼 풀이 있으면 이 풀로부터 버퍼를 가져와 사용한 다음 다시 풀로 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-129">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="5e7de-130">따라서 버퍼를 만들고 삭제하는 데 오버헤드를 피할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-130">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="5e7de-131">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="5e7de-131">maxReceivedMessageSize</span></span>|<span data-ttu-id="5e7de-132">헤더를 비롯하여 이 바인딩으로 구성된 채널에서 받을 수 있는 최대 메시지 크기(바이트)를 지정하는 양의 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-132">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="5e7de-133">이 한도를 초과하는 메시지를 보낸 사람은 SOAP 오류를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-133">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="5e7de-134">수신자는 메시지를 삭제하고 추적 로그에 이벤트 항목을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-134">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="5e7de-135">기본값은 65536입니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-135">The default is 65536.</span></span>|  
|<span data-ttu-id="5e7de-136">messageEncoding</span><span class="sxs-lookup"><span data-stu-id="5e7de-136">messageEncoding</span></span>|<span data-ttu-id="5e7de-137">메시지를 인코딩하는 데 사용되는 인코더를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-137">Defines the encoder used to encode the message.</span></span> <span data-ttu-id="5e7de-138">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-138">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="5e7de-139">-Text: 텍스트 메시지 인코더를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-139">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="5e7de-140">Mtom: 조직 메커니즘 1.0 MTOM (Message Transmission) 인코더를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-140">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><br /> <span data-ttu-id="5e7de-141">기본값은 Text입니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-141">The default is Text.</span></span><br /><br /> <span data-ttu-id="5e7de-142">이 특성은 <xref:System.ServiceModel.WSMessageEncoding> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-142">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|  
|<span data-ttu-id="5e7de-143">name</span><span class="sxs-lookup"><span data-stu-id="5e7de-143">name</span></span>|<span data-ttu-id="5e7de-144">바인딩의 구성 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-144">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="5e7de-145">이 값은 바인딩의 ID로 사용되므로 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-145">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="5e7de-146">[!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)]부터는 바인딩 및 동작에 이름이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-146">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="5e7de-147">기본 구성 및 이름이 없는 바인딩 및 동작에 대 한 자세한 내용은 참조 [단순화 된 구성](../../../../../docs/framework/wcf/simplified-configuration.md) 및 [WCF 서비스에 대 한 구성을 단순화](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-147">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|<span data-ttu-id="5e7de-148">openTimeout</span><span class="sxs-lookup"><span data-stu-id="5e7de-148">openTimeout</span></span>|<span data-ttu-id="5e7de-149">열기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-149">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="5e7de-150">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-150">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="5e7de-151">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-151">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="5e7de-152">privactyNoticeAt</span><span class="sxs-lookup"><span data-stu-id="5e7de-152">privactyNoticeAt</span></span>|<span data-ttu-id="5e7de-153">개인 정보 알림이 있는 URI를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-153">A String that specifies a URI at which the privacy notice is located.</span></span>|  
|<span data-ttu-id="5e7de-154">privactyNoticeVersion</span><span class="sxs-lookup"><span data-stu-id="5e7de-154">privactyNoticeVersion</span></span>|<span data-ttu-id="5e7de-155">현재 개인 정보 알림의 버전을 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-155">An integer that specifies the version of the current privacy notice.</span></span>|  
|<span data-ttu-id="5e7de-156">proxyAddress</span><span class="sxs-lookup"><span data-stu-id="5e7de-156">proxyAddress</span></span>|<span data-ttu-id="5e7de-157">HTTP 프록시의 주소를 지정하는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-157">A URI that specifies the address of the HTTP proxy.</span></span> <span data-ttu-id="5e7de-158">`useDefaultWebProxy`가 `true`일 경우 이 설정은 `null`이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-158">If `useDefaultWebProxy` is `true`, this setting must be `null`.</span></span> <span data-ttu-id="5e7de-159">기본값은 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-159">The default is `null`.</span></span>|  
|<span data-ttu-id="5e7de-160">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="5e7de-160">receiveTimeout</span></span>|<span data-ttu-id="5e7de-161">받기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-161">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="5e7de-162">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-162">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="5e7de-163">기본값은 00:10:00입니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-163">The default is 00:10:00.</span></span>|  
|<span data-ttu-id="5e7de-164">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="5e7de-164">sendTimeout</span></span>|<span data-ttu-id="5e7de-165">보내기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-165">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="5e7de-166">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-166">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="5e7de-167">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-167">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="5e7de-168">textEncoding</span><span class="sxs-lookup"><span data-stu-id="5e7de-168">textEncoding</span></span>|<span data-ttu-id="5e7de-169">바인딩에서 메시지를 내보내는 데 사용되는 문자 집합 인코딩을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-169">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="5e7de-170">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-170">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="5e7de-171">-BigEndianUnicode: 유니코드 BigEndian 인코딩입니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-171">-   BigEndianUnicode: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="5e7de-172">-Unicode: 16 비트 인코딩입니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-172">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="5e7de-173">UTF8: 8 비트 인코딩</span><span class="sxs-lookup"><span data-stu-id="5e7de-173">-   UTF8: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="5e7de-174">기본값은 UTF8입니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-174">The default is UTF8.</span></span> <span data-ttu-id="5e7de-175">이 특성은 <xref:System.Text.Encoding> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-175">This attribute is of type <xref:System.Text.Encoding>..</span></span>|  
|<span data-ttu-id="5e7de-176">transactionFlow</span><span class="sxs-lookup"><span data-stu-id="5e7de-176">transactionFlow</span></span>|<span data-ttu-id="5e7de-177">바인딩에서 WS-Transactions 이동을 지원할지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-177">A Boolean value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="5e7de-178">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-178">The default is `false`.</span></span>|  
|<span data-ttu-id="5e7de-179">useDefaultWebProxy</span><span class="sxs-lookup"><span data-stu-id="5e7de-179">useDefaultWebProxy</span></span>|<span data-ttu-id="5e7de-180">시스템의 자동 구성된 HTTP 프록시 사용 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-180">A Boolean value that indicates whether the system’s auto-configured HTTP proxy is used.</span></span> <span data-ttu-id="5e7de-181">이 특성이 `null`이면 프록시 주소는 `true`이어야 합니다(설정되지 않음).</span><span class="sxs-lookup"><span data-stu-id="5e7de-181">The proxy address must be `null` (that is, not set) if this attribute is `true`.</span></span> <span data-ttu-id="5e7de-182">기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-182">The default is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5e7de-183">자식 요소</span><span class="sxs-lookup"><span data-stu-id="5e7de-183">Child Elements</span></span>  
  
|<span data-ttu-id="5e7de-184">요소</span><span class="sxs-lookup"><span data-stu-id="5e7de-184">Element</span></span>|<span data-ttu-id="5e7de-185">설명</span><span class="sxs-lookup"><span data-stu-id="5e7de-185">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5e7de-186">\<security></span><span class="sxs-lookup"><span data-stu-id="5e7de-186">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md)|<span data-ttu-id="5e7de-187">메시지에 대한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-187">Defines the security settings for the message.</span></span> <span data-ttu-id="5e7de-188">이 요소는 <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-188">This element is of type <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>.</span></span>|  
|[<span data-ttu-id="5e7de-189">\<readerQuotas></span><span class="sxs-lookup"><span data-stu-id="5e7de-189">\<readerQuotas></span></span>](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="5e7de-190">이 바인딩으로 구성된 끝점에서 처리할 수 있는 SOAP 메시지의 복잡성에 대한 제약 조건을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-190">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="5e7de-191">이 요소는 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-191">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|[<span data-ttu-id="5e7de-192">reliableSession</span><span class="sxs-lookup"><span data-stu-id="5e7de-192">reliableSession</span></span>](http://msdn.microsoft.com/library/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b)|<span data-ttu-id="5e7de-193">채널 끝점 간에 신뢰할 수 있는 세션이 설정되는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-193">Specifies if reliable sessions are established between channel endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5e7de-194">부모 요소</span><span class="sxs-lookup"><span data-stu-id="5e7de-194">Parent Elements</span></span>  
  
|<span data-ttu-id="5e7de-195">요소</span><span class="sxs-lookup"><span data-stu-id="5e7de-195">Element</span></span>|<span data-ttu-id="5e7de-196">설명</span><span class="sxs-lookup"><span data-stu-id="5e7de-196">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5e7de-197">\<bindings></span><span class="sxs-lookup"><span data-stu-id="5e7de-197">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="5e7de-198">이 요소는 표준 및 사용자 지정 바인딩의 컬렉션을 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-198">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5e7de-199">설명</span><span class="sxs-lookup"><span data-stu-id="5e7de-199">Remarks</span></span>  
 <span data-ttu-id="5e7de-200">페더레이션은 인증 및 권한 부여를 위해 여러 시스템에서 ID를 공유하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-200">Federation is the ability to share identities across multiple systems for authentication and authorization.</span></span> <span data-ttu-id="5e7de-201">이러한 ID는 사용자나 시스템을 가리킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-201">These identities can refer to users or to machines.</span></span> <span data-ttu-id="5e7de-202">페더레이션 HTTP는 SOAP 보안과 혼합 모드 보안을 모두 지원하지만 전송 보안만을 사용하여 지원하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-202">Federated HTTP supports SOAP security as well as mixed-mode security, but it does not support exclusively using transport security.</span></span> <span data-ttu-id="5e7de-203">이 바인딩은 WS-페더레이션 프로토콜에 대 한 Windows Communication Foundation (WCF) 지원을 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-203">This binding provides Windows Communication Foundation (WCF) support for the WS-Federation protocol.</span></span> <span data-ttu-id="5e7de-204">이 바인딩으로 구성된 서비스는 HTTP 전송을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-204">Services configured with this binding must use the HTTP transport.</span></span>  
  
 <span data-ttu-id="5e7de-205">바인딩은 바인딩 요소의 스택으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-205">Bindings consist of a stack of binding elements.</span></span> <span data-ttu-id="5e7de-206"> 가 기본값인 로 설정된 경우</span><span class="sxs-lookup"><span data-stu-id="5e7de-206">The stack of binding elements in</span></span>  
  
 <span data-ttu-id="5e7de-207">`wsFederationHttpBinding`에 있는 바인딩 요소의 스택은`wsHttpBinding`</span><span class="sxs-lookup"><span data-stu-id="5e7de-207">`wsFederationHttpBinding` is the same as that contained in `wsHttpBinding`</span></span>  
  
 <span data-ttu-id="5e7de-208">때 [ \<보안 >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md) 기본값인으로 설정 된 <xref:System.ServiceModel.WSFederationHttpSecurityMode.Message>합니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-208">when [\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md) is set to the default value of <xref:System.ServiceModel.WSFederationHttpSecurityMode.Message>.</span></span>  
  
 <span data-ttu-id="5e7de-209">`wsFederationHttpBinding` 의 메시지 보안 설정의 세부 내용을 제어 [ \<메시지 >](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-209">The `wsFederationHttpBinding` controls the details of the message security settings in [\<message>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md).</span></span> <span data-ttu-id="5e7de-210">[ \<보안 >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md) 요소는 바인딩에 사용 되는 보안 바인딩을 만든 후 변경할 수 없을 때에 액세스 권한의 얻을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-210">Note that the [\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md) element provides get access only as the security used by the binding cannot be changed once the binding is created.</span></span>  
  
 <span data-ttu-id="5e7de-211">`wsFederationHttpBinding`은 또한 privactyNoticeAt 특성을 제공하여 개인 정보 알림이 있는 URI를 설정하고 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-211">The `wsFederationHttpBinding` also provides a privactyNoticeAt attribute to set and retrieve the URI at which the privacy notice is located.</span></span>  
  
 <span data-ttu-id="5e7de-212">정책 보안을 유지하는 것은 페더레이션 시나리오에서 특히 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-212">Keeping policy secure is especially important in federation scenarios.</span></span> <span data-ttu-id="5e7de-213">HTTPS와 같은 특정 형식의 보안을 사용하여 악의적인 사용자로부터 정책을 보호할 것을 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-213">The recommendation is to use some form of security, such as HTTPS, to protect the policy from malicious users.</span></span>  
  
 <span data-ttu-id="5e7de-214">이러한 바인딩을 사용하는 페더레이션 시나리오에서 서비스 정책은 발급된(SAML) 토큰을 암호화하기 위한 키, 토큰에 추가할 클레임 형식 등의 중요한 정보를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-214">In federation scenarios using this binding, the service policy potentially has important information such as the key to use to encrypt the issued (SAML) token, the type of claims to put in the token, and so forth.</span></span> <span data-ttu-id="5e7de-215">이 정책이 훼손되면 공격자는 발급된 토큰의 키를 확인할 수 있게 되므로 추가적인 정보 변조, 정보 노출 및 기타 악의적인 동작이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-215">If this policy is tampered with, an attacker could discover the key of the issued token leading to further tampering, info disclosure and other malicious behavior.</span></span> <span data-ttu-id="5e7de-216">이를 방지하려면 정책을 서비스에서 안전하게(예: HTTPS 사용) 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-216">To help prevent this, the policy must be obtained securely (for example using HTTPS) from the service.</span></span>  
  
 <span data-ttu-id="5e7de-217">이 바인딩에 대 한 자세한 내용은 참조 하십시오. [하는 방법: WSFederationHttpBinding 만들기](../../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5e7de-217">For more information on this binding, see [How to: Create a WSFederationHttpBinding](../../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5e7de-218">예제</span><span class="sxs-lookup"><span data-stu-id="5e7de-218">Example</span></span>  
  
```xml  
<configuration>  
<system.ServiceModel>  
<bindings>  
<wsFederationHttpBinding>  
    <binding   
        bypassProxyOnLocal="false"  
        transactionFlow="false"  
        hostNameComparisonMode="WeakWildcard"  
        maxReceivedMessageSize="1000"  
        messageEncoding="Mtom"   
        proxyAddress="http://foo/bar"   
        textEncoding="Utf16TextEncoding"  
        useDefaultWebProxy="false">  
        <reliableSession ordered="false"  
            inactivityTimeout="00:02:00" enabled="true" />  
        <security mode="None">  
           <message negotiateServiceCredential="false"  
                algorithmSuite="Aes128"  
                issuedTokenType="saml"   
                issuedKeyType="PublicKey">  
               <issuer address="http://localhost/Sts" />  
           </message>  
        </security>  
    </binding>  
</wsFederationBinding>  
</bindings>  
</system.ServiceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5e7de-219">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5e7de-219">See Also</span></span>  
 <xref:System.ServiceModel.WSFederationHttpBinding>  
 <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement>  
 [<span data-ttu-id="5e7de-220">방법: WSFederationHttpBinding 만들기</span><span class="sxs-lookup"><span data-stu-id="5e7de-220">How to: Create a WSFederationHttpBinding</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)  
 [<span data-ttu-id="5e7de-221">바인딩</span><span class="sxs-lookup"><span data-stu-id="5e7de-221">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="5e7de-222">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="5e7de-222">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="5e7de-223">바인딩을 사용 하 여 Windows Communication Foundation 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="5e7de-223">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="5e7de-224">\<binding></span><span class="sxs-lookup"><span data-stu-id="5e7de-224">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
