---
title: 데이터 집합 스키마 유추 프로세스 요약
ms.date: 03/30/2017
ms.assetid: fd0891c8-d068-4e30-a76f-7c375f078bf7
ms.openlocfilehash: 9bcc5ce1574eed60d2ef1aa35bdafe8c6050e44c
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="summary-of-the-dataset-schema-inference-process"></a><span data-ttu-id="5ee67-102">데이터 집합 스키마 유추 프로세스 요약</span><span class="sxs-lookup"><span data-stu-id="5ee67-102">Summary of the DataSet Schema Inference Process</span></span>
<span data-ttu-id="5ee67-103">유추 과정에서는 우선 XML 문서에서 테이블로 유추될 요소를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="5ee67-103">The inference process first determines, from the XML document, which elements will be inferred as tables.</span></span> <span data-ttu-id="5ee67-104">그런 다음 남아 있는 XML에서 해당 테이블의 열을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="5ee67-104">From the remaining XML, the inference process determines the columns for those tables.</span></span> <span data-ttu-id="5ee67-105">중첩된 테이블인 경우에는 유추 과정에서 중첩된 <xref:System.Data.DataRelation> 및 <xref:System.Data.ForeignKeyConstraint> 개체를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="5ee67-105">For nested tables, the inference process generates nested <xref:System.Data.DataRelation> and <xref:System.Data.ForeignKeyConstraint> objects.</span></span>  
  
 <span data-ttu-id="5ee67-106">다음은 유추 규칙에 대해 간략히 요약한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5ee67-106">Following is a brief summary of inference rules:</span></span>  
  
-   <span data-ttu-id="5ee67-107">특성이 있는 요소는 테이블로 유추됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ee67-107">Elements that have attributes are inferred as tables.</span></span>  
  
-   <span data-ttu-id="5ee67-108">자식 요소가 있는 요소는 테이블로 유추됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ee67-108">Elements that have child elements are inferred as tables.</span></span>  
  
-   <span data-ttu-id="5ee67-109">반복되는 요소는 하나의 테이블로 유추됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ee67-109">Elements that repeat are inferred as a single table.</span></span>  
  
-   <span data-ttu-id="5ee67-110">문서 요소에 열로 유추되는 특성이나 자식 요소가 없으면 문서 요소 또는 루트 요소는 <xref:System.Data.DataSet>으로 유추됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ee67-110">If the document, or root, element has no attributes, and no child elements that would be inferred as columns, it is inferred as a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="5ee67-111">그렇지 않으면 문서 요소는 테이블로 유추됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ee67-111">Otherwise, the document element is inferred as a table.</span></span>  
  
-   <span data-ttu-id="5ee67-112">특성은 열로 유추됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ee67-112">Attributes are inferred as columns.</span></span>  
  
-   <span data-ttu-id="5ee67-113">특성이나 자식 요소가 없거나 반복되지 않는 요소는 열로 유추됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ee67-113">Elements that have no attributes or child elements, and that do not repeat, are inferred as columns.</span></span>  
  
-   <span data-ttu-id="5ee67-114">유추 되는 다른 요소 내에 중첩 된 테이블로 유추 되 테이블로 중첩 된 **DataRelation** 두 테이블 사이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="5ee67-114">For elements that are inferred as nested tables within other elements that are also inferred as tables, a nested **DataRelation** is created between the two tables.</span></span> <span data-ttu-id="5ee67-115">라는 새 기본 키 열 **TableName_Id** 두 테이블에 추가 되 고에서 사용 되는 **DataRelation**합니다.</span><span class="sxs-lookup"><span data-stu-id="5ee67-115">A new, primary key column named **TableName_Id** is added to both tables and used by the **DataRelation**.</span></span> <span data-ttu-id="5ee67-116">A **ForeignKeyConstraint** 를 사용 하 여 두 테이블 간에 만들어집니다는 **TableName_Id** 열입니다.</span><span class="sxs-lookup"><span data-stu-id="5ee67-116">A **ForeignKeyConstraint** is created between the two tables using the **TableName_Id** column.</span></span>  
  
-   <span data-ttu-id="5ee67-117">테이블로 유추 되 고 텍스트를 포함 하지만 자식 요소가 없는 요소에 대해 새 열 이라는 **TableName_Text** 텍스트의 각 요소에 대해 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ee67-117">For elements that are inferred as tables and that contain text but have no child elements, a new column named **TableName_Text** is created for the text of each of the elements.</span></span> <span data-ttu-id="5ee67-118">테이블로 유추되는 요소에 텍스트와 자식 요소가 모두 있으면 해당 텍스트는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ee67-118">If an element is inferred as a table and has text, but also has child elements, the text is ignored.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ee67-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5ee67-119">See Also</span></span>  
 [<span data-ttu-id="5ee67-120">XML에서 데이터 집합 관계형 구조 유추</span><span class="sxs-lookup"><span data-stu-id="5ee67-120">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [<span data-ttu-id="5ee67-121">XML에서 데이터 집합 로드</span><span class="sxs-lookup"><span data-stu-id="5ee67-121">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [<span data-ttu-id="5ee67-122">XML에서 데이터 집합 스키마 정보 로드</span><span class="sxs-lookup"><span data-stu-id="5ee67-122">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [<span data-ttu-id="5ee67-123">데이터 집합에서 XML 사용</span><span class="sxs-lookup"><span data-stu-id="5ee67-123">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [<span data-ttu-id="5ee67-124">DataSet, DataTable 및 DataView</span><span class="sxs-lookup"><span data-stu-id="5ee67-124">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="5ee67-125">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="5ee67-125">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
