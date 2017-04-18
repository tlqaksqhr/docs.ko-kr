---
title: "방법: 단일 특성 (LINQ to XML)을 검색 (Visual Basic) | Microsoft 문서"
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
ms.assetid: 11b938d7-c011-4048-900e-8b9183c41c94
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 35f477ead2bdcfdf78781459f93a755dbc89e5cc
ms.lasthandoff: 03/13/2017


---
# <a name="how-to-retrieve-a-single-attribute-linq-to-xml-visual-basic"></a>방법: 단일 특성 (LINQ to XML)을 검색 (Visual Basic)
이 항목에서는 특성 이름이 제공되는 경우 요소의 단일 특성을 검색하는 방법에 대해 설명합니다. 이 방법은 특정 특성을 가진 요소를 찾으려는 경우 쿼리 식을 작성하는 데 유용합니다.  
  
 <xref:System.Xml.Linq.XElement.Attribute%2A>의 메서드는 <xref:System.Xml.Linq.XElement>반환 클래스는 <xref:System.Xml.Linq.XAttribute>지정 된 이름의.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XElement.Attribute%2A>  
  
## <a name="example"></a>예제  
 다음 예제에서는 <xref:System.Xml.Linq.XElement.Attribute%2A>메서드.</xref:System.Xml.Linq.XElement.Attribute%2A>  
  
```vb  
Dim cust As XElement = <PhoneNumbers>  
                           <Phone type="home">555-555-5555</Phone>  
                           <Phone type="work">555-555-6666</Phone>  
                       </PhoneNumbers>  
Dim elList = From el In cust...<Phone>  
For Each e As XElement In elList  
    Console.WriteLine(e.@type)  
Next  
```  
  
 이 예제에서는 트리에서 이름이 `Phone`인 하위 요소를 모두 찾은 다음 이름이 `type`인 특성을 찾습니다.  
  
 이 코드의 결과는 다음과 같습니다.  
  
```  
home  
work  
```  
  
## <a name="example"></a>예제  
 특성의 값을 검색 하려는 경우 캐스팅할 수 있습니다에 대 한와 마찬가지로 <xref:System.Xml.Linq.XElement>개체.</xref:System.Xml.Linq.XElement> 다음은 이에 대한 예입니다.  
  
```vb  
Dim cust As XElement = <PhoneNumbers>  
                           <Phone type="home">555-555-5555</Phone>  
                           <Phone type="work">555-555-6666</Phone>  
                       </PhoneNumbers>  
Dim elList As IEnumerable(Of XElement) = _  
    From el In cust...<Phone> _  
    Select el  
For Each el As XElement In elList  
    Console.WriteLine(el.@type)  
Next  
```  
  
 이 코드의 결과는 다음과 같습니다.  
  
```  
home  
work  
```  
  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]provides explicit cast operators for the <xref:System.Xml.Linq.XAttribute> class to `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID`, and `GUID?`.</xref:System.Xml.Linq.XAttribute>  
  
## <a name="example"></a>예제  
 다음 예제에서는 네임스페이스에 있는 특성에 대한 동일한 코드를 보여 줍니다. 자세한 내용은 참조 [XML 네임 스페이스 (Visual Basic) 작업](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)합니다.  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim cust As XElement = _  
            <aw:PhoneNumbers>  
                <aw:Phone aw:type="home">555-555-5555</aw:Phone>  
                <aw:Phone aw:type="work">555-555-6666</aw:Phone>  
            </aw:PhoneNumbers>  
        Dim elList As IEnumerable(Of XElement) = _  
            From el In cust...<aw:Phone> _  
            Select el  
        For Each el As XElement In elList  
            Console.WriteLine(el.@aw:type)  
        Next  
    End Sub  
End Module  
```  
  
 이 코드의 결과는 다음과 같습니다.  
  
```  
home  
work  
```  
  
## <a name="see-also"></a>참고 항목  
 [LINQ to XML 축 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
