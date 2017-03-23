---
title: "XML 선언 (Visual Basic)으로 직렬화 하는 작업 | Microsoft 문서"
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
ms.assetid: 8726f79e-2bb0-4ba0-969d-197cca591647
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
ms.openlocfilehash: 373df9b28ae7434d33ae81eba701d289cf1aa4f7
ms.lasthandoff: 03/13/2017

---
# <a name="serializing-with-an-xml-declaration-visual-basic"></a>XML 선언 (Visual Basic)으로 직렬화 하는 작업
이 항목에서는 serialization을 통해 XML 선언이 생성되는지 여부를 제어하는 방법에 대해 설명합니다.  
  
## <a name="xml-declaration-generation"></a>XML 선언 생성  
 에 대 한 직렬화는 <xref:System.IO.File>또는 <xref:System.IO.TextWriter>를 사용 하는 <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName>메서드 또는 <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName>XML 선언이 생성.</xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName> </xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName> </xref:System.IO.TextWriter> </xref:System.IO.File> 로 serialize 하면는 <xref:System.Xml.XmlWriter>, 작성기 설정 (에 지정 된는 <xref:System.Xml.XmlWriterSettings>개체)는 XML 선언이 생성 되는지 여부를 결정 합니다.</xref:System.Xml.XmlWriterSettings> </xref:System.Xml.XmlWriter>  
  
 `ToString` 메서드를 사용하여 문자열로 serialize하는 경우 생성되는 XML에는 XML 선언이 포함되지 않습니다.  
  
### <a name="serializing-with-an-xml-declaration"></a>XML 선언으로 serialization  
 다음 예제에서는 <xref:System.Xml.Linq.XElement>, 파일에 문서를 저장 한 다음 파일을 콘솔에 출력:</xref:System.Xml.Linq.XElement>  
  
```vb  
Dim root As XElement = <Root>  
                           <Child>child content</Child>  
                       </Root>  
root.Save("Root.xml")  
Dim str As String = File.ReadAllText("Root.xml")  
Console.WriteLine(str)  
```  
  
 이 예제는 다음과 같은 출력을 생성합니다.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<Root>  
  <Child>child content</Child>  
</Root>  
```  
  
### <a name="serializing-without-an-xml-declaration"></a>XML 선언을 사용하지 않고 serialize  
 다음 예제에서는 <xref:System.Xml.Linq.XElement> <xref:System.Xml.XmlWriter>.</xref:System.Xml.XmlWriter> </xref:System.Xml.Linq.XElement> 저장 하는 방법을 보여 줍니다.  
  
```vb  
Dim sb As StringBuilder = New StringBuilder()  
Dim xws As XmlWriterSettings = New XmlWriterSettings()  
xws.OmitXmlDeclaration = True  
  
Using xw As XmlWriter = XmlWriter.Create(sb, xws)  
    Dim root = <Root>  
                   <Child>child content</Child>  
               </Root>  
    root.Save(xw)  
End Using  
Console.WriteLine(sb.ToString())  
```  
  
 이 예제는 다음과 같은 출력을 생성합니다.  
  
```xml  
<Root><Child>child content</Child></Root>  
```  
  
## <a name="see-also"></a>참고 항목  
 [XML 트리 (Visual Basic)를 직렬화 하는 작업](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md)
