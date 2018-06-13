---
title: 데이터 집합 제약 조건에 keyref XSD(XML 스키마) 제약 조건 매핑
ms.date: 03/30/2017
ms.assetid: 5b634fea-cc1e-4f6b-9454-10858105b1c8
ms.openlocfilehash: a3a5033292db2b47e7a9811e36c0a4af016951fc
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32758557"
---
# <a name="map-keyref-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="0871a-102">데이터 집합 제약 조건에 keyref XSD(XML 스키마) 제약 조건 매핑</span><span class="sxs-lookup"><span data-stu-id="0871a-102">Map keyref XML Schema (XSD) Constraints to DataSet Constraints</span></span>
<span data-ttu-id="0871a-103">**keyref** 요소는 문서 내의 요소 간에 링크를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0871a-103">The **keyref** element allows you to establish links between elements within a document.</span></span> <span data-ttu-id="0871a-104">이 링크는 관계형 데이터베이스의 외래 키 관계와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="0871a-104">This is similar to a foreign key relationship in a relational database.</span></span> <span data-ttu-id="0871a-105">스키마를 지정 하는 경우는 **keyref** 요소가 요소는 해당 외래 키 제약 조건 테이블의 열에 스키마 매핑 프로세스 중에 변환 됩니다는 <xref:System.Data.DataSet>합니다.</span><span class="sxs-lookup"><span data-stu-id="0871a-105">If a schema specifies the **keyref** element, the element is converted during the schema mapping process to a corresponding foreign key constraint on the columns in the tables of the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="0871a-106">기본적으로는 **keyref** 요소와는 관계 생성의 **ParentTable**, **ChildTable**, **ParentColumn**, 및  **ChildColumn** 해당 관계에 지정 된 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="0871a-106">By default, the **keyref** element also generates a relation, with the **ParentTable**, **ChildTable**, **ParentColumn**, and **ChildColumn** properties specified on the relation.</span></span>  
  
 <span data-ttu-id="0871a-107">다음 표에서 윤곽선은 **msdata** 특성에 지정할 수 있습니다는 **keyref** 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="0871a-107">The following table outlines the **msdata** attributes you can specify in the **keyref** element.</span></span>  
  
