---
title: "방법: 자식 요소의 하위 항목 찾기(XPath 및 LINQ to XML)(C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 505b7512-bb8b-4f85-abbf-491f039c961e
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 873cfe6a725a932ac4616e7ccf0ea11e3f6479f5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-find-descendants-of-a-child-element-xpath-linq-to-xml-c"></a><span data-ttu-id="19c66-102">방법: 자식 요소의 하위 항목 찾기(XPath 및 LINQ to XML)(C#)</span><span class="sxs-lookup"><span data-stu-id="19c66-102">How to: Find Descendants of a Child Element (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="19c66-103">이 항목에서는 특정 이름을 가진 자식 요소의 하위 요소를 가져오는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="19c66-103">This topic shows how to get the descendant elements of a child element with a particular name.</span></span>  
  
 <span data-ttu-id="19c66-104">XPath 식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="19c66-104">The XPath expression is:</span></span>  
  
 `./Paragraph//Text/text()`  
  
## <a name="example"></a><span data-ttu-id="19c66-105">예제</span><span class="sxs-lookup"><span data-stu-id="19c66-105">Example</span></span>  
 <span data-ttu-id="19c66-106">이 예제에서는 워드 프로세서 문서의 XML 표현에서 텍스트를 추출하는 경우의 문제를 시뮬레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="19c66-106">This example simulates the problems of extracting text from an XML representation of a word processing document.</span></span> <span data-ttu-id="19c66-107">먼저 모든 `Paragraph` 요소를 선택한 다음 각 `Text` 요소의 모든 `Paragraph` 하위 요소를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="19c66-107">It first selects all `Paragraph` elements, and then it selects all `Text` descendant elements of each `Paragraph` element.</span></span> <span data-ttu-id="19c66-108">`Text` 요소의 하위 `Comment` 요소는 선택하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="19c66-108">This doesn't select the descendant `Text` elements of the `Comment` element.</span></span>  
  
```csharp  
XElement root = XElement.Parse(  
@"<Root>  
  <Paragraph>  
    <Text>This is the start of</Text>  
  </Paragraph>  
  <Comment>  
    <Text>This comment is not part of the paragraph text.</Text>  
  </Comment>  
  <Paragraph>  
    <Annotation Emphasis='true'>  
      <Text> a sentence.</Text>  
    </Annotation>  
  </Paragraph>  
  <Paragraph>  
    <Text>  This is a second sentence.</Text>  
  </Paragraph>  
</Root>");  
  
// LINQ to XML query  
string str1 =  
    root  
    .Elements("Paragraph")  
    .Descendants("Text")  
    .Select(s => s.Value)  
    .Aggregate(  
        new StringBuilder(),  
        (s, i) => s.Append(i),  
        s => s.ToString()  
    );  
  
// XPath expression  
string str2 =  
    ((IEnumerable)root.XPathEvaluate("./Paragraph//Text/text()"))  
    .Cast<XText>()  
    .Select(s => s.Value)  
    .Aggregate(  
        new StringBuilder(),  
        (s, i) => s.Append(i),  
        s => s.ToString()  
    );  
  
if (str1 == str2)  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
Console.WriteLine(str2);  
```  
  
 <span data-ttu-id="19c66-109">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="19c66-109">This example produces the following output:</span></span>  
  
```  
Results are identical  
This is the start of a sentence.  This is a second sentence.  
```  
  
## <a name="see-also"></a><span data-ttu-id="19c66-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="19c66-110">See Also</span></span>  
 [<span data-ttu-id="19c66-111">XPath 사용자를 위한 LINQ to XML(C#)</span><span class="sxs-lookup"><span data-stu-id="19c66-111">LINQ to XML for XPath Users (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
