---
title: "&lt;webProxyScript&gt; 요소 (네트워크 설정)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#webProxyScript
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/webProxyScript
helpviewer_keywords:
- <webProxyScript> element
- webProxyScript element
ms.assetid: a13c26db-6218-4af3-9696-38f24b23bfac
caps.latest.revision: "9"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: d1258301af903ef5c36df854c7c6dd504d6eef15
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltwebproxyscriptgt-element-network-settings"></a><span data-ttu-id="c0243-102">&lt;webProxyScript&gt; 요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="c0243-102">&lt;webProxyScript&gt; Element (Network Settings)</span></span>
<span data-ttu-id="c0243-103">웹 프록시 검색에 사용 되는 스크립트의 특성을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0243-103">Configures the characteristics of the script used to discover Web proxies.</span></span>  
  
 <span data-ttu-id="c0243-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="c0243-104">\<configuration></span></span>  
<span data-ttu-id="c0243-105">\<system.net ></span><span class="sxs-lookup"><span data-stu-id="c0243-105">\<system.net></span></span>  
<span data-ttu-id="c0243-106">\<설정 ></span><span class="sxs-lookup"><span data-stu-id="c0243-106">\<settings></span></span>  
<span data-ttu-id="c0243-107">\<webProxyScript ></span><span class="sxs-lookup"><span data-stu-id="c0243-107">\<webProxyScript></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0243-108">구문</span><span class="sxs-lookup"><span data-stu-id="c0243-108">Syntax</span></span>  
  
```xml  
<webProxyScript  
  downloadTimeout="hh:mm:ss"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c0243-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c0243-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c0243-110">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c0243-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c0243-111">특성</span><span class="sxs-lookup"><span data-stu-id="c0243-111">Attributes</span></span>  
  
|<span data-ttu-id="c0243-112">특성</span><span class="sxs-lookup"><span data-stu-id="c0243-112">Attribute</span></span>|<span data-ttu-id="c0243-113">설명</span><span class="sxs-lookup"><span data-stu-id="c0243-113">Description</span></span>|  
|---------------|-----------------|  
|`downloadTimeout`|<span data-ttu-id="c0243-114">시, 분 및 초에서 스크립트를 다운로드 하는 최대 시간을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0243-114">Specifies the maximum time to download the script in hours, minutes, and seconds.</span></span> <span data-ttu-id="c0243-115">기본값은 1 분입니다.</span><span class="sxs-lookup"><span data-stu-id="c0243-115">The default value is one minute.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c0243-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c0243-116">Child Elements</span></span>  
 <span data-ttu-id="c0243-117">없음</span><span class="sxs-lookup"><span data-stu-id="c0243-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c0243-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c0243-118">Parent Elements</span></span>  
  
|<span data-ttu-id="c0243-119">요소</span><span class="sxs-lookup"><span data-stu-id="c0243-119">Element</span></span>|<span data-ttu-id="c0243-120">설명</span><span class="sxs-lookup"><span data-stu-id="c0243-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c0243-121">설정</span><span class="sxs-lookup"><span data-stu-id="c0243-121">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="c0243-122"><xref:System.Net> 네임스페이스에 대한 기본 네트워크 옵션을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="c0243-122">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c0243-123">설명</span><span class="sxs-lookup"><span data-stu-id="c0243-123">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="c0243-124">구성 파일</span><span class="sxs-lookup"><span data-stu-id="c0243-124">Configuration Files</span></span>  
 <span data-ttu-id="c0243-125">이 요소는 응용 프로그램 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0243-125">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0243-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c0243-126">See Also</span></span>  
 [<span data-ttu-id="c0243-127">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="c0243-127">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
