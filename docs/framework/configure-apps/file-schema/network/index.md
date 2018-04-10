---
title: 네트워크 설정 스키마
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- elements [.NET Framework], network configuration elements
- sending data, network configuration elements
- receiving data, network configuration elements
- configuration settings [.NET Framework], networks
- Internet, network configuration elements
- network configuration elements
- network settings
- connections [.NET Framework], network configuration elements
- network resources, network configuration elements
ms.assetid: f1de5a0f-76c5-4833-819f-5222b8146340
caps.latest.revision: 14
author: mcleblanc
ms.author: markl
manager: markl
ms.workload:
- dotnet
ms.openlocfilehash: d8f13b75d0558c002fd29938ce98d85f358acc9a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="network-settings-schema"></a><span data-ttu-id="a8173-102">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="a8173-102">Network Settings Schema</span></span>
<span data-ttu-id="a8173-103">네트워크 설정으로 .NET Framework의 인터넷 연결 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a8173-103">Network settings specify how the .NET Framework connects to the Internet.</span></span> <span data-ttu-id="a8173-104">다음 표에서는 [\<system.Net> 요소(네트워크 설정)](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)의 각 자식 구성 요소의 기능을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a8173-104">The following table describes the function of each child configuration element under the [\<system.Net> Element (Network Settings)](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md).</span></span>  
  
|<span data-ttu-id="a8173-105">요소</span><span class="sxs-lookup"><span data-stu-id="a8173-105">Element</span></span>|<span data-ttu-id="a8173-106">설명</span><span class="sxs-lookup"><span data-stu-id="a8173-106">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a8173-107">\<authenticationModules> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="a8173-107">\<authenticationModules> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|<span data-ttu-id="a8173-108">인터넷 요청을 인증하는 데 사용되는 모듈을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a8173-108">Specifies the modules used to authenticate Internet requests.</span></span>|  
|[<span data-ttu-id="a8173-109">\<connectionManagement> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="a8173-109">\<connectionManagement> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|<span data-ttu-id="a8173-110">인터넷 호스트에 대한 최대 연결 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a8173-110">Specifies the maximum number of connections to Internet hosts.</span></span>|  
|[<span data-ttu-id="a8173-111">\<defaultProxy> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="a8173-111">\<defaultProxy> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|<span data-ttu-id="a8173-112">인터넷에 대한 HTTP 요청에 사용할 프록시 서버를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a8173-112">Specifies the proxy server used for HTTP requests to the Internet.</span></span>|  
|[<span data-ttu-id="a8173-113">\<mailSettings> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="a8173-113">\<mailSettings> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/mailsettings-element-network-settings.md)|<span data-ttu-id="a8173-114">메일 보내기 옵션에 대한 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="a8173-114">Contains settings for mail sending options.</span></span>|  
|[<span data-ttu-id="a8173-115">\<requestCaching> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="a8173-115">\<requestCaching> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|<span data-ttu-id="a8173-116">인터넷 호스트 정보를 요청하는 데 사용되는 모듈을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a8173-116">Specifies the modules used to request information from Internet hosts.</span></span>|  
|[<span data-ttu-id="a8173-117">\<requestCaching> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="a8173-117">\<requestCaching> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|<span data-ttu-id="a8173-118"><xref:System.Net?displayProperty=nameWithType> 네임스페이스에 대한 기본 네트워크 옵션을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="a8173-118">Configures basic network options for the <xref:System.Net?displayProperty=nameWithType> namespace.</span></span>|  
|[<span data-ttu-id="a8173-119">\<webRequestModules> 요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="a8173-119">\<webRequestModules> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|<span data-ttu-id="a8173-120">인터넷 호스트 정보를 요청하는 데 사용되는 모듈을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a8173-120">Specifies the modules used to request information from Internet hosts.</span></span>|  
  
 <span data-ttu-id="a8173-121">URI 설정으로 URI(Uniform Resource Identifier)를 사용하여 표현된 웹 주소를 .NET Framework에서 처리하는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a8173-121">Uri settings specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span> <span data-ttu-id="a8173-122">다음 표에서는 [\<URI> 요소(URI 설정)](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)의 각 자식 구성 요소의 기능을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a8173-122">The following table describes the function of each child configuration element under the [\<Uri> Element (Uri Settings)](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md).</span></span>  
  
|<span data-ttu-id="a8173-123">요소</span><span class="sxs-lookup"><span data-stu-id="a8173-123">Element</span></span>|<span data-ttu-id="a8173-124">설명</span><span class="sxs-lookup"><span data-stu-id="a8173-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a8173-125">\<IDN> 요소(URI 설정)</span><span class="sxs-lookup"><span data-stu-id="a8173-125">\<idn> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/idn-element-uri-settings.md)|<span data-ttu-id="a8173-126">IDN(Internationalized Domain Name) 구문 분석이 도메인 이름에 적용되는지 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a8173-126">Specifies if Internationalized Domain Name (IDN) parsing is applied to domain names.</span></span>|  
|[<span data-ttu-id="a8173-127">\<iriParsing> 요소(URI 설정)</span><span class="sxs-lookup"><span data-stu-id="a8173-127">\<iriParsing> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/iriparsing-element-uri-settings.md)|<span data-ttu-id="a8173-128">IRI(International Resource Identifier) 구문 분석이 <xref:System.Uri>에 적용되는지와 IRI 구문 분석 규칙을 적용해야 하는지 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a8173-128">Specifies if International Resource Identifier (IRI) parsing is applied to a <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>|  
|[<span data-ttu-id="a8173-129">\<schemeSettings> 요소 (URI 설정)</span><span class="sxs-lookup"><span data-stu-id="a8173-129">\<schemeSettings> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|<span data-ttu-id="a8173-130">특정 체계에 대해 <xref:System.Uri>가 구문 분석되는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a8173-130">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a8173-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a8173-131">See Also</span></span>  
 [<span data-ttu-id="a8173-132">인터넷 응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="a8173-132">Configuring Internet Applications</span></span>](../../../../../docs/framework/network-programming/configuring-internet-applications.md)  
 [<span data-ttu-id="a8173-133">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="a8173-133">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
