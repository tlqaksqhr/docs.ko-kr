---
title: "XML 선언으로 serialize(C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: c237fa4a-a042-40fd-886f-17b54c66bb75
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 44d7f199508abd6d60bb554806409cebb1b7f845
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="serializing-with-an-xml-declaration-c"></a><span data-ttu-id="a6ef2-102">XML 선언으로 serialize(C#)</span><span class="sxs-lookup"><span data-stu-id="a6ef2-102">Serializing with an XML Declaration (C#)</span></span>
<span data-ttu-id="a6ef2-103">이 항목에서는 serialization을 통해 XML 선언이 생성되는지 여부를 제어하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a6ef2-103">This topic describes how to control whether serialization generates an XML declaration.</span></span>  
  
## <a name="xml-declaration-generation"></a><span data-ttu-id="a6ef2-104">XML 선언 생성</span><span class="sxs-lookup"><span data-stu-id="a6ef2-104">XML Declaration Generation</span></span>  
 <span data-ttu-id="a6ef2-105"><xref:System.IO.File> 메서드 또는 <xref:System.IO.TextWriter> 메서드를 사용하여 <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType> 또는 <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType>로 serialize하면 XML 선언이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6ef2-105">Serializing to a <xref:System.IO.File> or a <xref:System.IO.TextWriter> using the <xref:System.Xml.Linq.XElement.Save%2A?displayProperty=nameWithType> method or the <xref:System.Xml.Linq.XDocument.Save%2A?displayProperty=nameWithType> method generates an XML declaration.</span></span> <span data-ttu-id="a6ef2-106"><xref:System.Xml.XmlWriter>로 serialize하면 <xref:System.Xml.XmlWriterSettings> 개체에 지정된 작성기 설정에 따라 XML 선언이 생성되는지 여부가 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6ef2-106">When you serialize to an <xref:System.Xml.XmlWriter>, the writer settings (specified in an <xref:System.Xml.XmlWriterSettings> object) determine whether an XML declaration is generated or not.</span></span>  
  
 <span data-ttu-id="a6ef2-107">`ToString` 메서드를 사용하여 문자열로 serialize하는 경우 생성되는 XML에는 XML 선언이 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a6ef2-107">If you are serializing to a string using the `ToString` method, the resulting XML will not include an XML declaration.</span></span>  
  
### <a name="serializing-with-an-xml-declaration"></a><span data-ttu-id="a6ef2-108">XML 선언으로 serialization</span><span class="sxs-lookup"><span data-stu-id="a6ef2-108">Serializing with an XML Declaration</span></span>  
 <span data-ttu-id="a6ef2-109">다음 예제에서는 <xref:System.Xml.Linq.XElement>를 만들고 문서를 파일에 저장한 다음 파일을 콘솔에 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="a6ef2-109">The following example creates an <xref:System.Xml.Linq.XElement>, saves the document to a file, and then prints the file to the console:</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Child", "child content")  
);  
root.Save("Root.xml");  
string str = File.ReadAllText("Root.xml");  
Console.WriteLine(str);  
```  
  
 <span data-ttu-id="a6ef2-110">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a6ef2-110">This example produces the following output:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<Root>  
  <Child>child content</Child>  
</Root>  
```  
  
### <a name="serializing-without-an-xml-declaration"></a><span data-ttu-id="a6ef2-111">XML 선언을 사용하지 않고 serialize</span><span class="sxs-lookup"><span data-stu-id="a6ef2-111">Serializing without an XML Declaration</span></span>  
 <span data-ttu-id="a6ef2-112">다음 예제에서는 <xref:System.Xml.Linq.XElement>를 <xref:System.Xml.XmlWriter>에 저장하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a6ef2-112">The following example shows how to save an <xref:System.Xml.Linq.XElement> to an <xref:System.Xml.XmlWriter>.</span></span>  
  
```csharp  
StringBuilder sb = new StringBuilder();  
XmlWriterSettings xws = new XmlWriterSettings();  
xws.OmitXmlDeclaration = true;  
  
using (XmlWriter xw = XmlWriter.Create(sb, xws)) {  
    XElement root = new XElement("Root",  
        new XElement("Child", "child content")  
    );  
    root.Save(xw);  
}  
Console.WriteLine(sb.ToString());  
```  
  
 <span data-ttu-id="a6ef2-113">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a6ef2-113">This example produces the following output:</span></span>  
  
```xml  
<Root><Child>child content</Child></Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a6ef2-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a6ef2-114">See Also</span></span>  
 [<span data-ttu-id="a6ef2-115">XML 트리 serialize(C#)</span><span class="sxs-lookup"><span data-stu-id="a6ef2-115">Serializing XML Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/serializing-xml-trees.md)
