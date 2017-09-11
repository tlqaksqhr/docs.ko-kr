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
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 50707da956df593f176764bed94adfc6aec3dfa5
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="serializing-with-an-xml-declaration-visual-basic"></a><span data-ttu-id="5c927-102">XML 선언 (Visual Basic)으로 직렬화 하는 작업</span><span class="sxs-lookup"><span data-stu-id="5c927-102">Serializing with an XML Declaration (Visual Basic)</span></span>
<span data-ttu-id="5c927-103">이 항목에서는 serialization을 통해 XML 선언이 생성되는지 여부를 제어하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5c927-103">This topic describes how to control whether serialization generates an XML declaration.</span></span>  
  
## <a name="xml-declaration-generation"></a><span data-ttu-id="5c927-104">XML 선언 생성</span><span class="sxs-lookup"><span data-stu-id="5c927-104">XML Declaration Generation</span></span>  
 <span data-ttu-id="5c927-105">에 대 한 직렬화는 <xref:System.IO.File>또는 <xref:System.IO.TextWriter>를 사용 하는 <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName>메서드 또는 <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName>XML 선언이 생성.</xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName> </xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName> </xref:System.IO.TextWriter> </xref:System.IO.File></span><span class="sxs-lookup"><span data-stu-id="5c927-105">Serializing to a <xref:System.IO.File> or a <xref:System.IO.TextWriter> using the <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=fullName> method or the <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=fullName> method generates an XML declaration.</span></span> <span data-ttu-id="5c927-106">로 serialize 하면는 <xref:System.Xml.XmlWriter>, 작성기 설정 (에 지정 된는 <xref:System.Xml.XmlWriterSettings>개체)는 XML 선언이 생성 되는지 여부를 결정 합니다.</xref:System.Xml.XmlWriterSettings> </xref:System.Xml.XmlWriter></span><span class="sxs-lookup"><span data-stu-id="5c927-106">When you serialize to an <xref:System.Xml.XmlWriter>, the writer settings (specified in an <xref:System.Xml.XmlWriterSettings> object) determine whether an XML declaration is generated or not.</span></span>  
  
 <span data-ttu-id="5c927-107">`ToString` 메서드를 사용하여 문자열로 serialize하는 경우 생성되는 XML에는 XML 선언이 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5c927-107">If you are serializing to a string using the `ToString` method, the resulting XML will not include an XML declaration.</span></span>  
  
### <a name="serializing-with-an-xml-declaration"></a><span data-ttu-id="5c927-108">XML 선언으로 serialization</span><span class="sxs-lookup"><span data-stu-id="5c927-108">Serializing with an XML Declaration</span></span>  
 <span data-ttu-id="5c927-109">다음 예제에서는 <xref:System.Xml.Linq.XElement>, 파일에 문서를 저장 한 다음 파일을 콘솔에 출력:</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="5c927-109">The following example creates an <xref:System.Xml.Linq.XElement>, saves the document to a file, and then prints the file to the console:</span></span>  
  
```vb  
Dim root As XElement = <Root>  
                           <Child>child content</Child>  
                       </Root>  
root.Save("Root.xml")  
Dim str As String = File.ReadAllText("Root.xml")  
Console.WriteLine(str)  
```  
  
 <span data-ttu-id="5c927-110">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="5c927-110">This example produces the following output:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<Root>  
  <Child>child content</Child>  
</Root>  
```  
  
### <a name="serializing-without-an-xml-declaration"></a><span data-ttu-id="5c927-111">XML 선언을 사용하지 않고 serialize</span><span class="sxs-lookup"><span data-stu-id="5c927-111">Serializing without an XML Declaration</span></span>  
 <span data-ttu-id="5c927-112">다음 예제에서는 <xref:System.Xml.Linq.XElement> <xref:System.Xml.XmlWriter>.</xref:System.Xml.XmlWriter> </xref:System.Xml.Linq.XElement> 저장 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5c927-112">The following example shows how to save an <xref:System.Xml.Linq.XElement> to an <xref:System.Xml.XmlWriter>.</span></span>  
  
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
  
 <span data-ttu-id="5c927-113">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="5c927-113">This example produces the following output:</span></span>  
  
```xml  
<Root><Child>child content</Child></Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5c927-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5c927-114">See Also</span></span>  
 [<span data-ttu-id="5c927-115">XML 트리 (Visual Basic)를 직렬화 하는 작업</span><span class="sxs-lookup"><span data-stu-id="5c927-115">Serializing XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md)
