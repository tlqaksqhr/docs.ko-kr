---
title: '&lt;iriParsing&gt; 요소 (Uri 설정)'
ms.date: 03/30/2017
ms.assetid: 953d0b53-445e-41f9-b302-77c4030852ce
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: f05f7e35d69f789d3ebb371689aafbc84004b732
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltiriparsinggt-element-uri-settings"></a><span data-ttu-id="574f3-102">&lt;iriParsing&gt; 요소 (Uri 설정)</span><span class="sxs-lookup"><span data-stu-id="574f3-102">&lt;iriParsing&gt; Element (Uri Settings)</span></span>
<span data-ttu-id="574f3-103">IRI(International Resource Identifier) 구문 분석이 <xref:System.Uri>에 적용되는지와 IRI 구문 분석 규칙을 적용해야 하는지 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="574f3-103">Specifies if International Resource Identifier (IRI) parsing is applied to a <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>  
  
## <a name="schema-hierarchy"></a><span data-ttu-id="574f3-104">스키마 계층 구조</span><span class="sxs-lookup"><span data-stu-id="574f3-104">Schema Hierarchy</span></span>  
 [<span data-ttu-id="574f3-105">\<configuration> 요소</span><span class="sxs-lookup"><span data-stu-id="574f3-105">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [<span data-ttu-id="574f3-106">\<Uri > 요소 (Uri 설정)</span><span class="sxs-lookup"><span data-stu-id="574f3-106">\<Uri> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)  
  
 [<span data-ttu-id="574f3-107">\<iriParsing ></span><span class="sxs-lookup"><span data-stu-id="574f3-107">\<iriParsing></span></span>](../../../../../docs/framework/configure-apps/file-schema/network/iriparsing-element-uri-settings.md)  
  
## <a name="syntax"></a><span data-ttu-id="574f3-108">구문</span><span class="sxs-lookup"><span data-stu-id="574f3-108">Syntax</span></span>  
  
```xml  
<iriParsing  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="574f3-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="574f3-109">Attributes and Elements</span></span>  
 <span data-ttu-id="574f3-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="574f3-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="574f3-111">특성</span><span class="sxs-lookup"><span data-stu-id="574f3-111">Attributes</span></span>  
  
|<span data-ttu-id="574f3-112">**요소**</span><span class="sxs-lookup"><span data-stu-id="574f3-112">**Element**</span></span>|<span data-ttu-id="574f3-113">**설명**</span><span class="sxs-lookup"><span data-stu-id="574f3-113">**Description**</span></span>|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="574f3-114">IRI 구문 분석 사용 되는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="574f3-114">Specifies whether IRI parsing is enabled.</span></span> <span data-ttu-id="574f3-115">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="574f3-115">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="574f3-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="574f3-116">Child Elements</span></span>  
 <span data-ttu-id="574f3-117">없음</span><span class="sxs-lookup"><span data-stu-id="574f3-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="574f3-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="574f3-118">Parent Elements</span></span>  
  
|<span data-ttu-id="574f3-119">**요소**</span><span class="sxs-lookup"><span data-stu-id="574f3-119">**Element**</span></span>|<span data-ttu-id="574f3-120">**설명**</span><span class="sxs-lookup"><span data-stu-id="574f3-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="574f3-121">Uri</span><span class="sxs-lookup"><span data-stu-id="574f3-121">uri</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md)|<span data-ttu-id="574f3-122">.NET Framework 웹 주소 (Uri) uniform resource identifier를 사용 하 여 표시를 처리 하는 방법을 지정 하는 설정을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="574f3-122">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="574f3-123">설명</span><span class="sxs-lookup"><span data-stu-id="574f3-123">Remarks</span></span>  
 <span data-ttu-id="574f3-124">기존 <xref:System.Uri> 클래스는.NET Framework 3.5에서 확장 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="574f3-124">The existing <xref:System.Uri> class has been extended in .NET Framework 3.5.</span></span> <span data-ttu-id="574f3-125">3.0 SP1 및 2.0 s p 1 식별자 IRI (International Resource) 및 이름 IDN (Internationalized Domain)에 대 한 지원을 제공 하기 위해.</span><span class="sxs-lookup"><span data-stu-id="574f3-125">3.0 SP1, and 2.0 SP1 to provide support for International Resource Identifiers (IRI) and Internationalized Domain Names (IDN).</span></span> <span data-ttu-id="574f3-126">IRI 및 IDN 구체적으로 설정 하지 않으면 현재 사용자의.NET Framework 2.0 동작 어떠한 변경도 표시 되지 것입니다 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="574f3-126">Current users will not see any change from the .NET Framework 2.0 behavior unless they specifically enable IRI and IDN support.</span></span> <span data-ttu-id="574f3-127">이 덕분에 .NET Framework 이전 버전과의 응용 프로그램 호환성이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="574f3-127">This ensures application compatibility with prior versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="574f3-128">IRI에 대 한 지원을 설정 하는 다음 두 가지 변경이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="574f3-128">To enable support for IRI, the following two changes are required:</span></span>  
  
1.  <span data-ttu-id="574f3-129">.NET Framework 2.0 디렉터리 아래에 있는 machine.config 파일에 다음 줄을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="574f3-129">Add the following line to the machine.config file under the .NET Framework 2.0 directory</span></span>  
  
    ```xml  
    <section name="uri" type="System.Configuration.UriSection, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    ```  
  
2.  <span data-ttu-id="574f3-130">IRI 구문 분석 규칙을 적용 해야 하는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="574f3-130">Specify whether IRI parsing rules should be applied.</span></span> <span data-ttu-id="574f3-131">이 설정은 machine.config 또는 app.config 파일에서 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="574f3-131">This can be done in the machine.config or in the app.config file.</span></span>  
  
 <span data-ttu-id="574f3-132">IRI 구문 분석을 사용 하도록 설정 (활성화 iriParsing = `true`) 최신 IRI에 따라 검사 문자 규칙 RFC 3987 및 정규화를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="574f3-132">Enabling IRI parsing (iriParsing enabled = `true`) will do normalization and character checking according to the latest IRI rules in RFC 3987.</span></span> <span data-ttu-id="574f3-133">기본값은 `false` 고 됩니다 정규화 및 수행 (IPv6 리터럴)에 대 한 RFC 2396에 따라 검사 및 RFC 3986 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="574f3-133">The default value is `false` and will do normalization and character checking according to RFC 2396 and RFC 3986 (for IPv6 literals).</span></span>  
  
### <a name="configuration-files"></a><span data-ttu-id="574f3-134">구성 파일</span><span class="sxs-lookup"><span data-stu-id="574f3-134">Configuration Files</span></span>  
 <span data-ttu-id="574f3-135">이 요소는 응용 프로그램 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="574f3-135">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="574f3-136">예제</span><span class="sxs-lookup"><span data-stu-id="574f3-136">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="574f3-137">설명</span><span class="sxs-lookup"><span data-stu-id="574f3-137">Description</span></span>  
 <span data-ttu-id="574f3-138">다음 예제에서 사용 되는 구성을 <xref:System.Uri> IRI 구문 분석 및 IDN 이름을 지원 하기 위해 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="574f3-138">The following example shows a configuration used by the <xref:System.Uri> class to support IRI parsing and IDN names.</span></span>  
  
### <a name="code"></a><span data-ttu-id="574f3-139">코드</span><span class="sxs-lookup"><span data-stu-id="574f3-139">Code</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <idn enabled="All" />  
    <iriParsing enabled="true" />  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="574f3-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="574f3-140">See Also</span></span>  
 <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection?displayProperty=nameWithType>  
 [<span data-ttu-id="574f3-141">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="574f3-141">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
