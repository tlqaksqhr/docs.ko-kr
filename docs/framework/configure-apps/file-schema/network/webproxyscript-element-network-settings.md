---
title: '&lt;webProxyScript&gt; 요소 (네트워크 설정)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#webProxyScript
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/webProxyScript
helpviewer_keywords:
- <webProxyScript> element
- webProxyScript element
ms.assetid: a13c26db-6218-4af3-9696-38f24b23bfac
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 6843662b73f6b7d45dd12616f5118569a2d19975
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltwebproxyscriptgt-element-network-settings"></a><span data-ttu-id="6df35-102">&lt;webProxyScript&gt; 요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="6df35-102">&lt;webProxyScript&gt; Element (Network Settings)</span></span>
<span data-ttu-id="6df35-103">웹 프록시 검색에 사용 되는 스크립트의 특성을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="6df35-103">Configures the characteristics of the script used to discover Web proxies.</span></span>  
  
 <span data-ttu-id="6df35-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="6df35-104">\<configuration></span></span>  
<span data-ttu-id="6df35-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="6df35-105">\<system.net></span></span>  
<span data-ttu-id="6df35-106">\<settings></span><span class="sxs-lookup"><span data-stu-id="6df35-106">\<settings></span></span>  
<span data-ttu-id="6df35-107">\<webProxyScript ></span><span class="sxs-lookup"><span data-stu-id="6df35-107">\<webProxyScript></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6df35-108">구문</span><span class="sxs-lookup"><span data-stu-id="6df35-108">Syntax</span></span>  
  
```xml  
<webProxyScript  
  downloadTimeout="hh:mm:ss"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6df35-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="6df35-109">Attributes and Elements</span></span>  
 <span data-ttu-id="6df35-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6df35-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6df35-111">특성</span><span class="sxs-lookup"><span data-stu-id="6df35-111">Attributes</span></span>  
  
|<span data-ttu-id="6df35-112">특성</span><span class="sxs-lookup"><span data-stu-id="6df35-112">Attribute</span></span>|<span data-ttu-id="6df35-113">설명</span><span class="sxs-lookup"><span data-stu-id="6df35-113">Description</span></span>|  
|---------------|-----------------|  
|`downloadTimeout`|<span data-ttu-id="6df35-114">시, 분 및 초에서 스크립트를 다운로드 하는 최대 시간을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6df35-114">Specifies the maximum time to download the script in hours, minutes, and seconds.</span></span> <span data-ttu-id="6df35-115">기본값은 1 분입니다.</span><span class="sxs-lookup"><span data-stu-id="6df35-115">The default value is one minute.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6df35-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="6df35-116">Child Elements</span></span>  
 <span data-ttu-id="6df35-117">없음</span><span class="sxs-lookup"><span data-stu-id="6df35-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6df35-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="6df35-118">Parent Elements</span></span>  
  
|<span data-ttu-id="6df35-119">요소</span><span class="sxs-lookup"><span data-stu-id="6df35-119">Element</span></span>|<span data-ttu-id="6df35-120">설명</span><span class="sxs-lookup"><span data-stu-id="6df35-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6df35-121">settings</span><span class="sxs-lookup"><span data-stu-id="6df35-121">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="6df35-122"><xref:System.Net> 네임스페이스에 대한 기본 네트워크 옵션을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="6df35-122">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6df35-123">설명</span><span class="sxs-lookup"><span data-stu-id="6df35-123">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="6df35-124">구성 파일</span><span class="sxs-lookup"><span data-stu-id="6df35-124">Configuration Files</span></span>  
 <span data-ttu-id="6df35-125">이 요소는 응용 프로그램 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6df35-125">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6df35-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6df35-126">See Also</span></span>  
 [<span data-ttu-id="6df35-127">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="6df35-127">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
