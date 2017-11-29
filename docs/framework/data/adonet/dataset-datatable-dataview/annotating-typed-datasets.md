---
title: "형식화된 데이터 집합에 주석 지정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: f82aaa62-321e-4c8a-b51b-9d1114700170
caps.latest.revision: "6"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: d3965ced44bae21feef3d01d49149387fce4fa46
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="annotating-typed-datasets"></a><span data-ttu-id="dcdbb-102">형식화된 데이터 집합에 주석 지정</span><span class="sxs-lookup"><span data-stu-id="dcdbb-102">Annotating Typed DataSets</span></span>
<span data-ttu-id="dcdbb-103">주석을 사용하면 원본으로 사용하는 스키마를 수정하지 않고 형식화된 <xref:System.Data.DataSet>의 요소 이름을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcdbb-103">Annotations enable you to modify the names of the elements in your typed <xref:System.Data.DataSet> without modifying the underlying schema.</span></span> <span data-ttu-id="dcdbb-104">기본 스키마에서 요소의 이름 수정로 인해 형식화 된 **데이터 집합** 않는 하지 데이터 원본에 없는 뿐만 아니라 데이터 원본에 없는 개체에 대 한 참조를 손실 되는 개체를 참조 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcdbb-104">Modifying the names of the elements in your underlying schema would cause the typed **DataSet** to refer to objects that do not exist in the data source, as well as lose a reference to the objects that do exist in the data source.</span></span>  
  
 <span data-ttu-id="dcdbb-105">주석을 사용 하면 사용자 지정할 수 있습니다 개체의 이름을 입력 한 **DataSet** 더 의미 있는 이름으로 만드는 코드의 가독성 및 형식화 된 **DataSet** 그대로 유지 하면서 사용 하도록 클라이언트에 대 한 보다 쉽게 기본 스키마를 그대로 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcdbb-105">Using annotations, you can customize the names of objects in your typed **DataSet** with more meaningful names, making code more readable and your typed **DataSet** easier for clients to use, while leaving underlying schema intact.</span></span> <span data-ttu-id="dcdbb-106">에 대 한 다음 스키마 요소 예를 들어는 **고객** 목차는 **Northwind** 데이터베이스는 **DataRow** 의 개체 이름  **CustomersRow** 및 <xref:System.Data.DataRowCollection> 라는 **고객**합니다.</span><span class="sxs-lookup"><span data-stu-id="dcdbb-106">For example, the following schema element for the **Customers** table of the **Northwind** database would result in a **DataRow** object name of **CustomersRow** and a <xref:System.Data.DataRowCollection> named **Customers**.</span></span>  
  
```xml  
<xs:element name="Customers">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 <span data-ttu-id="dcdbb-107">A **DataRowCollection** 이름 **고객** 클라이언트 코드에서 적절 한 의미 하지만 **DataRow** 이름 **CustomersRow** 잘못 된 것입니다 단일 개체 이므로</span><span class="sxs-lookup"><span data-stu-id="dcdbb-107">A **DataRowCollection** name of **Customers** is meaningful in client code, but a **DataRow** name of **CustomersRow** is misleading because it is a single object.</span></span> <span data-ttu-id="dcdbb-108">또한, 공통 시나리오 개체 참조 하지 않고는 **행** 식별자 대신는 단순히로 간주 하 고는 **고객** 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="dcdbb-108">Also, in common scenarios, the object would be referred to without the **Row** identifier and instead would be simply referred to as a **Customer** object.</span></span> <span data-ttu-id="dcdbb-109">솔루션에 대 한 새 이름을 식별 하는 스키마에 주석을 추가 하는 것은 **DataRow** 및 **DataRowCollection** 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="dcdbb-109">The solution is to annotate the schema and identify new names for the **DataRow** and **DataRowCollection** objects.</span></span> <span data-ttu-id="dcdbb-110">다음 코드는 이전 스키마에 주석을 단 것입니다.</span><span class="sxs-lookup"><span data-stu-id="dcdbb-110">Following is the annotated version of the previous schema.</span></span>  
  
```xml  
<xs:element name="Customers" codegen:typedName="Customer" codegen:typedPlural="Customers">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 <span data-ttu-id="dcdbb-111">지정 하는 **typedName** 값 **고객** 됩니다는 **DataRow** 의 개체 이름 **고객**합니다.</span><span class="sxs-lookup"><span data-stu-id="dcdbb-111">Specifying a **typedName** value of **Customer** will result in a **DataRow** object name of **Customer**.</span></span> <span data-ttu-id="dcdbb-112">지정 하는 **typedPlural** 값 **고객** 유지는 **DataRowCollection** 이름 **고객**합니다.</span><span class="sxs-lookup"><span data-stu-id="dcdbb-112">Specifying a **typedPlural** value of **Customers** preserves the **DataRowCollection** name of **Customers**.</span></span>  
  
 <span data-ttu-id="dcdbb-113">다음 표에서는 사용할 수 있는 주석을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dcdbb-113">The following table shows the annotations available for use.</span></span>  
  
