---
title: 데이터 집합 제약 조건에 고유 XSD(XML 스키마) 제약 조건 매핑
ms.date: 03/30/2017
ms.assetid: 56da90bf-21d3-4d1a-8bb8-de908866b78d
ms.openlocfilehash: 8aed9830d613eeb7d49d2339a8ac1892c0e28e93
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32761170"
---
# <a name="map-unique-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="0a5f2-102">데이터 집합 제약 조건에 고유 XSD(XML 스키마) 제약 조건 매핑</span><span class="sxs-lookup"><span data-stu-id="0a5f2-102">Map unique XML Schema (XSD) Constraints to DataSet Constraints</span></span>
<span data-ttu-id="0a5f2-103">XML 스키마 정의 언어 (XSD) 스키마에는 **고유** 요소는 요소나 특성에 고유성 제약 조건을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a5f2-103">In an XML Schema definition language (XSD) schema, the **unique** element specifies the uniqueness constraint on an element or attribute.</span></span> <span data-ttu-id="0a5f2-104">XML 스키마를 관계형 스키마로 변환하는 과정에서, XML 스키마의 요소나 특성에 지정된 UNIQUE 제약 조건은 생성된 해당 <xref:System.Data.DataTable>에 있는 <xref:System.Data.DataSet>의 UNIQUE 제약 조건에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a5f2-104">In the process of translating an XML Schema into a relational schema, the unique constraint specified on an element or attribute in the XML Schema is mapped to a unique constraint in the <xref:System.Data.DataTable> in the corresponding <xref:System.Data.DataSet> that is generated.</span></span>  
  
 <span data-ttu-id="0a5f2-105">다음 표에서 윤곽선은 **msdata** 에서 지정할 수 있는 특성의 **고유** 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="0a5f2-105">The following table outlines the **msdata** attributes that you can specify in the **unique** element.</span></span>  
  
|<span data-ttu-id="0a5f2-106">특성 이름</span><span class="sxs-lookup"><span data-stu-id="0a5f2-106">Attribute name</span></span>|<span data-ttu-id="0a5f2-107">설명</span><span class="sxs-lookup"><span data-stu-id="0a5f2-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="0a5f2-108">**msdata:ConstraintName**</span><span class="sxs-lookup"><span data-stu-id="0a5f2-108">**msdata:ConstraintName**</span></span>|<span data-ttu-id="0a5f2-109">이 특성을 지정하면 해당 값이 제약 조건 이름으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a5f2-109">If this attribute is specified, its value is used as the constraint name.</span></span> <span data-ttu-id="0a5f2-110">그렇지 않은 경우는 **이름** 특성에서 제약 조건 이름의 값을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a5f2-110">Otherwise, the **name** attribute provides the value of the constraint name.</span></span>|  
|<span data-ttu-id="0a5f2-111">**msdata:PrimaryKey**</span><span class="sxs-lookup"><span data-stu-id="0a5f2-111">**msdata:PrimaryKey**</span></span>|<span data-ttu-id="0a5f2-112">경우 `PrimaryKey="true"` 에 **고유** , unique 제약 조건을 사용 요소가 만들어집니다는 **IsPrimaryKey** 속성이로 설정 **true**합니다.</span><span class="sxs-lookup"><span data-stu-id="0a5f2-112">If `PrimaryKey="true"` is present in the **unique** element, a unique constraint is created with the **IsPrimaryKey** property set to **true**.</span></span>|  
  
 <span data-ttu-id="0a5f2-113">다음 예제에서는 사용 하는 XML 스키마는 **고유** 고유성 제약 조건을 지정 하는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="0a5f2-113">The following example shows an XML Schema that uses the **unique** element to specify a uniqueness constraint.</span></span>  
  
```xml  
<xs:schema id="SampleDataSet"   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  <xs:element name="Customers">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="CustomerID" type="xs:integer"   
           minOccurs="0"/>  
        <xs:element name="CompanyName" type="xs:string"   
           minOccurs="0"/>  
       <xs:element name="Phone" type="xs:string" />  
     </xs:sequence>  
   </xs:complexType>  
 </xs:element>  
  
 <xs:element name="SampleDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
      <xs:element ref="Customers" />  
    </xs:choice>  
  </xs:complexType>  
   <xs:unique     msdata:ConstraintName="UCustID"     name="UniqueCustIDConstr" >       <xs:selector xpath=".//Customers" />       <xs:field xpath="CustomerID" />     </xs:unique>  
</xs:element>  
</xs:schema>  
```  
  
 <span data-ttu-id="0a5f2-114">**고유** 스키마 요소에에서 지정 하는 모든 **고객** 인스턴스 문서에서 요소를 값은 **CustomerID** 자식 요소가 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a5f2-114">The **unique** element in the schema specifies that for all **Customers** elements in a document instance, the value of the **CustomerID** child element must be unique.</span></span> <span data-ttu-id="0a5f2-115">건물 안에 **DataSet**, 매핑 프로세스에서는이 스키마를 읽고 다음 테이블을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a5f2-115">In building the **DataSet**, the mapping process reads this schema and generates the following table:</span></span>  
  
