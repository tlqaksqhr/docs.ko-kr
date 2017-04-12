---
title: "원자화 XName 및 XNamespace 개체 (LINQ to XML) (Visual Basic) | Microsoft 문서"
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
ms.assetid: 21ee7585-7df9-40b4-8c76-a12bb5f29bb3
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: b08f3116f5acb404cf2c33072ec31fbaada4e7cb
ms.lasthandoff: 03/13/2017


---
# <a name="atomized-xname-and-xnamespace-objects-linq-to-xml-visual-basic"></a>원자화 XName 및 XNamespace 개체 (LINQ to XML) (Visual Basic)
<xref:System.Xml.Linq.XName>및 <xref:System.Xml.Linq.XNamespace>개체는 *원자화*; 즉, 동일한 정규화 된 이름을 포함 하는 경우 개체를 참조 하는 동일한.</xref:System.Xml.Linq.XNamespace></xref:System.Xml.Linq.XName> 이를 통해 쿼리 성능이 향상될 수 있습니다. 두 개의 원자화된 이름이 같은지 비교하는 경우 기본 중간 언어에서 이 두 개의 참조가 같은 개체를 가리키는지 여부만 확인하면 됩니다. 기본 코드는 시간이 많이 걸리는 문자열 비교를 수행할 필요가 없습니다.  
  
## <a name="atomization-semantics"></a>원자화 의미 체계  
 원자화 하는 경우 두 개의 <xref:System.Xml.Linq.XName>개체는 동일한 로컬 이름 및 동일한 네임 스페이스에는, 같은 인스턴스를 공유 합니다.</xref:System.Xml.Linq.XName> 마찬가지로, 두 경우에서 <xref:System.Xml.Linq.XNamespace>개체에 같은 네임 스페이스 URI, 같은 인스턴스를 공유 합니다.</xref:System.Xml.Linq.XNamespace>  
  
 클래스가 원자화된 개체를 사용하려면 클래스에 대한 생성자가 public이 아니라 private이어야 합니다. 이는 생성자가 public인 경우 원자화되지 않은 개체를 생성할 수 있기 때문입니다. <xref:System.Xml.Linq.XName> <xref:System.Xml.Linq.XNamespace>클래스를 <xref:System.Xml.Linq.XName>나 <xref:System.Xml.Linq.XNamespace>.</xref:System.Xml.Linq.XNamespace> </xref:System.Xml.Linq.XName> 문자열을 변환 하는 암시적 변환 연산자를 구현</xref:System.Xml.Linq.XNamespace> 하 고</xref:System.Xml.Linq.XName> 이를 통해 이러한 개체의 인스턴스를 가져올 수 있습니다. 생성자는 액세스할 수 없으므로 생성자를 사용하여 인스턴스를 가져올 수 없습니다.  
  
 <xref:System.Xml.Linq.XName>및 <xref:System.Xml.Linq.XNamespace>도 두 개의 비교 되는 개체가 참조 하는지 동일한 인스턴스를 확인 하는 같음 및 같지 않음 연산자를 구현 합니다.</xref:System.Xml.Linq.XNamespace></xref:System.Xml.Linq.XName>  
  
## <a name="example"></a>예제  
 다음 코드에서는 일부 <xref:System.Xml.Linq.XElement>개체와 동일한 이름이 같은 인스턴스를 공유 하는 방법을 보여 줍니다.</xref:System.Xml.Linq.XElement>  
  
```vb  
Dim r1 As New XElement("Root", "data1")  
Dim r2 As XElement = XElement.Parse("<Root>data2</Root>")  
  
If DirectCast(r1.Name, Object) = DirectCast(r2.Name, Object) Then  
    Console.WriteLine("r1 and r2 have names that refer to the same instance.")  
Else  
    Console.WriteLine("Different")  
End If  
  
Dim n As XName = "Root"  
  
If DirectCast(n, Object) = DirectCast(r1.Name, Object) Then  
    Console.WriteLine("The name of r1 and the name in 'n' refer to the same instance.")  
Else  
    Console.WriteLine("Different")  
End If  
  
```  
  
 이 예제는 다음과 같은 출력을 생성합니다.  
  
```  
r1 and r2 have names that refer to the same instance.  
The name of r1 and the name in 'n' refer to the same instance.  
```  
  
 앞서 언급 했 듯이 원자화 된 개체의 이점은 사용 하는 축 메서드 중 하나를 사용 하는 경우는 <xref:System.Xml.Linq.XName>를 매개 변수로 축 메서드 여부만 확인 두 이름이 참조 하는지 원하는 요소를 선택 하는 같은 인스턴스.</xref:System.Xml.Linq.XName>  
  
 다음 예에서는 전달 된 <xref:System.Xml.Linq.XName>에 <xref:System.Xml.Linq.XContainer.Descendants%2A>원자화 패턴으로 인해 다음 더 나은 성능을 메서드 호출.</xref:System.Xml.Linq.XContainer.Descendants%2A> </xref:System.Xml.Linq.XName>  
  
```vb  
Dim root As New XElement("Root", New XElement("C1", 1), New XElement("Z1", New XElement("C1", 2), New XElement("C1", 1)))  
  
Dim query = From e In root.Descendants("C1") Where CInt(e) = 1e  
  
For Each z As var In query  
    Console.WriteLine(z)  
Next  
```  
  
 이 예제는 다음과 같은 출력을 생성합니다.  
  
```  
<C1>1</C1>  
<C1>1</C1>  
```  
  
## <a name="see-also"></a>참고 항목  
 [성능 (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/performance-linq-to-xml.md)
