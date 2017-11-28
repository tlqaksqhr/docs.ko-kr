---
title: "&lt;추가&gt; schemeSettings (Uri 설정)에 대 한 요소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 594a7b3b-af23-4cfa-b616-0b2dddb1a705
caps.latest.revision: "7"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 8ce4cc33d054e74fc9868a16764e744daf260c10
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltaddgt-element-for-schemesettings-uri-settings"></a><span data-ttu-id="796a7-102">&lt;추가&gt; schemeSettings (Uri 설정)에 대 한 요소</span><span class="sxs-lookup"><span data-stu-id="796a7-102">&lt;add&gt; Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="796a7-103">체계 이름에 대 한 스키마 설정을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="796a7-103">Adds a scheme setting for a scheme name.</span></span>  
  
 <span data-ttu-id="796a7-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="796a7-104">\<configuration></span></span>  
<span data-ttu-id="796a7-105">\<uri ></span><span class="sxs-lookup"><span data-stu-id="796a7-105">\<uri></span></span>  
<span data-ttu-id="796a7-106">\<schemeSettings ></span><span class="sxs-lookup"><span data-stu-id="796a7-106">\<schemeSettings></span></span>  
<span data-ttu-id="796a7-107">\<add></span><span class="sxs-lookup"><span data-stu-id="796a7-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="796a7-108">구문</span><span class="sxs-lookup"><span data-stu-id="796a7-108">Syntax</span></span>  
  
```xml  
<add
  name="http|https"
  genericUriParserOptions="DontUnescapePathDotsAndSlashes"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="796a7-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="796a7-109">Attributes and Elements</span></span>  
 <span data-ttu-id="796a7-110">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="796a7-110">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="796a7-111">특성</span><span class="sxs-lookup"><span data-stu-id="796a7-111">Attributes</span></span>  
  
|<span data-ttu-id="796a7-112">특성</span><span class="sxs-lookup"><span data-stu-id="796a7-112">Attribute</span></span>|<span data-ttu-id="796a7-113">설명</span><span class="sxs-lookup"><span data-stu-id="796a7-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="796a7-114">name</span><span class="sxs-lookup"><span data-stu-id="796a7-114">name</span></span>|<span data-ttu-id="796a7-115">이 설정은 적용 되는 체계 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="796a7-115">The scheme name for which this setting applies.</span></span> <span data-ttu-id="796a7-116">이름에 지원 되는 값만 = "http" 및 name = "https"입니다.</span><span class="sxs-lookup"><span data-stu-id="796a7-116">The only supported values are name="http" and name="https".</span></span>|  
  
## <a name="attribute-name-attribute"></a><span data-ttu-id="796a7-117">{특성 name} 특성</span><span class="sxs-lookup"><span data-stu-id="796a7-117">{Attribute name} Attribute</span></span>  
  
|<span data-ttu-id="796a7-118">값</span><span class="sxs-lookup"><span data-stu-id="796a7-118">Value</span></span>|<span data-ttu-id="796a7-119">설명</span><span class="sxs-lookup"><span data-stu-id="796a7-119">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="796a7-120">genericUriParserOptions</span><span class="sxs-lookup"><span data-stu-id="796a7-120">genericUriParserOptions</span></span>|<span data-ttu-id="796a7-121">이 스키마에 대 한 파서 옵션을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="796a7-121">The parser options for this scheme.</span></span> <span data-ttu-id="796a7-122">지원 되는 값은 genericUriParserOptions = "DontUnescapePathDotsAndSlashes"입니다.</span><span class="sxs-lookup"><span data-stu-id="796a7-122">The only supported value is genericUriParserOptions= "DontUnescapePathDotsAndSlashes".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="796a7-123">자식 요소</span><span class="sxs-lookup"><span data-stu-id="796a7-123">Child Elements</span></span>  
 <span data-ttu-id="796a7-124">없음</span><span class="sxs-lookup"><span data-stu-id="796a7-124">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="796a7-125">부모 요소</span><span class="sxs-lookup"><span data-stu-id="796a7-125">Parent Elements</span></span>  
  
|<span data-ttu-id="796a7-126">요소</span><span class="sxs-lookup"><span data-stu-id="796a7-126">Element</span></span>|<span data-ttu-id="796a7-127">설명</span><span class="sxs-lookup"><span data-stu-id="796a7-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="796a7-128">\<schemeSettings> 요소 (URI 설정)</span><span class="sxs-lookup"><span data-stu-id="796a7-128">\<schemeSettings> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|<span data-ttu-id="796a7-129">특정 체계에 대해 <xref:System.Uri>가 구문 분석되는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="796a7-129">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="796a7-130">설명</span><span class="sxs-lookup"><span data-stu-id="796a7-130">Remarks</span></span>  
 <span data-ttu-id="796a7-131">기본적으로는 <xref:System.Uri?displayProperty=nameWithType> 클래스 이스케이프 해제 % 인코딩된 경로 압축을 실행 하기 전에 경로 구분 기호입니다.</span><span class="sxs-lookup"><span data-stu-id="796a7-131">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="796a7-132">다음과 같은 공격에 대 한 보안 메커니즘으로 구현 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="796a7-132">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="796a7-133">이 URI에서 전달 되 모듈 %를 처리 하지 않는 인코딩된 문자를 올바르게 이벤트를 서버에서 실행 되 고 다음 명령이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="796a7-133">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="796a7-134">이러한 이유로 <xref:System.Uri?displayProperty=nameWithType> 클래스가 먼저 이스케이프 해제 경로 구분 기호 및 경로 압축을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="796a7-134">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="796a7-135">위의 악성 URL을 전달 하는 결과 <xref:System.Uri?displayProperty=nameWithType> 클래스 생성자에 다음 URI:</span><span class="sxs-lookup"><span data-stu-id="796a7-135">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="796a7-136">이 기본 동작 schemeSettings 구성 옵션을 사용 하 여 특정 구성표에 대 한 이스케이프 해제 백분율 인코딩된 경로 구분 되지를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="796a7-136">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="796a7-137">구성 파일</span><span class="sxs-lookup"><span data-stu-id="796a7-137">Configuration Files</span></span>  
 <span data-ttu-id="796a7-138">이 요소는 응용 프로그램 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="796a7-138">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="796a7-139">예제</span><span class="sxs-lookup"><span data-stu-id="796a7-139">Example</span></span>  
 <span data-ttu-id="796a7-140">다음 예제에서 사용 되는 구성을 <xref:System.Uri> http 체계에 대 한 퍼센트 인코딩 경로 구분 기호를 이스케이프 하지 않아도 되도록 지원 하기 위해 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="796a7-140">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="796a7-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="796a7-141">See Also</span></span>  
 <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>  
 <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>  
 <xref:System.GenericUriParserOptions?displayProperty=nameWithType>  
 <xref:System.Uri?displayProperty=nameWithType>  
 [<span data-ttu-id="796a7-142">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="796a7-142">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
