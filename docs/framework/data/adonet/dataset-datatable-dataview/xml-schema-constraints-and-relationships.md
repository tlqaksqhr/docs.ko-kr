---
title: XML 스키마 제약 조건 및 관계
ms.date: 03/30/2017
ms.assetid: 165bc2bc-60a1-40e0-9b89-7c68ef979079
ms.openlocfilehash: 4b62b6bafa9ceeafd250e722314c4bd6c594bf82
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32759844"
---
# <a name="xml-schema-constraints-and-relationships"></a><span data-ttu-id="9af72-102">XML 스키마 제약 조건 및 관계</span><span class="sxs-lookup"><span data-stu-id="9af72-102">XML Schema Constraints and Relationships</span></span>
<span data-ttu-id="9af72-103">XML 스키마 정의 언어 (XSD) 스키마에서 제약 조건을 지정할 수 있습니다 (고유, key 및 keyref 제약 조건) 및 관계 (사용 하는 **msdata: relationship** 주석).</span><span class="sxs-lookup"><span data-stu-id="9af72-103">In an XML Schema definition language (XSD) schema, you can specify constraints (unique, key, and keyref constraints) and relationships (using the **msdata:Relationship** annotation).</span></span> <span data-ttu-id="9af72-104">이 항목에서는 XML 스키마에 지정된 제약 조건과 관계를 해석하여 <xref:System.Data.DataSet>을 생성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9af72-104">This topic explains how the constraints and relationships specified in an XML Schema are interpreted to generate the <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="9af72-105">에 일반적으로 XML 스키마에서 지정 된 **msdata: relationship** 주석에서 관계만 생성 하려는 경우는 **데이터 집합**합니다.</span><span class="sxs-lookup"><span data-stu-id="9af72-105">In general, in an XML Schema, you specify the **msdata:Relationship** annotation if you want to generate only relationships in the **DataSet**.</span></span> <span data-ttu-id="9af72-106">자세한 내용은 참조 [에서 XSD (XML 스키마) 데이터 집합 관계 생성](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9af72-106">For more information, see [Generating DataSet Relations from XML Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md).</span></span> <span data-ttu-id="9af72-107">제약 조건을 지정 (고유, key 및 keyref 등)에서 제약 조건을 생성 하려는 경우는 **DataSet**합니다.</span><span class="sxs-lookup"><span data-stu-id="9af72-107">You specify constraints (unique, key, and keyref) if you want to generate constraints in the **DataSet**.</span></span> <span data-ttu-id="9af72-108">이 항목의 뒷부분에서 설명하겠지만 KEY 및 KEYREF 제약 조건도 관계를 생성하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9af72-108">Note that the key and keyref constraints are also used to generate relationships, as explained later in this topic.</span></span>  
  
## <a name="generating-a-relationship-from-key-and-keyref-constraints"></a><span data-ttu-id="9af72-109">KEY 및 KEYREF 제약 조건에서 관계 생성</span><span class="sxs-lookup"><span data-stu-id="9af72-109">Generating a Relationship from key and keyref Constraints</span></span>  
 <span data-ttu-id="9af72-110">지정 하는 대신는 **msdata: relationship** 주석, XML 스키마 매핑 프로세스 중에 제약조건뿐만아니라관계를생성하는데사용되는key및keyref제약조건을지정할수있습니다 **데이터 집합**합니다.</span><span class="sxs-lookup"><span data-stu-id="9af72-110">Instead of specifying the **msdata:Relationship** annotation, you can specify key and keyref constraints, which are used during the XML Schema mapping process to generate not only the constraints but also the relationship in the **DataSet**.</span></span> <span data-ttu-id="9af72-111">그러나 지정 하는 경우 `msdata:ConstraintOnly="true"` 에 **keyref** 요소는 **데이터 집합** 제약 조건만 포함 하며 관계를 포함 하지 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9af72-111">However, if you specify `msdata:ConstraintOnly="true"` in the **keyref** element, the **DataSet** will include only the constraints and will not include the relationship.</span></span>  
  
 <span data-ttu-id="9af72-112">다음 예제에서는 포함 된 XML 스키마 **순서** 및 **OrderDetail** 중첩 되지 않은 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="9af72-112">The following example shows an XML Schema that includes **Order** and **OrderDetail** elements, which are not nested.</span></span> <span data-ttu-id="9af72-113">스키마에서는 KEY 및 KEYREF 제약 조건도 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9af72-113">The schema also specifies key and keyref constraints.</span></span>  
  
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
  
 <span data-ttu-id="9af72-114">**DataSet** XML 스키마 매핑 프로세스를 포함 하는 동안 생성 된는 **순서** 및 **OrderDetail** 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="9af72-114">The **DataSet** that is generated during the XML Schema mapping process includes the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="9af72-115">또한는 **DataSet** 관계 및 제약 조건을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="9af72-115">In addition, the **DataSet** includes relationships and constraints.</span></span> <span data-ttu-id="9af72-116">다음 예제에서는 이러한 관계와 제약 조건을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9af72-116">The following example shows these relationships and constraints.</span></span> <span data-ttu-id="9af72-117">스키마를 지정 하지 않는 참고는 **msdata: relationship** 주석; 관계를 생성 하는 key 및 keyref 제약 조건 대신 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9af72-117">Note that the schema does not specify the **msdata:Relationship** annotation; instead, the key and keyref constraints are used to generate the relation.</span></span>  
  
