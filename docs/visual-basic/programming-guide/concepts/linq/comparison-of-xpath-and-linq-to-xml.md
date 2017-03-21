---
title: "XPath 및 LINQ to 변환을 XML1 비교 | Microsoft 문서"
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
ms.assetid: c3fd07c1-6761-4e4b-8eb1-ddd780ed8d44
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: e9601c51468fdf5adab8e521f8f89ee7f2e12869
ms.lasthandoff: 03/13/2017


---
# <a name="comparison-of-xpath-and-linq-to-xml"></a>XPath 및 LINQ to XML 비교
XPath와 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]은 유사한 기능을 제공합니다. XML 트리를 쿼리하여 결과를 요소 컬렉션, 특성 컬렉션, 노드 컬렉션 또는 요소나 특성의 값으로 반환하는 데 사용할 수 있습니다. 하지만 차이점도 있습니다.  
  
## <a name="differences-between-xpath-and-linq-to-xml"></a>XPath와 LINQ to XML의 차이점  
 XPath는 새 형식의 프로젝션을 허용하지 않습니다. XPath는 트리에서 노드 컬렉션만 반환할 수 있지만, [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]은 쿼리를 실행하고 개체 그래프나 XML 트리를 새 모양으로 프로젝션할 수 있습니다. [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 쿼리는 훨씬 많은 기능을 포함하며 XPath 식보다 훨씬 더 강력합니다.  
  
 XPath 식은 문자열 내에 분리되어 존재합니다. Visual Basic 컴파일러는 컴파일 타임에 XPath 식을 구문 분석할 수 없습니다. 반면, [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 쿼리 구문 분석 되 고 오늘 기본 컴파일러에서 컴파일된 합니다. 컴파일러에서는 많은 쿼리 오류를 catch할 수 있습니다.  
  
 XPath 결과는 강력한 형식이 아닙니다. 많은 경우에 XPath 식의 계산 결과는 개체이며 적절한 형식을 결정하고 필요한 경우 결과를 캐스팅하는 것은 개발자에게 달려 있습니다. 이와 반대로 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 쿼리의 프로젝션은 강력한 형식입니다.  
  
## <a name="result-ordering"></a>결과 정렬  
 XPath 1.0 권장 사항에는 XPath 식의 계산 결과인 컬렉션이 정렬되지 않는다고 나와 있습니다.  
  
 그러나 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] XPath 축 메서드에서 반환하는 컬렉션을 반복할 때 컬렉션의 노드는 문서 순서로 반환됩니다. 이는 조건자가 `preceding` 및 `preceding-sibling`과 같이 문서 순서의 역순으로 표현되는 XPath 축에 액세스하는 경우에도 해당됩니다.  
  
 이와 반대로 대부분의는 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 축은 문서 순서로 있지만 그 중에서 컬렉션을 반환 <xref:System.Xml.Linq.XNode.Ancestors%2A>및 <xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A>, 역방향 문서 순서로 컬렉션을 반환 합니다.</xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A> </xref:System.Xml.Linq.XNode.Ancestors%2A> 다음 표에서는 축을 열거하고 각 축의 컬렉션 순서를 나타냅니다.  
  
|LINQ to XML 축|정렬|  
|----------------------|--------------|  
|XContainer.DescendantNodes|문서 순서|  
|XContainer.Descendants|문서 순서|  
|XContainer.Elements|문서 순서|  
|XContainer.Nodes|문서 순서|  
|XContainer.NodesAfterSelf|문서 순서|  
|XContainer.NodesBeforeSelf|문서 순서|  
|XElement.AncestorsAndSelf|문서 순서의 역순|  
|XElement.Attributes|문서 순서|  
|XElement.DescendantNodesAndSelf|문서 순서|  
|XElement.DescendantsAndSelf|문서 순서|  
|XNode.Ancestors|문서 순서의 역순|  
|XNode.ElementsAfterSelf|문서 순서|  
|XNode.ElementsBeforeSelf|문서 순서|  
|XNode.NodesAfterSelf|문서 순서|  
|XNode.NodesBeforeSelf|문서 순서|  
  
## <a name="positional-predicates"></a>위치 조건자  
 XPath 식에서 위치 조건자는 많은 축의 경우 문서 순서로 표현되지만 `preceding`, `preceding-sibling`, `ancestor` 및 `ancestor-or-self`와 같은 역방향 축의 경우에는 문서 순서의 역순으로 표현됩니다. 예를 들어, XPath 식 `preceding-sibling::*[1]`은 바로 이전 형제를 반환합니다. 이는 최종 결과 집합이 문서 순서로 제공되는 경우에도 해당됩니다.  
  
 이와 반대로 LINQ to XML의 모든 위치 조건자는 항상 축의 순서로 표현됩니다. 예를 들어, `anElement.ElementsBeforeSelf().ToList()[0]`은 바로 이전 형제가 아니라 쿼리된 요소에 대한 부모의 첫 번째 자식 요소를 반환합니다. 또 다른 예로, `anElement.Ancestors().ToList()[0]`은 부모 요소를 반환합니다.  
  
 위의 방법은 전체 컬렉션을 유형화합니다. 이 방법이 해당 쿼리를 가장 효율적으로 작성하는 방법은 아닙니다. 해당 쿼리는 위치 조건자의 동작을 보여 주기 위해 이 방법으로 작성되었습니다. 동일한 쿼리를 작성 하는 보다 적절 한 방법을 사용 하는 것은 <xref:System.Linq.Enumerable.First%2A>메서드를 다음과 같이: `anElement.ElementsBeforeSelf().First()`.</xref:System.Linq.Enumerable.First%2A>  
  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]에서 바로 이전 요소를 찾으려는 경우 다음 식을 작성할 수 있습니다.  
  
 `ElementsBeforeSelf().Last()`  
  
