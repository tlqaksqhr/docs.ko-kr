---
title: "방법: 요소의 단순 값 검색(C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 924a2699-72f6-4be1-aaa6-de62f8ec73b9
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 5dcbe3faa457a4880a85f5827d0e5c4808b6a44b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-retrieve-the-shallow-value-of-an-element-c"></a><span data-ttu-id="a7166-102">방법: 요소의 단순 값 검색(C#)</span><span class="sxs-lookup"><span data-stu-id="a7166-102">How to: Retrieve the Shallow Value of an Element (C#)</span></span>
<span data-ttu-id="a7166-103">이 항목에서는 요소의 부분 값을 가져오는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a7166-103">This topic shows how to get the shallow value of an element.</span></span> <span data-ttu-id="a7166-104">단일 문자열로 연결된 모든 하위 요소의 값을 포함하는 상세 값과 달리 부분 값은 특정 요소의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="a7166-104">The shallow value is the value of the specific element only, as opposed to the deep value, which includes the values of all descendent elements concatenated into a single string.</span></span>  
  
 <span data-ttu-id="a7166-105">캐스팅을 사용하거나 <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> 속성을 사용하여 요소 값을 검색하는 경우에는 상세 값이 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7166-105">When you retrieve an element value by using either casting or the <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> property, you retrieve the deep value.</span></span> <span data-ttu-id="a7166-106">부분 값을 검색하려면 다음 예제와 같이 `ShallowValue` 확장 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a7166-106">To retrieve the shallow value, you can use the `ShallowValue` extension method, as shown in the follwing example.</span></span> <span data-ttu-id="a7166-107">요소의 내용을 기준으로 요소를 선택하려는 경우에는 부분 값을 검색하는 것이 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="a7166-107">Retrieving the shallow value is useful when you want to select elements based on their content.</span></span>  
  
 <span data-ttu-id="a7166-108">다음 예제에서는 요소의 부분 값을 검색하는 확장 메서드를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="a7166-108">The following example declares an extension method that retrieves the shallow value of an element.</span></span> <span data-ttu-id="a7166-109">그런 다음 쿼리에 해당 확장명 메서드를 사용하여 계산된 값을 포함하는 모든 요소를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="a7166-109">It then uses the extension method in a query to list all elements that contain a calculated value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a7166-110">예제</span><span class="sxs-lookup"><span data-stu-id="a7166-110">Example</span></span>  
 <span data-ttu-id="a7166-111">아래에 있는 Report.xml 텍스트 파일은 이 예제의 소스입니다.</span><span class="sxs-lookup"><span data-stu-id="a7166-111">The following text file, Report.xml, is the source for this example.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<Report>  
  <Section>  
    <Heading>  
      <Column Name="CustomerId">=Customer.CustomerId.Heading</Column>  
      <Column Name="Name">=Customer.Name.Heading</Column>  
    </Heading>  
    <Detail>  
      <Column Name="CustomerId">=Customer.CustomerId</Column>  
      <Column Name="Name">=Customer.Name</Column>  
    </Detail>  
  </Section>  
</Report>  
```  
  
```csharp  
public static class MyExtensions  
{  
    public static string ShallowValue(this XElement xe)  
    {  
        return xe  
               .Nodes()  
               .OfType<XText>()  
               .Aggregate(new StringBuilder(),  
                          (s, c) => s.Append(c),  
                          s => s.ToString());  
    }  
}  
  
class Program  
{  
    static void Main(string[] args)  
    {  
        XElement root = XElement.Load("Report.xml");  
  
        IEnumerable<XElement> query = from el in root.Descendants()  
                                      where el.ShallowValue().StartsWith("=")  
                                      select el;  
  
        foreach (var q in query)  
        {  
            Console.WriteLine("{0}{1}{2}",  
                q.Name.ToString().PadRight(8),  
                q.Attribute("Name").ToString().PadRight(20),  
                q.ShallowValue());  
        }  
    }  
}  
```  
  
 <span data-ttu-id="a7166-112">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a7166-112">This example produces the following output:</span></span>  
  
```  
Column  Name="CustomerId"   =Customer.CustomerId.Heading  
Column  Name="Name"         =Customer.Name.Heading  
Column  Name="CustomerId"   =Customer.CustomerId  
Column  Name="Name"         =Customer.Name  
```  
  
## <a name="see-also"></a><span data-ttu-id="a7166-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a7166-113">See Also</span></span>  
 [<span data-ttu-id="a7166-114">LINQ to XML 축(C#)</span><span class="sxs-lookup"><span data-stu-id="a7166-114">LINQ to XML Axes (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes.md)