```  
....ConstraintName: OrderNumberKey  
....Type: UniqueConstraint  
....Table: Order  
....Columns: OrderNumber  
....IsPrimaryKey: False  
  
....ConstraintName: OrderNoRef  
....Type: ForeignKeyConstraint  
....Table: OrderDetail  
....Columns: OrderNo  
....RelatedTable: Order  
....RelatedColumns: OrderNumber  
  
..RelationName: OrderNoRef  
..ParentTable: Order  
..ParentColumns: OrderNumber  
..ChildTable: OrderDetail  
..ChildColumns: OrderNo  
..ParentKeyConstraint: OrderNumberKey  
..ChildKeyConstraint: OrderNoRef  
..Nested: False  
```  
  
 <span data-ttu-id="9af72-118">이전 스키마 예제에서는 **순서** 및 **OrderDetail** 요소가 중첩 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9af72-118">In the previous schema example, the **Order** and **OrderDetail** elements are not nested.</span></span> <span data-ttu-id="9af72-119">다음 스키마 예제에서는 이들 요소가 중첩됩니다.</span><span class="sxs-lookup"><span data-stu-id="9af72-119">In the following schema example, these elements are nested.</span></span> <span data-ttu-id="9af72-120">그러나 없습니다 **msdata: relationship** 에 주석이 지정 됩니다. 따라서 암시적 관계가 가정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9af72-120">However, no **msdata:Relationship** annotation is specified; therefore, an implicit relation is assumed.</span></span> <span data-ttu-id="9af72-121">자세한 내용은 참조 [지도 암시적 관계 사이 중첩 된 스키마 요소](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-implicit-relations-between-nested-schema-elements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9af72-121">For more information, see [Map Implicit Relations Between Nested Schema Elements](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-implicit-relations-between-nested-schema-elements.md).</span></span> <span data-ttu-id="9af72-122">스키마에서는 KEY 및 KEYREF 제약 조건도 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9af72-122">The schema also specifies key and keyref constraints.</span></span>  
  
```xml  
<xs:schema id="MyDataSet" xmlns=""   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  
 <xs:element name="MyDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
  
      <xs:element name="Order">  
        <xs:complexType>  
          <xs:sequence>  
            <xs:element name="OrderNumber" type="xs:integer" />  
            <xs:element name="EmpNumber" type="xs:integer" />  
  
            <xs:element name="OrderDetail">  
              <xs:complexType>  
                <xs:sequence>  
                  <xs:element name="OrderNo" type="xs:integer" />  
                  <xs:element name="ItemNo" type="xs:string" />  
                </xs:sequence>  
              </xs:complexType>  
            </xs:element>  
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
  
 <span data-ttu-id="9af72-123">**DataSet** 두 테이블이 포함 된 XML 스키마 매핑 프로세스에서 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="9af72-123">The **DataSet** resulting from the XML Schema mapping process includes two tables:</span></span>  
  
```  
Order(OrderNumber, EmpNumber, Order_Id)  
OrderDetail(OrderNumber, ItemNumber, Order_Id)  
```  
  
 <span data-ttu-id="9af72-124">**데이터 집합** 도 두 개의 관계가 포함 됩니다 (에 따라 하나는 **msdata: relationship** 주석 및 다른 key 및 keyref 제약 조건에 따라) 및 다양 한 제약 조건입니다.</span><span class="sxs-lookup"><span data-stu-id="9af72-124">The **DataSet** also includes the two relationships (one based on the **msdata:relationship** annotation and the other based on the key and keyref constraints) and various constraints.</span></span> <span data-ttu-id="9af72-125">다음 예제에서는 이러한 관계와 제약 조건을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9af72-125">The following example shows the relations and constraints.</span></span>  
  
```  
..RelationName: Order_OrderDetail  
..ParentTable: Order  
..ParentColumns: Order_Id  
..ChildTable: OrderDetail  
..ChildColumns: Order_Id  
..ParentKeyConstraint: Constraint1  
..ChildKeyConstraint: Order_OrderDetail  
..Nested: True  
  
..RelationName: OrderNoRef  
..ParentTable: Order  
..ParentColumns: OrderNumber  
..ChildTable: OrderDetail  
..ChildColumns: OrderNo  
..ParentKeyConstraint: OrderNumberKey  
..ChildKeyConstraint: OrderNoRef  
..Nested: False  
  
..ConstraintName: OrderNumberKey  
..Type: UniqueConstraint  
..Table: Order  
..Columns: OrderNumber  
..IsPrimaryKey: False  
  
..ConstraintName: Constraint1  
..Type: UniqueConstraint  
..Table: Order  
..Columns: Order_Id  
..IsPrimaryKey: True  
  
..ConstraintName: Order_OrderDetail  
..Type: ForeignKeyConstraint  
..Table: OrderDetail  
..Columns: Order_Id  
..RelatedTable: Order  
..RelatedColumns: Order_Id  
  
..ConstraintName: OrderNoRef  
..Type: ForeignKeyConstraint  
..Table: OrderDetail  
..Columns: OrderNo  
..RelatedTable: Order  
..RelatedColumns: OrderNumber  
```  
  
 <span data-ttu-id="9af72-126">중첩된 테이블을 참조 하는 keyref 제약 조건을 포함 하는 경우는 **msdata:IsNested = "true"** 주석을 **데이터 집합** keyref 제약 조건을 기반으로 하는 단일 중첩된 관계 만들어집니다 및 관련된 unique/key 제약 조건입니다.</span><span class="sxs-lookup"><span data-stu-id="9af72-126">If a keyref constraint referring to a nested table contains the **msdata:IsNested="true"** annotation, the **DataSet** will create a single nested relationship that is based on the keyref constraint and the related unique/key constraint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9af72-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9af72-127">See Also</span></span>  
 [<span data-ttu-id="9af72-128">XML 스키마에서 데이터 집합 관계형 구조 파생(XSD)</span><span class="sxs-lookup"><span data-stu-id="9af72-128">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 [<span data-ttu-id="9af72-129">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="9af72-129">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
