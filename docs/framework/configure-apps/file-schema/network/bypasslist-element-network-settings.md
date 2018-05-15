---
title: '&lt;bypasslist&gt; 요소 (네트워크 설정)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#bypasslist
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist
helpviewer_keywords:
- bypasslist element
- <bypasslist> element
ms.assetid: 124446b7-abb1-4e5e-a492-b64398f268f1
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 2d2076ee5e95ab722fe828ee625392671a6281c1
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltbypasslistgt-element-network-settings"></a><span data-ttu-id="33321-102">&lt;bypasslist&gt; 요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="33321-102">&lt;bypasslist&gt; Element (Network Settings)</span></span>
<span data-ttu-id="33321-103">프록시를 사용 하지 않는 주소를 설명 하는 정규식 집합을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="33321-103">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>  
  
 <span data-ttu-id="33321-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="33321-104">\<configuration></span></span>  
<span data-ttu-id="33321-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="33321-105">\<system.net></span></span>  
<span data-ttu-id="33321-106">\<defaultProxy ></span><span class="sxs-lookup"><span data-stu-id="33321-106">\<defaultProxy></span></span>  
<span data-ttu-id="33321-107">\<bypasslist ></span><span class="sxs-lookup"><span data-stu-id="33321-107">\<bypasslist></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33321-108">구문</span><span class="sxs-lookup"><span data-stu-id="33321-108">Syntax</span></span>  
  
```xml  
<bypasslist>   
</bypasslist>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="33321-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="33321-109">Attributes and Elements</span></span>  
 <span data-ttu-id="33321-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="33321-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="33321-111">특성</span><span class="sxs-lookup"><span data-stu-id="33321-111">Attributes</span></span>  
 <span data-ttu-id="33321-112">없음</span><span class="sxs-lookup"><span data-stu-id="33321-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="33321-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="33321-113">Child Elements</span></span>  
  
|<span data-ttu-id="33321-114">**요소**</span><span class="sxs-lookup"><span data-stu-id="33321-114">**Element**</span></span>|<span data-ttu-id="33321-115">**설명**</span><span class="sxs-lookup"><span data-stu-id="33321-115">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="33321-116">add</span><span class="sxs-lookup"><span data-stu-id="33321-116">add</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-bypasslist-network-settings.md)|<span data-ttu-id="33321-117">프록시 무시 목록에 IP 주소 또는 DNS 이름을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="33321-117">Adds an IP address or DNS name to the proxy bypass list.</span></span>|  
|[<span data-ttu-id="33321-118">clear</span><span class="sxs-lookup"><span data-stu-id="33321-118">clear</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-bypasslist-network-settings.md)|<span data-ttu-id="33321-119">무시 목록을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="33321-119">Clears the bypass list.</span></span>|  
|[<span data-ttu-id="33321-120">remove</span><span class="sxs-lookup"><span data-stu-id="33321-120">remove</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-bypasslist-network-settings.md)|<span data-ttu-id="33321-121">프록시 무시 목록에서 IP 주소 또는 DNS 이름을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="33321-121">Removes an IP address or DNS name from the proxy bypass list.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="33321-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="33321-122">Parent Elements</span></span>  
  
|<span data-ttu-id="33321-123">**요소**</span><span class="sxs-lookup"><span data-stu-id="33321-123">**Element**</span></span>|<span data-ttu-id="33321-124">**설명**</span><span class="sxs-lookup"><span data-stu-id="33321-124">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="33321-125">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="33321-125">defaultProxy</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|<span data-ttu-id="33321-126">HTTP(Hypertext Transfer Protocol) 프록시 서버를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="33321-126">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="33321-127">설명</span><span class="sxs-lookup"><span data-stu-id="33321-127">Remarks</span></span>  
 <span data-ttu-id="33321-128">무시 목록 Uri를 설명 하는 정규식을 포함 하는 <xref:System.Net.WebRequest> 인스턴스에서 직접 대신의 프록시 서버를 통해 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="33321-128">The bypass list contains regular expressions that describe URIs that <xref:System.Net.WebRequest> instances access directly instead of through the proxy server.</span></span>  
  
 <span data-ttu-id="33321-129">이 요소에 대 한 정규식을 지정 하는 경우 주의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="33321-129">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="33321-130">정규식 "[a-z] +\\.contoso\\.com" contoso.com 도메인에 호스트 된 일치 항목에도 모든 호스트 contoso.com.cpandl.com 도메인에 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="33321-130">The regular expression "[a-z]+\\.contoso\\.com" matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="33321-131">Contoso.com 도메인의 호스트에만 일치 하는 앵커 ("$")를 사용 하 여: "[a-z] +\\.contoso\\.com$"입니다.</span><span class="sxs-lookup"><span data-stu-id="33321-131">To match only a host in the contoso.com domain, use an anchor ("$"): "[a-z]+\\.contoso\\.com$".</span></span>  
  
 <span data-ttu-id="33321-132">정규식에 대 한 자세한 내용은 다음을 참조 합니다. [.NET framework 정규식](../../../../../docs/standard/base-types/regular-expressions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="33321-132">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../../docs/standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="33321-133">구성 파일</span><span class="sxs-lookup"><span data-stu-id="33321-133">Configuration Files</span></span>  
 <span data-ttu-id="33321-134">이 요소는 응용 프로그램 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33321-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="33321-135">예제</span><span class="sxs-lookup"><span data-stu-id="33321-135">Example</span></span>  
 <span data-ttu-id="33321-136">다음 예제에서는 무시 목록에 두 개의 주소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="33321-136">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="33321-137">첫 번째; contoso.com 도메인의 모든 서버에 대 한 프록시를 무시합니다. 두 번째 192.168로 시작 하는 IP 주소가 속해 있는 모든 서버에 대 한 프록시를 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="33321-137">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP addresses begin with 192.168.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <bypasslist>  
        <add address="[a-z]+\.contoso\.com$" />  
        <add address="192\.168\.\d{1,3}\.\d{1,3}" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="33321-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="33321-138">See Also</span></span>  
 <xref:System.Net.WebProxy?displayProperty=nameWithType>  
 [<span data-ttu-id="33321-139">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="33321-139">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
