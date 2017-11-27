---
title: "외부 매핑"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 076606b8-d889-4ba0-b5da-ae577b146f23
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 7a0650f444f901d37797ca81343f06cb566f8112
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="external-mapping"></a><span data-ttu-id="b6047-102">외부 매핑</span><span class="sxs-lookup"><span data-stu-id="b6047-102">External Mapping</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="b6047-103">지원 *외부 매핑*을 사용 하 여 별도 XML 파일을 데이터베이스의 데이터 모델 및 개체 모델 사이의 매핑을 지정 하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="b6047-103"> supports *external mapping*, a process by which you use a separate XML file to specify mapping between the data model of the database and your object model.</span></span> <span data-ttu-id="b6047-104">외부 매핑 파일을 사용하면 다음과 같은 장점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6047-104">Advantages of using an external mapping file include the following:</span></span>  
  
-   <span data-ttu-id="b6047-105">매핑 코드를 응용 프로그램 코드와 따로 유지할 수 있어</span><span class="sxs-lookup"><span data-stu-id="b6047-105">You can keep your mapping code out of your application code.</span></span> <span data-ttu-id="b6047-106">응용 프로그램 코드를 간단하게 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6047-106">This approach reduces clutter in your application code.</span></span>  
  
-   <span data-ttu-id="b6047-107">외부 매핑 파일을 구성 파일처럼 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6047-107">You can treat an external mapping file something like a configuration file.</span></span> <span data-ttu-id="b6047-108">예를 들어 외부 매핑 파일을 바꾸는 방법으로 이진 파일을 배포한 후 응용 프로그램의 동작을 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6047-108">For example, you can update how your application behaves after shipping the binaries by just swapping out the external mapping file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6047-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b6047-109">Requirements</span></span>  
 <span data-ttu-id="b6047-110">매핑 파일은 XML 파일이어야 하며 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 스키마 정의 파일(.xsd)에 대해 유효성이 검사되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6047-110">The mapping file must be an XML file, and the file must validate against a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] schema definition (.xsd) file.</span></span>  
  
 <span data-ttu-id="b6047-111">이 때 적용되는 규칙은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b6047-111">The following rules apply:</span></span>  
  
-   <span data-ttu-id="b6047-112">매핑 파일은 XML 파일이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6047-112">The mapping file must be an XML file.</span></span>  
  
-   <span data-ttu-id="b6047-113">XML 매핑 파일은 XML 스키마 정의 파일에 대해 유효해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6047-113">The XML mapping file must be valid against the XML schema definition file.</span></span> <span data-ttu-id="b6047-114">자세한 내용은 참조 [하는 방법: DBML 유효성 검사 및 외부 매핑 파일](../../../../../../docs/framework/data/adonet/sql/linq/how-to-validate-dbml-and-external-mapping-files.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b6047-114">For more information, see [How to: Validate DBML and External Mapping Files](../../../../../../docs/framework/data/adonet/sql/linq/how-to-validate-dbml-and-external-mapping-files.md).</span></span>  
  
-   <span data-ttu-id="b6047-115">외부 매핑은 특성 기반 매핑을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b6047-115">External mapping overrides attribute-based mapping.</span></span> <span data-ttu-id="b6047-116">즉, 외부 매핑 소스를 사용하여 <xref:System.Data.Linq.DataContext>를 만들면 <xref:System.Data.Linq.DataContext>에서는 사용자가 클래스에 만든 모든 매핑 특성을 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="b6047-116">In other words, when you use an external mapping source to create a <xref:System.Data.Linq.DataContext>, the <xref:System.Data.Linq.DataContext> ignores all mapping attributes you have created on classes.</span></span> <span data-ttu-id="b6047-117">이 동작은 외부 매핑 파일에 클래스가 포함되었는지 여부에 관계없이 항상 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6047-117">This behavior is true whether the class is included in the external mapping file.</span></span>  
  
