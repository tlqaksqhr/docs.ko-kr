---
title: "&lt;제거&gt; webRequestModules (네트워크 설정)에 대 한 요소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- remove element, webRequestModules
- webRequestModules, remove element
- <remove> element, webRequestModules
- <webRequestModules>, remove element
ms.assetid: dd84d2fe-2f4f-457a-9d3c-441d0d21cc10
caps.latest.revision: "13"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 391e5f2a7d9d8076ba9e9a3057e3d8899e2ce672
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltremovegt-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="cf050-102">&lt;제거&gt; webRequestModules (네트워크 설정)에 대 한 요소</span><span class="sxs-lookup"><span data-stu-id="cf050-102">&lt;remove&gt; Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="cf050-103">응용 프로그램에서 사용자 지정 웹 요청 모듈을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="cf050-103">Removes a custom Web request module from the application.</span></span>  
  
 <span data-ttu-id="cf050-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="cf050-104">\<configuration></span></span>  
<span data-ttu-id="cf050-105">\<system.net ></span><span class="sxs-lookup"><span data-stu-id="cf050-105">\<system.net></span></span>  
<span data-ttu-id="cf050-106">\<webRequestModules ></span><span class="sxs-lookup"><span data-stu-id="cf050-106">\<webRequestModules></span></span>  
<span data-ttu-id="cf050-107">\<제거 ></span><span class="sxs-lookup"><span data-stu-id="cf050-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf050-108">구문</span><span class="sxs-lookup"><span data-stu-id="cf050-108">Syntax</span></span>  
  
```xml  
<remove   
  prefix="URI prefix"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cf050-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="cf050-109">Attributes and Elements</span></span>  
 <span data-ttu-id="cf050-110">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cf050-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cf050-111">특성</span><span class="sxs-lookup"><span data-stu-id="cf050-111">Attributes</span></span>  
  
|<span data-ttu-id="cf050-112">**특성**</span><span class="sxs-lookup"><span data-stu-id="cf050-112">**Attribute**</span></span>|<span data-ttu-id="cf050-113">**설명**</span><span class="sxs-lookup"><span data-stu-id="cf050-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`prefix`|<span data-ttu-id="cf050-114">이 웹 요청 모듈에서 처리 요청에 대 한 URI 접두사입니다.</span><span class="sxs-lookup"><span data-stu-id="cf050-114">The URI prefix for requests handled by this Web request module.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cf050-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="cf050-115">Child Elements</span></span>  
 <span data-ttu-id="cf050-116">없음</span><span class="sxs-lookup"><span data-stu-id="cf050-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cf050-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="cf050-117">Parent Elements</span></span>  
  
|<span data-ttu-id="cf050-118">**요소**</span><span class="sxs-lookup"><span data-stu-id="cf050-118">**Element**</span></span>|<span data-ttu-id="cf050-119">**설명**</span><span class="sxs-lookup"><span data-stu-id="cf050-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="cf050-120">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="cf050-120">webRequestModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|<span data-ttu-id="cf050-121">네트워크 호스트에서 정보를 요청 하는 데는 모듈을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf050-121">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cf050-122">설명</span><span class="sxs-lookup"><span data-stu-id="cf050-122">Remarks</span></span>  
 <span data-ttu-id="cf050-123">`remove` 요소에 지정된 된 URI 접두사에 대 한 등록된 웹 요청 모듈 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf050-123">The `remove` element removes the registered Web request module for the specified URI prefix.</span></span>  
  
 <span data-ttu-id="cf050-124">에 대 한 값은 `prefix` 특성의 예: "http" 또는 "http://www.contoso.com"는 유효한 URI-선행 문자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf050-124">The value for the `prefix` attribute should be the leading characters of a valid URI -- for example, "http", or "http://www.contoso.com".</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="cf050-125">구성 파일</span><span class="sxs-lookup"><span data-stu-id="cf050-125">Configuration Files</span></span>  
 <span data-ttu-id="cf050-126">이 요소는 응용 프로그램 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf050-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cf050-127">예</span><span class="sxs-lookup"><span data-stu-id="cf050-127">Example</span></span>  
 <span data-ttu-id="cf050-128">다음 예제에서는 HTTP에 대 한 기존 웹 요청 모듈을 제거 하 고 만든 다음 www.contoso.com에 대 한 HTTP 요청에 대 한 새 사용자 지정 웹 요청 모듈을 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf050-128">The following example removes the existing Web request module for HTTP and then registers a new custom Web request module for HTTP requests to www.contoso.com.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <remove prefix="http">  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator, System, Version=2.0.3600.0,  
           Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cf050-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cf050-129">See Also</span></span>  
 <xref:System.Net.WebRequest>  
 [<span data-ttu-id="cf050-130">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="cf050-130">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
