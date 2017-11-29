---
title: "&lt;system.Net&gt; 요소 (네트워크 설정)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.Net
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.Net
helpviewer_keywords:
- system.Net element
- <system.Net> element
ms.assetid: 52de4d6c-b24d-44aa-ba7d-6b5061f1357e
caps.latest.revision: "14"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: d2eb903b8a84410aa08504c12e78a016d2368923
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltsystemnetgt-element-network-settings"></a><span data-ttu-id="917a7-102">&lt;system.Net&gt; 요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="917a7-102">&lt;system.Net&gt; Element (Network Settings)</span></span>
<span data-ttu-id="917a7-103">.NET Framework의 네트워크 연결 방법을 지정하는 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="917a7-103">Contains settings that specify how the .NET Framework connects to the network.</span></span>  
  
 <span data-ttu-id="917a7-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="917a7-104">\<configuration></span></span>  
<span data-ttu-id="917a7-105">\<system.net ></span><span class="sxs-lookup"><span data-stu-id="917a7-105">\<system.net></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="917a7-106">구문</span><span class="sxs-lookup"><span data-stu-id="917a7-106">Syntax</span></span>  
  
```xml  
<system.net>   
</system.net>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="917a7-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="917a7-107">Attributes and Elements</span></span>  
 <span data-ttu-id="917a7-108">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="917a7-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="917a7-109">특성</span><span class="sxs-lookup"><span data-stu-id="917a7-109">Attributes</span></span>  
 <span data-ttu-id="917a7-110">없음</span><span class="sxs-lookup"><span data-stu-id="917a7-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="917a7-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="917a7-111">Child Elements</span></span>  
  
|<span data-ttu-id="917a7-112">**요소**</span><span class="sxs-lookup"><span data-stu-id="917a7-112">**Element**</span></span>|<span data-ttu-id="917a7-113">**설명**</span><span class="sxs-lookup"><span data-stu-id="917a7-113">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="917a7-114">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="917a7-114">authenticationModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|<span data-ttu-id="917a7-115">인터넷 요청을 인증 하는 데 사용 되는 모듈을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="917a7-115">Specifies modules used to authenticate Internet requests.</span></span>|  
|[<span data-ttu-id="917a7-116">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="917a7-116">connectionManagement</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|<span data-ttu-id="917a7-117">인터넷 호스트에 대 한 연결의 최대 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="917a7-117">Specifies the maximum number of connections to an Internet host.</span></span>|  
|[<span data-ttu-id="917a7-118">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="917a7-118">defaultProxy</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|<span data-ttu-id="917a7-119">HTTP(Hypertext Transfer Protocol) 프록시 서버를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="917a7-119">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
|[<span data-ttu-id="917a7-120">mailSettings</span><span class="sxs-lookup"><span data-stu-id="917a7-120">mailSettings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/mailsettings-element-network-settings.md)|<span data-ttu-id="917a7-121">전송 프로토콜 SMTP (Simple Mail) 메일 보내기 옵션을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="917a7-121">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
|[<span data-ttu-id="917a7-122">requestCaching</span><span class="sxs-lookup"><span data-stu-id="917a7-122">requestCaching</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|<span data-ttu-id="917a7-123">네트워크 요청에 대 한 캐싱 메커니즘을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="917a7-123">Controls the caching mechanism for network requests.</span></span>|  
|[<span data-ttu-id="917a7-124">설정</span><span class="sxs-lookup"><span data-stu-id="917a7-124">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="917a7-125">클래스에 대 한 기본 네트워크 옵션을 구성 된 <xref:System.Net> 및 관련 자식 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="917a7-125">Configures basic network options for classes in the <xref:System.Net> and related child namespaces.</span></span>|  
|[<span data-ttu-id="917a7-126">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="917a7-126">webRequestModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|<span data-ttu-id="917a7-127">인터넷 호스트에서 정보를 요청 하는 데는 모듈을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="917a7-127">Specifies modules to use to request information from Internet hosts.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="917a7-128">부모 요소</span><span class="sxs-lookup"><span data-stu-id="917a7-128">Parent Elements</span></span>  
  
|<span data-ttu-id="917a7-129">**요소**</span><span class="sxs-lookup"><span data-stu-id="917a7-129">**Element**</span></span>|<span data-ttu-id="917a7-130">**설명**</span><span class="sxs-lookup"><span data-stu-id="917a7-130">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="917a7-131">구성</span><span class="sxs-lookup"><span data-stu-id="917a7-131">configuration</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="917a7-132">모든 네임 스페이스에 대 한 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="917a7-132">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="917a7-133">설명</span><span class="sxs-lookup"><span data-stu-id="917a7-133">Remarks</span></span>  
 <span data-ttu-id="917a7-134">[ \<system.net >](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md) 요소 클래스에 대 한 설정이 포함 되어는 <xref:System.Net> 및 관련 자식 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="917a7-134">The [\<system.net>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md) element contains settings for classes in the <xref:System.Net> and related child namespaces.</span></span> <span data-ttu-id="917a7-135">설정을 인증 모듈, 연결 관리, 메일 설정, 프록시 서버 및 인터넷 호스트에서 정보를 받는 데 인터넷 요청 모듈을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="917a7-135">The settings configure authentication modules, connection management, mail settings, the proxy server, and Internet request modules for receiving information from Internet hosts.</span></span>  
  
## <a name="example"></a><span data-ttu-id="917a7-136">예제</span><span class="sxs-lookup"><span data-stu-id="917a7-136">Example</span></span>  
 <span data-ttu-id="917a7-137">다음 예제에서 사용 하는 일반적인 구성에서는 <xref:System.Net> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="917a7-137">The following example shows a typical configuration used by <xref:System.Net> classes.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <add type="System.Net.DigestClient" />  
      <add type="System.Net.NegotiateClient" />  
      <add type="System.Net.KerberosClient" />  
      <add type="System.Net.NtlmClient" />  
      <add type="System.Net.BasicClient" />  
    </authenticationModules>  
    <connectionManagement>  
      <add address="*" maxconnection="2" />  
    </connectionManagement>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="true"  
        bypassonlocal="true"  
      />  
    </defaultProxy>  
    <webRequestModules>  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator"  
      />  
      <add prefix="https"  
           type="System.Net.HttpRequestCreator"  
      />  
      <add prefix="file"  
           type="System.Net.FileWebRequestCreator"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="917a7-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="917a7-138">See Also</span></span>  
 [<span data-ttu-id="917a7-139">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="917a7-139">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
