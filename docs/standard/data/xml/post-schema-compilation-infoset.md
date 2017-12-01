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
# <a name="post-schema-compilation-infoset"></a>Post-Schema Compilation Infoset
[World Wide Web Consortium (W3C) XML 스키마 권장 사항](http://go.microsoft.com/fwlink/?linkid=45242) 사전 스키마 유효성 검사 및 사후 스키마 컴파일을 위해 노출 해야 하는 정보 집합 (infoset)에 대해 설명 합니다. XML SOM(스키마 개체 모델)은 <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A>의 <xref:System.Xml.Schema.XmlSchemaSet> 메서드를 호출하기 전과 후에 이렇게 노출된 내용을 표시합니다.  
  
 pre-schema validation infoset은 스키마를 편집하는 동안 만들어집니다. post-schema compilation infoset은 <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A>의 <xref:System.Xml.Schema.XmlSchemaSet> 메서드를 호출한 후에 스키마를 컴파일하는 동안 생성되며 속성으로 노출됩니다.  
  
 SOM은 pre-schema validation 및 post-schema compilation infoset을 나타내는 개체 모델로, <xref:System.Xml.Schema?displayProperty=nameWithType> 네임스페이스의 클래스로 구성됩니다. <xref:System.Xml.Schema> 네임스페이스에서 클래스의 모든 읽기 및 쓰기 속성은 pre-schema validation infoset에 속하며 <xref:System.Xml.Schema> 네임스페이스에서 클래스의 모든 읽기 전용 속성은 post-schema compilation infoset에 속합니다. 다음 속성은 이 규칙의 예외로, pre-schema validation infoset 속성인 동시에 post-schema compilation infoset 속성이기도 합니다.  
  
|클래스|속성|  
|-----------|--------------|  
|<xref:System.Xml.Schema.XmlSchemaObject>|<xref:System.Xml.Schema.XmlSchemaObject.Parent%2A>|  
|<xref:System.Xml.Schema.XmlSchema>|<xref:System.Xml.Schema.XmlSchema.AttributeFormDefault%2A>, <xref:System.Xml.Schema.XmlSchema.BlockDefault%2A>, <xref:System.Xml.Schema.XmlSchema.ElementFormDefault%2A>, <xref:System.Xml.Schema.XmlSchema.FinalDefault%2A>, <xref:System.Xml.Schema.XmlSchema.TargetNamespace%2A>|  
|<xref:System.Xml.Schema.XmlSchemaExternal>|<xref:System.Xml.Schema.XmlSchemaExternal.Schema%2A>|  
|<xref:System.Xml.Schema.XmlSchemaAttributeGroup>|<xref:System.Xml.Schema.XmlSchemaAttributeGroup.AnyAttribute%2A>|  
|<xref:System.Xml.Schema.XmlSchemaParticle>|<xref:System.Xml.Schema.XmlSchemaParticle.MaxOccurs%2A>, <xref:System.Xml.Schema.XmlSchemaParticle.MinOccurs%2A>|  
|<xref:System.Xml.Schema.XmlSchemaComplexType>|<xref:System.Xml.Schema.XmlSchemaComplexType.AnyAttribute%2A>|  
  
 예를 들어, <xref:System.Xml.Schema.XmlSchemaElement> 및 <xref:System.Xml.Schema.XmlSchemaComplexType> 클래스에는 `BlockResolved` 및 `FinalResolved` 속성이 둘 다 있습니다. 이러한 속성을 사용하여 스키마를 컴파일하고 유효성을 검사한 후 `Block` 및 `Final` 속성에 대한 값을 유지합니다. `BlockResolved` 및 `FinalResolved`는 post-schema compilation infoset의 일부인 읽기 전용 속성입니다.  
  
 다음 예제에서는 스키마의 유효성을 검사한 후 설정한 <xref:System.Xml.Schema.XmlSchemaElement.ElementSchemaType%2A> 클래스의 <xref:System.Xml.Schema.XmlSchemaElement> 속성을 보여 줍니다. 유효성을 검사하기 전에 속성에 `null` 참조가 포함되며 <xref:System.Xml.Schema.XmlSchemaElement.SchemaTypeName%2A>이 해당 형식의 이름으로 설정됩니다. 유효성을 검사한 후 <xref:System.Xml.Schema.XmlSchemaElement.SchemaTypeName%2A>이 유효한 형식으로 확인되며 <xref:System.Xml.Schema.XmlSchemaElement.ElementSchemaType%2A> 속성을 통해 이 형식 개체를 사용할 수 있습니다.  
  
 [!code-cpp[PsciSample#1](../../../../samples/snippets/cpp/VS_Snippets_Data/PsciSample/CPP/PsciSample.cpp#1)]
 [!code-csharp[PsciSample#1](../../../../samples/snippets/csharp/VS_Snippets_Data/PsciSample/CS/PsciSample.cs#1)]
 [!code-vb[PsciSample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/PsciSample/VB/PsciSample.vb#1)]  
  
## <a name="see-also"></a>참고 항목  
 [XML SOM(스키마 개체 모델)](../../../../docs/standard/data/xml/xml-schema-object-model-som.md)
