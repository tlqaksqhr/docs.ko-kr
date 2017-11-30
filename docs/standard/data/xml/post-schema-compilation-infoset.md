---
title: Post-Schema Compilation Infoset
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
ms.assetid: 7f1bc7f4-401b-459f-9078-f099cc711fde
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 77fe1790a4ff2f910a740e969e458549f1fd9642
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="post-schema-compilation-infoset"></a><span data-ttu-id="4db08-102">Post-Schema Compilation Infoset</span><span class="sxs-lookup"><span data-stu-id="4db08-102">Post-Schema Compilation Infoset</span></span>
<span data-ttu-id="4db08-103">[World Wide Web Consortium (W3C) XML 스키마 권장 사항](http://go.microsoft.com/fwlink/?linkid=45242) 사전 스키마 유효성 검사 및 사후 스키마 컴파일을 위해 노출 해야 하는 정보 집합 (infoset)에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="4db08-103">The [World Wide Web Consortium (W3C) XML Schema Recommendation](http://go.microsoft.com/fwlink/?linkid=45242) discusses the information set (infoset) that must be exposed for pre-schema validation and post-schema compilation.</span></span> <span data-ttu-id="4db08-104">XML SOM(스키마 개체 모델)은 <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A>의 <xref:System.Xml.Schema.XmlSchemaSet> 메서드를 호출하기 전과 후에 이렇게 노출된 내용을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="4db08-104">The XML Schema Object Model (SOM) views this exposure before and after the <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> method of the <xref:System.Xml.Schema.XmlSchemaSet> is called.</span></span>  
  
 <span data-ttu-id="4db08-105">pre-schema validation infoset은 스키마를 편집하는 동안 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="4db08-105">The pre-schema validation infoset is built during the editing of the schema.</span></span> <span data-ttu-id="4db08-106">post-schema compilation infoset은 <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A>의 <xref:System.Xml.Schema.XmlSchemaSet> 메서드를 호출한 후에 스키마를 컴파일하는 동안 생성되며 속성으로 노출됩니다.</span><span class="sxs-lookup"><span data-stu-id="4db08-106">The post-schema compilation infoset is generated after the <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> method of the <xref:System.Xml.Schema.XmlSchemaSet> is called, during compilation of the schema, and is exposed as properties.</span></span>  
  
 <span data-ttu-id="4db08-107">SOM은 pre-schema validation 및 post-schema compilation infoset을 나타내는 개체 모델로, <xref:System.Xml.Schema?displayProperty=nameWithType> 네임스페이스의 클래스로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="4db08-107">The SOM is the object model that represents the pre-schema validation and post-schema compilation infosets; it consists of the classes in the <xref:System.Xml.Schema?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="4db08-108"><xref:System.Xml.Schema> 네임스페이스에서 클래스의 모든 읽기 및 쓰기 속성은 pre-schema validation infoset에 속하며 <xref:System.Xml.Schema> 네임스페이스에서 클래스의 모든 읽기 전용 속성은 post-schema compilation infoset에 속합니다.</span><span class="sxs-lookup"><span data-stu-id="4db08-108">All read and write properties of classes in the <xref:System.Xml.Schema> namespace belong to the pre-schema validation infoset, while all read-only properties of classes in the <xref:System.Xml.Schema> namespace belong to the post-schema compilation infoset.</span></span> <span data-ttu-id="4db08-109">다음 속성은 이 규칙의 예외로, pre-schema validation infoset 속성인 동시에 post-schema compilation infoset 속성이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="4db08-109">The exception to this rule are the following properties, which are both pre-schema validation infoset and post-schema compilation infoset properties.</span></span>  
  
|<span data-ttu-id="4db08-110">클래스</span><span class="sxs-lookup"><span data-stu-id="4db08-110">Class</span></span>|<span data-ttu-id="4db08-111">속성</span><span class="sxs-lookup"><span data-stu-id="4db08-111">Property</span></span>|  
|-----------|--------------|  
|<xref:System.Xml.Schema.XmlSchemaObject>|<xref:System.Xml.Schema.XmlSchemaObject.Parent%2A>|  
|<xref:System.Xml.Schema.XmlSchema>|<span data-ttu-id="4db08-112"><xref:System.Xml.Schema.XmlSchema.AttributeFormDefault%2A>, <xref:System.Xml.Schema.XmlSchema.BlockDefault%2A>, <xref:System.Xml.Schema.XmlSchema.ElementFormDefault%2A>, <xref:System.Xml.Schema.XmlSchema.FinalDefault%2A>, <xref:System.Xml.Schema.XmlSchema.TargetNamespace%2A></span><span class="sxs-lookup"><span data-stu-id="4db08-112"><xref:System.Xml.Schema.XmlSchema.AttributeFormDefault%2A>, <xref:System.Xml.Schema.XmlSchema.BlockDefault%2A>, <xref:System.Xml.Schema.XmlSchema.ElementFormDefault%2A>, <xref:System.Xml.Schema.XmlSchema.FinalDefault%2A>, <xref:System.Xml.Schema.XmlSchema.TargetNamespace%2A></span></span>|  
|<xref:System.Xml.Schema.XmlSchemaExternal>|<xref:System.Xml.Schema.XmlSchemaExternal.Schema%2A>|  
|<xref:System.Xml.Schema.XmlSchemaAttributeGroup>|<xref:System.Xml.Schema.XmlSchemaAttributeGroup.AnyAttribute%2A>|  
|<xref:System.Xml.Schema.XmlSchemaParticle>|<span data-ttu-id="4db08-113"><xref:System.Xml.Schema.XmlSchemaParticle.MaxOccurs%2A>, <xref:System.Xml.Schema.XmlSchemaParticle.MinOccurs%2A></span><span class="sxs-lookup"><span data-stu-id="4db08-113"><xref:System.Xml.Schema.XmlSchemaParticle.MaxOccurs%2A>, <xref:System.Xml.Schema.XmlSchemaParticle.MinOccurs%2A></span></span>|  
|<xref:System.Xml.Schema.XmlSchemaComplexType>|<xref:System.Xml.Schema.XmlSchemaComplexType.AnyAttribute%2A>|  
  
 <span data-ttu-id="4db08-114">예를 들어, <xref:System.Xml.Schema.XmlSchemaElement> 및 <xref:System.Xml.Schema.XmlSchemaComplexType> 클래스에는 `BlockResolved` 및 `FinalResolved` 속성이 둘 다 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4db08-114">For example, the <xref:System.Xml.Schema.XmlSchemaElement> and <xref:System.Xml.Schema.XmlSchemaComplexType> classes both have `BlockResolved` and `FinalResolved` properties.</span></span> <span data-ttu-id="4db08-115">이러한 속성을 사용하여 스키마를 컴파일하고 유효성을 검사한 후 `Block` 및 `Final` 속성에 대한 값을 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="4db08-115">These properties are used to hold the values for the `Block` and `Final` properties after the schema has been compiled and validated.</span></span> <span data-ttu-id="4db08-116">`BlockResolved` 및 `FinalResolved`는 post-schema compilation infoset의 일부인 읽기 전용 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="4db08-116">`BlockResolved` and `FinalResolved` are read-only properties that are part of the post-schema compilation infoset.</span></span>  
  
 <span data-ttu-id="4db08-117">다음 예제에서는 스키마의 유효성을 검사한 후 설정한 <xref:System.Xml.Schema.XmlSchemaElement.ElementSchemaType%2A> 클래스의 <xref:System.Xml.Schema.XmlSchemaElement> 속성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4db08-117">The following example shows the <xref:System.Xml.Schema.XmlSchemaElement.ElementSchemaType%2A> property of the <xref:System.Xml.Schema.XmlSchemaElement> class set after validating the schema.</span></span> <span data-ttu-id="4db08-118">유효성을 검사하기 전에 속성에 `null` 참조가 포함되며 <xref:System.Xml.Schema.XmlSchemaElement.SchemaTypeName%2A>이 해당 형식의 이름으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="4db08-118">Before validation, the property contains a `null` reference, and the <xref:System.Xml.Schema.XmlSchemaElement.SchemaTypeName%2A> is set to the name of the type in question.</span></span> <span data-ttu-id="4db08-119">유효성을 검사한 후 <xref:System.Xml.Schema.XmlSchemaElement.SchemaTypeName%2A>이 유효한 형식으로 확인되며 <xref:System.Xml.Schema.XmlSchemaElement.ElementSchemaType%2A> 속성을 통해 이 형식 개체를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4db08-119">After validation, the <xref:System.Xml.Schema.XmlSchemaElement.SchemaTypeName%2A> is resolved to a valid type, and the type object is available through the <xref:System.Xml.Schema.XmlSchemaElement.ElementSchemaType%2A> property.</span></span>  
  
 [!code-cpp[PsciSample#1](../../../../samples/snippets/cpp/VS_Snippets_Data/PsciSample/CPP/PsciSample.cpp#1)]
 [!code-csharp[PsciSample#1](../../../../samples/snippets/csharp/VS_Snippets_Data/PsciSample/CS/PsciSample.cs#1)]
 [!code-vb[PsciSample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/PsciSample/VB/PsciSample.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="4db08-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4db08-120">See Also</span></span>  
 [<span data-ttu-id="4db08-121">XML SOM(스키마 개체 모델)</span><span class="sxs-lookup"><span data-stu-id="4db08-121">XML Schema Object Model (SOM)</span></span>](../../../../docs/standard/data/xml/xml-schema-object-model-som.md)
