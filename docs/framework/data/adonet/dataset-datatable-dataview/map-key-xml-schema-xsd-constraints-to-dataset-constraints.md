---
title: 데이터 집합 제약 조건에 키 XSD(XML 스키마) 제약 조건 매핑
ms.date: 03/30/2017
ms.assetid: 22664196-f270-4ebc-a169-70e16a83dfa1
ms.openlocfilehash: ad39fd75a3f8872ed2c24a65481209e3c772a638
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="map-key-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="4628a-102">데이터 집합 제약 조건에 키 XSD(XML 스키마) 제약 조건 매핑</span><span class="sxs-lookup"><span data-stu-id="4628a-102">Map key XML Schema (XSD) Constraints to DataSet Constraints</span></span>
<span data-ttu-id="4628a-103">스키마에서는 요소에 대 한 key 제약 조건을 지정 하거나 사용 하 여 특성 수는 **키** 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="4628a-103">In a schema, you can specify a key constraint on an element or attribute using the **key** element.</span></span> <span data-ttu-id="4628a-104">KEY 제약 조건이 지정된 요소 또는 특성은 모든 스키마 인스턴스에서 고유한 값을 가져야 하며 null 값을 가져서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4628a-104">The element or attribute on which a key constraint is specified must have unique values in any schema instance, and cannot have null values.</span></span>  
  
 <span data-ttu-id="4628a-105">KEY 제약 조건이 정의된 열이 null 값을 가질 수 없다는 것을 제외하면, key 제약 조건은 UNIQUE 제약 조건과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="4628a-105">The key constraint is similar to the unique constraint, except that the column on which a key constraint is defined cannot have null values.</span></span>  
  
 <span data-ttu-id="4628a-106">다음 표에서 윤곽선은 **msdata** 에서 지정할 수 있는 특성의 **키** 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="4628a-106">The following table outlines the **msdata** attributes that you can specify in the **key** element.</span></span>  
  
|<span data-ttu-id="4628a-107">특성 이름</span><span class="sxs-lookup"><span data-stu-id="4628a-107">Attribute name</span></span>|<span data-ttu-id="4628a-108">설명</span><span class="sxs-lookup"><span data-stu-id="4628a-108">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="4628a-109">**msdata:ConstraintName**</span><span class="sxs-lookup"><span data-stu-id="4628a-109">**msdata:ConstraintName**</span></span>|<span data-ttu-id="4628a-110">이 특성을 지정하면 해당 값이 제약 조건 이름으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4628a-110">If this attribute is specified, its value is used as the constraint name.</span></span> <span data-ttu-id="4628a-111">그렇지 않은 경우는 **이름** 특성에서 제약 조건 이름의 값을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4628a-111">Otherwise, the **name** attribute provides the value of the constraint name.</span></span>|  
|<span data-ttu-id="4628a-112">**msdata:PrimaryKey**</span><span class="sxs-lookup"><span data-stu-id="4628a-112">**msdata:PrimaryKey**</span></span>|<span data-ttu-id="4628a-113">경우 `PrimaryKey="true"` 가 있으면는 **IsPrimaryKey** 제약 조건 속성이로 설정 되어 **true**, 있기 때문에 기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="4628a-113">If `PrimaryKey="true"` is present, the **IsPrimaryKey** constraint property is set to **true**, thus making it a primary key.</span></span> <span data-ttu-id="4628a-114">**AllowDBNull** 열 속성이로 설정 되어 **false**이므로 기본 키는 null 값을 가질 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4628a-114">The **AllowDBNull** column property is set to **false**, because primary keys cannot have null values.</span></span>|  
  
 <span data-ttu-id="4628a-115">Key 제약 조건을 지정 하는 스키마를 변환 매핑 프로세스에서는 포함 된 테이블에 unique 제약 조건을 만듭니다는 **AllowDBNull** 열 속성이로 설정 **false** 각 열에 제약 조건입니다.</span><span class="sxs-lookup"><span data-stu-id="4628a-115">In converting schema in which a key constraint is specified, the mapping process creates a unique constraint on the table with the **AllowDBNull** column property set to **false** for each column in the constraint.</span></span> <span data-ttu-id="4628a-116">**IsPrimaryKey** unique 제약 조건의 속성이 **false** 지정 하기 전 까지는 `msdata:PrimaryKey="true"` 에 **키** 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="4628a-116">The **IsPrimaryKey** property of the unique constraint is also set to **false** unless you have specified `msdata:PrimaryKey="true"` on the **key** element.</span></span> <span data-ttu-id="4628a-117">이것은 `PrimaryKey="true"`인 스키마의 UNIQUE 제약 조건에도 마찬가지로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4628a-117">This is identical to a unique constraint in the schema in which `PrimaryKey="true"`.</span></span>  
  
 <span data-ttu-id="4628a-118">다음 스키마 예제에서는 **키** 요소에 키 제약 조건을 지정 된 **CustomerID** 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="4628a-118">In the following schema example, the **key** element specifies the key constraint on the **CustomerID** element.</span></span>  
  
