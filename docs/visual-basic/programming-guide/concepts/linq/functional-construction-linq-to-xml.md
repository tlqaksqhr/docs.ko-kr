---
title: "함수 생성 (LINQ to XML) (Visual Basic) | Microsoft 문서"
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
ms.assetid: feac4273-39ab-43ae-bab7-4059c807a785
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 9fa8cb3c97a1e23a863296c828c82b240e9ab5db
ms.lasthandoff: 03/13/2017

---
# <a name="functional-construction-linq-to-xml-visual-basic"></a>함수 생성 (LINQ to XML) (Visual Basic)
[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]호출 하는 XML 요소를 만드는 강력한 방법을 제공 *함수 생성*합니다. 함수 생성은 단일 문으로 XML 트리를 만드는 기능입니다.  
  
 함수 생성을 가능하게 하는 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 프로그래밍 인터페이스의 몇 가지 주요 기능은 다음과 같습니다.  
  
-   <xref:System.Xml.Linq.XElement>생성자는 다양 한 유형의 콘텐츠에 대 한 인수를 사용 합니다.</xref:System.Xml.Linq.XElement> 예를 들어 다른 전달할 수 있습니다 <xref:System.Xml.Linq.XElement>자식 요소가 있는 개체입니다.</xref:System.Xml.Linq.XElement> 전달할 수는 <xref:System.Xml.Linq.XAttribute>요소의 특성이 되는 개체입니다.</xref:System.Xml.Linq.XAttribute> 또는 문자열로 변환되고 요소의 텍스트 내용이 되는 다른 모든 형식의 개체를 전달할 수 있습니다.  
  
-   <xref:System.Xml.Linq.XElement>생성자는 `params` 형식의 배열을 <xref:System.Object>생성자에 임의 개수의 개체를 전달할 수 있도록,.</xref:System.Object> </xref:System.Xml.Linq.XElement> 따라서 복잡한 내용을 가진 요소를 만들 수 있습니다.  
  
-   개체를 구현 하는 경우 <xref:System.Collections.Generic.IEnumerable%601>, 개체의 컬렉션이 열거 되 고 컬렉션의 모든 항목이 추가 됩니다.</xref:System.Collections.Generic.IEnumerable%601> 컬렉션에 있으면 <xref:System.Xml.Linq.XElement>또는 <xref:System.Xml.Linq.XAttribute>개체를 컬렉션의 각 항목은 개별적으로 추가 됩니다.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement> 이것은 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 쿼리의 결과를 생성자에 전달할 수 있도록 하기 때문에 중요합니다.  
  
 예를 들면 다음과 같습니다.  
  
 이러한 기능을 사용 하 여 XML 트리를 만드는 및의 결과 사용 하는 코드를 작성할 XML 리터럴을 사용 하는 코드를 작성할 수 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] XML 트리를 만들 때 쿼리:  
  
```vb  
Dim srcTree As XElement = _  
    <Root>  
        <Element>1</Element>  
        <Element>2</Element>  
        <Element>3</Element>  
        <Element>4</Element>  
        <Element>5</Element>  
    </Root>  
Dim xmlTree As XElement = _  
    <Root>  
        <Child>1</Child>  
        <Child>2</Child>  
        <%= From el In srcTree.Elements() _  
            Where CInt(el) > 2 _  
            Select el %>  
    </Root>  
Console.WriteLine(xmlTree)  
```  
  
 이 예제는 다음과 같은 출력을 생성합니다.  
  
```xml  
<Root>  
  <Child>1</Child>  
  <Child>2</Child>  
  <Element>3</Element>  
  <Element>4</Element>  
  <Element>5</Element>  
</Root>  
```  
  
## <a name="see-also"></a>참고 항목  
 [XML 트리 (Visual Basic) 만들기](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md)
