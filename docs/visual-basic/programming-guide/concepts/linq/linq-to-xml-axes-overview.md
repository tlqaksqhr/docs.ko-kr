---
title: "LINQ to XML 축 개요 (Visual Basic) | Microsoft 문서"
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
ms.assetid: 9161f151-cfa8-4408-94ba-08a9ba3a486d
caps.latest.revision: 4
author: stevehoag
ms.author: shoag
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: b127aa6b443e865c76831d886f110550ec785e9b
ms.lasthandoff: 03/13/2017


---
# <a name="linq-to-xml-axes-overview-visual-basic"></a>LINQ to XML 축 개요 (Visual Basic)
XML 트리를 만들거나 XML 문서를 XML 트리에 로드한 후 XML 트리를 쿼리하여 요소와 특성을 찾고 해당 값을 검색할 수 있습니다. 통해 컬렉션을 검색 된 *축 메서드*라고도 *축*합니다. 축 중 일부는 메서드는 <xref:System.Xml.Linq.XElement>및 <xref:System.Xml.Linq.XDocument>반환 하는 클래스 <xref:System.Collections.Generic.IEnumerable%601>컬렉션.</xref:System.Collections.Generic.IEnumerable%601> </xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> <xref:System.Xml.Linq.Extensions>클래스</xref:System.Xml.Linq.Extensions> 의 확장 메서드 축 중 일부는 확장명 메서드로 구현되는 축은 컬렉션에 대해 작동하고 컬렉션을 반환합니다.  
  
 에 설명 된 대로 [XElement 클래스 개요](http://msdn.microsoft.com/library/d35180fe-7016-4895-9bfc-ba1e3f7875ec), <xref:System.Xml.Linq.XElement>개체는 단일 요소 노드를 나타냅니다.</xref:System.Xml.Linq.XElement> 요소의 내용은 복합 요소(구조화된 내용이라고도 함)이거나 단순 요소일 수 있습니다. 단순 요소는 비어 있거나 값을 포함할 수 있습니다. 노드에 구조화된 내용이 포함되어 있으면 다양한 축 메서드를 사용하여 하위 요소의 열거형을 검색할 수 있습니다. 가장 일반적으로 사용 되는 축 메서드는 <xref:System.Xml.Linq.XContainer.Elements%2A>및 <xref:System.Xml.Linq.XContainer.Descendants%2A>.</xref:System.Xml.Linq.XContainer.Descendants%2A> </xref:System.Xml.Linq.XContainer.Elements%2A>  
  
 컬렉션을 반환하는 축 메서드 외에도 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 쿼리에서 일반적으로 사용하는 두 메서드가 있습니다. <xref:System.Xml.Linq.XContainer.Element%2A>메서드는 단일 <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement> 를 반환합니다 합니다.</xref:System.Xml.Linq.XContainer.Element%2A> <xref:System.Xml.Linq.XElement.Attribute%2A>메서드는 단일 <xref:System.Xml.Linq.XAttribute>.</xref:System.Xml.Linq.XAttribute> 를 반환합니다 합니다.</xref:System.Xml.Linq.XElement.Attribute%2A>  
  
 많은 용도를 위해 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 쿼리는 트리를 검사하고, 트리에서 데이터를 추출하고, 트리를 변환하는 가장 강력한 방법을 제공합니다. [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]쿼리를 구현 하는 개체에 대해 작동 <xref:System.Collections.Generic.IEnumerable%601>, 및 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 반환 축은 <xref:System.Collections.Generic.IEnumerable%601>의 <xref:System.Xml.Linq.XElement>컬렉션 및 <xref:System.Collections.Generic.IEnumerable%601>의 <xref:System.Xml.Linq.XAttribute>컬렉션.</xref:System.Xml.Linq.XAttribute> </xref:System.Collections.Generic.IEnumerable%601> </xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601> </xref:System.Collections.Generic.IEnumerable%601> 쿼리를 수행하려면 이러한 컬렉션이 필요합니다.  
  
 요소와 특성의 컬렉션을 검색하는 축 메서드 외에도 트리를 매우 자세히 반복하는 데 사용할 수 있는 축 메서드가 있습니다. 예를 들어, 요소와 특성을 처리하는 대신 트리의 노드로 작업할 수 있습니다. 노드는 요소와 특성보다 세부적인 단위입니다. 노드로 작업할 때 XML 주석, 텍스트 노드, 처리 명령 등을 검사할 수 있습니다. 이 기능은 워드 프로세서를 작성 중인 사용자가 문서를 XML로 저장하려는 경우 등에 중요합니다. 그러나 XML 프로그래머의 대다수는 요소, 특성 및 해당 값에 주로 관심이 있습니다.  
  
## <a name="methods-for-retrieving-a-collection-of-elements"></a>요소 컬렉션을 검색하는 메서드  
 다음은 요약의 메서드는 <xref:System.Xml.Linq.XElement>클래스 (또는 해당 기본 클래스)에 대해 호출 하는 <xref:System.Xml.Linq.XElement>요소의 컬렉션을 반환 합니다.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XElement>  
  
|메서드|설명|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XNode.Ancestors%2A?displayProperty=fullName></xref:System.Xml.Linq.XNode.Ancestors%2A?displayProperty=fullName>|반환 된 <xref:System.Collections.Generic.IEnumerable%601>의 <xref:System.Xml.Linq.XElement>이 요소의 상위 항목.</xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601> <xref:System.Collections.Generic.IEnumerable%601> <xref:System.Xml.Linq.XElement>지정 된 <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName> 있는 상위 항목</xref:System.Xml.Linq.XElement> 의</xref:System.Collections.Generic.IEnumerable%601> 오버 로드를 반환합니다.|  
|<xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=fullName></xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=fullName>|반환 된 <xref:System.Collections.Generic.IEnumerable%601>의 <xref:System.Xml.Linq.XElement>이 요소의 하위 요소.</xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601> <xref:System.Collections.Generic.IEnumerable%601> <xref:System.Xml.Linq.XElement>지정 된 <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName> 있는 하위 항목</xref:System.Xml.Linq.XElement> 의</xref:System.Collections.Generic.IEnumerable%601> 오버 로드를 반환합니다.|  
|<xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName></xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName>|반환 된 <xref:System.Collections.Generic.IEnumerable%601>의 <xref:System.Xml.Linq.XElement>이 요소의 자식 요소입니다.</xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601> <xref:System.Collections.Generic.IEnumerable%601> <xref:System.Xml.Linq.XElement>자식 요소에 지정 된 <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName> 있는</xref:System.Xml.Linq.XElement> 의</xref:System.Collections.Generic.IEnumerable%601> 오버 로드를 반환합니다.|  
|<xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A?displayProperty=fullName></xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A?displayProperty=fullName>|반환 된 <xref:System.Collections.Generic.IEnumerable%601>의 <xref:System.Xml.Linq.XElement>이 요소 뒤에 오는 요소.</xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601> <xref:System.Collections.Generic.IEnumerable%601> <xref:System.Xml.Linq.XElement>요소에 지정 된 <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName> 있는이 요소 뒤</xref:System.Xml.Linq.XElement> 의</xref:System.Collections.Generic.IEnumerable%601> 오버 로드를 반환합니다.|  
|<xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=fullName></xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=fullName>|반환 된 <xref:System.Collections.Generic.IEnumerable%601>의 <xref:System.Xml.Linq.XElement>이 요소 앞에 오는 요소.</xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601> <xref:System.Collections.Generic.IEnumerable%601> <xref:System.Xml.Linq.XElement>요소에 지정 된 <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName> 있는이 요소 앞</xref:System.Xml.Linq.XElement> 의</xref:System.Collections.Generic.IEnumerable%601> 오버 로드를 반환합니다.|  
|<xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A?displayProperty=fullName>|반환 된 <xref:System.Collections.Generic.IEnumerable%601>의 <xref:System.Xml.Linq.XElement>이 요소와 해당 상위의.</xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601> <xref:System.Collections.Generic.IEnumerable%601> <xref:System.Xml.Linq.XElement>요소에 지정 된 <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName> 있는</xref:System.Xml.Linq.XElement> 의</xref:System.Collections.Generic.IEnumerable%601> 오버 로드를 반환합니다.|  
|<xref:System.Xml.Linq.XElement.DescendantsAndSelf%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.DescendantsAndSelf%2A?displayProperty=fullName>|반환 된 <xref:System.Collections.Generic.IEnumerable%601>의 <xref:System.Xml.Linq.XElement>이 요소와 해당 하위 항목입니다.</xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601> <xref:System.Collections.Generic.IEnumerable%601> <xref:System.Xml.Linq.XElement>요소에 지정 된 <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName> 있는</xref:System.Xml.Linq.XElement> 의</xref:System.Collections.Generic.IEnumerable%601> 오버 로드를 반환합니다.|  
  
## <a name="method-for-retrieving-a-single-element"></a>단일 요소를 검색하는 메서드  
 단일 자식을 검색 하는 다음 메서드는 <xref:System.Xml.Linq.XElement>개체.</xref:System.Xml.Linq.XElement>  
  
|메서드|설명|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XContainer.Element%2A?displayProperty=fullName></xref:System.Xml.Linq.XContainer.Element%2A?displayProperty=fullName>|첫 번째 자식 <xref:System.Xml.Linq.XElement> <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName> 지정된 된 개체</xref:System.Xml.Linq.XElement> 를 반환합니다.|  
  
## <a name="method-for-retrieving-a-collection-of-attributes"></a>특성 컬렉션을 검색하는 메서드  
 특성을 검색 하는 다음 메서드는 <xref:System.Xml.Linq.XElement>개체.</xref:System.Xml.Linq.XElement>  
  
|메서드|설명|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XElement.Attributes%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Attributes%2A?displayProperty=fullName>|반환 된 <xref:System.Collections.Generic.IEnumerable%601>의 <xref:System.Xml.Linq.XAttribute>의 모든 특성.</xref:System.Xml.Linq.XAttribute> </xref:System.Collections.Generic.IEnumerable%601>|  
  
## <a name="method-for-retrieving-a-single-attribute"></a>단일 특성을 검색하는 메서드  
 단일 특성을 검색 하는 다음 메서드는 <xref:System.Xml.Linq.XElement>개체.</xref:System.Xml.Linq.XElement>  
  
|메서드|설명|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=fullName>|<xref:System.Xml.Linq.XAttribute>지정 된 <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName> 가</xref:System.Xml.Linq.XAttribute> 반환|  
  
## <a name="see-also"></a>참고 항목  
 [LINQ to XML 축 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
