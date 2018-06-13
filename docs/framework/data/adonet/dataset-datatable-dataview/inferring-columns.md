---
title: 열 유추
ms.date: 03/30/2017
ms.assetid: 0e022699-c922-454c-93e2-957dd7e7247a
ms.openlocfilehash: da98bcbc4537e08a6f8565b36f8b84b476efd027
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32761079"
---
# <a name="inferring-columns"></a><span data-ttu-id="5cbcc-102">열 유추</span><span class="sxs-lookup"><span data-stu-id="5cbcc-102">Inferring Columns</span></span>
<span data-ttu-id="5cbcc-103">ADO.NET에서 XML 문서로부터 <xref:System.Data.DataSet>의 테이블로 유추할 요소를 결정한 후에는 해당 테이블의 열을 유추합니다.</span><span class="sxs-lookup"><span data-stu-id="5cbcc-103">After ADO.NET has determined from an XML document which elements to infer as tables for a <xref:System.Data.DataSet>, it then infers the columns for those tables.</span></span> <span data-ttu-id="5cbcc-104">ADO.NET 2.0에는 각각에 대해 강력한 형식의 데이터 형식을 유추 하는 새로운 스키마 유추 엔진이 도입 **simpleType** 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="5cbcc-104">ADO.NET 2.0 introduced a new schema inference engine that infers a strongly typed data type for each **simpleType** element.</span></span> <span data-ttu-id="5cbcc-105">유추 된 데이터 형식이 이전 버전에서는 **simpleType** 요소가 항상 **xsd: string**합니다.</span><span class="sxs-lookup"><span data-stu-id="5cbcc-105">In previous versions, the data type of an inferred **simpleType** element was always **xsd:string**.</span></span>  
  
## <a name="migration-and-backward-compatibility"></a><span data-ttu-id="5cbcc-106">마이그레이션 및 이전 버전과의 호환성</span><span class="sxs-lookup"><span data-stu-id="5cbcc-106">Migration and Backward Compatibility</span></span>  
 <span data-ttu-id="5cbcc-107">**ReadXml** 형식의 인수를 사용 하는 메서드 **InferSchema**합니다.</span><span class="sxs-lookup"><span data-stu-id="5cbcc-107">The **ReadXml** method takes an argument of type **InferSchema**.</span></span> <span data-ttu-id="5cbcc-108">이 인수를 사용하면 이전 버전과 호환되는 유추 동작을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cbcc-108">This argument allows you to specify inference behavior compatible with previous versions.</span></span> <span data-ttu-id="5cbcc-109">에 대 한 사용 가능한 값은 **InferSchema** 열거형 다음 표에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cbcc-109">The available values for the **InferSchema** enumeration are shown in the following table.</span></span>  
  
 <xref:System.Data.XmlReadMode.InferSchema>  
 <span data-ttu-id="5cbcc-110">항상 단순 형식을 <xref:System.String>으로 유추하여 이전 버전과의 호환성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5cbcc-110">Provides backward compatibility by always inferring a simple type as <xref:System.String>.</span></span>  
  
 <xref:System.Data.XmlReadMode.InferTypedSchema>  
 <span data-ttu-id="5cbcc-111">강력한 형식의 데이터 형식을 유추합니다.</span><span class="sxs-lookup"><span data-stu-id="5cbcc-111">Infers a strongly typed data type.</span></span> <span data-ttu-id="5cbcc-112"><xref:System.Data.DataTable>과 함께 사용할 경우 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="5cbcc-112">Throws an exception if used with a <xref:System.Data.DataTable>.</span></span>  
  
 <xref:System.Data.XmlReadMode.IgnoreSchema>  
 <span data-ttu-id="5cbcc-113">인라인 스키마를 무시하고 데이터를 기존 <xref:System.Data.DataSet> 스키마로 읽어옵니다.</span><span class="sxs-lookup"><span data-stu-id="5cbcc-113">Ignores any inline schema and reads data into the existing <xref:System.Data.DataSet> schema.</span></span>  
  
## <a name="attributes"></a><span data-ttu-id="5cbcc-114">특성</span><span class="sxs-lookup"><span data-stu-id="5cbcc-114">Attributes</span></span>  
 <span data-ttu-id="5cbcc-115">에 정의 된 대로 [테이블 유추](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-tables.md), 특성이 있는 요소는 테이블로 유추 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5cbcc-115">As defined in [Inferring Tables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-tables.md), an element with attributes will be inferred as a table.</span></span> <span data-ttu-id="5cbcc-116">그러면 해당 요소의 특성은 테이블의 열로 유추됩니다.</span><span class="sxs-lookup"><span data-stu-id="5cbcc-116">The attributes of that element will then be inferred as columns for the table.</span></span> <span data-ttu-id="5cbcc-117">**ColumnMapping** 열의 속성을로 설정 됩니다 **MappingType.Attribute**, 스키마가 XML에 다시 기록 하는 경우 열 이름이 특성으로 작성 되도록 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cbcc-117">The **ColumnMapping** property of the columns will be set to **MappingType.Attribute**, to ensure that the column names will be written as attributes if the schema is written back to XML.</span></span> <span data-ttu-id="5cbcc-118">특성 값은 테이블의 행에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="5cbcc-118">The values of the attributes are stored in a row in the table.</span></span> <span data-ttu-id="5cbcc-119">예를 들어, 다음과 같은 XML을 가정해 봅시다.</span><span class="sxs-lookup"><span data-stu-id="5cbcc-119">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 <span data-ttu-id="5cbcc-120">위 유추 과정에서 이라는 테이블이 생성 됩니다 **Element1** 두 개의 열이 있는 **attr1** 및 **attr2**합니다.</span><span class="sxs-lookup"><span data-stu-id="5cbcc-120">The inference process will produce a table named **Element1** with two columns, **attr1** and **attr2**.</span></span> <span data-ttu-id="5cbcc-121">**ColumnMapping** 두 열 모두의 속성으로 설정 됩니다 **MappingType.Attribute**합니다.</span><span class="sxs-lookup"><span data-stu-id="5cbcc-121">The **ColumnMapping** property of both columns will be set to **MappingType.Attribute**.</span></span>  
  
 <span data-ttu-id="5cbcc-122">**데이터 집합:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="5cbcc-122">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="5cbcc-123">**Table:** Element1</span><span class="sxs-lookup"><span data-stu-id="5cbcc-123">**Table:** Element1</span></span>  
  
