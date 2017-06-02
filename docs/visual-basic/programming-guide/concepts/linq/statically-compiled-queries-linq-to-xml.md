---
title: "정적으로 컴파일된 쿼리 (LINQ to XML) (Visual Basic) | Microsoft 문서"
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
ms.assetid: 3f4825c7-c3b0-48da-ba4e-8e97fb2a2f34
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 2ea8e71acf861b93a21296c74254b3ca4d977d0a
ms.contentlocale: ko-kr
ms.lasthandoff: 03/13/2017


---
# <a name="statically-compiled-queries-linq-to-xml-visual-basic"></a>정적으로 컴파일된 쿼리 (LINQ to XML) (Visual Basic)
이점 중 하나는 가장 중요 한 성능 LINQ to XML을 반대인 <xref:System.Xml.XmlDocument>는 LINQ to XML의에서 쿼리가 정적으로 컴파일된다는 반면 XPath 쿼리는 런타임에 해석 되어야 합니다.</xref:System.Xml.XmlDocument> 이 기능은 LINQ to XML에 기본 제공되므로 이를 활용하기 위해 별도의 단계를 수행할 필요는 없습니다. 그러나 이 두 가지 기술 중 하나를 선택해야 하는 경우를 위해 그 차이를 알고 있는 것이 좋습니다. 이 항목에서는 그 차이에 대해 설명합니다.  
  
## <a name="statically-compiled-queries-vs-xpath"></a>정적으로 컴파일된 쿼리와 XPath  
 다음 예제에서는 지정된 이름을 가진 하위 요소와 지정된 값을 가진 특성이 포함된 하위 요소를 가져오는 방법을 보여 줍니다.  
  
 다음은 이에 해당하는 XPath 식입니다.  
  
```  
//Address[@Type='Shipping']  
```  
  
```vb  
Dim po = XDocument.Load("PurchaseOrders.xml")  
  
Dim list1 = From el In po.Descendants("Address")  
            Where el.@Type = "Shipping"  
  
For Each el In list1  
    Console.WriteLine(el)  
Next  
```  
  
 이 예제의 쿼리 식은 메서드 기반 쿼리 구문에 대한 컴파일러로 다시 작성되었습니다. 메서드 기반 쿼리 구문으로 작성된 다음 예제는 이전 쿼리에서와 같은 결과를 생성합니다.  
  
```vb  
Dim po = XDocument.Load("PurchaseOrders.xml")  
  
Dim list1 As IEnumerable(Of XElement) = po.Descendants("Address").Where(Function(el) el.@Type = "Shipping")  
  
For Each el In list1  
    Console.WriteLine(el)  
Next   
```  
  
 <xref:System.Linq.Enumerable.Where%2A>확장 메서드는.</xref:System.Linq.Enumerable.Where%2A> 자세한 내용은 참조 [확장 메서드](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md)합니다. 때문에 <xref:System.Linq.Enumerable.Where%2A>확장 메서드는 위의 쿼리는 다음과 같이 작성 된 것 처럼 컴파일됩니다:</xref:System.Linq.Enumerable.Where%2A>  
  
```vb  
Dim po = XDocument.Load("PurchaseOrders.xml")  
  
Dim list1 = Enumerable.Where(po.Descendants("Address"), Function(el) el.@Type = "Shipping")  
  
For Each el In list1  
    Console.WriteLine(el)  
Next  
```  
  
 이 예제의 결과는 위의 두 예제의 결과와 정확히 동일합니다. 이를 통해 쿼리가 정적으로 연결된 메서드 호출로 효과적으로 컴파일되었음을 알 수 있습니다. 이 예제에서는 반복기의 지연된 실행 의미 체계를 결합하여 성능을 향상합니다. 반복기의 지연 된 실행 의미 체계에 대 한 자세한 내용은 참조 [지연 된 실행과 지연 계산은 LINQ to XML (Visual Basic)에서](../../../../visual-basic/programming-guide/concepts/linq/deferred-execution-and-lazy-evaluation-in-linq-to-xml.md)합니다.  
  
> [!NOTE]
>  이러한 예제는 컴파일러에서 작성할 수 있는 대표적인 코드 예제입니다. 실제 구현은 이러한 예제와 약간 다를 수 있으나 성능은 이러한 예제와 같거나 매우 유사할 것입니다.  
  
## <a name="executing-xpath-expressions-with-xmldocument"></a>XmlDocument를 사용하여 XPath 식 실행  
 다음 예제에서는 <xref:System.Xml.XmlDocument>는 이전 예제와 동일한 결과를 얻는:</xref:System.Xml.XmlDocument>  
  
```vb  
Dim reader = Xml.XmlReader.Create("PurchaseOrders.xml")  
Dim doc As New Xml.XmlDocument()  
doc.Load(reader)  
Dim nl As Xml.XmlNodeList = doc.SelectNodes(".//Address[@Type='Shipping']")  
For Each n As Xml.XmlNode In nl  
    Console.WriteLine(n.OuterXml)  
Next  
reader.Close()  
```  
  
 이 쿼리는 LINQ to XML;를 사용 하는 예제와 동일한 출력 반환 유일한 차이점은 XML을 들여쓰기로 LINQ to XML에서 처리 하는 반면 <xref:System.Xml.XmlDocument>하지 않습니다.</xref:System.Xml.XmlDocument>  
  
 그러나는 <xref:System.Xml.XmlDocument>방법은 일반적으로 수행 되지 않습니다 LINQ to XML 하기 때문에 <xref:System.Xml.XmlNode.SelectNodes%2A>메서드에 다음을 수행 해야 내부적으로 호출 될 때마다:</xref:System.Xml.XmlNode.SelectNodes%2A> </xref:System.Xml.XmlDocument>  
  
-   XPath 식이 포함된 문자열을 구문 분석하여 문자열을 토큰으로 나눕니다.  
  
-   XPath 식이 올바른지 확인하기 위해 토큰의 유효성을 검사합니다.  
  
-   식을 내부 식 트리로 변환합니다.  
  
-   노드를 반복하여 식 계산 결과를 기준으로 결과 집합에 맞는 노드를 선택합니다.  
  
 이는 이에 해당하는 LINQ to XML 쿼리에서 수행하는 작업보다 훨씬 많습니다. 구체적인 성능 차이 다양 한 유형의 쿼리를 다르지만 일반적 LINQ to XML 쿼리의 더 적은 작업을 수행을 따라서 보다 성능이 우수, <xref:System.Xml.XmlDocument>.</xref:System.Xml.XmlDocument> 를 사용 하 여 XPath 식을 평가 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [성능 (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/performance-linq-to-xml.md)

