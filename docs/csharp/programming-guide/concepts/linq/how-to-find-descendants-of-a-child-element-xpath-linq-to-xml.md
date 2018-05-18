---
title: '방법: 자식 요소의 하위 항목 찾기(XPath 및 LINQ to XML)(C#)'
ms.date: 07/20/2015
ms.assetid: 505b7512-bb8b-4f85-abbf-491f039c961e
ms.openlocfilehash: 548ec3f76a17ef8575e7e5e90ef4cbf8d2666a64
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-find-descendants-of-a-child-element-xpath-linq-to-xml-c"></a>방법: 자식 요소의 하위 항목 찾기(XPath 및 LINQ to XML)(C#)
이 항목에서는 특정 이름을 가진 자식 요소의 하위 요소를 가져오는 방법을 보여 줍니다.  
  
 XPath 식은 다음과 같습니다.  
  
 `./Paragraph//Text/text()`  
  
## <a name="example"></a>예  
 이 예제에서는 워드 프로세서 문서의 XML 표현에서 텍스트를 추출하는 경우의 문제를 시뮬레이션합니다. 먼저 모든 `Paragraph` 요소를 선택한 다음 각 `Text` 요소의 모든 `Paragraph` 하위 요소를 선택합니다. `Text` 요소의 하위 `Comment` 요소는 선택하지 않습니다.  
  
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
  
 이 예제는 다음과 같은 출력을 생성합니다.  
  
```  
Results are identical  
This is the start of a sentence.  This is a second sentence.  
```  
  
## <a name="see-also"></a>참고 항목  
 [XPath 사용자를 위한 LINQ to XML(C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