-   [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="b6047-118">에서는 특성 기반 매핑과 외부 매핑의 혼합 사용을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b6047-118"> does not support the hybrid use of the two mapping approaches (attribute-based and external).</span></span>  
  
## <a name="xml-schema-definition-file"></a><span data-ttu-id="b6047-119">XML 스키마 정의 파일</span><span class="sxs-lookup"><span data-stu-id="b6047-119">XML Schema Definition File</span></span>  
 <span data-ttu-id="b6047-120">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 외부 매핑은 다음 XML 스키마 정의에 대해 유효해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6047-120">External mapping in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] must be valid against the following XML schema definition.</span></span>  
  
 <span data-ttu-id="b6047-121">이 스키마 정의 파일은 DBML 파일의 유효성을 검사하는 데 사용하는 스키마 정의 파일과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="b6047-121">Distinguish this schema definition file from the schema definition file that is used to validate a DBML file.</span></span> <span data-ttu-id="b6047-122">자세한 내용은 참조 [LINQ to SQL에서에서 코드 생성](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)).</span><span class="sxs-lookup"><span data-stu-id="b6047-122">For more information, see [Code Generation in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)).</span></span>  
  
> [!NOTE]
>  [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)]<span data-ttu-id="b6047-123"> 사용자의 경우 이 XSD 파일은 XML 스키마 대화 상자에 "LinqToSqlMapping.xsd"로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6047-123"> users will also find this XSD file in the XML Schemas dialog box as "LinqToSqlMapping.xsd".</span></span> <span data-ttu-id="b6047-124">외부 매핑 파일 유효성 검사를 위해이 파일을 올바르게 사용 하려면 참조 [하는 방법: DBML 유효성 검사 및 외부 매핑 파일](../../../../../../docs/framework/data/adonet/sql/linq/how-to-validate-dbml-and-external-mapping-files.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b6047-124">To use this file correctly for validating an external mapping file, see [How to: Validate DBML and External Mapping Files](../../../../../../docs/framework/data/adonet/sql/linq/how-to-validate-dbml-and-external-mapping-files.md).</span></span>  
  