## <a name="performance-differences"></a>성능 차이점  
 
          [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]에서 XPath 기능을 사용하는 XPath 쿼리의 성능은 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 쿼리의 성능보다 낮습니다.  
  
## <a name="comparison-of-composition"></a>구성 비교  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 쿼리의 구성은 XPath 식의 구성과 다소 비슷하지만 구문은 매우 다릅니다.  
  
 예를 들어, `customers`라는 변수에 요소가 있고 `CompanyName`라는 모든 자식 요소 아래에서 `Customer`이라는 손자 요소를 찾으려는 경우 다음과 같이 XPath 식을 작성할 수 있습니다.  
  
```vb  
customers.XPathSelectElements("./Customer/CompanyName")  
```  
  
 동일한 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 쿼리는 다음과 같습니다.  
  
```vb  
customers.Element("Customer").Elements("CompanyName")  
```  
  
 각 XPath 축과 유사한 LINQ to XML 축은 다음과 같습니다.  
  
|XPath 축|LINQ to XML 축|  
|----------------|----------------------|  
|child(기본 축)|<xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName></xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName>|  
|Parent(..)|<xref:System.Xml.Linq.XObject.Parent%2A?displayProperty=fullName></xref:System.Xml.Linq.XObject.Parent%2A?displayProperty=fullName>|  
|attribute axis(@)|<xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=fullName><br /><br /> 또는<br /><br /> <xref:System.Xml.Linq.XElement.Attributes%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Attributes%2A?displayProperty=fullName>|  
|ancestor 축|<xref:System.Xml.Linq.XNode.Ancestors%2A?displayProperty=fullName></xref:System.Xml.Linq.XNode.Ancestors%2A?displayProperty=fullName>|  
|ancestor-or-self 축|<xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A?displayProperty=fullName>|  
|descendant 축(//)|<xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=fullName></xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=fullName><br /><br /> 또는<br /><br /> <xref:System.Xml.Linq.XContainer.DescendantNodes%2A?displayProperty=fullName></xref:System.Xml.Linq.XContainer.DescendantNodes%2A?displayProperty=fullName>|  
|descendant-or-self|<xref:System.Xml.Linq.XElement.DescendantsAndSelf%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.DescendantsAndSelf%2A?displayProperty=fullName><br /><br /> 또는<br /><br /> <xref:System.Xml.Linq.XElement.DescendantNodesAndSelf%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.DescendantNodesAndSelf%2A?displayProperty=fullName>|  
|following-sibling|<xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A?displayProperty=fullName></xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A?displayProperty=fullName><br /><br /> 또는<br /><br /> <xref:System.Xml.Linq.XNode.NodesAfterSelf%2A?displayProperty=fullName></xref:System.Xml.Linq.XNode.NodesAfterSelf%2A?displayProperty=fullName>|  
|preceding-sibling|<xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=fullName></xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=fullName><br /><br /> 또는<br /><br /> <xref:System.Xml.Linq.XNode.NodesBeforeSelf%2A?displayProperty=fullName></xref:System.Xml.Linq.XNode.NodesBeforeSelf%2A?displayProperty=fullName>|  
|following|직접적으로 해당하는 축이 없음|  
|preceding|직접적으로 해당하는 축이 없음|  
  
## <a name="see-also"></a>참고 항목  
 [LINQ to XML에 대 한 XPath 사용자 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