|<span data-ttu-id="0871a-108">특성 이름</span><span class="sxs-lookup"><span data-stu-id="0871a-108">Attribute name</span></span>|<span data-ttu-id="0871a-109">설명</span><span class="sxs-lookup"><span data-stu-id="0871a-109">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="0871a-110">**msdata:ConstraintOnly**</span><span class="sxs-lookup"><span data-stu-id="0871a-110">**msdata:ConstraintOnly**</span></span>|<span data-ttu-id="0871a-111">경우 **ConstraintOnly = "true"** 에 지정 된 **keyref** 스키마의 요소를 한 제약 조건을 만들어지지만 관계는 만들어지지입니다.</span><span class="sxs-lookup"><span data-stu-id="0871a-111">If **ConstraintOnly="true"** is specified on the **keyref** element in the schema, a constraint is created, but no relation is created.</span></span> <span data-ttu-id="0871a-112">이 특성이 지정 되지 않은 경우 (또는로 설정 되어 **False**)에 제약 조건과 관계가 모두 만들어집니다는 **데이터 집합**합니다.</span><span class="sxs-lookup"><span data-stu-id="0871a-112">If this attribute is not specified (or is set to **False**), both the constraint and the relation are created in the **DataSet**.</span></span>|  
|<span data-ttu-id="0871a-113">**msdata:ConstraintName**</span><span class="sxs-lookup"><span data-stu-id="0871a-113">**msdata:ConstraintName**</span></span>|<span data-ttu-id="0871a-114">경우는 **ConstraintName** 특성을 지정 하면 해당 값 제약 조건 이름으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0871a-114">If the **ConstraintName** attribute is specified, its value is used as the name of the constraint.</span></span> <span data-ttu-id="0871a-115">그렇지 않은 경우는 **이름** 특성에는 **keyref** 스키마의 요소에서의 제약 조건 이름을 제공는 **데이터 집합**합니다.</span><span class="sxs-lookup"><span data-stu-id="0871a-115">Otherwise, the **name** attribute of the **keyref** element in the schema provides the constraint name in the **DataSet**.</span></span>|  
|<span data-ttu-id="0871a-116">**msdata:UpdateRule**</span><span class="sxs-lookup"><span data-stu-id="0871a-116">**msdata:UpdateRule**</span></span>|<span data-ttu-id="0871a-117">경우는 **UpdateRule** 특성에 지정 된는 **keyref** 스키마의 요소를 해당 값이 할당 된 **UpdateRule** 제약 조건 속성에는  **데이터 집합**합니다.</span><span class="sxs-lookup"><span data-stu-id="0871a-117">If the **UpdateRule** attribute is specified in the **keyref** element in the schema, its value is assigned to the **UpdateRule** constraint property in the **DataSet**.</span></span> <span data-ttu-id="0871a-118">그렇지 않은 경우는 **UpdateRule** 속성이 **Cascade**합니다.</span><span class="sxs-lookup"><span data-stu-id="0871a-118">Otherwise the **UpdateRule** property is set to **Cascade**.</span></span>|  
|<span data-ttu-id="0871a-119">**msdata:DeleteRule**</span><span class="sxs-lookup"><span data-stu-id="0871a-119">**msdata:DeleteRule**</span></span>|<span data-ttu-id="0871a-120">경우는 **DeleteRule** 특성에 지정 된는 **keyref** 스키마의 요소를 해당 값이 할당 된 **DeleteRule** 제약 조건 속성에는  **데이터 집합**합니다.</span><span class="sxs-lookup"><span data-stu-id="0871a-120">If the **DeleteRule** attribute is specified in the **keyref** element in the schema, its value is assigned to the **DeleteRule** constraint property in the **DataSet**.</span></span> <span data-ttu-id="0871a-121">그렇지 않은 경우는 **DeleteRule** 속성이 **Cascade**합니다.</span><span class="sxs-lookup"><span data-stu-id="0871a-121">Otherwise the **DeleteRule** property is set to **Cascade**.</span></span>|  
|<span data-ttu-id="0871a-122">**msdata:AcceptRejectRule**</span><span class="sxs-lookup"><span data-stu-id="0871a-122">**msdata:AcceptRejectRule**</span></span>|<span data-ttu-id="0871a-123">경우는 **AcceptRejectRule** 특성에 지정 된는 **keyref** 스키마의 요소를 해당 값이 할당 된 **AcceptRejectRule** 제약 조건 속성에는  **데이터 집합**합니다.</span><span class="sxs-lookup"><span data-stu-id="0871a-123">If the **AcceptRejectRule** attribute is specified in the **keyref** element in the schema, its value is assigned to the **AcceptRejectRule** constraint property in the **DataSet**.</span></span> <span data-ttu-id="0871a-124">그렇지 않은 경우는 **AcceptRejectRule** 속성이 **None**합니다.</span><span class="sxs-lookup"><span data-stu-id="0871a-124">Otherwise the **AcceptRejectRule** property is set to **None**.</span></span>|  
  
 <span data-ttu-id="0871a-125">다음 예제에 지정 하는 스키마는 **키** 및 **keyref** 간의 관계는 **OrderNumber** 의 자식 요소는 **순서**  요소 및 **OrderNo** 의 자식 요소는 **OrderDetail** 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="0871a-125">The following example contains a schema that specifies the **key** and **keyref** relationships between the **OrderNumber** child element of the **Order** element and the **OrderNo** child element of the **OrderDetail** element.</span></span>  
  
 <span data-ttu-id="0871a-126">예제에서는 **OrderNumber** 의 자식 요소는 **OrderDetail** 요소를 참조는 **OrderNo** 의 키 자식 요소는 **순서**요소입니다.</span><span class="sxs-lookup"><span data-stu-id="0871a-126">In the example, the **OrderNumber** child element of the **OrderDetail** element refers to the **OrderNo** key child element of the **Order** element.</span></span>  
  
