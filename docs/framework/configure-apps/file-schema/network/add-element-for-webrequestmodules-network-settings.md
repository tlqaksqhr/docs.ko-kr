---
title: "&lt;추가&gt; webRequestModules (네트워크 설정)에 대 한 요소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
helpviewer_keywords:
- <webRequestModules>, add element
- webRequestModules, add element
- add element, webRequestModules
- <add> element, webRequestModules
ms.assetid: 47ec4adc-f39f-4bcd-8680-1ec21fd26890
caps.latest.revision: "16"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 9b7d2c0f52ea42fcb98be149ab005cd67c2db46a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="87f0e-102">&lt;추가&gt; webRequestModules (네트워크 설정)에 대 한 요소</span><span class="sxs-lookup"><span data-stu-id="87f0e-102">&lt;add&gt; Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="87f0e-103">응용 프로그램에 사용자 지정 웹 요청 모듈을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="87f0e-103">Adds a custom Web request module to the application.</span></span>  
  
 <span data-ttu-id="87f0e-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="87f0e-104">\<configuration></span></span>  
<span data-ttu-id="87f0e-105">\<system.net ></span><span class="sxs-lookup"><span data-stu-id="87f0e-105">\<system.net></span></span>  
<span data-ttu-id="87f0e-106">\<webRequestModules ></span><span class="sxs-lookup"><span data-stu-id="87f0e-106">\<webRequestModules></span></span>  
<span data-ttu-id="87f0e-107">\<add></span><span class="sxs-lookup"><span data-stu-id="87f0e-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87f0e-108">구문</span><span class="sxs-lookup"><span data-stu-id="87f0e-108">Syntax</span></span>  
  
```xml  
<add   
  prefix="URI prefix"   
  type="type_fullname, assembly_fullname"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="87f0e-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="87f0e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="87f0e-110">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="87f0e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="87f0e-111">특성</span><span class="sxs-lookup"><span data-stu-id="87f0e-111">Attributes</span></span>  
  
|<span data-ttu-id="87f0e-112">**특성**</span><span class="sxs-lookup"><span data-stu-id="87f0e-112">**Attribute**</span></span>|<span data-ttu-id="87f0e-113">**설명**</span><span class="sxs-lookup"><span data-stu-id="87f0e-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`prefix`|<span data-ttu-id="87f0e-114">이 웹 요청 모듈에서 처리 요청에 대 한 URI 접두사입니다.</span><span class="sxs-lookup"><span data-stu-id="87f0e-114">The URI prefix for requests handled by this Web request module.</span></span>|  
|`type`|<span data-ttu-id="87f0e-115">정규화 된 형식 이름 (으로 표시는 <xref:System.Type.FullName%2A> 속성)와 어셈블리 이름 (가리키는 <xref:System.Reflection.Assembly.FullName%2A> 속성)을이 웹 요청 모듈을 구현 하는 쉼표로 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="87f0e-115">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma, that implements this Web request module.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="87f0e-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="87f0e-116">Child Elements</span></span>  
 <span data-ttu-id="87f0e-117">없음</span><span class="sxs-lookup"><span data-stu-id="87f0e-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="87f0e-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="87f0e-118">Parent Elements</span></span>  
  
|<span data-ttu-id="87f0e-119">**요소**</span><span class="sxs-lookup"><span data-stu-id="87f0e-119">**Element**</span></span>|<span data-ttu-id="87f0e-120">**설명**</span><span class="sxs-lookup"><span data-stu-id="87f0e-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="87f0e-121">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="87f0e-121">webRequestModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|<span data-ttu-id="87f0e-122">네트워크 호스트에서 정보를 요청 하는 데는 모듈을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="87f0e-122">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="87f0e-123">설명</span><span class="sxs-lookup"><span data-stu-id="87f0e-123">Remarks</span></span>  
 <span data-ttu-id="87f0e-124">`prefix` 특성 지정 된 웹 요청 모듈을 사용 하는 URI 접두사를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="87f0e-124">The `prefix` attribute defines the URI prefix that uses the specified Web request module.</span></span> <span data-ttu-id="87f0e-125">웹 요청 모듈은 일반적으로 HTTP 또는 FTP와 같은 특정 프로토콜을 처리 하도록 등록 되어 있지만 서버에서 경로 또는 특정 서버에 요청을 처리 하도록 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87f0e-125">Web request modules are typically registered to handle a specific protocol, such as HTTP or FTP, but can be registered to handle a request to a specific server or path on a server.</span></span>  
  
 <span data-ttu-id="87f0e-126">URI 일치 하는 접두사에 전달 되 면 웹 요청 모듈 만들어집니다는 <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> 메서드.</span><span class="sxs-lookup"><span data-stu-id="87f0e-126">The Web request module is created when a URI matching prefix is passed to the <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="87f0e-127">에 대 한 값은 `prefix` 특성의 예: "http" 또는 "http://www.contoso.com"는 유효한 URI-선행 문자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87f0e-127">The value for the `prefix` attribute should be the leading characters of a valid URI --for example, "http", or "http://www.contoso.com".</span></span>  
  
 <span data-ttu-id="87f0e-128">에 대 한 값은 `type` 특성 유효한 형식 이름 및 쉼표로 구분 하 여 해당 어셈블리 이름 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87f0e-128">The value for the `type` attribute should be a valid type name and corresponding assembly name, separated by a comma .</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="87f0e-129">구성 파일</span><span class="sxs-lookup"><span data-stu-id="87f0e-129">Configuration Files</span></span>  
 <span data-ttu-id="87f0e-130">이 요소는 응용 프로그램 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87f0e-130">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="87f0e-131">예</span><span class="sxs-lookup"><span data-stu-id="87f0e-131">Example</span></span>  
 <span data-ttu-id="87f0e-132">다음 예제에서는 HTTP에 대 한 사용자 지정 웹 요청 모듈을 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="87f0e-132">The following example registers a custom Web request module for HTTP.</span></span> <span data-ttu-id="87f0e-133">지정된 된 모듈에 대 한 올바른 값으로 PublicKeyToken 및 버전에 대 한 값 바꿔야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87f0e-133">You should replace the values for Version and PublicKeyToken with the correct values for the specified module.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator, System, Version=2.0.3600.0,  
           Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="87f0e-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="87f0e-134">See Also</span></span>  
 <xref:System.Net.WebRequest>  
 [<span data-ttu-id="87f0e-135">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="87f0e-135">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
