---
title: '방법: 특정 요소 이름으로 하위 항목 찾기(C#)'
ms.date: 07/20/2015
ms.assetid: f684da20-bee9-47f5-9607-7e3fd7e67470
ms.openlocfilehash: f95551f0c1506a56474d497622b90090cc4c8865
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-find-descendants-with-a-specific-element-name-c"></a><span data-ttu-id="5a1c1-102">방법: 특정 요소 이름으로 하위 항목 찾기(C#)</span><span class="sxs-lookup"><span data-stu-id="5a1c1-102">How to: Find Descendants with a Specific Element Name (C#)</span></span>
<span data-ttu-id="5a1c1-103">특정 이름을 가진 모든 하위 요소를 찾으려는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a1c1-103">Sometimes you want to find all descendants with a particular name.</span></span> <span data-ttu-id="5a1c1-104">모든 하위 요소를 반복하는 코드를 작성할 수 있지만 <xref:System.Xml.Linq.XContainer.Descendants%2A> 축을 사용하는 것이 더 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="5a1c1-104">You could write code to iterate through all of the descendants, but it is easier to use the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5a1c1-105">예</span><span class="sxs-lookup"><span data-stu-id="5a1c1-105">Example</span></span>  
 <span data-ttu-id="5a1c1-106">다음 예제에서는 요소 이름에 따라 하위 요소를 찾는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5a1c1-106">The following example shows how to find descendants based on the element name.</span></span>  
  
```csharp  
XElement root = XElement.Parse(@"<root>  
  <para>  
    <r>  
      <t>Some text </t>  
    </r>  
    <n>  
      <r>  
        <t>that is broken up into </t>  
      </r>  
    </n>  
    <n>  
      <r>  
        <t>multiple segments.</t>  
      </r>  
    </n>  
  </para>  
</root>");  
IEnumerable<string> textSegs =  
    from seg in root.Descendants("t")  
    select (string)seg;  
  
string str = textSegs.Aggregate(new StringBuilder(),  
    (sb, i) => sb.Append(i),  
    sp => sp.ToString()  
);  
  
Console.WriteLine(str);  
```  
  
 <span data-ttu-id="5a1c1-107">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5a1c1-107">This code produces the following output:</span></span>  
  
```  
Some text that is broken up into multiple segments.  
```  
  
## <a name="example"></a><span data-ttu-id="5a1c1-108">예</span><span class="sxs-lookup"><span data-stu-id="5a1c1-108">Example</span></span>  
 <span data-ttu-id="5a1c1-109">다음 예제에서는 네임스페이스에 있는 XML에 대한 동일한 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5a1c1-109">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="5a1c1-110">자세한 내용은 [XML 네임스페이스 작업(C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5a1c1-110">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
```csharp  
XElement root = XElement.Parse(@"<root xmlns='http://www.adatum.com'>  
  <para>  
    <r>  
      <t>Some text </t>  
    </r>  
    <n>  
      <r>  
        <t>that is broken up into </t>  
      </r>  
    </n>  
    <n>  
      <r>  
        <t>multiple segments.</t>  
      </r>  
    </n>  
  </para>  
</root>");  
XNamespace ad = "http://www.adatum.com";  
IEnumerable<string> textSegs =  
    from seg in root.Descendants(ad + "t")  
    select (string)seg;  
  
string str = textSegs.Aggregate(new StringBuilder(),  
    (sb, i) => sb.Append(i),  
    sp => sp.ToString()  
);  
  
Console.WriteLine(str);  
```  
  
 <span data-ttu-id="5a1c1-111">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5a1c1-111">This code produces the following output:</span></span>  
  
```  
Some text that is broken up into multiple segments.  
```  
  
## <a name="see-also"></a><span data-ttu-id="5a1c1-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5a1c1-112">See Also</span></span>  
 <xref:System.Xml.Linq.XContainer.Descendants%2A>  
 [<span data-ttu-id="5a1c1-113">기본 쿼리(LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="5a1c1-113">Basic Queries (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
