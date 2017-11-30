---
title: "스키마 노드 형식 및 구조 유추 규칙"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d74ce896-717d-4871-8fd9-b070e2f53cb0
caps.latest.revision: "2"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c28c0f21b03fe7db014f118251363230a6ffc591
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="rules-for-inferring-schema-node-types-and-structure"></a><span data-ttu-id="00cbb-102">스키마 노드 형식 및 구조 유추 규칙</span><span class="sxs-lookup"><span data-stu-id="00cbb-102">Rules for Inferring Schema Node Types and Structure</span></span>
<span data-ttu-id="00cbb-103">이 항목에서는 스키마 유추 과정에서 XML 문서의 노드 형식을 XSD(XML 스키마 정의 언어) 구조로 변환하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="00cbb-103">This topic describes how the schema inference process translates the node types in an XML document to an XML Schema definition language (XSD) structure.</span></span>  
  
## <a name="element-inference-rules"></a><span data-ttu-id="00cbb-104">요소 유추 규칙</span><span class="sxs-lookup"><span data-stu-id="00cbb-104">Element Inference Rules</span></span>  
 <span data-ttu-id="00cbb-105">이 단원에서는 요소 선언의 유추 규칙에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="00cbb-105">This section describes the inference rules for element declarations.</span></span> <span data-ttu-id="00cbb-106">유추되는 8개의 요소 선언 구조는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="00cbb-106">There are eight structures of element declarations that will be inferred:</span></span>  
  
1.  <span data-ttu-id="00cbb-107">단순 형식 요소</span><span class="sxs-lookup"><span data-stu-id="00cbb-107">Element of simple type</span></span>  
  
2.  <span data-ttu-id="00cbb-108">빈 요소</span><span class="sxs-lookup"><span data-stu-id="00cbb-108">Empty element</span></span>  
  
3.  <span data-ttu-id="00cbb-109">특성을 가진 빈 요소</span><span class="sxs-lookup"><span data-stu-id="00cbb-109">Empty element with attributes</span></span>  
  
4.  <span data-ttu-id="00cbb-110">특성 및 단순 내용을 가진 요소</span><span class="sxs-lookup"><span data-stu-id="00cbb-110">Element with attributes and simple content</span></span>  
  
5.  <span data-ttu-id="00cbb-111">자식 요소 시퀀스를 가진 요소</span><span class="sxs-lookup"><span data-stu-id="00cbb-111">Element with a sequence of child elements</span></span>  
  
6.  <span data-ttu-id="00cbb-112">자식 요소 시퀀스와 특성을 가진 요소</span><span class="sxs-lookup"><span data-stu-id="00cbb-112">Element with a sequence of child elements and attributes</span></span>  
  
7.  <span data-ttu-id="00cbb-113">자식 요소 선택 시퀀스를 가진 요소</span><span class="sxs-lookup"><span data-stu-id="00cbb-113">Element with a sequence of choices of child elements</span></span>  
  
