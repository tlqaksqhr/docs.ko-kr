---
title: '&lt;system.xml.serialization&gt; 요소'
ms.date: 03/30/2017
helpviewer_keywords:
- system.xml.serialization element
- XML serialization, configuration
- <system.xml.serialization> element
ms.assetid: 3ce45919-388a-418c-8968-6df0372c73ec
ms.openlocfilehash: e26a12facb92147d7660ae266ea5e1b090d7e198
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33583775"
---
# <a name="ltsystemxmlserializationgt-element"></a><span data-ttu-id="199f4-102">&lt;system.xml.serialization&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="199f4-102">&lt;system.xml.serialization&gt; Element</span></span>
<span data-ttu-id="199f4-103">XML serialization을 제어하기 위한 최상위 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="199f4-103">The top-level element for controlling XML serialization.</span></span> <span data-ttu-id="199f4-104">구성 파일에 대한 자세한 내용은 [구성 파일 스키마](../../../docs/framework/configure-apps/file-schema/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="199f4-104">For more information about configuration files, see [Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
 <span data-ttu-id="199f4-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="199f4-105">\<configuration></span></span>  
<span data-ttu-id="199f4-106">\<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="199f4-106">\<system.xml.serialization></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="199f4-107">구문</span><span class="sxs-lookup"><span data-stu-id="199f4-107">Syntax</span></span>  
  
```xml  
<system.xml.serialization>  
</system.xml.serialization>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="199f4-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="199f4-108">Attributes and Elements</span></span>  
 <span data-ttu-id="199f4-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="199f4-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="199f4-110">특성</span><span class="sxs-lookup"><span data-stu-id="199f4-110">Attributes</span></span>  
 <span data-ttu-id="199f4-111">없음</span><span class="sxs-lookup"><span data-stu-id="199f4-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="199f4-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="199f4-112">Child Elements</span></span>  
  
|<span data-ttu-id="199f4-113">요소</span><span class="sxs-lookup"><span data-stu-id="199f4-113">Element</span></span>|<span data-ttu-id="199f4-114">설명</span><span class="sxs-lookup"><span data-stu-id="199f4-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="199f4-115">\<dateTimeSerialization> 요소</span><span class="sxs-lookup"><span data-stu-id="199f4-115">\<dateTimeSerialization> Element</span></span>](../../../docs/standard/serialization/datetimeserialization-element.md)|<span data-ttu-id="199f4-116"><xref:System.DateTime> 개체의 serialization 모드를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="199f4-116">Determines the serialization mode of <xref:System.DateTime> objects.</span></span>|  
|[<span data-ttu-id="199f4-117">\<schemaImporterExtensions> 요소</span><span class="sxs-lookup"><span data-stu-id="199f4-117">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)|<span data-ttu-id="199f4-118"><xref:System.Xml.Serialization.XmlSchemaImporter>에서 XSD 형식을 .NET Framework 형식으로 매핑하는 데 사용되는 형식을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="199f4-118">Contains types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping of XSD types to .NET Framework types.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="199f4-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="199f4-119">Parent Elements</span></span>  
  
|<span data-ttu-id="199f4-120">요소</span><span class="sxs-lookup"><span data-stu-id="199f4-120">Element</span></span>|<span data-ttu-id="199f4-121">설명</span><span class="sxs-lookup"><span data-stu-id="199f4-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="199f4-122">\<configuration> 요소</span><span class="sxs-lookup"><span data-stu-id="199f4-122">\<configuration> Element</span></span>](../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="199f4-123">공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="199f4-123">The root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="199f4-124">예제</span><span class="sxs-lookup"><span data-stu-id="199f4-124">Example</span></span>  
 <span data-ttu-id="199f4-125">다음 코드 예제에서는 <xref:System.DateTime> 개체의 serialization 모드를 지정하는 방법과 <xref:System.Xml.Serialization.XmlSchemaImporter>에서 XSD 형식을 .NET Framework 형식으로 매핑할 때 사용되는 형식을 추가하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="199f4-125">The following code example illustrates how to specify the serialization mode of a <xref:System.DateTime> object, and the addition of types used by the <xref:System.Xml.Serialization.XmlSchemaImporter> when mapping XSD types to .NET Framework types.</span></span>  
  
```xml  
<system.xml.serialization>  
    <xmlSerializer checkDeserializeAdvances="false" />  
    <dateTimeSerialization mode = "Local" />  
    <schemaImporterExtensions>  
        <add   
        name = "MobileCapabilities"   
        type = "System.Web.Mobile.MobileCapabilities,   
        System.Web.Mobile, Version - 2.0.0.0, Culture = neuutral,   
        PublicKeyToken = b03f5f6f11d40a3a" />  
    </schemaImporterExtensions>  
</system.sxml.serialization>  
```  
  
## <a name="see-also"></a><span data-ttu-id="199f4-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="199f4-126">See Also</span></span>  
 <xref:System.Xml.Serialization.XmlSchemaImporter>  
 <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>  
 [<span data-ttu-id="199f4-127">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="199f4-127">Configuration File Schema</span></span>](../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="199f4-128">\<dateTimeSerialization> 요소</span><span class="sxs-lookup"><span data-stu-id="199f4-128">\<dateTimeSerialization> Element</span></span>](../../../docs/standard/serialization/datetimeserialization-element.md)  
 [<span data-ttu-id="199f4-129">\<schemaImporterExtensions> 요소</span><span class="sxs-lookup"><span data-stu-id="199f4-129">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)  
 [<span data-ttu-id="199f4-130">\<xmlSchemaImporterExtensions>에 대한 \<add> 요소</span><span class="sxs-lookup"><span data-stu-id="199f4-130">\<add> Element for \<xmlSchemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-xmlschemaimporterextensions.md)
