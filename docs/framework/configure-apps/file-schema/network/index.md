---
title: 네트워크 설정 스키마
ms.date: 03/30/2017
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
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: c080ff7ebef680712581d1f77fd4eb1ec99c6a86
ms.sourcegitcommit: e8dc507cfdaad504fc9d4c83d28d24569dcef91c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/03/2018
ms.locfileid: "32742616"
---
# <a name="network-settings-schema"></a><span data-ttu-id="68482-102">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="68482-102">Network Settings Schema</span></span>
<span data-ttu-id="68482-103">네트워크 설정으로 .NET Framework의 인터넷 연결 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="68482-103">Network settings specify how the .NET Framework connects to the Internet.</span></span> <span data-ttu-id="68482-104">다음 표에서는 [\<system.Net> 요소(네트워크 설정)](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)의 각 자식 구성 요소의 기능을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="68482-104">The following table describes the function of each child configuration element under the [\<system.Net> Element (Network Settings)](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md).</span></span>  
  
|<span data-ttu-id="68482-105">요소</span><span class="sxs-lookup"><span data-stu-id="68482-105">Element</span></span>|<span data-ttu-id="68482-106">설명</span><span class="sxs-lookup"><span data-stu-id="68482-106">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="68482-107">\<authenticationModules> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="68482-107">\<authenticationModules> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|<span data-ttu-id="68482-108">인터넷 요청을 인증하는 데 사용되는 모듈을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="68482-108">Specifies the modules used to authenticate Internet requests.</span></span>|  
|[<span data-ttu-id="68482-109">\<connectionManagement> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="68482-109">\<connectionManagement> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|<span data-ttu-id="68482-110">인터넷 호스트에 대한 최대 연결 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="68482-110">Specifies the maximum number of connections to Internet hosts.</span></span>|  
|[<span data-ttu-id="68482-111">\<defaultProxy> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="68482-111">\<defaultProxy> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|<span data-ttu-id="68482-112">인터넷에 대한 HTTP 요청에 사용할 프록시 서버를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="68482-112">Specifies the proxy server used for HTTP requests to the Internet.</span></span>|  
|[<span data-ttu-id="68482-113">\<mailSettings> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="68482-113">\<mailSettings> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/mailsettings-element-network-settings.md)|<span data-ttu-id="68482-114">메일 보내기 옵션에 대한 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="68482-114">Contains settings for mail sending options.</span></span>|  
|[<span data-ttu-id="68482-115">\<requestCaching> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="68482-115">\<requestCaching> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|<span data-ttu-id="68482-116">네트워크 요청에 대 한 캐싱 메커니즘을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="68482-116">Controls the caching mechanism for network requests.</span></span>|  
|[<span data-ttu-id="68482-117">\<webRequestModules> 요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="68482-117">\<webRequestModules> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|<span data-ttu-id="68482-118">인터넷 호스트 정보를 요청하는 데 사용되는 모듈을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="68482-118">Specifies the modules used to request information from Internet hosts.</span></span>|  
  
 <span data-ttu-id="68482-119">URI 설정으로 URI(Uniform Resource Identifier)를 사용하여 표현된 웹 주소를 .NET Framework에서 처리하는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="68482-119">Uri settings specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span> <span data-ttu-id="68482-120">다음 표에서는 [\<URI> 요소(URI 설정)](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)의 각 자식 구성 요소의 기능을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="68482-120">The following table describes the function of each child configuration element under the [\<Uri> Element (Uri Settings)](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md).</span></span>  
  
|<span data-ttu-id="68482-121">요소</span><span class="sxs-lookup"><span data-stu-id="68482-121">Element</span></span>|<span data-ttu-id="68482-122">설명</span><span class="sxs-lookup"><span data-stu-id="68482-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="68482-123">\<IDN> 요소(URI 설정)</span><span class="sxs-lookup"><span data-stu-id="68482-123">\<idn> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/idn-element-uri-settings.md)|<span data-ttu-id="68482-124">IDN(Internationalized Domain Name) 구문 분석이 도메인 이름에 적용되는지 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="68482-124">Specifies if Internationalized Domain Name (IDN) parsing is applied to domain names.</span></span>|  
|[<span data-ttu-id="68482-125">\<iriParsing> 요소(URI 설정)</span><span class="sxs-lookup"><span data-stu-id="68482-125">\<iriParsing> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/iriparsing-element-uri-settings.md)|<span data-ttu-id="68482-126">IRI(International Resource Identifier) 구문 분석이 <xref:System.Uri>에 적용되는지와 IRI 구문 분석 규칙을 적용해야 하는지 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="68482-126">Specifies if International Resource Identifier (IRI) parsing is applied to a <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>|  
|[<span data-ttu-id="68482-127">\<schemeSettings> 요소 (URI 설정)</span><span class="sxs-lookup"><span data-stu-id="68482-127">\<schemeSettings> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|<span data-ttu-id="68482-128">특정 체계에 대해 <xref:System.Uri>가 구문 분석되는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="68482-128">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="68482-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="68482-129">See Also</span></span>  
 [<span data-ttu-id="68482-130">인터넷 응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="68482-130">Configuring Internet Applications</span></span>](../../../../../docs/framework/network-programming/configuring-internet-applications.md)  
 [<span data-ttu-id="68482-131">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="68482-131">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
