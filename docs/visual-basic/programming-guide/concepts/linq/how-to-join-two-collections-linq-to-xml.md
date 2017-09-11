---
title: "방법: 두 컬렉션 (LINQ to XML) 조인 (Visual Basic) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 5a5758d4-906b-4285-908d-5b930db192e6
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: b336337d068799a68fd84d41be5e265cc6486171
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017


---
# <a name="how-to-join-two-collections-linq-to-xml-visual-basic"></a><span data-ttu-id="ec497-102">방법: 두 컬렉션 (LINQ to XML) 조인 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ec497-102">How to: Join Two Collections (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="ec497-103">XML 문서의 요소나 특성은 때때로 다른 요소나 특성을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec497-103">An element or attribute in an XML document can sometimes refer to another element or attribute.</span></span> <span data-ttu-id="ec497-104">예를 들어는 [샘플 XML 파일: Customers 및 Orders (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md) XML 문서에는 고객 목록과 주문 목록이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec497-104">For example, the [Sample XML File: Customers and Orders (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md) XML document contains a list of customers and a list of orders.</span></span> <span data-ttu-id="ec497-105">각 `Customer` 요소에는 `CustomerID` 특성이 포함되어 있고,</span><span class="sxs-lookup"><span data-stu-id="ec497-105">Each `Customer` element contains a `CustomerID` attribute.</span></span> <span data-ttu-id="ec497-106">각 `Order` 요소에는 `CustomerID` 요소가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec497-106">Each `Order` element contains a `CustomerID` element.</span></span> <span data-ttu-id="ec497-107">각 주문의 `CustomerID` 요소는 고객의 `CustomerID` 특성을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="ec497-107">The `CustomerID` element in each order refers to the `CustomerID` attribute in a customer.</span></span>  
  
 <span data-ttu-id="ec497-108">항목 [샘플 XSD 파일: Customers 및 Orders](../../../../visual-basic/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders.md) 이 문서의 유효성을 검사 하는 데 사용할 수 있는 XSD가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec497-108">The topic [Sample XSD File: Customers and Orders](../../../../visual-basic/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders.md) contains an XSD that can be used to validate this document.</span></span> <span data-ttu-id="ec497-109">이 항목에서는 XSD의 `xs:key` 및 `xs:keyref` 기능을 사용하여 `CustomerID` 요소의 `Customer` 특성을 키로 설정하고 각 `CustomerID` 요소의 `Order` 요소와 각 `CustomerID` 요소의 `Customer` 특성 간 관계를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ec497-109">It uses the `xs:key` and `xs:keyref` features of XSD to establish that the `CustomerID` attribute of the `Customer` element is a key, and to establish a relationship between the `CustomerID` element in each `Order` element and the `CustomerID` attribute in each `Customer` element.</span></span>  
  
 <span data-ttu-id="ec497-110">[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]에서는 `Join` 절을 사용하여 이 관계를 이용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec497-110">With [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], you can take advantage of this relationship by using the `Join` clause.</span></span>  
  
 <span data-ttu-id="ec497-111">사용 가능한 인덱스가 없기 때문에 이러한 조인의 런타임 성능은 좋지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ec497-111">Note that because there is no index available, such joining will have poor runtime performance.</span></span>  
  
 <span data-ttu-id="ec497-112">에 대 한 자세한 내용을 보려면 `Join`, 참조 [조인 작업 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/join-operations.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ec497-112">For more detailed information about `Join`, see [Join Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/join-operations.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ec497-113">예제</span><span class="sxs-lookup"><span data-stu-id="ec497-113">Example</span></span>  
 <span data-ttu-id="ec497-114">다음 예제에서는 `Customer` 요소와 `Order` 요소를 조인하고 주문의 `CompanyName` 요소가 포함된 새 XML 문서를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ec497-114">The following example joins the `Customer` elements to the `Order` elements, and generates a new XML document that includes the `CompanyName` element in the orders.</span></span>  
  
 <span data-ttu-id="ec497-115">쿼리를 실행 하기 전에 확인 하는 예제 문서에서 스키마를 준수 하는지 [샘플 XSD 파일: Customers 및 Orders](../../../../visual-basic/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ec497-115">Before executing the query, the example validates that the document complies with the schema in [Sample XSD File: Customers and Orders](../../../../visual-basic/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders.md).</span></span> <span data-ttu-id="ec497-116">이에 따라 조인 절이 항상 작동하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec497-116">This ensures that the join clause will always work.</span></span>  
  
 <span data-ttu-id="ec497-117">이 쿼리에서는 먼저 모든 `Customer` 요소를 검색하고 `Order` 요소와 조인한 다음</span><span class="sxs-lookup"><span data-stu-id="ec497-117">This query first retrieves all `Customer` elements, and then joins them to the `Order` elements.</span></span> <span data-ttu-id="ec497-118">`CustomerID`가 "K"보다 큰 고객의 주문만 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ec497-118">It selects only the orders for customers with a `CustomerID` greater than "K".</span></span> <span data-ttu-id="ec497-119">그런 다음 각 주문의 고객 정보가 포함된 새 `Order` 요소를 프로젝션합니다.</span><span class="sxs-lookup"><span data-stu-id="ec497-119">It then projects a new `Order` element that contains the customer information within each order.</span></span>  
  
 <span data-ttu-id="ec497-120">이 예제에서는 다음 XML 문서: [샘플 XML 파일: Customers 및 Orders (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ec497-120">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="ec497-121">이 예제에서는 다음 XSD 스키마를 사용 하 여: [샘플 XSD 파일: Customers 및 Orders](../../../../visual-basic/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ec497-121">This example uses the following XSD schema: [Sample XSD File: Customers and Orders](../../../../visual-basic/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders.md).</span></span>  
  
 <span data-ttu-id="ec497-122">이런 방식의 조인은 성능이 좋지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ec497-122">Note that joining in this fashion will not perform very well.</span></span> <span data-ttu-id="ec497-123">조인은 선형 검색을 통해 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec497-123">Joins are performed via a linear search.</span></span> <span data-ttu-id="ec497-124">성능에 도움이 될 해시 테이블이나 인덱스는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ec497-124">There are no hash tables or indexes to help with performance.</span></span>  
  
```vb  
Public Class Program  
    Public Shared errors As Boolean = False  
  
    Public Shared Function LamValidEvent(ByVal o As Object, _  
                 ByVal e As ValidationEventArgs) As Boolean  
        Console.WriteLine("{0}", e.Message)  
        errors = True  
    End Function  
  
    Shared Sub Main()  
        Dim schemas As New XmlSchemaSet()  
        schemas.Add("", "CustomersOrders.xsd")  
  
        Console.Write("Attempting to validate, ")  
        Dim custOrdDoc As XDocument = XDocument.Load("CustomersOrders.xml")  
  
        custOrdDoc.Validate(schemas, Function(o, e) LamValidEvent(0, e))  
        If errors Then  
            Console.WriteLine("custOrdDoc did not validate")  
        Else  
            Console.WriteLine("custOrdDoc validated")  
        End If  
  
        If Not errors Then  
            'Join customers and orders, and create a new XML document with  
            ' a different shape.  
            'The new document contains orders only for customers with a  
            ' CustomerID > 'K'.  
            Dim custOrd As XElement = custOrdDoc.<Root>.FirstOrDefault  
            Dim newCustOrd As XElement = _  
                <Root>  
                    <%= From c In custOrd.<Customers>.<Customer> _  
                        Join o In custOrd.<Orders>.<Order> _  
                        On c.@CustomerID Equals o.<CustomerID>.Value _  
                        Where c.@CustomerID.CompareTo("K") > 0 _  
                        Select _  
                        <Order>  
                            <CustomerID><%= c.@CustomerID %></CustomerID>  
                            <%= c.<CompanyName> %>  
                            <%= c.<ContactName> %>  
                            <%= o.<EmployeeID> %>  
                            <%= o.<OrderDate> %>  
                        </Order> _  
                    %>  
                </Root>  
            Console.WriteLine(newCustOrd)  
        End If  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="ec497-125">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ec497-125">This code produces the following output:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ec497-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ec497-126">See Also</span></span>  
 [<span data-ttu-id="ec497-127">고급 쿼리 기술 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ec497-127">Advanced Query Techniques (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/advanced-query-techniques-linq-to-xml.md)