|<span data-ttu-id="dcdbb-114">주석</span><span class="sxs-lookup"><span data-stu-id="dcdbb-114">Annotation</span></span>|<span data-ttu-id="dcdbb-115">설명</span><span class="sxs-lookup"><span data-stu-id="dcdbb-115">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="dcdbb-116">**typedName**</span><span class="sxs-lookup"><span data-stu-id="dcdbb-116">**typedName**</span></span>|<span data-ttu-id="dcdbb-117">개체의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="dcdbb-117">Name of the object.</span></span>|  
|<span data-ttu-id="dcdbb-118">**typedPlural**</span><span class="sxs-lookup"><span data-stu-id="dcdbb-118">**typedPlural**</span></span>|<span data-ttu-id="dcdbb-119">개체 컬렉션의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="dcdbb-119">Name of a collection of objects.</span></span>|  
|<span data-ttu-id="dcdbb-120">**typedParent**</span><span class="sxs-lookup"><span data-stu-id="dcdbb-120">**typedParent**</span></span>|<span data-ttu-id="dcdbb-121">부모 관계에서 참조될 때의 개체 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="dcdbb-121">Name of the object when referred to in a parent relationship.</span></span>|  
|<span data-ttu-id="dcdbb-122">**typedChildren**</span><span class="sxs-lookup"><span data-stu-id="dcdbb-122">**typedChildren**</span></span>|<span data-ttu-id="dcdbb-123">자식 관계에서 개체를 반환하기 위한 메서드의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="dcdbb-123">Name of the method to return objects from a child relationship.</span></span>|  
|<span data-ttu-id="dcdbb-124">**nullValue**</span><span class="sxs-lookup"><span data-stu-id="dcdbb-124">**nullValue**</span></span>|<span data-ttu-id="dcdbb-125">원본 값이 있으면 **DBNull**합니다.</span><span class="sxs-lookup"><span data-stu-id="dcdbb-125">Value if the underlying value is **DBNull**.</span></span> <span data-ttu-id="dcdbb-126">다음 표를 참조 하십시오 **nullValue** 주석입니다.</span><span class="sxs-lookup"><span data-stu-id="dcdbb-126">See the following table for **nullValue** annotations.</span></span> <span data-ttu-id="dcdbb-127">기본값은 **_throw**합니다.</span><span class="sxs-lookup"><span data-stu-id="dcdbb-127">The default is **_throw**.</span></span>|  
  
 <span data-ttu-id="dcdbb-128">다음 표에서에 지정 될 수 있는 값을 보여 줍니다.는 **nullValue** 주석입니다.</span><span class="sxs-lookup"><span data-stu-id="dcdbb-128">The following table shows the values that can be specified for the **nullValue** annotation.</span></span>  
  