```  
?<?xml version="1.0" encoding="utf-16"?>  
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema" targetNamespace="http://schemas.microsoft.com/linqtosql/mapping/2007" xmlns="http://schemas.microsoft.com/linqtosql/mapping/2007"  
elementFormDefault="qualified" >  
  <xs:element name="Database" type="Database" />  
  <xs:complexType name="Database">  
    <xs:sequence>  
      <xs:element name="Table" type="Table" minOccurs="0" maxOccurs="unbounded" />  
      <xs:element name="Function" type="Function" minOccurs="0" maxOccurs="unbounded" />  
    </xs:sequence>  
    <xs:attribute name="Name" type="xs:string" use="optional" />  
    <xs:attribute name="Provider" type="xs:string" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="Table">  
    <xs:sequence>  
      <xs:element name="Type" type="Type" minOccurs="1" maxOccurs="1" />  
    </xs:sequence>  
    <xs:attribute name="Name" type="xs:string" use="optional" />  
    <xs:attribute name="Member" type="xs:string" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="Type">  
    <xs:sequence>  
      <xs:choice minOccurs="0" maxOccurs="unbounded">  
        <xs:element name="Column" type="Column" minOccurs="0" maxOccurs="unbounded" />  
        <xs:element name="Association" type="Association" minOccurs="0" maxOccurs="unbounded" />  
      </xs:choice>  
      <xs:element name="Type" type="Type" minOccurs="0" maxOccurs="unbounded" />  
    </xs:sequence>  
    <xs:attribute name="Name" type="xs:string" use="required" />  
    <xs:attribute name="InheritanceCode" type="xs:string" use="optional" />  
    <xs:attribute name="IsInheritanceDefault" type="xs:boolean" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="Column">  
    <xs:attribute name="Name" type="xs:string" use="optional" />  
    <xs:attribute name="Member" type="xs:string" use="required" />  
    <xs:attribute name="Storage" type="xs:string" use="optional" />  
    <xs:attribute name="DbType" type="xs:string" use="optional" />  
    <xs:attribute name="IsPrimaryKey" type="xs:boolean" use="optional" />  
    <xs:attribute name="IsDbGenerated" type="xs:boolean" use="optional" />  
    <xs:attribute name="CanBeNull" type="xs:boolean" use="optional" />  
    <xs:attribute name="UpdateCheck" type="UpdateCheck" use="optional" />  
    <xs:attribute name="IsDiscriminator" type="xs:boolean" use="optional" />  
    <xs:attribute name="Expression" type="xs:string" use="optional" />  
    <xs:attribute name="IsVersion" type="xs:boolean" use="optional" />  
    <xs:attribute name="AutoSync" type="AutoSync" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="Association">  
    <xs:attribute name="Name" type="xs:string" use="optional" />  
    <xs:attribute name="Member" type="xs:string" use="required" />  
    <xs:attribute name="Storage" type="xs:string" use="optional" />  
    <xs:attribute name="ThisKey" type="xs:string" use="optional" />  
    <xs:attribute name="OtherKey" type="xs:string" use="optional" />  
    <xs:attribute name="IsForeignKey" type="xs:boolean" use="optional" />  
    <xs:attribute name="IsUnique" type="xs:boolean" use="optional" />  
    <xs:attribute name="DeleteRule" type="xs:string" use="optional" />  
    <xs:attribute name="DeleteOnNull" type="xs:boolean" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="Function">  
    <xs:sequence>  
      <xs:element name="Parameter" type="Parameter" minOccurs="0" maxOccurs="unbounded" />  
      <xs:choice>  
        <xs:element name="ElementType" type="Type" minOccurs="0" maxOccurs="unbounded" />  
        <xs:element name="Return" type="Return" minOccurs="0" maxOccurs="1" />  
      </xs:choice>  
    </xs:sequence>  
    <xs:attribute name="Name" type="xs:string" use="optional" />  
    <xs:attribute name="Method" type="xs:string" use="required" />  
    <xs:attribute name="IsComposable" type="xs:boolean" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="Parameter">  
    <xs:attribute name="Name" type="xs:string" use="optional" />  
    <xs:attribute name="Parameter" type="xs:string" use="required" />  
    <xs:attribute name="DbType" type="xs:string" use="optional" />  
    <xs:attribute name="Direction" type="ParameterDirection" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="Return">  
    <xs:attribute name="DbType" type="xs:string" use="optional" />  
  </xs:complexType>  
  <xs:simpleType name="UpdateCheck">  
    <xs:restriction base="xs:string">  
      <xs:enumeration value="Always" />  
      <xs:enumeration value="Never" />  
      <xs:enumeration value="WhenChanged" />  
    </xs:restriction>  
  </xs:simpleType>  
  <xs:simpleType name="ParameterDirection">  
    <xs:restriction base="xs:string">  
      <xs:enumeration value="In" />  
      <xs:enumeration value="Out" />  
      <xs:enumeration value="InOut" />  
    </xs:restriction>  
  </xs:simpleType>  
  <xs:simpleType name="AutoSync">  
    <xs:restriction base="xs:string">  
      <xs:enumeration value="Never" />  
      <xs:enumeration value="OnInsert" />  
      <xs:enumeration value="OnUpdate" />  
      <xs:enumeration value="Always" />  
      <xs:enumeration value="Default" />  
    </xs:restriction>  
  </xs:simpleType>  
</xs:schema>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b6047-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b6047-125">See Also</span></span>  
 [<span data-ttu-id="b6047-126">LINQ to SQL에서에서 코드 생성</span><span class="sxs-lookup"><span data-stu-id="b6047-126">Code Generation in LINQ to SQL</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)  
 [<span data-ttu-id="b6047-127">참조</span><span class="sxs-lookup"><span data-stu-id="b6047-127">Reference</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)  
 [<span data-ttu-id="b6047-128">방법: 외부 파일로 개체 모델 생성</span><span class="sxs-lookup"><span data-stu-id="b6047-128">How to: Generate the Object Model as an External File</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-generate-the-object-model-as-an-external-file.md)
