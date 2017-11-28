---
title: "&lt;제거&gt; bypasslist (네트워크 설정)에 대 한 요소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- <bypasslist>, remove element
- remove elemment, bypasslist
- bypasslist, remove element
- remove element, bypasslist
ms.assetid: 61dcfb4a-e3d9-4abf-a2cd-7d685fe2f64b
caps.latest.revision: "16"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: a87632ec9725aa24d085ca6c1bf1e54545b324fd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltremovegt-element-for-bypasslist-network-settings"></a><span data-ttu-id="1c628-102">&lt;제거&gt; bypasslist (네트워크 설정)에 대 한 요소</span><span class="sxs-lookup"><span data-stu-id="1c628-102">&lt;remove&gt; Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="1c628-103">프록시 무시 목록에서 IP 주소 또는 DNS 이름을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="1c628-103">Removes an IP address or DNS name from the proxy bypass list.</span></span>  
  
 <span data-ttu-id="1c628-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="1c628-104">\<configuration></span></span>  
<span data-ttu-id="1c628-105">\<system.net ></span><span class="sxs-lookup"><span data-stu-id="1c628-105">\<system.net></span></span>  
<span data-ttu-id="1c628-106">\<defaultProxy ></span><span class="sxs-lookup"><span data-stu-id="1c628-106">\<defaultProxy></span></span>  
<span data-ttu-id="1c628-107">\<bypasslist ></span><span class="sxs-lookup"><span data-stu-id="1c628-107">\<bypasslist></span></span>  
<span data-ttu-id="1c628-108">\<제거 ></span><span class="sxs-lookup"><span data-stu-id="1c628-108">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c628-109">구문</span><span class="sxs-lookup"><span data-stu-id="1c628-109">Syntax</span></span>  
  
```xml  
<remove   
  address="regular expression"   
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1c628-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="1c628-110">Attributes and Elements</span></span>  
 <span data-ttu-id="1c628-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1c628-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1c628-112">특성</span><span class="sxs-lookup"><span data-stu-id="1c628-112">Attributes</span></span>  
  
|<span data-ttu-id="1c628-113">**특성**</span><span class="sxs-lookup"><span data-stu-id="1c628-113">**Attribute**</span></span>|<span data-ttu-id="1c628-114">**설명**</span><span class="sxs-lookup"><span data-stu-id="1c628-114">**Description**</span></span>|  
|-------------------|---------------------|  
|`address`|<span data-ttu-id="1c628-115">IP 주소 또는 DNS 이름을 설명 하는 정규식입니다.</span><span class="sxs-lookup"><span data-stu-id="1c628-115">A regular expression describing an IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1c628-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="1c628-116">Child Elements</span></span>  
 <span data-ttu-id="1c628-117">없음</span><span class="sxs-lookup"><span data-stu-id="1c628-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1c628-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="1c628-118">Parent Elements</span></span>  
  
|<span data-ttu-id="1c628-119">**요소**</span><span class="sxs-lookup"><span data-stu-id="1c628-119">**Element**</span></span>|<span data-ttu-id="1c628-120">**설명**</span><span class="sxs-lookup"><span data-stu-id="1c628-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="1c628-121">bypasslist</span><span class="sxs-lookup"><span data-stu-id="1c628-121">bypasslist</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|<span data-ttu-id="1c628-122">프록시를 사용 하지 않는 주소를 설명 하는 정규식 집합을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c628-122">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1c628-123">설명</span><span class="sxs-lookup"><span data-stu-id="1c628-123">Remarks</span></span>  
 <span data-ttu-id="1c628-124">`remove` 요소 IP 주소 또는 DNS 서버 이름을 프록시 서버를 사용 하지 않는 주소 목록에서 설명 하는 정규식을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c628-124">The `remove` element removes regular expressions describing IP addresses or DNS server names from the list of addresses that bypass a proxy server.</span></span> <span data-ttu-id="1c628-125">구성 파일 또는 구성 계층 구조의 상위 수준에서 주소 이전 정의 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1c628-125">The addresses were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
 <span data-ttu-id="1c628-126">에 대 한 값의 `address` 특성 IP 주소 또는 호스트 이름 집합을 설명 하는 정규식을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c628-126">The value for the `address` attribute should be a regular expression that describes a set of IP addresses or host names.</span></span>  
  
 <span data-ttu-id="1c628-127">정규식에 대 한 자세한 내용은 다음을 참조 합니다. [.NET framework 정규식](../../../../../docs/standard/base-types/regular-expressions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1c628-127">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../../docs/standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="1c628-128">구성 파일</span><span class="sxs-lookup"><span data-stu-id="1c628-128">Configuration Files</span></span>  
 <span data-ttu-id="1c628-129">이 요소는 응용 프로그램 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c628-129">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1c628-130">예제</span><span class="sxs-lookup"><span data-stu-id="1c628-130">Example</span></span>  
 <span data-ttu-id="1c628-131">다음 예제에서는 adventure-works.com 도메인에 대 한 이전 정의 제거 하 고 무시 목록을 contoso.com 도메인에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c628-131">The following example removes any previous definition for the adventure-works.com domain, and then adds the contoso.com domain to the bypass list.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <bypasslist>  
        <remove address="[a-z]+\.adventure-works\.com$" />  
        <add address="[a-z]+\.contoso\.com$" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1c628-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1c628-132">See Also</span></span>  
 <xref:System.Net.WebProxy?displayProperty=nameWithType>  
 [<span data-ttu-id="1c628-133">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="1c628-133">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
