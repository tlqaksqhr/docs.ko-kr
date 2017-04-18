---
title: "방법: 요소 (LINQ to XML)의 값을 검색 (Visual Basic) | Microsoft 문서"
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
ms.assetid: 76b9b2a5-b3ba-49da-ba74-82100e1bd21c
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: d38928df51006a8db9417d34ccbe6cd03091db66
ms.lasthandoff: 03/13/2017


---
# <a name="how-to-retrieve-the-value-of-an-element-linq-to-xml-visual-basic"></a>방법: 요소 (LINQ to XML)의 값을 검색 (Visual Basic)
이 항목에서는 요소의 값을 가져오는 방법을 보여 줍니다. 두 가지 주요 방법으로 요소의 값을 가져올 수 있습니다. 캐스팅 하는 한 가지 방법은 <xref:System.Xml.Linq.XElement>또는 <xref:System.Xml.Linq.XAttribute>를 원하는 형식.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement> 명시적 변환 연산자는 요소나 특성의 내용을 지정된 형식으로 변환하고 변수에 할당합니다. 또는 사용할 수는 <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=fullName>속성 또는 <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=fullName>속성.</xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=fullName> </xref:System.Xml.Linq.XElement.Value%2A?displayProperty=fullName>  
  
 Visual basic에서 가장 좋은 방법은 사용 하 여 <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=fullName>속성.</xref:System.Xml.Linq.XElement.Value%2A?displayProperty=fullName>  
  
## <a name="example"></a>예제  
 요소의 값을 검색 하려면 캐스팅 하기만 하면는 <xref:System.Xml.Linq.XElement>개체를 원하는 형식.</xref:System.Xml.Linq.XElement> 다음과 같이 요소를 문자열로 항상 캐스팅할 수 있습니다.  
  
```vb  
Dim e As XElement = <StringElement>abcde</StringElement>  
Console.WriteLine(e)  
Console.WriteLine("Value of e:" & e.Value)  
```  
  
 이 예제는 다음과 같은 출력을 생성합니다.  
  
```  
<StringElement>abcde</StringElement>  
Value of e:abcde  
```  
  
## <a name="example"></a>예제  
 또한 요소를 문자열 이외의 형식으로 캐스팅할 수도 있습니다. 예를 들어, 정수가 포함된 요소가 있는 경우 다음 코드에서와 같이 요소를 `int`로 캐스팅할 수 있습니다.  
  
```vb  
Dim e As XElement = <Age>44</Age>  
Console.WriteLine(e)  
Console.WriteLine("Value of e:" & CInt(e))  
```  
  
 이 예제는 다음과 같은 출력을 생성합니다.  
  
```  
<Age>44</Age>  
Value of e:44  
```  
  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]provides explicit cast operators for the following data types: `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID`, and `GUID?`.  
  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]에 대 한 동일한 캐스트 연산자를 제공 <xref:System.Xml.Linq.XAttribute>개체.</xref:System.Xml.Linq.XAttribute>  
  
## <a name="example"></a>예제  
 사용할 수는 <xref:System.Xml.Linq.XElement.Value%2A>요소의 콘텐츠를 검색 하는 속성:</xref:System.Xml.Linq.XElement.Value%2A>  
  
```vb  
Dim e As XElement = <StringElement>abcde</StringElement>  
Console.WriteLine(e)  
Console.WriteLine("Value of e:" & e.Value)  
```  
  
 이 예제는 다음과 같은 출력을 생성합니다.  
  
```  
<StringElement>abcde</StringElement>  
Value of e:abcde  
```  
  
## <a name="example"></a>예제  
 요소가 있는지 확실하지 않은 경우에도 요소의 값을 검색하려는 경우가 있습니다. 이 경우에 할당 하면 캐스팅 된 요소를 nullable 형식 (중 `string` 또는 nullable 형식 중 하나는 [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)]) 요소는 할당 된 존재 하지 않는 경우, 변수로 설정 됩니다 `Nothing`합니다. 다음 코드에서는 요소 수 또는 존재 하지 않을 때 쉽습니다 사용 하는 것 보다 캐스팅을 사용 하 여 <xref:System.Xml.Linq.XElement.Value%2A>속성.</xref:System.Xml.Linq.XElement.Value%2A>  
  
```vb  
Dim root As XElement = <Root>  
                           <Child1>child 1 content</Child1>  
                           <Child2>2</Child2>  
                       </Root>  
  
' The following assignments show why it is easier to use  
' casting when the element might or might not exist.  
  
Dim c1 As String = CStr(root.Element("Child1"))  
Console.WriteLine("c1:{0}", IIf(c1 Is Nothing, "element does not exist", c1))  
  
Dim c2 As Nullable(Of Integer) = CType(root.Element("Child2"), Nullable(Of Integer))  
Console.WriteLine("c2:{0}", IIf(Not (c2.HasValue), "element does not exist", c2.ToString()))  
  
Dim c3 As String = CStr(root.Element("Child3"))  
Console.WriteLine("c3:{0}", IIf(c3 Is Nothing, "element does not exist", c3))  
  
Dim c4 As Nullable(Of Integer) = CType(root.Element("Child4"), Nullable(Of Integer))  
Console.WriteLine("c4:{0}", IIf(Not (c4.HasValue), "element does not exist", c4.ToString()))  
  
Console.WriteLine()  
  
' The following assignments show the required code when using  
' the Value property when the attribute might or might not exist.  
' Notice that this is more difficult than the casting approach.  
  
Dim e1 As XElement = root.Element("Child1")  
Dim v1 As String  
If (e1 Is Nothing) Then  
    v1 = Nothing  
Else  
    v1 = e1.Value  
End If  
Console.WriteLine("v1:{0}", IIf(v1 Is Nothing, "element does not exist", v1))  
  
Dim e2 As XElement = root.Element("Child2")  
Dim v2 As Nullable(Of Integer)  
If (e2 Is Nothing) Then  
    v2 = Nothing  
Else  
    v2 = e2.Value  
End If  
Console.WriteLine("v2:{0}", IIf(Not (v2.HasValue), "element does not exist", v2))  
  
Dim e3 As XElement = root.Element("Child3")  
Dim v3 As String  
If (e3 Is Nothing) Then  
    v3 = Nothing  
Else  
    v3 = e3.Value  
End If  
Console.WriteLine("v3:{0}", IIf(v3 Is Nothing, "element does not exist", v3))  
  
Dim e4 As XElement = root.Element("Child4")  
Dim v4 As Nullable(Of Integer)  
If (e4 Is Nothing) Then  
    v4 = Nothing  
Else  
    v4 = e4.Value  
End If  
Console.WriteLine("v4:{0}", IIf(Not (v4.HasValue), "element does not exist", v4))  
```  
  
 이 코드의 결과는 다음과 같습니다.  
  
```  
c1:child 1 content  
c2:2  
c3:element does not exist  
c4:element does not exist  
  
v1:child 1 content  
v2:2  
v3:element does not exist  
v4:element does not exist  
```  
  
 일반적으로 요소 및 특성 내용을 검색하는 데 캐스팅을 사용하면 보다 간단한 코드를 작성할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [LINQ to XML 축 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
