---
title: "&lt;지우기&gt; bypasslist (네트워크 설정)에 대 한 요소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/clear
- http://schemas.microsoft.com/.NetConfiguration/v2.0#clear
helpviewer_keywords:
- clear element, bypasslist
- <clear> element, bypasslist
- <bypasslist>, clear element
- bypasslist, clear element
ms.assetid: 301584ca-a914-4100-b180-3b288d3b099e
caps.latest.revision: "14"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 620197065a8e689997b4081b3d90169aa0e3c6c3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltcleargt-element-for-bypasslist-network-settings"></a><span data-ttu-id="73006-102">&lt;지우기&gt; bypasslist (네트워크 설정)에 대 한 요소</span><span class="sxs-lookup"><span data-stu-id="73006-102">&lt;clear&gt; Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="73006-103">프록시 무시 목록을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="73006-103">Clears the proxy bypass list.</span></span>  
  
 <span data-ttu-id="73006-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="73006-104">\<configuration></span></span>  
<span data-ttu-id="73006-105">\<system.net ></span><span class="sxs-lookup"><span data-stu-id="73006-105">\<system.net></span></span>  
<span data-ttu-id="73006-106">\<defaultProxy ></span><span class="sxs-lookup"><span data-stu-id="73006-106">\<defaultProxy></span></span>  
<span data-ttu-id="73006-107">\<bypasslist ></span><span class="sxs-lookup"><span data-stu-id="73006-107">\<bypasslist></span></span>  
<span data-ttu-id="73006-108">\<지우기 ></span><span class="sxs-lookup"><span data-stu-id="73006-108">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73006-109">구문</span><span class="sxs-lookup"><span data-stu-id="73006-109">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="73006-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="73006-110">Attributes and Elements</span></span>  
 <span data-ttu-id="73006-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="73006-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="73006-112">특성</span><span class="sxs-lookup"><span data-stu-id="73006-112">Attributes</span></span>  
 <span data-ttu-id="73006-113">없음</span><span class="sxs-lookup"><span data-stu-id="73006-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="73006-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="73006-114">Child Elements</span></span>  
 <span data-ttu-id="73006-115">없음</span><span class="sxs-lookup"><span data-stu-id="73006-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="73006-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="73006-116">Parent Elements</span></span>  
  
|<span data-ttu-id="73006-117">**요소**</span><span class="sxs-lookup"><span data-stu-id="73006-117">**Element**</span></span>|<span data-ttu-id="73006-118">**설명**</span><span class="sxs-lookup"><span data-stu-id="73006-118">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="73006-119">bypasslist</span><span class="sxs-lookup"><span data-stu-id="73006-119">bypasslist</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|<span data-ttu-id="73006-120">프록시를 사용 하지 않는 주소를 설명 하는 정규식 집합을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="73006-120">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="73006-121">설명</span><span class="sxs-lookup"><span data-stu-id="73006-121">Remarks</span></span>  
 <span data-ttu-id="73006-122">`clear` 요소 무시 목록에서 모든 항목을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="73006-122">The `clear` element clears all entries from the bypass list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="73006-123">구성 파일</span><span class="sxs-lookup"><span data-stu-id="73006-123">Configuration Files</span></span>  
 <span data-ttu-id="73006-124">이 요소는 응용 프로그램 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73006-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="73006-125">예</span><span class="sxs-lookup"><span data-stu-id="73006-125">Example</span></span>  
 <span data-ttu-id="73006-126">다음 예제에서는 무시 목록 지우고 무시 목록에 두 개의 주소를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="73006-126">The following example clears the bypass list and then adds two addresses to the bypass list.</span></span> <span data-ttu-id="73006-127">첫 번째; contoso.com 도메인의 모든 서버에 대 한 프록시를 무시합니다. 두 번째 192.168로 IP 주소로 시작 되는 모든 서버에 대 한 프록시를 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="73006-127">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP address begins with 192.168.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <bypasslist>  
         <clear/>  
        <add address="[a-z]+\.contoso\.com$" />  
        <add address="192\.168\.\d{1,3}\.\d{1,3}" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>   
```  
  
## <a name="see-also"></a><span data-ttu-id="73006-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="73006-128">See Also</span></span>  
 <xref:System.Net.WebProxy?displayProperty=nameWithType>  
 [<span data-ttu-id="73006-129">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="73006-129">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
