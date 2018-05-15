---
title: 중첩된 요소에 지정된 관계 매핑
ms.date: 03/30/2017
ms.assetid: 24a2d3e5-4af7-4f9a-ab7a-fe6684c9e4fe
ms.openlocfilehash: e1fde0ef585621a6821838613a7e77dedf7042b1
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="map-relations-specified-for-nested-elements"></a><span data-ttu-id="b1072-102">중첩된 요소에 지정된 관계 매핑</span><span class="sxs-lookup"><span data-stu-id="b1072-102">Map Relations Specified for Nested Elements</span></span>
<span data-ttu-id="b1072-103">스키마를 포함할 수 있습니다는 **msdata: relationship** 주석을 명시적으로 스키마의 두 요소 간의 매핑을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1072-103">A schema can include an **msdata:Relationship** annotation to explicitly specify the mapping between any two elements in the schema.</span></span> <span data-ttu-id="b1072-104">에 지정 된 두 요소가 **msdata: relationship** 스키마에서 중첩 될 수 있지만 될 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b1072-104">The two elements specified in **msdata:Relationship** can be nested in the schema, but do not have to be.</span></span> <span data-ttu-id="b1072-105">매핑 프로세스를 사용 하 여 **msdata: relationship** 두 열 간의 기본 키/외래 키 관계를 생성 하는 스키마에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1072-105">The mapping process uses **msdata:Relationship** in the schema to generate the primary key/foreign key relationship between the two columns.</span></span>  
  
 <span data-ttu-id="b1072-106">다음 예제는 XML 스키마를 보여 줍니다.는 **OrderDetail** 의 자식 요소 **순서**합니다.</span><span class="sxs-lookup"><span data-stu-id="b1072-106">The following example shows an XML Schema in which the **OrderDetail** element is a child element of **Order**.</span></span> <span data-ttu-id="b1072-107">**msdata: relationship** 이 부모-자식 관계를 식별 하 고 지정 하는 **OrderNumber** 열이 결과 **순서** 테이블이 관련 되어는 **OrderNo** 열이 결과 **OrderDetail** 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="b1072-107">The **msdata:Relationship** identifies this parent-child relationship and specifies that the **OrderNumber** column of the resulting **Order** table is related to the **OrderNo** column of the resulting **OrderDetail** table.</span></span>  
  
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
       <xs:element name="OrderNumber" type="xs:string" />  
       <xs:element name="EmpNumber" type="xs:string" />  
       <xs:element name="OrderDetail">  
          <xs:annotation>  
           <xs:appinfo>  
            <msdata:Relationship name="OrdODRelation"   
                                msdata:parent="Order"   
                                msdata:child="OrderDetail"   
                                msdata:parentkey="OrderNumber"   
                                msdata:childkey="OrderNo"/>  
           </xs:appinfo>  
          </xs:annotation>  
          <xs:complexType>  
            <xs:sequence>  
             <xs:element name="OrderNo" type="xs:string" />  
             <xs:element name="ItemNo" type="xs:string" />  
            </xs:sequence>  
         </xs:complexType>  
       </xs:element>  
     </xs:sequence>  
    </xs:complexType>  
   </xs:element>  
  </xs:choice>  
 </xs:complexType>  
</xs:element>  
</xs:schema>  
```  
  
 <span data-ttu-id="b1072-108">XML 스키마 매핑 프로세스에서는 <xref:System.Data.DataSet>에 다음 항목을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b1072-108">The XML Schema mapping process creates the following in the <xref:System.Data.DataSet>:</span></span>  
  
-   <span data-ttu-id="b1072-109">**순서** 및 **OrderDetail** 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="b1072-109">An **Order** and an **OrderDetail** table.</span></span>  
  
    ```  
    Order(OrderNumber, EmpNumber)  
    OrderDetail(OrderNo, ItemNo)  
    ```  
  
-   <span data-ttu-id="b1072-110">간의 관계는 **순서** 및 **OrderDetail** 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="b1072-110">A relationship between the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="b1072-111">**Nested** 이 관계에 대 한 속성이로 설정 되어 **True** 때문에 **순서** 및 **OrderDetail** 스키마에서 요소가 중첩 .</span><span class="sxs-lookup"><span data-stu-id="b1072-111">The **Nested** property for this relationship is set to **True** because the **Order** and **OrderDetail** elements are nested in the schema.</span></span>  
  
    ```  
    ParentTable: Order  
    ParentColumns: OrderNumber   
    ChildTable: OrderDetail  
    ChildColumns: OrderNo   
    RelationName: OrdODRelation  
    Nested: True  
    ```  
  
 <span data-ttu-id="b1072-112">매핑 프로세스에서는 어떠한 제약 조건도 만들지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b1072-112">The mapping process does not create any constraints.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1072-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b1072-113">See Also</span></span>  
 [<span data-ttu-id="b1072-114">XSD(XML 스키마)에서 데이터 집합 관계 생성</span><span class="sxs-lookup"><span data-stu-id="b1072-114">Generating DataSet Relations from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 [<span data-ttu-id="b1072-115">데이터 집합 제약 조건에 XSD(XML 스키마) 제약 조건 매핑</span><span class="sxs-lookup"><span data-stu-id="b1072-115">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 [<span data-ttu-id="b1072-116">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="b1072-116">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
