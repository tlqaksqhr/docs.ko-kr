---
title: "&lt;xmlSchemaImporterExtensions&gt;의 요소 &lt;add&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XML serialization, configuration
- <add> element for <xmlSchemaImporterExtensions> element
ms.assetid: c828a558-094b-441e-9065-790b87315fa0
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 766d04dd792534f0da33116ed959d81ff376e026
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltaddgt-element-for-ltxmlschemaimporterextensionsgt"></a><span data-ttu-id="c4d2d-102">&lt;xmlSchemaImporterExtensions&gt;의 요소 &lt;add&gt;</span><span class="sxs-lookup"><span data-stu-id="c4d2d-102">&lt;add&gt; Element for &lt;xmlSchemaImporterExtensions&gt;</span></span>
<span data-ttu-id="c4d2d-103"><xref:System.Xml.Serialization.XmlSchemaImporter>에서 XSD 형식을 .NET Framework 형식으로 매핑하는 데 사용하는 형식을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c4d2d-103">Adds types used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping XSD types to .NET Framework types.</span></span> <span data-ttu-id="c4d2d-104">구성 파일에 대한 자세한 내용은 [구성 파일 스키마](../../../docs/framework/configure-apps/file-schema/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c4d2d-104">For more information about configuration files, see [Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
 <span data-ttu-id="c4d2d-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="c4d2d-105">\<configuration></span></span>  
<span data-ttu-id="c4d2d-106">\<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="c4d2d-106">\<system.xml.serialization></span></span>  
<span data-ttu-id="c4d2d-107">\<XmlSchemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="c4d2d-107">\<XmlSchemaImporterExtensions></span></span>  
<span data-ttu-id="c4d2d-108">\<add></span><span class="sxs-lookup"><span data-stu-id="c4d2d-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4d2d-109">구문</span><span class="sxs-lookup"><span data-stu-id="c4d2d-109">Syntax</span></span>  
  
```xml  
<add name = "typeName" type="fully qualified type [,Version=version number] [,Culture=culture] [,PublicKeyToken= token]"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c4d2d-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c4d2d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c4d2d-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c4d2d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c4d2d-112">특성</span><span class="sxs-lookup"><span data-stu-id="c4d2d-112">Attributes</span></span>  
  
|<span data-ttu-id="c4d2d-113">특성</span><span class="sxs-lookup"><span data-stu-id="c4d2d-113">Attribute</span></span>|<span data-ttu-id="c4d2d-114">설명</span><span class="sxs-lookup"><span data-stu-id="c4d2d-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c4d2d-115">**name**</span><span class="sxs-lookup"><span data-stu-id="c4d2d-115">**name**</span></span>|<span data-ttu-id="c4d2d-116">인스턴스를 찾는 데 사용되는 단순한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c4d2d-116">A simple name that is used to find the instance.</span></span>|  
|<span data-ttu-id="c4d2d-117">**type**</span><span class="sxs-lookup"><span data-stu-id="c4d2d-117">**type**</span></span>|<span data-ttu-id="c4d2d-118">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="c4d2d-118">Required.</span></span> <span data-ttu-id="c4d2d-119">추가할 스키마 확장 클래스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c4d2d-119">Specifies the schema  extension class to add.</span></span> <span data-ttu-id="c4d2d-120">**type** 특성 값은 한 줄로 표시되어야 하며 정규화된 형식 이름을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4d2d-120">The **type** attribute value must be on one line, and include the fully qualified type name.</span></span> <span data-ttu-id="c4d2d-121">GAC(전역 어셈블리 캐시)에 추가되는 어셈블리에는 서명된 어셈블리의 버전, 문화권 및 공개 키 토큰도 포함되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4d2d-121">When the assembly is placed in the Global Assembly Cache (GAC), it must also include the version, culture, and public key token of the signed assembly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c4d2d-122">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c4d2d-122">Child Elements</span></span>  
 <span data-ttu-id="c4d2d-123">없음</span><span class="sxs-lookup"><span data-stu-id="c4d2d-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c4d2d-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c4d2d-124">Parent Elements</span></span>  
  
|<span data-ttu-id="c4d2d-125">요소</span><span class="sxs-lookup"><span data-stu-id="c4d2d-125">Element</span></span>|<span data-ttu-id="c4d2d-126">설명</span><span class="sxs-lookup"><span data-stu-id="c4d2d-126">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c4d2d-127">\<xmlSchemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="c4d2d-127">\<xmlSchemaImporterExtensions></span></span>|<span data-ttu-id="c4d2d-128"><xref:System.Xml.Serialization.XmlSchemaImporter>에서 사용하는 형식을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="c4d2d-128">Contains the types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter>.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c4d2d-129">예제</span><span class="sxs-lookup"><span data-stu-id="c4d2d-129">Example</span></span>  
 <span data-ttu-id="c4d2d-130">다음 코드 예제에서는 XmlSchemaImporter가 형식을 매핑할 때 사용할 수 있는 확장 형식을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c4d2d-130">The following code example adds an extension type that the XmlSchemaImporter can use when mapping types.</span></span>  
  
```xml  
<configuration>  
  <system.xml.serialization>  
    <xmlSchemaImporterExtensions>  
       <add name="contoso" type="System.Web.Mobile.MobileCapabilities,   
       System.Web.Mobile, Version=2.0.0.0, Culture=neutral,   
       PublicKeyToken=b03f5f7f11d50a3a" />   
    </xmlSchemaImporterExtensions>  
  </system.xml.serialization>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c4d2d-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c4d2d-131">See Also</span></span>  
 <xref:System.Xml.Serialization.XmlSchemaImporter>  
 [<span data-ttu-id="c4d2d-132">\<system.xml.serialization> 요소</span><span class="sxs-lookup"><span data-stu-id="c4d2d-132">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)  
 [<span data-ttu-id="c4d2d-133">\<schemaImporterExtensions> 요소</span><span class="sxs-lookup"><span data-stu-id="c4d2d-133">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)
