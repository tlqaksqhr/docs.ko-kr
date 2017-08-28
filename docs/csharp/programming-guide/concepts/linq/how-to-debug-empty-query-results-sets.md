---
title: "방법: 빈 쿼리 결과 집합 디버그(C#)"
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
ms.assetid: b569f0dc-425e-45a6-acbf-770fb761c981
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 78c6d612e11f50bedf8f1c2e9826775494faa465
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-debug-empty-query-results-sets-c"></a>방법: 빈 쿼리 결과 집합 디버그(C#)
XML 트리를 쿼리할 때 가장 일반적인 문제 중 하나는 XML 트리에 기본 네임스페이스가 있으면 개발자가 경우에 따라 XML이 네임스페이스에 없는 것처럼 쿼리를 작성하는 것입니다.  
  
 이 항목의 첫 번째 예제 집합에서는 기본 네임스페이스의 XML이 로드되고 적절하지 않게 쿼리되는 일반적인 방법을 보여 줍니다.  
  
 두 번째 예제 집합에서는 네임스페이스의 XML을 쿼리할 수 있도록 필요한 수정을 하는 방법을 보여 줍니다.  
  
 자세한 내용은 [XML 네임스페이스 작업(C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 이 예제에서는 네임스페이스에 XML을 만들고 빈 결과 집합을 반환하는 쿼리를 만드는 방법을 보여 줍니다.  
  
```csharp  
XElement root = XElement.Parse(  
@"<Root xmlns='http://www.adventure-works.com'>  
    <Child>1</Child>  
    <Child>2</Child>  
    <Child>3</Child>  
    <AnotherChild>4</AnotherChild>  
    <AnotherChild>5</AnotherChild>  
    <AnotherChild>6</AnotherChild>  
</Root>");  
IEnumerable<XElement> c1 =  
    from el in root.Elements("Child")  
    select el;  
Console.WriteLine("Result set follows:");  
foreach (XElement el in c1)  
    Console.WriteLine((int)el);  
Console.WriteLine("End of result set");  
```  
  
 이 예제의 결과는 다음과 같습니다.  
  
```  
Result set follows:  
End of result set  
```  
  
## <a name="example"></a>예제  
 이 예제에서는 네임스페이스에 XML을 만들고 제대로 코딩된 쿼리를 만드는 방법을 보여 줍니다.  
  
 해결 방법은 <xref:System.Xml.Linq.XNamespace> 개체를 선언하고 초기화하여 <xref:System.Xml.Linq.XName> 개체를 지정할 때 사용하는 것입니다. 이 경우 <xref:System.Xml.Linq.XElement.Elements%2A> 메서드의 인수는 <xref:System.Xml.Linq.XName> 개체입니다.  
  
```csharp  
XElement root = XElement.Parse(  
@"<Root xmlns='http://www.adventure-works.com'>  
    <Child>1</Child>  
    <Child>2</Child>  
    <Child>3</Child>  
    <AnotherChild>4</AnotherChild>  
    <AnotherChild>5</AnotherChild>  
    <AnotherChild>6</AnotherChild>  
</Root>");  
XNamespace aw = "http://www.adventure-works.com";  
IEnumerable<XElement> c1 =  
    from el in root.Elements(aw + "Child")  
    select el;  
Console.WriteLine("Result set follows:");  
foreach (XElement el in c1)  
    Console.WriteLine((int)el);  
Console.WriteLine("End of result set");  
```  
  
 이 예제의 결과는 다음과 같습니다.  
  
```  
Result set follows:  
1  
2  
3  
End of result set  
```  
  
## <a name="see-also"></a>참고 항목  
 [기본 쿼리(LINQ to XML)(C#)](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)

