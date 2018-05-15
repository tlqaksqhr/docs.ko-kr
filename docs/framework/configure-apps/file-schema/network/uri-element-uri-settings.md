---
title: '&lt;Uri&gt; 요소 (Uri 설정)'
ms.date: 03/30/2017
ms.assetid: c22bab8b-477c-4ae4-8498-65ad409e0847
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 05b2fb4255643f657f37012ec51a1b29ed68095d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="lturigt-element-uri-settings"></a><span data-ttu-id="c0f93-102">&lt;Uri&gt; 요소 (Uri 설정)</span><span class="sxs-lookup"><span data-stu-id="c0f93-102">&lt;Uri&gt; Element (Uri Settings)</span></span>
<span data-ttu-id="c0f93-103">.NET Framework 웹 주소 (Uri) uniform resource identifier를 사용 하 여 표시를 처리 하는 방법을 지정 하는 설정을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0f93-103">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>  
  
## <a name="schema-hierarchy"></a><span data-ttu-id="c0f93-104">스키마 계층 구조</span><span class="sxs-lookup"><span data-stu-id="c0f93-104">Schema Hierarchy</span></span>  
 [<span data-ttu-id="c0f93-105">\<configuration> 요소</span><span class="sxs-lookup"><span data-stu-id="c0f93-105">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [<span data-ttu-id="c0f93-106">\<uri ></span><span class="sxs-lookup"><span data-stu-id="c0f93-106">\<uri></span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)  
  
## <a name="syntax"></a><span data-ttu-id="c0f93-107">구문</span><span class="sxs-lookup"><span data-stu-id="c0f93-107">Syntax</span></span>  
  
```xml  
<uri>  
</uri>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c0f93-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c0f93-108">Attributes and Elements</span></span>  
 <span data-ttu-id="c0f93-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c0f93-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c0f93-110">특성</span><span class="sxs-lookup"><span data-stu-id="c0f93-110">Attributes</span></span>  
 <span data-ttu-id="c0f93-111">없음</span><span class="sxs-lookup"><span data-stu-id="c0f93-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c0f93-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c0f93-112">Child Elements</span></span>  
  
|<span data-ttu-id="c0f93-113">**요소**</span><span class="sxs-lookup"><span data-stu-id="c0f93-113">**Element**</span></span>|<span data-ttu-id="c0f93-114">**설명**</span><span class="sxs-lookup"><span data-stu-id="c0f93-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="c0f93-115">idn</span><span class="sxs-lookup"><span data-stu-id="c0f93-115">idn</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/idn-element-uri-settings.md)|<span data-ttu-id="c0f93-116">IDN(Internationalized Domain Name) 구문 분석이 도메인 이름에 적용되는지 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c0f93-116">Specifies if Internationalized Domain Name (IDN) parsing is applied to domain names.</span></span>|  
|[<span data-ttu-id="c0f93-117">iriParsing</span><span class="sxs-lookup"><span data-stu-id="c0f93-117">iriParsing</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/iriparsing-element-uri-settings.md)|<span data-ttu-id="c0f93-118">리소스 IRI (International Identifier) 구문 분석에 적용 됩니다 지정 <xref:System.Uri> IRI 구문 분석 규칙을 적용 해야 하는지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="c0f93-118">Specifies if International Resource Identifier (IRI) parsing is applied to <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>|  
|[<span data-ttu-id="c0f93-119">schemeSettings</span><span class="sxs-lookup"><span data-stu-id="c0f93-119">schemeSettings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|<span data-ttu-id="c0f93-120">특정 체계에 대해 <xref:System.Uri>가 구문 분석되는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c0f93-120">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c0f93-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c0f93-121">Parent Elements</span></span>  
  
|<span data-ttu-id="c0f93-122">**요소**</span><span class="sxs-lookup"><span data-stu-id="c0f93-122">**Element**</span></span>|<span data-ttu-id="c0f93-123">**설명**</span><span class="sxs-lookup"><span data-stu-id="c0f93-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="c0f93-124">구성</span><span class="sxs-lookup"><span data-stu-id="c0f93-124">configuration</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="c0f93-125">모든 네임 스페이스에 대 한 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="c0f93-125">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c0f93-126">설명</span><span class="sxs-lookup"><span data-stu-id="c0f93-126">Remarks</span></span>  
 <span data-ttu-id="c0f93-127">`uri` 요소의 멤버에 대 한 설정이 포함 되어는 <xref:System.Uri> 클래스에 의해 사용 되는 클래스는 <xref:System.Net> 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="c0f93-127">The `uri` element contains settings for members of the <xref:System.Uri> class used by classes in the <xref:System.Net> namespace.</span></span> <span data-ttu-id="c0f93-128">이 설정은 IRI 및 IDN에 대 한 지원을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0f93-128">The settings configure support for IRI and IDN.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c0f93-129">예제</span><span class="sxs-lookup"><span data-stu-id="c0f93-129">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="c0f93-130">설명</span><span class="sxs-lookup"><span data-stu-id="c0f93-130">Description</span></span>  
 <span data-ttu-id="c0f93-131">다음 예제에서 사용 되는 구성을 <xref:System.Uri> IRI 구문 분석 및 IDN 이름을 지원 하기 위해 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="c0f93-131">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span> <span data-ttu-id="c0f93-132">이 예제에서는 또한 모든 스키마 설정을 지우고 http 체계에 대 한 퍼센트 인코딩 경로 구분 기호를 이스케이프 하지 않아도 되도록 하는 것에 대 한 지원을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0f93-132">The example also clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
### <a name="code"></a><span data-ttu-id="c0f93-133">코드</span><span class="sxs-lookup"><span data-stu-id="c0f93-133">Code</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
    <schemeSettings>  
      <clear/>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c0f93-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c0f93-134">See Also</span></span>  
 [<span data-ttu-id="c0f93-135">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="c0f93-135">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