```xml  
<xs:schema id="cod"  
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  <xs:element name="Customers">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
        <xs:element name="CompanyName" type="xs:string" minOccurs="0" />  
       <xs:element name="Phone" type="xs:string" />  
     </xs:sequence>  
   </xs:complexType>  
 </xs:element>  
<xs:element name="MyDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
      <xs:element ref="Customers" />  
    </xs:choice>  
  </xs:complexType>  
   <xs:key  msdata:PrimaryKey="true"  
       msdata:ConstraintName="KeyCustID"  
          name="KeyConstCustomerID" >  
     <xs:selector xpath=".//Customers" />  
     <xs:field xpath="CustomerID" />  
    </xs:key>  
 </xs:element>  
</xs:schema>   
```  
  
 <span data-ttu-id="4628a-119">**키** 요소를 지정 하는 값은 **CustomerID** 의 자식 요소는 **고객** 요소는 고유 값 이어야 하 고 null 값을 가질 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4628a-119">The **key** element specifies that the values of the **CustomerID** child element of the **Customers** element must have unique values and cannot have null values.</span></span> <span data-ttu-id="4628a-120">XSD(XML 스키마 정의 언어) 스키마를 변환할 때 매핑 프로세스에서는 다음 테이블을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4628a-120">In translating the XML Schema definition language (XSD) schema, the mapping process creates the following table:</span></span>  
  
```  
Customers(CustomerID, CompanyName, Phone)  
```  
  
 <span data-ttu-id="4628a-121">XML 스키마 매핑도 만듭니다.는 **UniqueConstraint** 에 **CustomerID** 열에서 다음에 표시 된 대로 <xref:System.Data.DataSet>합니다.</span><span class="sxs-lookup"><span data-stu-id="4628a-121">The XML Schema mapping also creates a **UniqueConstraint** on the **CustomerID** column, as shown in the following <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="4628a-122">여기에서는 편의를 위해 관련 속성만 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4628a-122">(For simplicity, only relevant properties are shown.)</span></span>  
  
```  
      DataSetName: MyDataSet  
TableName: customers  
  ColumnName: CustomerID  
      AllowDBNull: False  
      Unique: True  
  ConstraintName: KeyCustID  
      Table: customers  
      Columns: CustomerID   
      IsPrimaryKey: True  
```  
  
 <span data-ttu-id="4628a-123">에 **데이터 집합** 생성 하는 **IsPrimaryKey** 의 속성에서 **UniqueConstraint** 로 설정 되어 **true** 때문에 스키마 지정 `msdata:PrimaryKey="true"` 에 **키** 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="4628a-123">In the **DataSet** that is generated, the **IsPrimaryKey** property of the **UniqueConstraint** is set to **true** because the schema specifies `msdata:PrimaryKey="true"` in the **key** element.</span></span>  
  
 <span data-ttu-id="4628a-124">값은 **ConstraintName** 속성은 **UniqueConstraint** 에 **데이터 집합** 의 값이는 **msdata:ConstraintName** 에 지정 된 특성의 **키** 스키마의 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="4628a-124">The value of the **ConstraintName** property of the **UniqueConstraint** in the **DataSet** is the value of the **msdata:ConstraintName** attribute specified in the **key** element in the schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4628a-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4628a-125">See Also</span></span>  
 [<span data-ttu-id="4628a-126">데이터 집합 제약 조건에 XSD(XML 스키마) 제약 조건 매핑</span><span class="sxs-lookup"><span data-stu-id="4628a-126">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 [<span data-ttu-id="4628a-127">XSD(XML 스키마)에서 데이터 집합 관계 생성</span><span class="sxs-lookup"><span data-stu-id="4628a-127">Generating DataSet Relations from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 [<span data-ttu-id="4628a-128">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="4628a-128">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