|<span data-ttu-id="dcdbb-129">nullValue 값</span><span class="sxs-lookup"><span data-stu-id="dcdbb-129">nullValue Value</span></span>|<span data-ttu-id="dcdbb-130">설명</span><span class="sxs-lookup"><span data-stu-id="dcdbb-130">Description</span></span>|  
|---------------------|-----------------|  
|<span data-ttu-id="dcdbb-131">*대체 값*</span><span class="sxs-lookup"><span data-stu-id="dcdbb-131">*Replacement Value*</span></span>|<span data-ttu-id="dcdbb-132">반환될 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="dcdbb-132">Specify a value to be returned.</span></span> <span data-ttu-id="dcdbb-133">반환되는 값은 요소의 형식과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcdbb-133">The returned value must match the type of the element.</span></span> <span data-ttu-id="dcdbb-134">예를 들어, `nullValue="0"`을 사용하여 null 정수 필드에 0을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="dcdbb-134">For example, use `nullValue="0"` to return 0 for null integer fields.</span></span>|  
|<span data-ttu-id="dcdbb-135">**_throw**</span><span class="sxs-lookup"><span data-stu-id="dcdbb-135">**_throw**</span></span>|<span data-ttu-id="dcdbb-136">예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="dcdbb-136">Throw an exception.</span></span> <span data-ttu-id="dcdbb-137">이 값이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="dcdbb-137">This is the default.</span></span>|  
|<span data-ttu-id="dcdbb-138">**_null**</span><span class="sxs-lookup"><span data-stu-id="dcdbb-138">**_null**</span></span>|<span data-ttu-id="dcdbb-139">기본 형식이 발견되면 null 참조를 반환하거나 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="dcdbb-139">Return a null reference or throw an exception if a primitive type is encountered.</span></span>|  
|<span data-ttu-id="dcdbb-140">**_empty**</span><span class="sxs-lookup"><span data-stu-id="dcdbb-140">**_empty**</span></span>|<span data-ttu-id="dcdbb-141">문자열에 대해 반환 **String.Empty**, 그렇지 않으면 빈 생성자에서 만든 개체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcdbb-141">For strings, return **String.Empty**, otherwise return an object created from an empty constructor.</span></span> <span data-ttu-id="dcdbb-142">기본 형식이 발견되면 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="dcdbb-142">If a primitive type is encountered, throw an exception.</span></span>|  
  
 <span data-ttu-id="dcdbb-143">다음 표에서 형식화 된 개체에 대 한 기본 값을 보여 줍니다. **DataSet** 및 사용할 수 있는 주석입니다.</span><span class="sxs-lookup"><span data-stu-id="dcdbb-143">The following table shows default values for objects in a typed **DataSet** and the available annotations.</span></span>  
  