```xml  
<xs:schema id="MyDataSet" xmlns=""   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  
 <xs:element name="MyDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
      <xs:element name="OrderDetail">  
       <xs:complexType>  
         <xs:sequence>  
           <xs:element name="OrderNo" type="xs:integer" />  
           <xs:element name="ItemNo" type="xs:string" />  
         </xs:sequence>  
       </xs:complexType>  
      </xs:element>  
      <xs:element name="Order">  
        <xs:complexType>  
          <xs:sequence>  
            <xs:element name="OrderNumber" type="xs:integer" />  
            <xs:element name="EmpNumber" type="xs:integer" />  
          </xs:sequence>  
        </xs:complexType>  
      </xs:element>  
    </xs:choice>  
  </xs:complexType>  
  
  <xs:key name="OrderNumberKey"  >  
    <xs:selector xpath=".//Order" />  
    <xs:field xpath="OrderNumber" />  
  </xs:key>  
  
  <xs:keyref name="OrderNoRef" refer="OrderNumberKey">  
    <xs:selector xpath=".//OrderDetail" />  
    <xs:field xpath="OrderNo" />  
  </xs:keyref>  
 </xs:element>  
</xs:schema>  
```  
  
 <span data-ttu-id="0871a-127">다음을 생성 하는 XML 스키마 정의 언어 (XSD) 스키마 매핑 프로세스 **DataSet** 두 테이블이 포함 된:</span><span class="sxs-lookup"><span data-stu-id="0871a-127">The XML Schema definition language (XSD) schema mapping process produces the following **DataSet** with two tables:</span></span>  
  
```  
OrderDetail(OrderNo, ItemNo) and  
Order(OrderNumber, EmpNumber)  
```  
  
 <span data-ttu-id="0871a-128">또한는 **DataSet** 다음과 같은 제약 조건을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="0871a-128">In addition, the **DataSet** defines the following constraints:</span></span>  
  
-   <span data-ttu-id="0871a-129">에 unique 제약 조건을 **순서** 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="0871a-129">A unique constraint on the **Order** table.</span></span>  
  
    ```  
              Table: Order  
    Columns: OrderNumber   
    ConstraintName: OrderNumberKey  
    Type: UniqueConstraint  
    IsPrimaryKey: False  
    ```  
  
-   <span data-ttu-id="0871a-130">간의 관계는 **순서** 및 **OrderDetail** 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="0871a-130">A relationship between the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="0871a-131">**Nested** 속성이 **False** 두 요소가 스키마에서 중첩 되지 않은 때문에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0871a-131">The **Nested** property is set to **False** because the two elements are not nested in the schema.</span></span>  
  
    ```  
              ParentTable: Order  
    ParentColumns: OrderNumber   
    ChildTable: OrderDetail  
    ChildColumns: OrderNo   
    ParentKeyConstraint: OrderNumberKey  
    ChildKeyConstraint: OrderNoRef  
    RelationName: OrderNoRef  
    Nested: False  
    ```  
  
-   <span data-ttu-id="0871a-132">외래 키 제약 조건을 **OrderDetail** 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="0871a-132">A foreign key constraint on the **OrderDetail** table.</span></span>  
  
    ```  
              ConstraintName: OrderNoRef  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: OrderNo   
    RelatedTable: Order  
    RelatedColumns: OrderNumber   
    ```  
  
## <a name="see-also"></a><span data-ttu-id="0871a-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0871a-133">See Also</span></span>  
 [<span data-ttu-id="0871a-134">데이터 집합 제약 조건에 XSD(XML 스키마) 제약 조건 매핑</span><span class="sxs-lookup"><span data-stu-id="0871a-134">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 [<span data-ttu-id="0871a-135">XSD(XML 스키마)에서 데이터 집합 관계 생성</span><span class="sxs-lookup"><span data-stu-id="0871a-135">Generating DataSet Relations from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 [<span data-ttu-id="0871a-136">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="0871a-136">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