```  
Customers (CustomerID, CompanyName, Phone)  
```  
  
 <span data-ttu-id="0a5f2-116">매핑 프로세스에서 unique 제약 조건을 만듭니다는 **CustomerID** 열에서 다음에 표시 된 대로 **DataSet**합니다.</span><span class="sxs-lookup"><span data-stu-id="0a5f2-116">The mapping process also creates a unique constraint on the **CustomerID** column, as shown in the following **DataSet**.</span></span> <span data-ttu-id="0a5f2-117">여기에서는 편의를 위해 관련 속성만 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0a5f2-117">(For simplicity, only relevant properties are shown.)</span></span>  
  
```  
      DataSetName: MyDataSet  
TableName: Customers  
  ColumnName: CustomerID  
      AllowDBNull: True  
      Unique: True  
  ConstraintName: UcustID       Type: UniqueConstraint  
      Table: Customers  
      Columns: CustomerID   
      IsPrimaryKey: False  
```  
  
 <span data-ttu-id="0a5f2-118">에 **데이터 집합** 생성 하는 **IsPrimaryKey** 속성이 **False** unique 제약 조건에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a5f2-118">In the **DataSet** that is generated, the **IsPrimaryKey** property is set to **False** for the unique constraint.</span></span> <span data-ttu-id="0a5f2-119">**고유** 나타내는 속성에는 **CustomerID** 열 값은 고유 해야 합니다. (에 지정 된 대로 null 참조일 수 있습니다 하지만 **AllowDBNull** 열 속성)입니다.</span><span class="sxs-lookup"><span data-stu-id="0a5f2-119">The **unique** property on the column indicates that the **CustomerID** column values must be unique (but they can be a null reference, as specified by the **AllowDBNull** property of the column).</span></span>  
  
 <span data-ttu-id="0a5f2-120">스키마를 수정 하 고 선택 사항인 경우 **msdata: primarykey** 특성 값을 **True**, 테이블에 unique 제약 조건이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="0a5f2-120">If you modify the schema and set the optional **msdata:PrimaryKey** attribute value to **True**, the unique constraint is created on the table.</span></span> <span data-ttu-id="0a5f2-121">**AllowDBNull** 열 속성이로 설정 되어 **False**, 및 **IsPrimaryKey** 속성으로 설정 하는 제약 조건의 **True**되므로, **CustomerID** 열 기본 키 열입니다.</span><span class="sxs-lookup"><span data-stu-id="0a5f2-121">The **AllowDBNull** column property is set to **False**, and the **IsPrimaryKey** property of the constraint set to **True**, thus making the **CustomerID** column a primary key column.</span></span>  
  
 <span data-ttu-id="0a5f2-122">XML 스키마의 요소나 특성의 조합에 UNIQUE 제약 조건을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a5f2-122">You can specify a unique constraint on a combination of elements or attributes in the XML Schema.</span></span> <span data-ttu-id="0a5f2-123">다음 예제에서는의 조합을 지정 하는 방법을 보여 줍니다 **CustomerID** 및 **CompanyName** 값 모두에 대해 고유 해야 합니다. **고객** 모든 인스턴스에서 하 여 다른 추가 **xs:field** 스키마의 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="0a5f2-123">The following example demonstrates how to specify that a combination of **CustomerID** and **CompanyName** values must be unique for all **Customers** in any instance, by adding another **xs:field** element in the schema.</span></span>  
  
```xml  
      <xs:unique     
         msdata:ConstraintName="SomeName"    
         name="UniqueCustIDConstr" >   
  <xs:selector xpath=".//Customers" />   
  <xs:field xpath="CustomerID" />   
  <xs:field xpath="CompanyName" />   
</xs:unique>  
```  
  
 <span data-ttu-id="0a5f2-124">이 결과에서 생성 된 제약 조건 **DataSet**합니다.</span><span class="sxs-lookup"><span data-stu-id="0a5f2-124">This is the constraint that is created in the resulting **DataSet**.</span></span>  
  
```  
ConstraintName: SomeName  
  Table: Customers  
  Columns: CustomerID CompanyName   
  IsPrimaryKey: False  
```  
  
## <a name="see-also"></a><span data-ttu-id="0a5f2-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0a5f2-125">See Also</span></span>  
 [<span data-ttu-id="0a5f2-126">데이터 집합 제약 조건에 XSD(XML 스키마) 제약 조건 매핑</span><span class="sxs-lookup"><span data-stu-id="0a5f2-126">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 [<span data-ttu-id="0a5f2-127">XSD(XML 스키마)에서 데이터 집합 관계 생성</span><span class="sxs-lookup"><span data-stu-id="0a5f2-127">Generating DataSet Relations from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 [<span data-ttu-id="0a5f2-128">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="0a5f2-128">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
