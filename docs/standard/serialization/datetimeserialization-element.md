---
title: "&lt;dateTimeSerialization&gt; 요소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- dateTimeSerialization element
- XML serialization, configuration
- <dateTimeSerialization> element
ms.assetid: 90fda55c-7730-41e9-bc4b-6423a4b920af
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bd6dda1f26e44c4864d5afea1427b2580ac1ed10
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="ltdatetimeserializationgt-element"></a><span data-ttu-id="dccfa-102">&lt;dateTimeSerialization&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="dccfa-102">&lt;dateTimeSerialization&gt; Element</span></span>
<span data-ttu-id="dccfa-103"><xref:System.DateTime> 개체의 serialization 모드를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="dccfa-103">Determines the serialization mode of <xref:System.DateTime> objects.</span></span>  
  
 <span data-ttu-id="dccfa-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="dccfa-104">\<configuration></span></span>  
<span data-ttu-id="dccfa-105">\<dateTimeSerialization></span><span class="sxs-lookup"><span data-stu-id="dccfa-105">\<dateTimeSerialization></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dccfa-106">구문</span><span class="sxs-lookup"><span data-stu-id="dccfa-106">Syntax</span></span>  
  
```xml  
<dateTimeSerialization  
    mode = "Roundtrip" | "Local"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dccfa-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="dccfa-107">Attributes and Elements</span></span>  
 <span data-ttu-id="dccfa-108">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dccfa-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dccfa-109">특성</span><span class="sxs-lookup"><span data-stu-id="dccfa-109">Attributes</span></span>  
  
|<span data-ttu-id="dccfa-110">특성</span><span class="sxs-lookup"><span data-stu-id="dccfa-110">Attributes</span></span>|<span data-ttu-id="dccfa-111">설명</span><span class="sxs-lookup"><span data-stu-id="dccfa-111">Description</span></span>|  
|----------------|-----------------|  
|`mode`|<span data-ttu-id="dccfa-112">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="dccfa-112">Optional.</span></span> <span data-ttu-id="dccfa-113">serialization 모드를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="dccfa-113">Specifies the serialization mode.</span></span> <span data-ttu-id="dccfa-114"><xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode> 값 중 하나로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="dccfa-114">Set to one of the <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode> values.</span></span> <span data-ttu-id="dccfa-115">기본값은 **RoundTrip**입니다.</span><span class="sxs-lookup"><span data-stu-id="dccfa-115">The default is **RoundTrip**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dccfa-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="dccfa-116">Child Elements</span></span>  
 <span data-ttu-id="dccfa-117">없음</span><span class="sxs-lookup"><span data-stu-id="dccfa-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dccfa-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="dccfa-118">Parent Elements</span></span>  
  
|<span data-ttu-id="dccfa-119">요소</span><span class="sxs-lookup"><span data-stu-id="dccfa-119">Element</span></span>|<span data-ttu-id="dccfa-120">설명</span><span class="sxs-lookup"><span data-stu-id="dccfa-120">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dccfa-121">system.xml.serialization</span><span class="sxs-lookup"><span data-stu-id="dccfa-121">system.xml.serialization</span></span>|<span data-ttu-id="dccfa-122">XML serialization을 제어하기 위한 최상위 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="dccfa-122">The top-level element for controlling XML serialization.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dccfa-123">설명</span><span class="sxs-lookup"><span data-stu-id="dccfa-123">Remarks</span></span>  
 <span data-ttu-id="dccfa-124">.NET Framework의 1.0, 1.1 및 2.0 이상 버전에서 이 속성이 **Local**로 설정되면 <xref:System.DateTime> 개체는 항상 로컬 시간으로 형식이 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="dccfa-124">In versions 1.0, 1.1, 2.0 and later versions of the .NET Framework, when this property is set to **Local**, <xref:System.DateTime> objects are always formatted as the local time.</span></span> <span data-ttu-id="dccfa-125">따라서 현지 시간대 정보가 serialize된 데이터에 항상 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="dccfa-125">That is, local time zone information is always included with the serialized data.</span></span> <span data-ttu-id="dccfa-126">.NET Framework 이전 버전과의 호환성을 제공하려면 이 속성을 **Local**로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="dccfa-126">Set this property to **Local** to ensure compatibility with older versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="dccfa-127">이 속성이 **Roundtrip**으로 설정된 .NET Framework 버전 2.0 이상에서는 <xref:System.DateTime> 개체를 검사하여 개체가 로컬, UTC 또는 미지정 표준 시간대에 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="dccfa-127">In version 2.0 and later versions of the .NET Framework that have this property set to **Roundtrip**, <xref:System.DateTime> objects are examined to determine whether they are in the local, UTC, or an unspecified time zone.</span></span> <span data-ttu-id="dccfa-128">그런 다음 <xref:System.DateTime> 개체는 이 정보를 유지할 수 있는 방식으로 serialize됩니다.</span><span class="sxs-lookup"><span data-stu-id="dccfa-128">The <xref:System.DateTime> objects are then serialized in such a way that this information is preserved.</span></span> <span data-ttu-id="dccfa-129">이 동작이 기본 동작이며 이전 버전의 framework와 통신하지 않는 모든 새 응용 프로그램에 대해 이를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="dccfa-129">This is the default behavior and is the recommended behavior for all new applications that do not communicate with older versions of the framework.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dccfa-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dccfa-130">See Also</span></span>  
 <xref:System.DateTime>  
 <xref:System.Xml.Serialization.XmlSchemaImporter>  
 <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>  
 [<span data-ttu-id="dccfa-131">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="dccfa-131">Configuration File Schema</span></span>](../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="dccfa-132">\<schemaImporterExtensions> 요소</span><span class="sxs-lookup"><span data-stu-id="dccfa-132">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)  
 [<span data-ttu-id="dccfa-133">\<xmlSchemaImporterExtensions>에 대한 \<add> 요소</span><span class="sxs-lookup"><span data-stu-id="dccfa-133">\<add> Element for \<xmlSchemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-xmlschemaimporterextensions.md)  
 [<span data-ttu-id="dccfa-134">\<system.xml.serialization> 요소</span><span class="sxs-lookup"><span data-stu-id="dccfa-134">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)