|<span data-ttu-id="dcdbb-144">개체/메서드/이벤트</span><span class="sxs-lookup"><span data-stu-id="dcdbb-144">Object/Method/Event</span></span>|<span data-ttu-id="dcdbb-145">기본</span><span class="sxs-lookup"><span data-stu-id="dcdbb-145">Default</span></span>|<span data-ttu-id="dcdbb-146">주석</span><span class="sxs-lookup"><span data-stu-id="dcdbb-146">Annotation</span></span>|  
|---------------------------|-------------|----------------|  
|<span data-ttu-id="dcdbb-147">**DataTable**</span><span class="sxs-lookup"><span data-stu-id="dcdbb-147">**DataTable**</span></span>|<span data-ttu-id="dcdbb-148">TableNameDataTable</span><span class="sxs-lookup"><span data-stu-id="dcdbb-148">TableNameDataTable</span></span>|<span data-ttu-id="dcdbb-149">typedPlural</span><span class="sxs-lookup"><span data-stu-id="dcdbb-149">typedPlural</span></span>|  
|<span data-ttu-id="dcdbb-150">**DataTable** 메서드</span><span class="sxs-lookup"><span data-stu-id="dcdbb-150">**DataTable** Methods</span></span>|<span data-ttu-id="dcdbb-151">NewTableNameRow</span><span class="sxs-lookup"><span data-stu-id="dcdbb-151">NewTableNameRow</span></span><br /><br /> <span data-ttu-id="dcdbb-152">AddTableNameRow</span><span class="sxs-lookup"><span data-stu-id="dcdbb-152">AddTableNameRow</span></span><br /><br /> <span data-ttu-id="dcdbb-153">DeleteTableNameRow</span><span class="sxs-lookup"><span data-stu-id="dcdbb-153">DeleteTableNameRow</span></span>|<span data-ttu-id="dcdbb-154">typedName</span><span class="sxs-lookup"><span data-stu-id="dcdbb-154">typedName</span></span>|  
|<span data-ttu-id="dcdbb-155">**DataRowCollection**</span><span class="sxs-lookup"><span data-stu-id="dcdbb-155">**DataRowCollection**</span></span>|<span data-ttu-id="dcdbb-156">TableName</span><span class="sxs-lookup"><span data-stu-id="dcdbb-156">TableName</span></span>|<span data-ttu-id="dcdbb-157">typedPlural</span><span class="sxs-lookup"><span data-stu-id="dcdbb-157">typedPlural</span></span>|  
|<span data-ttu-id="dcdbb-158">**DataRow**</span><span class="sxs-lookup"><span data-stu-id="dcdbb-158">**DataRow**</span></span>|<span data-ttu-id="dcdbb-159">TableNameRow</span><span class="sxs-lookup"><span data-stu-id="dcdbb-159">TableNameRow</span></span>|<span data-ttu-id="dcdbb-160">typedName</span><span class="sxs-lookup"><span data-stu-id="dcdbb-160">typedName</span></span>|  
|<span data-ttu-id="dcdbb-161">**DataColumn**</span><span class="sxs-lookup"><span data-stu-id="dcdbb-161">**DataColumn**</span></span>|<span data-ttu-id="dcdbb-162">DataTable.ColumnNameColumn</span><span class="sxs-lookup"><span data-stu-id="dcdbb-162">DataTable.ColumnNameColumn</span></span><br /><br /> <span data-ttu-id="dcdbb-163">DataRow.ColumnName</span><span class="sxs-lookup"><span data-stu-id="dcdbb-163">DataRow.ColumnName</span></span>|<span data-ttu-id="dcdbb-164">typedName</span><span class="sxs-lookup"><span data-stu-id="dcdbb-164">typedName</span></span>|  
|<span data-ttu-id="dcdbb-165">**Property**</span><span class="sxs-lookup"><span data-stu-id="dcdbb-165">**Property**</span></span>|<span data-ttu-id="dcdbb-166">PropertyName</span><span class="sxs-lookup"><span data-stu-id="dcdbb-166">PropertyName</span></span>|<span data-ttu-id="dcdbb-167">typedName</span><span class="sxs-lookup"><span data-stu-id="dcdbb-167">typedName</span></span>|  
|<span data-ttu-id="dcdbb-168">**자식** 접근자</span><span class="sxs-lookup"><span data-stu-id="dcdbb-168">**Child** Accessor</span></span>|<span data-ttu-id="dcdbb-169">GetChildTableNameRows</span><span class="sxs-lookup"><span data-stu-id="dcdbb-169">GetChildTableNameRows</span></span>|<span data-ttu-id="dcdbb-170">typedChildren</span><span class="sxs-lookup"><span data-stu-id="dcdbb-170">typedChildren</span></span>|  
|<span data-ttu-id="dcdbb-171">**부모** 접근자</span><span class="sxs-lookup"><span data-stu-id="dcdbb-171">**Parent** Accessor</span></span>|<span data-ttu-id="dcdbb-172">TableNameRow</span><span class="sxs-lookup"><span data-stu-id="dcdbb-172">TableNameRow</span></span>|<span data-ttu-id="dcdbb-173">typedParent</span><span class="sxs-lookup"><span data-stu-id="dcdbb-173">typedParent</span></span>|  
|<span data-ttu-id="dcdbb-174">**데이터 집합** 이벤트</span><span class="sxs-lookup"><span data-stu-id="dcdbb-174">**DataSet** Events</span></span>|<span data-ttu-id="dcdbb-175">TableNameRowChangeEvent</span><span class="sxs-lookup"><span data-stu-id="dcdbb-175">TableNameRowChangeEvent</span></span><br /><br /> <span data-ttu-id="dcdbb-176">TableNameRowChangeEventHandler</span><span class="sxs-lookup"><span data-stu-id="dcdbb-176">TableNameRowChangeEventHandler</span></span>|<span data-ttu-id="dcdbb-177">typedName</span><span class="sxs-lookup"><span data-stu-id="dcdbb-177">typedName</span></span>|  
  
 <span data-ttu-id="dcdbb-178">사용 하려면 입력 **DataSet** 주석, 다음을 포함 해야 **xmlns** XML 스키마 정의 언어 (XSD) 스키마에서 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcdbb-178">To use typed **DataSet** annotations, you must include the following **xmlns** reference in your XML Schema definition language (XSD) schema.</span></span> <span data-ttu-id="dcdbb-179">(데이터베이스 테이블에서 xsd를 만들려면 <xref:System.Data.DataSet.WriteXmlSchema%2A> 또는 [Visual Studio에서 데이터 집합 작업](http://msdn.microsoft.com/library/8bw9ksd6.aspx)).</span><span class="sxs-lookup"><span data-stu-id="dcdbb-179">(To create an xsd from database tables, see <xref:System.Data.DataSet.WriteXmlSchema%2A> or [Working with Datasets in Visual Studio](http://msdn.microsoft.com/library/8bw9ksd6.aspx)).</span></span>  
  
