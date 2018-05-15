---
title: 요소 텍스트 유추
ms.date: 03/30/2017
ms.assetid: 789799e5-716f-459f-a168-76c5cf22178b
ms.openlocfilehash: b32d8f3f89a16166ffc0e903ef1f63c3b97a249c
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="inferring-element-text"></a><span data-ttu-id="4631e-102">요소 텍스트 유추</span><span class="sxs-lookup"><span data-stu-id="4631e-102">Inferring Element Text</span></span>
<span data-ttu-id="4631e-103">요소 텍스트를 포함 하 고 테이블로 유추 될 (특성이 있는 요소) 또는 반복된 요소와 같은 이름의 새 열에 자식 요소가 없는 경우 **TableName_Text** 요소의 유추 테이블에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4631e-103">If an element contains text and has no child elements to be inferred as tables (such as elements with attributes or repeated elements), a new column with the name **TableName_Text** will be added to the table that is inferred for the element.</span></span> <span data-ttu-id="4631e-104">이 요소에 포함된 텍스트는 테이블의 행에 추가되어 새 열에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="4631e-104">The text contained in the element will be added to a row in the table and stored in the new column.</span></span> <span data-ttu-id="4631e-105">**ColumnMapping** 새 열의 속성이로 설정 됩니다 **MappingType.SimpleContent**합니다.</span><span class="sxs-lookup"><span data-stu-id="4631e-105">The **ColumnMapping** property of the new column will be set to **MappingType.SimpleContent**.</span></span>  
  
 <span data-ttu-id="4631e-106">예를 들어, 다음과 같은 XML을 가정해 봅시다.</span><span class="sxs-lookup"><span data-stu-id="4631e-106">For example, consider the following XML.</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1">Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="4631e-107">위 유추 과정에서 이라는 테이블이 생성 됩니다 **Element1** 열이 두 개: **attr1** 및 **Element1_Text**합니다.</span><span class="sxs-lookup"><span data-stu-id="4631e-107">The inference process will produce a table named **Element1** with two columns: **attr1** and **Element1_Text**.</span></span> <span data-ttu-id="4631e-108">**ColumnMapping** 의 속성은 **attr1** 열으로 설정 됩니다 **MappingType.Attribute**합니다.</span><span class="sxs-lookup"><span data-stu-id="4631e-108">The **ColumnMapping** property of the **attr1** column will be set to **MappingType.Attribute**.</span></span> <span data-ttu-id="4631e-109">**ColumnMapping** 의 속성은 **Element1_Text** 열으로 설정 됩니다 **MappingType.SimpleContent**합니다.</span><span class="sxs-lookup"><span data-stu-id="4631e-109">The **ColumnMapping** property of the **Element1_Text** column will be set to **MappingType.SimpleContent**.</span></span>  
  
 <span data-ttu-id="4631e-110">**데이터 집합:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="4631e-110">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="4631e-111">**Table:** Element1</span><span class="sxs-lookup"><span data-stu-id="4631e-111">**Table:** Element1</span></span>  
  
|<span data-ttu-id="4631e-112">attr1</span><span class="sxs-lookup"><span data-stu-id="4631e-112">attr1</span></span>|<span data-ttu-id="4631e-113">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="4631e-113">Element1_Text</span></span>|  
|-----------|--------------------|  
|<span data-ttu-id="4631e-114">value1</span><span class="sxs-lookup"><span data-stu-id="4631e-114">value1</span></span>|<span data-ttu-id="4631e-115">Text1</span><span class="sxs-lookup"><span data-stu-id="4631e-115">Text1</span></span>|  
  
 <span data-ttu-id="4631e-116">요소에 텍스트뿐만 아니라 텍스트가 포함된 자식 요소도 있는 경우에는 해당 요소에 포함된 텍스트를 저장할 열이 테이블에 추가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4631e-116">If an element contains text, but also has child elements that contain text, a column will not be added to the table to store the text contained in the element.</span></span> <span data-ttu-id="4631e-117">따라서 이 요소에 포함된 텍스트는 무시되지만 자식 요소에 있는 텍스트는 해당 테이블의 행에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="4631e-117">The text contained in the element will be ignored, while the text in the child elements is included in a row in the table.</span></span> <span data-ttu-id="4631e-118">예를 들어, 다음과 같은 XML을 가정해 봅시다.</span><span class="sxs-lookup"><span data-stu-id="4631e-118">For example, consider the following XML.</span></span>  
  
```xml  
<Element1>  
  Text1  
  <ChildElement1>Text2</ChildElement1>  
  Text3  
</Element1>  
```  
  
 <span data-ttu-id="4631e-119">위 유추 과정에서 이라는 테이블이 생성 됩니다 **Element1** 라는 열이 하나인 **ChildElement1**합니다.</span><span class="sxs-lookup"><span data-stu-id="4631e-119">The inference process will produce a table named **Element1** with one column named **ChildElement1**.</span></span> <span data-ttu-id="4631e-120">에 대 한 텍스트는 **ChildElement1** 요소는 테이블의 행에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4631e-120">The text for the **ChildElement1** element will be included in a row in the table.</span></span> <span data-ttu-id="4631e-121">다른 텍스트는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4631e-121">The other text will be ignored.</span></span> <span data-ttu-id="4631e-122">**ColumnMapping** 의 속성은 **ChildElement1** 열으로 설정 됩니다 **MappingType.Element**합니다.</span><span class="sxs-lookup"><span data-stu-id="4631e-122">The **ColumnMapping** property of the **ChildElement1** column will be set to **MappingType.Element**.</span></span>  
  
 <span data-ttu-id="4631e-123">**데이터 집합:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="4631e-123">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="4631e-124">**Table:** Element1</span><span class="sxs-lookup"><span data-stu-id="4631e-124">**Table:** Element1</span></span>  
  
|<span data-ttu-id="4631e-125">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="4631e-125">ChildElement1</span></span>|  
|-------------------|  
|<span data-ttu-id="4631e-126">Text2</span><span class="sxs-lookup"><span data-stu-id="4631e-126">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4631e-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4631e-127">See Also</span></span>  
 [<span data-ttu-id="4631e-128">XML에서 데이터 집합 관계형 구조 유추</span><span class="sxs-lookup"><span data-stu-id="4631e-128">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [<span data-ttu-id="4631e-129">XML에서 데이터 집합 로드</span><span class="sxs-lookup"><span data-stu-id="4631e-129">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [<span data-ttu-id="4631e-130">XML에서 데이터 집합 스키마 정보 로드</span><span class="sxs-lookup"><span data-stu-id="4631e-130">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [<span data-ttu-id="4631e-131">데이터 집합에서 XML 사용</span><span class="sxs-lookup"><span data-stu-id="4631e-131">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [<span data-ttu-id="4631e-132">DataSet, DataTable 및 DataView</span><span class="sxs-lookup"><span data-stu-id="4631e-132">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="4631e-133">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="4631e-133">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