8.  <span data-ttu-id="00cbb-114">자식 요소 선택 시퀀스와 특성을 가진 요소</span><span class="sxs-lookup"><span data-stu-id="00cbb-114">Element with a sequence of choices of child elements and attributes</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="00cbb-115">모든 `complexType` 선언은 익명 형식으로 유추됩니다.</span><span class="sxs-lookup"><span data-stu-id="00cbb-115">All `complexType` declarations are inferred as anonymous types.</span></span> <span data-ttu-id="00cbb-116">유추되는 요소 중 루트 요소만이 전역 요소이며, 기타 모든 요소는 로컬 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="00cbb-116">The only global element inferred is the root element; all other elements are local.</span></span>  
  
 <span data-ttu-id="00cbb-117">스키마 유추 과정에 대 한 자세한 내용은 참조 [XML 문서에서 스키마 유추](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="00cbb-117">For more information about the schema inference process, see [Inferring Schemas from XML Documents](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md).</span></span>  
  
### <a name="simple-typed-element"></a><span data-ttu-id="00cbb-118">단순 형식 요소</span><span class="sxs-lookup"><span data-stu-id="00cbb-118">Simple Typed Element</span></span>  
 <span data-ttu-id="00cbb-119">다음 표에서는 <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> 메서드에 대한 XML 입력 및 생성된 XML 스키마를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="00cbb-119">The following table shows the XML input to the <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> method, and the XML schema generated.</span></span> <span data-ttu-id="00cbb-120">굵게 표시된 요소는 단순 형식 요소에 대해 유추된 스키마를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="00cbb-120">The bolded element shows the schema inferred for the simple type element.</span></span>  
  
 <span data-ttu-id="00cbb-121">스키마 유추 과정에 대 한 자세한 내용은 참조 [XML 문서에서 스키마 유추](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="00cbb-121">For more information about the schema inference process, see [Inferring Schemas from XML Documents](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md).</span></span>  
  
|<span data-ttu-id="00cbb-122">XML</span><span class="sxs-lookup"><span data-stu-id="00cbb-122">XML</span></span>|<span data-ttu-id="00cbb-123">스키마</span><span class="sxs-lookup"><span data-stu-id="00cbb-123">Schema</span></span>|  
|---------|------------|  
|`<?xml version="1.0"?>`<br /><br /> `<root>text</root>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> `<xs:element name="root" type="xs:string" />`<br /><br /> `</xs:schema>`|  
  
### <a name="empty-element"></a><span data-ttu-id="00cbb-124">빈 요소</span><span class="sxs-lookup"><span data-stu-id="00cbb-124">Empty Element</span></span>  
 <span data-ttu-id="00cbb-125">다음 표에서는 <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> 메서드에 대한 XML 입력 및 생성된 XML 스키마를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="00cbb-125">The following table shows the XML input to the <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> method, and the XML schema generated.</span></span> <span data-ttu-id="00cbb-126">굵게 표시된 요소는 빈 요소에 대해 유추된 스키마를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="00cbb-126">The bolded element shows the schema inferred for the empty element.</span></span>  
  
 <span data-ttu-id="00cbb-127">스키마 유추 과정에 대 한 자세한 내용은 참조 [XML 문서에서 스키마 유추](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="00cbb-127">For more information about the schema inference process, see [Inferring Schemas from XML Documents](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md).</span></span>  
  
|<span data-ttu-id="00cbb-128">XML</span><span class="sxs-lookup"><span data-stu-id="00cbb-128">XML</span></span>|<span data-ttu-id="00cbb-129">스키마</span><span class="sxs-lookup"><span data-stu-id="00cbb-129">Schema</span></span>|  
|---------|------------|  
|`<?xml version="1.0"?>`<br /><br /> `<empty/>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> `<xs:element name="empty" />`<br /><br /> `</xs:schema>`|  
  
### <a name="empty-element-with-attributes"></a><span data-ttu-id="00cbb-130">특성을 가진 빈 요소</span><span class="sxs-lookup"><span data-stu-id="00cbb-130">Empty Element with Attributes</span></span>  
 <span data-ttu-id="00cbb-131">다음 표에서는 <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> 메서드에 대한 XML 입력 및 생성된 XML 스키마를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="00cbb-131">The following table shows the XML input to the <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> method, and the XML schema generated.</span></span> <span data-ttu-id="00cbb-132">굵게 표시된 요소는 특성을 가진 빈 요소에 대해 유추된 스키마를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="00cbb-132">The bolded elements show the schema inferred for the empty element with attributes.</span></span>  
  
 <span data-ttu-id="00cbb-133">스키마 유추 과정에 대 한 자세한 내용은 참조 [XML 문서에서 스키마 유추](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="00cbb-133">For more information about the schema inference process, see [Inferring Schemas from XML Documents](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md).</span></span>  
  
|<span data-ttu-id="00cbb-134">XML</span><span class="sxs-lookup"><span data-stu-id="00cbb-134">XML</span></span>|<span data-ttu-id="00cbb-135">스키마</span><span class="sxs-lookup"><span data-stu-id="00cbb-135">Schema</span></span>|  
|---------|------------|  
|`<?xml version="1.0"?>`<br /><br /> `<empty attribute1="text"/>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> `<xs:element name="empty">`<br /><br /> `<xs:complexType>`<br /><br /> `<xs:attribute name="attribute1" type="xs:string" use="required" />`<br /><br /> `</xs:complexType>`<br /><br /> `</xs:element>`<br /><br /> `</xs:schema>`|  
  
### <a name="element-with-attributes-and-simple-content"></a><span data-ttu-id="00cbb-136">특성 및 단순 내용을 가진 요소</span><span class="sxs-lookup"><span data-stu-id="00cbb-136">Element with Attributes and Simple Content</span></span>  
 <span data-ttu-id="00cbb-137">다음 표에서는 <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> 메서드에 대한 XML 입력 및 생성된 XML 스키마를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="00cbb-137">The following table shows the XML input to the <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> method, and the XML schema generated.</span></span> <span data-ttu-id="00cbb-138">굵게 표시된 요소는 특성 및 단순 내용을 가진 요소에 대해 유추된 스키마를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="00cbb-138">The bolded elements show the schema inferred for an element with attributes and simple content.</span></span>  
  
 <span data-ttu-id="00cbb-139">스키마 유추 과정에 대 한 자세한 내용은 참조 [XML 문서에서 스키마 유추](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="00cbb-139">For more information about the schema inference process, see [Inferring Schemas from XML Documents](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md).</span></span>  
  
|<span data-ttu-id="00cbb-140">XML</span><span class="sxs-lookup"><span data-stu-id="00cbb-140">XML</span></span>|<span data-ttu-id="00cbb-141">스키마</span><span class="sxs-lookup"><span data-stu-id="00cbb-141">Schema</span></span>|  
|---------|------------|  
|`<?xml version="1.0"?>`<br /><br /> `<root attribute1="text">value</root>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> `<xs:element name="root">`<br /><br /> `<xs:complexType>`<br /><br /> `<xs:simpleContent>`<br /><br /> `<xs:extension base="xs:string">`<br /><br /> `<xs:attribute name="attribute1" type="xs:string" use="required" />`<br /><br /> `</xs:extension>`<br /><br /> `</xs:simpleContent>`<br /><br /> `</xs:complexType>`<br /><br /> `</xs:element>`<br /><br /> `</xs:schema>`|  
  
### <a name="element-with-a-sequence-of-child-elements"></a><span data-ttu-id="00cbb-142">자식 요소 시퀀스를 가진 요소</span><span class="sxs-lookup"><span data-stu-id="00cbb-142">Element with a Sequence of Child Elements</span></span>  
 <span data-ttu-id="00cbb-143">다음 표에서는 <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> 메서드에 대한 XML 입력 및 생성된 XML 스키마를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="00cbb-143">The following table shows the XML input to the <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> method, and the XML schema generated.</span></span> <span data-ttu-id="00cbb-144">굵게 표시된 요소는 자식 요소 시퀀스를 가진 요소에 대해 유추된 스키마를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="00cbb-144">The bolded elements show the schema inferred for an element with a sequence of child elements.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="00cbb-145">요소에 자식 요소가 한 개만 있더라도 여전히 시퀀스로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="00cbb-145">Even if an element has only one child element, it is still treated as a sequence.</span></span>  
  
 <span data-ttu-id="00cbb-146">스키마 유추 과정에 대 한 자세한 내용은 참조 [XML 문서에서 스키마 유추](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="00cbb-146">For more information about the schema inference process, see [Inferring Schemas from XML Documents](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md).</span></span>  
  
|<span data-ttu-id="00cbb-147">XML</span><span class="sxs-lookup"><span data-stu-id="00cbb-147">XML</span></span>|<span data-ttu-id="00cbb-148">스키마</span><span class="sxs-lookup"><span data-stu-id="00cbb-148">Schema</span></span>|  
|---------|------------|  
|`<?xml version="1.0"?>`<br /><br /> `<root>`<br /><br /> `<subElement/>`<br /><br /> `</root>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> `<xs:element name="root">`<br /><br /> `<xs:complexType>`<br /><br /> `<xs:sequence>`<br /><br /> `<xs:element name="subElement" />`<br /><br /> `</xs:sequence>`<br /><br /> `</xs:complexType>`<br /><br /> `</xs:element>`<br /><br /> `</xs:schema>`|  
  
### <a name="element-with-a-sequence-of-child-elements-and-attributes"></a><span data-ttu-id="00cbb-149">자식 요소 시퀀스와 특성을 가진 요소</span><span class="sxs-lookup"><span data-stu-id="00cbb-149">Element with a Sequence of Child Elements and Attributes</span></span>  
 <span data-ttu-id="00cbb-150">다음 표에서는 <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> 메서드에 대한 XML 입력 및 생성된 XML 스키마를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="00cbb-150">The following table shows the XML input to the <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> method, and the XML schema generated.</span></span> <span data-ttu-id="00cbb-151">굵게 표시된 요소는 자식 요소 시퀀스 및 특성을 가진 요소에 대해 유추된 스키마를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="00cbb-151">The bolded elements show the schema inferred for an element with a sequence of child elements and attributes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="00cbb-152">요소에 자식 요소가 한 개만 있더라도 여전히 시퀀스로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="00cbb-152">Even if an element has only one child element, it is still treated as a sequence.</span></span>  
  
 <span data-ttu-id="00cbb-153">스키마 유추 과정에 대 한 자세한 내용은 참조 [XML 문서에서 스키마 유추](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="00cbb-153">For more information about the schema inference process, see [Inferring Schemas from XML Documents](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md).</span></span>  
  
|<span data-ttu-id="00cbb-154">XML</span><span class="sxs-lookup"><span data-stu-id="00cbb-154">XML</span></span>|<span data-ttu-id="00cbb-155">스키마</span><span class="sxs-lookup"><span data-stu-id="00cbb-155">Schema</span></span>|  
|---------|------------|  
|`<?xml version="1.0"?>`<br /><br /> `<root attribute1="text">`<br /><br /> `<subElement1/>`<br /><br /> `<subElement2/>`<br /><br /> `</root>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> `<xs:element name="root">`<br /><br /> `<xs:complexType>`<br /><br /> `<xs:sequence>`<br /><br /> `<xs:element name="subElement1" />`<br /><br /> `<xs:element name="subElement2" />`<br /><br /> `</xs:sequence>`<br /><br /> `<xs:attribute name="attribute1" type="xs:string" use="required" />`<br /><br /> `</xs:complexType>`<br /><br /> `</xs:element>`<br /><br /> `</xs:schema>`|  
  
### <a name="element-with-a-sequence-and-choices-of-child-elements"></a><span data-ttu-id="00cbb-156">자식 요소 시퀀스 및 선택 항목을 가진 요소</span><span class="sxs-lookup"><span data-stu-id="00cbb-156">Element with a Sequence and Choices of Child Elements</span></span>  
 <span data-ttu-id="00cbb-157">다음 표에서는 <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> 메서드에 대한 XML 입력 및 생성된 XML 스키마를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="00cbb-157">The following table shows the XML input to the <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> method, and the XML schema generated.</span></span> <span data-ttu-id="00cbb-158">굵게 표시된 요소는 자식 요소 시퀀스 및 선택 항목을 가진 요소에 대해 유추된 스키마를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="00cbb-158">The bolded elements show the schema inferred for an element with a sequence and choice of child elements.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="00cbb-159">`maxOccurs` 요소의 `xs:choice` 특성은 유추된 스키마에서 `"unbounded"`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="00cbb-159">The `maxOccurs` attribute of the `xs:choice` element is set to `"unbounded"` in the inferred schema.</span></span>  
  
 <span data-ttu-id="00cbb-160">스키마 유추 과정에 대 한 자세한 내용은 참조 [XML 문서에서 스키마 유추](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="00cbb-160">For more information about the schema inference process, see [Inferring Schemas from XML Documents](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md).</span></span>  
  
|<span data-ttu-id="00cbb-161">XML</span><span class="sxs-lookup"><span data-stu-id="00cbb-161">XML</span></span>|<span data-ttu-id="00cbb-162">스키마</span><span class="sxs-lookup"><span data-stu-id="00cbb-162">Schema</span></span>|  
|---------|------------|  
|`<?xml version="1.0"?>`<br /><br /> `<root>`<br /><br /> `<subElement1/>`<br /><br /> `<subElement2/>`<br /><br /> `<subElement1/>`<br /><br /> `</root>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> `<xs:element name="root">`<br /><br /> `<xs:complexType>`<br /><br /> `<xs:sequence>`<br /><br /> `<xs:choice maxOccurs="unbounded">`<br /><br /> `<xs:element name="subElement1" />`<br /><br /> `<xs:element name="subElement2" />`<br /><br /> `</xs:choice>`<br /><br /> `</xs:sequence>`<br /><br /> `</xs:complexType>`<br /><br /> `</xs:element>`<br /><br /> `</xs:schema>`|  
  
### <a name="element-with-a-sequence-and-choice-of-child-elements-and-attributes"></a><span data-ttu-id="00cbb-163">자식 요소 시퀀스 및 선택 항목과 특성을 가진 요소</span><span class="sxs-lookup"><span data-stu-id="00cbb-163">Element with a Sequence and Choice of Child Elements and Attributes</span></span>  
 <span data-ttu-id="00cbb-164">다음 표에서는 <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> 메서드에 대한 XML 입력 및 생성된 XML 스키마를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="00cbb-164">The following table shows the XML input to the <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> method, and the XML schema generated.</span></span> <span data-ttu-id="00cbb-165">굵게 표시된 요소는 자식 요소 시퀀스 및 선택 항목과 특성을 가진 요소에 대해 유추된 스키마를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="00cbb-165">The bolded elements show the schema inferred for an element with a sequence and choice of child elements and attributes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="00cbb-166">`maxOccurs` 요소의 `xs:choice` 특성은 유추된 스키마에서 `"unbounded"`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="00cbb-166">The `maxOccurs` attribute of the `xs:choice` element is set to `"unbounded"` in the inferred schema.</span></span>  
  
 <span data-ttu-id="00cbb-167">스키마 유추 과정에 대 한 자세한 내용은 참조 [XML 문서에서 스키마 유추](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="00cbb-167">For more information about the schema inference process, see [Inferring Schemas from XML Documents](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md).</span></span>  
  
|<span data-ttu-id="00cbb-168">XML</span><span class="sxs-lookup"><span data-stu-id="00cbb-168">XML</span></span>|<span data-ttu-id="00cbb-169">스키마</span><span class="sxs-lookup"><span data-stu-id="00cbb-169">Schema</span></span>|  
|---------|------------|  
|`<?xml version="1.0"?>`<br /><br /> `<root attribute1="text">`<br /><br /> `<subElement1/>`<br /><br /> `<subElement2/>`<br /><br /> `<subElement1/>`<br /><br /> `</root>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> `<xs:element name="root">`<br /><br /> `<xs:complexType>`<br /><br /> `<xs:sequence>`<br /><br /> `<xs:choice maxOccurs="unbounded">`<br /><br /> `<xs:element name="subElement1" />`<br /><br /> `<xs:element name="subElement2" />`<br /><br /> `</xs:choice>`<br /><br /> `</xs:sequence>`<br /><br /> `<xs:attribute name="attribute1" type="xs:string" use="required" />`<br /><br /> `</xs:complexType>`<br /><br /> `</xs:element>`<br /><br /> `</xs:schema>`|  
  
### <a name="attribute-processing"></a><span data-ttu-id="00cbb-170">특성 처리</span><span class="sxs-lookup"><span data-stu-id="00cbb-170">Attribute Processing</span></span>  
 <span data-ttu-id="00cbb-171">노드에서 새로운 특성이 나타날 때마다 해당 특성은 `use="required"`와 함께 노드의 유추된 정의에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="00cbb-171">Whenever a new attribute is encountered within a node, it is added to the inferred definition of the node with `use="required"`.</span></span> <span data-ttu-id="00cbb-172">인스턴스에서 같은 노드가 다시 나타나면 유추 과정에서 현재 인스턴스의 특성을 이미 유추된 특성과 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="00cbb-172">The next time the same node is found in the instance, the inference process will compare attributes of the current instance with the ones already inferred.</span></span> <span data-ttu-id="00cbb-173">인스턴스에 이미 유추된 특성의 일부가 누락되어 있으면 `use="optional"`이 특성 정의에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="00cbb-173">If some of the already inferred ones are missing in the instance, `use="optional"` is added to the attribute definition.</span></span> <span data-ttu-id="00cbb-174">새로운 특성은 `use="optional"`과 함께 기존 선언에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="00cbb-174">New attributes are added to existing declarations with `use="optional"`.</span></span>  
  
### <a name="occurrence-constraints"></a><span data-ttu-id="00cbb-175">발생 제약 조건</span><span class="sxs-lookup"><span data-stu-id="00cbb-175">Occurrence Constraints</span></span>  
 <span data-ttu-id="00cbb-176">스키마 유추 과정에서는 스키마의 유추된 구성 요소에 대해 `minOccurs` 또는 `maxOccurs` 및 `"0"` 또는 `"1"`의 값을 갖는 `"1"` 및 `"unbounded"` 특성이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="00cbb-176">During the schema inference process, the `minOccurs` and `maxOccurs` attributes are generated, for inferred components of a schema, with the values `"0"` or `"1"` and `"1"` or `"unbounded"`.</span></span> <span data-ttu-id="00cbb-177">`"1"` 및 `"unbounded"` 값은 `"0"` 및 `"1"` 값이 XML 문서의 유효성을 검사할 수 없을 경우에만 사용됩니다. 예를 들어, `MinOccurs="0"`이 요소를 정확하게 나타내지 못하면 `minOccurs="1"`이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="00cbb-177">The values `"1"` and `"unbounded"` are used only when the values `"0"` and `"1"` cannot validate the XML document (for example, if `MinOccurs="0"` does not accurately describe an element, `minOccurs="1"` is used).</span></span>  
  
### <a name="mixed-content"></a><span data-ttu-id="00cbb-178">혼합 내용</span><span class="sxs-lookup"><span data-stu-id="00cbb-178">Mixed Content</span></span>  
 <span data-ttu-id="00cbb-179">요소에 텍스트와 요소가 섞여 있는 것과 같이 혼합 내용이 있으면 유추된 복합 형식 정의에 대해 `mixed="true"` 특성이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="00cbb-179">If an element contains mixed content (for example text interspersed with elements), the `mixed="true"` attribute is generated for the inferred complex type definition.</span></span>  
  
## <a name="other-node-type-inference-rules"></a><span data-ttu-id="00cbb-180">기타 노드 형식 유추 규칙</span><span class="sxs-lookup"><span data-stu-id="00cbb-180">Other Node Type Inference Rules</span></span>  
 <span data-ttu-id="00cbb-181">다음 표에서는 처리 명령, 주석, entityreference, CDATA, 문서 형식 및 네임스페이스 노드의 유추 규칙에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="00cbb-181">The following table describes the inference rules for processing instruction, comment, entity reference, CDATA, document type, and namespace nodes.</span></span>  
  
|<span data-ttu-id="00cbb-182">노드 형식</span><span class="sxs-lookup"><span data-stu-id="00cbb-182">Node Type</span></span>|<span data-ttu-id="00cbb-183">변환</span><span class="sxs-lookup"><span data-stu-id="00cbb-183">Translation</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="00cbb-184">처리 명령</span><span class="sxs-lookup"><span data-stu-id="00cbb-184">Processing instruction</span></span>|<span data-ttu-id="00cbb-185">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="00cbb-185">Ignored.</span></span>|  
|<span data-ttu-id="00cbb-186">주석</span><span class="sxs-lookup"><span data-stu-id="00cbb-186">Comment</span></span>|<span data-ttu-id="00cbb-187">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="00cbb-187">Ignored.</span></span>|  
|<span data-ttu-id="00cbb-188">EntityReference</span><span class="sxs-lookup"><span data-stu-id="00cbb-188">Entity reference</span></span>|<span data-ttu-id="00cbb-189"><xref:System.Xml.Schema.XmlSchemaInference> 클래스는 엔터티 참조를 처리하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="00cbb-189">The <xref:System.Xml.Schema.XmlSchemaInference> class does not handle entity references.</span></span> <span data-ttu-id="00cbb-190">XML 문서에 엔터티 참조가 있는 경우 엔터티를 확장하는 판독기를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00cbb-190">If an XML document contains entity references, you need to use a reader that expands the entities.</span></span> <span data-ttu-id="00cbb-191">예를 들어, 매개 변수로서 <xref:System.Xml.XmlTextReader>로 설정된 <xref:System.Xml.XmlTextReader.EntityHandling%2A> 속성과 함께 <xref:System.Xml.EntityHandling.ExpandEntities>를 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00cbb-191">For example, you can pass an <xref:System.Xml.XmlTextReader> with the <xref:System.Xml.XmlTextReader.EntityHandling%2A> property set to <xref:System.Xml.EntityHandling.ExpandEntities> as a parameter.</span></span> <span data-ttu-id="00cbb-192">엔터티 참조가 발생할 때 판독기가 엔터티를 확장하지 않으면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="00cbb-192">If entity references are encountered and the reader does not expand entities, an exception is throw.</span></span>|  
|<span data-ttu-id="00cbb-193">CDATA</span><span class="sxs-lookup"><span data-stu-id="00cbb-193">CDATA</span></span>|<span data-ttu-id="00cbb-194">XML 문서의 모든 `<![CDATA[ … ]]` 섹션은 `xs:string`으로 유추됩니다.</span><span class="sxs-lookup"><span data-stu-id="00cbb-194">Any `<![CDATA[ … ]]` sections in an XML document will be inferred as `xs:string`.</span></span>|  
|<span data-ttu-id="00cbb-195">문서 형식</span><span class="sxs-lookup"><span data-stu-id="00cbb-195">Document type</span></span>|<span data-ttu-id="00cbb-196">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="00cbb-196">Ignored.</span></span>|  
|<span data-ttu-id="00cbb-197">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="00cbb-197">Namespaces</span></span>|<span data-ttu-id="00cbb-198">무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="00cbb-198">Ignored.</span></span>|  
  
 <span data-ttu-id="00cbb-199">스키마 유추 과정에 대 한 자세한 내용은 참조 [XML 문서에서 스키마 유추](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="00cbb-199">For more information about the schema inference process, see [Inferring Schemas from XML Documents](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00cbb-200">참고 항목</span><span class="sxs-lookup"><span data-stu-id="00cbb-200">See Also</span></span>  
 <xref:System.Xml.Schema.XmlSchemaInference>  
 [<span data-ttu-id="00cbb-201">XML SOM(스키마 개체 모델)</span><span class="sxs-lookup"><span data-stu-id="00cbb-201">XML Schema Object Model (SOM)</span></span>](../../../../docs/standard/data/xml/xml-schema-object-model-som.md)  
 [<span data-ttu-id="00cbb-202">XML 스키마 유추</span><span class="sxs-lookup"><span data-stu-id="00cbb-202">Inferring an XML Schema</span></span>](../../../../docs/standard/data/xml/inferring-an-xml-schema.md)  
 [<span data-ttu-id="00cbb-203">XML 문서에서 스키마 유추</span><span class="sxs-lookup"><span data-stu-id="00cbb-203">Inferring Schemas from XML Documents</span></span>](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md)  
 [<span data-ttu-id="00cbb-204">단순 형식 유추 규칙</span><span class="sxs-lookup"><span data-stu-id="00cbb-204">Rules for Inferring Simple Types</span></span>](../../../../docs/standard/data/xml/rules-for-inferring-simple-types.md)
