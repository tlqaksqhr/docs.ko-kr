---
title: "방법: 중간 값 계산(C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 7fd3001f-f8f9-4bce-879f-d4c7af8a04fe
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 93aa3683315b88c0ca85abc0eaff3efc8a15452a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-calculate-intermediate-values-c"></a><span data-ttu-id="635cd-102">방법: 중간 값 계산(C#)</span><span class="sxs-lookup"><span data-stu-id="635cd-102">How to: Calculate Intermediate Values (C#)</span></span>
<span data-ttu-id="635cd-103">이 예제에서는 정렬, 필터링 및 선택에 사용할 수 있는 중간 값을 계산하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="635cd-103">This example shows how to calculate intermediate values that can be used in sorting, filtering, and selecting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="635cd-104">예제</span><span class="sxs-lookup"><span data-stu-id="635cd-104">Example</span></span>  
 <span data-ttu-id="635cd-105">다음 예제에서는 `Let` 절을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="635cd-105">The following example uses the `Let` clause.</span></span>  
  
 <span data-ttu-id="635cd-106">이 예제에서는 XML 문서 [샘플 XML 파일: 숫자 데이터(LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="635cd-106">This example uses the following XML document: [Sample XML File: Numerical Data (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("Data.xml");  
IEnumerable<decimal> extensions =  
    from el in root.Elements("Data")  
    let extension = (decimal)el.Element("Quantity") * (decimal)el.Element("Price")  
    where extension >= 25  
    orderby extension  
    select extension;  
foreach (decimal ex in extensions)  
    Console.WriteLine(ex);  
```  
  
 <span data-ttu-id="635cd-107">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="635cd-107">This code produces the following output:</span></span>  
  
```  
55.92  
73.50  
89.99  
198.00  
435.00  
```  
  
## <a name="example"></a><span data-ttu-id="635cd-108">예제</span><span class="sxs-lookup"><span data-stu-id="635cd-108">Example</span></span>  
 <span data-ttu-id="635cd-109">다음 예제에서는 네임스페이스에 있는 XML에 대한 동일한 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="635cd-109">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="635cd-110">자세한 내용은 [XML 네임스페이스 작업(C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="635cd-110">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
 <span data-ttu-id="635cd-111">이 예제에서는 XML 문서 [샘플 XML 파일: 네임스페이스의 숫자 데이터](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-numerical-data-in-a-namespace.md)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="635cd-111">This example uses the following XML document: [Sample XML File: Numerical Data in a Namespace](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-numerical-data-in-a-namespace.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("DataInNamespace.xml");  
XNamespace ad = "http://www.adatum.com";  
IEnumerable<decimal> extensions =  
    from el in root.Elements(ad + "Data")  
    let extension = (decimal)el.Element(ad + "Quantity") * (decimal)el.Element(ad + "Price")  
    where extension >= 25  
    orderby extension  
    select extension;  
foreach (decimal ex in extensions)  
    Console.WriteLine(ex);  
```  
  
 <span data-ttu-id="635cd-112">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="635cd-112">This code produces the following output:</span></span>  
  
```  
55.92  
73.50  
89.99  
198.00  
435.00  
```  
  
## <a name="see-also"></a><span data-ttu-id="635cd-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="635cd-113">See Also</span></span>  
 [<span data-ttu-id="635cd-114">기본 쿼리(LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="635cd-114">Basic Queries (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