```  
xmlns:codegen="urn:schemas-microsoft-com:xml-msprop"  
```  
  
 <span data-ttu-id="dcdbb-180">다음은 주석이 있는 샘플 스키마를 노출 하는 **고객** 목차는 **Northwind** 와 관계를 사용 하 여 데이터베이스의 **주문** 포함 된 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="dcdbb-180">The following is a sample annotated schema that exposes the **Customers** table of the **Northwind** database with a relation to the **Orders** table included.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<xs:schema id="CustomerDataSet"   
      xmlns:codegen="urn:schemas-microsoft-com:xml-msprop"  
      xmlns=""   
      xmlns:xs="http://www.w3.org/2001/XMLSchema"   
      xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  <xs:element name="CustomerDataSet" msdata:IsDataSet="true">  
    <xs:complexType>  
      <xs:choice maxOccurs="unbounded">  
        <xs:element name="Customers" codegen:typedName="Customer" codegen:typedPlural="Customers">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element name="CustomerID"  
codegen:typedName="CustomerID" type="xs:string" minOccurs="0" />  
              <xs:element name="CompanyName"  
codegen:typedName="CompanyName" type="xs:string" minOccurs="0" />  
              <xs:element name="Phone" codegen:typedName="Phone" codegen:nullValue="" type="xs:string" minOccurs="0" />  
            </xs:sequence>  
          </xs:complexType>  
        </xs:element>  
        <xs:element name="Orders" codegen:typedName="Order" codegen:typedPlural="Orders">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element name="OrderID" codegen:typedName="OrderID"  
type="xs:int" minOccurs="0" />  
              <xs:element name="CustomerID"  
codegen:typedName="CustomerID"                  codegen:nullValue="" type="xs:string" minOccurs="0" />  
              <xs:element name="EmployeeID"  
codegen:typedName="EmployeeID" codegen:nullValue="0"   
type="xs:int" minOccurs="0" />  
              <xs:element name="OrderAdapter"  
codegen:typedName="OrderAdapter" codegen:nullValue="1980-01-01T00:00:00"   
type="xs:dateTime" minOccurs="0" />  
            </xs:sequence>  
          </xs:complexType>  
        </xs:element>  
      </xs:choice>  
    </xs:complexType>  
    <xs:unique name="Constraint1">  
      <xs:selector xpath=".//Customers" />  
      <xs:field xpath="CustomerID" />  
    </xs:unique>  
    <xs:keyref name="CustOrders" refer="Constraint1"  
codegen:typedParent="Customer" codegen:typedChildren="GetOrders">  
      <xs:selector xpath=".//Orders" />  
      <xs:field xpath="CustomerID" />  
    </xs:keyref>  
  </xs:element>  
</xs:schema>  
```  
  
 <span data-ttu-id="dcdbb-181">다음 코드 예제를 사용 하 여 강력한 형식의 **DataSet** 샘플 스키마에서 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcdbb-181">The following code example uses a strongly typed **DataSet** created from the sample schema.</span></span> <span data-ttu-id="dcdbb-182">하나 사용 하 여 <xref:System.Data.SqlClient.SqlDataAdapter> 채우는 데는 **고객** 테이블과 다른 <xref:System.Data.SqlClient.SqlDataAdapter> 채우는 데는 **Orders** 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="dcdbb-182">It uses one <xref:System.Data.SqlClient.SqlDataAdapter> to populate the **Customers** table and another <xref:System.Data.SqlClient.SqlDataAdapter> to populate the **Orders** table.</span></span> <span data-ttu-id="dcdbb-183">강력한 형식의 **DataSet** 정의 **Datarelation**합니다.</span><span class="sxs-lookup"><span data-stu-id="dcdbb-183">The strongly typed **DataSet** defines the **DataRelations**.</span></span>  
  
```vb  
' Assumes a valid SqlConnection object named connection.  
Dim customerAdapter As SqlDataAdapter = New SqlDataAdapter( _  
    "SELECT CustomerID, CompanyName, Phone FROM Customers", &  
    connection)  
