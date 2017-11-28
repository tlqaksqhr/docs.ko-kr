---
title: "방법: 특정 요소 이름으로 하위 항목 찾기(C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: f684da20-bee9-47f5-9607-7e3fd7e67470
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b1cc45f07accd7ae6dcc530f0fd5a9078bce949d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-find-descendants-with-a-specific-element-name-c"></a><span data-ttu-id="004af-102">방법: 특정 요소 이름으로 하위 항목 찾기(C#)</span><span class="sxs-lookup"><span data-stu-id="004af-102">How to: Find Descendants with a Specific Element Name (C#)</span></span>
<span data-ttu-id="004af-103">특정 이름을 가진 모든 하위 요소를 찾으려는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="004af-103">Sometimes you want to find all descendants with a particular name.</span></span> <span data-ttu-id="004af-104">모든 하위 요소를 반복하는 코드를 작성할 수 있지만 <xref:System.Xml.Linq.XContainer.Descendants%2A> 축을 사용하는 것이 더 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="004af-104">You could write code to iterate through all of the descendants, but it is easier to use the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis.</span></span>  
  
## <a name="example"></a><span data-ttu-id="004af-105">예제</span><span class="sxs-lookup"><span data-stu-id="004af-105">Example</span></span>  
 <span data-ttu-id="004af-106">다음 예제에서는 요소 이름에 따라 하위 요소를 찾는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="004af-106">The following example shows how to find descendants based on the element name.</span></span>  
  
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
  
 <span data-ttu-id="004af-107">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="004af-107">This code produces the following output:</span></span>  
  
```  
Some text that is broken up into multiple segments.  
```  
  
## <a name="example"></a><span data-ttu-id="004af-108">예제</span><span class="sxs-lookup"><span data-stu-id="004af-108">Example</span></span>  
 <span data-ttu-id="004af-109">다음 예제에서는 네임스페이스에 있는 XML에 대한 동일한 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="004af-109">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="004af-110">자세한 내용은 [XML 네임스페이스 작업(C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="004af-110">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
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
  
 <span data-ttu-id="004af-111">이 코드의 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="004af-111">This code produces the following output:</span></span>  
  
```  
Some text that is broken up into multiple segments.  
```  
  
## <a name="see-also"></a><span data-ttu-id="004af-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="004af-112">See Also</span></span>  
 <xref:System.Xml.Linq.XContainer.Descendants%2A>  
 [<span data-ttu-id="004af-113">기본 쿼리(LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="004af-113">Basic Queries (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