|<span data-ttu-id="5cbcc-124">attr1</span><span class="sxs-lookup"><span data-stu-id="5cbcc-124">attr1</span></span>|<span data-ttu-id="5cbcc-125">attr2</span><span class="sxs-lookup"><span data-stu-id="5cbcc-125">attr2</span></span>|  
|-----------|-----------|  
|<span data-ttu-id="5cbcc-126">value1</span><span class="sxs-lookup"><span data-stu-id="5cbcc-126">value1</span></span>|<span data-ttu-id="5cbcc-127">value2</span><span class="sxs-lookup"><span data-stu-id="5cbcc-127">value2</span></span>|  
  
## <a name="elements-without-attributes-or-child-elements"></a><span data-ttu-id="5cbcc-128">특성이나 자식 요소가 없는 요소</span><span class="sxs-lookup"><span data-stu-id="5cbcc-128">Elements Without Attributes or Child Elements</span></span>  
 <span data-ttu-id="5cbcc-129">요소에 자식 요소나 특성이 없으면 해당 요소는 열로 유추됩니다.</span><span class="sxs-lookup"><span data-stu-id="5cbcc-129">If an element has no child elements or attributes, it will be inferred as a column.</span></span> <span data-ttu-id="5cbcc-130">**ColumnMapping** 열의 속성이로 설정 됩니다 **MappingType.Element**합니다.</span><span class="sxs-lookup"><span data-stu-id="5cbcc-130">The **ColumnMapping** property of the column will be set to **MappingType.Element**.</span></span> <span data-ttu-id="5cbcc-131">자식 요소의 텍스트는 해당 테이블의 행에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="5cbcc-131">The text for child elements is stored in a row in the table.</span></span> <span data-ttu-id="5cbcc-132">예를 들어, 다음과 같은 XML을 가정해 봅시다.</span><span class="sxs-lookup"><span data-stu-id="5cbcc-132">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="5cbcc-133">위 유추 과정에서 이라는 테이블이 생성 됩니다 **Element1** 두 개의 열이 있는 **ChildElement1** 및 **ChildElement2**합니다.</span><span class="sxs-lookup"><span data-stu-id="5cbcc-133">The inference process will produce a table named **Element1** with two columns, **ChildElement1** and **ChildElement2**.</span></span> <span data-ttu-id="5cbcc-134">**ColumnMapping** 두 열 모두의 속성으로 설정 됩니다 **MappingType.Element**합니다.</span><span class="sxs-lookup"><span data-stu-id="5cbcc-134">The **ColumnMapping** property of both columns will be set to **MappingType.Element**.</span></span>  
  
 <span data-ttu-id="5cbcc-135">**데이터 집합:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="5cbcc-135">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="5cbcc-136">**Table:** Element1</span><span class="sxs-lookup"><span data-stu-id="5cbcc-136">**Table:** Element1</span></span>  
  
|<span data-ttu-id="5cbcc-137">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="5cbcc-137">ChildElement1</span></span>|<span data-ttu-id="5cbcc-138">ChildElement2</span><span class="sxs-lookup"><span data-stu-id="5cbcc-138">ChildElement2</span></span>|  
|-------------------|-------------------|  
|<span data-ttu-id="5cbcc-139">Text1</span><span class="sxs-lookup"><span data-stu-id="5cbcc-139">Text1</span></span>|<span data-ttu-id="5cbcc-140">Text2</span><span class="sxs-lookup"><span data-stu-id="5cbcc-140">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5cbcc-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5cbcc-141">See Also</span></span>  
 [<span data-ttu-id="5cbcc-142">XML에서 데이터 집합 관계형 구조 유추</span><span class="sxs-lookup"><span data-stu-id="5cbcc-142">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [<span data-ttu-id="5cbcc-143">XML에서 데이터 집합 로드</span><span class="sxs-lookup"><span data-stu-id="5cbcc-143">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [<span data-ttu-id="5cbcc-144">XML에서 데이터 집합 스키마 정보 로드</span><span class="sxs-lookup"><span data-stu-id="5cbcc-144">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [<span data-ttu-id="5cbcc-145">데이터 집합에서 XML 사용</span><span class="sxs-lookup"><span data-stu-id="5cbcc-145">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [<span data-ttu-id="5cbcc-146">DataSet, DataTable 및 DataView</span><span class="sxs-lookup"><span data-stu-id="5cbcc-146">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="5cbcc-147">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="5cbcc-147">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
