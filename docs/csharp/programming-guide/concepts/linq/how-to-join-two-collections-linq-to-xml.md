---
title: '방법: 두 컬렉션 조인(LINQ to XML)(C#)'
ms.date: 07/20/2015
ms.assetid: 7b817ede-911a-4cff-9dd3-639c3fc228c9
ms.openlocfilehash: d4e7c73262cce234dc8373d42b2a8cb366316622
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-join-two-collections-linq-to-xml-c"></a><span data-ttu-id="a62a9-102">방법: 두 컬렉션 조인(LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="a62a9-102">How to: Join Two Collections (LINQ to XML) (C#)</span></span>
<span data-ttu-id="a62a9-103">XML 문서의 요소나 특성은 때때로 다른 요소나 특성을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a62a9-103">An element or attribute in an XML document can sometimes refer to another element or attribute.</span></span> <span data-ttu-id="a62a9-104">예를 들어 [샘플 XML 파일: Customers 및 Orders(LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml-2.md) XML 문서에는 고객 목록과 주문 목록이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a62a9-104">For example, the [Sample XML File: Customers and Orders (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml-2.md) XML document contains a list of customers and a list of orders.</span></span> <span data-ttu-id="a62a9-105">각 `Customer` 요소에는 `CustomerID` 특성이 포함되어 있고,</span><span class="sxs-lookup"><span data-stu-id="a62a9-105">Each `Customer` element contains a `CustomerID` attribute.</span></span> <span data-ttu-id="a62a9-106">각 `Order` 요소에는 `CustomerID` 요소가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a62a9-106">Each `Order` element contains a `CustomerID` element.</span></span> <span data-ttu-id="a62a9-107">각 주문의 `CustomerID` 요소는 고객의 `CustomerID` 특성을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="a62a9-107">The `CustomerID` element in each order refers to the `CustomerID` attribute in a customer.</span></span>  
  
 <span data-ttu-id="a62a9-108">[샘플 XSD 파일: Customers 및 Orders](../../../../csharp/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders1.md) 항목에는 이 문서의 유효성을 검사하는 데 사용할 수 있는 XSD가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a62a9-108">The topic [Sample XSD File: Customers and Orders](../../../../csharp/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders1.md) contains an XSD that can be used to validate this document.</span></span> <span data-ttu-id="a62a9-109">이 항목에서는 XSD의 `xs:key` 및 `xs:keyref` 기능을 사용하여 `CustomerID` 요소의 `Customer` 특성을 키로 설정하고 각 `CustomerID` 요소의 `Order` 요소와 각 `CustomerID` 요소의 `Customer` 특성 간 관계를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a62a9-109">It uses the `xs:key` and `xs:keyref` features of XSD to establish that the `CustomerID` attribute of the `Customer` element is a key, and to establish a relationship between the `CustomerID` element in each `Order` element and the `CustomerID` attribute in each `Customer` element.</span></span>  
  
 <span data-ttu-id="a62a9-110">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]에서는 `join` 절을 사용하여 이 관계를 이용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a62a9-110">With [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you can take advantage of this relationship by using the `join` clause.</span></span>  
  
 <span data-ttu-id="a62a9-111">사용 가능한 인덱스가 없기 때문에 이러한 조인의 런타임 성능은 좋지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a62a9-111">Note that because there is no index available, such joining will have poor runtime performance.</span></span>  
  
 <span data-ttu-id="a62a9-112">`join`에 대한 자세한 내용은 [조인 작업(C#)](../../../../csharp/programming-guide/concepts/linq/join-operations.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a62a9-112">For more detailed information about `join`, see [Join Operations (C#)](../../../../csharp/programming-guide/concepts/linq/join-operations.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a62a9-113">예</span><span class="sxs-lookup"><span data-stu-id="a62a9-113">Example</span></span>  
 <span data-ttu-id="a62a9-114">다음 예제에서는 `Customer` 요소와 `Order` 요소를 조인하고 주문의 `CompanyName` 요소가 포함된 새 XML 문서를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a62a9-114">The following example joins the `Customer` elements to the `Order` elements, and generates a new XML document that includes the `CompanyName` element in the orders.</span></span>  
  
 <span data-ttu-id="a62a9-115">예제에서는 쿼리를 실행하기 전에 문서가 [샘플 XSD 파일: Customers 및 Orders](../../../../csharp/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders1.md)의 스키마를 준수하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a62a9-115">Before executing the query, the example validates that the document complies with the schema in [Sample XSD File: Customers and Orders](../../../../csharp/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders1.md).</span></span> <span data-ttu-id="a62a9-116">이에 따라 조인 절이 항상 작동하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a62a9-116">This ensures that the join clause will always work.</span></span>  
  
 <span data-ttu-id="a62a9-117">이 쿼리에서는 먼저 모든 `Customer` 요소를 검색하고 `Order` 요소와 조인한 다음</span><span class="sxs-lookup"><span data-stu-id="a62a9-117">This query first retrieves all `Customer` elements, and then joins them to the `Order` elements.</span></span> <span data-ttu-id="a62a9-118">`CustomerID`가 "K"보다 큰 고객의 주문만 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a62a9-118">It selects only the orders for customers with a `CustomerID` greater than "K".</span></span> <span data-ttu-id="a62a9-119">그런 다음 각 주문의 고객 정보가 포함된 새 `Order` 요소를 프로젝션합니다.</span><span class="sxs-lookup"><span data-stu-id="a62a9-119">It then projects a new `Order` element that contains the customer information within each order.</span></span>  
  
 <span data-ttu-id="a62a9-120">이 예제에서는 XML 문서 [샘플 XML 파일: 고객 및 주문(LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml-2.md)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a62a9-120">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span></span>  
  
 <span data-ttu-id="a62a9-121">이 예제에서는 XSD 스키마로 [샘플 XSD 파일: Customers 및 Orders](../../../../csharp/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders1.md)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a62a9-121">This example uses the following XSD schema: [Sample XSD File: Customers and Orders](../../../../csharp/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders1.md).</span></span>  
  
 <span data-ttu-id="a62a9-122">이런 방식의 조인은 성능이 좋지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a62a9-122">Note that joining in this fashion will not perform very well.</span></span> <span data-ttu-id="a62a9-123">조인은 선형 검색을 통해 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="a62a9-123">Joins are performed via a linear search.</span></span> <span data-ttu-id="a62a9-124">성능에 도움이 될 해시 테이블이나 인덱스는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a62a9-124">There are no hash tables or indexes to help with performance.</span></span>  
  
```csharp  
XmlSchemaSet schemas = new XmlSchemaSet();  
schemas.Add("", "CustomersOrders.xsd");  
  
Console.Write("Attempting to validate, ");  
XDocument custOrdDoc = XDocument.Load("CustomersOrders.xml");  
  
bool errors = false;  
custOrdDoc.Validate(schemas, (o, e) =>  
                     {  
                         Console.WriteLine("{0}", e.Message);  
                         errors = true;  
                     });  
Console.WriteLine("custOrdDoc {0}", errors ? "did not validate" : "validated");  
  
if (!errors)  
{  
    // Join customers and orders, and create a new XML document with  
    // a different shape.  
  
    // The new document contains orders only for customers with a  
    // CustomerID > 'K'  
    XElement custOrd = custOrdDoc.Element("Root");  
    XElement newCustOrd = new XElement("Root",  
        from c in custOrd.Element("Customers").Elements("Customer")  
        join o in custOrd.Element("Orders").Elements("Order")  
                   on (string)c.Attribute("CustomerID") equals  
                      (string)o.Element("CustomerID")  
        where ((string)c.Attribute("CustomerID")).CompareTo("K") > 0  
        select new XElement("Order",  
            new XElement("CustomerID", (string)c.Attribute("CustomerID")),  
            new XElement("CompanyName", (string)c.Element("CompanyName")),  
            new XElement("ContactName", (string)c.Element("ContactName")),  
            new XElement("EmployeeID", (string)o.Element("EmployeeID")),  
            new XElement("OrderDate", (DateTime)o.Element("OrderDate"))  
        )  
    );  
    Console.WriteLine(newCustOrd);  
}  
```  
  
 <span data-ttu-id="a62a9-125">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a62a9-125">This code produces the following output:</span></span>  
  
```  
Attempting to validate, custOrdDoc validated  
<Root>  
  <Order>  
    <CustomerID>LAZYK</CustomerID>  
    <CompanyName>Lazy K Kountry Store</CompanyName>  
    <ContactName>John Steel</ContactName>  
    <EmployeeID>1</EmployeeID>  
    <OrderDate>1997-03-21T00:00:00</OrderDate>  
  </Order>  
  <Order>  
    <CustomerID>LAZYK</CustomerID>  
    <CompanyName>Lazy K Kountry Store</CompanyName>  
    <ContactName>John Steel</ContactName>  
    <EmployeeID>8</EmployeeID>  
    <OrderDate>1997-05-22T00:00:00</OrderDate>  
  </Order>  
  <Order>  
    <CustomerID>LETSS</CustomerID>  
    <CompanyName>Let's Stop N Shop</CompanyName>  
    <ContactName>Jaime Yorres</ContactName>  
    <EmployeeID>1</EmployeeID>  
    <OrderDate>1997-06-25T00:00:00</OrderDate>  
  </Order>  
  <Order>  
    <CustomerID>LETSS</CustomerID>  
    <CompanyName>Let's Stop N Shop</CompanyName>  
    <ContactName>Jaime Yorres</ContactName>  
    <EmployeeID>8</EmployeeID>  
    <OrderDate>1997-10-27T00:00:00</OrderDate>  
  </Order>  
  <Order>  
    <CustomerID>LETSS</CustomerID>  
    <CompanyName>Let's Stop N Shop</CompanyName>  
    <ContactName>Jaime Yorres</ContactName>  
    <EmployeeID>6</EmployeeID>  
    <OrderDate>1997-11-10T00:00:00</OrderDate>  
  </Order>  
  <Order>  
    <CustomerID>LETSS</CustomerID>  
    <CompanyName>Let's Stop N Shop</CompanyName>  
    <ContactName>Jaime Yorres</ContactName>  
    <EmployeeID>4</EmployeeID>  
    <OrderDate>1998-02-12T00:00:00</OrderDate>  
  </Order>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a62a9-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a62a9-126">See Also</span></span>  
 [<span data-ttu-id="a62a9-127">고급 쿼리 기술(LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="a62a9-127">Advanced Query Techniques (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/advanced-query-techniques-linq-to-xml.md)