Dim orderAdapter As SqlDataAdapter = New SqlDataAdapter( _  
    "SELECT OrderID, CustomerID, EmployeeID, OrderAdapter FROM Orders", &  
    connection)  
  
' Populate a strongly typed DataSet.  
connection.Open()  
Dim customers As CustomerDataSet = New CustomerDataSet()  
customerAdapter.Fill(customers, "Customers")  
orderAdapter.Fill(customers, "Orders")  
connection.Close()  
  
' Add a strongly typed event.  
AddHandler customers.Customers.CustomerChanged, &  
    New CustomerDataSet.CustomerChangeEventHandler( _  
    AddressOf OnCustomerChanged)  
  
' Add a strongly typed DataRow.  
Dim newCustomer As CustomerDataSet.Customer = _  
    customers.Customers.NewCustomeromer()  
newCustomer.CustomerID = "NEW01"  
newCustomer.CompanyName = "My New Company"  
customers.Customers.AddCustomer(newCustomer)  
  
' Navigate the child relation.  
Dim customer As CustomerDataSet.Customer  
Dim order As CustomerDataSet.Order  
  
For Each customer In customers.Customers  
  Console.WriteLine(customer.CustomerID)  
  For Each order In customer.GetOrders()  
    Console.WriteLine(vbTab & order.OrderID)  
  Next  
Next  
  
Private Shared Sub OnCustomerChanged( _  
    sender As Object, e As CustomerDataSet.CustomerChangeEvent)  
  
End Sub  
```  
  
```csharp  
// Assumes a valid SqlConnection object named connection.  
SqlDataAdapter customerAdapter = new SqlDataAdapter(  
    "SELECT CustomerID, CompanyName, Phone FROM Customers",  
    connection);  
SqlDataAdapter orderAdapter = new SqlDataAdapter(  
    "SELECT OrderID, CustomerID, EmployeeID, OrderAdapter FROM Orders",   
    connection);  
  
// Populate a strongly typed DataSet.  
connection.Open();  
CustomerDataSet customers = new CustomerDataSet();  
customerAdapter.Fill(customers, "Customers");  
orderAdapter.Fill(customers, "Orders");  
connection.Close();  
  
// Add a strongly typed event.  
customers.Customers.CustomerChanged += new   
  CustomerDataSet.CustomerChangeEventHandler(OnCustomerChanged);  
  
// Add a strongly typed DataRow.  
CustomerDataSet.Customer newCustomer =   
    customers.Customers.NewCustomeromer();  
newCustomer.CustomerID = "NEW01";  
newCustomer.CompanyName = "My New Company";  
customers.Customers.AddCustomer(newCustomer);  
  
// Navigate the child relation.  
foreach(CustomerDataSet.Customer customer in customers.Customers)  
{  
  Console.WriteLine(customer.CustomerID);  
  foreach(CustomerDataSet.Order order in customer.GetOrders())  
    Console.WriteLine("\t" + order.OrderID);  
}  
  
protected static void OnCustomerChanged(object sender, CustomerDataSet.CustomerChangeEvent e)  
    {  
  
    }  
```  
  
## <a name="see-also"></a><span data-ttu-id="dcdbb-184">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dcdbb-184">See Also</span></span>  
 <xref:System.Data.DataColumnCollection>  
 <xref:System.Data.DataSet>  
 [<span data-ttu-id="dcdbb-185">형식화된 데이터 집합</span><span class="sxs-lookup"><span data-stu-id="dcdbb-185">Typed DataSets</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)  
 [<span data-ttu-id="dcdbb-186">DataSet, DataTable 및 DataView</span><span class="sxs-lookup"><span data-stu-id="dcdbb-186">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="dcdbb-187">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="dcdbb-187">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
