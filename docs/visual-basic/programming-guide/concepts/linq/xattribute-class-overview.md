---
title: "XAttribute 클래스 개요 (Visual Basic) | Microsoft 문서"
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
ms.assetid: 7781580a-9583-4a1b-ae1e-91c5936eb0b1
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 1ce5f4be6006908b35057854f89432471fd9f06b
ms.lasthandoff: 03/13/2017

---
# <a name="xattribute-class-overview-visual-basic"></a>XAttribute 클래스 개요 (Visual Basic)
특성은 요소와 연결된 이름/값 쌍입니다. <xref:System.Xml.Linq.XAttribute>클래스는 XML 특성을 나타냅니다.</xref:System.Xml.Linq.XAttribute>  
  
## <a name="overview"></a>개요  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]에서 특성 작업은 요소 작업과 유사합니다. 특성과 요소의 생성자는 유사합니다. 특성과 요소의 컬렉션을 검색하는 데 사용하는 메서드는 유사합니다. 특성 컬렉션의 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 쿼리 식은 요소 컬렉션의 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 쿼리 식과 매우 유사하게 보입니다.  
  
 특성이 요소에 추가된 순서는 유지됩니다. 즉, 특성을 반복하는 경우 특성은 추가된 동일한 순서로 표시됩니다.  
  
## <a name="the-xattribute-constructor"></a>XAttribute 생성자  
 다음 생성자는 <xref:System.Xml.Linq.XAttribute>클래스는 가장 일반적으로 사용 합니다:</xref:System.Xml.Linq.XAttribute>  
  
|생성자|설명|  
|-----------------|-----------------|  
|`XAttribute(XName name, object content)`|만듭니다는 <xref:System.Xml.Linq.XAttribute>개체.</xref:System.Xml.Linq.XAttribute> `name` 인수는 특성의 이름을 지정하고, `content`는 특성의 내용을 지정합니다.|  
  
### <a name="creating-an-element-with-an-attribute"></a>특성을 사용하여 요소 만들기  
 다음 코드에서는 Visual Basic에서 XML 리터럴을 사용 하 여 특성을 포함 하는 요소를 보여 줍니다.  
  
```vb  
Dim phone As XElement = <Phone Type="Home">555-555-5555</Phone>  
Console.WriteLine(phone)  
```  
  
 이 예제는 다음과 같은 출력을 생성합니다.  
  
```xml  
<Phone Type="Home">555-555-5555</Phone>  
```  
  
### <a name="functional-construction-of-attributes"></a>특성의 함수 생성  
 생성할 수 있습니다 <xref:System.Xml.Linq.XAttribute>의 생성과 함께 인라인으로 <xref:System.Xml.Linq.XElement>개체를 다음과 같이:</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XAttribute>  
  
```vb  
Dim c As XElement = _  
    <Customers>  
        <Customer>  
            <Name>John Doe</Name>  
            <PhoneNumbers>  
                <Phone type="home">555-555-5555</Phone>  
                <Phone type="work">666-666-6666</Phone>  
            </PhoneNumbers>  
        </Customer>  
    </Customers>  
Console.WriteLine(c)  
```  
  
 이 예제는 다음과 같은 출력을 생성합니다.  
  
```xml  
<Customers>  
  <Customer>  
    <Name>John Doe</Name>  
    <PhoneNumbers>  
      <Phone type="home">555-555-5555</Phone>  
      <Phone type="work">666-666-6666</Phone>  
    </PhoneNumbers>  
  </Customer>  
</Customers>  
```  
  
### <a name="attributes-are-not-nodes"></a>특성은 노드가 아님  
 특성과 요소 사이에는 차이점이 있습니다. <xref:System.Xml.Linq.XAttribute>개체 노드를 XML 트리에 않습니다.</xref:System.Xml.Linq.XAttribute> 특성은 XML 요소와 연결된 이름/값 쌍입니다. DOM(문서 개체 모델)과 대조적으로 이는 XML의 구조를 더욱 충실하게 반영합니다. 하지만 <xref:System.Xml.Linq.XAttribute>개체와 작동 하는 XML 트리 노드 실제로 <xref:System.Xml.Linq.XAttribute>개체 작업과 매우 비슷합니다 <xref:System.Xml.Linq.XElement>개체.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XAttribute>  
  
 이 차이는 주로 노드 수준에서 XML 트리 작업을 하는 코드를 작성하는 개발자에게만 중요합니다. 대부분의 개발자는 이 차이에 대해 염려하지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [LINQ to XML 프로그래밍 개요 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
