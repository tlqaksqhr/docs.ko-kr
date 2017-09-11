---
title: "방법: 프로젝션 형식 제어(C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: e4db6b7e-4cc9-4c8f-af85-94acf32aa348
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: e681fbffe681237d0b0ac3d7a161180e478172f9
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-control-the-type-of-a-projection-c"></a><span data-ttu-id="6252a-102">방법: 프로젝션 형식 제어(C#)</span><span class="sxs-lookup"><span data-stu-id="6252a-102">How to: Control the Type of a Projection (C#)</span></span>
<span data-ttu-id="6252a-103">프로젝션은 데이터 집합을 하나 가져와서 필터링하고 모양을 변경하며 형식까지도 변경하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="6252a-103">Projection is the process of taking one set of data, filtering it, changing its shape, and even changing its type.</span></span> <span data-ttu-id="6252a-104">대부분의 쿼리 식은 프로젝션을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="6252a-104">Most query expressions perform projections.</span></span> <span data-ttu-id="6252a-105">이 단원에 나와 있는 대부분의 쿼리 식은 <xref:System.Collections.Generic.IEnumerable%601>의 <xref:System.Xml.Linq.XElement>로 확인되지만 다른 형식의 컬렉션을 만들기 위해 프로젝션의 형식을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6252a-105">Most of the query expressions shown in this section evaluate to <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>, but you can control the type of the projection to create collections of other types.</span></span> <span data-ttu-id="6252a-106">이 항목에서는 프로젝션의 형식을 제어하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6252a-106">This topic shows how to do this.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6252a-107">예제</span><span class="sxs-lookup"><span data-stu-id="6252a-107">Example</span></span>  
 <span data-ttu-id="6252a-108">다음 예제에서는 새 형식 `Customer`를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="6252a-108">The following example defines a new type, `Customer`.</span></span> <span data-ttu-id="6252a-109">쿼리 식은 `Customer` 절에서 새 `Select` 개체를 인스턴스화합니다.</span><span class="sxs-lookup"><span data-stu-id="6252a-109">The query expression then instantiates new `Customer` objects in the `Select` clause.</span></span> <span data-ttu-id="6252a-110">이에 따라 쿼리 식의 형식이 <xref:System.Collections.Generic.IEnumerable%601>의 `Customer`이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6252a-110">This causes the type of the query expression to be <xref:System.Collections.Generic.IEnumerable%601> of `Customer`.</span></span>  
  
 <span data-ttu-id="6252a-111">이 예제에서는 XML 문서 [샘플 XML 파일: 고객 및 주문(LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml-2.md)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6252a-111">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span></span>  
  
```csharp  
public class Customer  
{  
    private string customerID;  
    public string CustomerID{ get{return customerID;} set{customerID = value;}}  
  
    private string companyName;  
    public string CompanyName{ get{return companyName;} set{companyName = value;}}  
  
    private string contactName;  
    public string ContactName { get{return contactName;} set{contactName = value;}}  
  
    public Customer(string customerID, string companyName, string contactName)  
    {  
        CustomerID = customerID;  
        CompanyName = companyName;  
        ContactName = contactName;  
    }  
  
    public override string ToString()  
    {  
        return String.Format("{0}:{1}:{2}", this.customerID, this.companyName, this.contactName);  
    }  
}  
  
class Program  
{  
    static void Main(string[] args)  
    {  
        XElement custOrd = XElement.Load("CustomersOrders.xml");  
        IEnumerable<Customer> custList =  
            from el in custOrd.Element("Customers").Elements("Customer")  
            select new Customer(  
                (string)el.Attribute("CustomerID"),  
                (string)el.Element("CompanyName"),  
                (string)el.Element("ContactName")  
            );  
        foreach (Customer cust in custList)  
            Console.WriteLine(cust);  
    }  
}  
```  
  
 <span data-ttu-id="6252a-112">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6252a-112">This code produces the following output:</span></span>  
  
```  
GREAL:Great Lakes Food Market:Howard Snyder  
HUNGC:Hungry Coyote Import Store:Yoshi Latimer  
LAZYK:Lazy K Kountry Store:John Steel  
LETSS:Let's Stop N Shop:Jaime Yorres  
```  
  
## <a name="see-also"></a><span data-ttu-id="6252a-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6252a-113">See Also</span></span>  
 <span data-ttu-id="6252a-114"><xref:System.Linq.Enumerable.Select%2A></span><span class="sxs-lookup"><span data-stu-id="6252a-114"><xref:System.Linq.Enumerable.Select%2A></span></span>   
 [<span data-ttu-id="6252a-115">프로젝션 및 변환(LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="6252a-115">Projections and Transformations (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)

