---
title: "스키마 가져오기 및 내보내기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, schema import and export
- XsdDataContractExporter class
- XsdDataContractImporter class
ms.assetid: 0da32b50-ccd9-463a-844c-7fe803d3bf44
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7a65f2c1daaac7e0e795412d666bb7d15e639361
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="schema-import-and-export"></a><span data-ttu-id="7a2be-102">스키마 가져오기 및 내보내기</span><span class="sxs-lookup"><span data-stu-id="7a2be-102">Schema Import and Export</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="7a2be-103"> 에는 새로운 serialization 엔진인 <xref:System.Runtime.Serialization.DataContractSerializer>가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a2be-103"> includes a new serialization engine, the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="7a2be-104">`DataContractSerializer`는 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 개체와 XML을 양방향으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="7a2be-104">The `DataContractSerializer` translates between [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] objects and XML (in both directions).</span></span> <span data-ttu-id="7a2be-105">이 serializer 이외에도, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에는 관련 스키마를 가져오고 내보내는 메커니즘이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a2be-105">In addition to the serializer itself, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] includes associated schema import and schema export mechanisms.</span></span> <span data-ttu-id="7a2be-106">*스키마* serializer 생성 하거나 deserializer가 액세스할 수 있는 XML 형태에, 정규화 되 고 컴퓨터가 읽을 수 있는 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="7a2be-106">*Schema* is a formal, precise, and machine-readable description of the shape of XML that the serializer produces or that the deserializer can access.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="7a2be-107">에서는 여러 타사 플랫폼과 상호 운용할 수 있는 W3C(World Wide Web 컨소시엄) XSD(XML 스키마 정의 언어)를 스키마 표현으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7a2be-107"> uses the World Wide Web Consortium (W3C) XML Schema definition language (XSD) as its schema representation, which is widely interoperable with numerous third-party platforms.</span></span>  
  
 <span data-ttu-id="7a2be-108">스키마 가져오기 구성 요소인 <xref:System.Runtime.Serialization.XsdDataContractImporter>는 XSD 스키마 문서를 사용하고 일반적으로 데이터 계약 클래스인 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 클래스를 생성하므로, serialize된 형태가 해당 스키마에 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="7a2be-108">The schema import component, <xref:System.Runtime.Serialization.XsdDataContractImporter>, takes an XSD schema document and generates [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] classes (normally data contract classes) such that the serialized forms correspond to the given schema.</span></span>  
  
 <span data-ttu-id="7a2be-109">예를 들어 다음과 같은 스키마 단편이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a2be-109">For example, the following schema fragment:</span></span>  
  
 [!code-csharp[c_SchemaImportExport#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#8)]
 [!code-vb[c_SchemaImportExport#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#8)]  
  
 <span data-ttu-id="7a2be-110">코드를 보다 쉽게 파악할 수 있도록 간소화된 다음과 같은 형식을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="7a2be-110">generates the following type (simplified slightly for better readability).</span></span>  
  
 [!code-csharp[c_SchemaImportExport#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#1)]
 [!code-vb[c_SchemaImportExport#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#1)]  
  
 <span data-ttu-id="7a2be-111">생성 된 형식을 따르는지 몇 가지 데이터 계약 모범 사례를 참고 (에 [모범 사례: 데이터 계약 버전 관리](../../../../docs/framework/wcf/best-practices-data-contract-versioning.md)):</span><span class="sxs-lookup"><span data-stu-id="7a2be-111">Note that the generated type follows several data contract best practices (found in [Best Practices: Data Contract Versioning](../../../../docs/framework/wcf/best-practices-data-contract-versioning.md)):</span></span>  
  
-   <span data-ttu-id="7a2be-112">이 형식은 <xref:System.Runtime.Serialization.IExtensibleDataObject> 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="7a2be-112">The type implements the <xref:System.Runtime.Serialization.IExtensibleDataObject> interface.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="7a2be-113">[이후 버전과 호환 데이터 계약](../../../../docs/framework/wcf/feature-details/forward-compatible-data-contracts.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7a2be-113"> [Forward-Compatible Data Contracts](../../../../docs/framework/wcf/feature-details/forward-compatible-data-contracts.md).</span></span>  
  
-   <span data-ttu-id="7a2be-114">데이터 멤버는 private 필드를 래핑하는 public 속성으로 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a2be-114">Data members are implemented as public properties that wrap private fields.</span></span>  
  
-   <span data-ttu-id="7a2be-115">클래스는 부분 클래스로, 생성된 코드를 수정하지 않고 추가 클래스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a2be-115">The class is a partial class, and additions can be made without modifying generated code.</span></span>  
  
 <span data-ttu-id="7a2be-116"><xref:System.Runtime.Serialization.XsdDataContractExporter>를 사용하면 반대로 작업할 수 있습니다. 즉 `DataContractSerializer`로 serialize할 수 있는 형식을 사용하고 XSD 스키마 문서를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a2be-116">The <xref:System.Runtime.Serialization.XsdDataContractExporter> enables you to do the reverse—take types that are serializable with the `DataContractSerializer` and generate an XSD Schema document.</span></span>  
  
## <a name="fidelity-is-not-guaranteed"></a><span data-ttu-id="7a2be-117">정확도는 보장되지 않음</span><span class="sxs-lookup"><span data-stu-id="7a2be-117">Fidelity Is Not Guaranteed</span></span>  
 <span data-ttu-id="7a2be-118">스키마나 형식을 통해 완벽히 정확한 라운드트립을 만든다고 보장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7a2be-118">It is not guaranteed that schema or types make a round trip with total fidelity.</span></span> <span data-ttu-id="7a2be-119">(A *왕복* 를 클래스 집합을 만들고 스키마를 다시 만들기 위해 그 결과 내보낼 스키마를 가져오는 것을 의미 합니다.) 이 경우 동일한 스키마는 반환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7a2be-119">(A *round trip* means to import a schema to create a set of classes, and export the result to create a schema again.) The same schema may not be returned.</span></span> <span data-ttu-id="7a2be-120">이 프로세스를 반대로 해도 정확도는 보장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7a2be-120">Reversing the process is also not guaranteed to preserve fidelity.</span></span> <span data-ttu-id="7a2be-121">(형식의 스키마를 생성하기 위해 형식을 내보낸 다음 그 형식을 다시 가져옵니다.)</span><span class="sxs-lookup"><span data-stu-id="7a2be-121">(Export a type to generate its schema, and then import the type back.</span></span> <span data-ttu-id="7a2be-122">이때도 동일한 형식은 반환되지 않을 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7a2be-122">It is unlikely the same type is returned.)</span></span>  
  
## <a name="supported-types"></a><span data-ttu-id="7a2be-123">지원 형식</span><span class="sxs-lookup"><span data-stu-id="7a2be-123">Supported Types</span></span>  
 <span data-ttu-id="7a2be-124">데이터 계약 모델은 WC3 스키마의 제한된 하위 집합만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="7a2be-124">The data contract model supports only a limited subset of the WC3 schema.</span></span> <span data-ttu-id="7a2be-125">이 하위 집합을 따르지 않는 스키마는 가져오기 프로세스 동안 예외를 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="7a2be-125">Any schema that does not conform to this subset will cause an exception during the import process.</span></span> <span data-ttu-id="7a2be-126">예를 들어 데이터 계약의 데이터 멤버가 XML 특성으로 serialize되도록 지정하는 방법이 없다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="7a2be-126">For example, there is no way to specify that a data member of a data contract should be serialized as an XML attribute.</span></span> <span data-ttu-id="7a2be-127">이 경우, XML 특성을 사용하도록 하는 스키마는 지원되지 않고, 올바른 XML 프로젝션으로 데이터 계약을 생성할 수 없으므로 가져오기 작업 동안 예외가 발생됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a2be-127">Thus, schemas that require the use of XML attributes are not supported and will cause exceptions during import, because it is impossible to generate a data contract with the correct XML projection.</span></span>  
  
 <span data-ttu-id="7a2be-128">예를 들어 다음과 같은 스키마 단편은 가져오기 기본 설정을 사용하여 가져올 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7a2be-128">For example, the following schema fragment cannot be imported using the default import settings.</span></span>  
  
 [!code-xml[c_SchemaImportExport#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/common/source.config#9)]  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="7a2be-129">[데이터 계약 스키마 참조](../../../../docs/framework/wcf/feature-details/data-contract-schema-reference.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7a2be-129"> [Data Contract Schema Reference](../../../../docs/framework/wcf/feature-details/data-contract-schema-reference.md).</span></span> <span data-ttu-id="7a2be-130">스키마가 데이터 계약 규칙을 따르지 않으면 다른 serialization 엔진을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7a2be-130">If a schema does not conform to the data contract rules, use a different serialization engine.</span></span> <span data-ttu-id="7a2be-131">예를 들어 <xref:System.Xml.Serialization.XmlSerializer>는 별도의 자체 스키마 가져오기 메커니즘을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7a2be-131">For example, the <xref:System.Xml.Serialization.XmlSerializer> uses its own separate schema import mechanism.</span></span> <span data-ttu-id="7a2be-132">또한 지원되는 스키마 범위가 확장되는 특별한 가져오기 모드도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a2be-132">Also, there is a special import mode in which the range of supported schema is expanded.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="7a2be-133">생성에 대 한 섹션 <xref:System.Xml.Serialization.IXmlSerializable> 의 형식은 [스키마 클래스 생성를 가져와서](../../../../docs/framework/wcf/feature-details/importing-schema-to-generate-classes.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7a2be-133"> the section about generating <xref:System.Xml.Serialization.IXmlSerializable> types in [Importing Schema to Generate Classes](../../../../docs/framework/wcf/feature-details/importing-schema-to-generate-classes.md).</span></span>  
  
 <span data-ttu-id="7a2be-134">`XsdDataContractExporter`는 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]로 serialize할 수 있는 모든 `DataContractSerializer` 형식을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="7a2be-134">The `XsdDataContractExporter` supports any [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] types that can be serialized with the `DataContractSerializer`.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="7a2be-135">[데이터 계약 Serializer에서 지 원하는 형식](../../../../docs/framework/wcf/feature-details/types-supported-by-the-data-contract-serializer.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7a2be-135"> [Types Supported by the Data Contract Serializer](../../../../docs/framework/wcf/feature-details/types-supported-by-the-data-contract-serializer.md).</span></span> <span data-ttu-id="7a2be-136">`XsdDataContractExporter`를 사용하여 스키마를 생성하지 않는 이상, `XsdDataContractImporter`를 통해 생성된 스키마는 일반적으로 <xref:System.Xml.Serialization.XmlSchemaProviderAttribute>가 사용할 수 있는 유효한 데이터가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a2be-136">Note that schema generated using the `XsdDataContractExporter` is normally valid data that the `XsdDataContractImporter` can use (unless the <xref:System.Xml.Serialization.XmlSchemaProviderAttribute> is used to customize the schema).</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="7a2be-137">사용 하는 <xref:System.Runtime.Serialization.XsdDataContractImporter>, 참조 [스키마 클래스 생성를 가져와서](../../../../docs/framework/wcf/feature-details/importing-schema-to-generate-classes.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7a2be-137"> using the <xref:System.Runtime.Serialization.XsdDataContractImporter>, see [Importing Schema to Generate Classes](../../../../docs/framework/wcf/feature-details/importing-schema-to-generate-classes.md).</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="7a2be-138">사용 하는 <xref:System.Runtime.Serialization.XsdDataContractExporter>, 참조 [클래스에서 스키마 내보내기](../../../../docs/framework/wcf/feature-details/exporting-schemas-from-classes.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7a2be-138"> using the <xref:System.Runtime.Serialization.XsdDataContractExporter>, see [Exporting Schemas from Classes](../../../../docs/framework/wcf/feature-details/exporting-schemas-from-classes.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a2be-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7a2be-139">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 <xref:System.Runtime.Serialization.XsdDataContractImporter>  
 <xref:System.Runtime.Serialization.XsdDataContractExporter>  
 [<span data-ttu-id="7a2be-140">스키마를 가져와 클래스 생성</span><span class="sxs-lookup"><span data-stu-id="7a2be-140">Importing Schema to Generate Classes</span></span>](../../../../docs/framework/wcf/feature-details/importing-schema-to-generate-classes.md)  
 [<span data-ttu-id="7a2be-141">클래스에서 스키마 내보내기</span><span class="sxs-lookup"><span data-stu-id="7a2be-141">Exporting Schemas from Classes</span></span>](../../../../docs/framework/wcf/feature-details/exporting-schemas-from-classes.md)
